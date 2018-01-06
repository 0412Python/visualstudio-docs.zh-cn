---
title: "如何： 创建产品清单 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- product files [ClickOnce]
- product files [Windows Installer]
- prerequisites, custom bootstrapper package
- dependencies, custom bootstrapper package
ms.assetid: 2d316aaa-8bc0-4ce5-90ab-23b3eac0b5dd
caps.latest.revision: "10"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 071bfa46df7e11f760bc32cda0a732388835d2d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-product-manifest"></a>如何：创建产品清单
若要部署你的应用程序的先决条件，你可以创建引导程序包。 引导程序包包含一个单个产品清单文件，但是包清单的每个区域设置。 包清单中包含包的本地化特定的方面。 这包括字符串、 最终用户许可协议和语言包。  
  
 有关产品清单的详细信息，请参阅[如何： 创建程序包清单](../deployment/how-to-create-a-package-manifest.md)。  
  
## <a name="creating-the-product-manifest"></a>创建产品清单  
  
#### <a name="to-create-the-product-manifest"></a>若要创建产品清单  
  
1.  创建引导程序包的目录。 此示例使用 C:\package。  
  
2.  在 Visual Studio 中，创建新的 XML 文件调用`product.xml`，并将其保存到 C:\package 文件夹。  
  
3.  添加以下 XML 来描述包的 XML 命名空间和产品代码。 将产品代码替换包的唯一标识符。  
  
    ```  
    <Product  
    xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"   
    ProductCode="Custom.Bootstrapper.Package">  
    ```  
  
4.  添加 XML，以指定包具有依赖关系。 此示例使用在 Microsoft Windows Installer 3.1 上的依赖关系。  
  
    ```  
    <RelatedProducts>  
        <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />  
      </RelatedProducts>  
    ```  
  
5.  添加 XML，以列出相应的引导程序包中的所有文件。 此示例使用的包文件名称 CorePackage.msi。  
  
    ```  
    <PackageFiles>  
        <PackageFile Name="CorePackage.msi"/>  
    </PackageFiles>  
    ```  
  
6.  复制或移动到 C:\package 文件夹 CorePackage.msi 文件。  
  
7.  添加 XML，以使用引导程序命令安装包。 引导程序会自动添加**/qn**将以无提示方式安装的.msi 文件的标志。 如果该文件是.exe，引导程序通过使用命令行界面运行.exe 文件。 下面的 XML 演示没有自变量到 CorePackage.msi，但你可以将命令行自变量放入参数属性。  
  
    ```  
    <Commands>  
        <Command PackageFile="CorePackage.msi" Arguments="">  
    ```  
  
8.  添加以下 XML，以检查是否安装了此引导程序包。 产品代码替换为可再发行组件的 GUID。  
  
    ```  
    <InstallChecks>  
        <MsiProductCheck   
            Property="IsMsiInstalled"   
            Product="{XXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>  
    </InstallChecks>  
    ```  
  
9. 添加 XML，以更改具体取决于的引导程序行为，如果已安装的引导程序组件。 如果安装的组件，引导程序包将不运行。 下面的 XML 检查当前用户是否是管理员，因为此组件需要管理特权。  
  
    ```  
    <InstallConditions>  
        <BypassIf   
           Property="IsMsiInstalled"   
           Compare="ValueGreaterThan" Value="0"/>  
        <FailIf Property="AdminUser"   
            Compare="ValueNotEqualTo" Value="True"  
            String="NotAnAdmin"/>  
    </InstallConditions>  
    ```  
  
10. 添加 XML，以设置退出代码，如果安装成功和是否需要重新启动。 下面的 XML 演示失败，而且 FailReboot 退出代码，指示引导程序将不继续安装包。  
  
    ```  
    <ExitCodes>  
        <ExitCode Value="0" Result="Success"/>  
        <ExitCode Value="1641" Result="SuccessReboot"/>  
        <ExitCode Value="3010" Result="SuccessReboot"/>  
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>  
    </ExitCodes>  
    ```  
  
11. 添加以下 XML，以结束引导程序的命令部分。  
  
    ```  
        </Command>  
    </Commands>  
    ```  
  
12. 将 C:\package 文件夹移动到 Visual Studio 引导程序目录。 对于 Visual Studio 2010 中，这是 files\microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages 目录。  
  
## <a name="example"></a>示例  
 产品清单包含自定义系统必备组件的安装说明。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<Product  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  ProductCode="Custom.Bootstrapper.Package">  
  
  <RelatedProducts>  
    <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />  
  </RelatedProducts>  
  
  <PackageFiles>  
    <PackageFile Name="CorePackage.msi"/>  
  </PackageFiles>  
  
  <InstallChecks>  
    <MsiProductCheck Product="IsMsiInstalled"   
      Property="{XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>  
  </InstallChecks>  
  
  <Commands>  
    <Command PackageFile="CorePackage.msi" Arguments="">  
  
      <InstallConditions>  
        <BypassIf Property="IsMsiInstalled"  
          Compare="ValueGreaterThan" Value="0"/>  
        <FailIf Property="AdminUser"   
          Compare="ValueNotEqualTo" Value="True"  
         String="NotAnAdmin"/>  
      </InstallConditions>  
  
      <ExitCodes>  
        <ExitCode Value="0" Result="Success"/>  
        <ExitCode Value="1641" Result="SuccessReboot"/>  
        <ExitCode Value="3010" Result="SuccessReboot"/>  
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>  
      </ExitCodes>  
    </Command>  
  </Commands>  
</Product>  
```  
  
## <a name="see-also"></a>请参阅  
 [产品和包架构引用](../deployment/product-and-package-schema-reference.md)