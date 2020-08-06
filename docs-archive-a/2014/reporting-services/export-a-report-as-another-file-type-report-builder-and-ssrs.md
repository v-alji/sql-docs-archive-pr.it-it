---
title: Esportare un report in un altro tipo di file (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b577568b-ecbd-44c3-be88-31dab6fc38a2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 240d3266b7b8c9a445658a9fd21fb9ea18a4c113
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711760"
---
# <a name="export-a-report-as-another-file-type-report-builder-and-ssrs"></a><span data-ttu-id="710fa-102">Esportare un report in un altro tipo di file (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="710fa-102">Export a Report as Another File Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="710fa-103">È possibile eseguire il rendering di un report in un altro formato di file, ad esempio CSV, immagine, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)]o [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], durante la visualizzazione in anteprima in Generatore report o Progettazione report oppure durante la visualizzazione nel server di report.</span><span class="sxs-lookup"><span data-stu-id="710fa-103">You can render a report to another file format, such as CSV, Image, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)], or [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], while previewing your report in Report Builder or Report Designer, or you can render the report while viewing the report on the report server.</span></span> <span data-ttu-id="710fa-104">Il rendering del report in un formato specifico risulta utile quando si desidera salvare immediatamente il report in un altro tipo di file senza pubblicarlo sul server di report oppure quando si desidera visualizzare l'aspetto che avrà il report quando verrà recapitato ai lettori in un formato specifico.</span><span class="sxs-lookup"><span data-stu-id="710fa-104">Rendering the report in a specific format in is helpful when you want to immediately save the report as another file type without publishing the report to the report server or when you want to see how your report design will appear when delivered to your report readers in a specific format.</span></span> <span data-ttu-id="710fa-105">Il rendering del report nel server di report risulta utile quando si impostano sottoscrizioni o si recapitano i report tramite posta elettronica oppure se si desidera salvare un report disponibile nel server di report.</span><span class="sxs-lookup"><span data-stu-id="710fa-105">Rendering the report on the report server is useful when you set up subscriptions or deliver your reports via e-mail, or if you want to save a report that is available on the report server.</span></span> <span data-ttu-id="710fa-106">Per altre informazioni, vedere [Sottoscrizioni e recapito &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="710fa-106">For more information, see [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-export-a-report-as-another-file-type-in-report-builder"></a><span data-ttu-id="710fa-107">Per esportare un report in un altro tipo di file in Generatore report</span><span class="sxs-lookup"><span data-stu-id="710fa-107">To export a report as another file type in Report Builder</span></span>  
  
1.  <span data-ttu-id="710fa-108">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="710fa-108">Preview the report.</span></span>  
  
2.  <span data-ttu-id="710fa-109">Sulla barra multifunzione fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="710fa-109">On the ribbon, click **Export**.</span></span>  
  
3.  <span data-ttu-id="710fa-110">Selezionare il formato che si desidera usare.</span><span class="sxs-lookup"><span data-stu-id="710fa-110">Select the format that you want to use.</span></span>  
  
     <span data-ttu-id="710fa-111">Verrà aperta la finestra di dialogo **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="710fa-111">The **Save As** dialog box opens.</span></span> <span data-ttu-id="710fa-112">Per impostazione predefinita, il nome del file è quello del report esportato.</span><span class="sxs-lookup"><span data-stu-id="710fa-112">By default, the file name is that of the report that you exported.</span></span> <span data-ttu-id="710fa-113">Se lo si desidera, tale nome può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="710fa-113">Optionally, you can change the file name.</span></span>  
  
4.  <span data-ttu-id="710fa-114">Passare al percorso in cui è stato salvato il report esportato e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="710fa-114">Navigate to the location where you saved the exported report and open it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="710fa-115">Se il programma non consente di aprire il report nel formato scelto dal momento che non si dispone di un'applicazione associata a questo tipo di file, verrà richiesto di salvare il report esportato o di trovare un programma online che ne permette l'apertura.</span><span class="sxs-lookup"><span data-stu-id="710fa-115">If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-report-manager"></a><span data-ttu-id="710fa-116">Per esportare un report in un altro tipo di file in Gestione report</span><span class="sxs-lookup"><span data-stu-id="710fa-116">To export a report as another file type in Report Manager</span></span>  
  
1.  <span data-ttu-id="710fa-117">Dalla home page di Gestione report passare al report da \*\*\*\* esportare.</span><span class="sxs-lookup"><span data-stu-id="710fa-117">From the Report Manager **Home** page, navigate to the report that you want to export.</span></span>  
  
2.  <span data-ttu-id="710fa-118">Fare clic sul report.</span><span class="sxs-lookup"><span data-stu-id="710fa-118">Click the report.</span></span>  
  
     <span data-ttu-id="710fa-119">Il report verrà generato.</span><span class="sxs-lookup"><span data-stu-id="710fa-119">The report is generated.</span></span>  
  
3.  <span data-ttu-id="710fa-120">Sulla barra degli strumenti del Visualizzatore report fare clic sulla freccia a discesa **Selezionare un formato** .</span><span class="sxs-lookup"><span data-stu-id="710fa-120">On the Report Viewer toolbar, click the **Select a format** drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="710fa-121">Selezionare il formato che si desidera usare.</span><span class="sxs-lookup"><span data-stu-id="710fa-121">Select the format that you want to use.</span></span>  
  
5.  <span data-ttu-id="710fa-122">Fare clic su **esportare**.</span><span class="sxs-lookup"><span data-stu-id="710fa-122">Click **Export**.</span></span>  
  
     <span data-ttu-id="710fa-123">Verrà visualizzato un messaggio in cui si chiede se si desidera aprire o salvare il file.</span><span class="sxs-lookup"><span data-stu-id="710fa-123">A message appears asking you if you want to open or save the file.</span></span>  
  
6.  <span data-ttu-id="710fa-124">Per visualizzare il report nel formato di esportazione selezionato, fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="710fa-124">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="710fa-125">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="710fa-125">\- or -</span></span>  
  
     <span data-ttu-id="710fa-126">Per salvare immediatamente il report nel formato di esportazione selezionato, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="710fa-126">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="710fa-127">Il report verrà visualizzato o salvato con l'applicazione associata al formato scelto.</span><span class="sxs-lookup"><span data-stu-id="710fa-127">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="710fa-128">Se si fa clic su **Salva**, verrà richiesto di specificare un percorso in cui salvare il report.</span><span class="sxs-lookup"><span data-stu-id="710fa-128">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="710fa-129">**Nota** Se non è possibile aprire il report nel formato selezionato perché non è stato associato alcun programma a questo tipo di file, verrà richiesto di salvare il report esportato o di individuare un programma online con cui aprirlo.</span><span class="sxs-lookup"><span data-stu-id="710fa-129">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-a-sharepoint-library"></a><span data-ttu-id="710fa-130">Per esportare un report in un altro tipo di file in una raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="710fa-130">To export a report as another file type in a SharePoint library</span></span>  
  
1.  <span data-ttu-id="710fa-131">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="710fa-131">Preview the report.</span></span>  
  
2.  <span data-ttu-id="710fa-132">Nella barra degli strumenti, fare clic su **Azioni**, scegliere **Esporta**, quindi selezionare il formato che si desidera usare.</span><span class="sxs-lookup"><span data-stu-id="710fa-132">On the toolbar, click **Actions**, point to **Export**, and then select the format that you want to use.</span></span>  
  
     <span data-ttu-id="710fa-133">Viene visualizzata la finestra di dialogo **Download file** .</span><span class="sxs-lookup"><span data-stu-id="710fa-133">The **File Download** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="710fa-134">Per visualizzare il report nel formato di esportazione selezionato, fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="710fa-134">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="710fa-135">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="710fa-135">\- or -</span></span>  
  
     <span data-ttu-id="710fa-136">Per salvare immediatamente il report nel formato di esportazione selezionato, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="710fa-136">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="710fa-137">Il report verrà visualizzato o salvato con l'applicazione associata al formato scelto.</span><span class="sxs-lookup"><span data-stu-id="710fa-137">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="710fa-138">Se si fa clic su **Salva**, verrà richiesto di specificare un percorso in cui salvare il report.</span><span class="sxs-lookup"><span data-stu-id="710fa-138">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="710fa-139">Se lo si desidera, modificare il nome del file del report esportato.</span><span class="sxs-lookup"><span data-stu-id="710fa-139">Optionally, change the file name of the exported report.</span></span>  
  
     <span data-ttu-id="710fa-140">**Nota** Se non è possibile aprire il report nel formato selezionato perché non è stato associato alcun programma a questo tipo di file, verrà richiesto di salvare il report esportato o di individuare un programma online con cui aprirlo.</span><span class="sxs-lookup"><span data-stu-id="710fa-140">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="710fa-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="710fa-141">See Also</span></span>  
 <span data-ttu-id="710fa-142">[Esportazione di report &#40;Generatore report e SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="710fa-142">[Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="710fa-143">[Paginazione in Reporting Services &#40;Generatore report e SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="710fa-143">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="710fa-144">Funzionalità interattiva per estensioni per il rendering di report differenti &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="710fa-144">Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;</span></span>](report-builder/interactive-functionality-different-report-rendering-extensions.md)  
  
  
