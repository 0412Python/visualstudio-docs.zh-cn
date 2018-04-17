---
title: 如何： 通过使用模块包括文件 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, modules
- modules [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6af9ef6114a3ac187c50d17f16c39c89b08370dd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-include-files-by-using-a-module"></a>如何：使用模块包括文件
  *模块*(无法将其与混淆[!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]模块) 是用于使您能够将如 ASPX 主控页文件、 文本文件或映像部署到 SharePoint 的容器。  
  
 你可以选择将文件部署到文档库，或者作为正常文件 (例如，default.aspx) 之外的文档库。 若要将文件添加到文档库中，指定`Type="GhostableInLibrary"`作为中的属性**文件**元素。 此设置指示 SharePoint，以创建要添加到库时，转到带有你的文件的列表项。 若要部署文档库之外的文件，请指定`Type="Ghostable"`或只需忽略**类型**属性。  
  
## <a name="adding-a-module-to-a-sharepoint-solution"></a>将模块添加到 SharePoint 解决方案  
  
#### <a name="to-add-a-module"></a>若要添加模块  
  
1.  在 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 中打开或创建一个 SharePoint 项目。  
  
     有关详细信息，请参阅[SharePoint 项目和项目项模板](../sharepoint/sharepoint-project-and-project-item-templates.md)。  
  
2.  在**解决方案资源管理器**，选择项目节点，然后，在菜单栏上，选择**项目**，**添加新项**。  
  
     此时将打开“添加新项”对话框。  
  
3.  在 SharePoint 模板列表中，选择**模块**模板，然后选择**添加**按钮。  
  
     此步骤将在项目中创建名为 Module1 的节点。  
  
4.  在 Module1 下，删除 Sample.txt 文件。  
  
     Sample.txt 包含在所有新模块例如目的，不需要。 （请注意，删除文件还会删除其条目从模块的 Elements.xml 文件。）  
  
5.  如果你想将文件部署到 SharePoint 中的特定文件夹结构，创建这些文件夹中的 Module1 下[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]通过选择 Module1 节点，然后在菜单栏中选择**项目**，**新建文件夹**。  
  
6.  选择的文件夹，以添加该文件，然后，在菜单栏上，选择**项目**，**添加现有项**。  
  
7.  选择你想要部署到 SharePoint，然后选择的一个或多个文件**添加**按钮。  
  
     当将文件添加到项目中时，它的项是自动添加到模块的 Elements.xml 文件中。 部署项目时，文件复制到 SharePoint 服务器，相对于项目的根目录，由指定**文件**元素的**Url**属性，如`Url="Module1/New Folder/SomeFile.doc`。 如果你想要更改文件的部署位置，请将其移到另一个文件夹中**解决方案资源管理器**或更改其**Url**设置。  
  
8.  对于你想要在文档库中显示任何文件，追加`Type="GhostableInLibrary"`属性设为 Elements.xml 中其条目。 例如，应用于对象的  
  
    ```  
    <File Path="Module1\Some Folder\SomePage.aspx" Url="Module1/Some Folder/SomePage.aspx" Type="GhostableInLibrary" />  
    ```  
  
9. 将项目部署。  
  
     文件将复制到 SharePoint 中的指定位置。  
  
## <a name="see-also"></a>另请参阅  
 [打包和部署 SharePoint 解决方案](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [开发 SharePoint 解决方案](../sharepoint/developing-sharepoint-solutions.md)  
  
  