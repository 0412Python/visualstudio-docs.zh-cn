---
title: CA1724： 类型名不应与命名空间 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 39e6b539d0259f83475e3e3a685bed7ffe6a7c87
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724：类型名不应与命名空间冲突
|||  
|-|-|  
|TypeName|TypeNamesShouldNotMatchNamespaces|  
|CheckId|CA1724|  
|类别|Microsoft.Naming|  
|是否重大更改|重大|  
  
## <a name="cause"></a>原因  
 类型名与匹配[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]不区分大小写的比较中的命名空间名称。  
  
## <a name="rule-description"></a>规则说明  
 类型名称不应该与 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 类库中定义的命名空间的名称匹配。 与该规则冲突将使库的可用性下降。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 选择的名称不匹配的类型名称[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]类库命名空间。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 对于新开发，没有已知会出现情况，必须在此禁止显示此规则的警告。 禁止显示警告之前，请仔细考虑如何你的库的用户也可能因匹配名称产生混淆。 发布库，你可能需要禁止显示此规则的警告。