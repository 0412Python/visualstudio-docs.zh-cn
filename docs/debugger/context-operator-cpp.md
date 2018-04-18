---
title: 上下文运算符在调试器 （c + +） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.operators
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- expressions [C++], native debugger
- evaluation
- format specifiers, expressions
- context operator, in expressions
- debugging [C++], expressions
- native expression evaluator
ms.assetid: 73cc9afe-f4a4-474e-bb89-5a33fb5e570c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 918561fb4efcce71874c571863a10a40b15bbaa1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="context-operator-in-the-visual-studio-debugger-c"></a>上下文运算符在 Visual Studio 调试器 （c + +）
可使用 C++ 中的上下文运算符来限定断点位置、变量名称或表达式。 上下文运算符可用于指定来自外部范围的但被本地名称隐藏的名称。  
  
##  <a name="BKMK_Using_context_operators_to_specify_a_symbol"></a> 语法  
 有两种方法指定上下文：  
  
1.  {,,[*模块*] } *表达式*  
  
     大括号必须包含两个逗号和模块（可执行文件或 DLL）名称或完整路径。  
  
     例如，在 EXAMPLE.dll 的 `SomeFunction` 函数处设置断点：  
  
    ```C++  
    {,,EXAMPLE.dll}SomeFunction  
    ```  
  
2.  *模块*!*表达式*  
  
    ```C++  
    EXAMPLE.dll!SomeFunction  
    ```  
  
-   *模块* 是模块的名称。 您可以使用完整路径来消除同名模块之间的歧义。  
  
     如果 *模块* 路径包括逗号、嵌入空格或大括号，则必须在路径两边使用引号，以便上下文分析器能够正确识别该字符串。 单引号被视为 Windows 文件名的一部分，因此必须使用双引号。 例如，应用于对象的  
  
    ```C++  
    {,,"a long, long, library name.dll"} g_Var  
    ```  
  
-   *表达式* 是解析为有效目标（如 *模块*中的函数名、变量名或指针地址）的任何有效的 C++ 表达式。  
  
 当表达式计算器遇到表达式中的符号时，它按下列顺序搜索该符号：  
  
1.  词法范围向外，从当前块开始（括在大括号中的一系列语句），然后从该封闭块继续向外。 当前块是包含当前位置（指令指针地址）的代码。  
  
2.  函数范围。 当前函数。  
  
3.  类范围（如果当前位置在 C++ 成员函数内）。 类范围包含所有基类。 表达式计算器使用常规域控制规则。  
  
4.  当前模块中的全局符号。  
  
5.  当前程序中的公共符号。