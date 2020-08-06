---
title: Finestra di dialogo Proprietà azione (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.action.f1
- "10413"
- "10504"
- sql12.rtp.rptdesigner.calculatedseriesproperties.action.f1
- sql12.rtp.rptdesigner.pictureproperties.action.f1
- sql12.rtp.rptdesigner.actionproperties.f1
- sql12.rtp.rptdesigner.charttitleproperties.action.f1
- "10133"
- "10052"
- "10147"
- sql12.rtp.rptdesigner.chartproperties.action.f1
- "10122"
- sql12.rtp.rptdesigner.serieslabelproperties.action.f1
- sql12.rtp.rptdesigner.textboxproperties.action.f1
- "10162"
- "10168"
- sql12.rtp.rptdesigner.textproperties.action.f1
- sql12.rtp.rptdesigner.placeholderproperties.action.f1
- "10250"
- "10129"
- "10244"
- sql12.rtp.rptdesigner.seriesproperties.action.f1
ms.assetid: 2c5d915b-4f97-42cf-b8f1-49ca3ff3d0f9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77b51af0763010676b95fcedb433ab963fc7fcdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630367"
---
# <a name="action-properties-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="a7e52-102">Finestra di dialogo Proprietà azione (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a7e52-102">Action Properties Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a7e52-103">È possibile utilizzare la finestra di dialogo **Azione** per abilitare opzioni dei collegamenti ipertestuali per un grafico, un misuratore e gli elementi della mappa che supportano i collegamenti.</span><span class="sxs-lookup"><span data-stu-id="a7e52-103">The **Action** dialog box can be used to enable hyperlink options for a chart, gauge, and map elements that support links.</span></span> <span data-ttu-id="a7e52-104">Definire un'azione in modo che un utente possa fare clic sul report e collegarsi a un URL, a un report diverso nello stesso server di report o in un sito di SharePoint integrato con un server di report oppure a un percorso diverso nello stesso report.</span><span class="sxs-lookup"><span data-stu-id="a7e52-104">Define an action so that a user can click on the report and link to a URL, to a different report on the same report server or on a SharePoint site that is integrated with a report server, or to a different location in the same report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a7e52-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a7e52-105">Options</span></span>  
 <span data-ttu-id="a7e52-106">**Abilita come azione**</span><span class="sxs-lookup"><span data-stu-id="a7e52-106">**Enable as an action**</span></span>  
 <span data-ttu-id="a7e52-107">Selezionare un'opzione per indicare l'azione da eseguire quando l'utente fa clic sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="a7e52-107">Select an option to indicate the action to perform when the user clicks the item.</span></span>  
  
 <span data-ttu-id="a7e52-108">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="a7e52-108">**None**</span></span>  
 <span data-ttu-id="a7e52-109">Selezionare questa opzione per indicare che all'elemento non è associata alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="a7e52-109">Choose this option to indicate that the item has no action.</span></span>  
  
 <span data-ttu-id="a7e52-110">**Vai al report**</span><span class="sxs-lookup"><span data-stu-id="a7e52-110">**Go to report**</span></span>  
 <span data-ttu-id="a7e52-111">Scegliere questa opzione per creare un collegamento a un report drill-through disponibile in un server di report.</span><span class="sxs-lookup"><span data-stu-id="a7e52-111">Choose this option to create a link to a drillthrough report that is located on a report server.</span></span> <span data-ttu-id="a7e52-112">Le opzioni aggiuntive elencate di seguito vengono visualizzate quando si seleziona **Vai al report**.</span><span class="sxs-lookup"><span data-stu-id="a7e52-112">The following additional options appear when you select **Go to report**.</span></span>  
  
 <span data-ttu-id="a7e52-113">**Specificare un report**</span><span class="sxs-lookup"><span data-stu-id="a7e52-113">**Specify a report**</span></span>  
 <span data-ttu-id="a7e52-114">Digitare o selezionare il nome del report che si desidera utilizzare come report drill-through.</span><span class="sxs-lookup"><span data-stu-id="a7e52-114">Type or select the name of the report that you want to use as a drillthrough report.</span></span> <span data-ttu-id="a7e52-115">I report drill-through devono trovarsi sullo stesso server di report di questo report.</span><span class="sxs-lookup"><span data-stu-id="a7e52-115">Drillthrough reports must be on the same report server as this report.</span></span>  
  
 <span data-ttu-id="a7e52-116">Per un report pubblicato in un server di report configurato per la modalità nativa, utilizzare un percorso completo o relativo senza l'estensione del nome di file.</span><span class="sxs-lookup"><span data-stu-id="a7e52-116">For a report published to a report server configured for native mode, use a full or relative path without the file name extension.</span></span> <span data-ttu-id="a7e52-117">Se il report è archiviato nella stessa cartella del report corrente, è sufficiente utilizzare il nome del report.</span><span class="sxs-lookup"><span data-stu-id="a7e52-117">If the report is in the same folder as the current report, use the name of the report only.</span></span> <span data-ttu-id="a7e52-118">Se il report si trova in una cartella diversa nello stesso server di report, utilizzare un percorso relativo o completo.</span><span class="sxs-lookup"><span data-stu-id="a7e52-118">If the report is in a different folder on the same report server, use a relative path or a full path.</span></span> <span data-ttu-id="a7e52-119">Un percorso relativo inizia dalla cartella corrente e risale la gerarchia di cartelle, ad esempio ../Cartella2/Report1.</span><span class="sxs-lookup"><span data-stu-id="a7e52-119">A relative path starts from the current folder and moves up the folder hierarchy, for example, ../Folder2/Report1.</span></span> <span data-ttu-id="a7e52-120">Un percorso completo inizia da /, la cartella Home,</span><span class="sxs-lookup"><span data-stu-id="a7e52-120">A full path starts from /, the Home folder.</span></span> <span data-ttu-id="a7e52-121">ad esempio /Report/Report1.</span><span class="sxs-lookup"><span data-stu-id="a7e52-121">For example, /Reports/Report1.</span></span>  
  
 <span data-ttu-id="a7e52-122">Per un report pubblicato in un server di report configurato per la modalità integrata SharePoint, utilizzare un URL completo, inclusa l'estensione del nome di file (RDL).</span><span class="sxs-lookup"><span data-stu-id="a7e52-122">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL including the file name extension (.rdl).</span></span> <span data-ttu-id="a7e52-123">Ad esempio, http:// *\<SharePointservername>/\<site>* /Documents/Report1.rdl.</span><span class="sxs-lookup"><span data-stu-id="a7e52-123">For example, http://*\<SharePointservername>/\<site>*/Documents/Report1.rdl.</span></span> <span data-ttu-id="a7e52-124">I percorsi relativi non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="a7e52-124">Relative paths are not supported.</span></span>  
  
 <span data-ttu-id="a7e52-125">Per altre informazioni, vedere [Specifica di percorsi di elementi esterni &#40;Generatore report e SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) nella [documentazione di Generatore report](https://go.microsoft.com/fwlink/?LinkId=154494) nel sito msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a7e52-125">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) in the [Report Builder documentation](https://go.microsoft.com/fwlink/?LinkId=154494) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="a7e52-126">**Utilizzare i parametri seguenti per eseguire il report**</span><span class="sxs-lookup"><span data-stu-id="a7e52-126">**Use these parameters to run the report**</span></span>  
 <span data-ttu-id="a7e52-127">Aggiungere un elenco di parametri da passare al report drill-through.</span><span class="sxs-lookup"><span data-stu-id="a7e52-127">Add a list of parameters to pass to the drillthrough report.</span></span> <span data-ttu-id="a7e52-128">I nomi dei parametri devono corrispondere ai parametri definiti per il report di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a7e52-128">The parameter names must match the parameters defined for the target report.</span></span> <span data-ttu-id="a7e52-129">Utilizzare i pulsanti **Aggiungi** ed **Elimina** per aggiungere e rimuovere parametri e le frecce SU e GIÙ per ordinare l'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="a7e52-129">Use the **Add** and **Delete** buttons to add and remove parameters and use the up and down arrows to order the list of parameters.</span></span>  
  
 <span data-ttu-id="a7e52-130">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="a7e52-130">**Add**</span></span>  
 <span data-ttu-id="a7e52-131">Consente di aggiungere un nuovo parametro da passare al report drill-through.</span><span class="sxs-lookup"><span data-stu-id="a7e52-131">Add a new parameter to pass to the drillthrough report.</span></span>  
  
 <span data-ttu-id="a7e52-132">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="a7e52-132">**Delete**</span></span>  
 <span data-ttu-id="a7e52-133">Consente di eliminare un parametro per il report drill-through.</span><span class="sxs-lookup"><span data-stu-id="a7e52-133">Delete a parameter for the drillthrough report.</span></span>  
  
 <span data-ttu-id="a7e52-134">**Freccia in su**</span><span class="sxs-lookup"><span data-stu-id="a7e52-134">**Up arrow**</span></span>  
 <span data-ttu-id="a7e52-135">Consente di spostare il parametro di una posizione verso l'alto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a7e52-135">Move the parameter up in the list.</span></span>  
  
 <span data-ttu-id="a7e52-136">**Freccia GIÙ**</span><span class="sxs-lookup"><span data-stu-id="a7e52-136">**Down arrow**</span></span>  
 <span data-ttu-id="a7e52-137">Consente di spostare il parametro di una posizione verso il basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a7e52-137">Move the parameter down in the list.</span></span>  
  
 <span data-ttu-id="a7e52-138">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a7e52-138">**Name**</span></span>  
 <span data-ttu-id="a7e52-139">Digitare il testo che corrisponde al nome di un parametro definito nel report drill-through.</span><span class="sxs-lookup"><span data-stu-id="a7e52-139">Type text that is the name of a parameter defined in the drillthrough report.</span></span>  
  
 <span data-ttu-id="a7e52-140">**Valore**</span><span class="sxs-lookup"><span data-stu-id="a7e52-140">**Value**</span></span>  
 <span data-ttu-id="a7e52-141">Digitare o selezionare un valore da passare per il parametro denominato nel report drill-through.</span><span class="sxs-lookup"><span data-stu-id="a7e52-141">Type or select a value to pass for the named parameter in the drillthrough report.</span></span> <span data-ttu-id="a7e52-142">Fare clic sul pulsante **espressione** (*FX*) per modificare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="a7e52-142">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="a7e52-143">**Omettere**</span><span class="sxs-lookup"><span data-stu-id="a7e52-143">**Omit**</span></span>  
 <span data-ttu-id="a7e52-144">Selezionare questa opzione per impedire l'esecuzione del parametro.</span><span class="sxs-lookup"><span data-stu-id="a7e52-144">Select to prevent the parameter from running.</span></span> <span data-ttu-id="a7e52-145">Per impostazione predefinita, questa casella di controllo è deselezionata e non è attiva.</span><span class="sxs-lookup"><span data-stu-id="a7e52-145">By default, this check box is cleared and not active.</span></span> <span data-ttu-id="a7e52-146">Per selezionare la casella di controllo, fare clic sul pulsante **Espressione** (*fx*) e digitare **True** o creare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="a7e52-146">To select the check box, click the **Expression** (*fx*) button and either type **True** or create an expression.</span></span> <span data-ttu-id="a7e52-147">La casella di controllo viene selezionata quando si fa clic su **OK** nella finestra di dialogo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="a7e52-147">The check box is selected when you click **OK** in the **Expression** dialog box.</span></span>  
  
 <span data-ttu-id="a7e52-148">**Vai al segnalibro**</span><span class="sxs-lookup"><span data-stu-id="a7e52-148">**Go to bookmark**</span></span>  
 <span data-ttu-id="a7e52-149">Selezionare questa opzione per definire un collegamento a un segnalibro nel report corrente.</span><span class="sxs-lookup"><span data-stu-id="a7e52-149">Choose this option to define a link to a bookmark in the current report.</span></span> <span data-ttu-id="a7e52-150">L'opzione aggiuntiva elencata di seguito viene visualizzata quando si seleziona **Vai al segnalibro**.</span><span class="sxs-lookup"><span data-stu-id="a7e52-150">The following additional option appears when you select **Go to bookmark**.</span></span>  
  
 <span data-ttu-id="a7e52-151">**Selezionare un segnalibro**</span><span class="sxs-lookup"><span data-stu-id="a7e52-151">**Select bookmark**</span></span>  
 <span data-ttu-id="a7e52-152">Digitare o selezionare l'ID del segnalibro del report a cui passare quando viene fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="a7e52-152">Type or select the bookmark ID for the report to jump to when the user clicks the link.</span></span> <span data-ttu-id="a7e52-153">Fare clic sul pulsante Espressione (**fx**) per modificare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="a7e52-153">Click the Expression (**fx**) button to change the expression.</span></span> <span data-ttu-id="a7e52-154">L'ID del segnalibro può essere un ID statico oppure un'espressione che restituisce l'ID di un segnalibro.</span><span class="sxs-lookup"><span data-stu-id="a7e52-154">The bookmark ID can be either a static ID or an expression that evaluates to a bookmark ID.</span></span> <span data-ttu-id="a7e52-155">L'espressione può includere un campo contenente un ID del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="a7e52-155">The expression can include a field that contains a bookmark ID.</span></span>  
  
 <span data-ttu-id="a7e52-156">Per creare un collegamento a un segnalibro, è innanzitutto necessario impostare la proprietà Bookmark di un elemento del report.</span><span class="sxs-lookup"><span data-stu-id="a7e52-156">To link to a bookmark, you must first set the Bookmark property of a report item.</span></span> <span data-ttu-id="a7e52-157">Per impostare la proprietà Bookmark, selezionare un elemento del report e nel riquadro Proprietà digitare un valore o un'espressione per l'ID del segnalibro, ad esempio SalesChart o 5TopSales.</span><span class="sxs-lookup"><span data-stu-id="a7e52-157">To set the Bookmark property, select a report item, and in the Properties pane, type a value or expression for the bookmark ID; for example, SalesChart or 5TopSales.</span></span>  
  
 <span data-ttu-id="a7e52-158">**Vai a URL**</span><span class="sxs-lookup"><span data-stu-id="a7e52-158">**Go to URL**</span></span>  
 <span data-ttu-id="a7e52-159">Selezionare questa opzione per definire un collegamento a una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="a7e52-159">Choose this option to define a link to a Web page.</span></span> <span data-ttu-id="a7e52-160">Digitare o selezionare l'URL di una pagina Web o un'espressione che restituisca l'URL di una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="a7e52-160">Type or select the URL of a Web page or an expression that evaluates to the URL of a Web page.</span></span> <span data-ttu-id="a7e52-161">Fare clic sul pulsante **espressione** (*FX*) per modificare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="a7e52-161">Click the **Expression** (*fx*) button to change the expression.</span></span> <span data-ttu-id="a7e52-162">L'espressione può includere un campo contenente un URL.</span><span class="sxs-lookup"><span data-stu-id="a7e52-162">This expression can include a field that contains a URL.</span></span> <span data-ttu-id="a7e52-163">L'opzione aggiuntiva elencata di seguito viene visualizzata quando si seleziona **Vai a URL**.</span><span class="sxs-lookup"><span data-stu-id="a7e52-163">The following additional option appears when you select **Go to URL**.</span></span>  
  
 <span data-ttu-id="a7e52-164">**Selezionare un URL**</span><span class="sxs-lookup"><span data-stu-id="a7e52-164">**Select URL**</span></span>  
 <span data-ttu-id="a7e52-165">Digitare o immettere l'URL dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="a7e52-165">Type or enter the URL of the item.</span></span> <span data-ttu-id="a7e52-166">Per un elemento pubblicato in un server di report configurato per la modalità nativa, utilizzare un percorso completo o relativo.</span><span class="sxs-lookup"><span data-stu-id="a7e52-166">For an item published to a report server configured for native mode, use a full or relative path.</span></span> <span data-ttu-id="a7e52-167">Ad esempio, http:// *\<servername>* /images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="a7e52-167">For example, http://*\<servername>*/images/image1.jpg.</span></span> <span data-ttu-id="a7e52-168">Per un elemento pubblicato in un server di report configurato per la modalità integrata SharePoint, utilizzare un URL completo (ad esempio, http:// *\<SharePointservername>/\<site>* /Documents/images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="a7e52-168">For an item published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e52-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7e52-169">See Also</span></span>  
 <span data-ttu-id="a7e52-170">[Grafici &#40;Generatore report e SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a7e52-170">[Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a7e52-171">[Guida Generatore report per finestre di dialogo, riquadri e procedure guidate](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="a7e52-171">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="a7e52-172">[Parametri del report &#40;Generatore report e Progettazione report&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a7e52-172">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="a7e52-173">[Aggiunta di un sottoreport e di parametri &#40;Generatore report e SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a7e52-173">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a7e52-174">Ordinamento interattivo, mappe documento e collegamenti &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a7e52-174">Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;</span></span>](report-design/interactive-sort-document-maps-and-links-report-builder-and-ssrs.md)  
  
  
