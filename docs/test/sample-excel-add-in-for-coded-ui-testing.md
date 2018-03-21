---
title: "用于编码的 UI 测试的示例 Excel 外接程序 | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- coded UI tests, Excel Add-in sample
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: a81fd5d3d10c15d58671e7e65fae2259824afbe4
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="sample-excel-add-in-for-coded-ui-testing"></a>用于编码的 UI 测试的示例 Excel 外接程序
此 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 示例外接程序经过特别设计，用于支持对 Visual Studio Enterprise 中记录和运行的 Excel 工作表进行编码的 UI 测试。 此外接程序是使用 Visual Studio Tools for Office 创建的。

 有关如何创建 Excel 外接程序的详细信息，请参阅[演练：创建你的第一个 Excel VSTO 外接程序](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)或在 MSDN 中搜索“Excel 外接程序”。

 虽然 Excel 外接程序不是此用于 Excel 的编码的 UI 测试扩展文档的主要主题，不过有几个注释可能会有所帮助。

 此外接程序的重要部分有：

-   `ThisAddIn` 类 - 管理 `ExcelUICommunicator` 与[用于 Excel 的编码的 UI 测试扩展示例](../test/sample-coded-ui-test-extension-for-excel.md)之间的 .NET 远程通道。

-   `ExcelCodedUIAddinHelper_TemporaryKey.pfx` - 用于测试外接程序的安全证书。

-   `ExcelUICommunicator` 类 - 此类实现 `IExcelUICommunication` 接口。

## <a name="thisaddin-class"></a>ThisAddIn 类
 实际上，此类大部分是你在创建 Excel 外接程序项目时，由 Visual Studio Tools for Office 在 `ThisAddIn.Designer.cs` 中生成的。

 必须实现的成员是事件处理程序：`ThisAddIn_Startup()` 和 `ThisAddIn_Shutdown()`。 它们的用途是初始化或关闭 `ExcelUICommunicator` 使用的 .NET 远程通道。

## <a name="excelcodeduiaddinhelpertemporarykeypfx"></a>ExcelCodedUIAddinHelper_TemporaryKey.pfx
 此文件包含一个由 Visual Studio Tools for Office 生成的临时安全证书，可以授予外接程序程序集在 Excel 进程中进行操作的权限，以便测试外接程序和扩展。 应删除此证书，并且在项目“属性”窗口的“签名”选项卡中创建新证书，或附加自己的测试证书。

## <a name="exceluicommunicator-class"></a>ExcelUICommunicator 类
 此类实现 `IExcelUITestCommunication` 接口，并从 Excel 对象模型获取请求的 UI 信息。 有关详细信息，请参阅[示例 Excel Communicator 接口](../test/sample-excel-communicator-interface.md)。

## <a name="see-also"></a>请参阅

- [扩展编码的 UI 测试和操作录制以支持 Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
- [演练：创建你的第一个 Excel VSTO 外接程序](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)
- [Office 和 SharePoint 开发](/office-dev/office-dev/office-and-sharepoint-development-in-visual-studio)
