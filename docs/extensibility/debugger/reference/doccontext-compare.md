---
title: "DOCCONTEXT_COMPARE |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DOCCONTEXT_COMPARE
helpviewer_keywords: DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d2882ebf3a1b21a4921f863496a42ac50ac1b2fa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
指定用于比较两个文档上下文的条件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```csharp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## <a name="members"></a>成员  
 DOCCONTEXT_EQUAL  
 查找列表，它等于目标文档上下文中的第一个文档上下文。  
  
 DOCCONTEXT_LESS_THAN  
 在小于目标文档上下文的列表中找到的第一个文档上下文。  
  
 DOCCONTEXT_GREATER_THAN  
 查找列表大于目标文档上下文中的第一个文档上下文。  
  
 DOCCONTEXT_SAME_DOCUMENT  
 在同一文档作为目标文档上下文中的列表中找到的第一个文档上下文。  
  
## <a name="remarks"></a>备注  
 作为自变量传递[比较](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)方法。  
  
 这些值用于指定在列表中查找第一个文档上下文比较条件。 文档上下文提供文档上下文中的一组要比较本身针对通过`IDebugDocumentContext2::Compare`方法。 为其比较运算符的列表中的第一个文档上下文`true`随后会返回。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)