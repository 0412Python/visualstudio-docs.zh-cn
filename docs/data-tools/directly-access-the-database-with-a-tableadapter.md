---
title: 直接访问使用 TableAdapter 数据库
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Visual Basic], accessing with a TableAdapter
- DBDirect methods
- datasets [Visual Basic], adding to projects
- data [Visual Studio], saving
- TableAdapter.Delete method
- GenerateDbDirectMethods property
- TableAdapter.Insert method
- TableAdapter.GenerateDBDirectMethods property
- TableAdapter.Update method
- saving data
- TableAdapters
ms.assetid: 012c5924-91f7-4790-b2a6-f51402b7014b
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b1a3b35cc491ed91e07316444c31cf4a29ef1517
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="directly-access-the-database-with-a-tableadapter"></a>直接访问使用 TableAdapter 数据库
除了`InsertCommand`， `UpdateCommand`，和`DeleteCommand`，Tableadapter 创建的可以直接对数据库运行的方法。 这些方法 (`TableAdapter.Insert`， `TableAdapter.Update`，和`TableAdapter.Delete`) 可以调用以进行操作直接在数据库中的数据。

 如果你不想要创建这些直接的方法，设置 TableAdapter 的`GenerateDbDirectMethods`属性`false`中**属性**窗口。 如果任何查询添加到 TableAdapter 的主查询除了 TableAdapter，它们就不生成这些 DbDirect 方法的独立查询。

## <a name="send-commands-directly-to-a-database"></a>命令将直接发送到数据库
 调用的 TableAdapter DbDirect 方法的执行您要完成的任务。

#### <a name="to-insert-new-records-directly-into-a-database"></a>若要直接向数据库中插入新记录

-   调用 TableAdapter 的`Insert`方法，在值中为每一列将作为参数传递。 下面的过程使用`Region`作为示例 Northwind 数据库中的表。

    > [!NOTE]
    >  如果你没有可用的实例，实例化你想要使用的 TableAdapter。

     [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_1.vb)]
     [!code-csharp[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_1.cs)]

#### <a name="to-update-records-directly-in-a-database"></a>若要直接在数据库中更新记录

-   调用 TableAdapter 的`Update`方法，在新的和原始值中为每一列将作为参数传递。

    > [!NOTE]
    >  如果你没有可用的实例，实例化你想要使用的 TableAdapter。

     [!code-vb[VbRaddataSaving#18](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_2.vb)]
     [!code-csharp[VbRaddataSaving#18](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_2.cs)]

#### <a name="to-delete-records-directly-from-a-database"></a>若要直接从数据库中删除记录

-   调用 TableAdapter 的`Delete`方法，在值中为每一列将作为参数传递的`Delete`方法。 下面的过程使用`Region`作为示例 Northwind 数据库中的表。

    > [!NOTE]
    >  如果你没有可用的实例，实例化你想要使用的 TableAdapter。

     [!code-vb[VbRaddataSaving#21](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_3.vb)]
     [!code-csharp[VbRaddataSaving#21](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_3.cs)]

## <a name="see-also"></a>请参阅

- [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)