---
title: "Visual Studio Build Tools 2017 工作负载和组件 ID | Microsoft Docs"
description: "使用 Visual Studio 工作负载和组件 ID 来构建基于 Windows 的经典应用程序"
keywords: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.date: 12/01/2017
ms.topic: article
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: 
ms.technology: vs-acquisition
ms.assetid: b99298df-0280-47fc-af73-44cd7a8ac553
ms.workload: multiple
ms.openlocfilehash: 4b41304a893dbee45b7de08edb9a37e07ef8656d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-build-tools-2017-component-directory"></a>Visual Studio 生成工具 2017 组件目录

本页中的表中列出了可用于通过命令行安装 Visual Studio 的 ID。 请注意，我们将在发布 Visual Studio 更新时添加其他组件。

另请注意以下有关本页的注意事项：

* 每个工作负载均有其自己的部分，后跟工作负载 ID 和适用于工作负载的组件表格。
* 默认情况下，安装工作负载时将安装**必需**组件。 如果愿意，还可以安装**推荐**和**可选**组件。
* 我们还添加了一个部分，此部分列出了不属于任何工作负载的其他组件。

有关如何使用这些 ID 的详细信息，请参阅[使用命令行参数安装 Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) 页。 另外，有关其他产品的工作负载和组件 ID 的列表，请参阅 [Visual Studio 2017 工作负载和组件 ID](workload-and-component-ids.md) 页。

## <a name="msbuild-tools"></a>MSBuild 工具

**ID：**Microsoft.VisualStudio.Workload.MSBuildTools

**说明：**提供构建基于 MSBuild 的应用程序所需的工具。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.0.27019.1 | 必需
Microsoft.VisualStudio.Component.CoreBuildTools | Visual Studio 生成工具核心 | 15.0.27005.2 | 必需
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 和 Visual Basic Roslyn 编译器 | 15.0.27019.1 | 必需
Microsoft.VisualStudio.Component.FSharp.MSBuild | F# 编译器 | 15.0.27019.1 | Optional

## <a name="net-core-build-tools"></a>.NET Core 生成工具

**ID：**Microsoft.VisualStudio.Workload.NetCoreBuildTools

**说明：**用于生成 .NET Core 应用程序的工具。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Net.Core.Component.SDK | .NET Core 1.0 - 1.1 开发工具 | 15.0.26606.0 | 必需
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 目标和生成任务 | 15.0.26919.1 | 必需
Microsoft.Net.Core.Component.SDK.1x | .NET Core 1.0 - 1.1 桌面版开发工具 | 15.0.26919.1 | Optional

## <a name="visual-c-build-tools"></a>Visual C++ 生成工具

**ID：**Microsoft.VisualStudio.Workload.VCTools

**说明：**使用功能强大的 Visual C++ 工具集、ATL 以及 MFC 和 C++/CLI 等可选功能生成基于 Windows 的经典应用程序。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.VisualStudio.Component.VC.CoreBuildTools | Visual C++ 生成工具的核心功能 | 15.0.27005.2 | 必需
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Visual C++ 2017 Redistributable 更新 | 15.0.27019.1 | 必需
Microsoft.VisualStudio.Component.Windows10SDK | Windows 通用 C 运行时 | 15.0.26621.2 | 必需
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 静态分析工具 | 15.0.26208.0 | 建议
Microsoft.VisualStudio.Component.VC.CMake.Project | 适用于 CMake 的 Visual C++ 工具 | 15.0.27019.1 | 建议
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 v141 工具集（x86、x64） | 15.0.27019.1 | 建议
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | 适用于桌面 C++ [x86 和 x64] 的 Windows 10 SDK (10.0.16299.0) | 15.0.27128.1 | 建议
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | 适用于 UWP 的 Windows 10 SDK (10.0.16299.0)：C#、VB 和 JS | 15.0.27128.1 | 建议
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | 适用于 UWP 的 Windows 10 SDK (10.0.16299.0)：C++ | 15.0.27128.1 | 建议
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 和 Web 开发 | 15.0.27005.2 | 建议
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 通用 CRT SDK | 15.0.27019.1 | Optional
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26621.2 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 目标包 | 15.0.26621.2 | Optional
Microsoft.VisualStudio.Component.VC.140 | 用于桌面的 VC++ 2015.3 v140 工具集（x86、x64） | 15.0.27019.1 | Optional
Microsoft.VisualStudio.Component.VC.ATL | Visual C++ ATL 支持 | 15.0.26823.1 | Optional
Microsoft.VisualStudio.Component.VC.ATLMFC | MFC 和 ATL 支持（x86 和 x64） | 15.0.27005.2 | Optional
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2（实验） | 15.0.27019.1 | Optional
Microsoft.VisualStudio.Component.VC.CLI.Support | C++/CLI 支持 | 15.0.27019.1 | Optional
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | 标准库模块（试验） | 15.0.27019.1 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM | 用于 ARM 的 Visual C++ 编译器和库 | 15.0.27019.1 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | 用于 ARM64 的 Visual C++ 编译器和库 | 15.0.27019.1 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK (10.0.10240.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK (10.0.10586.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | 适用于桌面 C++ [x86 和 x64] 的 Windows 10 SDK (10.0.15063.0) | 15.0.27128.1 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | 适用于 UWP 的 Windows 10 SDK (10.0.15063.0)：C#、VB 和 JS | 15.0.27128.1 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | 适用于 UWP 的 Windows 10 SDK (10.0.15063.0)：C++ | 15.0.27128.1 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop.arm | 适用于桌面 C++ [ARM 和 ARM64] 的 Windows 10 SDK (10.0.16299.0) | 15.0.27128.1 | Optional
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK 和 UCRT SDK | 15.0.27019.1 | Optional

## <a name="web-development-build-tools"></a>Web 开发生成工具

**ID：**Microsoft.VisualStudio.Workload.WebBuildTools

**说明：**用于构建 Web 应用程序的 MSBuild 任务和目标。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26621.2 | 必需
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 目标包 | 15.0.26621.2 | 必需
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 开发工具 | 15.0.27005.2 | 必需
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF 开发生成工具 | 15.0.27019.1 | 必需
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Web 开发生成工具 | 15.0.26323.1 | 必需
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 目标包 | 15.0.26621.2 | 建议
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 目标包 | 15.0.26621.2 | 建议
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 目标包 | 15.0.26621.2 | 建议
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 目标包 | 15.0.26621.2 | 建议
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 目标包 | 15.0.26621.2 | 建议
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 开发工具 | 15.0.26606.0 | 建议
Microsoft.Net.Core.Component.SDK | .NET Core 1.0 - 1.1 开发工具 | 15.0.26606.0 | 建议
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 目标和生成任务 | 15.0.26919.1 | 建议
Microsoft.Net.Component.3.5.DeveloperTools | .NET Framework 3.5 开发工具 | 15.0.26621.2 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 目标包 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.0.27128.1 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 目标包 | 15.0.27019.1 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 15.0.26419.1 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 目标包 | 15.0.26621.2 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 开发工具 | 15.0.26621.2 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 开发工具 | 15.0.27019.1 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 开发工具 | 15.0.27005.2 | Optional

## <a name="unaffiliated-components"></a>独立组件

这些组件不随附于任何工作负载，但可选择作为单个组件。

组件 ID | name | 版本
--- | --- | ---
Microsoft.VisualStudio.Component.VC.Tools.14.11 | VC++ 2017 版本 15.4 v14.11 工具集 | 15.0.27128.1

## <a name="get-support"></a>获取支持
有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [Visual Studio 工作负荷和组件 ID](workload-and-component-ids.md)
* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
* [使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
  * [命令行参数示例](command-line-parameter-examples.md)
* [创建 Visual Studio 的脱机安装](create-an-offline-installation-of-visual-studio.md)
