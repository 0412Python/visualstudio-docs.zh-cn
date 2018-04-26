---
title: CA1405：COM 可见类型的基类型应对 COM 可见
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1eefb3fdb207ecacca4998168509e8c5b9b1a2f1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405：COM 可见类型的基类型应对 COM 可见
|||
|-|-|
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|
|CheckId|CA1405|
|类别|Microsoft.Interoperability|
|是否重大更改|DependsOnFix|

## <a name="cause"></a>原因
 组件对象模型 (COM) 可见类型派生自不是 COM 可见的类型。

## <a name="rule-description"></a>规则说明
 当 COM 可见类型将成员添加的新版本中时，它必须遵守的严格的准则，以避免中断绑定到当前版本的 COM 客户端。 对 COM 不可见的类型假定它不需要遵循以下 COM 版本控制规则，当它添加新成员时。 但是，如果某个 COM 可见类型派生自 COM 可见类型中，公开的类接口<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName>或<xref:System.Runtime.InteropServices.ClassInterfaceType>（默认值）、 基类型的所有公共成员 （除非它们专门标记为 COM 可见，这样具有冗余）公开给 com。 如果基类型的后续版本中添加新成员，可能会中断将绑定到的类接口派生的任何的类型 COM 客户端。 COM 可见类型应该派生 COM 可见类型，以降低破坏 COM 客户端的可能性。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，则请 COM 可见的基类型或派生的类型 COM 可见。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示与该规则冲突的类型。

 [!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]

## <a name="see-also"></a>请参阅
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName> [与非托管代码交互操作](/dotnet/framework/interop/index)