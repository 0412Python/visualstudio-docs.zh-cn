---
title: 在 Visual Studio 中的远程调试 |Microsoft 文档
ms.custom: remotedebugging
ms.date: 05/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.remote.overview
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: db20b62c5ef409f523253c5ba19e2c68213743be
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
ms.locfileid: "34477686"
---
# <a name="remote-debugging"></a>Remote Debugging
你可以调试已部署在另一台计算机的 Visual Studio 应用程序。 要进行此操作，可使用 Visual Studio 远程调试器。

有关远程调试的深入说明，请参阅这些主题。

|方案|链接|
|-|-|-|
|Azure 应用服务|[快照调试器](../debugger/debug-live-azure-applications.md)或[远程调试在 Azure 上的 ASP.NET](../debugger/remote-debugging-azure.md)|
|Azure VM|[远程调试 Azure 上的 ASP.NET](../debugger/remote-debugging-azure.md)|
|Azure Service Fabric|[调试 Azure Service Fabric 应用程序](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application)|
|ASP.NET|[远程调试 ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md) 或[远程调试 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|C# 或 Visual Basic|[远程调试 C# 或 Visual Basic 项目](../debugger/remote-debugging-csharp.md)|
|C++|[远程调试 C++ 项目](../debugger/remote-debugging-cpp.md)|
|通用 Windows 应用 (UWP)|[在远程计算机上运行 UWP 应用](../debugger/run-windows-store-apps-on-a-remote-machine.md)或[调试安装的应用包](../debugger/debug-installed-app-package.md)|

如果你只想要下载并安装远程调试器，并且不需要任何其他说明为你的方案，请按照本文中的步骤。
  
## <a name="download-and-install-the-remote-tools"></a>下载并安装远程工具  

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

## <a name="unblock_msvsmon"></a> 取消阻止 Windows 服务器上的远程工具下载

在 Windows Server 上的 Internet Explorer 中的默认安全设置可以使花费大量时间来下载组件，如远程工具。

* 在 Internet Explorer，可防止打开网站和访问 web 资源，除非显式允许包含资源的域上启用增强的安全配置 （即，受信任）。

* 在 Windows Server 2016，默认设置**Internet 选项** > **安全** > **Internet**  >  **自定义级别** > **下载**还禁用文件下载。 如果你选择下载直接在 Windows Server 上的远程工具，你必须启用文件下载。

若要下载 Windows 服务器上的工具，我们建议以下项之一：

* 下载一个正在运行 Visual Studio，例如另一台计算机上的远程工具，然后将复制 *.exe*到 Windows Server 的文件。

* 运行远程调试器[从文件共享](#fileshare_msvsmon)Visual Studio 计算机上。

* 下载直接在 Windows Server 上的远程工具，并接受提示以添加受信任的站点。 现代网站通常包括许多第三方资源，因此这可能会导致大量的提示。 此外，任何重定向的链接可能需要手动添加。 你可以选择在开始下载之前添加一些受信任的站点。 转到**Internet 选项 > 安全 > 受信任的站点 > 站点**并添加以下站点。

  * visualstudio.com
  * download.visualstudio.microsoft.com
  * 有关： 空白

  对于较旧版本的上 my.visualstudio.com 的调试器中，添加这些其他的站点，以确保该登录名成功：

  * microsoft.com
  * go.microsoft.com
  * download.microsoft.com
  * my.visualstudio.com
  * login.microsoftonline.com
  * login.live.com
  * secure.aadcdn.microsoftonline p.com
  * msft.sts.microsoft.com
  * auth.gfx.ms
  * app.vssps.visualstudio.com
  * vlscppe.microsoft.com
  * query.prod.cms.rt.microsoft.com

    如果你选择下载的远程工具时添加这些域，然后选择**添加**出现提示时。

    ![阻止内容的对话框](../debugger/media/remotedbg-blocked-content.png)

    当你下载的软件时，可以一些其他的请求，以授予加载各种 web 站点脚本和资源的权限。 My.visualstudio.com，我们建议你将其他域以确保该登录名已成功添加。

### <a name="fileshare_msvsmon"></a> （可选）若要从文件共享运行远程调试器

你可以找到远程调试器 (*msvsmon.exe*) 在 Visual Studio Community、 Professional 或 Enterprise 已安装的计算机上。 在某些情况下，设置远程调试的最简单方法是从文件共享运行远程调试器 (msvsmon.exe)。 有关使用情况限制，请参阅将远程调试器的帮助页 (**帮助 > 用法**在远程调试器中)。

1. 查找*msvsmon.exe*匹配你的 Visual Studio 版本的目录中。 针对 Visual Studio Enterprise 2017:

      *程序文件 (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x86\msvsmon.exe*
      
      *程序文件 (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x64\msvsmon.exe*

2. 共享**远程调试器**Visual Studio 计算机上的文件夹。

3. 在远程计算机上运行*msvsmon.exe*。 请按照[安装说明进行操作](#bkmk_setup)。

> [!TIP] 
> 命令行安装和命令行参考，请参阅的帮助页*msvsmon.exe*通过键入``msvsmon.exe /?``安装 Visual Studio 的计算机上的命令行中 (或转到**帮助 > 用法**在远程调试器中)。
  
## <a name="requirements_msvsmon"></a> 要求

[!INCLUDE [remote-debugger-requirements](../debugger/includes/remote-debugger-requirements.md)]
  
## <a name="set-up-the-remote-debugger"></a>设置远程调试器  

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

### <a name="configure_msvsmon"></a> 配置远程调试器  
首次启动后，你可以更改远程调试器的部分配置。
  
-   如果你需要为要连接到远程调试器，请选择其他用户添加权限**工具 > 权限**。 你必须拥有管理员特权才能授予或拒绝权限。

     > [!IMPORTANT] 
     > 你可以从所使用的 Visual Studio 计算机，用户帐户运行远程调试器使用不同的用户帐户，但必须将其他用户帐户添加到远程调试器权限。 

     或者，可以使用从命令行启动远程调试器 **/ 允许\<用户名 >** 参数： **msvsmon /allow \< username@computer>**。
  
-   如果你需要更改身份验证模式或端口号，或指定远程工具的超时值： 选择**工具 > 选项**。  
  
     默认情况下使用的端口号的列表，请参阅[远程调试器端口分配](../debugger/remote-debugger-port-assignments.md)。  
  
     > [!WARNING]
     >  可以选择在“无身份验证”模式下运行远程工具，但强烈建议不要使用此模式。 在此模式下运行时，无法保证网络安全。 只有在确认网络不会遇到恶意通信的情况下，才可选择“无身份验证”模式。

##  <a name="bkmk_configureService"></a> （可选）配置远程调试器作为服务
用于调试在 ASP.NET 和其他服务器环境中，您必须以管理员身份运行远程调试器或时，如果你希望始终运行，作为服务运行远程调试器。
  
 如果你想要配置远程调试器作为服务，请按照下列步骤。  
  
1.  找到  “远程调试器配置向导”(rdbgwiz.exe)。 （这是独立于远程调试器的应用程序。）仅当安装远程工具时它才可用。 它不与 Visual Studio 一起安装。  
  
2.  开始运行配置向导。 当第一页出现时，单击“下一步” 。  
  
3.  勾选“将 Visual Studio 2015 远程调试器作为服务运行”  复选框。  
  
4.  添加用户帐户的名称和密码。  
  
     你可能需要添加**作为服务登录**从右到此帐户的用户 (查找**本地安全策略**(secpol.msc) 中**启动**页或窗口 (或类型**secpol**在命令提示符)。 当显示窗口时，双击“用户权限分配” ，然后在右窗格中找到  “作为服务登录”。 双击该选项。 添加到的用户帐户**属性**窗口并单击**确定**)。 单击 **“下一步”**。  
  
5.  选择你希望远程工具与之通信的网络类型。 必须至少选择一种网络类型。 如果这些计算机通过域连接，则应选择第一项。 如果这些计算机通过工作组或家庭组连接，则应选择第二或第三项。 单击 **“下一步”**。  
  
6.  如果可以启动服务，则会显示 “你已成功完成 Visual Studio 远程调试器配置向导”。 如果无法启动服务，则会显示“未能完成 Visual Studio 远程调试器配置向导” 。 此页还提供了为使服务正常启动要遵循的一些提示。  
  
7.  单击 **“完成”**。  
  
 此时，远程调试器正作为服务运行。 你可以通过转到对此进行验证**控制面板 > 服务**，然后查找**Visual Studio 2015 远程调试器**。  
  
 你可以停止和启动远程调试器服务从**控制面板 > 服务**。

## <a name="set-up-debugging-with-remote-symbols"></a>使用远程符号设置调试 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]
  
## <a name="see-also"></a>请参阅  
 [调试器功能简介](../debugger/debugger-feature-tour.md)   
 [配置 Windows 防火墙以允许远程调试](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [远程调试器端口分配](../debugger/remote-debugger-port-assignments.md)   
 [远程调试远程 IIS 计算机上的 ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [远程调试错误和疑难解答](../debugger/remote-debugging-errors-and-troubleshooting.md)
