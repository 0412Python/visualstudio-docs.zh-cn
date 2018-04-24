---
title: 使用 c + + 核心准则检查器
ms.date: 11/04/2016
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: wpickett
dev_langs:
- CPP
ms.technology: vs-ide-code-analysis
ms.openlocfilehash: 7f1ec5df06cbe24008f0506b838c3743a572ea5b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="using-the-c-core-guidelines-checkers"></a>使用 c + + 核心准则检查器
C + + 核心准则所移动的一组准则、 规则和有关在 c + + 专家和设计器创建的 c + + 中对编码的最佳做法。 Visual Studio 当前支持 c + + 的这些规则作为其代码分析工具的一部分的子集。 核心原则检查器在 Visual Studio 2017，默认情况下已安装并且位于[可用作 Visual Studio 2015 的 NuGet 包](#vs2015_corecheck)。

## <a name="the-c-core-guidelines-project"></a>C + + 核心准则项目
 C + + 核心准则由 Bjarne stroustrup 撰写和其他人创建的它是如何安全地并有效地使用现代 c + + 的指南。 这些准则强调静态类型安全和资源安全。 它们识别消除或最小化的语言中，最容易出错的部件的方法和建议如何使你的代码更简单和更高的性能，以可靠的方式。 由标准 c + + Foundation 维护这些准则。 若要了解详细信息，请参阅本文档中， [c + + 核心准则](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)，和上访问 c + + 核心准则文档项目文件[GitHub](https://github.com/isocpp/CppCoreGuidelines)。

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>启用代码分析中的 c + + 核心检查准则
 可以通过选择你的项目启用代码分析**生成时启用代码分析**中的复选框**代码分析**部分**属性页**对话框你的项目。

 ![代码分析常规设置的属性页](../code-quality/media/cppcorecheck_codeanalysis_general.png "CPPCoreCheck_CodeAnalysis_General")

 C + + 核心检查规则是运行时启用代码分析的默认规则集的扩展。 由于 c + + 核心检查规则是在开发下，某些规则是很好地建立，并且某些可能不是可供所有代码上使用，但仍可能提供有用的信息。 规则分为两个组： 发布的和试验性。 你可以选择是在你的项目的属性中运行的发布或实验性的规则。

 ![代码分析扩展设置的属性页](../code-quality/media/cppcorecheck_codeanalysis_extensions.png "CPPCoreCheck_CodeAnalysis_Extensions")

 若要启用或禁用的 c + + 核心检查规则集，请打开**属性页**对话框为你的项目。 下**配置属性**，展开**代码分析**，**扩展**。 在下拉列表中控制旁边**检查 （发布） 启用 c + + 核心**或**检查 （实验） 启用 c + + 核心**，选择**是**或**否**。 选择**确定**或**应用**以保存所做的更改。

## <a name="examples"></a>示例
 下面是一些可以找到 c + + 核心检查规则的问题的一个示例：

```cpp
// CoreCheckExample.cpp
// Add CppCoreCheck package and enable code analysis in build for warnings.

int main()
{
    int arr[10];           // warning C26494
    int* p = arr;          // warning C26485

    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
    {
        int* q = p + 1;    // warning C26481 (suppressed)
        p = q++;           // warning C26481 (suppressed)
    }

    return 0;
}
```

 此示例演示几个可以找到 c + + 核心检查规则的警告：

-   C26494 是规则 Type.5： 始终初始化的对象。

-   C26485 是规则 Bounds.3： 没有数组指针衰减。

-   C26481 是规则 Bounds.1： 不要使用指针算法。 请改用 `span`。

 如果 c + + 核心检查代码分析规则集已安装并启用编译此代码时前, 两个警告输出，但第三个将被取消。 下面是示例代码的生成输出：

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C + + 核心原则有可帮助你编写更好、 更安全的代码。 但是，如果你有一条规则或配置文件不应应用的实例，很容易禁止它显示在代码中直接。 你可以使用`gsl::suppress`属性以防止 c + + 核心检查检测和报告任何违反了下面的代码块中的规则。 若要禁止显示特定规则的各个语句，则可以将其标记。 你甚至可以禁止整个边界配置文件显示通过编写`[[gsl::suppress(bounds)]]`而不包括任何特定的规则数。

## <a name="supported-rule-sets"></a>支持的规则集
当新的规则添加到 c + + 核心准则检查器时，可能会增加为预先存在的代码生成的警告数。 你可以使用预定义的规则集来筛选要启用的规则的种类。
最多的规则的参考主题正在[Visual Studio c + + 核心检查参考](code-analysis-for-cpp-corecheck.md)。

从 Visual Studio 2017 版本 15.3，开始受支持的规则集是：
  - **所有者指针规则**强制实施[资源管理检查与所有者相关<T>从 c + + 核心准则](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)。

  - **Const 规则**强制实施[const 相关检查从 c + + 核心准则](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)。

  - **原始指针规则**强制实施[资源管理检查相关的原始指针从 c + + 核心准则](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)。

  - **唯一指针规则**强制实施[资源管理检查与从 c + + 核心准则中具有唯一指针语义类型的相关](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)。

  - **限定规则**强制实施[限定配置文件的 c + + 核心准则](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)。

  - **键入规则**强制实施[键入配置文件的 c + + 核心准则](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)。

  **Visual Studio 2017 版本 15.5**：
  - **类规则**重点放在正确使用特殊的方法和虚拟规范的几个规则。 这是建议用于检查的子集[类和类层次结构](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class)。
  - **并发规则**捕获错误声明防护对象的一个规则。 有关详细信息，请参阅[与并发相关准则](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency)。
  - **声明规则**几个规则从[接口准则](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces)哪些专注于如何全局变量声明。
  - **函数规则**采用的帮助的两个检查`noexcept`说明符。 这是的指导原则部件[清除函数设计和实现](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions)。
  - **共享指针规则**作为的一部分[资源管理](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource)准则强制，我们添加特定于如何共享指针的几个规则都传递给函数或在本地使用。
  - **样式规则**一个简单但很重要检查，bans 使用[goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto)。 这是提高编码样式和使用的表达式和 c + + 中的语句的第一步。

  **Visual Studio 2017 版本 15.6**:
  - **算术规则**规则，以检测算术[溢出](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow)，[有符号的无符号操作](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned)和[位操作](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative)。


 你可以选择限制为只是一个或几个组的警告。 **本机最小**和**本机建议**规则集包括 c + + 核心检查规则以及其他 PREfast 检查。 若要查看可用的规则集，请打开项目属性对话框，选择**代码 Analysis\General**，打开中的下拉列表**规则集**组合框和选取**选择多个规则集**. 有关使用 Visual Studio 中的规则集的详细信息，请参阅[使用规则集组合代码分析规则](using-rule-sets-to-group-code-analysis-rules.md)。

## <a name="macros"></a>宏
 C + + 核心准则检查程序附带的头文件中，定义更加轻松地禁止显示的代码中的警告的整个类别的宏：

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

这些宏对应规则集，然后展开为一个空格分隔的警告编号列表。 通过使用相应的杂注构造，可以配置有效的规则集，值得关注的项目或一段代码。 在下面的示例中，代码分析会发出警告仅涉及缺少常量修饰符：

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>特性
 Microsoft Visual c + + 编译器提供有限的支持为 GSL 禁止显示属性。 可用来禁止显示警告表达式和函数内的块语句上。

```cpp
// Supress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Supress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{
    new int;
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```

## <a name="suppressing-analysis-by-using-command-line-options"></a>禁止分析显示通过使用命令行选项
 而不是 #pragmas，你可以在该文件的属性页中使用命令行选项来禁止显示警告项目或单个文件。 例如，若要禁用该警告 26400 文件：

 1) 右键单击中的文件**解决方案资源管理器**

 2) 选择**属性 |C / C + + |命令行**

 3) 在**其他选项**窗口中，添加`/wd26400`。

 你可以使用命令行选项来临时禁用通过指定的文件的所有代码分析`/analyze-`。 这将生成警告*D9025 重写 '/ 分析' 与 ' / 分析-*，这将提醒你稍后可重新启用代码分析。

 ## <a name="corecheck_per_file"></a> 启用 c + + 核心准则检查程序在特定的项目文件
有时可能会有用到已设定焦点的执行代码分析，仍使用 Visual Studio IDE。 下面的示例方案可以适用于大型项目使用，以保存生成时间并轻松地筛选器结果：

1.  在命令行界面中设置`esp.extension`和`esp.annotationbuildlevel`环境变量。
2.  若要继承这些变量，请从命令行界面启动 Visual Studio。
3.  加载你的项目并打开其属性。
4.  启用代码分析，选取合适的规则集，但未启用代码分析扩展。
5.  转到你想要使用 c + + 核心准则检查器分析并打开其属性的文件。
6.  选择**C / C + + \Command 行选项**并添加 `/analyze:plugin EspXEngine.dll`
7.  禁用使用预编译标头 (**C / C + + \Precompiled 标头**)。 此操作，因为扩展引擎可能会尝试从的预编译标头 (PCH); 读取其内部信息如果使用默认项目选项编译的 PCH，则它将不兼容。
8.  重新生成项目。 常见 PREFast 检查应运行的所有文件。 由于 c + + 核心准则检查程序未启用默认情况下，它仅应在配置为使用该文件上运行。

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>如何使用 Visual Studio 外部的 c + + 核心准则检查器
你可以使用 c + + 核心准则检查中自动生成。

### <a name="msbuild"></a>MSBuild
 本机代码分析检查程序 (采用 PREfast) 集成到由自定义目标文件的 MSBuild 环境。 你可以使用项目属性来启用它，并添加 c + + 核心准则检查器 （这基于采用 PREfast）：

 ```xml
  <PropertyGroup>
    <EnableCppCoreCheck>true</EnableCppCoreCheck>
    <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>¬¬
    <RunCodeAnalysis>true</RunCodeAnalysis>
  </PropertyGroup>
```
请确保添加 Microsoft.Cpp.targets 文件导入前的这些属性。 你可以选择特定的规则集或创建自定义规则集或使用包括其他 PREfast 检查默认规则集。

你可以仅在指定的文件上运行 c + + 核心检查程序，通过使用相同的方法[前面所述](#corecheck_per_file)，但使用 MSBuild 文件。 可以通过使用设置环境变量`BuildMacro`项：

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>CppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

如果你不想修改项目文件，你可以在命令行上传递属性：

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>非 MSBuild 项目
如果你使用不依赖于 MSBuild 生成系统你仍可运行检查器中，但你需要熟悉的代码分析引擎配置某些内部结构。 不保证这些内部结构都必须在将来支持。

你需要设置几个环境变量和正确的命令行选项用于编译器。 它是更好的做法工作下的"本机工具命令提示"环境，以便无需搜索编译器的特定路径，包括目录，等等。

1.  **环境变量**
  - `set esp.extensions=cppcorecheck.dll` 这将告知引擎加载的 c + + 核心准则模块。
  - `set esp.annotationbuildlevel=ignore` 这会禁用处理 SAL 批注的逻辑。 批注不会影响在 c + + 核心准则检查器中，代码分析，但它们的处理时间 （有时很长时间）。 此设置是可选的但强烈建议。
  - `set caexcludepath=%include%` 我们强烈建议你禁用警告，在标准标头上激发。 你可以添加更多路径在这里，例如你的项目中的常见标头的路径。
2.  **命令行选项**
  - `/analyze`  启用代码分析 (也可以考虑使用 / 分析： 仅和 / 分析： quiet)。
  - `/analyze:plugin EspXEngine.dll` 此选项将代码分析扩展引擎加载到采用 PREfast。 此引擎，反过来，加载 c + + 核心准则检查程序。



## <a name="use-the-guideline-support-library"></a>使用准则支持库
 原则支持库旨在帮助你按照核心。 GSL 包括使您易出错构造替换更安全的替代项的定义。 例如，可以将`T*, length`的参数与对`span<T>`类型。 GSL 位于[ http://www.nuget.org/packages/Microsoft.Gsl ](http://www.nuget.org/packages/Microsoft.Gsl)。 库是开放源代码，因此你可以查看源、 添加批注或参与。 处找不到该项目[ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL)。

 ## <a name="vs2015_corecheck"></a> 在 Visual Studio 2015 项目中使用 c + + 核心检查准则
  如果你使用 Visual Studio 2015，默认情况下不安装 c + + 核心检查的代码分析规则集。 然后才能启用 Visual Studio 2015 中的 c + + 核心检查代码分析工具，你必须执行一些附加步骤。 通过使用 Nuget 包还原时，Microsoft 提供有关 Visual Studio 2015 项目的支持。 应用程序包名为 Microsoft.CppCoreCheck，并且在可用[ http://www.nuget.org/packages/Microsoft.CppCoreCheck ](http://www.nuget.org/packages/Microsoft.CppCoreCheck)。 此程序包要求你至少安装了 Visual Studio 2015 更新 1。

 包也将作为一个依赖项，仅限标头的原则支持库 (GSL) 安装另一个包。 GSL，还可以在 GitHub 上[ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL)。

 由于已加载代码分析规则的方法，您必须安装到你想要在 Visual Studio 2015 中检查每个 c + + 项目的 Microsoft.CppCoreCheck NuGet 包。

#### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>若要将 Microsoft.CppCoreCheck 包添加到 Visual Studio 2015 中的项目

1.  在**解决方案资源管理器**，右键单击以在你想要向其中添加包的解决方案中打开你的项目的上下文菜单。 选择**管理 NuGet 包**以打开**NuGet 包管理器**。

2.  在**NuGet 包管理器**窗口中，搜索 Microsoft.CppCoreCheck。

     ![Nuget 包管理器窗口显示 CppCoreCheck 包](../code-quality/media/cppcorecheck_nuget_window.PNG "CPPCoreCheck_Nuget_Window")

3.  选择 Microsoft.CppCoreCheck 包，然后选择**安装**按钮以将规则添加到你的项目。

 NuGet 包添加其他 MSBuild *.targets*到你的项目启用代码分析时将调用你项目的文件。 这 *.targets*文件将作为其他扩展的 c + + 核心检查规则添加到 Visual Studio 代码分析工具。 安装包时，你可以使用属性页对话框启用或禁用发布和试验性规则。

## <a name="see-also"></a>请参阅
[Visual Studio c + + 核心检查参考](code-analysis-for-cpp-corecheck.md)。

