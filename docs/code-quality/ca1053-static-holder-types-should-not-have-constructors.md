---
title: CA1053:静态容器类型不应具有构造函数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da5edc8f31510fa01d2132735ede502ad7f6ad6a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55922597"
---
# <a name="ca1053-static-holder-types-should-not-have-constructors"></a>CA1053:静态容器类型不应具有构造函数

|||
|-|-|
|TypeName|StaticHolderTypesShouldNotHaveConstructors|
|CheckId|CA1053|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或嵌套公共类型只声明了静态成员，但具有公共或受保护的默认构造函数。

## <a name="rule-description"></a>规则说明
 由于调用静态成员不需要类型的示例，因此没必要使用构造函数。 此外，因为该类型不具有非静态成员，创建一个实例不提供访问任何类型的成员。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请删除默认构造函数或将其公开。

> [!NOTE]
>  如果类型未定义任何构造函数，某些编译器自动创建一个公共的默认构造函数。 如果这与您的类型的情况，请添加私有默认构造函数以消除冲突。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 构造函数存在建议的类型不是静态类型。

## <a name="example"></a>示例
 下面的示例显示了与此规则冲突的类型。 请注意，在源代码中没有默认构造函数。 当此代码编译到程序集中时，C# 编译器将插入默认构造函数，这会违反此规则。 若要更正此问题，声明一个私有构造函数。

 [!code-csharp[FxCop.Design.StaticTypes#1](../code-quality/codesnippet/CSharp/ca1053-static-holder-types-should-not-have-constructors_1.cs)]