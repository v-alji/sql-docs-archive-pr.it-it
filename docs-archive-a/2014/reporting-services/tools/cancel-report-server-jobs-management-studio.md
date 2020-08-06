---
title: Annulla processi server di report (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.cancelreportserverjobs.f1
ms.assetid: 1c5b4975-49e9-4d0b-b298-2638e81edbfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0ef8ada32aab4ac368871da711d0fe63fff7620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722503"
---
# <a name="cancel-report-server-jobs-management-studio"></a><span data-ttu-id="7e46e-102">Annulla processi server di report (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7e46e-102">Cancel Report Server Jobs (Management Studio)</span></span>
  <span data-ttu-id="7e46e-103">La finestra di dialogo **Annulla processi server di report** consente di visualizzare o annullare i report in corso.</span><span class="sxs-lookup"><span data-stu-id="7e46e-103">Use the **Cancel Report Server Jobs** dialog box to view or cancel in-progress reports.</span></span> <span data-ttu-id="7e46e-104">In questa finestra di dialogo vengono visualizzati tutti i processi attualmente in esecuzione nel server di report.</span><span class="sxs-lookup"><span data-stu-id="7e46e-104">This dialog box shows all jobs that are currently running on the report server.</span></span> <span data-ttu-id="7e46e-105">Sebbene non sia possibile sospendere o riavviare i processi attualmente in corso di elaborazione, è possibile annullare tutti i processi o singoli processi il cui completamento sta richiedendo troppo tempo.</span><span class="sxs-lookup"><span data-stu-id="7e46e-105">Although you cannot pause or restart jobs that are currently processing, you can cancel all jobs or individual jobs if they are taking too long to complete.</span></span>  
  
 <span data-ttu-id="7e46e-106">È possibile annullare sia i processi utente che i processi di sistema.</span><span class="sxs-lookup"><span data-stu-id="7e46e-106">You can cancel user jobs and system jobs.</span></span>  
  
-   <span data-ttu-id="7e46e-107">Un processo utente è qualsiasi processo avviato da un singolo utente,</span><span class="sxs-lookup"><span data-stu-id="7e46e-107">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="7e46e-108">inclusi l'esecuzione di un report su richiesta, la creazione manuale di uno snapshot della cronologia del report o la creazione manuale di uno snapshot dell'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="7e46e-108">This includes running a report on-demand, manually creating a report history snapshot, or manually creating report execution snapshot.</span></span> <span data-ttu-id="7e46e-109">Anche una sottoscrizione standard in corso è un processo utente.</span><span class="sxs-lookup"><span data-stu-id="7e46e-109">An in-progress standard subscription is also a user job.</span></span>  
  
-   <span data-ttu-id="7e46e-110">Un processo di sistema è un processo avviato dal server di report.</span><span class="sxs-lookup"><span data-stu-id="7e46e-110">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="7e46e-111">I processi dei sistema includono l'elaborazione pianificata dei report.</span><span class="sxs-lookup"><span data-stu-id="7e46e-111">System jobs include scheduled report processing.</span></span>  
  
 <span data-ttu-id="7e46e-112">Per aprire questa pagina, avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connettersi a un server di report, fare clic su **Processi**e quindi su **Annulla tutti i processi**.</span><span class="sxs-lookup"><span data-stu-id="7e46e-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Jobs**, and then click **Cancel All Jobs**.</span></span> <span data-ttu-id="7e46e-113">È anche possibile aprire **Processi**, fare clic con il pulsante destro del mouse su un processo in esecuzione nel server di report e scegliere **Annulla processo/i**.</span><span class="sxs-lookup"><span data-stu-id="7e46e-113">You can also open **Jobs**, right-click a job that is running on the report server, and select **Cancel Job(s)**.</span></span>  
  
 <span data-ttu-id="7e46e-114">Prima di annullare un processo, è possibile visualizzare le relative proprietà per determinare quando è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="7e46e-114">Before cancelling a job, you can view its properties to determine when the job started.</span></span> <span data-ttu-id="7e46e-115">Per altre informazioni, vedere [Proprietà processo &#40;Management Studio&#41;](job-properties-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7e46e-115">For more information, see [Job Properties &#40;Management Studio&#41;](job-properties-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e46e-116">Questa caratteristica non è supportata in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="7e46e-116">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="7e46e-117">Questa pagina non viene visualizzata quando è in esecuzione [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e46e-117">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="7e46e-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7e46e-118">Options</span></span>  
 <span data-ttu-id="7e46e-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="7e46e-119">**Name**</span></span>  
 <span data-ttu-id="7e46e-120">Indica il nome del report.</span><span class="sxs-lookup"><span data-stu-id="7e46e-120">Shows the name of the report.</span></span> <span data-ttu-id="7e46e-121">Le sottoscrizioni sono identificate tramite le rispettive descrizioni.</span><span class="sxs-lookup"><span data-stu-id="7e46e-121">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="7e46e-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7e46e-122">**Type**</span></span>  
 <span data-ttu-id="7e46e-123">I valori validi sono **Utente** e **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="7e46e-123">Valid values are **User** and **System**.</span></span>  
  
 <span data-ttu-id="7e46e-124">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="7e46e-124">**Start Time**</span></span>  
 <span data-ttu-id="7e46e-125">Ora di inizio del processo.</span><span class="sxs-lookup"><span data-stu-id="7e46e-125">Shows when the job started.</span></span>  
  
 <span data-ttu-id="7e46e-126">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="7e46e-126">**User Name**</span></span>  
 <span data-ttu-id="7e46e-127">Per i processi avviati da un utente, in questa colonna viene indicato il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7e46e-127">For jobs that are initiated by a user, this column shows the name of the user.</span></span>  
  
 <span data-ttu-id="7e46e-128">**Status**</span><span class="sxs-lookup"><span data-stu-id="7e46e-128">**Status**</span></span>  
 <span data-ttu-id="7e46e-129">Stato del processo.</span><span class="sxs-lookup"><span data-stu-id="7e46e-129">Shows the status of the job.</span></span> <span data-ttu-id="7e46e-130">I valori validi sono **Nuovo** e **In esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="7e46e-130">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="7e46e-131">All'avvio del processo, lo stato è sempre impostato come **Nuovo** .</span><span class="sxs-lookup"><span data-stu-id="7e46e-131">Status is always **New** when the job begins.</span></span> <span data-ttu-id="7e46e-132">Dopo 60 secondi, lo stato viene modificato in **In esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="7e46e-132">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="7e46e-133">Per visualizzare la modifica, è necessario aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="7e46e-133">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="7e46e-134">**OK**</span><span class="sxs-lookup"><span data-stu-id="7e46e-134">**OK**</span></span>  
 <span data-ttu-id="7e46e-135">Consente di annullare un singolo processo o più processi.</span><span class="sxs-lookup"><span data-stu-id="7e46e-135">Cancel a single job or multiple jobs.</span></span> <span data-ttu-id="7e46e-136">I processi vengono annullati immediatamente e non possono essere ripresi.</span><span class="sxs-lookup"><span data-stu-id="7e46e-136">The jobs are cancelled immediately and cannot be resumed.</span></span> <span data-ttu-id="7e46e-137">Se si annulla erroneamente un processo, è necessario richiedere di nuovo il report o la sottoscrizione per avviare un nuovo processo.</span><span class="sxs-lookup"><span data-stu-id="7e46e-137">If you mistakenly cancel a job, you must request the report or subscription again to start a new job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e46e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e46e-138">See Also</span></span>  
 <span data-ttu-id="7e46e-139">[Guida sensibile al contesto del server di report in Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="7e46e-139">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="7e46e-140">[Eseguire la connessione a un server di report in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7e46e-140">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="7e46e-141">Gestire un processo in esecuzione</span><span class="sxs-lookup"><span data-stu-id="7e46e-141">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
