---
title: "添加 CorrelationInitializers 对话框 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: AddCorrelationInitializers.UI
ms.assetid: c0517467-d54a-4ee6-aef0-c19b96b6f395
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 4c4d8e07aa172aef524b4d85bda5ad8efdfb509f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="add-correlationinitializers-dialog-box"></a>“添加相关初始值设定项”对话框
**添加相关初始值设定项**中使用对话框[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]配置**CorrelationInitializers**属性<xref:System.ServiceModel.Activities.Send>， <xref:System.ServiceModel.Activities.Receive>， <xref:System.ServiceModel.Activities.SendReply>，和<xref:System.ServiceModel.Activities.ReceiveReply>活动。 [!INCLUDE[crabout](../test/includes/crabout_md.md)]活动设计器，可使用此框中，请参阅[发送](../workflow-designer/send-activity-designer.md)，[接收](../workflow-designer/receive-activity-designer.md)， [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)，和[SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)主题。  
  
 使用此对话框指定的集合中的相关初始值设定项可初始化基于查询的上下文、回调上下文或各消息传递活动之间的请求-答复相关性。  
  
 下表描述的用户界面 (UI) 元素**添加相关初始值设定项**对话框。  
  
|UI 元素|描述|  
|----------------|-----------------|  
|**添加初始值设定项**|单击**添加初始化**框以将其他初始值设定项添加到集合。|  
|**相关类型**|指定相关初始值设定项的类型。 有四种类型可供选择：<br /><br /> 1.用于指定 <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer> 的回调相关初始值设定项。<br />2.用于指定 <xref:System.ServiceModel.Activities.CorrelationInitializer> 的上下文相关初始值设定项。<br />3.用于指定 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> 的请求-答复相关初始值设定项。<br />4.用于指定 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 的查询相关初始值设定项。<br /><br /> 若要编辑**correlationtype**<br /><br /> 1.选项卡中的特定行**添加初始值设定项**DataGrid。<br />2.按 Ctrl + Tab 将焦点设置到**CorrelationTypeComboBox**<br />3.按 Alt + 向下弹出**ComboBox**和对其进行编辑。|  
|**XPath 查询**|包含用于从传入和传出消息中提取相关数据的查询的键/值对。 仅当使用 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 类型时此列表才有效。|  
  
## <a name="to-launch-the-add-correlation-initializers-dialog-box"></a>启动“添加相关初始值设定项”对话框  
 **添加相关初始值设定项**对话框由**发送**，**接收**， **ReceiveAndSendReply**，和**SendAndReceiveReply**设计器。 在每个用例和涉及的情况下访问它们都相同**接收**设计器是使用此处来演示该过程。  
  
 **接收**活动设计器可以拖动从**工具箱**拖放到[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]图面任何位置通常放置活动的。 这将创建具有 Receive 的默认 <xref:System.ServiceModel.Activities.Receive> 的 <xref:System.Activities.Activity.DisplayName%2A> 活动。 选择**接收**活动设计器，然后为 （集合） 文本旁的省略号按钮的单击**CorrelationInitializers**属性在属性网格**添加相关初始值设定项**对话框出现。  
  
## <a name="see-also"></a>请参阅  
 [添加相关对话框](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)   
 [“初始化相关”对话框](../workflow-designer/initialize-correlation-dialog-box.md)