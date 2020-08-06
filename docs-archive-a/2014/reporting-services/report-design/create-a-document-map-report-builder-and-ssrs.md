---
title: Creare una mappa documento (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c200a97b-67f2-499f-8374-3ed1ebe3f33c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a9dad0f8e6ee1d9b9ada44fda0eec5908f27cfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627146"
---
# <a name="create-a-document-map-report-builder-and-ssrs"></a><span data-ttu-id="27071-102">Creare una mappa documento (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="27071-102">Create a Document Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="27071-103">Una mappa documento offre un set di collegamenti a elementi di report in un report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="27071-103">A document map provides a set of navigational links to report items in a rendered report.</span></span> <span data-ttu-id="27071-104">Quando si visualizza un report che include una mappa documento, accanto al report viene visualizzato un riquadro distinto.</span><span class="sxs-lookup"><span data-stu-id="27071-104">When you view a report that includes a document map, a separate side pane appears next to the report.</span></span> <span data-ttu-id="27071-105">Gli utenti possono fare clic sui collegamenti della mappa documento per passare alla pagina del report in cui viene visualizzato l'elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="27071-105">A user can click links in the document map to jump to the report page that displays that item.</span></span> <span data-ttu-id="27071-106">Le sezioni del report e i gruppi sono disposti in una gerarchia di collegamenti.</span><span class="sxs-lookup"><span data-stu-id="27071-106">Report sections and groups are arranged in a hierarchy of links.</span></span> <span data-ttu-id="27071-107">Se si fa clic sugli elementi nella mappa documento, il report viene aggiornato e viene visualizzata l'area del report corrispondente all'elemento nella mappa documento.</span><span class="sxs-lookup"><span data-stu-id="27071-107">Clicking items in the document map refreshes the report and displays the area of the report that corresponds to the item in the document map.</span></span>  
  
 <span data-ttu-id="27071-108">Per aggiungere collegamenti alla mappa documento, impostare la proprietà `DocumentMapLabel` dell'elemento del report sul testo creato o su un'espressione che restituisca il testo da visualizzare nella mappa documento.</span><span class="sxs-lookup"><span data-stu-id="27071-108">To add links to the document map, you set the `DocumentMapLabel` property of the report item to text that you create or to an expression that evaluates to the text that you want display in the document map.</span></span> <span data-ttu-id="27071-109">A quest'ultima è possibile inoltre aggiungere i valori univoci per una tabella o un gruppo di matrici.</span><span class="sxs-lookup"><span data-stu-id="27071-109">You can also add the unique values for a table or matrix group to the document map.</span></span> <span data-ttu-id="27071-110">Per un gruppo basato su un colore, ad esempio, ogni colore univoco rappresenta un collegamento alla pagina del report in cui viene visualizzata l'istanza del gruppo per il colore specifico.</span><span class="sxs-lookup"><span data-stu-id="27071-110">For example, for a group based on color, each unique color is a link to the report page that displays the group instance for that color.</span></span>  
  
 <span data-ttu-id="27071-111">È inoltre possibile creare un URL di un report in cui viene ignorata la visualizzazione della mappa documento, in modo che sia possibile eseguire il report senza visualizzare la mappa documento e successivamente fare clic sul pulsante **Mostra/Nascondi mappa documento** sulla barra degli strumenti del visualizzatore di report per attivare e disattivare la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="27071-111">You can also create a URL to a report that overrides the display of the document map, so that you can run the report without displaying the document map, and then click the **Show/Hide Document Map** button on the report viewer toolbar to toggle the display.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="document-maps-and-rendering-extensions"></a><a name="DocMapRenderExtensions"></a> <span data-ttu-id="27071-112">Mappe documento ed estensioni per il rendering</span><span class="sxs-lookup"><span data-stu-id="27071-112">Document Maps and Rendering Extensions</span></span>  
 <span data-ttu-id="27071-113">La mappa documento è destinata all'uso nell'estensione per il rendering HTML, ad esempio in Anteprima e nel Visualizzatore report.</span><span class="sxs-lookup"><span data-stu-id="27071-113">The document map is intended for use in the HTML rendering extension-for example, in Preview and the Report Viewer.</span></span> <span data-ttu-id="27071-114">Altre estensioni per il rendering usano modalità diverse per organizzare una mappa documento:</span><span class="sxs-lookup"><span data-stu-id="27071-114">Other rendering extensions have different ways of articulating a document map:</span></span>  
  
-   <span data-ttu-id="27071-115">Con l'estensione per il rendering PDF, una mappa documento viene visualizzata come riquadro Segnalibri.</span><span class="sxs-lookup"><span data-stu-id="27071-115">PDF renders a document map as the Bookmarks pane.</span></span>  
  
-   <span data-ttu-id="27071-116">Con l'estensione per il rendering Excel, una mappa documento viene visualizzata come foglio di lavoro denominato che include una gerarchia di collegamenti.</span><span class="sxs-lookup"><span data-stu-id="27071-116">Excel renders a document map as a named worksheet that includes a hierarchy of links.</span></span> <span data-ttu-id="27071-117">Le sezioni del report vengono visualizzate in fogli di lavoro distinti inclusi nella mappa documento nella stessa cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="27071-117">Report sections are rendered in separate worksheets that are included with the document map in the same workbook.</span></span>  
  
-   <span data-ttu-id="27071-118">In Word è inclusa una mappa documento come sommario.</span><span class="sxs-lookup"><span data-stu-id="27071-118">Word includes a document map as the table of contents.</span></span>  
  
-   <span data-ttu-id="27071-119">In Atom, TIFF, XML e CSV le mappe documento vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="27071-119">Atom, TIFF, XML, and CSV ignore document maps.</span></span>  
  
 <span data-ttu-id="27071-120">Per altre informazioni, vedere [Funzionalità interattiva per estensioni per il rendering di report differenti &#40;Generatore report e SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="27071-120">For more information, see [Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span></span>  
  
##  <a name="AddRptItemToMap"></a>   
#### <a name="to-add-a-report-item-to-a-document-map"></a><span data-ttu-id="27071-121">Per aggiungere un elemento del report a una mappa documento</span><span class="sxs-lookup"><span data-stu-id="27071-121">To add a report item to a document map</span></span>  
  
1.  <span data-ttu-id="27071-122">In visualizzazione Progettazione fare clic sull'elemento del report, ad esempio una tabella, una matrice o un misuratore, che si desidera aggiungere alla mappa documento.</span><span class="sxs-lookup"><span data-stu-id="27071-122">In Design view, select the report item such as a table, matrix, or gauge that you want to add to the document map.</span></span> <span data-ttu-id="27071-123">Le proprietà dell'elemento di report verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="27071-123">The report item properties appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27071-124">Per selezionare un'area dati Tablix, fare clic in una cella per visualizzare gli handle di riga e di colonna, quindi fare clic sull'handle d'angolo.</span><span class="sxs-lookup"><span data-stu-id="27071-124">To select a tablix data region, click in any cell to display the row and column handles, and then click the corner handle.</span></span>  
  
2.  <span data-ttu-id="27071-125">Nel riquadro Proprietà digitare il testo che si desidera visualizzare nella mappa documento nella `DocumentMapLabel` Proprietà oppure immettere un'espressione che restituisca un'etichetta.</span><span class="sxs-lookup"><span data-stu-id="27071-125">In the Properties pane, type the text that you want to appear in the document map in the `DocumentMapLabel` property, or enter an expression that evaluates to a label.</span></span> <span data-ttu-id="27071-126">Digitare ad esempio **SalesChart**.</span><span class="sxs-lookup"><span data-stu-id="27071-126">For example, type **Sales Chart**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27071-127">Se il riquadro Proprietà non è visualizzato, nel gruppo **Mostra/Nascondi** della scheda **Visualizza** selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="27071-127">If you do not see the Properties pane, on the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="27071-128">Ripetere i passaggi 1 e 2 per ogni elemento di report da visualizzare nella mappa documento.</span><span class="sxs-lookup"><span data-stu-id="27071-128">Repeat steps 1 and 2 for every report item that you want to appear in the document map.</span></span>  
  
4.  <span data-ttu-id="27071-129">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="27071-129">Click **Run**.</span></span> <span data-ttu-id="27071-130">Verrà avviata l'esecuzione del report e nella mappa documento verranno visualizzate le etichette create.</span><span class="sxs-lookup"><span data-stu-id="27071-130">The report runs and the document map displays the labels you created.</span></span> <span data-ttu-id="27071-131">Fare clic su un collegamento qualsiasi per passare alla pagina del report in cui è presente l'elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="27071-131">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="AddUniqueValuesToMap"></a>   
#### <a name="to-add-unique-group-values-to-a-document-map"></a><span data-ttu-id="27071-132">Per aggiungere valori di gruppo univoci a una mappa documento</span><span class="sxs-lookup"><span data-stu-id="27071-132">To add unique group values to a document map</span></span>  
  
1.  <span data-ttu-id="27071-133">In visualizzazione Progettazione selezionare la tabella, la matrice o l'elenco che contiene il gruppo che si desidera visualizzare nella mappa documento.</span><span class="sxs-lookup"><span data-stu-id="27071-133">In Design view, select the table, matrix, or list that contains the group that you want to display in the document map.</span></span> <span data-ttu-id="27071-134">Nel riquadro di raggruppamento verranno visualizzati i gruppi di righe e di colonne.</span><span class="sxs-lookup"><span data-stu-id="27071-134">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="27071-135">Nel riquadro Gruppi di righe fare clic con il pulsante destro del mouse sul gruppo, quindi scegliere **Modifica gruppo**.</span><span class="sxs-lookup"><span data-stu-id="27071-135">In the Row Groups pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="27071-136">Verrà visualizzata la scheda **Generale** della finestra di dialogo **Proprietà gruppo Tablix** .</span><span class="sxs-lookup"><span data-stu-id="27071-136">The **General** page of the **Tablix Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="27071-137">Fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="27071-137">Click **Advanced**.</span></span>  
  
4.  <span data-ttu-id="27071-138">Nella casella di riepilogo **Mappa documento** digitare o selezionare un'espressione corrispondente all'espressione di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="27071-138">In the **Document map** list box, type or select an expression that matches the group expression.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="27071-139">Ripetere i passaggi da 1 a 4 per ogni gruppo che si desidera visualizzare nella mappa documento.</span><span class="sxs-lookup"><span data-stu-id="27071-139">Repeat steps 1-4 for every group that you want to appear in the document map.</span></span>  
  
7.  <span data-ttu-id="27071-140">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="27071-140">Click **Run**.</span></span> <span data-ttu-id="27071-141">Verrà avviata l'esecuzione del report e nella mappa documento verranno visualizzati i valori dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="27071-141">The report runs and the document map displays the group values.</span></span> <span data-ttu-id="27071-142">Fare clic su un collegamento qualsiasi per passare alla pagina del report in cui è presente l'elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="27071-142">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="HideMapWhenViewRpt"></a>   
#### <a name="to-hide-the-document-map-when-you-view-a-report"></a><span data-ttu-id="27071-143">Per nascondere la mappa documento quando si visualizza un report</span><span class="sxs-lookup"><span data-stu-id="27071-143">To hide the document map when you view a report</span></span>  
  
1.  <span data-ttu-id="27071-144">In Gestione report selezionare il report in cui è presente la mappa documento.</span><span class="sxs-lookup"><span data-stu-id="27071-144">In Report Manager, browse to the report that has the document map.</span></span>  
  
     <span data-ttu-id="27071-145">Per i report di esempio [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] , l'URL seguente specifica il report denominato Product Catalog.</span><span class="sxs-lookup"><span data-stu-id="27071-145">For example, for the [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] sample reports, the following URL specifies the report named Product Catalog.</span></span>  
  
    ```  
    http://localhost/Reports/Pages/Report.aspx?ItemPath=%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    ```  
  
2.  <span data-ttu-id="27071-146">Copiare il percorso del report nel server.</span><span class="sxs-lookup"><span data-stu-id="27071-146">Copy the report path on the server.</span></span> <span data-ttu-id="27071-147">Nell'esempio il percorso del report è `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span><span class="sxs-lookup"><span data-stu-id="27071-147">In the example, the report path is `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span></span>  
  
3.  <span data-ttu-id="27071-148">Creare un nuovo URL con i tre componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27071-148">Create a new URL with the following three components:</span></span>  
  
    -   <span data-ttu-id="27071-149">Visualizzatore di report nel server di report `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span><span class="sxs-lookup"><span data-stu-id="27071-149">The report viewer on the report server: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span></span>  
  
    -   <span data-ttu-id="27071-150">Nome del report copiato nel passaggio 1, ad esempio `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span><span class="sxs-lookup"><span data-stu-id="27071-150">The name of the report you copied in step 1, for example: `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span></span>  
  
    -   <span data-ttu-id="27071-151">Parametri relativi alle informazioni sul dispositivo che specificano la disattivazione della visualizzazione della mappa documento `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span><span class="sxs-lookup"><span data-stu-id="27071-151">The device information parameters that specify hiding the document map: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span></span>  
  
     <span data-ttu-id="27071-152">L'URL seguente è costituito da questi tre componenti aggiunti nell'ordine in cui vengono elencati.</span><span class="sxs-lookup"><span data-stu-id="27071-152">The following URL consists of these three components appended in the order they are listed.</span></span>  
  
    ```  
    http://localhost/ReportServer/Pages/ReportViewer.aspx?  
    %2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    &rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False  
    ```  
  
     <span data-ttu-id="27071-153">Per usare questo URL, copiarlo e rimuovere tutte le interruzioni di riga.</span><span class="sxs-lookup"><span data-stu-id="27071-153">To use this URL, copy it and remove all line breaks.</span></span>  
  
4.  <span data-ttu-id="27071-154">Incollare l'URL in Gestione report, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="27071-154">Paste the URL in Report Manager, and then press ENTER.</span></span> <span data-ttu-id="27071-155">Verrà avviata l'esecuzione del report e la mappa documento verrà nascosta.</span><span class="sxs-lookup"><span data-stu-id="27071-155">The report runs, and the document map is hidden.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27071-156">Per ulteriori informazioni sul download di report di esempio, vedere [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Generatore report e progettazione report report di esempio](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="27071-156">For more information about downloading sample reports, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
>   
>  <span data-ttu-id="27071-157">Per altre informazioni, vedere "Accesso con URL" nella [documentazione relativa a Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) inclusa nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="27071-157">For more information, see "URL Access" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="27071-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27071-158">See Also</span></span>  
 [<span data-ttu-id="27071-159">Ricerca e visualizzazione di report in Gestione report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="27071-159">Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md)  
  
  
