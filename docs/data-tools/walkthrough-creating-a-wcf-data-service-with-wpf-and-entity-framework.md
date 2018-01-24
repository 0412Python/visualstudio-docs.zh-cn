---
title: "演练： 创建带有适用于 WPF 和实体框架的 WCF 数据服务 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data services in Visual Studio
- WCF Data Services, Visual Studio
- ADO.NET Data Services, Visual Studio
- WCF data services in Visual Studio
ms.assetid: da66ad1b-a25d-485c-af13-2d18f0422e3d
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: c4db93f300c47bf3a09dac2fbf9d5b1f4bc17108
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2018
---
# <a name="walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework"></a>演练： 创建带有适用于 WPF 和实体框架的 WCF 数据服务
本演练演示如何创建一个简单[!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]承载于[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]Web 应用程序，然后从 Windows 窗体应用程序访问它。  
  
在此演练中，将：  
  
-   创建 Web 应用程序以承载 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]。  
  
-   创建一个表示 Northwind 数据库中 Customers 表的 [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]。  
  
-   创建 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]。  
  
-   创建一个客户端应用程序，并添加对 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]的引用。  
  
-   启用对该服务的数据绑定并生成用户界面。  
  
-   可以选择向应用程序添加筛选功能。  
  
## <a name="prerequisites"></a>系统必备  
本演练使用 SQL Server Express LocalDB 和 Northwind 示例数据库。  
  
1.  如果你没有 SQL Server Express LocalDB，将其安装从[SQL Server Express 下载页面](https://www.microsoft.com/sql-server/sql-server-editions-express)，或通过**Visual Studio Installer**。 在 Visual Studio 安装程序中，SQL Server Express LocalDB 可以安装的一部分**数据存储和处理**工作负荷，也可以作为单个组件。  
  
2.  按照这些步骤来安装 Northwind 示例数据库：  

    1. 在 Visual Studio 中，打开**SQL Server 对象资源管理器**窗口。 (SQL Server 对象资源管理器安装的一部分**数据存储和处理**在 Visual Studio 安装程序中的工作负荷。)展开**SQL Server**节点。 LocalDB 实例上右键单击并选择**新查询...**.  

       查询编辑器窗口将打开。  

    2. 复制[Northwind TRANSACT-SQL 脚本](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true)到剪贴板。 此 T-SQL 脚本从头创建 Northwind 数据库，并使用数据填充它。  

    3. 将 T-SQL 脚本粘贴到查询编辑器中，，然后选择**执行**按钮。  

       短时间内之后, 执行完查询和创建 Northwind 数据库。  
  
## <a name="creating-the-service"></a>创建服务  
若要创建 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]，你将添加一个 Web 项目，创建一个[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]，然后通过此模型创建服务。  
  
首先，将添加一个 Web 项目以承载服务。  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-create-the-web-project"></a>创建 Web 项目  
  
1.  在菜单栏上，选择**文件**，**新建**，**项目**。  
  
2.  在**新项目**对话框框中，展开**Visual Basic**或**Visual C#**和**Web**节点，然后选择**ASP。NET Web 应用程序**模板。  
  
3.  在**名称**文本框中，输入**NorthwindWeb**，然后选择**确定**按钮。  
  
4.  在**新建 ASP.NET 项目**对话框中，在**选择模板**列表中，选择**空**，然后选择**确定**按钮。  
  
在下一步，你将创建[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]表示 Northwind 数据库中的客户表。  
  
#### <a name="to-create-the-entity-data-model"></a>创建实体数据模型  
  
1.  在菜单栏上，选择**项目**，**添加新项**。  
  
2.  在**添加新项**对话框框中，选择**数据**节点，然后选择**ADO.NET 实体数据模型**项。  
  
3.  在**名称**文本框中，输入`NorthwindModel`，然后选择**添加**按钮。  
  
     此时将显示实体数据模型向导。  
  
4.  在实体数据模型向导中，在**选择模型内容**页上，选择**EF 设计器从数据库**项，然后依次**下一步**按钮。  
  
5.  在 **“选择你的数据连接”** 页上执行下列步骤之一：  
  
    -   如果下拉列表中包含到 Northwind 示例数据库的数据连接，请选择该连接。  
  
         或  
  
    -   选择**新连接**按钮以配置一个新的数据连接。 有关详细信息，请参阅[添加新连接](../data-tools/add-new-connections.md)。  
  
6.  如果数据库需要密码，请选择**是，在连接字符串中包含敏感数据**选项按钮，，然后选择**下一步**按钮。  
  
    > [!NOTE]
    >  如果显示一个对话框，选择**是**将文件保存到你的项目。  
  
7.  上**选择你的版本**页上，选择**Entity Framework 5.0**选项按钮，，然后选择**下一步**按钮。  
  
    > [!NOTE]
    >  为了使用具有 WCF 服务的 Entity Framework 6 的最新版本，你将需要安装 WCF Data Services Entity Framework 提供程序 NuGet 包。 请参阅[使用 WCF 数据服务 5.6.0 与 Entity Framework 6 +](http://blogs.msdn.com/b/odatateam/archive/2013/10/02/using-wcf-data-services-5-6-0-with-entity-framework-6.aspx)。  
  
8.  上**选择数据库对象**页上，展开**表**节点中，选择**客户**复选框，然后依次**完成**按钮。  
  
     随即显示实体模型关系图，NorthwindModel.edmx 文件也将添加到项目中。  
  
在下一步，你将创建并测试数据服务。  
  
#### <a name="to-create-the-data-service"></a>创建数据服务  
  
1.  在菜单栏上，选择**项目**，**添加新项**。  
  
2.  在**添加新项**对话框框中，选择**Web**节点，然后选择**WCF 数据服务 5.6**项。  
  
3.  在**名称**文本框中，输入`NorthwindCustomers`，然后选择**添加**按钮。  
  
     NorthwindCustomers.svc 文件将显示在**代码编辑器**。  
  
4.  在**代码编辑器**，定位到第一个`TODO:`注释并将替换为以下代码：  
  
     [!code-vb[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.cs)]  
  
5.  使用下面的代码替换 `InitializeService` 事件处理程序中的注释：  
  
     [!code-vb[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.cs)]  
  
6.  在菜单栏上，选择**调试**，**启动但不调试**运行该服务。 此时将打开一个浏览窗口，并显示该服务的 XML 架构。  
  
7.  在**地址**栏上，输入`Customers`NorthwindCustomers.svc 的 URL 的末尾，然后选择**ENTER**密钥。  
  
     Customers 表中的数据将以 XML 表示形式显示。  
  
    > [!NOTE]
    >  某些情况下，Internet Explorer 会将数据错误解释为 RSS 源。 必须确保禁用显示 RSS 源的选项。 有关详细信息，请参阅[服务引用疑难解答](../data-tools/troubleshooting-service-references.md)。  
  
8.  关闭浏览器窗口。  
  
在接下来的步骤中，将创建一个 Windows 窗体客户端应用程序以使用该服务。  
  
## <a name="creating-the-client-application"></a>创建客户端应用程序  
 若要创建客户端应用程序，你将另外添加一个项目，添加对该项目的服务引用，配置数据源，并创建一个用户界面以显示服务中的数据。  
  
 在第一个步骤中，你将 Windows 窗体项目添加到解决方案中，并将其设置为启动项目。  
  
#### <a name="to-create-the-client-application"></a>创建客户端应用程序  
  
1.  在菜单栏上，选择文件，**添加**，**新项目**。  
  
2.  在**新项目**对话框框中，展开**Visual Basic**或**Visual C#**节点，然后选择**Windows**节点，然后选择**Windows 窗体应用程序**。  
  
3.  在“名称”文本框中，输入 `NorthwindClient`，然后选择“确定”按钮。  
  
4.  在**解决方案资源管理器**，选择**NorthwindClient**项目节点。  
  
5.  在菜单栏上，选择**项目**，**设为启动项目**。  
  
在下一步，你将添加到的服务引用[!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]Web 项目中。  
  
#### <a name="to-add-a-service-reference"></a>添加服务引用  
  
1.  在菜单栏上，选择**项目**，**添加服务引用**。  
  
2.  在**添加服务引用**对话框框中，选择**发现**按钮。  
  
     NorthwindCustomers 服务的 URL 显示在**地址**字段。  
  
3.  选择**确定**按钮以添加服务引用。  
  
在下一步的步骤中，你将配置数据源以启用数据绑定到服务。  
  
#### <a name="to-enable-data-binding-to-the-service"></a>启用对服务的数据绑定  
  
1.  在菜单栏上，选择**视图**，**其他窗口**，**数据源**。  
  
2.  在**数据源**窗口中，选择**添加新数据源**按钮。  
  
3.  上**选择数据源类型**页**数据源配置向导**，选择**对象**，然后选择**下一步**按钮.  
  
4.  上**选择数据对象**页上，展开**NorthwindClient**节点，然后展开**NorthwindClient.ServiceReference1**节点。  
  
5.  选择**客户**复选框，然后依次**完成**按钮。  
  
在下一步，你将创建将显示从服务的数据的用户界面。  
  
#### <a name="to-create-the-user-interface"></a>创建用户界面  
  
1.  在**数据源**窗口中，打开快捷菜单**客户**节点，然后选择**复制**。  
  
2.  在**Form1.vb**或**Form1.cs**窗体设计器，打开快捷菜单，选择**粘贴**。  
  
     一个 <xref:System.Windows.Forms.DataGridView> 控件、一个 <xref:System.Windows.Forms.BindingSource> 组件以及一个 <xref:System.Windows.Forms.BindingNavigator> 组件将添加到窗体中。  
  
3.  选择**CustomersDataGridView**控件，然后在**属性**窗口集**停靠**属性**填充**。  
  
4.  在**解决方案资源管理器**，打开快捷菜单**Form1**节点，然后选择**查看代码**以打开代码编辑器中，并添加以下 Imports 或 Using 语句文件的顶部：  
  
    ```vb  
    Imports NorthwindClient.ServiceReference1  
    ```  
  
    ```csharp  
    using NorthwindClient.ServiceReference1;  
    ```  
  
5.  将以下代码添加到 `Form1_Load` 事件处理程序中：  
  
    ```vb  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
            Dim proxy As New NorthwindEntities _  
    (New Uri("http://localhost:53161/NorthwindCustomers.svc/"))  
            Me.CustomersBindingSource.DataSource = proxy.Customers  
        End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(object sender, EventArgs e)  
    {  
    NorthwindEntities proxy = new NorthwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc/"));  
    this.CustomersBindingSource.DataSource = proxy.Customers;  
    }  
  
    ```  
  
6.  在**解决方案资源管理器**，打开 NorthwindCustomers.svc 文件的快捷菜单，选择**用浏览器查看**。 此时将打开 Internet Explorer，并显示该服务的 XML 架构。  
  
7.  从 Internet Explorer 地址栏中复制 URL。  
  
8.  在步骤 4 中添加的代码中，选择 `http://localhost:53161/NorthwindCustomers.svc/` 并使用刚刚复制的 URL 替换它。  
  
9. 在菜单栏上，选择**调试**，**启动调试**运行该应用程序。 此时将显示客户信息。  
  
 现在，你有了一个可以使用的应用程序，该应用程序将显示 NorthwindCustomers 服务中的客户的列表。 如果希望通过该服务公开其他数据，则可以修改[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]以包括 Northwind 数据库中的其他表。  
  
在下一个可选步骤中，将学习如何筛选服务返回的数据。  
  
## <a name="adding-filtering-capabilities"></a>添加筛选功能  
 在此步骤中，将自定义应用程序以根据客户的城市筛选数据。  
  
#### <a name="to-add-filtering-by-city"></a>添加根据城市进行筛选的功能  
  
1.  在**解决方案资源管理器**，打开快捷菜单**Form1.vb**或**Form1.cs**节点，然后选择**打开**。  
  
2.  添加<xref:System.Windows.Forms.TextBox>控件和<xref:System.Windows.Forms.Button>控件从**工具箱**到窗体。  
  
3.  打开的快捷菜单<xref:System.Windows.Forms.Button>控制，并选择**查看代码**，然后添加下面的代码`Button1_Click`事件处理程序：  
  
    ```vb  
    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
            Dim proxy As New northwindEntities _  
    (New Uri("http://localhost:53161/NorthwindCustomers.svc"))  
            Dim city As String = TextBox1.Text  
  
            If city <> "" Then  
                Me.CustomersBindingSource.DataSource = From c In _  
             proxy.Customers Where c.City = city  
            End If  
  
        End Sub  
    ```  
  
    ```csharp  
    private void Button1_Click(object sender, EventArgs e)  
    {  
    ServiceReference1.northwindModel.northwindEntities proxy = new northwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc"));  
    string city = TextBox1.Text;  
  
    if (!string.IsNullOrEmpty(city)) {  
    this.CustomersBindingSource.DataSource = from c in proxy.Customers where c.City == city;  
    }  
  
    }  
    ```  
  
4.  在以上代码中，使用 `http://localhost:53161/NorthwindCustomers.svc` 事件处理程序中的 URL 替换 `Form1_Load`。  
  
5.  在菜单栏上，选择**调试**，**启动调试**运行该应用程序。  
  
6.  在文本框中，输入**伦敦**，然后选择按钮。 将仅显示来自 London 的客户。  
  
## <a name="see-also"></a>请参阅  
 [Windows Communication Foundation 服务和 Visual Studio 中的 WCF 数据服务](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)   
 [如何：添加、更新或删除 WCF 数据服务引用](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)