---
title: 如何：创建 LINQ to SQL 类映射到表和视图 （O-R 设计器） |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 0fb78bbc-7a78-4ab4-b32f-85ece912e660
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c2be46e61438c555fc7ee7d523b3ff9b758c0a15
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58934990"
---
# <a name="how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-or-designer"></a>如何：创建映射到表和视图的 LINQ to SQL 类（O/R 设计器）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
LINQ to SQL 类映射到数据库表和视图称为*实体类*。 实体类映射到记录，而一个实体类的各个属性则映射到构成一条记录的各个列。 创建通过拖动表或视图从基于数据库表或视图的实体类**服务器资源管理器**/**数据库资源管理器**拖到[LINQ to SQL 中的工具Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)。 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]生成的类并应用特定 [！要启用 LINQ to SQL 属性 [！LINQ to SQL 功能 (数据通信和编辑功能<xref:System.Data.Linq.DataContext>)。 有关详细信息 [！LINQ to SQL 类，请参阅[LINQ to SQL 对象模型](http://msdn.microsoft.com/library/81dd0c37-e2a4-4694-83b0-f2e49e693810)。

> [!NOTE]
> [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]是一个简单的对象关系映射器，因为它仅支持 1:1 映射关系。 换句话说，实体类与数据库表或视图之间只能具有 1:1 映射关系。 不支持复杂映射（例如，将一个实体类映射到多个表）。 但是，可以将一个实体类映射到一个联接多个相关表的视图。

## <a name="create-linq-to-sql-classes-that-are-mapped-to-database-tables-or-views"></a>创建映射到数据库表或视图的 LINQ to SQL 类
 通过将表或视图从**服务器资源管理器**/**数据库资源管理器**拖到[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]创建实体类除了<xref:System.Data.Linq.DataContext>用于方法执行更新。

 默认情况下，[！LINQ to SQL 运行时创建逻辑，以将更改从可更新的实体类保存回数据库。 此逻辑基于表的架构（列定义和主键信息）。 如果不希望此行为，可以配置一个实体类以使用存储的过程来执行插入、 更新和删除而不是使用默认值 [！LINQ to SQL 运行时行为。 有关详细信息，请参阅[如何：分配存储过程以便执行更新、插入和删除操作（O/R 设计器）](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)。

 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]

#### <a name="to-create-linq-to-sql-classes-that-are-mapped-to-database-tables-or-views"></a>创建映射到数据库表或视图的 LINQ to SQL 类

1.  在中**服务器**/**数据库资源管理器**，展开**表**或**视图**和找到的数据库表或视图所需若要在你的应用程序中使用。

2.  将该表或视图拖动到 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]上。

     一个实体类将创建并显示在设计图面上。 该实体类的属性映射到所选表或视图中的列。

## <a name="create-an-object-data-source-and-display-the-data-on-a-form"></a>创建对象数据源并在窗体中显示数据
 使用创建实体类后[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]，可以创建对象数据源并填充[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)与实体类。

#### <a name="to-create-an-object-data-source-based-on-linq-to-sql-entity-classes"></a>创建基于 LINQ to SQL 实体类的对象数据源

1.  在“生成”菜单中，单击“生成解决方案”以生成项目。

2.  在 **“数据”** 菜单上，单击 **“显示数据源”**。

3.  在 **“数据源”** 窗口中，单击 **“添加新数据源”**。

4.  单击“选择数据源类型”页上的“对象”，然后单击“下一步”。

5.  展开节点，然后找到并选择您的类。

    > [!NOTE]
    > 如果“Customer”类不可用，则退出向导，生成项目，然后重新运行向导。

6.  单击“完成”以创建数据源，并将“Customer”实体类添加到“数据源”窗口。

7.  将项从“数据源”窗口拖动到窗体。

## <a name="see-also"></a>请参阅

- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [演练：创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)
- [DataContext 方法（O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)
- [如何：创建映射到存储过程和函数的 DataContext 方法（O/R 设计器）](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)
- [LINQ to SQL 对象模型](http://msdn.microsoft.com/library/81dd0c37-e2a4-4694-83b0-f2e49e693810)
- [演练：自定义实体类的插入、更新和删除行为](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)
- [演练：向实体类添加验证](http://msdn.microsoft.com/library/85b06a02-b2e3-4534-95b8-d077c8d4c1d7)
- [如何：创建 LINQ to SQL 类之间的关联（关系）（O/R 设计器）](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)