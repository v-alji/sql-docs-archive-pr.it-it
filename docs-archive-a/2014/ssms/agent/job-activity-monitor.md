---
title: Monitoraggio attività processi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.ACTIVITYMON.F1
- sql12.ag.jobactivitymonitor.alljobs.f1
ms.assetid: 11f2182c-5f71-46f8-8d2b-74f0fc48f2d6
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6f89d5448f0885c85229c2808ee6f85bf6fa071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715035"
---
# <a name="job-activity-monitor"></a><span data-ttu-id="106ab-102">Monitoraggio attività processi</span><span class="sxs-lookup"><span data-stu-id="106ab-102">Job Activity Monitor</span></span>
  <span data-ttu-id="106ab-103">Utilizzare questa pagina per visualizzare l'attività corrente dei processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="106ab-103">Use this page to view the current activity of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="106ab-104">Fare clic su **Filtro** per limitare i processi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="106ab-104">Click **Filter** to limit the jobs displayed.</span></span> <span data-ttu-id="106ab-105">La griglia **Attività processi agente** è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="106ab-105">The **Agent Job Activity** grid is read-only.</span></span> <span data-ttu-id="106ab-106">Per ordinare la griglia fare clic sulle intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="106ab-106">Click on the column headers to sort the grid.</span></span> <span data-ttu-id="106ab-107">Per modificare un processo, selezionarlo facendo doppio clic per aprire la finestra di dialogo **Proprietà processo** .</span><span class="sxs-lookup"><span data-stu-id="106ab-107">To modify a job, double-click the job to open the **Job Properties** dialog box.</span></span> <span data-ttu-id="106ab-108">Fare clic con il pulsante destro del mouse su un processo nella griglia per avviare l'esecuzione di tutti i passaggi di processo, per avviare un particolare passaggio di processo, per disabilitare o abilitare il processo, per aggiornare il processo, per eliminare il processo, per visualizzare la cronologia del processo o per visualizzare le proprietà del processo.</span><span class="sxs-lookup"><span data-stu-id="106ab-108">Right-click a job in the grid to start it running all job steps, start at a particular job step, disable or enable the job, refresh the job, delete the job, view the history of the job, or view the properties of the job.</span></span> <span data-ttu-id="106ab-109">Fare clic su **Aggiorna** per aggiornare la griglia con le informazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="106ab-109">Click **Refresh** to update the grid with current information.</span></span>  
  
## <a name="options"></a><span data-ttu-id="106ab-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="106ab-110">Options</span></span>  
 <span data-ttu-id="106ab-111">**Nome**</span><span class="sxs-lookup"><span data-stu-id="106ab-111">**Name**</span></span>  
 <span data-ttu-id="106ab-112">Nome del processo.</span><span class="sxs-lookup"><span data-stu-id="106ab-112">Name of the job.</span></span>  
  
 <span data-ttu-id="106ab-113">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="106ab-113">**Enabled**</span></span>  
 <span data-ttu-id="106ab-114">Indica se il processo è abilitato (**sì**) o non abilitato (**no**).</span><span class="sxs-lookup"><span data-stu-id="106ab-114">Whether the job is enabled (**yes**) or not enabled (**no**).</span></span>  
  
 <span data-ttu-id="106ab-115">**Stato** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="106ab-115">**Status** <sup>1</sup></span></span>  
 <span data-ttu-id="106ab-116">Stato corrente del processo.</span><span class="sxs-lookup"><span data-stu-id="106ab-116">Current status of the job.</span></span>  
  
 <span data-ttu-id="106ab-117">**Risultati ultima esecuzione**</span><span class="sxs-lookup"><span data-stu-id="106ab-117">**Last Run Outcome**</span></span>  
 <span data-ttu-id="106ab-118">Stato del processo all'ultima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="106ab-118">Job status when last run.</span></span>  
  
 <span data-ttu-id="106ab-119">**Ultima esecuzione**</span><span class="sxs-lookup"><span data-stu-id="106ab-119">**Last Run**</span></span>  
 <span data-ttu-id="106ab-120">Data e ora dell'ultima esecuzione del processo utilizzando la data e l'ora locali del server.</span><span class="sxs-lookup"><span data-stu-id="106ab-120">Date and time job was last run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="106ab-121">**Prossima esecuzione** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="106ab-121">**Next Run** <sup>1</sup></span></span>  
 <span data-ttu-id="106ab-122">Data e ora pianificate per la successiva esecuzione del processo utilizzando la data e l'ora locali del server.</span><span class="sxs-lookup"><span data-stu-id="106ab-122">Date and time the job is next scheduled to run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="106ab-123">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="106ab-123">**Category**</span></span>  
 <span data-ttu-id="106ab-124">Categoria assegnata al processo.</span><span class="sxs-lookup"><span data-stu-id="106ab-124">The job category assigned to the job.</span></span>  
  
 <span data-ttu-id="106ab-125">**Eseguibile**</span><span class="sxs-lookup"><span data-stu-id="106ab-125">**Runnable**</span></span>  
 <span data-ttu-id="106ab-126">**Sì** se il processo può essere eseguito, **No** se il processo non può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="106ab-126">**Yes** if the job can be run; **No** if the job cannot be run.</span></span> <span data-ttu-id="106ab-127">Un processo non può essere eseguito se non è associato a passaggi o a un server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="106ab-127">A job is not runnable if it has no steps or if it has no target server.</span></span>  
  
 <span data-ttu-id="106ab-128">**Pianificate**</span><span class="sxs-lookup"><span data-stu-id="106ab-128">**Scheduled**</span></span>  
 <span data-ttu-id="106ab-129">**Sì** se il processo è assegnato a una programmazione processi, **No** se il processo non ha alcuna programmazione.</span><span class="sxs-lookup"><span data-stu-id="106ab-129">**Yes** if the job is assigned to a job schedule; **No** if the job has no schedule.</span></span>  
  
 <span data-ttu-id="106ab-130"><sup>1</sup> Solo i membri del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ruolo predefinito del server sysadmin e del gruppo Administrators del server possono visualizzare i valori in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="106ab-130"><sup>1</sup>Only members of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sysadmin fixed server role and the server administrators group can see values in this column.</span></span> <span data-ttu-id="106ab-131">Membri del ruolo SQLAgentOperatorRole non possono vedere i valori in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="106ab-131">Members of the SQLAgentOperatorRole role cannot see values in this column.</span></span>  
  
#### <a name="to-open-the-job-activity-monitor"></a><span data-ttu-id="106ab-132">Per aprire Monitoraggio attività processi</span><span class="sxs-lookup"><span data-stu-id="106ab-132">To open the Job Activity Monitor</span></span>  
  
-   <span data-ttu-id="106ab-133">In **Esplora oggetti**espandere il server, espandere **SQL Server Agent**, fare clic con il pulsante destro del mouse su **Monitoraggio attività processi**e scegliere **Visualizza attività processi**.</span><span class="sxs-lookup"><span data-stu-id="106ab-133">In **Object Explorer**, expand your server, expand **SQL Server Agent**, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106ab-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="106ab-134">See Also</span></span>  
 [<span data-ttu-id="106ab-135">Monitoraggio delle attività del processo</span><span class="sxs-lookup"><span data-stu-id="106ab-135">Monitor Job Activity</span></span>](monitor-job-activity.md)  
  
  
