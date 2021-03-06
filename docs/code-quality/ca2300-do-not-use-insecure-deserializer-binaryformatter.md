---
title: CA2300:不要使用不安全反序列化程序 BinaryFormatter
ms.date: 04/05/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2e3ad5c23d880c65a57fdd94739475537c1aebff
ms.sourcegitcommit: 0e22ead8234b2c4467bcd0dc047b4ac5fb39b977
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59367295"
---
# <a name="ca2300-do-not-use-insecure-deserializer-binaryformatter"></a>CA2300:不要使用不安全反序列化程序 BinaryFormatter

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerBinaryFormatter|
|CheckId|CA2300|
|类别|Microsoft.Security|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

一个<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>反序列化方法是调用或引用。

## <a name="rule-description"></a>规则说明

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

此规则查找<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>反序列化方法调用或引用。 如果你想要反序列化时，才<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>属性设置为限制类型中，禁用此规则，并启用规则[CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)并[CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)相反。

## <a name="how-to-fix-violations"></a>如何解决冲突

- 如果可能，而是使用安全的序列化程序和**不允许攻击者能够指定任意类型进行反序列化**。 一些更安全的序列化程序包括：
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -永远不会使用<xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>。 如果必须使用类型解析程序，您必须将反序列化的类型对预期的列表。
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - NewtonSoft Json.NET-使用 TypeNameHandling.None。 如果必须为 TypeNameHandling 使用另一个值，然后必须将反序列化的类型对预期的列表。
  - 协议缓冲区
- 使序列化的数据篡改。 在序列化之后, 密码学角度上登录序列化的数据。 在反序列化之前, 验证的加密签名。 您必须从正在泄露保护加密密钥和应设计为密钥轮换。
- 限制反序列化的类型。 实现一个自定义<xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>。 反序列化之前<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>，将<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>属性设置为您的自定义的一个实例<xref:System.Runtime.Serialization.SerializationBinder>。 在重写<xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>方法，如果类型为意外然后引发一个异常。
 - 如果你限制反序列化的类型，可能想要禁用此规则，并启用规则[CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)并[CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)。 启用规则[CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)并[CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)有助于确保<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder>属性始终设置反序列化之前。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

- 它可以安全地禁止显示此规则的警告，如果知道输入是受信任。 请考虑应用程序的信任边界和数据流可能随时间变化。
- 它可以安全地禁止显示此警告，如果您执行了上述的预防措施之一。

## <a name="pseudo-code-examples"></a>伪代码示例

### <a name="violation"></a>冲突

```csharp
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        BinaryFormatter formatter = new BinaryFormatter();
        return formatter.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Runtime.Serialization.Formatters.Binary

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim formatter As BinaryFormatter = New BinaryFormatter()
        Return formatter.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```

## <a name="related-rules"></a>相关的规则

[CA2301:如果没有第一个设置 BinaryFormatter.Binder 不调用 BinaryFormatter.Deserialize](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)

[CA2302:确保在调用 BinaryFormatter.Deserialize 之前设置 BinaryFormatter.Binder](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)