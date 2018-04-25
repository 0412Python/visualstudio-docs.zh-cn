---
title: Visual Studio 无法恢复的处理器错误 | Microsoft Docs
ms.custom: ''
ms.date: 02/23/2017
ms.topic: conceptual
helpviewer_keywords:
- editor
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 37cb88b9a07728c2e8c263551e9f0aa2e750ec12
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# Visual Studio 无法恢复的处理器错误

Visual Studio 2017 使用多个进程外的进程来运行必需的后台任务，如实时单元测试、代码分析器等。 在进程外运行这些进程可提供 Visual Studio 性能优势，例如运行资源密集型作业或长时间运行的作业时，Visual Studio 可更快响应。 此外，由于 Visual Studio 是一个 32 位进程，在进程外运行进程可为内存密集型作业提供更大的操作内存空间。

如果由于某种原因，其中的任何所需进程结束了，将出现一个包含以下消息的弹出信息栏：

“很抱歉，Visual Studio 使用的进程遇到不可恢复的错误。 建议保存你的工作，然后关闭并重新启动 Visual Studio。”

如果看到此消息，应立即保存工作，然后关闭并重新启动 Visual Studio。 如果不这样做，Visual Studio 随时可能会崩溃。

## 进程列表

下面是 Visual Studio 使用的进程外的进程列表，为了使 Visual Studio 正常运行，必须运行以下进程。

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- PerfWatson2.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.VSDetouredHost.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- ServiceHub.RoslynCodeAnalysisService.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe
- WaAppAgent.exe
