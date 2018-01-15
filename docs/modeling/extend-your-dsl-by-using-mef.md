---
title: "通过使用 MEF 扩展 DSL |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4a746d3b2c913025bb9fc84b4f3fec34fe2bc7cf
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="extend-your-dsl-by-using-mef"></a>使用 MEF 扩展 DSL
可以通过使用 Managed Extensibility Framework (MEF) 扩展你的域特定语言 (DSL)。 你或其他开发人员将能够为 DSL 编写扩展，而无需更改的 DSL 定义和程序代码。 此类扩展包括菜单命令、 拖放处理程序和验证。 用户将能够安装 DSL，，然后根据需要为其安装扩展。  
  
 此外，当你启用 MEF DSL 中时，它可以更方便地你编写的一些功能 DSL，即使它们的所有生成的 DSL 以及。  
  
 有关 MEF 的详细信息，请参阅[Managed Extensibility Framework (MEF)](/dotnet/framework/mef/index)。  
  
### <a name="to-enable-your-dsl-to-be-extended-by-mef"></a>若要启用 DSL 由 MEF 扩展  
  
1.  创建一个名为的新文件夹**MefExtension**内**DslPackage**项目。 将以下文件添加到它：  
  
     文件名：`CommandExtensionVSCT.tt`  
  
    > [!IMPORTANT]
    >  在此文件会作为 DslPackage\GeneratedCode\Constants.tt 中定义 GUID CommandSetId 相同中设置 GUID  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#  
    // CmdSet Guid must be defined before master template is included  
    // This Guid must be kept synchronized with the CommandSetId Guid in Constants.tt  
    Guid guidCmdSet = new Guid ("00000000-0000-0000-0000-000000000000");  
    string menuidCommandsExtensionBaseId="0x4000";  
    #>  
    <#@ include file="DslPackage\CommandExtensionVSCT.tt" #>  
    ```  
  
     文件名：`CommandExtensionRegistrar.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="DslPackage\CommandExtensionRegistrar.tt" #>  
    ```  
  
     文件名：`ValidationExtensionEnablement.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="DslPackage\ValidationExtensionEnablement.tt" #>  
    ```  
  
     文件名：`ValidationExtensionRegistrar.tt`  
  
     如果你添加此文件，你必须验证在中启用 DSL 使用至少一个中的交换机**EditorValidation** DSL 资源管理器中。  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="DslPackage\ValidationExtensionRegistrar.tt" #>  
    ```  
  
     文件名：`PackageExtensionEnablement.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="DslPackage\PackageExtensionEnablement.tt" #>  
    ```  
  
2.  创建一个名为的新文件夹**MefExtension**内**Dsl**项目。 将以下文件添加到它：  
  
     文件名：`DesignerExtensionMetaDataAttribute.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="Dsl\DesignerExtensionMetadataAttribute.tt" #>  
    ```  
  
     文件名：`GestureExtensionEnablement.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="Dsl\GestureExtensionEnablement.tt" #>  
    ```  
  
     文件名：`GestureExtensionController.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="Dsl\GestureExtensionController.tt" #>  
    ```  
  
3.  将以下行添加到名为的现有文件**DslPackage\Commands.vsct**:  
  
    ```  
    <Include href="MefExtension\CommandExtensionVSCT.vsct"/>  
    ```  
  
     在现有之后插入行`<Include>`指令。  
  
4.  `Open DslDefinition.dsl.`  
  
5.  DSL 资源管理器，在选择**Editor\Validation**。  
  
6.  在属性窗口中，请确保至少一个属性名为**使用...**是`true`。  
  
7.  在解决方案资源管理器工具栏中，单击**转换所有模板**。  
  
     附属文件将显示下每个你添加的文件。  
  
8.  生成并运行解决方案来验证仍能工作。  
  
 DSL 现 MEF 启用。 您可以编写作为 MEF 扩展的菜单命令、 笔势处理程序和验证约束。 DSL 解决方案以及其他自定义代码中，你可以编写这些扩展。 此外，你或其他开发人员可以编写单独[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]扩展 DSL 的扩展。  
  
## <a name="creating-an-extension-for-a-mef-enabled-dsl"></a>为 MEF 启用 DSL 创建扩展  
 如果你有权创建您自己或他人的 MEF 启用 DSL，您可以为其编写扩展。 扩展可以用于添加菜单命令、 笔势处理程序或验证约束。 若要创作这些扩展，你可以使用[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]扩展 (VSIX) 解决方案。 解决方案由两部分组成： 一个类库项目的生成代码程序集，并打包程序集的 VSIX 项目。  
  
#### <a name="to-create-a-dsl-extension-vsix"></a>若要创建 DSL 扩展 VSIX  
  
1.  创建一个新类库项目。 为此，请在**新项目**对话框中，选择**Visual Basic**或**Visual C#** ，然后选择**类库**。  
  
2.  在新类库项目中，添加对 DSL 的程序集的引用。  
  
    -   此程序集通常具有结尾的名称"。Dsl.dll"。  
  
    -   如果你有权 DSL 项目，你可以找到程序集文件的目录下**Dsl\bin\\\***  
  
    -   如果你有权访问 DSL VSIX 文件，你可以通过将 VSIX 文件的文件扩展名更改为".zip"来查找程序集。 解压缩.zip 文件。  
  
3.  添加对以下.NET 程序集引用：  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.11.0.dll  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0.dll  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.Shell.11.0.dll  
  
    -   System.ComponentModel.Composition.dll  
  
    -   System.Windows.Forms.dll  
  
4.  同一解决方案中创建一个 VSIX 项目。 为此，请在**新项目**对话框框中，展开**Visual Basic**或**Visual C#**，单击**扩展性**，然后选择**VSIX 项目**。  
  
5.  在解决方案资源管理器，右键单击该 VSIX 项目，然后单击**设为启动项目**。  
  
6.  在新的项目中，打开**source.extension.vsixmanifest**。  
  
7.  单击**添加内容**。 在对话框中，设置**内容类型**到**MEF 组件**，和**源项目**到你的类库项目。  
  
8.  添加对 DSL 的 VSIX 引用。  
  
    1.  在**source.extension.vsixmanifest**，单击**添加引用**  
  
    2.  在对话框中，单击**添加负载**然后找到 DSL 的 VSIX 文件。 VSIX 文件的生成 DSL 解决方案中、 在**DslPackage\bin\\\***。  
  
         这允许用户在同一时间安装 DSL 和你的扩展。 如果用户已经安装了 DSL，将安装你的扩展。  
  
9. 查看和更新的其他字段**source.extension.vsixmanifest**。 单击**选择版本**并确认正确[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]设置版本。  
  
10. 将代码添加到类库项目。 作为参考下, 一节中使用的示例。  
  
     你可以添加任意数量的命令、 笔势和验证类。  
  
11. 若要测试此扩展，请按**F5**。 在实验实例中的[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，创建或打开 DSL 的示例文件。  
  
## <a name="writing-mef-extensions-for-dsls"></a>为 Dsl 编写 MEF 扩展  
 你可以在一个单独的 DSL 扩展解决方案程序集代码项目中编写扩展。 你还可以在 DslPackage 项目中，使用 MEF，方便地将作为 DSL 的一部分的命令、 笔势和验证代码。  
  
### <a name="menu-commands"></a>菜单命令  
 若要编写菜单命令，定义一个类以实现<xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement.ICommandExtension>，并添加前缀具有 DSL，名为中定义的属性类*YourDsl*`CommandExtension`。 你可以编写多个菜单命令类。  
  
 `QueryStatus()`每当用户右击关系图都会调用。 它应检查当前选定内容和设置`command.Enabled`指出该命令适用。  
  
```  
using System.ComponentModel.Composition;  
using System.Linq;  
using Company.MyDsl; // My DSL  
using Company.MyDsl.ExtensionEnablement; // My DSL  
using Microsoft.VisualStudio.Modeling; // Transactions  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement; // IVsSelectionContext  
using Microsoft.VisualStudio.Modeling.ExtensionEnablement; // ICommandExtension  
  
namespace MyMefExtension  
{  
  // Defined in Dsl\MefExtension\DesignerExtensionMetaDataAttribute.cs:  
  [MyDslCommandExtension]   
  public class MyCommandClass : ICommandExtension  
  {   
    /// <summary>  
    /// Provides access to current document and selection.  
    /// </summary>  
    [Import]  
    IVsSelectionContext SelectionContext { get; set; }  
  
    /// <summary>  
    /// Called when the user selects this command.  
    /// </summary>  
    /// <param name="command"></param>  
    public void Execute(IMenuCommand command)  
    {  
      // Transaction is required if you want to update elements.  
      using (Transaction t = SelectionContext.CurrentStore  
              .TransactionManager.BeginTransaction("fix names"))  
      {  
        foreach (ExampleShape shape in SelectionContext.CurrentSelection)  
        {  
          ExampleElement element = shape.ModelElement as ExampleElement;  
          element.Name = element.Name + " !";  
        }  
        t.Commit();  
      }  
    }  
  
    /// <summary>  
    /// Called when the user right-clicks the diagram.  
    /// Determines whether the command should appear.  
    /// This method should set command.Enabled and command.Visible.  
    /// </summary>  
    /// <param name="command"></param>  
    public void QueryStatus(IMenuCommand command)  
    {  
      command.Enabled =  
        command.Visible = (SelectionContext.CurrentSelection.OfType<ExampleShape>().Count() > 0);  
    }  
  
    /// <summary>  
    /// Called when the user right-clicks the diagram.  
    /// Determines the text of the command in the menu.  
    /// </summary>  
    public string Text  
    {  
      get { return "My menu command"; }  
    }  
  }  
}  
  
```  
  
### <a name="gesture-handlers"></a>笔势处理程序  
 笔势处理程序可以处理拖放到关系图从任意位置，内部或外部的对象[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。 下面的示例使用户可以将文件从 Windows 资源管理器拖动到关系图。 它将创建包含的文件名称的元素。  
  
 你可以编写处理程序来处理来自其他 DSL 模型和 UML 模型的拖动。 有关详细信息，请参阅[如何： 添加的拖放处理](../modeling/how-to-add-a-drag-and-drop-handler.md)。  
  
```  
  
using System.ComponentModel.Composition;  
using System.Linq;  
using Company.MyDsl;  
using Company.MyDsl.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling; // Transactions  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;   
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;   
  
namespace MefExtension  
{  
  [MyDslGestureExtension]  
  class MyGestureExtension : IGestureExtension  
  {  
    public void OnDoubleClick(ShapeElement targetElement, DiagramPointEventArgs diagramPointEventArgs)  
    {  
      System.Windows.Forms.MessageBox.Show("double click!");  
    }  
  
    /// <summary>  
    /// Called when the user drags anything over the diagram.  
    /// Return true if the dragged object can be dropped on the current target.  
    /// </summary>  
    /// <param name="targetMergeElement">The shape or diagram that the mouse is currently over</param>  
    /// <param name="diagramDragEventArgs">Data about the dragged element.</param>  
    /// <returns></returns>  
    public bool CanDragDrop(ShapeElement targetMergeElement, DiagramDragEventArgs diagramDragEventArgs)  
    {  
      // This handler only allows items to be dropped onto the diagram:  
      return targetMergeElement is MefDsl2Diagram &&  
      // And only accepts files dragged from Windows Explorer:  
        diagramDragEventArgs.Data.GetFormats().Contains("FileNameW");  
    }  
  
    /// <summary>  
    /// Called when the user drops an item onto the diagram.  
    /// </summary>  
    /// <param name="targetDropElement"></param>  
    /// <param name="diagramDragEventArgs"></param>  
    public void OnDragDrop(ShapeElement targetDropElement, DiagramDragEventArgs diagramDragEventArgs)  
    {  
      MefDsl2Diagram diagram = targetDropElement as MefDsl2Diagram;  
      if (diagram == null) return;  
  
      // This handler only accepts files dragged from Windows Explorer:  
      string[] draggedFileNames = diagramDragEventArgs.Data.GetData("FileNameW") as string[];  
      if (draggedFileNames == null || draggedFileNames.Length == 0) return;   
  
      using (Transaction t = diagram.Store.TransactionManager.BeginTransaction("file names"))  
      {  
        // Create an element to represent each file:  
        foreach (string fileName in draggedFileNames)  
        {  
          ExampleElement element = new ExampleElement(diagram.ModelElement.Partition);  
          element.Name = fileName;  
  
          // This method of adding the new element allows the position  
          // of the shape to be specified:            
          ElementGroup group = new ElementGroup(element);  
          diagram.ElementOperations.MergeElementGroupPrototype(  
            diagram, group.CreatePrototype(), PointD.ToPointF(diagramDragEventArgs.MousePosition));  
        }  
        t.Commit();  
      }  
    }  
  }  
}  
  
```  
  
### <a name="validation-constraints"></a>验证约束  
 验证方法标记`ValidationExtension`属性是由而生成的 DSL，还通过<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationMethodAttribute>。 该方法可以出现在任何不通过特性标记的类。  
  
 有关详细信息，请参阅[域特定语言中的验证](../modeling/validation-in-a-domain-specific-language.md)。  
  
```  
using Company.MyDsl;  
using Company.MyDsl.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.Validation;  
  
namespace MefExtension  
{  
  class MyValidationExtension // Can be any class.  
  {  
    // SAMPLE VALIDATION METHOD.  
    // All validation methods have the following attributes.  
  
    // Specific to the extended DSL:  
    [MyDslValidationExtension]   
  
    // Determines when validation is applied:  
    [ValidationMethod(  
       ValidationCategories.Save  
     | ValidationCategories.Open  
     | ValidationCategories.Menu)]  
  
    /// <summary>  
    /// When validation is executed, this method is invoked  
    /// for every element in the model that is an instance  
    /// of the second parameter type.  
    /// </summary>  
    /// <param name="context">For reporting errors</param>  
    /// <param name="elementToValidate"></param>  
    private void ValidateClassNames  
      (ValidationContext context,  
       // Type determines to what elements this will be applied:  
       ExampleElement elementToValidate)  
    {   
      // Write code here to test values and links.  
      if (elementToValidate.Name.IndexOf(' ') >= 0)  
      {  
        // Log any unacceptable values:  
        context.LogError(  
          // Description:  
          "Name must not contain spaces"   
          // Error code unique to this type of error:  
          , "MyDsl001"   
          // Element to highlight when user double-clicks error:  
          , elementToValidate);   
} } } }  
  
```  
  
## <a name="see-also"></a>请参阅  
 [传送 Visual Studio 扩展](../extensibility/shipping-visual-studio-extensions.md)   
 [Managed 的 Extensibility Framework (MEF)](/dotnet/framework/mef/index)   
 [如何： 添加一个拖放处理程序](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [域特定语言中的验证](../modeling/validation-in-a-domain-specific-language.md)