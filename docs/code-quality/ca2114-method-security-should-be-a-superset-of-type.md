---
title: CA2114：方法安全性应是类型安全性的超集
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5d2fc6fb60dd837dd93de1db2758ee0e2c216850
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114：方法安全性应是类型安全性的超集
|||
|-|-|
|TypeName|MethodSecurityShouldBeASupersetOfType|
|CheckId|CA2114|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 某个类型有声明性安全和其方法之一具有相同的安全操作的声明性安全并且安全操作不是[链接需求](/dotnet/framework/misc/link-demands)，和由类型检查的权限不是权限的子集该方法检查。

## <a name="rule-description"></a>规则说明
 同时为同一操作的方法级别和类型级别的声明性安全，不应具有一种方法。 不会合并两个检查;仅方法级别要求应用。 例如，如果一个类型要求的权限`X`，其方法之一要求的权限和`Y`，代码不需要具有权限`X`执行方法。

## <a name="how-to-fix-violations"></a>如何解决冲突
 评审以确保这两种操作所需的代码。 如果这两种操作是必需的请确保方法级别的操作包括指定类型级别的安全性。 例如，如果你的类型要求的权限`X`，而其方法必须还要求权限`Y`，该方法应显式要求`X`和`Y`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 则可以安全地禁止显示此规则的警告，如果方法不需要类型所指定的安全性。 但是，这不是普通情况，可能表明需要进行仔细的设计检查。

## <a name="example"></a>示例
 下面的示例使用环境权限来演示违反此规则的风险。 在此示例中，应用程序代码在拒绝类型所需的权限之前创建受保护的类型的实例。 在现实世界威胁方案中，应用程序将需要另一种方法获取对象的实例。

 在下面的示例中，库需求写入类型的权限和读取权限的方法。

 [!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]

## <a name="example"></a>示例
 下面的应用程序代码通过调用方法，即使它不满足类型级安全性要求演示漏洞的修补程序的库。

 [!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]

 本示例生成以下输出。

 **[所有权限]个人信息： 6/16/1964年 12:00:00 AM**
 **[没有写入权限 （按类型比较）] 的个人信息： 6/16/1964年 12:00:00 AM**
 **[没有读取权限 （要求的方法）] 无法访问个人信息： 请求失败。**
## <a name="see-also"></a>请参阅
 [安全编码准则](/dotnet/standard/security/secure-coding-guidelines)[链接需求](/dotnet/framework/misc/link-demands)[数据和建模](/dotnet/framework/data/index)