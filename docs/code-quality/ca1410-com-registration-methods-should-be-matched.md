---
title: CA1410：应对 COM 注册方法进行匹配
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9043425c69f95f5cb7cc414b0efe877b7db8e238
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915090"
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410：应对 COM 注册方法进行匹配
|||
|-|-|
|TypeName|ComRegistrationMethodsShouldBeMatched|
|CheckId|CA1410|
|类别|Microsoft.Interoperability|
|是否重大更改|非重大|

## <a name="cause"></a>原因
 一个类型声明的方法，将标有<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName>属性但未声明的方法，将标有<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>属性，反之亦然。

## <a name="rule-description"></a>规则说明
 组件对象模型 (COM) 客户端创建[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]类型，该类型必须首先注册。 如果不可用，将标有一个方法<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>在注册过程中，运行用户指定的代码调用属性。 相应的方法标记为<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>在反向注册方法的操作的注销过程中调用属性。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，将添加相应的注册或注销方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示与该规则冲突的类型。 注释的代码演示了冲突的修复。

 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]

## <a name="related-rules"></a>相关的规则
 [CA1411：COM 注册方法应该是不可见的](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)

## <a name="see-also"></a>请参阅
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName> [向 COM 注册程序集](/dotnet/framework/interop/registering-assemblies-with-com) [Regasm.exe （程序集注册工具）](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)