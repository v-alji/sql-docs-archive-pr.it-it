---
title: Stampare un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b96936c9-c387-41a9-8c19-6eb325769ffd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe029019cdf9739153256db399cfa1426d3ba632
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626536"
---
# <a name="print-a-report-report-builder-and-ssrs"></a><span data-ttu-id="91db1-102">Stampare un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="91db1-102">Print a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="91db1-103">Dopo avere salvato un report in un server di report, è possibile visualizzarlo e stamparlo da un browser, da Gestione report o da qualsiasi applicazione utilizzata per visualizzare un report esportato.</span><span class="sxs-lookup"><span data-stu-id="91db1-103">After you save a report to a report server, you can view and print the report from a browser, Report Manager, or any application that you use to view an exported report.</span></span> <span data-ttu-id="91db1-104">Prima di salvare un report, è possibile stamparlo durante l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="91db1-104">Before saving a report, you can print it when you preview it.</span></span>  
  
 <span data-ttu-id="91db1-105">Quando si stampa un report, è possibile specificare le dimensioni della pagina da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="91db1-105">When you print a report, you can specify the size of the paper to use.</span></span> <span data-ttu-id="91db1-106">Le dimensioni del foglio determinano il numero di pagine del report e la quantità di dati contenuta in ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="91db1-106">The size of the paper determines the number of pages in a report and which report data fits on each page.</span></span> <span data-ttu-id="91db1-107">Il formato della carta influisce solo sui report visualizzati con i renderer di interruzioni di pagina manuali: PDF, immagine e stampa.</span><span class="sxs-lookup"><span data-stu-id="91db1-107">Paper size affects only reports that are rendered with hard page-break renders: PDF, Image, and Print.</span></span> <span data-ttu-id="91db1-108">L'impostazione del formato della carta non influisce su altri renderer.</span><span class="sxs-lookup"><span data-stu-id="91db1-108">Setting the paper size has no effect on other renderers.</span></span> <span data-ttu-id="91db1-109">Per altre informazioni, vedere [Tipi di rendering  &#40;Generatore report e SSRS &#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="91db1-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="91db1-110">È possibile esportare un report in un renderer di interruzione di pagina manuale oppure fare clic sul pulsante Stampa per stampare una copia del report dalla barra degli strumenti del visualizzatore di report in Gestione report o in un'anteprima in Generatore report.</span><span class="sxs-lookup"><span data-stu-id="91db1-110">From the report viewer toolbar in Report Manager or in preview in Report Builder, you can export a report to a hard page-break renderer or click the Print button to print a copy of the report.</span></span> <span data-ttu-id="91db1-111">Potrebbe essere necessario impostare il formato della carta o altre proprietà di impostazione pagina.</span><span class="sxs-lookup"><span data-stu-id="91db1-111">You might need to set the paper size or other page setup properties.</span></span> <span data-ttu-id="91db1-112">Usare la finestra di dialogo **Proprietà report** per modificare le proprietà di impostazione della pagina, tra cui il formato della carta.</span><span class="sxs-lookup"><span data-stu-id="91db1-112">Use the **Report Properties** dialog box to change page setup properties, including paper size.</span></span>  
  
 <span data-ttu-id="91db1-113">È possibile specificare i margini della pagina di stampa in due modi diversi, ovvero in modalità di progettazione e in modalità di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91db1-113">You can specify print page margins in two different locations: in design mode and in run mode.</span></span>  
  
-   <span data-ttu-id="91db1-114">**Modalità progettazione.**</span><span class="sxs-lookup"><span data-stu-id="91db1-114">**Design mode.**</span></span> <span data-ttu-id="91db1-115">Quando si impostano i margini della pagina in modalità di progettazione, queste impostazioni vengono salvate nella definizione del report quando si salva il report.</span><span class="sxs-lookup"><span data-stu-id="91db1-115">When you set page margins in design mode, these settings are saved in the report definition when you save the report.</span></span>  
  
-   <span data-ttu-id="91db1-116">**Modalità di esecuzione.**</span><span class="sxs-lookup"><span data-stu-id="91db1-116">**Run mode.**</span></span> <span data-ttu-id="91db1-117">Quando si impostano i margini della pagina in modalità di esecuzione, queste informazioni non vengono salvate nella definizione del report.</span><span class="sxs-lookup"><span data-stu-id="91db1-117">When you set page margins in run mode, this information is not saved in the report definition.</span></span> <span data-ttu-id="91db1-118">La volta successiva che si stampa il report, verranno utilizzate le impostazioni della definizione del report, a meno che non si indichino nuovamente i margini di stampa.</span><span class="sxs-lookup"><span data-stu-id="91db1-118">The next time you print the report, you will get the settings from the report definition, unless you indicate your print margins again.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91db1-119">I margini di stampa non vengono visualizzati nelle modalità di progettazione o esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91db1-119">Print margins are not displayed in design or run modes.</span></span> <span data-ttu-id="91db1-120">Non c'è relazione tra l'area dell'area di progettazione e l'area di stampa del report.</span><span class="sxs-lookup"><span data-stu-id="91db1-120">There is no relationship between the design surface area and the print area of your report.</span></span> <span data-ttu-id="91db1-121">Per vedere i margini di stampa, in modalità di esecuzione fare clic su Layout di stampa nella scheda **Esegui** sulla barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="91db1-121">To see print margins, in run mode, click Print Layout on the **Run** tab on the Ribbon.</span></span>  
  
 <span data-ttu-id="91db1-122">Per altre informazioni sul paginazione dei report, vedere [Paginazione in Reporting Services &#40;Generatore report e SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="91db1-122">For more information about report paging, see [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-print-a-report-in-report-builder"></a><span data-ttu-id="91db1-123">Per stampare un report in Generatore report</span><span class="sxs-lookup"><span data-stu-id="91db1-123">To print a report in Report Builder</span></span>  
  
1.  <span data-ttu-id="91db1-124">Aprire un report.</span><span class="sxs-lookup"><span data-stu-id="91db1-124">Open a report.</span></span>  
  
2.  <span data-ttu-id="91db1-125">Nella scheda Home fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="91db1-125">On the Home tab, click **Run**.</span></span>  
  
3.  <span data-ttu-id="91db1-126">(Facoltativo) Fare clic su **Layout di stampa** per visualizzare un'anteprima del report prima di stamparlo.</span><span class="sxs-lookup"><span data-stu-id="91db1-126">(optional) Click **Print Layout** to see how the report will look when it is printed.</span></span>  
  
4.  <span data-ttu-id="91db1-127">(Facoltativo) Fare clic su **Imposta pagina** per impostare la carta, l'orientamento e i margini.</span><span class="sxs-lookup"><span data-stu-id="91db1-127">(optional) Click **Page Setup** to set paper, orientation, and margins.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91db1-128">I valori predefiniti di tali voci provengono dalle proprietà del report impostate in visualizzazione Progettazione.</span><span class="sxs-lookup"><span data-stu-id="91db1-128">The default values for these come from the report properties, which are set in Design view.</span></span> <span data-ttu-id="91db1-129">I valori impostati nella finestra di dialogo **Imposta pagina** sono validi solo per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="91db1-129">The values you set here in the **Page Setup** dialog box are for this session only.</span></span> <span data-ttu-id="91db1-130">Quando il report viene chiuso e poi riaperto, verranno ripristinati i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="91db1-130">When you close this report and reopen it, it will have the default values again.</span></span>  
  
5.  <span data-ttu-id="91db1-131">Fare clic su **Stampa**.</span><span class="sxs-lookup"><span data-stu-id="91db1-131">Click **Print**.</span></span>  
  
6.  <span data-ttu-id="91db1-132">Nella finestra di dialogo **Stampa** selezionare una stampante e specificare altre opzioni di stampa.</span><span class="sxs-lookup"><span data-stu-id="91db1-132">In the **Print** dialog box, select a printer and specify other printing options.</span></span>  
  
### <a name="to-print-a-report-from-a-web-browser-application"></a><span data-ttu-id="91db1-133">Per stampare un report da un'applicazione browser</span><span class="sxs-lookup"><span data-stu-id="91db1-133">To print a report from a Web browser application</span></span>  
  
1.  <span data-ttu-id="91db1-134">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="91db1-134">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="91db1-135">In Gestione report passare al report che si desidera stampare,</span><span class="sxs-lookup"><span data-stu-id="91db1-135">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="91db1-136">quindi aprirlo.</span><span class="sxs-lookup"><span data-stu-id="91db1-136">Open the report.</span></span>  
  
3.  <span data-ttu-id="91db1-137">Fare clic su **Stampa**sulla barra degli strumenti nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="91db1-137">On the toolbar at the top of the report, click **Print**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91db1-138">Quando si stampa per la prima volta un report in formato HTML, per il server di report viene richiesta l'installazione di un controllo ActiveX utilizzato per la stampa.</span><span class="sxs-lookup"><span data-stu-id="91db1-138">The first time you print an HTML report, the report server prompts you to install an ActiveX control used for printing.</span></span> <span data-ttu-id="91db1-139">È necessario installare e configurare il controllo per poter stampare.</span><span class="sxs-lookup"><span data-stu-id="91db1-139">You must install and configure the control to print.</span></span>  
  
4.  <span data-ttu-id="91db1-140">Nella finestra di dialogo **Stampa** selezionare una stampante e fare clic su **Stampa**.</span><span class="sxs-lookup"><span data-stu-id="91db1-140">In the **Print** dialog box, select a printer, and then click **Prin**t.</span></span>  
  
### <a name="to-print-a-report-from-other-applications"></a><span data-ttu-id="91db1-141">Per stampare un report da altre applicazioni</span><span class="sxs-lookup"><span data-stu-id="91db1-141">To print a report from other applications</span></span>  
  
1.  <span data-ttu-id="91db1-142">In Gestione report passare al report che si desidera stampare,</span><span class="sxs-lookup"><span data-stu-id="91db1-142">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="91db1-143">quindi aprirlo.</span><span class="sxs-lookup"><span data-stu-id="91db1-143">Open the report.</span></span>  
  
2.  <span data-ttu-id="91db1-144">Selezionare un formato di rendering sulla barra degli strumenti nella parte superiore del report, quindi fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="91db1-144">On the toolbar at the top of the report, select a rendering format, and then click **Export**.</span></span> <span data-ttu-id="91db1-145">Il report verrà aperto nell'applicazione di visualizzazione corrispondente al formato di rendering selezionato.</span><span class="sxs-lookup"><span data-stu-id="91db1-145">The report opens in a viewer application that corresponds to the rendering format.</span></span>  
  
     <span data-ttu-id="91db1-146">Ad esempio, se si seleziona il formato PDF, il report verrà aperto in Adobe Acrobat Reader.</span><span class="sxs-lookup"><span data-stu-id="91db1-146">For example, if you select PDF, the report opens in Adobe Acrobat Reader.</span></span>  
  
3.  <span data-ttu-id="91db1-147">Scegliere **Stampa** dal menu **File**del programma in uso.</span><span class="sxs-lookup"><span data-stu-id="91db1-147">On the **File** menu in that program, click **Print**.</span></span>  
  
### <a name="to-change-paper-size"></a><span data-ttu-id="91db1-148">Per modificare il formato della carta</span><span class="sxs-lookup"><span data-stu-id="91db1-148">To change paper size</span></span>  
  
1.  <span data-ttu-id="91db1-149">Fare clic con il pulsante destro del mouse al di fuori del corpo del report e scegliere **Proprietà report**.</span><span class="sxs-lookup"><span data-stu-id="91db1-149">Right-click outside of the report body and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="91db1-150">Selezionare un valore dall'elenco **Formato carta**in **Imposta pagina** .</span><span class="sxs-lookup"><span data-stu-id="91db1-150">In **Page Setup**, select a value from the **Paper Size** list.</span></span> <span data-ttu-id="91db1-151">Verranno popolate le proprietà **Larghezza** e **Altezza** .</span><span class="sxs-lookup"><span data-stu-id="91db1-151">Each option populates the **Width** and **Height** properties.</span></span> <span data-ttu-id="91db1-152">È anche possibile specificare un formato personalizzato digitando valori numerici nelle caselle **Larghezza** e **Altezza** .</span><span class="sxs-lookup"><span data-stu-id="91db1-152">You can also specify a custom size by typing numeric values in the **Width** and **Height** boxes.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="91db1-153">I valori relativi alle dimensioni sono calcolati in base all'unità di misura predefinita specificata dall'utente nelle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="91db1-153">Size values have a default unit based on the user's locale settings.</span></span> <span data-ttu-id="91db1-154">Per specificare un'unità di misura diversa, digitare un identificatore di unità fisica, ad esempio cm, mm, pt o pc, dopo il valore numerico.</span><span class="sxs-lookup"><span data-stu-id="91db1-154">To designate a different unit, type a physical unit designator such as cm, mm, pt, or pc after the numeric value.</span></span>  
  
### <a name="to-set-page-margins-in-design-mode"></a><span data-ttu-id="91db1-155">Per impostare i margini della pagina in modalità di progettazione</span><span class="sxs-lookup"><span data-stu-id="91db1-155">To set page margins in design mode</span></span>  
  
-   <span data-ttu-id="91db1-156">Fare clic con il pulsante destro del mouse sull'area blu intorno all'area di progettazione, scegliere **Proprietà report**, quindi fare clic sulla pagina **Imposta pagina** .</span><span class="sxs-lookup"><span data-stu-id="91db1-156">Right-click the blue area around the design surface, click **Report Properties**, and then click the **Page Setup** page.</span></span>  
  
### <a name="to-set-page-margins-in-run-mode"></a><span data-ttu-id="91db1-157">Per impostare i margini della pagina in modalità di esecuzione</span><span class="sxs-lookup"><span data-stu-id="91db1-157">To set page margins in run mode</span></span>  
  
-   <span data-ttu-id="91db1-158">Fare clic su **Imposta pagina** nella scheda **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="91db1-158">Click **Page Setup** on the **Run** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91db1-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91db1-159">See Also</span></span>  
 <span data-ttu-id="91db1-160">[Stampa di report &#40;Generatore report e SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91db1-160">[Print Reports &#40;Report Builder and SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91db1-161">[Esportazione di report &#40;Generatore report e SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91db1-161">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91db1-162">[Finestra di dialogo Proprietà report, Imposta pagina &#40;Generatore report&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="91db1-162">[Report Properties Dialog Box, Page Setup &#40;Report Builder&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span></span>  
 [<span data-ttu-id="91db1-163">Visualizzazione di progettazione report &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="91db1-163">Report Design View &#40;Report Builder&#41;</span></span>](report-design-view-report-builder.md)  
  
  
