---
title: DISASSEMBLY_FLAGS |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DISASSEMBLY_FLAGS
helpviewer_keywords:
- DISASSEMBLY_FLAGS enumeration
ms.assetid: c1ec5a4d-5d42-4660-932c-7348550140cb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dd1aa9c73fad40d07be371ad7f9b3108464aeb34
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="disassemblyflags"></a>DISASSEMBLY_FLAGS
指定反汇编的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
typedef DWORD DISASSEMBLY_FLAGS;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
```  
  
## <a name="members"></a>成员  
 DF_DOCUMENTCHANGE  
 指示此指令为比前一个不同的文档。  
  
 DF_DISABLED  
 指示此指令将不会执行。  
  
 DF_INSTRUCTION_ACTIVE  
 指示此指令是一个要执行的下一步说明 （可能有多个）。  
  
 DF_DATA  
 指示此指令实际上是数据 （而不是代码）。  
  
 DF_HASSOURCE  
 指示此指令具有源。 某些指令，如分析或垃圾收集代码具有没有相应的源。  
  
 DF_DOCUMENT_CHECKSUM  
 指示`bstrDocumentUrl`字段后的文档 URL 包含校验和数据。 请参阅备注部分[DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)校验和数据的存储方式的结构。  
  
## <a name="remarks"></a>备注  
 用作`dwFlags`的成员[DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)结构。  
  
 这些标志可以与按位组合`OR`。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)