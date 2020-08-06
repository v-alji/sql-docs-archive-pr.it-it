---
title: Pagina Cronologia report (Gestione report) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services-native
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 4070be8c1d6b0633131e96c665d4551c1b676a9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628350"
---
# <a name="report-history-page-report-manager"></a><span data-ttu-id="da66a-102">Pagina Cronologia report (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="da66a-102">Report History Page (Report Manager)</span></span>

<span data-ttu-id="da66a-103">La pagina Cronologia report consente di visualizzare gli snapshot del report generati e archiviati nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="da66a-103">Use the Report History page to view report snapshots that are generated and stored over time.</span></span> <span data-ttu-id="da66a-104">A seconda delle opzioni impostate nel server di report, è possibile che la cronologia del report includa solo gli snapshot più recenti.</span><span class="sxs-lookup"><span data-stu-id="da66a-104">Depending on options that are set on the report server, report history may contain only the more recent snapshots.</span></span>  
  

<span data-ttu-id="da66a-105">La cronologia del report viene sempre visualizzata nel contesto del report a cui si riferisce,</span><span class="sxs-lookup"><span data-stu-id="da66a-105">Report history is always viewed within the context of the report from which it originates.</span></span> <span data-ttu-id="da66a-106">ovvero non è possibile visualizzare la cronologia di tutti i report in un server di report in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="da66a-106">You cannot view the history of all reports on a report server in one place.</span></span>  
  
<span data-ttu-id="da66a-107">Per generare la cronologia, è necessario che il report possa essere eseguito in modo automatico, ovvero il report deve utilizzare credenziali archiviate e i report con parametri devono includere valori predefiniti per tutti i parametri.</span><span class="sxs-lookup"><span data-stu-id="da66a-107">To generate report history, the report must be able to run unattended (that is, it must use stored credentials; parameterized reports must contain default parameter values for all parameters).</span></span> <span data-ttu-id="da66a-108">È possibile generare la cronologia del report manualmente o come operazione pianificata.</span><span class="sxs-lookup"><span data-stu-id="da66a-108">Report history can be generated manually or as a scheduled operation.</span></span> <span data-ttu-id="da66a-109">Le proprietà della cronologia del report determinano i metodi di creazione consentiti.</span><span class="sxs-lookup"><span data-stu-id="da66a-109">History properties on the report determine the ways in which report history can be created.</span></span>  
  
<span data-ttu-id="da66a-110">È possibile fare clic su uno snapshot della cronologia del report per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="da66a-110">You can click a report history snapshot to view it.</span></span> <span data-ttu-id="da66a-111">L'unico elemento distintivo degli snapshot visualizzati nella cronologia del report è rappresentato dalla data e ora di creazione.</span><span class="sxs-lookup"><span data-stu-id="da66a-111">Snapshots that appear in report history are distinguished only by the date and time at which they were created.</span></span> <span data-ttu-id="da66a-112">Non sono disponibili indicatori visivi per distinguere gli snapshot generati tramite una pianificazione o un'operazione manuale.</span><span class="sxs-lookup"><span data-stu-id="da66a-112">There is no visual indication to distinguish whether a snapshot was generated in response to a schedule or a manual operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da66a-113">Questa funzionalità non è disponibile in ogni edizione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da66a-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="da66a-114">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="da66a-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="da66a-115">Spostamento</span><span class="sxs-lookup"><span data-stu-id="da66a-115">Navigation</span></span>  
 <span data-ttu-id="da66a-116">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="da66a-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-report-history-page"></a><span data-ttu-id="da66a-117">Per aprire la pagina Cronologia report</span><span class="sxs-lookup"><span data-stu-id="da66a-117">To open the Report History page</span></span>  
  
1.  <span data-ttu-id="da66a-118">Aprire Gestione report e individuare il report per il quale si desidera visualizzare gli snapshot del report.</span><span class="sxs-lookup"><span data-stu-id="da66a-118">Open Report Manager, and locate the report for which you want to view report snapshots.</span></span>  
  
2.  <span data-ttu-id="da66a-119">Passare con il puntatore del mouse sul report, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="da66a-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="da66a-120">Nel menu a discesa fare clic su **Visualizza cronologia report**.</span><span class="sxs-lookup"><span data-stu-id="da66a-120">In the drop-down menu, click **View Report History**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="da66a-121">Opzioni</span><span class="sxs-lookup"><span data-stu-id="da66a-121">Options</span></span>  
 <span data-ttu-id="da66a-122">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="da66a-122">**Delete**</span></span>  
 <span data-ttu-id="da66a-123">Fare clic per eliminare uno o più snapshot.</span><span class="sxs-lookup"><span data-stu-id="da66a-123">Click to delete one or more snapshots.</span></span> <span data-ttu-id="da66a-124">Prima di fare clic su **Elimina**selezionare la casella di controllo accanto allo snapshot che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="da66a-124">Before clicking **Delete**, select the check box next to the snapshot that you want to delete.</span></span>  
  
 <span data-ttu-id="da66a-125">**Nuovo snapshot**</span><span class="sxs-lookup"><span data-stu-id="da66a-125">**New Snapshot**</span></span>  
 <span data-ttu-id="da66a-126">Fare clic per aggiungere uno snapshot alla cronologia del report.</span><span class="sxs-lookup"><span data-stu-id="da66a-126">Click to add a snapshot to report history.</span></span> <span data-ttu-id="da66a-127">Questo pulsante è disponibile se si seleziona l'opzione **Consenti creazione manuale della cronologia** nella pagina delle proprietà Cronologia del report.</span><span class="sxs-lookup"><span data-stu-id="da66a-127">This button is available when you choose the option **Allow history to be created manually** on the History properties page of the report.</span></span>  
  
 <span data-ttu-id="da66a-128">**Ultima esecuzione**</span><span class="sxs-lookup"><span data-stu-id="da66a-128">**Last Run**</span></span>  
 <span data-ttu-id="da66a-129">Visualizza data e ora di creazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="da66a-129">Displays the date and time at which the snapshot was created.</span></span> <span data-ttu-id="da66a-130">Fare clic su una descrizione per visualizzare uno snapshot specifico.</span><span class="sxs-lookup"><span data-stu-id="da66a-130">Click a description to view a particular snapshot.</span></span>  
  
 <span data-ttu-id="da66a-131">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="da66a-131">**Size**</span></span>  
 <span data-ttu-id="da66a-132">Visualizza la dimensione della definizione e dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="da66a-132">Displays the size of the report definition plus the data in the report.</span></span> <span data-ttu-id="da66a-133">Questo valore indica lo spazio occupato nel database del server di report dalla definizione e dai dati del report.</span><span class="sxs-lookup"><span data-stu-id="da66a-133">This value indicates how much space in the report server database is used by the report definition and data.</span></span> <span data-ttu-id="da66a-134">Le dimensioni del report visualizzabile, che include elementi di formattazione, sono effettivamente più grandi.</span><span class="sxs-lookup"><span data-stu-id="da66a-134">The size of the rendered report, which includes formatting, is actually larger.</span></span> <span data-ttu-id="da66a-135">Le dimensioni totali, indicate tra parentesi, rappresentano la somma delle dimensioni di tutti gli snapshot presenti nella cronologia del report per il report corrente.</span><span class="sxs-lookup"><span data-stu-id="da66a-135">The total size, indicated in parentheses, sums the sizes of all snapshots in the report history for the current report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da66a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da66a-136">See Also</span></span>  
 <span data-ttu-id="da66a-137">[Visualizzazione o eliminazione della cronologia del report &#40;Gestione report&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="da66a-137">[View or Delete Report History &#40;Report Manager&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="da66a-138">[Aggiungere uno snapshot alla cronologia del report &#40;Gestione report&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="da66a-138">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="da66a-139">[Pagina delle proprietà generale, report &#40;Gestione report&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="da66a-139">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="da66a-140">[Guida sensibile al contesto Gestione report](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="da66a-140">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="da66a-141">Pagina delle proprietà Opzioni snapshot &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="da66a-141">Snapshot Options Properties Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/snapshot-options-properties-page-report-manager.md)