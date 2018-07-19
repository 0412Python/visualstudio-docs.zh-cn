---
title: 如何： 发布具有特定的区域设置的项目 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, localized projects
- locales, publishing for
- deploying applications [ClickOnce], localized projects
- locales, deploying for
- publishing localized projects
- macros, deploying with
- macros, publishing with
ms.assetid: 7c4cd83a-f985-4c85-9022-fadb5dbd2b39
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4752556fadead75bb29b6920d51ebbb54a5679aa
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080794"
---
# <a name="how-to-publish-a-project-that-has-a-specific-locale"></a>如何： 发布具有特定的区域设置的项目
一个应用程序包含多个具有不同区域设置的组件的现象并不少见。 在本方案中，你将创建一个包含若干个项目的解决方案，然后为每个区域设置发布不同的项目。 本过程演示如何使用宏，用“en”区域设置发布解决方案中第一个项目。 如果希望使用“en”之外的其他区域设置来尝试此过程，请务必将宏中的 `localeString` 设置为与所用区域设置（例如，“de”或“de-DE”）相匹配的值。  
  
> [!NOTE]
>  在使用此宏时，“发布位置”应当是一个有效的 URL 或通用命名约定 (UNC) 共享。 此外，还必须在你的计算机上安装 Internet 信息服务 (IIS)。 若要安装 IIS，请在**启动**菜单上，单击**控制面板**。 双击**添加或删除程序**。 在中**添加或删除程序**，单击**添加/删除 Windows 组件**。 在中**Windows 组件向导**，选择**Internet 信息服务 (IIS)** 中的复选框**组件**列表。 然后单击**完成**以关闭向导。  
  
### <a name="to-create-the-publishing-macro"></a>创建发布宏  
  
1.  若要打开 Macro 资源管理器，在**工具**菜单，依次指向**宏**，然后单击**Macro 资源管理器**。  
  
2.  创建一个新的宏模块。 在 Macro 资源管理器，选择**MyMacros**。 上**工具**菜单，依次指向**宏**，然后单击**新建宏模块**。 该模块**命名为 PublishSpecificCulture**。  
  
3.  在 Macro 资源管理器，展开**MyMacros**节点，然后再打开**PublishAllProjects**模块通过双击 (或从**工具**菜单，指向**宏**，然后单击**宏 IDE**)。  
  
4.  在“宏 IDE”中，将以下代码添加到该模块中 `Import` 语句的后面：  
  
    ```vb  
    Module PublishSpecificCulture  
        Sub PublishProjectFirstProjectWithEnLocale()  
            ' Note: You should publish projects by using the IDE at least once  
            ' before you use this macro. Items such as the certficate and the   
            ' security zone must be set.  
            Dim localeString As String = "en"  
  
            ' Get first project.  
            Dim proj As Project = DTE.Solution.Projects.Item(1)  
            Dim publishProperties As Object = proj.Properties.Item("Publish").Value  
  
            ' GenerateManifests and SignManifests must always be set to  
            ' True for publishing to work.   
            proj.Properties.Item("GenerateManifests").Value = True  
            proj.Properties.Item("SignManifests").Value = True  
  
            'Set the publish language.  
            'This will set the deployment language and pick up all   
            ' en resource dlls:  
            Dim originalTargetCulture As String = _  
                publishProperties.Item("TargetCulture").Value  
            publishProperties.Item("TargetCulture").Value = localeString  
  
            'Append 'en' to end of publish, install, and update URLs if needed:  
            Dim originalPublishUrl As String = _  
                publishProperties.Item("PublishUrl").Value  
            Dim originalInstallUrl As String = _  
                publishProperties.Item("InstallUrl").Value  
            Dim originalUpdateUrl As String = _  
                publishProperties.Item("UpdateUrl").Value  
            publishProperties.Item("PublishUrl").Value = _  
                AppendStringToUrl(localeString, New Uri(originalPublishUrl))  
            If originalInstallUrl <> String.Empty Then  
                publishProperties.Item("InstallUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalInstallUrl))  
            End If  
            If originalUpdateUrl <> String.Empty Then  
                publishProperties.Item("UpdateUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalUpdateUrl))  
            End If  
            proj.Save()  
  
            Dim slnbld2 As SolutionBuild2 = _  
                CType(DTE.Solution.SolutionBuild, SolutionBuild2)  
            slnbld2.Clean(True)  
  
            slnbld2.BuildProject( _  
            proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
            proj.UniqueName, True)  
  
            ' Only publish if build is successful.  
            If slnbld2.LastBuildInfo <> 0 Then  
                MsgBox("Build failed for " & proj.UniqueName)  
            Else  
                slnbld2.PublishProject( _  
                proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
                proj.UniqueName, True)  
                If slnbld2.LastPublishInfo = 0 Then  
                    MsgBox("Publish succeeded for " & proj.UniqueName _  
                    & vbCrLf & "." _  
                    & " Publish Language was '" & localeString & "'.")  
                Else  
                    MsgBox("Publish failed for " & proj.UniqueName)  
                End If  
            End If  
  
            ' Return URLs and target culture to their previous state.  
            publishProperties.Item("PublishUrl").Value = originalPublishUrl  
            publishProperties.Item("InstallUrl").Value = originalInstallUrl  
            publishProperties.Item("UpdateUrl").Value = originalUpdateUrl  
            publishProperties.Item("TargetCulture").Value = originalTargetCulture  
            proj.Save()  
        End Sub  
  
        Private Function AppendStringToUrl(ByVal str As String, _  
        ByVal baseUri As Uri) As String  
            Dim returnValue As String = baseUri.OriginalString  
            If baseUri.IsFile OrElse baseUri.IsUnc Then  
                returnValue = IO.Path.Combine(baseUri.OriginalString, str)  
            Else  
                If Not baseUri.ToString.EndsWith("/") Then  
                    returnValue = baseUri.OriginalString & "/" & str  
                Else  
                    returnValue = baseUri.OriginalString & str  
                End If  
            End If  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
5.  关闭“宏 IDE”。 焦点将返回到 Visual Studio。  
  
### <a name="to-publish-a-project-for-a-specific-locale"></a>发布针对特定区域设置的项目  
  
1.  若要创建 Visual Basic Windows 应用程序项目，在**文件**菜单，依次指向**新建**，然后单击**项目**。  
  
2.  在中**新的项目**对话框中，选择**Windows 应用程序**从**Visual Basic**节点。 将项目命名*PublishLocales*。  
  
3.  单击 Form1。 在中**属性**窗口下**设计**，更改**语言**属性从 **（默认）** 到**英语**. 更改**文本**到窗体的属性**MyForm**。  
  
     请注意，只在需要时才会创建本地化的资源 DLL。 例如，在指定了新的区域设置后，如果更改窗体的文本或它的某个控件，便会创建本地化的资源 DLL。  
  
4.  将发布*PublishLocales*通过使用 Visual Studio IDE。  
  
     在中**解决方案资源管理器**，选择*PublishLocales*。 上**项目**菜单中，选择**属性**。 在项目设计器上**发布**页上，指定的发布位置**http://localhost/PublishLocales**，然后单击**立即发布**。  
  
     当出现发布网页时，关闭它。 （对于此步骤，你只需发布该项目，而不必安装它。）  
  
5.  将发布*PublishLocales*再次通过调用 Visual Studio 命令提示符窗口中的宏。 若要查看命令提示符窗口中，在**视图**菜单，依次指向**其他 Windows** ，然后单击**命令窗口**，或按**Ctrl** +**Alt**+**A**。 在命令提示符窗口中，键入`macros`; 自动补全将提供可用宏的列表。 选择以下宏并按 Enter：  
  
     `Macros.MyMacros.PublishSpecificCulture.PublishProjectFirstProjectWithEnLocale`  
  
6.  当发布过程成功后时，它将生成一条消息，指出"已成功发布*PublishLocales\PublishLocales.vbproj*。 发布语言为‘en’”。单击**确定**消息框中。 发布网页出现时，单击**安装**。  
  
7.  查找范围*C:\Inetpub\wwwroot\PublishLocales\en*。 您应看到已安装的文件清单，如*setup.exe*，和发布网页文件，除了已本地化的资源 DLL。 (默认情况下 ClickOnce 将追加 *.deploy* Exe 和 Dll; 上的扩展部署后，可以删除此扩展。)  
  
## <a name="see-also"></a>请参阅  
 [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)   
 [宏开发环境](http://msdn.microsoft.com/en-us/d23105d8-34fe-4ad9-8278-fae2c660aeac)   
 [宏资源管理器窗口](http://msdn.microsoft.com/en-us/762169e6-f83f-44b4-bffa-d0f107cae9a3)   
 [如何： 编辑和以编程方式创建宏](http://msdn.microsoft.com/en-us/6716f820-1feb-48ad-a718-27eb6b473c5a)