---
title: Visualizzazione Anteprima | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.previewview.f1
helpviewer_keywords:
- Preview view [Reporting Services]
ms.assetid: 108255d1-5be8-47c1-80f3-1f2a055e4d02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1ff7c59c3ac5143d4f4103edea1a5ee309046547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716020"
---
# <a name="preview-view"></a><span data-ttu-id="54ffc-102">Visualizzazione Anteprima</span><span class="sxs-lookup"><span data-stu-id="54ffc-102">Preview View</span></span>
  <span data-ttu-id="54ffc-103">Utilizzare la visualizzazione **Anteprima** per visualizzare il report di cui è stato eseguito il rendering.</span><span class="sxs-lookup"><span data-stu-id="54ffc-103">Use **Preview** view to display the rendered report.</span></span> <span data-ttu-id="54ffc-104">Quando si visualizza l'anteprima di un report, Progettazione report esegue il report localmente e lo visualizza nella visualizzazione Anteprima.</span><span class="sxs-lookup"><span data-stu-id="54ffc-104">When a report is previewed, Report Designer runs the report locally and displays it in the Preview view.</span></span> <span data-ttu-id="54ffc-105">Nella modalità di anteprima, il report viene completamente elaborato.</span><span class="sxs-lookup"><span data-stu-id="54ffc-105">In preview mode, the report is processed in full.</span></span> <span data-ttu-id="54ffc-106">Se la query del report è complessa o il report contiene una grande quantità di dati, la visualizzazione dell'anteprima potrebbe impiegare alcuni minuti la prima volta.</span><span class="sxs-lookup"><span data-stu-id="54ffc-106">If the report has a complex query or has a large amount of data, preview might take several minutes to complete the first time you view it.</span></span> <span data-ttu-id="54ffc-107">Per le modifiche successive che riguardano solo il formato del report, l'anteprima utilizza i dati nella cache.</span><span class="sxs-lookup"><span data-stu-id="54ffc-107">For subsequent changes that affect only the format of the report, preview uses cached data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="54ffc-108">Quando [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] viene eseguito come RemoteApp, i report non possono essere visualizzati nella vista **Anteprima** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54ffc-108">When [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] is run as a RemoteApp, reports cannot be displayed in **Preview** view in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="54ffc-109">L'accesso ai programmi di RemoteApp può essere effettuato in modalità remota tramite Servizi Desktop remoto.</span><span class="sxs-lookup"><span data-stu-id="54ffc-109">RemoteApp programs are programs that are accessed remotely through Remote Desktop Services.</span></span> <span data-ttu-id="54ffc-110">Per ulteriori informazioni, vedere [Guida dettagliata a RemoteApp di Servizi terminal in Windows Server 2008](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="54ffc-110">For more information, see [TS RemoteApp Step-by-Step Guide](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span></span>  
  
## <a name="options"></a><span data-ttu-id="54ffc-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="54ffc-111">Options</span></span>  
 <span data-ttu-id="54ffc-112">Utilizzare la barra degli strumenti per gestire le funzionalità di anteprima.</span><span class="sxs-lookup"><span data-stu-id="54ffc-112">Use the toolbar to manage preview functions.</span></span>  
  
 <span data-ttu-id="54ffc-113">**Mostra/Nascondi mappa documento**</span><span class="sxs-lookup"><span data-stu-id="54ffc-113">**Show or Hide Document Map**</span></span>  
 <span data-ttu-id="54ffc-114">Selezionare questa opzione per mostrare o nascondere la mappa del documento, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="54ffc-114">Choose this option to show or hide the document map if one exists.</span></span>  
  
 <span data-ttu-id="54ffc-115">**Mostra/Nascondi parametri**</span><span class="sxs-lookup"><span data-stu-id="54ffc-115">**Show or Hide Parameter Area**</span></span>  
 <span data-ttu-id="54ffc-116">Selezionare questa opzione per mostrare o nascondere le caselle dei parametri per i report con parametri.</span><span class="sxs-lookup"><span data-stu-id="54ffc-116">Choose this option to show or hide the parameters boxes for reports with parameters.</span></span>  
  
 <span data-ttu-id="54ffc-117">**Prima pagina**</span><span class="sxs-lookup"><span data-stu-id="54ffc-117">**First Page**</span></span>  
 <span data-ttu-id="54ffc-118">Selezionare questa opzione per passare alla prima pagina del report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-118">Choose this option to go to the first page of the report.</span></span>  
  
 <span data-ttu-id="54ffc-119">**Pagina precedente**</span><span class="sxs-lookup"><span data-stu-id="54ffc-119">**Previous Page**</span></span>  
 <span data-ttu-id="54ffc-120">Selezionare questa opzione per passare alla pagina precedente del report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-120">Choose this option to go to the previous page of the report.</span></span>  
  
 <span data-ttu-id="54ffc-121">**Pagina corrente**</span><span class="sxs-lookup"><span data-stu-id="54ffc-121">**Current Page**</span></span>  
 <span data-ttu-id="54ffc-122">Consente di visualizzare la pagina corrente del report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-122">Displays the current page of the report.</span></span>  
  
 <span data-ttu-id="54ffc-123">**Totale pagine**</span><span class="sxs-lookup"><span data-stu-id="54ffc-123">**Total Pages**</span></span>  
 <span data-ttu-id="54ffc-124">Consente di visualizzare il numero totale di pagine del report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-124">Displays the total number of pages in the report.</span></span>  
  
 <span data-ttu-id="54ffc-125">**Pagina successiva**</span><span class="sxs-lookup"><span data-stu-id="54ffc-125">**Next Page**</span></span>  
 <span data-ttu-id="54ffc-126">Selezionare questa opzione per passare alla pagina successiva del report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-126">Choose this option to go to the next page of the report.</span></span>  
  
 <span data-ttu-id="54ffc-127">**Ultima pagina**</span><span class="sxs-lookup"><span data-stu-id="54ffc-127">**Last Page**</span></span>  
 <span data-ttu-id="54ffc-128">Selezionare questa opzione per passare all'ultima pagina del report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-128">Choose this option to go to the last page of the report.</span></span>  
  
 <span data-ttu-id="54ffc-129">**Torna al report padre**</span><span class="sxs-lookup"><span data-stu-id="54ffc-129">**Back to Parent Report**</span></span>  
 <span data-ttu-id="54ffc-130">Selezionare questa opzione per passare al report padre.</span><span class="sxs-lookup"><span data-stu-id="54ffc-130">Choose this option to go to the parent report.</span></span> <span data-ttu-id="54ffc-131">Utilizzare questa opzione per passare ai report drill-through.</span><span class="sxs-lookup"><span data-stu-id="54ffc-131">This option is used to navigate drillthrough reports.</span></span>  
  
 <span data-ttu-id="54ffc-132">**Arresta rendering**</span><span class="sxs-lookup"><span data-stu-id="54ffc-132">**Stop Rendering**</span></span>  
 <span data-ttu-id="54ffc-133">Selezionare questa opzione per arrestare il processo di rendering.</span><span class="sxs-lookup"><span data-stu-id="54ffc-133">Choose this option to stop the rendering process.</span></span>  
  
 <span data-ttu-id="54ffc-134">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="54ffc-134">**Refresh**</span></span>  
 <span data-ttu-id="54ffc-135">Scegliere questa opzione per aggiornare la cache dei dati ed eseguire nuovamente il report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-135">Choose this option to refresh the data cache and run the report again.</span></span>  
  
 <span data-ttu-id="54ffc-136">**Stampa**</span><span class="sxs-lookup"><span data-stu-id="54ffc-136">**Print**</span></span>  
 <span data-ttu-id="54ffc-137">Selezionare questa opzione per stampare il report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-137">Choose this option to print the report.</span></span>  
  
 <span data-ttu-id="54ffc-138">**Layout di stampa**</span><span class="sxs-lookup"><span data-stu-id="54ffc-138">**Print Layout**</span></span>  
 <span data-ttu-id="54ffc-139">Selezionare questa opzione per alternare la visualizzazione del report in anteprima alla visualizzazione del report così come verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="54ffc-139">Choose this option to toggle between the preview report and the view of the report as it will appear on the printed page.</span></span>  
  
 <span data-ttu-id="54ffc-140">**Imposta pagina**</span><span class="sxs-lookup"><span data-stu-id="54ffc-140">**Page Setup**</span></span>  
 <span data-ttu-id="54ffc-141">Selezionare questa opzione per modificare in base alle proprie esigenze le proprietà della pagina e di stampa.</span><span class="sxs-lookup"><span data-stu-id="54ffc-141">Choose this option to conveniently change page and print properties.</span></span> <span data-ttu-id="54ffc-142">Utilizzare l'opzione Layout di stampa per visualizzare le modifiche prima di eseguire la stampa.</span><span class="sxs-lookup"><span data-stu-id="54ffc-142">Use Print Layout to view changes before printing.</span></span>  
  
 <span data-ttu-id="54ffc-143">**Export**</span><span class="sxs-lookup"><span data-stu-id="54ffc-143">**Export**</span></span>  
 <span data-ttu-id="54ffc-144">Scegliere questa opzione per esportare in un formato specifico il report di cui è stato eseguito il rendering.</span><span class="sxs-lookup"><span data-stu-id="54ffc-144">Choose this option to export the rendered report in a specific format.</span></span>  
  
 <span data-ttu-id="54ffc-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="54ffc-145">**Zoom**</span></span>  
 <span data-ttu-id="54ffc-146">Consente di selezionare un fattore di zoom per ingrandire o ridurre il report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-146">Select a zoom factor to zoom in or out on the report.</span></span>  
  
 <span data-ttu-id="54ffc-147">**Testo di ricerca**</span><span class="sxs-lookup"><span data-stu-id="54ffc-147">**Search Text**</span></span>  
 <span data-ttu-id="54ffc-148">Consente di digitare il testo da cercare nel report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-148">Type text to search for a match within the report.</span></span> <span data-ttu-id="54ffc-149">Non è possibile utilizzare operatori di ricerca.</span><span class="sxs-lookup"><span data-stu-id="54ffc-149">You cannot use search operators.</span></span> <span data-ttu-id="54ffc-150">Fare clic su **Trova** per cercare la prima occorrenza.</span><span class="sxs-lookup"><span data-stu-id="54ffc-150">Click **Find** to search for the first instance.</span></span>  
  
 <span data-ttu-id="54ffc-151">**Trovare**</span><span class="sxs-lookup"><span data-stu-id="54ffc-151">**Find**</span></span>  
 <span data-ttu-id="54ffc-152">Selezionare questa opzione per iniziare la ricerca del testo desiderato nel report.</span><span class="sxs-lookup"><span data-stu-id="54ffc-152">Choose this option to begin searching the report for the search text.</span></span>  
  
 <span data-ttu-id="54ffc-153">**Trova successivo**</span><span class="sxs-lookup"><span data-stu-id="54ffc-153">**Find Next**</span></span>  
 <span data-ttu-id="54ffc-154">Selezionare questa opzione per cercare l'occorrenza successiva del testo desiderato.</span><span class="sxs-lookup"><span data-stu-id="54ffc-154">Choose this option to search for the next instance of the search text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ffc-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54ffc-155">See Also</span></span>  
 <span data-ttu-id="54ffc-156">[Visualizzazione in anteprima di report](../reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="54ffc-156">[Previewing Reports](../reports/previewing-reports.md) </span></span>  
 [<span data-ttu-id="54ffc-157">Guida sensibile al contesto di Progettazione report</span><span class="sxs-lookup"><span data-stu-id="54ffc-157">Report Designer F1 Help</span></span>](report-designer-f1-help.md)  
  
  
