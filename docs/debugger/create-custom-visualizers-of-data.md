---
title: 创建自定义数据可视化工具 |Microsoft Docs
ms.date: 11/07/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.visualizer.troubleshoot
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers
ms.assetid: c24c006f-f2ac-429f-89db-677fc0c6e1ea
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6342b571d1116d4a67e5ae01268c636ffbba6722
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56633689"
---
# <a name="create-custom-data-visualizers"></a>创建自定义数据可视化工具
 一个*可视化工具*属于[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]调试器用户界面中以适合其数据类型的方式显示变量或对象。 例如，HTML 可视化工具解释 HTML 字符串，并显示结果，就像在浏览器窗口中显示。 位图可视化工具解释位图结构并显示它所代表的图形。 某些可视化工具可让你还可以查看的数据修改。

 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 调试器包括六个标准可视化工具。 文本、 HTML、 XML 和 JSON 可视化工具处理字符串对象。 WPF 树可视化工具显示 WPF 对象可视化树的属性。 数据集可视化工具一种用于 DataSet、 DataView 和 DataTable 对象。

可从 Microsoft、 第三方和社区下载更多可视化工具。 此外可以编写自己的可视化工具，并将它们安装在[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]调试器。

在调试器中，可视化工具由一个放大镜图标表示![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "可视化工具图标")。 可以选择在图标**数据提示**，调试器**监视**窗口中，或**快速监视**对话框中，并选择相应的对象的相应可视化工具。

## <a name="write-custom-visualizers"></a>编写自定义可视化工具

 > [!NOTE]
 > 若要创建的本机代码的自定义可视化工具，请参阅[SQLite 本机调试器可视化工具](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/SqliteVisualizer)示例。 对于 UWP 和 Windows 8.x 应用程序不支持自定义可视化工具。

可以为任何托管类（除 <xref:System.Object> 和 <xref:System.Array> 之外）的对象编写自定义可视化工具。

调试器可视化工具的结构由两部分组成：

- *调试器端*运行在 Visual Studio 调试器中，并创建并显示可视化工具用户界面。

- “调试对象端”在 Visual Studio 正在调试的进程（“调试对象”）中运行。 调试对象进程中存在要实现可视化效果 （例如，字符串对象） 的数据对象。 调试对象端将对象发送到调试器端，在您创建的用户界面中显示。

在调试器端接收中的数据对象*对象提供程序*实现<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider>接口。 调试对象端将通过对象发送*对象源*，它派生自<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>。

对象提供程序还可以发送数据返回到对象源，使你可以编写可视化工具，可以编辑数据。 重写要与表达式计算器和对象源的对象提供程序。

调试对象端和调试器端通过与其他通信<xref:System.IO.Stream>方法将数据序列化对象插入<xref:System.IO.Stream>和反序列化<xref:System.IO.Stream>回数据对象。

仅当类型为开放类型，可以为泛型类型编写可视化工具。 此限制与使用 `DebuggerTypeProxy` 特性时的限制相同。 有关详细信息，请参阅[使用 DebuggerTypeProxy 特性](../debugger/using-debuggertypeproxy-attribute.md)。

自定义可视化工具可能有安全性问题。 请参阅[可视化工具安全注意事项](../debugger/visualizer-security-considerations.md)。

以下步骤进行可视化工具创建了高级概述。 有关详细说明，请参阅[演练： 编写可视化工具C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)或[演练： 用 Visual Basic 编写可视化工具](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)。

### <a name="to-create-the-debugger-side"></a>创建调试器端

若要在调试器端创建可视化工具用户界面，您可以创建继承的类<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>，并替代<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName>方法来显示的界面。 可以使用<xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService>要在可视化工具中显示 Windows 窗体、 对话框和控件。

1.  使用 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> 方法在调试器端获取可视化的对象。

1.  创建一个从 <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer> 继承的类。

1.  重写 <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> 方法以显示接口。 使用<xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService>方法，以便在界面中显示 Windows 窗体、 对话框和控件。

4.  将应用<xref:System.Diagnostics.DebuggerVisualizerAttribute>，为其提供要显示的可视化工具 (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>)。

### <a name="to-create-the-debuggee-side"></a>创建调试对象端

使用指定调试对象端代码<xref:System.Diagnostics.DebuggerVisualizerAttribute>。

1.  应用 <xref:System.Diagnostics.DebuggerVisualizerAttribute>，为它指定可视化工具 (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>) 和对象源 (<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>)。 如果省略对象源，可视化工具将使用默认对象源。

1.  若要允许编辑，也显示的数据对象的可视化工具，请重写`TransferData`或`CreateReplacementObject`方法从<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>。

## <a name="see-also"></a>请参阅

- [演练：用 C# 编写可视化工具](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)
- [演练：用 Visual Basic 编写可视化工具](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)
- [如何：安装可视化工具](../debugger/how-to-install-a-visualizer.md)
- [如何：测试和调试可视化工具](../debugger/how-to-test-and-debug-a-visualizer.md)
- [可视化工具 API 参考](../debugger/visualizer-api-reference.md)
- [查看调试器中的数据](../debugger/viewing-data-in-the-debugger.md)