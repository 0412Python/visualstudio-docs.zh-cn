---
title: CA1307：指定 StringComparison
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dac870bde757d77e1d0025a1b387f54ca928a5f1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307：指定 StringComparison
|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|类别|Microsoft.Globalization|
|是否重大更改|非重大|

## <a name="cause"></a>原因
 字符串比较运算使用不设置的方法重载<xref:System.StringComparison>参数。

## <a name="rule-description"></a>规则说明
 许多字符串运算，最重要<xref:System.String.Compare%2A>和<xref:System.String.Equals%2A>方法，提供接受的重载<xref:System.StringComparison>作为参数的枚举值。

 每当重载存在接受<xref:System.StringComparison>参数，它应使用而不是不使用此参数的重载。 通过显式设置此参数，你的代码通常是发出更清楚且更易维护。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，请将字符串比较方法更改为接受的重载<xref:System.StringComparison>枚举作为参数。 例如： 更改`String.Compare(str1, str2)`到`String.Compare(str1, str2, StringComparison.Ordinal)`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 则可以安全地禁止显示此规则的警告，当库或应用程序适用于有限的本地用户，并因此不会本地化。

## <a name="see-also"></a>请参阅
 [全球化警告](../code-quality/globalization-warnings.md) [CA1309： 使用序号 StringComparison](../code-quality/ca1309-use-ordinal-stringcomparison.md)