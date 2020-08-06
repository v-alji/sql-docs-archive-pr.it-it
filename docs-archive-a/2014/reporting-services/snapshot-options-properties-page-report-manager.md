---
title: Pagina delle proprietà Opzioni snapshot (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f6641f59-5267-4f57-8957-63b93d1a9679
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3025b23dfe498a92c2ce1d8535229d8d23dfd429
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712692"
---
# <a name="snapshot-options-properties-page-report-manager"></a><span data-ttu-id="27d5e-102">Pagina delle proprietà Opzioni snapshot (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="27d5e-102">Snapshot Options Properties Page (Report Manager)</span></span>
  <span data-ttu-id="27d5e-103">Utilizzare la pagina delle proprietà Opzioni snapshot per pianificare gli snapshot del report da aggiungere alla cronologia del report e impostare limiti per il numero di snapshot del report archiviati nella cronologia.</span><span class="sxs-lookup"><span data-stu-id="27d5e-103">Use the Snapshot Options properties page to schedule report snapshots to be added to report history, and to set limits on the number of report snapshots that are stored in report history.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27d5e-104">Questa funzionalità non è disponibile in ogni edizione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27d5e-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="27d5e-105">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vedere [servizi di database aggiuntivi](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span><span class="sxs-lookup"><span data-stu-id="27d5e-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Additional Database Services](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="27d5e-106">Spostamento</span><span class="sxs-lookup"><span data-stu-id="27d5e-106">Navigation</span></span>  
 <span data-ttu-id="27d5e-107">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="27d5e-107">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-snapshot-options-properties-page-for-a-report"></a><span data-ttu-id="27d5e-108">Per aprire la pagina delle proprietà Opzioni snapshot per un report</span><span class="sxs-lookup"><span data-stu-id="27d5e-108">To open the Snapshot Options properties page for a report</span></span>  
  
1.  <span data-ttu-id="27d5e-109">Aprire Gestione report, quindi individuare il report per il quale si desidera configurare le proprietà dello snapshot del report.</span><span class="sxs-lookup"><span data-stu-id="27d5e-109">Open Report Manager, and locate the report for which you want to configure report snapshot properties.</span></span>  
  
2.  <span data-ttu-id="27d5e-110">Passare con il puntatore del mouse sul report, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="27d5e-110">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="27d5e-111">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="27d5e-111">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="27d5e-112">Verrà visualizzata la pagina delle proprietà Generale per il report.</span><span class="sxs-lookup"><span data-stu-id="27d5e-112">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="27d5e-113">Selezionare la scheda **Opzioni snapshot** .</span><span class="sxs-lookup"><span data-stu-id="27d5e-113">Select the **Snapshot Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="27d5e-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="27d5e-114">Options</span></span>  
 <span data-ttu-id="27d5e-115">**Consenti creazione manuale della cronologia del report**</span><span class="sxs-lookup"><span data-stu-id="27d5e-115">**Allow report history to be created manually**</span></span>  
 <span data-ttu-id="27d5e-116">Selezionare questa casella di controllo per aggiungere snapshot alla cronologia del report, se necessario.</span><span class="sxs-lookup"><span data-stu-id="27d5e-116">Select this check box to add snapshots to report history as needed.</span></span> <span data-ttu-id="27d5e-117">Se si seleziona questa casella di controllo, nella pagina Cronologia verrà visualizzato il pulsante **Nuovo snapshot** .</span><span class="sxs-lookup"><span data-stu-id="27d5e-117">Selecting this check box causes the **New Snapshot** button to appear on the History page.</span></span>  
  
 <span data-ttu-id="27d5e-118">**Archivia tutti gli snapshot dell'esecuzione del report nella cronologia del report**</span><span class="sxs-lookup"><span data-stu-id="27d5e-118">**Store all report execution snapshots in report history**</span></span>  
 <span data-ttu-id="27d5e-119">Selezionare questa casella di controllo per copiare nella cronologia gli snapshot del report generati in base alle proprietà di esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="27d5e-119">Select this check box to copy a report snapshot that you generate based on report execution properties to report history.</span></span> <span data-ttu-id="27d5e-120">È possibile impostare le proprietà di esecuzione del report in modo da eseguire un report da uno snapshot generato.</span><span class="sxs-lookup"><span data-stu-id="27d5e-120">You can set report execution properties to run a report from a generated snapshot.</span></span> <span data-ttu-id="27d5e-121">L'impostazione di questa proprietà della cronologia consente di mantenere una registrazione di tutti gli snapshot del report generati nel tempo tramite l'inserimento di copie degli snapshot nella cronologia del report.</span><span class="sxs-lookup"><span data-stu-id="27d5e-121">By setting this report history property, you can keep a record of all reports snapshots that are generated over time by placing copies of them in report history.</span></span>  
  
 <span data-ttu-id="27d5e-122">**Utilizza la seguente pianificazione per aggiungere snapshot alla cronologia del report**</span><span class="sxs-lookup"><span data-stu-id="27d5e-122">**Use the following schedule to add snapshots to report history**</span></span>  
 <span data-ttu-id="27d5e-123">Selezionare questa casella di controllo per aggiungere gli snapshot alla cronologia del report in base a una pianificazione prestabilita.</span><span class="sxs-lookup"><span data-stu-id="27d5e-123">Select this check box to add snapshots to report history on a scheduled basis.</span></span> <span data-ttu-id="27d5e-124">È possibile creare una pianificazione utilizzata esclusivamente a questo scopo oppure selezionare una pianificazione condivisa predefinita, nel caso sia disponibile una pianificazione pronta appropriata.</span><span class="sxs-lookup"><span data-stu-id="27d5e-124">You can create a schedule that is used exclusively for this purpose, or you can select a predefined shared schedule if one contains the schedule information you want.</span></span>  
  
 <span data-ttu-id="27d5e-125">**Selezionare il numero di snapshot da memorizzare**</span><span class="sxs-lookup"><span data-stu-id="27d5e-125">**Select the number of snapshots to keep**</span></span>  
 <span data-ttu-id="27d5e-126">Selezionare una delle opzioni indicate di seguito per stabilire il numero di report da mantenere nella cronologia.</span><span class="sxs-lookup"><span data-stu-id="27d5e-126">Select from the following options to control the number of reports that are kept in report history.</span></span> <span data-ttu-id="27d5e-127">Le impostazioni di cronologia del report possono variare per ogni report.</span><span class="sxs-lookup"><span data-stu-id="27d5e-127">Report history settings can vary for each report.</span></span>  
  
-   <span data-ttu-id="27d5e-128">Selezionare **Usa impostazione predefinita** per utilizzare l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="27d5e-128">Select **Use default setting** to retain the default setting.</span></span> <span data-ttu-id="27d5e-129">L'amministratore del server di report gestisce un'impostazione globale per l'archiviazione della cronologia dei report.</span><span class="sxs-lookup"><span data-stu-id="27d5e-129">The report server administrator controls a master setting for report history storage.</span></span> <span data-ttu-id="27d5e-130">Se si seleziona questa opzione, il numero di snapshot da mantenere corrisponde a quello impostato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="27d5e-130">If you choose this option, the number of snapshots that are retained is obtained from this master setting.</span></span>  
  
-   <span data-ttu-id="27d5e-131">Selezionare **Nessun limite per il numero di snapshot archiviabili nella cronologia** per conservare tutti gli snapshot della cronologia del report.</span><span class="sxs-lookup"><span data-stu-id="27d5e-131">Select **Keep an unlimited number of snapshots in report history** to retain all report history snapshots.</span></span> <span data-ttu-id="27d5e-132">Per mantenere ridotte le dimensioni della cronologia del report sarà necessario eliminare manualmente gli snapshot non più necessari.</span><span class="sxs-lookup"><span data-stu-id="27d5e-132">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
-   <span data-ttu-id="27d5e-133">Selezionare **Numero massimo di copie della cronologia** per conservare un numero specifico di snapshot.</span><span class="sxs-lookup"><span data-stu-id="27d5e-133">Select **Limit the copies of report history** to retain a set number of snapshots.</span></span> <span data-ttu-id="27d5e-134">Raggiunto tale limite, le copie meno recenti vengono rimosse dalla cronologia del report per fare spazio alle copie più recenti.</span><span class="sxs-lookup"><span data-stu-id="27d5e-134">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="27d5e-135">La cronologia del report viene archiviata nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="27d5e-135">Report history is stored in the report server database.</span></span> <span data-ttu-id="27d5e-136">Se vi sono report di grandi dimensioni o numerosi report per i quali si desidera conservare la cronologia, limitare la quantità di cronologia del report per semplificare la gestione dei requisiti di spazio su disco del database del server di report.</span><span class="sxs-lookup"><span data-stu-id="27d5e-136">If you have large reports or numerous reports for which you want to maintain history, consider limiting the amount of report history to help manage the disk space requirements of the report server database.</span></span>  
  
 <span data-ttu-id="27d5e-137">**Applica**</span><span class="sxs-lookup"><span data-stu-id="27d5e-137">**Apply**</span></span>  
 <span data-ttu-id="27d5e-138">Fare clic per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="27d5e-138">Click to save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d5e-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27d5e-139">See Also</span></span>  
 <span data-ttu-id="27d5e-140">[Aggiungere uno snapshot alla cronologia del report &#40;Gestione report&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="27d5e-140">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="27d5e-141">[Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="27d5e-141">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="27d5e-142">[Creare, modificare ed eliminare snapshot nella cronologia dei report](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span><span class="sxs-lookup"><span data-stu-id="27d5e-142">[Create, Modify, and Delete Snapshots in Report History](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span></span>  
 [<span data-ttu-id="27d5e-143">Guida sensibile al contesto di Gestione report</span><span class="sxs-lookup"><span data-stu-id="27d5e-143">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
