---
title: 如何： 创建 WCF 工作流服务应用程序 |Microsoft 文档
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d901354b4a6a5f90ef75567131540405af7c9690
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-wcf-workflow-service-application"></a>如何：创建 WCF 工作流服务应用程序

[!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 工作流服务应用程序是在它们自身与客户端之间跨进程边界传递消息的分布式通信服务。 服务端服务协定的实现是通过 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 中的工作流活动，以类似于 .NET Framework 3.5 中的旧工作流服务的方式基于声明完成的。

### <a name="to-create-a-wcf-workflow-service-application"></a>创建 WCF 工作流服务应用程序

1.  启动 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]。

2.  上**文件**菜单上，指向**新建**，然后选择**项目...**.

     **“新建项目”** 对话框随即打开。

3.  在**已安装的模板**窗格中，选择**WCF**或**工作流**从**Visual C#**或**Visual Basic**具体取决于选择的语言的分组。

4.  在中间窗格中，选择**WCF 工作流服务应用程序**。

5.  在**名称**框中，输入你的项目，以便可以方便地标识的描述性名称。

6.  在**位置**框中，输入你要在其中保存你的项目，或单击的目录**浏览**以导航到。

7.  在**解决方案**框中，选择创建新的解决方案，然后单击**确定**。

    > [!NOTE]
    > 如果你想要添加到现有的解决方案的工作流控制台应用程序，打开该解决方案中的[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]，右键单击该解决方案中的**解决方案资源管理器**，然后选择**添加**，然后**新建项目...**以打开**新项目**对话框。 按照此过程中的上述步骤继续操作。

8.  该项目模板将创建一个 XAML 格式的服务定义。 Windows 工作流设计器将打开到设计视图，其中<xref:System.Activities.Statements.Sequence>包含一组活动<xref:System.ServiceModel.Activities.Receive>和<xref:System.ServiceModel.Activities.SendReply>活动。

## <a name="see-also"></a>请参阅

- [如何：创建活动](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [创建工作流项目](../workflow-designer/creating-a-workflow-project.md)