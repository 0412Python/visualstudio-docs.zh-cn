---
title: 注释
description: 本指南介绍如何使用 Visual Studio for Mac 的源代码编辑器中的注释
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 0FE5E929-1846-4F48-B5E3-70990FAF9504
ms.openlocfilehash: 4a7dfd0daaddad9f91d461689a0174469dd253c2
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="comments"></a>注释

调试或编写代码时，它可用来临时或长期注释代码块。 

注释掉整个代码块：

* 选择代码并从上下文菜单中选择“切换行注释”

或

* 在所选代码上使用 `cmd + /` 键绑定。

这些方法可用来注释和取消注释代码部分。 在 C# 文件中，可以添加其他级别的行注释，以允许注释和取消注释代码区域，同时仍然保留实际注释： 

 ![多级别注释](media/source-editor-image8.png)

注释还可用于为可能与之交互的未来开发者编写代码。 这些功能通常以多行注释的形式完成，可以在每种语言中通过以下方法添加：

**C#**

``` cs
/*
 This is a multi-line
 comment in C#
*/
```
**F#**

```fsharp
(*
 This is a multi-line
  comment in F#
*)
```
