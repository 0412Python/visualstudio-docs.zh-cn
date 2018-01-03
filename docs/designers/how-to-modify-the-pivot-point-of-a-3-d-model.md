---
title: "如何：修改三维模型的透视点 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c20b4ec8-29f5-4ca5-bc39-d4548ca6f573
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 603b3f57bb2b9a1e9c99a4ca3870c38bc569d620
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-modify-the-pivot-point-of-a-3-d-model"></a>如何：修改三维模型的透视点
本文档说明如何使用模型编辑器修改三维模型的透视点。 透视点是空间中的点，定义用于旋转和缩放的对象的数学中心。  
  
 本文档演示了此活动：  
  
-   修改对象的透视点  
  
## <a name="modifying-the-pivot-point-of-a-3-d-model"></a>修改三维模型的中心点  
 可以通过修改三维模型的中心点来重新定义三维模型的原点。  
  
 请确保显示“属性”窗口和“工具箱”。  
  
#### <a name="to-modify-the-pivot-point-of-a-3-d-model"></a>修改三维模型的中心点  
  
1.  从现有的三维模型开始，例如[如何：创建基本三维模型](../designers/how-to-create-a-basic-3-d-model.md)中所述的模型。  
  
2.  进入透视模式。 在“模型编辑器模式”工具栏上，选择“透视模式”按钮以激活透视模式。 “透视模式”按钮周围将显示一个框，用于指示模型编辑器现在处于透视模式中。 在透视模式中，转换等操作会影响对象的透视点，而不影响世界空间中对象的结构。  
  
3.  修改对象的透视点。 在“选择”模式中，选择对象，然后在“模型查看器”工具栏上选择“转换”工具。 一个表示透视点的框显示在设计图面上。 移动框以修改对象的透视点。  
  
     通过移动框，可以在所有三个维度中移动透视点。 若要沿一个轴转换透视点，请移动与该轴相对应的箭头。 框和箭头将更改为黄色以指示受转换影响的轴。  
  
     还可以使用“属性”窗口中的“透视转换”属性以指定透视点。  
  
    > [!TIP]
    >  可以通过旋转对象来查看新透视点的效果。 若要旋转它，请使用“旋转”工具或修改“旋转”属性。  
  
 下面是具有修改后的中心点的模型：  
  
 ![具有已修改透视点的房屋模型](../designers/media/digit-modified-model.png "Digit-Modified-Model")  
  
## <a name="see-also"></a>请参阅  
 [如何：创建基本三维模型](../designers/how-to-create-a-basic-3-d-model.md)   
 [模型编辑器](../designers/model-editor.md)