---
title: 在编码的 UI 测试中使用 HTML5 控件 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 2000b214-ae92-4334-b549-aa0eb4f45fe1
caps.latest.revision: 19
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a6002c3636030b67e9dca5e76c7ef57fbd93b6e5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805071"
---
# <a name="using-html5-controls-in-coded-ui-tests"></a>在编码的 UI 测试中使用 HTML5 控件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

编码的 UI 测试包括对某些包含在 Internet Explorer 9 和 Internet Explorer 10 中的 HTML5 控件的支持。  
  
 **要求**  
  
-   Visual Studio Enterprise  
  
> [!WARNING]
>  在 Internet Explorer 10 之前的版本中，可以在比 Internet Explorer 进程更高的特权级别中运行编码的 UI 测试。 当在 Internet Explorer 10 中运行编码的 UI 测试时，编码的 UI 测试和 Internet Explorer 进程必须处于相同的特权级别。 这是因为 Internet Explorer 10 提供了更安全的 AppContainer 功能。  
  
> [!WARNING]
>  如果你在 Internet Explorer 10 中创建编码的 UI 测试，则使用 Internet Explorer 9 或 Internet Explorer 8 可能无法运行它。 这是因为 Internet Explorer 10 包含 HTML5 控件（如音频、视频、进度条和滑块）。 Internet Explorer 9 或 Internet Explorer 8 无法识别这些 HTML5 控件。 同样，使用 Internet Explorer 9 的编码的 UI 测试可能包含 Internet Explorer 8 无法识别的某些 HTML5 控件。  
  
## <a name="supported-html5-controls"></a>支持的 HTML5 控件  
 编码的 UI 测试包括对以下 HTML5 控件的录制、播放和验证支持：  
  
-   [音频控件](#UsingHTML5ControlsCodedUITestsAudio)  
  
-   [视频控件](#UsingHTML5ControlsCodedUITestsVideo)  
  
-   [滑块](#UsingHTML5ControlsCodedUITestsSlider)  
  
-   [进度栏](#UsingHTML5ControlsCodedUITestsProgressBar)  
  
###  <a name="UsingHTML5ControlsCodedUITestsAudio"></a>音频控件  
 **音频控件：** 正确录制和播放 HTML5 音频控件上的操作。  
  
 ![HTML5 音频控件](../test/media/codedui-html5-audio.png "CodedUI_HTML5_Audio")  
  
|操作|录制|生成的代码|  
|------------|---------------|--------------------|  
|**播放音频**<br /><br /> 直接通过控件，或通过控件上下文菜单。|从 00:00:00 开始播放 \<名称> 音频|HtmlAudio.Play(TimeSpan)|  
|**搜寻音频中的特定时间**|搜寻 \<名称> 音频的 00:01:48|HtmlAudio.Seek(TimeSpan)|  
|**暂停音频**<br /><br /> 直接通过控件，或通过控件上下文菜单。|在 00:01:53 暂停 \<名称> 音频|HtmlAudio.Pause(TimeSpan)|  
|**音频静音**<br /><br /> 直接通过控件，或通过控件上下文菜单。|使 \<名称> 音频静音|HtmlAudio.Mute()|  
|**取消静音音频**<br /><br /> 直接通过控件，或通过控件上下文菜单。|使 \<名称> 音频取消静音|HtmlAudio.Unmute()|  
|**更改音频音量**|将 \<名称> 音频的音量设为 79%|HtmlAudio.SetVolume(float)|  
  
 以下属性可用于 HtmlAudio，并且你可以对所有这些属性添加断言：  
  
```  
string AutoPlay  
string Controls  
string CurrentSrc  
string CurrentTime  
string CurrentTimeAsString  
string Duration  
string DurationAsString  
string Ended  
string Loop  
string Muted  
string Paused  
string PlaybackRate  
string ReadyState  
string Seeking  
string Src  
string Volume  
  
```  
  
 **搜索属性：**`HtmlAudio` 的搜索属性为 `Id`、`Name` 和 `Title`。  
  
 **筛选器属性：**`HtmlAudio` 的筛选器属性为 `Src`、`Class`、`ControlDefinition` 和 `TagInstance`。  
  
> [!NOTE]
>  定位和暂停的时间可以很长。 在播放期间，编码的 UI 测试将一直等到 `(TimeSpan)` 中指定的时间再暂停音频。 如果由于某种特殊情况，过了指定的时间才命中暂停命令，将引发异常。  
  
###  <a name="UsingHTML5ControlsCodedUITestsVideo"></a>视频控件  
 **视频控件：** 正确录制和播放 HTML5 视频控件上的操作。  
  
 ![HTML5 视频控件](../test/media/codedui-html5-video.png "CodedUI_HTML5_Video")  
  
|操作|录制|生成的代码|  
|------------|---------------|--------------------|  
|**播放视频**<br /><br /> 直接通过控件，或通过控件上下文菜单。|从 00:00:00 开始播放 \<名称> 视频|HtmlVideo.Play(TimeSpan)|  
|**搜寻视频中的特定时间**|搜寻 \<名称> 视频的 00:01:48|HtmlVideo.Seek(TimeSpan)|  
|**暂停视频**<br /><br /> 直接通过控件，或通过控件上下文菜单。|在 00:01:53 暂停 \<名称> 视频|HtmlVideo.Pause(TimeSpan)|  
|**视频静音**<br /><br /> 直接通过控件，或通过控件上下文菜单。|使 \<名称> 视频静音|HtmlVideo.Mute()|  
|**取消静音视频**<br /><br /> 直接通过控件，或通过控件上下文菜单。|使 \<名称> 视频取消静音|HtmlVideo.Unmute()|  
|**更改视频音量**|将 \<名称> 视频的音量设为 79%||  
  
 HtmlAudio 的所有属性都可用于 HtmlVideo。 此外，以下三个属性也可用。 可以对所有这些属性添加断言。  
  
```  
string Poster  
string VideoHeight  
string VideoWidth  
  
```  
  
 **搜索属性：**`HtmlVideo` 的搜索属性为 `Id`、`Name` 和 `Title`。  
  
 **筛选器属性：**`HtmlVideo` 的筛选器属性为 `Src`、`Poster`、`Class`、`ControlDefinition` 和 `TagInstance`。  
  
> [!NOTE]
>  如果使用 -30s 或 +30s 标签对视频后退或快进，将聚合标签以定位到相应的时间。  
  
###  <a name="UsingHTML5ControlsCodedUITestsSlider"></a>滑块  
 **滑块控件：** 正确录制和播放 HTML5 滑块控件上的操作。  
  
 ![HTML5 滑块控件](../test/media/codedui-html5-slider.png "CodedUI_HTML5_Slider")  
  
|操作|录制|生成的代码|  
|------------|---------------|--------------------|  
|**设置滑块位置**|将 \<名称> 滑块的位置设为 \<x>|HtmlSlider.ValueAsNumber=\<x>|  
  
 以下属性可用于 HtmlSlider，并且你可以对所有这些属性添加断言：  
  
```  
string Disabled  
string Max  
string Min  
string Required  
string Step  
string ValueAsNumber  
```  
  
###  <a name="UsingHTML5ControlsCodedUITestsProgressbar"></a>进度栏  
 **进度栏控件：** 进度栏是一种不可交互的控件。 你可以对此控件的 `Value` 和 `Max` 属性添加断言。  
  
 ![HTML5 进度栏控件](../test/media/codedui-html5-progressbar.png "CodedUI_HTML5_ProgressBar")  
  
## <a name="see-also"></a>请参阅  
 [HTML 元素](http://go.microsoft.com/fwlink/?LinkID=232441)   
 [使用 UI 自动化来测试代码](../test/use-ui-automation-to-test-your-code.md)   
 [创建编码的 UI 测试](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)   
 [自定义编码的 UI 测试](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeCUITModify)   
 [支持编码的 UI 测试和操作录制的配置和平台](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
