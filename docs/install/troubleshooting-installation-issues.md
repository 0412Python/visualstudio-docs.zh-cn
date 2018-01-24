---
title: "安装问题疑难解答 | Microsoft Docs"
description: "有时也会遇到问题。 如果 Visual Studio 安装或升级失败，可在此页寻求帮助。"
ms.date: 11/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 556EDD3F-E365-43EE-B3DD-03AA4353F75B
author: timsneath
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9cd0a1b21cf7a61c9340c36be5db419d71c36e1b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-visual-studio-2017-installation-and-upgrade-issues"></a>Visual Studio 2017 安装和升级问题疑难解答

## <a name="symptoms"></a>症状
尝试安装或更新 Visual Studio 2017 时，操作失败。

## <a name="workaround"></a>解决方法
若要解决此问题，请按照以下步骤操作。

### <a name="step-1---check-whether-this-problem-is-a-known-issue"></a>第 1 步 - 检查此问题是否是已知问题
Visual Studio 安装程序存在一些已知问题，Microsoft 正在努力修复中。 若要确定你遇到的问题是否有解决办法，请参阅[发行说明的“已知问题”部分](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#known-issues)。

### <a name="step-2---check-with-the-developer-community"></a>第 2 步 - 通过开发者社区获取帮助
在 [Visual Studio 开发人员社区](https://developercommunity.visualstudio.com/spaces/8/index.html)中搜索错误消息。 社区的其他成员可能已记录下你遇到的问题的解决方案。

### <a name="step-3---delete-the-visual-studio-installer-directory-to-fix-upgrade-problems"></a>第 3 步 - 删除 Visual Studio 安装程序目录以修复升级问题
Visual Studio 安装程序引导程序是最轻型的可执行文件，用于安装 Visual Studio 安装程序的剩余部分。 删除 Visual Studio 安装程序文件，然后重新运行引导程序，可能会修复一些更新故障。

>[!NOTE]
执行以下操作将重新安装 Visual Studio 安装程序文件并重置安装元数据。

1. 关闭 Visual Studio 安装程序。
2. 删除 Visual Studio 安装程序目录。 通常，该目录是 `C:\Program Files (x86)\Microsoft Visual Studio\Installer`。
3. 运行 Visual Studio 安装程序引导程序。 引导程序位于“下载”文件夹中，文件名格式为 `vs_[Visual Studio edition]__*.exe`。 如果找不到此应用程序，可以转到 [Visual Studio 下载](https://www.visualstudio.com/downloads/)页，然后单击你的 Visual Studio 版本所对应的“下载”，便可下载引导程序。 运行此可执行文件，重置安装元数据。
4. 尝试重新安装或更新 Visual Studio。 如果安装程序仍无法安装，请转到下一步。

### <a name="step-4---report-a-problem"></a>第 4 步 - 报告问题
在某些情况下（如出现与文件损坏相关的问题时），可能需要逐个调查每个问题：

1. 收集安装日志。 有关详细信息，请参阅[如何获取 Visual Studio 安装日志](#how-to-get-the-visual-studio-installation-logs)。
2. 打开 Visual Studio 安装程序，然后单击“报告问题”，打开 Visual Studio 反馈工具。
![可以使用 Tab 键定位到“提供反馈”按钮，从而打开反馈工具](media/report-a-problem.png)
3. 为问题报告命名一个标题，然后输入相关详细信息。 单击“下一步”，转到“附件”部分，然后附加生成的日志文件（此文件通常位于 `%TEMP%\vslogs.zip`）。
4. 单击“下一步”，检查问题报告，然后单击“提交”。

### <a name="step-5---run-installcleanupexe-to-remove-installation-files"></a>第 5 步 - 运行 InstallCleanup.exe 以删除安装文件
作为最后一种方法，可以[删除 Visual Studio](remove-visual-studio.md) 以删除所有安装文件和产品信息。

1. 按照[删除 Visual Studio](remove-visual-studio.md) 中的说明执行。
2. 按照[第 3 步 - 删除 Visual Studio 安装程序目录以修复升级问题](#step-3---delete-the-visual-studio-installer-directory-to-fix-upgrade-problems)中的说明操作，重新运行引导程序。
3. 尝试重新安装或更新 Visual Studio。

### <a name="step-6---contact-us-optional"></a>第 6 步 - 与我们联系（可选）
如果其他任何步骤都无法使你成功安装，则可以通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

## <a name="how-to-troubleshoot-an-offline-installer"></a>如何解决脱机安装程序问题
下面的表格列出了通过本地布局进行安装时的已知问题和解决办法，可能会对你有所帮助。

| 问题       | 项                   | 解决方案 |
| ----------- | ---------------------- | -------- |
| 用户没有访问文件的权限。 | 权限 (ACL) | 请确保调整权限 (ACL)，以便它们在共享脱机安装前先向其他用户授予*读取*权限。 |
| 无法安装新的工作负载、组件或语言。  | `--layout`  | 若要通过部分布局进行安装，并选择之前未在此部分布局中下载过的工作负载、组件或语言，请确保可连接到 Internet。 |

## <a name="how-to-get-the-visual-studio-installation-logs"></a>如何获取 Visual Studio 安装日志
若要排查大部分的安装问题，需要有安装日志。 使用 Visual Studio 安装程序中的[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)提交问题时，这些日志会自动添加到报告中。

如果联系 Microsoft 支持部门，可能需要使用 [Microsoft Visual Studio 和 .NET Framework 日志收集工具](https://aka.ms/vscollect)来提供这些安装日志。 日志收集工具从 Visual Studio 2017 安装的所有组件（包括 .NET Framework、Windows SDK 和 SQL Server）中收集安装日志。 它还会收集计算机信息、Windows Installer 清单，以及 Visual Studio 安装程序、Windows Installer 和系统还原的 Windows 事件日志信息。

收集日志的具体步骤：

1. [下载工具](https://aka.ms/vscollect)。
2. 打开管理命令提示符。
3. 从工具保存目录运行 `Collect.exe`。
4. 在 `%TEMP%` 目录中查找生成的 `vslogs.zip` 文件，例如，`C:\Users\YourName\AppData\Local\Temp\vslogs.zip`。

> [!NOTE]
> 工具必须在安装失败时使用的同一用户帐户下运行。 若要从其他用户帐户运行工具，请设置 `–user:<name>` 选项，以指定安装失败时使用的用户帐户。 有关其他选项和使用情况信息，请通过管理员命令提示符运行 `Collect.exe -?`。

## <a name="more-support-options"></a>更多支持选项

如果其他任何步骤都无法使你成功安装，则可以通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （这需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅
* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
* [用于检测和管理 Visual Studio 实例的工具](tools-for-managing-visual-studio-instances.md)
* [删除 Visual Studio 2017](remove-visual-studio.md)
