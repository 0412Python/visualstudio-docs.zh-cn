---
title: byteLength 属性 (ArrayBuffer) |Microsoft 文档
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
ms.assetid: c158fa59-d006-4842-9d06-0fd8e630ea31
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5f576eb85652a7c250e0f446f4082dd6207e8fb2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24633497"
---
# <a name="bytelength-property-arraybuffer"></a>byteLength 属性 (ArrayBuffer)
只读。 ArrayBuffer 的长度（以字节为单位）。  
  
## <a name="syntax"></a>语法  
  
```JavaScript  
var arrayLength = arrayBuffer.byteLength;  
```  
  
## <a name="remarks"></a>备注  
  
## <a name="example"></a>示例  
 下面的示例演示如何获取的字节长度的 ArrayBuffer。  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
  
        alert(buffer.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>要求  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]