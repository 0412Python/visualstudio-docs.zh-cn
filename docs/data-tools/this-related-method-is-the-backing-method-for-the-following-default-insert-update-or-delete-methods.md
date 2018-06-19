---
title: 此相关方法是以下默认插入、更新或删除方法的支持方法
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: fdb359ebe4a42e0ddad8b93c1e746922ac609f60
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31922478"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>此相关方法是以下默认插入、更新或删除方法的支持方法

此相关方法是下列默认插入、更新或删除方法的备份方法。 如果删除这些方法，则备份方法也将被删除。 是否要继续?

所选的 `DataContext` 方法当前用作 O/R 设计器上某实体类的插入、更新或删除方法之一。 如果删除所选方法，则使用此方法的实体类在更新过程中执行插入、更新或删除时将还原为默认的运行时行为。

## <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>删除所选方法，使实体类使用运行时更新

- 单击 **“是”**。

    所选方法将被删除，并且使用此方法重写更新行为的所有类将还原为使用默认 LINQ to SQL 运行时行为。

## <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>关闭消息框，不对所选方法进行更改

- 单击“否” 。

    消息框关闭，不进行任何更改。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)