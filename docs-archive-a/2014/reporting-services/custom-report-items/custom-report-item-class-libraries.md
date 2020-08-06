---
title: Librerie di classi dell'elemento del report personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, RDL
- RDL [Reporting Services], custom report items
ms.assetid: f18c5d8f-1d6b-4f0b-8657-c14896c2ce0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60f8cf912eb6ff3f5080e9cf757df40f37e65079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623910"
---
# <a name="custom-report-item-class-libraries"></a><span data-ttu-id="1f3aa-102">Librerie di classi dell'elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="1f3aa-102">Custom Report Item Class Libraries</span></span>
  <span data-ttu-id="1f3aa-103">Gli elementi del report personalizzati utilizzano le classi dello spazio dei nomi `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-103">Custom report items use classes from the `Microsoft.ReportDesigner` namespace.</span></span> <span data-ttu-id="1f3aa-104">Le classi utilizzate per implementare un elemento del report personalizzato possono essere suddivise in due categorie principali: le classi univoche progettate per supportare l'infrastruttura dell'elemento del report personalizzato e le classi wrapper gestite che incapsulano la funzionalità degli elementi RDL (Report Definition Language) rilevanti.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-104">The classes used to implement a custom report item can be grouped into two main categories: unique classes designed to support custom report item infrastructure, and managed wrapper classes that encapsulate the functionality of relevant Report Definition Language (RDL) elements.</span></span> <span data-ttu-id="1f3aa-105">Per un esempio di codice sull'uso di queste classi, vedere [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Esempi del prodotto SQL Server Reporting Services).</span><span class="sxs-lookup"><span data-stu-id="1f3aa-105">For a code sample on how to use these classes, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-infrastructure-classes"></a><span data-ttu-id="1f3aa-106">Classi di infrastruttura dell'elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="1f3aa-106">Custom Report Item Infrastructure Classes</span></span>  
 <span data-ttu-id="1f3aa-107">Le classi riportate di seguito vengono utilizzate per implementare un elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-107">The following classes are used to implement a custom report item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f3aa-108">Nelle tabelle seguenti non vengono forniti elenchi completi, ma solo le proprietà e i metodi utilizzati più di frequente per ciascuna classe.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-108">The following tables are not complete listings; they include only the most commonly used properties and methods for each class.</span></span>  
  
### <a name="microsoftreportdesignercustomreportitemdesigner"></a><span data-ttu-id="1f3aa-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span><span class="sxs-lookup"><span data-stu-id="1f3aa-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span></span>  
 <span data-ttu-id="1f3aa-110">È la classe principale dell'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-110">This is the main custom report item class.</span></span> <span data-ttu-id="1f3aa-111">La classe principale dell'implementazione dell'elemento del report personalizzato deve ereditare da questa classe.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-111">The main class of your custom report item implementation must inherit from this class.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="1f3aa-112">Proprietà pubbliche</span><span class="sxs-lookup"><span data-stu-id="1f3aa-112">Public Properties</span></span>  
  
|||  
|-|-|  
|`Name`|<span data-ttu-id="1f3aa-113">Nome dell'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-113">The name of the custom report item.</span></span>|  
|`Type`|<span data-ttu-id="1f3aa-114">Tipo di elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-114">The type of the custom report item.</span></span>|  
|`CustomData`|<span data-ttu-id="1f3aa-115">Oggetto <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> che incapsula le proprietà dei dati dell'elemento del report personalizzato specificate in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-115">A <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> object that encapsulates the custom report item data properties specified at design time.</span></span>|  
|`CustomProperties`|<span data-ttu-id="1f3aa-116">Raccolta di proprietà personalizzate per l'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-116">A collection of custom properties for the custom report item.</span></span>|  
|`Height`|<span data-ttu-id="1f3aa-117">Altezza del controllo dell'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-117">The height of the custom report item control.</span></span>|  
|`Width`|<span data-ttu-id="1f3aa-118">Larghezza del controllo dell'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-118">The width of the custom report item control.</span></span>|  
|`Report`|<span data-ttu-id="1f3aa-119">Contenitore per le proprietà a livello di report, ad esempio l'elenco dei set di dati nel report.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-119">A container for the report-level properties, such as the list of datasets in the report.</span></span>|  
|`AltReportItem`|<span data-ttu-id="1f3aa-120">Oggetto elemento del report alternativo, da utilizzare se il controllo di runtime di un elemento del report personalizzato non è supportato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-120">The alternate report item object, to be used where the custom report item run-time control is not supported.</span></span>|  
|`Style`|<span data-ttu-id="1f3aa-121">Proprietà di stile per l'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-121">The style properties for the custom report item.</span></span>|  
|`Adornment`|<span data-ttu-id="1f3aa-122">Finestra dell'area di controllo utilizzata per la modifica interattiva del controllo.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-122">An adornment window used for interactive editing of the control.</span></span>|  
|`Site`|<span data-ttu-id="1f3aa-123">`ISite` del componente.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-123">The `ISite` of the component.</span></span>|  
|`DesignerVerbCollection`|<span data-ttu-id="1f3aa-124">Matrice di verbi personalizzati per il menu di scelta rapida del controllo.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-124">An array of custom verbs for the control's shortcut menu.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="1f3aa-125">Metodi pubblici</span><span class="sxs-lookup"><span data-stu-id="1f3aa-125">Public Methods</span></span>  
  
|||  
|-|-|  
|`BeginEdit`|<span data-ttu-id="1f3aa-126">Attiva la modifica interattiva per il controllo.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-126">Activates interactive editing for the control.</span></span>|  
|`DoDefaultAction`|<span data-ttu-id="1f3aa-127">Viene chiamato quando si fa doppio clic o si preme Invio sul controllo.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-127">Called in response to double-clicking or pressing Return on the control.</span></span>|  
|`EndEdit`|<span data-ttu-id="1f3aa-128">Disattiva la modifica interattiva per il controllo.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-128">Deactivates interactive editing for the control.</span></span>|  
|`GetService`|<span data-ttu-id="1f3aa-129">Restituisce un oggetto che rappresenta un servizio.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-129">Returns an object which represents a service.</span></span>|  
|`InitializeNewComponent`|<span data-ttu-id="1f3aa-130">Viene chiamato quando si crea un nuovo elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-130">Called when a new custom report item is created.</span></span>|  
|`Invalidate`|<span data-ttu-id="1f3aa-131">Ridisegna l'intera superficie del controllo.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-131">Repaints the entire surface of the control.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragDrop`|<span data-ttu-id="1f3aa-132">Viene chiamato quando si trascina un oggetto sul controllo.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-132">Called when an object is dragged onto the control.</span></span>|  
|`OnPaint`|<span data-ttu-id="1f3aa-133">Viene chiamato in risposta all'evento `Paint`.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-133">Called in response to the `Paint` event.</span></span>|  
  
### <a name="microsoftreportdesignercustomreportitemattribute"></a><span data-ttu-id="1f3aa-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span><span class="sxs-lookup"><span data-stu-id="1f3aa-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span></span>  
 <span data-ttu-id="1f3aa-135">Attributo utilizzato per identificare il tipo di elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-135">This is the attribute used to identify the type of the custom report item.</span></span> <span data-ttu-id="1f3aa-136">Il nome deve corrispondere al valore dell'attributo <`Name`> dell' `ReportItem` elemento nel file di configurazione progettazione report.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-136">The name must match the value of the <`Name`> attribute of the `ReportItem` element in the Report Designer configuration file.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="1f3aa-137">Metodi pubblici</span><span class="sxs-lookup"><span data-stu-id="1f3aa-137">Public Methods</span></span>  
  
|||  
|-|-|  
|`CustomReportItemAttribute`|<span data-ttu-id="1f3aa-138">Crea l'oggetto CustomReportItemAttribute.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-138">Constructs the CustomReportItemAttribute object.</span></span>|  
  
### <a name="microsoftreportdesignerlocalizednameattribute"></a><span data-ttu-id="1f3aa-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span><span class="sxs-lookup"><span data-stu-id="1f3aa-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span></span>  
 <span data-ttu-id="1f3aa-140">Attributo utilizzato per specificare il nome visualizzato da utilizzare per la finestra di progettazione dell'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-140">This is the attribute used to specify display name to use for the custom report item designer.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="1f3aa-141">Metodi pubblici</span><span class="sxs-lookup"><span data-stu-id="1f3aa-141">Public Methods</span></span>  
  
|||  
|-|-|  
|`LocalizedNameAttribute`|<span data-ttu-id="1f3aa-142">Crea l'oggetto LocalizedNameAttribute.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-142">Constructs the LocalizedNameAttribute object.</span></span>|  
  
### <a name="microsoftreportdesigneradornment"></a><span data-ttu-id="1f3aa-143">Microsoft.ReportDesigner.Adornment</span><span class="sxs-lookup"><span data-stu-id="1f3aa-143">Microsoft.ReportDesigner.Adornment</span></span>  
 <span data-ttu-id="1f3aa-144">La classe `Adornment` viene utilizzata dal componente dell'elemento del report personalizzato per la fase di progettazione per fornire aree esterne al rettangolo principale dell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-144">The `Adornment` class is used by the custom report item design-time component to provide areas outside of the main rectangle of the design surface.</span></span> <span data-ttu-id="1f3aa-145">Tali aree possono gestire eventi dell'interfaccia utente, quali clic del mouse e operazioni di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-145">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="1f3aa-146">Metodi pubblici</span><span class="sxs-lookup"><span data-stu-id="1f3aa-146">Public Methods</span></span>  
  
|||  
|-|-|  
|`OnShow`|<span data-ttu-id="1f3aa-147">Viene chiamato quando viene attivato `Adornment`.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-147">Called when the `Adornment` is activated.</span></span>|  
|`OnHide`|<span data-ttu-id="1f3aa-148">Viene chiamato quando viene disattivato `Adornment`.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-148">Called when the `Adornment` is deactivated.</span></span>|  
|`Paint`|<span data-ttu-id="1f3aa-149">Viene chiamato in risposta all'evento `Paint`.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-149">Called in response to the `Paint` event.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragOver`<br /><br /> `OnDragLeave`<br /><br /> `OnDragDrop`|<span data-ttu-id="1f3aa-150">Viene chiamato quando un oggetto viene trascinato in `Adornment`.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-150">Called when an object is dragged into the `Adornment`.</span></span>|  
  
### <a name="microsoftreportdesigneradornerservice"></a><span data-ttu-id="1f3aa-151">Microsoft.ReportDesigner.AdornerService</span><span class="sxs-lookup"><span data-stu-id="1f3aa-151">Microsoft.ReportDesigner.AdornerService</span></span>  
 <span data-ttu-id="1f3aa-152">Questa classe viene utilizzata per fornire una raccolta di servizi visualizzati utilizzati dall'elemento del report personalizzato per supportare gli oggetti `Adornment` per il componente della fase di progettazione dell'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-152">This class is used to provide a collection of display services used by the custom report item to support `Adornment` objects for the custom report item design-time component.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="1f3aa-153">Proprietà pubbliche</span><span class="sxs-lookup"><span data-stu-id="1f3aa-153">Public Properties</span></span>  
  
|||  
|-|-|  
|`AdornerWindowBounds`|<span data-ttu-id="1f3aa-154">Limiti della finestra Adorner.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-154">The bounds of the Adorner window.</span></span>|  
|`AdornerWindowRegion`|<span data-ttu-id="1f3aa-155">Area della finestra Adorner.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-155">The region of the Adorner window.</span></span>|  
|`AdornerWindowGraphics`|<span data-ttu-id="1f3aa-156">Contesto grafico per la finestra Adorner.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-156">A graphics context for the Adorner window.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="1f3aa-157">Metodi pubblici</span><span class="sxs-lookup"><span data-stu-id="1f3aa-157">Public Methods</span></span>  
  
|||  
|-|-|  
|`ComponentRectInDesignerFrame`|<span data-ttu-id="1f3aa-158">Restituisce i limiti del componente convertito nelle coordinate della cornice della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-158">Returns the bounds of the component translated into designer frame coordinates.</span></span>|  
|`InvalidateAdorner`|<span data-ttu-id="1f3aa-159">Invalida la finestra Adorner.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-159">Invalidates the Adorner window.</span></span>|  
|`PointToAdorner`|<span data-ttu-id="1f3aa-160">Restituisce un punto nelle coordinate dello schermo convertito nelle coordinate della finestra Adorner.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-160">Returns a point in screen coordinates translated to Adorner window coordinates.</span></span>|  
  
### <a name="microsoftreportdesignerexpressioneditor"></a><span data-ttu-id="1f3aa-161">Microsoft.ReportDesigner.ExpressionEditor</span><span class="sxs-lookup"><span data-stu-id="1f3aa-161">Microsoft.ReportDesigner.ExpressionEditor</span></span>  
 <span data-ttu-id="1f3aa-162">Questa classe può essere utilizzata da un controllo della fase di progettazione dell'elemento del report personalizzato per richiamare l'Editor espressioni.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-162">This class can be used from your custom report item design-time control to invoke the Expression Editor.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="1f3aa-163">Metodi pubblici</span><span class="sxs-lookup"><span data-stu-id="1f3aa-163">Public Methods</span></span>  
  
|||  
|-|-|  
|`EditValue`|<span data-ttu-id="1f3aa-164">Richiama l'Editor espressioni, inizializzato con il valore dell'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-164">Invokes the Expression Editor, initialized with the given object value.</span></span>|  
  
### <a name="microsoftreportdesignerifieldsdataobject"></a><span data-ttu-id="1f3aa-165">Microsoft.ReportDesigner.IFieldsDataObject</span><span class="sxs-lookup"><span data-stu-id="1f3aa-165">Microsoft.ReportDesigner.IFieldsDataObject</span></span>  
 <span data-ttu-id="1f3aa-166">Questa classe è una raccolta di campi di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e viene utilizzata per supportare eventi di trascinamento della selezione nell'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-166">This class is a collection of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] fields, and is used to support drag-and-drop events in the design environment.</span></span> <span data-ttu-id="1f3aa-167">Eredita dall'oggetto `IReportItemDataObject`.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-167">Inherits from `IReportItemDataObject`.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="1f3aa-168">Proprietà pubbliche</span><span class="sxs-lookup"><span data-stu-id="1f3aa-168">Public Properties</span></span>  
  
|||  
|-|-|  
|`DataSetName`|<span data-ttu-id="1f3aa-169">Nome del set di dati contenente i campi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-169">The name of the dataset containing the fields to be dropped.</span></span>|  
|`Fields`|<span data-ttu-id="1f3aa-170">Raccolta di campi (`Microsoft.ReportDesigner.Field`) da eliminare.</span><span class="sxs-lookup"><span data-stu-id="1f3aa-170">The collection of fields (`Microsoft.ReportDesigner.Field`) to be dropped.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1f3aa-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f3aa-171">See Also</span></span>  
 <span data-ttu-id="1f3aa-172">[Report Definition Language &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1f3aa-172">[Report Definition Language &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span></span>  
 <span data-ttu-id="1f3aa-173">[Creazione di un componente runtime dell'elemento del report personalizzato](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="1f3aa-173">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 [<span data-ttu-id="1f3aa-174">Creazione di un componente dell'elemento del report personalizzato per la fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="1f3aa-174">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
  
  
