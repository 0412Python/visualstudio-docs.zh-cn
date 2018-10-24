---
title: 控制 Visual Studio 部署的更新
description: 了解从网络安装时，如何更改 Visual Studio 查找更新的位置。
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 35C7AB05-07D5-4B38-BCAC-AB88444E7368
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9cfc35698ce87027192031ef453a4c42ecc3c199
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49830426"
---
# <a name="control-updates-to-network-based-visual-studio-deployments"></a>控制对基于网络的 Visual Studio 部署的更新

企业管理员通常会创建布局，并将其托管在网络文件共享上，以供部署给最终用户。

## <a name="controlling-where-visual-studio-looks-for-updates"></a>控制 Visual Studio 在何处查找更新

默认情况下，即使安装从网络共享进行部署，Visual Studio 也仍会继续联机查找更新。 用户可以安装可用的更新。 无法在脱机布局中找到的更新内容都将从 Web 下载。

要直接控制 Visual Studio 查找更新的位置，可对其查找的位置进行修改。 还可对控制用户更新到的版本。 为此，请执行以下步骤：

1. 创建脱机布局：
   ```cmd
   vs_enterprise.exe --layout C:\vs2017offline --lang en-US
   ```
2. 将脱机布局复制到托管文件共享上：
   ```cmd
   xcopy /e C:\vs2017offline \\server\share\VS2017
   ```
3. 修改布局中的 response.json 文件，将 `channelUri` 值更改为指向管理员控制的 channelManifest.json 的副本。

   请务必在此值中转义反斜杠，如下例所示：

   ```json
   "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
   ```

   现在，最终用户可以从此共享运行安装程序来安装 Visual Studio。
   ```cmd
   \\server\share\VS2017\vs_enterprise.exe
   ```

如果确定用户应更新到更高版本的 Visual Studio，企业管理员可以[更新布局位置](update-a-network-installation-of-visual-studio.md)，以纳入更新后的文件，如下所示。

1. 使用类似于以下的命令：
   ```cmd
   vs_enterprise.exe --layout \\server\share\VS2017 --lang en-US
   ```
2. 确保在更新后的布局中 response.json 文件仍包含自定义设置，特别是 channelUri 修改，如下所示：
   ```json
   "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
   ```
   通过此布局安装的现有 Visual Studio 将在 `\\server\share\VS2017\ChannelManifest.json` 中查找更新。 如果此 channelManifest.json 比用户已安装的版本更高，Visual Studio 会通知用户有更新可供安装。

   安装 Visual Studio 的新用户将直接通过此布局自动安装更新后的 Visual Studio 版本。

## <a name="controlling-notifications-in-the-visual-studio-ide"></a>在 Visual Studio IDE 中控制通知

如上所述，Visual Studio 检查其安装位置（例如，网络共享或 Internet），以确定是否有任何更新。 若有更新，Visual Studio 会在窗口右上角显示通知标志来通知用户。

 ![更新的通知标志](media/notification-flag.png)

如果不想提示最终用户进行更新，可禁用该通知。 （例如，如果通过中心软件分发机制来提供更新，可能希望禁用通知。）

由于 Visual Studio 2017 [将注册表项存储在专用注册表中](tools-for-managing-visual-studio-instances.md#editing-the-registry-for-a-visual-studio-instance)，因此无法照常直接编辑注册表。 不过，Visual Studio 提供可用于更改 Visual Studio 设置的实用工具 `vsregedit.exe`。 可以使用下面的命令禁用通知：

```cmd
vsregedit.exe set "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" HKCU ExtensionManager AutomaticallyCheckForUpdates2Override dword 0
```

（请确保替换目录，以匹配要编辑的已安装实例。）

> [!TIP]
> 使用 [vswhere.exe](tools-for-managing-visual-studio-instances.md#detecting-existing-visual-studio-instances) 可以在客户端工作站上查找 Visual Studio 的特定实例。

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>请参阅

* [安装 Visual Studio](install-visual-studio.md)
* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
* [使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
* [用于管理 Visual Studio 实例的工具](tools-for-managing-visual-studio-instances.md)
