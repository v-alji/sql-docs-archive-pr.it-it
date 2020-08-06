---
title: Gestire gli avvisi dati personali in Gestione avvisi dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: e0e4ffdf-bd4c-4ebd-872b-07486cbb47c2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 371c62c2f97334e20280a659c8039ab20852ccfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721222"
---
# <a name="manage-my-data-alerts-in-data-alert-manager"></a><span data-ttu-id="ea9d2-102">Gestire gli avvisi dati in Gestione avvisi dati</span><span class="sxs-lookup"><span data-stu-id="ea9d2-102">Manage My Data Alerts in Data Alert Manager</span></span>
  <span data-ttu-id="ea9d2-103">Gli utenti di SharePoint possono visualizzare un elenco degli avvisi dati creati e le informazioni sugli avvisi.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-103">SharePoint users can view a list of the data alerts that they created and information about the alerts.</span></span> <span data-ttu-id="ea9d2-104">Possono inoltre eliminare i propri avvisi, aprire definizioni di avviso per la modifica nella finestra di progettazione Avviso dati ed eseguire i propri avvisi.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-104">Users can also delete their alerts, open alert definitions for edit in Data Alert Designer, and run their alerts.</span></span> <span data-ttu-id="ea9d2-105">Nella figura seguente sono illustrate le funzionalità disponibili per gli utenti in Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-105">The following picture shows the features available to users in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="ea9d2-106">![Funzionalità di Gestione avvisi per gli utenti di SharePoint](media/rs-alertmanageriw.gif "Funzionalità di Gestione avvisi per gli utenti di SharePoint")</span><span class="sxs-lookup"><span data-stu-id="ea9d2-106">![Alert Manager features for SharePoint users](media/rs-alertmanageriw.gif "Alert Manager features for SharePoint users")</span></span>  
  
### <a name="to-view-a-list-of-your-alerts"></a><span data-ttu-id="ea9d2-107">Per visualizzare un elenco di avvisi</span><span class="sxs-lookup"><span data-stu-id="ea9d2-107">To view a list of your alerts</span></span>  
  
1.  <span data-ttu-id="ea9d2-108">Passare alla raccolta di SharePoint in cui sono stati salvati i report per i quali sono stati creati avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-108">Go to the SharePoint library where you saved the reports on which you created data alerts.</span></span>  
  
2.  <span data-ttu-id="ea9d2-109">Fare clic sull'icona per espandere il menu a discesa in un report, quindi fare clic su **Gestisci avvisi dati**.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-109">Click the icon for the expand drop-down menu on a report and click **Manage Data Alerts**.</span></span> <span data-ttu-id="ea9d2-110">Nella figura seguente è illustrato il menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-110">The following picture shows the drop-down menu.</span></span>  
  
     <span data-ttu-id="ea9d2-111">![Aprire Gestione avvisi dal menu di scelta rapida del report](media/rs-openalertmanager.gif "Aprire Gestione avvisi dal menu di scelta rapida del report")</span><span class="sxs-lookup"><span data-stu-id="ea9d2-111">![Open Alert Manager from report context menu](media/rs-openalertmanager.gif "Open Alert Manager from report context menu")</span></span>  
  
     <span data-ttu-id="ea9d2-112">Verrà aperto Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-112">Data Alert Manager opens.</span></span> <span data-ttu-id="ea9d2-113">Per impostazione predefinita, vengono elencati gli avvisi per il report selezionati nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-113">By default, it lists the alerts for the report that you selected in the library.</span></span>  
  
3.  <span data-ttu-id="ea9d2-114">Fare clic sulla freccia GIÙ accanto all'elenco **Visualizza avvisi per il report** e selezionare un report per visualizzare i relativi avvisi oppure fare clic su **Mostra tutto** per elencare tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-114">Click the down arrow next to the **View alerts for report** list and select a report to view its alerts, or click **Show All** to list all alerts.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea9d2-115">Se il report selezionato non dispone di avvisi, non è necessario tornare alla raccolta di SharePoint per individuare e selezionare un report che disponga di avvisi.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-115">If the report that you selected does not have any alerts, you do not have to return to the SharePoint library to locate and select a report that hasalerts.</span></span> <span data-ttu-id="ea9d2-116">È invece possibile fare clic su **Mostra tutto** per visualizzare un elenco di tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-116">Instead, click **Show All** to see a list of all your alerts.</span></span>  
  
     <span data-ttu-id="ea9d2-117">In una tabella vengono elencati il nome dell'avviso, il nome del report, il nome del creatore dell'avviso, il numero di volte in cui l'avviso è stato inviato, l'ultima modifica alla definizione di avviso e lo stato dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-117">A table lists the alert name, report name, your name as the creator of the alert, the number the alert was sent, the last time the alert definition was modified, and the status of the alert.</span></span> <span data-ttu-id="ea9d2-118">Se l'avviso non può essere generato o inviato, nella colonna relativa allo stato sono incluse informazioni sull'errore che consentono di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-118">If the alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-edit-an-alert-definition"></a><span data-ttu-id="ea9d2-119">Per modificare una definizione di avviso</span><span class="sxs-lookup"><span data-stu-id="ea9d2-119">To edit an alert definition</span></span>  
  
-   <span data-ttu-id="ea9d2-120">Fare clic con il pulsante destro del mouse sull'avviso dati per il quale si desidera modificare la definizione, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-120">Right-click the data alert for which you want to edit the alert definition and click **Edit**.</span></span>  
  
     <span data-ttu-id="ea9d2-121">La definizione di avviso viene aperta in Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-121">The alert definition opens in Data Alert Designer.</span></span> <span data-ttu-id="ea9d2-122">Per altre informazioni, vedere [Modificare un avviso dati nella finestra di progettazione di avvisi](edit-a-data-alert-in-alert-designer.md) e [Finestra di progettazione Avviso dati](../../2014/reporting-services/data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="ea9d2-122">For more information, see [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md) and [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea9d2-123">La definizione di avviso dati può essere modificata solo dall'utente che l'ha creata.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-123">Only the user that created the data alert definition can edit it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea9d2-124">Se il report è cambiato e i feed di dati generati dal report sono cambiati, la definizione di avviso potrebbe non essere più valida.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-124">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="ea9d2-125">Questa condizione si verifica quando una colonna, a cui fa riferimento l'avviso nelle regole, viene eliminata dal report, quando il tipo di dati contenuto in tale colonna viene modificato, quando la colonna viene inclusa in un feed di dati diverso oppure quando il report viene eliminato o spostato.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-125">This occurs when a column that the alert references in its rules is deleted from the report, changes data type, or is included in a different data feed or the report is deleted or moved.</span></span> <span data-ttu-id="ea9d2-126">È possibile aprire una definizione di avviso che non è valida, ma non è possibile salvarla di nuovo fino a quando non diventa valida in base alla versione corrente del feed di dati del report in base a cui è compilata.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-126">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="ea9d2-127">Per altre informazioni sulla modalità di generazione di feed di dati dai report, vedere [Generazione di feed di dati dai report &#40;Generatore report e SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ea9d2-127">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="ea9d2-128">Per eliminare una definizione di avviso</span><span class="sxs-lookup"><span data-stu-id="ea9d2-128">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="ea9d2-129">Fare clic con il pulsante destro del mouse sull'avviso dati che si desidera eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-129">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
     <span data-ttu-id="ea9d2-130">Dopo avere eliminato l'avviso, non verranno inviati ulteriori messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-130">When you delete the alert, no further alert messages are sent.</span></span>  
  
### <a name="to-run-an-alert"></a><span data-ttu-id="ea9d2-131">Per eseguire un avviso</span><span class="sxs-lookup"><span data-stu-id="ea9d2-131">To run an alert</span></span>  
  
-   <span data-ttu-id="ea9d2-132">Fare clic con il pulsante destro del mouse sull'avviso dati che si desidera eseguire, quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-132">Right-click the data alert that you want to run and click **Run**.</span></span>  
  
     <span data-ttu-id="ea9d2-133">L'istanza di avviso viene creata e il messaggio di avviso dati viene inviato immediatamente, indipendentemente dalle opzioni di pianificazione specificate nella finestra di progettazione Avviso dati.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-133">The alert instance is created and the data alert message is immediately sent, regardless of the schedule options you specified in Data Alert Designer.</span></span> <span data-ttu-id="ea9d2-134">Un avviso configurato per essere inviato ogni settimana e solo se i risultati cambiano viene ad esempio inviato.</span><span class="sxs-lookup"><span data-stu-id="ea9d2-134">For example, an alert configured to be sent weekly and then only if the results change is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea9d2-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea9d2-135">See Also</span></span>  
 <span data-ttu-id="ea9d2-136">[Gestione avvisi dati per gli amministratori di avvisi](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="ea9d2-136">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="ea9d2-137">Reporting Services Data Alerts</span><span class="sxs-lookup"><span data-stu-id="ea9d2-137">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
