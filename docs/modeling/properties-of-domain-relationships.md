---
title: "属性的域关系 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, domain relationships
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: c2fe3f843a6247c93e3fa8f75ea66fe824561d83
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="properties-of-domain-relationships"></a>域关系的属性
下表中的属性是与域关系相关联。 有关域关系的信息，请参阅[了解模型、 类和关系](../modeling/understanding-models-classes-and-relationships.md)。 有关如何使用这些属性的详细信息，请参阅[自定义和扩展的域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)。  
  
|属性|描述|默认|  
|--------------|-----------------|-------------|  
|访问修饰符|访问的域关系级别 (`public`或`internal`)。|`public`|  
|自定义特性|用于将属性添加到生成的域关系的源代码类。|\<none>|  
|生成双派生|如果`True`，生成基类和 （以支持通过替代的自定义） 的分部类。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|`False`|  
|具有自定义的构造函数|如果`True`，指示在源代码中提供的自定义的构造函数。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|`False`|  
|继承修饰符|描述的域关系从生成的源代码类继承的类型 (`none`，`abstract`或`sealed`)。|\<none>|  
|允许存在重复项|如果`True`，相同的两个元素之间，则可能创建重复的域关系的链接。|`False`|  
|基本关系|如果派生的域关系，域关系的基本关系。|\<none>|  
|嵌入|如果`True`，域关系是嵌入的关系。 如果`False`，关系是引用关系。|\<both>|  
|name|域关系的名称。|当前的名称|  
|命名空间|隶属于域关系命名空间。|当前命名空间|  
|说明|与域关系相关联的非正式说明。|\<none>|  
|描述|说明用于记录的代码并在生成的设计器 UI 中使用。|\<none>|  
|显示名称|域关系的生成设计器中显示的名称。|\<none>|  
|帮助关键字|可选关键字用于编制索引的域关系的 F1 帮助。|\<none>|  
  
## <a name="see-also"></a>请参阅  
 [域特定语言工具词汇表](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)