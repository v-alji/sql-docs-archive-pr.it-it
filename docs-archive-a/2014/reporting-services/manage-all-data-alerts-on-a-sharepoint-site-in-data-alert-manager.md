---
title: Gestire tutti gli avvisi dati in un sito di SharePoint con Gestione avvisi dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: 9c70b0f4-2db8-4c2e-acbf-96e2a55ddc48
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b41fdbd18a0b1b4a7a69a3ca202de1c555c070de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721221"
---
# <a name="manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager"></a><span data-ttu-id="5096d-102">Gestire tutti gli avvisi dati in un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5096d-102">Manage All Data Alerts on a SharePoint Site in Data Alert Manager</span></span>
  <span data-ttu-id="5096d-103">Gli amministratori di avvisi di SharePoint possono visualizzare un elenco degli avvisi dati creati da qualsiasi utente del sito e le informazioni sugli avvisi.</span><span class="sxs-lookup"><span data-stu-id="5096d-103">SharePoint alerting administrators can view a list of the data alerts that were created by any site user and information about the alerts.</span></span> <span data-ttu-id="5096d-104">Gli amministratori di avvisi possono inoltre eliminare avvisi.</span><span class="sxs-lookup"><span data-stu-id="5096d-104">Alerting administrators can also delete alerts.</span></span> <span data-ttu-id="5096d-105">Nella figura seguente sono illustrate le funzionalità disponibili per gli amministratori di avvisi in Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="5096d-105">The following picture shows the features available to alerting administrators in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="5096d-106">![Gestione avvisi per gli amministratori del sito di SharePoint](media/rs-alertmanagersite.gif "Gestione avvisi per gli amministratori del sito di SharePoint")</span><span class="sxs-lookup"><span data-stu-id="5096d-106">![Alert Manager for SharePoin tsite administrators](media/rs-alertmanagersite.gif "Alert Manager for SharePoin tsite administrators")</span></span>  
  
### <a name="to-view-a-list-of-alerts-created-by-a-site-user"></a><span data-ttu-id="5096d-107">Per visualizzare un elenco di avvisi creati da un utente del sito</span><span class="sxs-lookup"><span data-stu-id="5096d-107">To view a list of alerts created by a site user</span></span>  
  
1.  <span data-ttu-id="5096d-108">Passare al sito di SharePoint in cui sono state salvate le definizioni di avviso dati.</span><span class="sxs-lookup"><span data-stu-id="5096d-108">Go to the SharePoint site where data alerts definitions are saved.</span></span>  
  
2.  <span data-ttu-id="5096d-109">Nella home page fare clic su **Azioni sito**.</span><span class="sxs-lookup"><span data-stu-id="5096d-109">On the Home page, click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="5096d-110">Scorrere verso la parte inferiore dell'elenco e fare clic su **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="5096d-110">Scroll to the bottom of the list and click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="5096d-111">In **Reporting Services**fare clic su **Gestisci avvisi dati**.</span><span class="sxs-lookup"><span data-stu-id="5096d-111">Under **Reporting Services**, click **Manage Data Alerts**.</span></span>  
  
5.  <span data-ttu-id="5096d-112">Fare clic sulla freccia a discesa dall'elenco **Visualizza avvisi per l'utente** e selezionare l'utente di cui visualizzare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="5096d-112">Click the down arrow by the **View alerts for user** list and select the user whose alerts you want to view.</span></span>  
  
6.  <span data-ttu-id="5096d-113">Fare clic sulla freccia a discesa dell'elenco **Visualizza avvisi per il report** e selezionare un avviso specifico da visualizzare o fare clic su **Mostra tutto** per elencare tutti gli avvisi creati dall'utente selezionato.</span><span class="sxs-lookup"><span data-stu-id="5096d-113">Click the down arrow next to the **View alerts for report** list and select a specific alert to view, or click **Show All** to list all alerts created by the selected user.</span></span>  
  
     <span data-ttu-id="5096d-114">In una tabella sono elencati il nome, il nome del report, il nome dell'utente che ha creato l'avviso dati, il numero di volte che l'avviso dati è stato inviato, l'ultima modifica della definizione di avviso dati e lo stato dell'avviso dati.</span><span class="sxs-lookup"><span data-stu-id="5096d-114">A table lists the name, report name, name of the person who created the data alert, the number times the data alert was sent, the last time the data alert definition was modified, and the status of the data alert.</span></span> <span data-ttu-id="5096d-115">Se l'avviso dati non può essere generato o inviato, nella colonna relativa allo stato sono incluse informazioni sull'errore che consentono di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="5096d-115">If the data alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="5096d-116">Per eliminare una definizione di avviso</span><span class="sxs-lookup"><span data-stu-id="5096d-116">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="5096d-117">Fare clic con il pulsante destro del mouse sull'avviso dati che si desidera eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="5096d-117">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5096d-118">Dopo avere eliminato l'avviso, non verranno inviati ulteriori messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="5096d-118">After you delete the alert, no further alert messages are sent.</span></span> <span data-ttu-id="5096d-119">Se tuttavia si esegue una query sul database di avvisi, è possibile trovare ancora la definizione di avviso.</span><span class="sxs-lookup"><span data-stu-id="5096d-119">However, if you query the alerting database you might find that the alert definition still exists.</span></span> <span data-ttu-id="5096d-120">Il servizio avvisi consente di eseguire la pulizia in base a una pianificazione e la definizione di avviso verrà eliminata definitivamente alla successiva operazione di pulizia.</span><span class="sxs-lookup"><span data-stu-id="5096d-120">The alerting service performs clean up on a schedule and the alert definition is deleted permanently in the next cleanup.</span></span> <span data-ttu-id="5096d-121">L'intervallo di pulizia predefinito è impostato su 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="5096d-121">The default cleanup interval is 20 minutes.</span></span> <span data-ttu-id="5096d-122">Questo e altri intervalli di pulizia sono configurabili.</span><span class="sxs-lookup"><span data-stu-id="5096d-122">This and other cleanup intervals are configurable.</span></span> <span data-ttu-id="5096d-123">Per altre informazioni, vedere [Avvisi dati di Reporting Services](../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="5096d-123">For more information, see [Reporting Services Data Alerts](../ssms/agent/alerts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5096d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5096d-124">See Also</span></span>  
 <span data-ttu-id="5096d-125">[Gestione avvisi dati per gli amministratori di avvisi](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="5096d-125">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="5096d-126">Reporting Services Data Alerts</span><span class="sxs-lookup"><span data-stu-id="5096d-126">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
