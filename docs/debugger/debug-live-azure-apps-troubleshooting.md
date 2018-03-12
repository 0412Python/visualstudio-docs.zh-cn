---
title: "有关快照调试疑难解答和已知问题 |Microsoft 文档"
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7792e22398afd476703407e8ae2159e0f1afd931
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>有关在 Visual Studio 中调试快照的疑难解答和已知问题

如果本主题中所述的步骤未解决你遇到的问题，请与联系snaphelp@microsoft.com。

## <a name="issue-snappoint-does-not-turn-on"></a>问题： Snappoint 未开启

如果看到警告图标![Snappoint 警告图标](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "Snappoint 警告图标")与你 snappoint 而不是正则 snappoint 图标，然后 snappoint 未打开。

![Snappoint 未开启](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "Snappoint 未开启")

执行以下步骤：

1. 请确保你有用于生成和部署你 app.isua1 的源代码的相同版本。 请确保要为你的部署将加载正确的符号。 若要执行此操作，查看**模块**窗口快照调试时，并验证是否为正在调试的模块加载符号文件列显示.pdb 文件。 请注意，快照调试器将尝试自动下载并为你的部署使用符号。

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>问题： 符号时不会加载打开快照

如果你看到以下窗口，则未加载符号。

![不加载符号](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "不加载符号")

执行以下步骤：

- 单击**更改符号设置...** 此页上的链接。 在**调试 > 符号**设置，将添加一个符号缓存目录。 重新启动快照调试后设置符号路径。

   符号或在你的项目中可用的.pdb 文件必须匹配你的 App Service 部署。 大多数部署 (通过 Visual Studio、 CI/CD VSTS 或 Kudu，与部署等) 将沿你符号文件发布到你的应用程序服务。 设置符号缓存目录使 Visual Studio 以使用这些符号。

   ![符号设置](../debugger/media/snapshot-troubleshooting-symbol-settings.png "符号设置")

- 或者，如果你的组织使用的符号服务器，或者将符号放置在不同的路径中，使用符号设置加载你的部署的正确符号。

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>问题： 我无法看到云资源管理器中的"附加快照调试器"选项

执行以下步骤：

- 请确保安装了快照调试器组件。 打开 Visual Studio 安装程序中，并检查**快照调试器**组件在 Azure 工作负荷。
- 确保你的应用程序受支持。 目前，只有 ASP.NET (4.6.1+) 和 ASP.NET Core （2.0 +） 应用部署到 Azure 应用程序服务都受支持。

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>问题： 我只看到限制诊断工具中的快照

![Throttled snappoint](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "限制 snappoint")

执行以下步骤：

- 快照占用很少的内存，但会提交费用。 如果快照调试器检测到你的服务器是在大量的内存负载下，它将不会快照。 你可以通过停止快照调试器会话，然后重试删除已捕获的快照。

## <a name="known-issues"></a>已知问题

- 当前不支持针对相同的应用程序服务的多个 Visual Studio 客户端调试的快照。
- ASP.NET 核心项目不完全支持 Roslyn IL 优化。 对于某些 ASP.NET Core 项目，你可能无法看到某些变量或条件语句中使用某些变量。 
- 特殊变量，如*$FUNCTION*或*$CALLER*，无法计算条件语句或 logpoints 对于 ASP.NET Core 项目中。
- 快照调试不能在应用程序服务具有[本地缓存](/azure/app-service/app-service-local-cache)开启。
- 当前不支持调试 API 应用程序的快照。

## <a name="site-extension-upgrade"></a>站点扩展升级

快照调试和 Application Insights 依赖于 ICorProfiler 也不能将加载到站点过程在升级过程中导致文件锁定问题。 我们建议使用此过程以确保没有为您的生产站点没有停机时间。

- 创建[部署槽](/azure/app-service/web-sites-staged-publishing)App Service 中并将你的网站部署到槽。
- 从 Visual Studio 中的云资源管理器或从 Azure 门户中交换槽与生产环境。
- 停止槽站点。 这将需要几秒钟来关闭从所有实例的站点 w3wp.exe 进程终止。
- 从 Kudu 站点或 Azure 门户中升级槽站点扩展 (*应用服务边栏选项卡 > 开发工具 > 扩展 > 更新*)。
- 启动槽站点。 我们建议访问网站来再次预热。
- 与生产槽交换。

## <a name="see-also"></a>请参阅

[在 Visual Studio 中进行调试](../debugger/index.md)  
[调试使用快照调试器的实时 ASP.NET 应用程序](../debugger/debug-live-azure-applications.md)  
[快照调试常见问题解答](../debugger/debug-live-azure-apps-faq.md)  
