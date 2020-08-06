---
title: Aggiungere uno snapshot alla cronologia del report (Gestione report) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
helpviewer_keywords:
- report history [Reporting Services], adding snapshots
- historical data [Reporting Services]
- snapshots [Reporting Services], adding report snapshots
- adding snapshots to report history
- report snapshots [Reporting Services], adding
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 84d4c264ab0b82fca2a34e6356b53113d63e6994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630332"
---
# <a name="add-a-snapshot-to-report-history-report-manager"></a><span data-ttu-id="62700-102">Aggiungere uno snapshot alla cronologia del report (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="62700-102">Add a Snapshot to Report History (Report Manager)</span></span>

<span data-ttu-id="62700-103">La cronologia di un report è una raccolta di snapshot del report creati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="62700-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="62700-104">Uno snapshot del report indica un report che include informazioni sul layout e i risultati di query recuperati in un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="62700-104">A report snapshot is a report that contains layout information and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="62700-105">Diversamente dai report su richiesta, per i quali vengono recuperati risultati di query aggiornati quando si seleziona il report, gli snapshot dei report vengono elaborati in base a una pianificazione e quindi salvati nel server di report.</span><span class="sxs-lookup"><span data-stu-id="62700-105">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="62700-106">Quando si seleziona uno snapshot per la visualizzazione, il server di report recupera il report archiviato dal database del server di report e visualizza i dati e il layout del report aggiornati al momento della creazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="62700-106">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
<span data-ttu-id="62700-107">Gli snapshot dei report non vengono salvati in un formato di rendering specifico,</span><span class="sxs-lookup"><span data-stu-id="62700-107">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="62700-108">ma ne viene eseguito il rendering nel formato di visualizzazione finale, ad esempio HTML, solo quando vengono richiesti da un utente o un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62700-108">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="62700-109">Il rendering posticipato rende uno snapshot portabile.</span><span class="sxs-lookup"><span data-stu-id="62700-109">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="62700-110">È possibile eseguire il rendering del report nel formato corretto per il dispositivo o il browser da cui proviene la richiesta.</span><span class="sxs-lookup"><span data-stu-id="62700-110">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
## <a name="to-manually-add-snapshots-to-report-history"></a><span data-ttu-id="62700-111">Per aggiungere manualmente snapshot alla cronologia del report</span><span class="sxs-lookup"><span data-stu-id="62700-111">To manually add snapshots to report history</span></span>

1. <span data-ttu-id="62700-112">In Gestione report passare alla pagina **Contenuto** e posizionare il puntatore del mouse sull'elemento per il quale si vuole visualizzare la cronologia, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="62700-112">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>
  
2. <span data-ttu-id="62700-113">Nel menu a discesa fare clic su **Visualizza cronologia report**.</span><span class="sxs-lookup"><span data-stu-id="62700-113">In the drop-down menu, click **View Report History**.</span></span>  
  
3. <span data-ttu-id="62700-114">Fare clic su **Nuovo snapshot**.</span><span class="sxs-lookup"><span data-stu-id="62700-114">Click **New Snapshot**.</span></span> <span data-ttu-id="62700-115">Verrà creato un nuovo snapshot nella colonna **Data ultima esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="62700-115">A new snapshot is created in the **When Run** column.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="62700-116">A tale scopo la cronologia del report dovrà essere configurata dall'amministratore su **Consenti creazione manuale della cronologia**.</span><span class="sxs-lookup"><span data-stu-id="62700-116">In order to do this, the report history must be configured by the administrator to **Allow history to be created manually**.</span></span> <span data-ttu-id="62700-117">Per altre informazioni, vedere [Limitare la cronologia dei report &#40;Gestione report&#41;](../reports/limit-report-history-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="62700-117">For more information, see [Limit Report History &#40;Report Manager&#41;](../reports/limit-report-history-report-manager.md).</span></span>

4. <span data-ttu-id="62700-118">Fare clic su **Apply**.</span><span class="sxs-lookup"><span data-stu-id="62700-118">Click **Apply**.</span></span>

## <a name="to-automatically-add-all-snapshots-to-report-history"></a><span data-ttu-id="62700-119">Per aggiungere automaticamente tutti gli snapshot alla cronologia del report</span><span class="sxs-lookup"><span data-stu-id="62700-119">To automatically add all snapshots to report history</span></span>  
  
1. <span data-ttu-id="62700-120">Per un report già configurato per essere eseguito come snapshot dell'esecuzione del report, è possibile impostare proprietà aggiuntive per salvare una copia dello snapshot nella cronologia del report ogni volta che lo snapshot viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="62700-120">For a report that is already configured to run as a report execution snapshot, you can set additional properties to save a copy of the snapshot to report history each time the snapshot is refreshed.</span></span>  
  
2. <span data-ttu-id="62700-121">In Gestione report passare alla pagina **Contenuto** , posizionare il puntatore del mouse sull'elemento per il quale si vuole visualizzare la cronologia e quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="62700-121">In Report Manager, navigate to the **Contents** page, hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
3. <span data-ttu-id="62700-122">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="62700-122">In the drop-down menu, click **Manage**.</span></span>  
  
4. <span data-ttu-id="62700-123">Fare clic su **Opzioni snapshot**.</span><span class="sxs-lookup"><span data-stu-id="62700-123">Click **Snapshot Options**.</span></span>  
  
5. <span data-ttu-id="62700-124">Selezionare la casella di controllo **Archivia tutti gli snapshot dell'esecuzione del report nella cronologia**.</span><span class="sxs-lookup"><span data-stu-id="62700-124">Select the check box for **Store all report execution snapshots in history**.</span></span>  
  
6. <span data-ttu-id="62700-125">Fare clic su **Apply**.</span><span class="sxs-lookup"><span data-stu-id="62700-125">Click **Apply**.</span></span>  
  
### <a name="to-automatically-add-snapshots-to-report-history-based-on-a-schedule"></a><span data-ttu-id="62700-126">Per aggiungere automaticamente snapshot alla cronologia del report in base a una pianificazione</span><span class="sxs-lookup"><span data-stu-id="62700-126">To automatically add snapshots to report history based on a schedule</span></span>  
  
1. <span data-ttu-id="62700-127">In Gestione report passare alla pagina **Contenuto** e posizionare il puntatore del mouse sull'elemento per il quale si vuole visualizzare la cronologia, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="62700-127">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
2. <span data-ttu-id="62700-128">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="62700-128">In the drop-down menu, click **Manage**.</span></span>  
  
3. <span data-ttu-id="62700-129">Fare clic su **Opzioni snapshot**.</span><span class="sxs-lookup"><span data-stu-id="62700-129">Click **Snapshot Options**.</span></span>  
  
4. <span data-ttu-id="62700-130">Selezionare la casella di controllo **Usa la pianificazione seguente per aggiungere snapshot alla cronologia del report**.</span><span class="sxs-lookup"><span data-stu-id="62700-130">Select the check box for **Use the following schedule to add snapshots to report history**.</span></span> <span data-ttu-id="62700-131">selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="62700-131">Perform one of the following:</span></span>  
  
    - <span data-ttu-id="62700-132">Selezionare **Pianificazione in base al report**.</span><span class="sxs-lookup"><span data-stu-id="62700-132">Select **Report-specific schedule**.</span></span> <span data-ttu-id="62700-133">Compilare i dettagli della pianificazione, selezionare le date di inizio e fine e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="62700-133">Fill in the schedule details, select the start and end dates for the schedule, and then click **OK**.</span></span>  
  
    - <span data-ttu-id="62700-134">Selezionare **Pianificazione condivisa**.</span><span class="sxs-lookup"><span data-stu-id="62700-134">Select **Shared schedule**.</span></span> <span data-ttu-id="62700-135">Dall'elenco selezionare la pianificazione preferita.</span><span class="sxs-lookup"><span data-stu-id="62700-135">From the list, select the preferred schedule.</span></span>  
  
5. <span data-ttu-id="62700-136">Fare clic su **Apply**.</span><span class="sxs-lookup"><span data-stu-id="62700-136">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62700-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62700-137">See Also</span></span>

- [<span data-ttu-id="62700-138">Configurare le proprietà di esecuzione per un report &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="62700-138">Configure Execution Properties for a Report  &#40;Report Manager&#41;</span></span>](../reports/configure-execution-properties-for-a-report-report-manager.md)
- [<span data-ttu-id="62700-139">Aprire e chiudere un report &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="62700-139">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)
- [<span data-ttu-id="62700-140">Limitare la cronologia dei report &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="62700-140">Limit Report History &#40;Report Manager&#41;</span></span>](../reports/limit-report-history-report-manager.md)
- [<span data-ttu-id="62700-141">Pianificazioni</span><span class="sxs-lookup"><span data-stu-id="62700-141">Schedules</span></span>](../subscriptions/schedules.md)   
- [<span data-ttu-id="62700-142">Gestione report &#40;modalità nativa SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="62700-142">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)