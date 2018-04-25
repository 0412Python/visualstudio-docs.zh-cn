---
title: 属性术语表 | Microsoft IntelliTest 开发人员测试工具 | Microsoft Docs
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Attribute glossary
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: fd799598f7e497c217024965d7a83ff1df322acd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="attribute-glossary"></a>属性术语表

## <a name="attributes-by-namespace"></a>按命名空间分的属性

* **Microsoft.Pex.Framework**
  * [PexAssumeNotNull](#pexassumenotnull)
  * [PexClass](#pexclass)
  * [PexGenericArguments](#pexgenericarguments)
  * [PexMethod](#pexmethod)
     - [PexExplorationAttributeBase](#pexexplorationattributebase)<p />

* **Microsoft.Pex.Framework.Settings**
  * [PexAssemblySettings](#pexassemblysettings)<p />

* **Microsoft.Pex.Framework.Instrumentation**
  * [PexAssemblyUnderTest](#pexassemblyundertest)
  * [PexInstrumentAssembly](#pexinstrumentassemblyattribute)<p />

* **Microsoft.Pex.Framework.Using**
  * [PexUseType](#pexusetype)<p />

* **Microsoft.Pex.Framework.Validation**
  * [PexAllowedException](#pexallowedexception)
  * [PexAllowedExceptionFromAssembly](#pexallowedexceptionfromassembly)
  * [PexAllowedExceptionFromType](#pexallowedexceptionfromtype)
  * [PexAllowedExceptionFromTypeUnderTest](#pexallowedexceptionfromtypeundertest)

<a name="pexassumenotnull"></a>
## <a name="pexassumenotnull"></a>PexAssumeNotNull

此属性表示控制的值不能为“null”。 可以将其附加到：

* 参数化测试方法的参数

  ```
  // assume foo is not null
  [PexMethod]
  public void SomeTest([PexAssumeNotNull]IFoo foo, ...) {}
  ```

* 字段

  ```
  public class Foo {
     // this field should not be null
     [PexAssumeNotNull]
     public object Bar;
  }
  ```

* 类型

  ```
  // never consider null for Foo types
  [PexAssumeNotNull]
  public class Foo {}
  ```

该属性还可附加到测试程序集、测试装置或测试方法；在这种情况下，第一个参数必须指示假设应用到的字段或类型。 属性应用到类型时，该参数会应用到采用此正式类型的所有字段。

<a name="pexclass"></a>
## <a name="pexclass"></a>PexClass

此属性标记包含“explorations”的类。 它等同于 MSTest TestClassAttribute（或 NUnit TestFixtureAttribute）。 此属性是可选的。

标记为 [PexClass](#pexclass) 的类必须采用默认构造类型：

* 公开导出的类型
* 默认构造函数
* 非抽象

如果类不满足这些要求，系统会报错，浏览失败。

此外，强烈建议使这些类成为“部分”，便于 IntelliTest 生成属于该类但位于单独文件的新类。 此方法可解决因[可见性](input-generation.md#visibility)引起的许多问题，是 C# 中的典型技术。

**其他套件和类别**：

```
[TestClass] // MSTest test fixture attribute
[PexClass(Suite = "checkin")] // fixture attribute
public partial class MyTests { ... }
```

**指定待测试的类型**：

```
[PexClass(typeof(Foo))] // this is a test for Foo
public partial class FooTest { ... }
```

类可能包含注释为 [PexMethod](#pexmethod) 的方法。 IntelliTest 还理解[设置和清理方法](test-generation.md#setup-teardown)。

<a name="pexgenericarguments"></a>
## <a name="pexgenericarguments"></a>PexGenericArguments

此属性为实例化[泛型参数化单元测试](test-generation.md#generic-parameterized)提供类型元组。

<a name="pexmethod"></a>
## <a name="pexmethod"></a>PexMethod

此属性将方法标识为[参数化单元测试](test-generation.md#parameterized-unit-testing)。
该方法必须位于标记为 [PexClass](#pexclass) 属性的类中。

IntelliTest 将生成传统的无参数测试，该测试使用不同的参数调用[参数化单元测试](test-generation.md#parameterized-unit-testing)。

参数化单元测试：

* 必须是实例方法
* 必须对测试类[可见](input-generation.md#visibility)测试类中生成的测试根据[设置瀑布图](settings-waterfall.md)进行放置
* 可采用任意数量的参数
* 可为泛型

**示例**

```
[PexClass]
public partial class MyTests {
     [PexMethod]
     public void MyTest(int i)
     { ... }
}
```

<a name="pexexplorationattributebase"></a>
## <a name="pexexplorationattributebase"></a>PexExplorationAttributeBase

[详细信息](https://msdn.microsoft.com/library/microsoft.pex.framework.pexexplorationattributebase.aspx)

<a name="pexassemblysettings"></a>
## <a name="pexassemblysettings"></a>PexAssemblySettings

此属性可在程序集级别下设置，覆盖所有浏览的默认设置值。

```
using Microsoft.Pex.Framework;
// overriding the test framework selection
[assembly: PexAssemblySettings(TestFramework = "Naked")]
```

<a name="pexassemblyundertest"></a>
## <a name="pexassemblyundertest"></a>PexAssemblyUnderTest

此属性指定正在由当前测试项目测试的程序集。 

```
[assembly: PexAssemblyUnderTest("MyAssembly")]
```

<a name="pexinstrumentassemblyattribute"></a>
## <a name="pexinstrumentassemblyattribute"></a>PexInstrumentAssemblyAttribute

此属性用于指定要进行检测的程序集。

**示例**

```
using Microsoft.Pex.Framework;

// the assembly containing ATypeFromTheAssemblyToInstrument should be instrumented
[assembly: PexInstrumentAssembly(typeof(ATypeFromTheAssemblyToInstrument))]

// the assembly name can be used as well
[assembly: PexInstrumentAssembly("MyAssemblyName")]
```

<a name="pexusetype"></a>
## <a name="pexusetype"></a>PexUseType

此属性告知 IntelliTest 它能够使用特定类型实例化（抽象化）基类型或接口。

**示例**

```
[PexMethod]
[PexUseType(typeof(A))]
[PexUseType(typeof(B))]
public void MyTest(object testParameter)
{
     ... // IntelliTest will consider types A and B to instantiate 'testParameter'
}
```

<a name="pexallowedexception"></a>
## <a name="pexallowedexception"></a>PexAllowedException

如果此属性附加到 [PexMethod](#pexmethod)（或 [PexClass](#pexclass)），该属性会更改测试失败时指定的默认 IntelliTest 逻辑。 即使测试引发指定的异常，也不会被视为失败。

**示例**

以下测试指定堆栈的构造函数可能会引发 ArgumentOutOfRangeException：

```
class Stack {
  int[] _elements;
  int _count;
  public Stack(int capacity) {
    if (capacity<0) throw new ArgumentOutOfRangeException();
    _elements = new int[capacity];
    _count = 0;
  }
  ...
}
```

筛选器会附加到装置，如下所示（也可以在程序集或测试级别对其进行定义）：

```
[PexMethod]
[PexAllowedException(typeof(ArgumentOutOfRangeException))]
class CtorTest(int capacity) {
  Stack s = new Stack(capacity); // may throw ArgumentOutOfRangeException
}
```

<a name="pexallowedexceptionfromassembly"></a>
## <a name="pexallowedexceptionfromassembly"></a>PexAllowedExceptionFromAssembly

[详细信息](https://msdn.microsoft.com/library/microsoft.pex.framework.validation.pexallowedexceptionfromassemblyattribute.aspx)

<a name="pexallowedexceptionfromtype"></a>
## <a name="pexallowedexceptionfromtype"></a>PexAllowedExceptionFromType

[详细信息](https://msdn.microsoft.com/library/microsoft.pex.framework.validation.pexallowedexceptionfromtypeattribute.aspx)

<a name="pexallowedexceptionfromtypeundertest"></a>
## <a name="pexallowedexceptionfromtypeundertest"></a>PexAllowedExceptionFromTypeUnderTest

[详细信息](https://msdn.microsoft.com/library/microsoft.pex.framework.validation.pexallowedexceptionfromtypeundertestattribute.aspx)

## <a name="got-feedback"></a>是否获得反馈？

在 [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest) 上发布想法和功能请求。
