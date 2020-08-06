---
title: Creazione di un componente dell'elemento del report personalizzato per la fase di progettazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: 323fd58a-a462-4c48-b188-77ebc0b4212e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b663dc3b0a9c54d1674bf153ee09dd36e0de7a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623912"
---
# <a name="creating-a-custom-report-item-design-time-component"></a><span data-ttu-id="29ff7-102">Creazione di un componente dell'elemento del report personalizzato per la fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="29ff7-102">Creating a Custom Report Item Design-Time Component</span></span>
  <span data-ttu-id="29ff7-103">Un componente dell'elemento del report personalizzato per la fase di progettazione è un controllo che può essere utilizzato nell'ambiente Progettazione report di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="29ff7-103">A custom report item design-time component is a control that can be used in the Visual Studio Report Designer environment.</span></span> <span data-ttu-id="29ff7-104">Il componente dell'elemento del report personalizzato per la fase di progettazione fornisce un'area di progettazione attivata in grado di accettare operazioni di trascinamento della selezione, integrazione con il Visualizzatore proprietà di [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] e la possibilità di fornire editor di proprietà personalizzati.</span><span class="sxs-lookup"><span data-stu-id="29ff7-104">The custom report item design-time component provides an activated design surface that can accept drag-and-drop operations, integration with the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser, and the ability to provide custom property editors.</span></span>  
  
 <span data-ttu-id="29ff7-105">Con un componente dell'elemento del report personalizzato per la fase di progettazione, è possibile posizionare un elemento del report personalizzato in un report nell'ambiente di progettazione, impostare proprietà dei dati personalizzate nell'elemento del report personalizzato, quindi salvare l'elemento del report personalizzato come parte del progetto report.</span><span class="sxs-lookup"><span data-stu-id="29ff7-105">With a custom report item design-time component, the user can position a custom report item on a report in the design environment, set custom data properties on the custom report item, and then save the custom report item as part of the report project.</span></span>  
  
 <span data-ttu-id="29ff7-106">Le proprietà impostate mediante il componente per la fase di progettazione nell'ambiente di sviluppo vengono serializzate e deserializzate dall'ambiente di progettazione host, quindi archiviate come elementi nel file RDL (Report Definition Language).</span><span class="sxs-lookup"><span data-stu-id="29ff7-106">The properties that are set using the design-time component in the development environment are serialized and deserialized by the host design environment and then stored as elements in the Report Definition Language (RDL) file.</span></span> <span data-ttu-id="29ff7-107">Quando il report viene eseguito dal componente Elaborazione report, le proprietà impostate mediante il componente per la fase di progettazione vengono passate dal componente Elaborazione report a un componente runtime dell'elemento del report personalizzato che esegue il rendering dell'elemento del report personalizzato e lo passa nuovamente a Elaborazione report.</span><span class="sxs-lookup"><span data-stu-id="29ff7-107">When the report is executed by the report processor, the properties that are set using the design-time component are passed by the report processor to a custom report item run-time component, which renders the custom report item and passes it back to the report processor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29ff7-108">Il componente dell'elemento del report personalizzato per la fase di progettazione viene implementato come componente [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29ff7-108">The custom report item design-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component.</span></span> <span data-ttu-id="29ff7-109">In questo documento vengono illustrati dettagli di implementazione specifici del componente dell'elemento del report personalizzato per la fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="29ff7-109">This document will describe implementation details specific to the custom report item design-time component.</span></span> <span data-ttu-id="29ff7-110">Per altre informazioni sullo sviluppo di componenti tramite [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], vedere [Components in Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) (Componenti in Visual Studio) in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="29ff7-110">For more information about developing components using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see [Components in Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) in the MSDN library.</span></span>  
  
 <span data-ttu-id="29ff7-111">Per un esempio di elemento del report personalizzato completamente implementato, vedere [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Esempi del prodotto SQL Server Reporting Services).</span><span class="sxs-lookup"><span data-stu-id="29ff7-111">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="implementing-a-design-time-component"></a><span data-ttu-id="29ff7-112">Implementazione di un componente per la fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="29ff7-112">Implementing a Design-Time Component</span></span>  
 <span data-ttu-id="29ff7-113">La classe principale di un componente dell'elemento del report personalizzato per la fase di progettazione viene ereditata dalla classe `Microsoft.ReportDesigner.CustomReportItemDesigner`.</span><span class="sxs-lookup"><span data-stu-id="29ff7-113">The main class of a custom report item design-time component is inherited from the `Microsoft.ReportDesigner.CustomReportItemDesigner` class.</span></span> <span data-ttu-id="29ff7-114">Oltre agli attributi standard utilizzati per un controllo [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], la classe del componente deve definire un attributo `CustomReportItem`.</span><span class="sxs-lookup"><span data-stu-id="29ff7-114">In addition to the standard attributes used for a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] control, your component class should define a `CustomReportItem` attribute.</span></span> <span data-ttu-id="29ff7-115">Questo attributo deve corrispondere al nome dell'elemento del report personalizzato secondo la definizione presente nel file reportserver.config.</span><span class="sxs-lookup"><span data-stu-id="29ff7-115">This attribute must correspond to the name of the custom report item as it is defined in the reportserver.config file.</span></span> <span data-ttu-id="29ff7-116">Per un elenco di attributi [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], vedere Attributi nella documentazione di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="29ff7-116">For a list of [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] attributes, see Attributes in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
 <span data-ttu-id="29ff7-117">Nell'esempio di codice seguente vengono illustrati gli attributi applicati a un controllo dell'elemento del report personalizzato per la fase di progettazione:</span><span class="sxs-lookup"><span data-stu-id="29ff7-117">The following code example shows attributes being applied to a custom report item design-time control:</span></span>  
  
```csharp  
namespace PolygonsCRI  
{  
    [LocalizedName("Polygons")]  
    [Editor(typeof(CustomEditor), typeof(ComponentEditor))]  
        [ToolboxBitmap(typeof(PolygonsDesigner),"Polygons.ico")]  
        [CustomReportItem("Polygons")]  
  
    public class PolygonsDesigner : CustomReportItemDesigner  
    {  
...  
```  
  
### <a name="initializing-the-component"></a><span data-ttu-id="29ff7-118">Inizializzazione del componente</span><span class="sxs-lookup"><span data-stu-id="29ff7-118">Initializing the Component</span></span>  
 <span data-ttu-id="29ff7-119">Le proprietà specificate dall'utente per un elemento del report personalizzato vengono passate mediante una classe <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData>.</span><span class="sxs-lookup"><span data-stu-id="29ff7-119">You pass user-specified properties for a custom report item using a <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class.</span></span> <span data-ttu-id="29ff7-120">L'implementazione della classe `CustomReportItemDesigner` deve eseguire l'override del metodo `InitializeNewComponent` per creare una nuova istanza della classe <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> del componente e impostarla su valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="29ff7-120">Your implementation of the `CustomReportItemDesigner` class should override the `InitializeNewComponent` method to create a new instance of your component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class and set it to default values.</span></span>  
  
 <span data-ttu-id="29ff7-121">Nell'esempio di codice seguente viene illustrata una classe del componente dell'elemento del report personalizzato per la fase di progettazione che esegue l'override del metodo `CustomReportItemDesigner.InitializeNewComponent` per inizializzare la classe <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> del componente:</span><span class="sxs-lookup"><span data-stu-id="29ff7-121">The following code example shows an example of a custom report item design-time component class overriding the `CustomReportItemDesigner.InitializeNewComponent` method to initialize the component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class:</span></span>  
  
```csharp  
public override void InitializeNewComponent()  
        {  
            CustomData = new CustomData();  
            CustomData.DataRowHierarchy = new DataHierarchy();  
  
            // Shape grouping  
            CustomData.DataRowHierarchy.DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].Group.Name = Name + "_Shape";  
            CustomData.DataRowHierarchy.DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Point grouping  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.Name = Name + "_Point";  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Static column  
            CustomData.DataColumnHierarchy = new DataHierarchy();  
            CustomData.DataColumnHierarchy.DataMembers.Add(new DataMember());  
  
            // Points  
            IList<IList<DataValue>> dataValues = new List<IList<DataValue>>();  
            CustomData.DataRows.Add(dataValues);  
            CustomData.DataRows[0].Add(new List<DataValue>());  
            CustomData.DataRows[0][0].Add(NewDataValue("X", ""));  
            CustomData.DataRows[0][0].Add(NewDataValue("Y", ""));  
        }  
```  
  
### <a name="modifying-component-properties"></a><span data-ttu-id="29ff7-122">Modifica delle proprietà del componente</span><span class="sxs-lookup"><span data-stu-id="29ff7-122">Modifying Component Properties</span></span>  
 <span data-ttu-id="29ff7-123">È possibile modificare le proprietà `CustomData` nell'ambiente di progettazione in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="29ff7-123">You can modify `CustomData` properties in the design environment in several ways.</span></span> <span data-ttu-id="29ff7-124">È possibile modificare qualsiasi proprietà esposta dal componente per la fase di progettazione che sia contrassegnata con l'attributo <xref:System.ComponentModel.BrowsableAttribute> tramite il visualizzatore proprietà [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29ff7-124">You can modify any properties that are exposed by the design-time component that are marked with the <xref:System.ComponentModel.BrowsableAttribute> attribute by using the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser.</span></span> <span data-ttu-id="29ff7-125">È anche possibile modificare le proprietà trascinando elementi nell'area di progettazione dell'elemento del report personalizzato o facendo clic con il pulsante destro del mouse sul controllo nell'ambiente di progettazione e scegliendo **Proprietà** dal menu di scelta rapida per visualizzare una finestra delle proprietà personalizzata.</span><span class="sxs-lookup"><span data-stu-id="29ff7-125">In addition, you can modify properties by dragging items onto the custom report item's design surface, or by right-clicking the control in the design environment and selecting **Properties** on the shortcut menu to display a custom properties window.</span></span>  
  
 <span data-ttu-id="29ff7-126">Nell'esempio di codice seguente viene illustrata una proprietà `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` alla quale è applicato l'attributo <xref:System.ComponentModel.BrowsableAttribute>:</span><span class="sxs-lookup"><span data-stu-id="29ff7-126">The following code example shows a `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` property that has the <xref:System.ComponentModel.BrowsableAttribute> attribute applied:</span></span>  
  
```csharp  
[Browsable(true), Category("Data")]  
public string DataSetName  
{  
      get  
      {  
         return CustomData.DataSetName;  
      }  
      set  
      {  
         CustomData.DataSetName = value;  
      }  
   }  
  
```  
  
 <span data-ttu-id="29ff7-127">È possibile associare il componente per la fase di progettazione a una finestra di dialogo dell'editor di proprietà personalizzato.</span><span class="sxs-lookup"><span data-stu-id="29ff7-127">You can provide your design-time component with a custom properties editor dialog box.</span></span> <span data-ttu-id="29ff7-128">L'implementazione dell'editor di proprietà personalizzato deve ereditare dalla classe <xref:System.ComponentModel.ComponentEditor> e creare un'istanza di una finestra di dialogo che può essere utilizzata per la modifica delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="29ff7-128">The custom property editor implementation should inherit from the <xref:System.ComponentModel.ComponentEditor> class, and it should create an instance of a dialog box that can be used for property editing.</span></span>  
  
 <span data-ttu-id="29ff7-129">Nell'esempio seguente viene illustrata un'implementazione di una classe che eredita da <xref:System.ComponentModel.ComponentEditor> e che consente di visualizzare una finestra di dialogo dell'editor di proprietà personalizzato:</span><span class="sxs-lookup"><span data-stu-id="29ff7-129">The following example shows an implementation of a class that inherits from <xref:System.ComponentModel.ComponentEditor> and displays a custom property editor dialog box:</span></span>  
  
```csharp  
internal sealed class CustomEditor : ComponentEditor  
{  
   public override bool EditComponent(  
      ITypeDescriptorContext context, object component)  
    {  
     PolygonsDesigner designer = (PolygonsDesigner)component;  
     PolygonProperties dialog = new PolygonProperties();  
     dialog.m_designerComponent = designer;  
     DialogResult result = dialog.ShowDialog();  
     if (result == DialogResult.OK)  
     {  
        designer.Invalidate();  
        designer.ChangeService().OnComponentChanged(designer, null, null, null);  
        return true;  
     }  
     else  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="29ff7-130">La finestra di dialogo dell'editor di proprietà personalizzato può richiamare l'Editor espressioni di Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="29ff7-130">Your custom property editor dialog box can invoke the Report Designer Expression Editor.</span></span> <span data-ttu-id="29ff7-131">Nell'esempio seguente l'Editor espressioni viene richiamato quando si seleziona il primo elemento nella casella combinata:</span><span class="sxs-lookup"><span data-stu-id="29ff7-131">In the following example, the Expression Editor is invoked when the user selects the first element in the combo box:</span></span>  
  
```csharp  
private void EditableCombo_SelectedIndexChanged(object sender,   
    EventArgs e)  
{  
   ComboBox combo = (ComboBox)sender;  
   if (combo.SelectedIndex == 0 && m_launchEditor)  
   {  
      m_launchEditor = false;  
      ExpressionEditor editor = new ExpressionEditor();  
      string newValue;  
      newValue = (string)editor.EditValue(null, m_designerComponent.Site, m_oldComboValue);  
      combo.Items[0] = newValue;  
   }  
}  
  
```  
  
### <a name="using-designer-verbs"></a><span data-ttu-id="29ff7-132">Utilizzo dei verbi di progettazione</span><span class="sxs-lookup"><span data-stu-id="29ff7-132">Using Designer Verbs</span></span>  
 <span data-ttu-id="29ff7-133">Un verbo di progettazione è un comando di menu collegato a un gestore evento.</span><span class="sxs-lookup"><span data-stu-id="29ff7-133">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="29ff7-134">È possibile aggiungere verbi di progettazione da visualizzare nel menu di scelta rapida di un componente quando il controllo di runtime di un elemento del report personalizzato viene utilizzato nell'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="29ff7-134">You can add designer verbs that will appear in a component's shortcut menu when your custom report item run-time control is being used in the design environment.</span></span> <span data-ttu-id="29ff7-135">È possibile restituire l'elenco dei verbi di progettazione disponibili del componente runtime tramite la proprietà `Verbs`.</span><span class="sxs-lookup"><span data-stu-id="29ff7-135">You can return the list of available designer verbs from your run-time component by using the `Verbs` property.</span></span>  
  
 <span data-ttu-id="29ff7-136">Nell'esempio di codice seguente vengono illustrati un verbo di progettazione e un gestore evento aggiunti a <xref:System.ComponentModel.Design.DesignerVerbCollection>, oltre al codice del gestore evento:</span><span class="sxs-lookup"><span data-stu-id="29ff7-136">The following code example shows a designer verb and an event handler being added to the <xref:System.ComponentModel.Design.DesignerVerbCollection>, as well as the event handler code:</span></span>  
  
```csharp  
public override DesignerVerbCollection Verbs  
{  
    get  
    {  
        if (m_verbs == null)  
        {  
            m_verbs = new DesignerVerbCollection();  
            m_verbs.Add(new DesignerVerb("Proportional Scaling", new EventHandler(OnProportionalScaling)));  
         m_verbs[0].Checked = (GetCustomProperty("poly:Proportional") == bool.TrueString);  
        }  
  
        return m_verbs;  
    }  
}  
  
private void OnProportionalScaling(object sender, EventArgs e)  
{  
   bool proportional = !  
        (GetCustomProperty("poly:Proportional") == bool.TrueString);  
   m_verbs[0].Checked = proportional;  
   SetCustomProperty("poly:Proportional", proportional.ToString());  
   ChangeService().OnComponentChanged(this, null, null, null);  
   Invalidate();  
}  
```  
  
### <a name="using-adornments"></a><span data-ttu-id="29ff7-137">Utilizzo delle aree di controllo</span><span class="sxs-lookup"><span data-stu-id="29ff7-137">Using Adornments</span></span>  
 <span data-ttu-id="29ff7-138">Le classi di un elemento del report personalizzato possono anche implementare una classe `Microsoft.ReportDesigner.Design.Adornment`.</span><span class="sxs-lookup"><span data-stu-id="29ff7-138">Custom report item classes can also implement a `Microsoft.ReportDesigner.Design.Adornment` class.</span></span> <span data-ttu-id="29ff7-139">Un'area di controllo consente al controllo dell'elemento del report personalizzato di fornire aree esterne al rettangolo principale dell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="29ff7-139">An adornment allows the custom report item control to provide areas outside the main rectangle of the design surface.</span></span> <span data-ttu-id="29ff7-140">Tali aree possono gestire eventi dell'interfaccia utente, quali clic del mouse e operazioni di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="29ff7-140">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span> <span data-ttu-id="29ff7-141">La `Adornment` classe definita nello [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` spazio dei nomi è un'implementazione pass-through della <xref:System.Windows.Forms.Design.Behavior.Adorner> classe trovata in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="29ff7-141">The `Adornment` class that is defined in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` namespace is a pass-through implementation of the <xref:System.Windows.Forms.Design.Behavior.Adorner> class found in Windows Forms.</span></span> <span data-ttu-id="29ff7-142">Per la documentazione completa sulla `Adorner` classe, vedere [Cenni preliminari sul servizio di comportamento](https://go.microsoft.com/fwlink/?LinkId=116673) in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="29ff7-142">For complete documentation on the `Adorner` class, see [Behavior Service Overview](https://go.microsoft.com/fwlink/?LinkId=116673) in the MSDN library.</span></span> <span data-ttu-id="29ff7-143">Per il codice di esempio che implementa una `Microsoft.ReportDesigner.Design.Adornment` classe, vedere [SQL Server Reporting Services esempi del prodotto](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="29ff7-143">For sample code that implements a `Microsoft.ReportDesigner.Design.Adornment` class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
 <span data-ttu-id="29ff7-144">Per ulteriori informazioni sulla programmazione e sull'utilizzo di Windows Form in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], vedere i seguenti argomenti in MSDN Library:</span><span class="sxs-lookup"><span data-stu-id="29ff7-144">For more information about programming and using Windows Forms in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see these topics in the MSDN Library:</span></span>  
  
-   <span data-ttu-id="29ff7-145">Attributi per componenti in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="29ff7-145">Design-Time Attributes for Components</span></span>  
  
-   <span data-ttu-id="29ff7-146">Componenti di [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29ff7-146">Components in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span></span>  
  
-   <span data-ttu-id="29ff7-147">Procedura dettagliata: creazione di un controllo di Windows Form che usufruisca delle caratteristiche offerte da Visual Studio in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="29ff7-147">Walkthrough: Creating a Windows Forms Control that Takes Advantage of Visual Studio Design-Time Features</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ff7-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29ff7-148">See Also</span></span>  
 <span data-ttu-id="29ff7-149">[Architettura dell'elemento del report personalizzato](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="29ff7-149">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="29ff7-150">[Creazione di un componente runtime dell'elemento del report personalizzato](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="29ff7-150">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="29ff7-151">[Librerie di classi dell'elemento del report personalizzato](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="29ff7-151">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="29ff7-152">Procedura: Distribuire un elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="29ff7-152">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
