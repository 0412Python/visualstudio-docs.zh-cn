---
title: 编辑 Python 代码 | Microsoft Docs
description: 在 Visual Studio 中编辑 Python 提供 IntelliSense、代码片段和导航功能，以及格式设置、linting 和重构。
ms.custom: ''
ms.date: 03/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 8e9d5a3b18e7193786ea2b6d0bf2dfb038828e78
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="editing-python-code"></a>编辑 Python 代码

开发人员需要花费大量时间埋头于代码编辑器，因此可借助 [Visual Studio 中的 Python 的支持](installing-python-support-in-visual-studio.md)中的功能来提高工作效率。 这些功能包括 IntelliSense 语法突出显示、自动完成、签名帮助、方法重写、搜索和导航。

编辑器还集成了 Visual Studio 中的交互式窗口，便于在两者之间交换代码。 请参阅[教程步骤 3：使用 REPL 交互窗口](tutorial-working-with-python-in-visual-studio-step-03-interactive-repl.md)和[使用交互窗口：将代码发送到交互命令](python-interactive-repl-in-visual-studio.md#send-code-to-interactive-command)了解详细信息。

|   |   |
|---|---|
| ![视频的摄像机图标](../install/media/video-icon.png "观看视频") | 有关编辑 Python 代码的演示，请[观看视频（Microsoft 虚拟学院）](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Editing-Python-Code-r2iQH5LWE_4605918567)（2 分 30 秒）。|

有关在 Visual Studio 中编辑代码的常规文档，请参阅[在代码和文本编辑器中编写代码](../ide/writing-code-in-the-code-and-text-editor.md)。 另请参阅 [Visual Studio 中的大纲显示](../ide/outlining.md)，方便你将重点放在代码的特定部分。

你也可以使用 Visual Studio 对象浏览器（“视图”>“其他窗口”>“对象浏览器”或 Ctrl+W、J）检查每个模块中定义的 Python 类及这些类中定义的函数。

## <a name="intellisense"></a>IntelliSense

IntelliSense 可提供[完成](#completions)、[签名帮助](#signature-help)、[快速信息](#quick-info)和[代码着色](#code-coloring)等功能。

为了提高性能，**Visual Studio 2017 版本 15.5** 和更早版本中的 IntelliSense 将取决于为项目中的每个 Python 环境生成的完成数据库。 添加、删除或更新包后可能需要刷新数据库。 数据库状态将显示在“IntelliSense”选项卡上的“Python 环境”窗口（“解决方案资源管理器”的同级）中（请参阅[环境窗口引用](python-environments-window-tab-reference.md#intellisense-tab)）。

**Visual Studio 2017 版本 15.6**和更高版本使用不同的方法提供不依赖于数据库的 IntelliSense 完成。

### <a name="completions"></a>完成

完成显示为语句、标识符和可能在编辑器的当前位置输入的其他字词。 在列表中显示的内容基于上下文，并进行筛选以忽略不正确或干扰的选项。 完成通过键入不同的语句（如 `import`）和运算符（包括句点）触发，但可以随时通过键入 Ctrl-J、空格使其显示。

![成员完成](media/code-editing-completions-simple.png)

打开完成列表时，可使用箭头键、鼠标或通过继续键入搜索所需完成。 随着键入更多的字母，将进一步筛选列表以显示可能的完成。 还可以使用如下快捷方式：

- 键入非名称开头的字母，如键入“parse”查找“argparse”
- 仅键入位于单词开头的字母，如键入“abc”查找“AbstractBaseClass”或键入“air”查找“as_integer_ratio”
- 跳过字母，如键入“b64”查找“base64”

示例如下：

![使用筛选的成员完成](media/code-editing-completion-filtering.png)

在变量或值后键入一个句点后将自动显示成员完成，并显示可能类型的方法和属性。 如果某个变量属于多个类型，该列表将包含所有类型的所有可能项，并提供附加信息，指示支持每个完成的类型。 如果所有可能的类型支持某个完成，则该完成不显示批注。

![关于多种类型的成员完成](media/code-editing-completion-types.png)

默认情况下，不显示以双下划线开头和结尾的“dunder”成员。 一般情况下，无法直接访问这类成员。 但如果需要该完成，请键入前导双下划线将这些完成添加到列表：

![私有成员完成](media/code-editing-completion-dunder.png)

`import` 和 `from ... import` 语句会显示一系列可以导入的模块。 通过 `from ... import`，列表会包含可以从指定模块导入的成员。

![导入完成](media/code-editing-completion-import.png)

`raise` 和 `except` 语句会显示可能为错误类型的类列表。 该列表可能不包括用户定义的所有异常，但有助于快速查找合适的内置异常：

![异常完成](media/code-editing-completion-exception.png)

键入 @ 将启动装饰器并显示可能的修饰器。 其中许多项不能用作修饰器；请查看库文档以确定使用哪个项。

![修饰器完成](media/code-editing-completion-decorator.png)

> [!Tip]
> 可以通过“工具”>“选项”>“文本编辑器”>“Python”>“高级”来配置完成的行为。 其中，**基于搜索字符串筛选列表**将在你键入时应用筛选完成建议（默认为选中状态），而**成员完成显示成员交集**将仅显示所有可能的类型支持的完成（默认为未选中）。 请参阅[选项 - 完成结果](python-support-options-and-settings-in-visual-studio.md#completion-results)。

### <a name="signature-help"></a>签名帮助

编写调用函数的代码时，签名帮助将在键入左括号 `(` 时出现，并显示可用的文档和参数信息。 还可以在函数调用中使用 Ctrl+Shift+空格使其显示。 显示的信息取决于函数源代码中的文档字符串，但包括所有默认值。

![签名帮助](media/code-editing-signature-help.png)

> [!Tip]
> 若要禁用签名帮助，请转到“工具”>“选项”>“文本编辑器”>“Python”>“常规”并清除“语句完成”>“参数信息”。

### <a name="quick-info"></a>快速信息

将鼠标指针悬停在标识符的上方可显示快速信息工具提示。 根据标识符，快速信息可能会显示可能的值或类型、所有可用文档、返回类型以及定义位置：

![快速信息](media/code-editing-quick-info.png)

### <a name="code-coloring"></a>代码着色

代码着色使用代码分析中的信息为变量、语句和代码的其他部分着色。 例如，引用模块或类的变量可能采用不同于函数或其他值的颜色显示，而参数名称将采用不同于局部变量或全局变量的颜色显示。 （默认情况下，函数不以粗体形式显示）：

![代码着色](media/code-editing-code-coloring.png)

若要自定义颜色，请转到“工具”>“选项”>“环境”>“字体和颜色”，然后修改“显示项”列表中的 Python 项：

![“字体”和“颜色”选项](media/code-editing-customize-colors.png)

> [!Tip]
> 若要禁用代码着色，请转到“工具”>“选项”>“文本编辑器”>“Python”>“高级”，然后清除“杂项选项”>“基于类型为名称着色”。 请参阅[选项 - 杂项选项](python-support-options-and-settings-in-visual-studio.md#miscellaneous-options)。

## <a name="code-snippets"></a>代码片段

代码片段是可通过键入快捷方式并按 Tab 键或使用“编辑”>“IntelliSense”>“插入代码片段”和外侧代码命令，选择“Python”，然后选择所需代码段来插入文件的几段代码。

例如，`class` 是一个插入类定义的代码片段的快捷方式。 在键入 `class` 时，将在自动完成列表中显示代码片段：

![类快捷方式的的代码片段](media/code-editing-code-snippet-class.png)

按 Tab 将生成类的剩余部分。 然后可以在名称和基列表上键入，使用 Tab 键在突出显示的字段间移动，然后按 Enter 开始键入正文。

![突出显示要完成的代码片段的区域](media/code-editing-code-snippets.png)

### <a name="menu-commands"></a>菜单命令

在使用“编辑”>“IntelliSense”>“插入代码片段”菜单命令时，首先选择“Python”，然后选择代码段：

![通过插入代码片段命令选择代码片段](media/code-editing-code-snippet-insert.png)

同样，“编辑”>“IntelliSense”>“外侧代码”命令将当前选择的内容置于所选结构化元素内的文本编辑器中。 例如，假设你有一段如下所示的代码：

```python
sum = 0
for x in range(1, 100):
    sum = sum + x
```

选中此代码并选择“外侧代码”命令将显示可用代码段的列表。 从列表中选择 `def` 将所选代码置于函数定义内，然后可以使用 Tab 键在突出显示的函数名称和参数之间导航：

![为代码片段使用“外侧代码”命令](media/code-editing-code-snippet-surround-with.png)

### <a name="examine-available-snippets"></a>检查可用片段

你可以在代码片段管理器中看到可用的代码片段（通过使用“工具”>“代码片段管理器”菜单命令打开），并选择“Python”作为语言：

![代码片段管理器](media/code-editing-code-snippets-manager.png)

若要创建自己的代码段，请参阅[演练：创建代码段](../ide/walkthrough-creating-a-code-snippet.md)。

如果编写优质的代码片段并且想要将其共享，请随时发布到 gist 并[告诉我们](https://github.com/Microsoft/PTVS/issues)。 我们可能将其包含在 Visual Studio 的未来版本中。

## <a name="navigating-your-code"></a>导航代码

Visual Studio 中的 Python 支持提供多种方式在代码中快速导航，其中包括其源代码可用的库：[导航栏](#navigation-bar)、[转到定义](#go-to-definition)、[导航到](#navigate-to)、[查找所有引用](#find-all-references)。 还可以使用 Visual Studio [对象浏览器](../ide/viewing-the-structure-of-code.md#BKMK_ObjectBrowser)。

### <a name="navigation-bar"></a>导航栏

导航栏在每个编辑器窗口的顶部显示且包含两级定义列表。 左侧下拉列表包含当前文件中的顶级类和函数定义；右侧下拉列表显示左侧作用域内的定义列表。 在编辑器中移动时，列表会进行更新，以显示当前上下文，并且还可以从这些列表中选择某项以直接转入。

![导航栏](media/code-editing-navigation-bar.png)

> [!Tip]
> 若要隐藏导航栏，请转到“工具”>“选项”>“文本编辑器”>“Python”>“常规”，然后清除“设置”>“导航栏”。

### <a name="go-to-definition"></a>转到定义

**转到定义**可从使用标识符（如函数名、类或变量）快速跳转至定义它的源代码。 通过右键单击标识符并选择“转到定义”，或将插入点放在标识符中并按 F12 可进行调用。 如果源代码可用，它可用于代码和外部库。 如果库源代码不可用，则“转到定义”将跳转到模块引用的相关 `import` 语句或显示错误。

![转到定义](media/code-editing-go-to-definition.png)

### <a name="navigate-to"></a>定位到

“编辑”>“导航到...”命令（Ctrl-comma）将在编辑器中显示搜索框，你可在搜索框中键入任何字符串并查看在定义函数、类或变量的代码中是否存在包含此字符串的匹配项。 此功能与“转到定义”类似，但无需查找标识符的使用。

双击任何名称或使用箭头键和 Enter 选择名称，然后导航到该标识符的定义。

![定位到](media/code-editing-navigate-to.png)

### <a name="find-all-references"></a>查找所有引用

**查找所有引用**是一种有用的方法，用于发现同时定义和使用任何给定标识符的位置，包括导入和分配。 通过右键单击标识符并选择“查找所有引用”或将插入点放在标识符中并按 Shift+F12 可以进行调用。 双击列表中的项可导航到其位置。

![查找所有引用结果](media/code-editing-find-all-references.png)

## <a name="see-also"></a>请参阅

- [格式设置](formatting-python-code.md)
- [重构](refactoring-python-code.md)
- [Linting](linting-python-code.md)