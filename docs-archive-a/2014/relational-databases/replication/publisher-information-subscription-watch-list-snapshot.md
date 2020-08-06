---
title: Informazioni sul server di pubblicazione, elenco verifica sottoscrizioni (pubblicazione snapshot, SQL Server 2005 e versioni successive) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.snapshot.f1
ms.assetid: 2ebeee62-7f54-4c77-9d37-15708bc5cc23
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ea44958c81465570c036ab7dd83247fb55652f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716255"
---
# <a name="publisher-information-subscription-watch-list-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="6060e-102">Informazioni sul server di pubblicazione, Elenco verifica sottoscrizioni (Pubblicazione snapshot, SQL Server 2005 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="6060e-102">Publisher Information, Subscription Watch List (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="6060e-103">La scheda **Elenco verifica sottoscrizioni** è disponibile per i server di distribuzione che eseguono [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive e consente di visualizzare le informazioni sulle sottoscrizioni da tutte le pubblicazioni disponibili nel server di pubblicazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="6060e-103">The **Subscription Watch List** tab is available for Distributors running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="6060e-104">È possibile filtrare l'elenco delle sottoscrizioni per visualizzare errori, avvisi ed eventuali sottoscrizioni con prestazioni scarse.</span><span class="sxs-lookup"><span data-stu-id="6060e-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="6060e-105">Questa scheda offre gli amministratori un unico punto per il monitoraggio di tutte le attività di replica eseguite nel server di pubblicazione. Monitoraggio replica visualizza infatti tutte le sottoscrizioni che necessitano di attenzione in base al tipo di replica selezionato e all'opzione scelta nell'elenco a discesa **Mostra** .</span><span class="sxs-lookup"><span data-stu-id="6060e-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="6060e-106">Poiché gli elementi visualizzati in questa scheda si basano sullo stato e le prestazioni correnti, le sottoscrizioni vengono visualizzate in questa pagina solo se queste corrispondono all'opzione selezionata nella casella di riepilogo **Mostra** .</span><span class="sxs-lookup"><span data-stu-id="6060e-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6060e-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6060e-107">Options</span></span>  
 <span data-ttu-id="6060e-108">Per ulteriori informazioni su una sottoscrizione e sulle attività correlate, fare clic con il pulsante destro del mouse sulla riga della sottoscrizione e quindi scegliere un'opzione dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="6060e-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="6060e-109">Per modificare la modalità di visualizzazione dei dati nella griglia, fare clic con il pulsante destro del mouse sulla griglia, quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6060e-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="6060e-110">**Ordinamento**: consente di ordinare una o più colonne nella finestra di dialogo **Ordina colonne** .</span><span class="sxs-lookup"><span data-stu-id="6060e-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="6060e-111">**Seleziona colonne da visualizzare**: consente di selezionare le colonne da visualizzare e l'ordine di visualizzazione nella finestra di dialogo **Seleziona colonne** .</span><span class="sxs-lookup"><span data-stu-id="6060e-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="6060e-112">**Filtro**: consente di filtrare le righe nella griglia in base a valori di colonna nella finestra di dialogo **Impostazioni filtro** .</span><span class="sxs-lookup"><span data-stu-id="6060e-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="6060e-113">**Cancella filtro**: consente di cancellare qualsiasi impostazione di filtro per la griglia.</span><span class="sxs-lookup"><span data-stu-id="6060e-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="6060e-114">Le impostazioni di filtro sono specifiche di ogni griglia.</span><span class="sxs-lookup"><span data-stu-id="6060e-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="6060e-115">La selezione e l'ordinamento delle colonne vengono applicati a tutte le griglie dello stesso tipo, ad esempio la griglia delle pubblicazioni per ogni server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6060e-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="6060e-116">**Mostra sottoscrizioni snapshot**</span><span class="sxs-lookup"><span data-stu-id="6060e-116">**Show Snapshot Subscriptions**</span></span>  
 <span data-ttu-id="6060e-117">Consente di selezionare il tipo di sottoscrizioni (transazionali, snapshot o merge) da visualizzare per il server di distribuzione selezionato.</span><span class="sxs-lookup"><span data-stu-id="6060e-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="6060e-118">**Mostra**</span><span class="sxs-lookup"><span data-stu-id="6060e-118">**Show**</span></span>  
 <span data-ttu-id="6060e-119">Consente di selezionare gli stati della sottoscrizione da visualizzare per il tipo di sottoscrizione selezionato.</span><span class="sxs-lookup"><span data-stu-id="6060e-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="6060e-120">Ad esempio, è possibile scegliere di visualizzare solo le sottoscrizioni con errori.</span><span class="sxs-lookup"><span data-stu-id="6060e-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="6060e-121">**Status**</span><span class="sxs-lookup"><span data-stu-id="6060e-121">**Status**</span></span>  
 <span data-ttu-id="6060e-122">Stato di ogni sottoscrizione determinato dallo stato dell'agente snapshot o dell'agente di distribuzione. Viene visualizzato lo stato con priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="6060e-122">The status of each subscription, which is determined by the status of the Snapshot Agent or the Distribution Agent (the higher priority status is displayed).</span></span>  
  
 <span data-ttu-id="6060e-123">Per impostazione predefinita, la griglia contenente le informazioni sulla sottoscrizione viene ordinata in base alla colonna **Stato** .</span><span class="sxs-lookup"><span data-stu-id="6060e-123">By default, the grid containing subscription information is sorted by the **Status** column.</span></span> <span data-ttu-id="6060e-124">Nell'elenco seguente vengono indicati i valori di stato possibili e l'ordinamento di tali valori, ad esempio gli errori vengono sempre visualizzati nella parte superiore della griglia.</span><span class="sxs-lookup"><span data-stu-id="6060e-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="6060e-125">Errore</span><span class="sxs-lookup"><span data-stu-id="6060e-125">Error</span></span>  
  
-   <span data-ttu-id="6060e-126">Scadenza imminente/Scaduta</span><span class="sxs-lookup"><span data-stu-id="6060e-126">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="6060e-127">Sottoscrizione non inizializzata</span><span class="sxs-lookup"><span data-stu-id="6060e-127">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="6060e-128">Ripetizione comando non riuscito</span><span class="sxs-lookup"><span data-stu-id="6060e-128">Retrying failed command</span></span>  
  
-   <span data-ttu-id="6060e-129">Sincronizzazione in corso</span><span class="sxs-lookup"><span data-stu-id="6060e-129">Synchronizing</span></span>  
  
-   <span data-ttu-id="6060e-130">Non in sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="6060e-130">Not synchronizing</span></span>  
  
 <span data-ttu-id="6060e-131">L'ordinamento determina inoltre il valore da visualizzare quando per una particolare sottoscrizione sono disponibili più stati.</span><span class="sxs-lookup"><span data-stu-id="6060e-131">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="6060e-132">Se, ad esempio, per una sottoscrizione sono presenti errori e la scadenza della sottoscrizione è imminente, nella colonna **Stato** sarà visualizzato il valore **Errore**.</span><span class="sxs-lookup"><span data-stu-id="6060e-132">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="6060e-133">I valori di stato **Scadenza imminente/Scaduta** e **Sottoscrizione non inizializzata** sono avvisi.</span><span class="sxs-lookup"><span data-stu-id="6060e-133">The status values **Expiring soon/Expired** and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="6060e-134">Quando viene visualizzato un avviso, nella colonna **Stato** viene inoltre visualizzato se è in esecuzione un agente.</span><span class="sxs-lookup"><span data-stu-id="6060e-134">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="6060e-135">Ad esempio, lo stato potrebbe essere **In esecuzione, Scadenza imminente/Scaduta**.</span><span class="sxs-lookup"><span data-stu-id="6060e-135">For example, the status could be **Running, Expiring soon/Expired**.</span></span>  
  
 <span data-ttu-id="6060e-136">Il valore di stato **Scadenza imminente/Scaduta** viene visualizzato solo se è stato impostato un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="6060e-136">The status value **Expiring soon/Expired** is displayed only if a threshold is set.</span></span> <span data-ttu-id="6060e-137">Per altre informazioni sull'impostazione di valori soglia, vedere [Impostare valori di soglia e avvisi in Monitoraggio replica](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="6060e-137">For information on setting thresholds, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="6060e-138">**Sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="6060e-138">**Subscription**</span></span>  
 <span data-ttu-id="6060e-139">Nome di ogni sottoscrizione nel formato: *SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="6060e-139">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="6060e-140">**Publication**</span><span class="sxs-lookup"><span data-stu-id="6060e-140">**Publication**</span></span>  
 <span data-ttu-id="6060e-141">Nome della pubblicazione con cui viene sincronizzata una sottoscrizione nel formato: *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="6060e-141">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="6060e-142">**Ultima sincronizzazione**</span><span class="sxs-lookup"><span data-stu-id="6060e-142">**Last Synchronization**</span></span>  
 <span data-ttu-id="6060e-143">Data e ora dell'ultima esecuzione dell'agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6060e-143">The time at which the Distribution Agent last ran.</span></span> <span data-ttu-id="6060e-144">Se il processo di sincronizzazione è in corso, viene visualizzato **In corso** .</span><span class="sxs-lookup"><span data-stu-id="6060e-144">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6060e-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6060e-145">See Also</span></span>  
 <span data-ttu-id="6060e-146">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="6060e-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="6060e-147">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="6060e-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="6060e-148">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="6060e-148">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
