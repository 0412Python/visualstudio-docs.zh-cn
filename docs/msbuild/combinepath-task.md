---
title: CombinePath 任务 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CombinePath task
- CombinePath task [MSBuild]
ms.assetid: c20edbf4-3d4f-4f66-b1d5-753a0d858ed8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6b73ddd4715d3abd29f87d7ef38a269d821733ba
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56610276"
---
# <a name="combinepath-task"></a>CombinePath 任务
将指定路径合并到单个路径。

## <a name="task-parameters"></a>任务参数
 下表描述了 [CombinePath 任务](../msbuild/combinepath-task.md)的参数。

|参数|说明|
|---------------|-----------------|
|`BasePath`|必选 `String` 参数。<br /><br /> 与其他路径组合的基路径。 可以是相对路径、绝对路径或空白。|
|`Paths`|必选 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 要与 BasePath 组合成组合路径的各个路径的列表。 路径可以是相对路径，也可以是绝对路径。|
|`CombinedPaths`|可选的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 输出参数。<br /><br /> 由此任务创建的组合路径。|

## <a name="remarks"></a>备注
 除上面列出的参数外，此任务还从 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数，后者自身继承自 <xref:Microsoft.Build.Utilities.Task> 类。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension 基类](../msbuild/taskextension-base-class.md)。

## <a name="see-also"></a>请参阅
- [任务](../msbuild/msbuild-tasks.md)
- [任务参考](../msbuild/msbuild-task-reference.md)