---
title: IWebAppDiagnosticsSetup::DiagnosticsSupported |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsSetup::DiagnosticsSupported
ms.assetid: 5bbcd0d0-1460-4cf7-bbb1-f4f4a04f739a
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76b3a3b4c1cbc3c5f3e9c3fddaca2be79d3f5851
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58156302"
---
# <a name="iwebappdiagnosticssetupdiagnosticssupported"></a>IWebAppDiagnosticsSetup::DiagnosticsSupported
确定此应用程序是否支持诊断。 如果[SetSite](http://go.microsoft.com/fwlink/?LinkId=232439)实现此接口具有一个非 NULL 值，在对象上名为[DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)返回`true`。 如果不是，它将返回`false`并调用[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)失败。  
  
> [!IMPORTANT]
>  [IWebAppDiagnosticsSetup 接口](../../winscript/reference/iwebappdiagnosticssetup-interface.md)是实现由 PDM v11.0 和更高版本。 在 activdbg100 中找到。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DiagnosticsSupported(        [out, retval] VARIANT_BOOL* pRetVal        );  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 如果[SetSite](http://go.microsoft.com/fwlink/?LinkId=232439)实现此接口具有一个非 NULL 值，在对象上名为[DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)返回`true`。 如果不是，它将返回`false`，并调用[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)失败。