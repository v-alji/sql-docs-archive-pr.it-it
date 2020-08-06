---
title: Proprietà pianificazione (pagina Generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.general.f1
ms.assetid: 20e43966-6caf-4972-a2e2-0d9131ac8f51
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a61837cd977526021be948d8c74a93eba6506e67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627072"
---
# <a name="schedule-properties-general-page"></a><span data-ttu-id="a2426-102">Proprietà pianificazione (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="a2426-102">Schedule Properties (General Page)</span></span>
  <span data-ttu-id="a2426-103">Utilizzare questa pagina per visualizzare o modificare una pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="a2426-103">Use this page to view or modify a shared schedule.</span></span> <span data-ttu-id="a2426-104">È possibile utilizzare le pianificazioni condivise al posto di di pianificazioni specifiche di report o sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="a2426-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="a2426-105">Le modifiche alla pianificazione vengono applicate dopo aver salvato la pianificazione stessa.</span><span class="sxs-lookup"><span data-stu-id="a2426-105">Changes to the schedule are applied after you save the schedule.</span></span> <span data-ttu-id="a2426-106">La modifica di una pianificazione non ha effetto sui processi attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="a2426-106">Editing a schedule has no effect on jobs that are currently in progress.</span></span> <span data-ttu-id="a2426-107">Se si modifica una pianificazione mentre è in uso, tutte le sottoscrizioni e i report in esecuzione attivati da tale pianificazione verranno portati a termine.</span><span class="sxs-lookup"><span data-stu-id="a2426-107">If you edit a schedule while it is being used, all currently processing reports and subscriptions triggered from that schedule will be allowed to finish.</span></span>  
  
 <span data-ttu-id="a2426-108">Non è possibile supportare tutte le combinazioni di frequenze in una singola pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a2426-108">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="a2426-109">Ad esempio, se si desidera eseguire un report alle 12.00</span><span class="sxs-lookup"><span data-stu-id="a2426-109">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="a2426-110">e alle 16.00</span><span class="sxs-lookup"><span data-stu-id="a2426-110">and 4:00 P.M.</span></span> <span data-ttu-id="a2426-111">ogni venerdì è necessario creare due pianificazioni giornaliere, una con giorno di esecuzione venerdì e inizio alle ore 12.00</span><span class="sxs-lookup"><span data-stu-id="a2426-111">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="a2426-112">e l'altra con inizio alle ore 16.00</span><span class="sxs-lookup"><span data-stu-id="a2426-112">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="a2426-113">L'elaborazione delle pianificazioni si basa sull'orario locale del server di report che ospita ed elabora la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a2426-113">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="a2426-114">Per aprire questa pagina, avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , connettersi a un server di report, aprire la cartella **pianificazioni condivise** , fare clic con il pulsante destro del mouse su una pianificazione condivisa e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a2426-114">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2426-115">Questa funzionalità non è disponibile in ogni edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e questa pagina non è visualizzata quando si esegue un'edizione che non dispone di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a2426-115">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and this page does not appear when you are running an edition which does not have this feature.</span></span> <span data-ttu-id="a2426-116">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [funzionalità supportate dalle edizioni di SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="a2426-116">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a2426-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a2426-117">Options</span></span>  
 <span data-ttu-id="a2426-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a2426-118">**Name**</span></span>  
 <span data-ttu-id="a2426-119">Consente di specificare il nome della pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="a2426-119">Specifies the name for the shared schedule.</span></span>  
  
 <span data-ttu-id="a2426-120">**Inizia l'esecuzione della pianificazione il**</span><span class="sxs-lookup"><span data-stu-id="a2426-120">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="a2426-121">Consente di specificare la data di inizio della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a2426-121">Specifies a start date for this schedule.</span></span>  
  
 <span data-ttu-id="a2426-122">**Arresta l'esecuzione della pianificazione il**</span><span class="sxs-lookup"><span data-stu-id="a2426-122">**Stop this schedule on**</span></span>  
 <span data-ttu-id="a2426-123">Consente di impostare la data di scadenza della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a2426-123">Specifies an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="a2426-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a2426-124">**Type**</span></span>  
 <span data-ttu-id="a2426-125">Specifica se il criterio di occorrenza è basato principalmente su ore, giorni, settimane o mesi oppure se l'esecuzione è prevista una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a2426-125">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, months, or only runs once.</span></span>  
  
 <span data-ttu-id="a2426-126">**Ora (criterio di occorrenza)**</span><span class="sxs-lookup"><span data-stu-id="a2426-126">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="a2426-127">Consente di specificare le opzioni per l'esecuzione di un'operazione pianificata a intervalli di un'ora, ad esempio per eseguire un report ogni 6 ore.</span><span class="sxs-lookup"><span data-stu-id="a2426-127">Specifies options for running a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="a2426-128">È possibile specificare l'intervallo in ore e minuti.</span><span class="sxs-lookup"><span data-stu-id="a2426-128">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="a2426-129">**Giorno (criterio di occorrenza)**</span><span class="sxs-lookup"><span data-stu-id="a2426-129">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="a2426-130">Consente di specificare le opzioni per l'esecuzione di un'operazione pianificata a intervalli di giorni, ad esempio per eseguire un report ogni 2 giorni.</span><span class="sxs-lookup"><span data-stu-id="a2426-130">Specifies options for running a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="a2426-131">È possibile specificare l'intervallo in giorni e impostare l'ora e i minuti in cui si desidera eseguire la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a2426-131">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="a2426-132">**Settimana (criterio di occorrenza)**</span><span class="sxs-lookup"><span data-stu-id="a2426-132">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="a2426-133">Consente di specificare le opzioni per l'esecuzione di un'operazione pianificata a intervalli di una settimana oppure quando lo schema che si desidera ripetere si basa su settimane, ad esempio per eseguire un report ogni due settimane.</span><span class="sxs-lookup"><span data-stu-id="a2426-133">Specifies options for running a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="a2426-134">È possibile specificare una pianificazione settimanale relativa al giorno, all'ora e ai minuti in cui si desidera eseguire la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a2426-134">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="a2426-135">**Mese (criterio di occorrenza)**</span><span class="sxs-lookup"><span data-stu-id="a2426-135">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="a2426-136">Consente di specificare le opzioni per l'esecuzione di un'operazione pianificata a intervalli di un mese oppure quando lo schema che si desidera ripetere si basa su mesi.</span><span class="sxs-lookup"><span data-stu-id="a2426-136">Specifies options for running a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="a2426-137">È possibile specificare una pianificazione mensile relativa al giorno, all'ora e ai minuti in cui si desidera eseguire la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a2426-137">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="a2426-138">Dalla pianificazione è possibile omettere mesi specifici.</span><span class="sxs-lookup"><span data-stu-id="a2426-138">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="a2426-139">**Una sola volta**</span><span class="sxs-lookup"><span data-stu-id="a2426-139">**Once**</span></span>  
 <span data-ttu-id="a2426-140">Consente di specificare una pianificazione che viene eseguita una sola volta nella data e all'ora specifiche.</span><span class="sxs-lookup"><span data-stu-id="a2426-140">Specifies a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2426-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2426-141">See Also</span></span>  
 <span data-ttu-id="a2426-142">[Guida sensibile al contesto del server di report Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="a2426-142">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="a2426-143">[Connettersi a un server di report in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a2426-143">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="a2426-144">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="a2426-144">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="a2426-145">Pianificazioni</span><span class="sxs-lookup"><span data-stu-id="a2426-145">Schedules</span></span>](../subscriptions/schedules.md)  
  
  
