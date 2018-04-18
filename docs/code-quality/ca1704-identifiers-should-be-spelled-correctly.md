---
title: CA1704： 标识符应正确拼写 |Microsoft 文档
ms.date: 03/28/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 91f6601bac8e3f42ce4d2b8b8948d78b08c190f4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704：标识符应正确拼写

|||
|-|-|
|TypeName|IdentifiersShouldBeSpelledCorrectly|
|CheckId|CA1704|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因

标识符名称包含一个或多个未被 Microsoft 拼写检查器库识别的单词。 此规则不检查构造函数或特殊名称的成员，如 get 和 set 属性访问器。

## <a name="rule-description"></a>规则说明

此规则将该标识符解析为令牌，并检查每个令牌的拼写正确。 分析算法会执行以下转换：

- 以大写字母开头的新令牌。 例如，MyNameIsJoe 标记化"我的"、"Name"、"Is"、"Joe"。

- 对于多个大写字母，最后一个大写字母开始一个新的标记。 例如，GUIEditor 标记化到"完全安装"，"编辑器"。

- 删除前导空格和尾随撇号。 例如，发件人将向"发件人"。

- 下划线表示令牌的末尾，并删除。 例如，Hello_world 归为"Hello"，"world"。

- 将删除嵌入的与号。 例如，for&mat 标记化为“format”。

## <a name="language"></a>语言

只对基于英语区域性字典当前检查拼写检查器。 你可以通过添加更改你的项目的项目文件中的区域性**CodeAnalysisCulture**元素。

例如：

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> 如果你将区域性设置为基于英语区域性之外的任何内容时，会以无提示方式禁用此代码分析规则。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复与此规则的冲突，更正该单词的拼写或添加到自定义词典的单词。

### <a name="to-add-words-to-a-custom-dictionary"></a>将字添加到自定义字典

命名自定义字典 XML 文件*CustomDictionary.xml*。 将字典的安装目录中的工具，项目目录，或与下的用户配置文件的工具相关联的目录中放置 (*%USERPROFILE%\Application 数据\\...*).若要了解如何将自定义字典添加到 Visual Studio 中的项目，请参阅[如何： 自定义代码分析字典](../code-quality/how-to-customize-the-code-analysis-dictionary.md)。

- 添加的单词时应不会导致违反了字典/单词/识别路径下。

- 添加应导致违反了无法识别的单词/字典/路径下的单词。

- 添加的单词时应将标记为过时已弃用字典/单词路径下。 请参阅相关的规则主题[CA1726： 使用首选的词条](../code-quality/ca1726-use-preferred-terms.md)有关详细信息。

- 将异常添加到字典/首字母缩写词/CasingExceptions 路径的首字母缩写词大小写规则。

下面是结构的自定义字典文件的示例：

```xml
<Dictionary>
   <Words>
      <Unrecognized>
         <Word>cb</Word>
      </Unrecognized>
      <Recognized>
         <Word>stylesheet</Word>
         <Word>GotDotNet</Word>
      </Recognized>
      <Deprecated>
         <Term PreferredAlternate="EnterpriseServices">ComPlus</Term>
      </Deprecated>
   </Words>
   <Acronyms>
      <CasingExceptions>
         <Acronym>CJK</Acronym>
         <Acronym>Pi</Acronym>
      </CasingExceptions>
   </Acronyms>
</Dictionary>
```

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

仅当是故意拼写错误的单词和单词适用于一组有限的库，禁止显示此规则的警告。 正确的拼写的单词可以减少所需的新软件库学习曲线。

## <a name="related-rules"></a>相关的规则

- [CA2204：应正确拼写文本](../code-quality/ca2204-literals-should-be-spelled-correctly.md)
- [CA1703：资源字符串应正确拼写](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1709：标识符的大小写应当正确](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708：标识符不应仅以大小写进行区分](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA1707：标识符不应包含下划线](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1726：使用首选词条](../code-quality/ca1726-use-preferred-terms.md)

## <a name="see-also"></a>请参阅

- [如何：自定义代码分析字典](../code-quality/how-to-customize-the-code-analysis-dictionary.md)
