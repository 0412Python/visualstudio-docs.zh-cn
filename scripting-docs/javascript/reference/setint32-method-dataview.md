---
title: setInt32 方法 (DataView) |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 07e5f068-0e3f-4c23-84b3-c72658d7f194
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 00f3f6b03cdd3a8d5d7b95184f1c0ff5c356592a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24639127"
---
# <a name="setint32-method-dataview"></a>setInt32 方法 (DataView)
从开始处的视图，请指定的字节偏移量的位置中设置的 Int32 值。 没有任何对齐约束;多字节值可能会设置任何偏移量的位置。  
  
## <a name="syntax"></a>语法  
  
```  
dataView.setInt32 (byteOffset, value, littleEndian);   
```  
  
## <a name="parameters"></a>参数  
 `byteOffset`  
 应从该处检索的值的缓冲区中的位置。  
  
 `value`  
 要设置的值。  
  
 `littleEndian`  
 可选。 如果 false 或未定义，则应编写 big endian 值，否则应编写一个小 endian 值。  
  
## <a name="remarks"></a>备注  
 如果他们将编写视图的结尾之外，这些方法将引发异常。  
  
## <a name="example"></a>示例  
 下面的示例演示如何设置第一个 Int32 处于数据视图。  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setInt32(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>要求  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]