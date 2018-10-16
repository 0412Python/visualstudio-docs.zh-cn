---
title: 如何： 安装与 SignTool.exe (ClickOnce) 文件进行签名 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, signtool.exe
- deploying applications [ClickOnce], re-signing setup.exe
- ClickOnce deployment, signtool.exe
- ClickOnce applications, re-signing setup.exe
- ClickOnce deployment, re-signing setup.exe
ms.assetid: 545a4005-d283-4110-9821-c78a9833c250
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: f6975fb9c3c3e1abeeaebe23b4a85f41833e421e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49179304"
---
# <a name="how-to-sign-setup-files-with-signtoolexe-clickonce"></a>如何：用 SignTool.exe (ClickOnce) 对安装文件进行签名
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

你可以使用 SignTool.exe 为安装程序 (setup.exe) 签名。 此过程有助于确保不会在最终用户计算机上安装经过篡改的文件。  
  
 默认情况下，ClickOnce 具有签名的清单和一个签名的安装程序。 但是，如果想在以后更改安装程序的参数，则以后必须对该安装程序进行签名。 如果对安装程序签名后更改参数，则签名将会损坏。  
  
 下面的过程将生成未签名的清单和未签名的安装程序。 然后，在 Visual Studio 中启用 ClickOnce 签名以生成签名的清单。 此安装程序将处于未签名状态，以便客户可以用他们自己的证书对可执行文件进行签名。  
  
### <a name="to-generate-an-unsigned-setup-program-and-sign-later"></a>生成未签名的安装程序并在以后进行签名  
  
1.  在开发计算机上，安装想要用于对清单进行签名的证书。  
  
2.  在解决方案资源管理器中，选择项目。  
  
3.  上**项目**菜单上，单击*ProjectName* **属性**。  
  
4.  在中**签名**页上，清除**ClickOnce 清单签名**。  
  
5.  在中**发布**页上，单击**先决条件**。  
  
6.  验证所有系统必备组件未选择，然后单击**确定**。  
  
7.  在中**发布**页上，验证的发布设置，然后单击**立即发布**。  
  
     该解决方案会将未签名的应用程序清单、未签名的部署清单、特定于版本的文件以及未签名的安装程序发布到发布文件夹位置。  
  
8.  在中**发布**页上，单击**先决条件**。  
  
9. 在中**先决条件**对话框中，清除**创建用于安装系统必备组件安装程序**。  
  
10. 在中**发布**页上，验证的发布设置，然后单击**立即发布**。  
  
     该解决方案会将签名的应用程序清单、签名的部署清单和特定于版本的文件发布到发布文件夹位置。 发布过程不会覆盖未签名的安装程序。  
  
11. 在客户站点，打开命令提示符。  
  
12. 转到包含 .exe 文件的目录。  
  
13. 利用以下命令为 .exe 文件签名：  
  
    ```  
    signtool sign /sha1 CertificateHash Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
     例如，若要为安装程序签名，请使用下列命令之一：  
  
    ```  
    signtool sign /sha1 CCB... Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
## <a name="see-also"></a>请参阅  
 [如何：为应用程序和部署清单重新签名](../deployment/how-to-re-sign-application-and-deployment-manifests.md)



