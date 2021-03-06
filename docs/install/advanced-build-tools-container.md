---
title: 容器的高级示例
description: ''
ms.date: 04/18/2018
ms.topic: conceptual
ms.assetid: e03835db-a616-41e6-b339-92b41d0cfc70
author: heaths
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: fb273a54a89bb4c0339cac739b9dd0fe7fdd0afc
ms.sourcegitcommit: 489aca71046fb6e4aafd0a4509cd7dc149d707b1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58415585"
---
# <a name="advanced-example-for-containers"></a>容器的高级示例

[将生成工具安装到容器](build-tools-container.md)中的示例 Dockerfile 始终使用基于最新 microsoft/windowsservercore 映像和最新 Visual Studio 生成工具安装程序的 [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) 映像。 如果将此映像发布到 [Docker 注册表](https://azure.microsoft.com/services/container-registry)以供他人进行拉取，则此映像可能适用于许多方案。 但在实际中，更常见的是明确使用的基础映像、下载的二进制文件和安装的工具版本。

下面的示例 Dockerfile 使用 microsoft/dotnet-framework 映像的特定版本标记。 对基础映像使用特定标记十分普遍，这样可轻松记住生成或重新生成映像始终具有相同基础。

> [!NOTE]
> 无法将 Visual Studio 安装到 microsoft/windowsservercore:10.0.14393.1593 或任何基于它的映像中，后者具有与在容器中启动安装程序有关的已知问题。 有关详细信息，请参阅[容器的已知问题](build-tools-container-issues.md)。

以下示例下载的是生成工具的最新版本。 若要使用可稍后安装到容器中的旧版生成工具，则必须先[创建](create-an-offline-installation-of-visual-studio.md)和[维护](update-a-network-installation-of-visual-studio.md)布局。

## <a name="install-script"></a>安装脚本

若要在发生安装错误时收集日志，请在工作目录中创建名为“Install.cmd”的批处理脚本，它包含以下内容：

```shell
@if not defined _echo echo off
setlocal enabledelayedexpansion

call %*
if "%ERRORLEVEL%"=="3010" (
    exit /b 0
) else (
    if not "%ERRORLEVEL%"=="0" (
        set ERR=%ERRORLEVEL%
        call C:\TEMP\collect.exe -zip:C:\vslogs.zip

        exit /b !ERR!
    )
)
```

## <a name="dockerfile"></a>Dockerfile

在工作目录中，使用以下内容创建“Dockerfile”：

::: moniker range="vs-2017"

```dockerfile
# escape=`

# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:1a66e2b5f3a5b8b98ac703a8bfd4902ae60d307ed9842978df40dbc04ac86b1b
ARG FROM_IMAGE=microsoft/dotnet-framework:4.7.1-20180410-windowsservercore-1709
FROM ${FROM_IMAGE}

# Copy our Install script.
COPY Install.cmd C:\TEMP\

# Download collect.exe in case of an install failure.
ADD https://aka.ms/vscollect.exe C:\TEMP\collect.exe

# Use the latest release channel. For more control, specify the location of an internal layout.
ARG CHANNEL_URL=https://aka.ms/vs/15/release/channel
ADD ${CHANNEL_URL} C:\TEMP\VisualStudio.chman

# Download and install Build Tools excluding workloads and components with known issues.
ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe
RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
    --installPath C:\BuildTools `
    --channelUri C:\TEMP\VisualStudio.chman `
    --installChannelUri C:\TEMP\VisualStudio.chman `
    --all `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
    --remove Microsoft.VisualStudio.Component.Windows81SDK

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

   > [!WARNING]
   > 无法在 mcr\.microsoft\.com\/windows\/servercore:1809 或更高版本上正常安装 Visual Studio 2017 版本 15.8 或更低版本（任何产品）。 不显示任何错误信息。
   >
   > 有关详细信息，请参阅[容器的已知问题](build-tools-container-issues.md)。

::: moniker-end

::: moniker range="vs-2019"

```dockerfile
# escape=`

# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:1a66e2b5f3a5b8b98ac703a8bfd4902ae60d307ed9842978df40dbc04ac86b1b
ARG FROM_IMAGE=microsoft/dotnet-framework:4.7.1-20180410-windowsservercore-1709
FROM ${FROM_IMAGE}

# Copy our Install script.
COPY Install.cmd C:\TEMP\

# Download collect.exe in case of an install failure.
ADD https://aka.ms/vscollect.exe C:\TEMP\collect.exe

# Use the latest release channel. For more control, specify the location of an internal layout.
ARG CHANNEL_URL=https://aka.ms/vs/16/release/channel
ADD ${CHANNEL_URL} C:\TEMP\VisualStudio.chman

# Download and install Build Tools excluding workloads and components with known issues.
ADD https://aka.ms/vs/16/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe
RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
    --installPath C:\BuildTools `
    --channelUri C:\TEMP\VisualStudio.chman `
    --installChannelUri C:\TEMP\VisualStudio.chman `
    --all `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
    --remove Microsoft.VisualStudio.Component.Windows81SDK

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

::: moniker-end

运行以下命令以在当前工作目录中生成映像：

::: moniker range="vs-2017"

```shell
docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
```

::: moniker-end

::: moniker range="vs-2019"

```shell
docker build -t buildtools2019:16.0.28714.193 -t buildtools2019:latest -m 2GB .
```

::: moniker-end

使用 `--build-arg` 命令行开关选择性地传递某个或同时传递 `FROM_IMAGE` 或 `CHANNEL_URL` 参数，以指定不同的基础映像或内部布局的位置来保持固定的映像。

## <a name="diagnosing-install-failures"></a>诊断安装失败

此示例下载特定工具并验证哈希代码是否匹配。 它还下载最新 Visual Studio 和 .NET 日志收集实用工具，以便在安装失败时，可以将日志复制到主机以分析失败。

::: moniker range="vs-2017"

```shell
> docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
Sending build context to Docker daemon

...
Step 8/10 : RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache ...
 ---> Running in 4b62b4ce3a3c
The command 'cmd /S /C C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe ...' returned a non-zero code: 1603

> docker cp 4b62b4ce3a3c:C:\vslogs.zip "%TEMP%\vslogs.zip"
```
::: moniker-end

::: moniker range="vs-2019"

```shell
> docker build -t buildtools2019:16.0.28714.193 -t buildtools2019:latest -m 2GB .
Sending build context to Docker daemon

...
Step 8/10 : RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache ...
 ---> Running in 4b62b4ce3a3c
The command 'cmd /S /C C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe ...' returned a non-zero code: 1603

> docker cp 4b62b4ce3a3c:C:\vslogs.zip "%TEMP%\vslogs.zip"

::: moniker-end

After the last line finishes executing, open "%TEMP%\vslogs.zip" on your machine, or submit an issue on the [Developer Community](https://developercommunity.visualstudio.com) website.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## See also

* [Install Build Tools into a Container](build-tools-container.md)
* [Known Issues for Containers](build-tools-container-issues.md)
* [Visual Studio Build Tools workload and component IDs](workload-component-id-vs-build-tools.md)
