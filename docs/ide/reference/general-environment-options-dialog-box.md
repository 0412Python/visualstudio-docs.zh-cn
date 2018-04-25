---
title: “选项”对话框 ->“环境”->“常规”| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.Message.0x800a002e
- VS.ToolsOptionsPages.Environment.General
- VS.Environment.General
helpviewer_keywords:
- MRU lists
- windows, customizing
- MDI, environment options
- speed, environment animation
- File menu
- menus, customizing
- Windows menu customizing
- status bars, displaying
- Visual Studio Start page, setting
- IDE, startup options
- editors, autocompletion
- Options dialog box, General Environment
- General Environment Options dialog box
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c427752fa1b89acb2fa55afc7acd8c4535686c37
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="general-environment-options-dialog-box"></a>“选项”对话框 ->“环境”->“常规”

使用此页更改集成开发环境 (IDE) 的颜色主题、状态栏设置和文件扩展名关联以及其他选项。 可以通过打开“工具”菜单，选择“选项”，打开“环境”文件夹然后选择“常规”页来访问“选项”对话框。 如果此页未出现在列表中，请在“选项”对话框中选中“显示所有设置”复选框。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请打开“工具”菜单并选择“导入和导出设置”。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。

## <a name="visual-experience"></a>视觉体验

颜色主题

为 IDE 选择“蓝色”、“浅色”或“深色”颜色主题。

可以通过从 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.VisualStudio2017ColorThemeEditor) 中下载并安装“Visual Studio 颜色主题编辑器”来安装其他预定义的主题并创建自定义主题。 安装此工具后，其他颜色主题将显示在“颜色主题”列表框中。

**在菜单栏中应用标题大小写**

菜单默认位于“标题大小写”中。 取消选中此选项，将其设置为“全部大写”。

基于客户端性能自动调整视觉体验

指定由 Visual Studio 自动设置视觉体验调整，还是由你明确地设置调整。 这种调整可能会将颜色的显示从渐变更改为纯色，也可能会限制菜单或弹出窗口中动画的使用。

启用丰富客户端体验

启用 Visual Studio 的完整视觉体验，包括渐变和动画。 使用远程桌面连接或较旧的图形适配器时，请清除此选项，因为在这些情况下这些功能可能会使性能变差。 只有在清除了“基于客户端自动调整视觉体验”选项时，此选项才可用。

使用硬件图形加速（如果可用）

如果可用，请使用硬件图形加速，而不是软件加速。

## <a name="other"></a>其他

**“窗口”菜单中显示的项**自定义“窗口”菜单的“窗口”列表中显示的窗口数。 键入一个介于 1 和 24 之间的数字。 默认情况下，该数字为 10。

**“最近使用的文件”列表中显示的项**自定义出现在“文件”菜单上的最近使用过的项目和文件数。 键入一个介于 1 和 24 之间的数字。 默认情况下，该数字为 10。 这可以轻松地检索最近使用的项目和文件。

**显示状态栏**显示状态栏。 状态栏位于 IDE 窗口的底部并显示关于正在进行的操作的进度信息。

**“关闭”按钮只影响活动工具窗口**指定在单击“关闭”按钮时，只关闭具有焦点的工具窗口，而不是停靠集中的所有工具窗口。 默认情况下，该选项是选中的。

**“自动隐藏”按钮只影响活动工具窗口**指定在单击“自动隐藏”按钮时，只自动隐藏具有焦点的工具窗口，而不是停靠集中的所有工具窗口。 默认情况下，不选择该选项。

## <a name="see-also"></a>请参阅

[环境选项对话框](../../ide/reference/environment-options-dialog-box.md)
[自定义窗口布局](../../ide/customizing-window-layouts-in-visual-studio.md)