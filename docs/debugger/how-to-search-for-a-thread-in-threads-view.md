---
title: 如何： 搜索线程视图中的线程 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- threads, searching
ms.assetid: 5609a9b3-c279-4426-9e2e-dd87896a6d6f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b5eee67e195821f89dbd820f930288eb24f20a11
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-search-for-a-thread-in-threads-view"></a>如何：在线程视图中搜索线程
可以通过将其线程 ID 或模块字符串用作搜索条件来搜索特定线程在线程视图中。 你还可以指定搜索的初始方向。 在对话框中的字段将显示所选线程的属性的线程树中。  
  
### <a name="to-search-for-a-thread-in-threads-view"></a>要搜索线程视图中的线程  
  
1.  排列窗口，因此该 Spy + + 和活动[线程视图](../debugger/threads-view.md)是可见的窗口。  
  
2.  从**搜索**菜单上，选择**查找线程**。  
  
     [线程搜索对话框](../debugger/thread-search-dialog-box.md)打开。  
  
3.  键入的线程 ID 或模块字符串作为搜索条件。  
  
4.  清除不希望为其指定值的任何字段。  
  
    > [!TIP]
    >  若要查找的模块拥有的所有线程，请清除**线程**文本框然后键入该模块中的名称**模块**框。 然后使用**查找下一个**表示不继续搜索线程。  
  
5.  选择**向上**或**下**搜索的初始方向。  
  
6.  单击 **“确定”**。  
  
 如果找到匹配的线程，则它将突出显示在线程视图窗口中。