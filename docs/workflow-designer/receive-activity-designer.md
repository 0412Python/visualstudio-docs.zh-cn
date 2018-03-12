---
title: "Receive 活动设计器 |Microsoft 文档"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Receive.UI
ms.assetid: f58d3c70-944d-4bb4-90a7-e68c103caddc
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d8058b13dd488ddca2237056048673529c379256
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="receive-activity-designer"></a>Receive 活动设计器
**接收**活动设计器用于创建和配置<xref:System.ServiceModel.Activities.Receive>活动。 <xref:System.ServiceModel.Activities.Receive> 活动是接收消息的活动，可接收的消息包括内置类型（如 <xref:System.ServiceModel.Channels.Message>、<xref:System.IO.Stream> 或 <xref:System.Xml.Linq.XElement>）或者应用程序定义的数据协定、消息协定或可序列化的 XML 类。

## <a name="the-receive-activity"></a>Receive 活动
 <xref:System.ServiceModel.Activities.Receive> 活动可以接收一个或多个项，具体取决于所用接收内容的类型。 <xref:System.ServiceModel.Activities.SendReply> 活动可绑定到作为服务上请求/响应消息交换模式的一部分接收消息的 <xref:System.ServiceModel.Activities.Receive> 活动。

### <a name="using-the-receive-activity-designer"></a>使用 Receive 活动设计器
 **接收**在找不到活动设计器**消息**类别**工具箱**，通过单击访问的哪一**工具箱**选项卡上[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)](或者，选择**工具栏**从**视图**菜单或 CTRL + ALT + X。)

 **接收**活动设计器可以拖动从**工具箱**拖放到[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]图面任何位置通常放置活动的。 这将创建具有 Receive 的默认 <xref:System.ServiceModel.Activities.Receive> 的 <xref:System.Activities.Activity.DisplayName%2A> 活动。 <xref:System.Activities.Activity.DisplayName%2A>可以在的标头中编辑**接收**活动设计器中或在**DisplayName**属性网格的框。

 若要创建<xref:System.ServiceModel.Activities.SendReply>活动并将其绑定到所选<xref:System.ServiceModel.Activities.Receive>活动，右键单击**接收**活动设计器中，单击**创建 SendReply**上下文菜单中的项和**SendReplyToReceive**如下所示设计器**接收**设计器。 <xref:System.ServiceModel.Activities.SendReply> 活动是作为服务上请求/响应消息交换模式的一部分发送答复消息的一个活动。 可以使用配置**SendReplyToReceive**设计器。

 或者， **ReceiveAndSendReply**模板设计器中的**消息**类别**工具箱**可以用于创建一对预配置<xref:System.ServiceModel.Activities.Receive>和<xref:System.ServiceModel.Activities.SendReply>活动。 有关使用有关的详细信息**ReceiveAndSendReply**和**SendReplyToReceive**模板，请参阅[ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)主题。

### <a name="the-receive-activity-properties"></a>Receive 活动属性
 下表列出 <xref:System.ServiceModel.Activities.Receive> 属性并说明如何在设计器中使用它们。 这些属性可以在属性网格中或 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 图面上进行编辑。 唯一必需的属性是 <xref:System.ServiceModel.Activities.Receive.OperationName%2A> 属性。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|指定 <xref:System.ServiceModel.Activities.Receive> 活动的友好名称。 默认值为 Receive。<br /><br /> 虽然对友好 <xref:System.Activities.Activity.DisplayName%2A> 使用非默认值不是绝对必需的，但最好使用非默认值。|
|<xref:System.ServiceModel.Activities.Receive.OperationName%2A>|True|指定由此 <xref:System.ServiceModel.Activities.Receive> 活动实现的服务操作的名称。 此属性用于构造的默认值为**操作**属性如果**操作**属性未显式设置。|
|<xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>|False|指定服务协定的名称。 此属性用于将服务操作分组至各个服务协定。 所有具有相同的 <xref:System.ServiceModel.Activities.Receive> 的 <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> 活动都分组到同一服务协定（WSDL 端口类型）中。 默认值为顶级（根）活动的完全限定的 CLR 名称。|
|<xref:System.ServiceModel.Activities.Receive.Content%2A>|False|指定要接收的消息或参数内容。 它可为 <xref:System.ServiceModel.Activities.ReceiveMessageContent> 活动或 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 活动。 通过单击旁的省略号按钮来编辑此属性**内容**在属性网格或单击字段**定义...**按钮旁边**内容**上的标签**接收**活动设计器图面。 两者都显示**内容定义**对话框。 有关如何使用此框的详细信息，请参阅[内容定义对话框](../workflow-designer/content-definition-dialog-box.md)主题。|
|<xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>|False|使用 <xref:System.ServiceModel.Activities.Receive> 对象指定工作流的服务操作中各 <xref:System.ServiceModel.MessageQuerySet> 活动之间的关联。 单击省略号按钮旁边<xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>属性在属性网格中，若要打开**CorrelatesOn 定义**对话框。 有关使用此对话框中的详细信息，请参阅[内容定义对话框](../workflow-designer/content-definition-dialog-box.md)主题。|
|<xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A>|False|指定用于将消息路由到相应工作流实例的 <xref:System.ServiceModel.Activities.CorrelationHandle>。<br /><br /> 单击省略号按钮旁边<xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A>属性在属性网格中，若要打开**表达式编辑器**对话框。 有关使用此对话框中的详细信息，请参阅[如何： 使用表达式编辑器](../workflow-designer/how-to-use-the-expression-editor.md)主题。|
|<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>|False|指定在工作流中对配置此 <xref:System.ServiceModel.Activities.CorrelationInitializer> 活动的多个 <xref:System.ServiceModel.Activities.CorrelationHandle> 对象进行初始化的 <xref:System.ServiceModel.Activities.Receive> 对象的集合。 单击省略号按钮旁边<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>属性在属性网格中，若要打开**添加相关初始值设定项**对话框。 有关使用此框的详细信息，请参阅[添加 CorrelationInitializers 对话框](../workflow-designer/add-correlationinitializers-dialog-box.md)主题。|
|<xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A>|False|指定一个值，该值确定如果消息未关联到现有的工作流实例，是否创建一个新工作流实例来处理该消息。 如果值设置为**true**，创建一个新的工作流实例来处理消息时该消息未关联到现有工作流实例。|
|<xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>|False|指定由此 <xref:System.ServiceModel.Activities.Receive> 活动实现的服务操作的已知类型集合。 此属性应与设置为 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 的 <xref:System.Runtime.Serialization.DataContractSerializer> 属性结合使用。 如果使用了 <xref:System.Xml.Serialization.XmlSerializer>，则忽略此项。<br /><br /> 单击旁的省略号按钮**KnownTypes**字段在属性网格中显示**类型集合编辑器**对话框中可以使用该对话框添加相关类型。 有关使用此框的详细信息，请参阅[类型集合编辑器对话框](../workflow-designer/type-collection-editor-dialog-box.md)主题。|
|<xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A>|False|指定消息的 <xref:System.Net.Security.ProtectionLevel>。<br /><br /> 1。<xref:System.Net.Security.ProtectionLevel>意味着仅身份验证。<br />2。<xref:System.Net.Security.ProtectionLevel>意味着数据进行签名以帮助确保传输的数据的完整性。<br />3。<xref:System.Net.Security.ProtectionLevel>方法进行加密和签名数据以帮助确保保密性和传输数据的完整性。|
|<xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>|False|指定 <xref:System.ServiceModel.Activities.Receive> 活动实现的服务操作所使用的序列化程序的类型。 默认值为 <xref:System.Runtime.Serialization.DataContractSerializer>，它使用提供的数据协定将类型实例序列化和反序列化为 XML 流或文档。 如果需要对 XML 进行更多控制，还可使用 <xref:System.Xml.Serialization.XmlSerializer>。|
|<xref:System.ServiceModel.Activities.Receive.Action%2A>|False|指定消息的操作标头。 如果它未显式设置，其默认值为： https://tempuri.org/ {服务协定命名空间} / {服务协定名称} / {操作名称}。|

## <a name="see-also"></a>请参阅

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [发送](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)