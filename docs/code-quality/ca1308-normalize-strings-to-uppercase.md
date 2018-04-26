---
title: CA1308：将字符串规范化为大写
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a5cda66d2a43ee3fde8e3e7b2d22a64a09655da3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308：将字符串规范化为大写
|||
|-|-|
|TypeName|NormalizeStringsToUppercase|
|CheckId|CA1308|
|类别|Microsoft.Globalization|
|是否重大更改|非重大|

## <a name="cause"></a>原因
 某个操作将正常化为小写的字符串。

## <a name="rule-description"></a>规则说明
 字符串应正常化为大写字母。 小的一组字符，如果它们转换为小写形式，则不能再转换回来。 若要进行往返行程表示要转换的字符从一个区域设置为以不同方式，表示字符数据的另一个区域设置，然后执行到准确地检索从已转换的字符的原始字符。

## <a name="how-to-fix-violations"></a>如何解决冲突
 更改操作将字符串转换为小写，以便将字符串转换为改为大写。 例如，更改`String.ToLower(CultureInfo.InvariantCulture)`到`String.ToUpper(CultureInfo.InvariantCulture)`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 则可以安全地禁止显示一条警告消息，当您不需要安全决策基于 （例如，当在 UI 中显示时） 的结果。

## <a name="see-also"></a>请参阅
 [全球化警告](../code-quality/globalization-warnings.md)