---
title: Proprietà processo (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.jobproperties.f1
ms.assetid: 807ffd0e-9363-4f8f-9c36-c5d746ad19fd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4d309ba78a21114cf51c48f0a5c5b3b2f7c2500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716027"
---
# <a name="job-properties-management-studio"></a><span data-ttu-id="bac15-102">Proprietà processo (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bac15-102">Job Properties (Management Studio)</span></span>
  <span data-ttu-id="bac15-103">Usare la pagina **Proprietà processo** per visualizzare le informazioni su una sottoscrizione o su un report in corso prima di annullarlo.</span><span class="sxs-lookup"><span data-stu-id="bac15-103">Use the **Job Properties** page to view information about an in-progress report or subscription before you cancel it.</span></span>  
  
 <span data-ttu-id="bac15-104">Per aprire questa pagina, avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connettersi a un server di report e aprire la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="bac15-104">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, and open the **Jobs** folder.</span></span> <span data-ttu-id="bac15-105">Fare clic con il pulsante destro del mouse su un processo in esecuzione, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bac15-105">Right-click a job that is running, and then click **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bac15-106">Questa caratteristica non è supportata in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="bac15-106">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="bac15-107">Questa pagina non viene visualizzata quando è in esecuzione [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bac15-107">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="bac15-108">Attività</span><span class="sxs-lookup"><span data-stu-id="bac15-108">Tasks</span></span>  
 <span data-ttu-id="bac15-109">Per visualizzare le informazioni su un processo, è prima necessario aggiornare la pagina per recuperare le informazioni sui processi attualmente in esecuzione nel server di report:</span><span class="sxs-lookup"><span data-stu-id="bac15-109">Before you can view information about a job, refresh the page to retrieve information about jobs that are currently running on the report server:</span></span>  
  
1.  <span data-ttu-id="bac15-110">Aprire la cartella del server di report.</span><span class="sxs-lookup"><span data-stu-id="bac15-110">Open the report server folder.</span></span>  
  
2.  <span data-ttu-id="bac15-111">Fare clic con il pulsante destro del mouse su **Processi**, quindi scegliere **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="bac15-111">Right-click **Jobs**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="bac15-112">Se un processo è presente nell'elenco, fare clic con il pulsante destro del mouse su di esso, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bac15-112">If a job is listed, right-click the job, and then click **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bac15-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bac15-113">Options</span></span>  
 <span data-ttu-id="bac15-114">**ID processo**</span><span class="sxs-lookup"><span data-stu-id="bac15-114">**Job ID**</span></span>  
 <span data-ttu-id="bac15-115">GUID assegnato a un processo durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="bac15-115">A GUID that is assigned to a job while it is processing.</span></span> <span data-ttu-id="bac15-116">Il valore viene generato casualmente ogni volta che viene eseguito un report o una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="bac15-116">The value is randomly generated each time a report or subscription runs.</span></span>  
  
 <span data-ttu-id="bac15-117">**Stato processo**</span><span class="sxs-lookup"><span data-stu-id="bac15-117">**Job Status**</span></span>  
 <span data-ttu-id="bac15-118">I valori validi sono **Nuovo** e **In esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="bac15-118">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="bac15-119">All'avvio del processo, lo stato è sempre impostato come **Nuovo** .</span><span class="sxs-lookup"><span data-stu-id="bac15-119">Status is always **New** when the job begins.</span></span> <span data-ttu-id="bac15-120">Dopo 60 secondi, lo stato viene modificato in **In esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="bac15-120">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="bac15-121">Per visualizzare la modifica, è necessario aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="bac15-121">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="bac15-122">**Tipo di processo**</span><span class="sxs-lookup"><span data-stu-id="bac15-122">**Job Type**</span></span>  
 <span data-ttu-id="bac15-123">I valori validi sono **Utente** e **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="bac15-123">Valid values are **User** and **System**.</span></span> <span data-ttu-id="bac15-124">Un processo utente è qualsiasi processo avviato da un singolo utente,</span><span class="sxs-lookup"><span data-stu-id="bac15-124">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="bac15-125">inclusi l'esecuzione di un report su richiesta, la generazione manuale di uno snapshot della cronologia del report o la creazione manuale di uno snapshot dell'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="bac15-125">This includes running a report on-demand, manually generating a report history snapshot, or manually creating a report execution snapshot.</span></span> <span data-ttu-id="bac15-126">Anche una sottoscrizione standard in corso è un processo utente.</span><span class="sxs-lookup"><span data-stu-id="bac15-126">An in-progress standard subscription is also a user job.</span></span> <span data-ttu-id="bac15-127">Un processo di sistema è un processo avviato dal server di report.</span><span class="sxs-lookup"><span data-stu-id="bac15-127">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="bac15-128">I processi di sistema includono l'elaborazione di report avviata da una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="bac15-128">System jobs include report processing that is triggered by a schedule.</span></span>  
  
 <span data-ttu-id="bac15-129">**Azione del processo**</span><span class="sxs-lookup"><span data-stu-id="bac15-129">**Job Action**</span></span>  
 <span data-ttu-id="bac15-130">Per i report, in questa colonna vengono indicati i processi di esecuzione del report in corso.</span><span class="sxs-lookup"><span data-stu-id="bac15-130">For reports, this column shows which report execution processes are underway.</span></span> <span data-ttu-id="bac15-131">Questo valore corrisponde sempre a **Rendering**.</span><span class="sxs-lookup"><span data-stu-id="bac15-131">This value is always **Render**.</span></span>  
  
 <span data-ttu-id="bac15-132">**Descrizione del processo**</span><span class="sxs-lookup"><span data-stu-id="bac15-132">**Job Description**</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="bac15-133">per impostazione predefinita non fornisce descrizioni dei processi.</span><span class="sxs-lookup"><span data-stu-id="bac15-133">does not provide job descriptions by default.</span></span>  
  
 <span data-ttu-id="bac15-134">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="bac15-134">**Server Name**</span></span>  
 <span data-ttu-id="bac15-135">Indica il nome del server di report che sta elaborando il processo.</span><span class="sxs-lookup"><span data-stu-id="bac15-135">Shows the name of the report server that is processing the job.</span></span> <span data-ttu-id="bac15-136">Se è stata configurata una distribuzione con scalabilità orizzontale, questo valore indica il server che sta elaborando il processo.</span><span class="sxs-lookup"><span data-stu-id="bac15-136">If you configured a scale-out deployment, this value will show which server is processing the job.</span></span>  
  
 <span data-ttu-id="bac15-137">**Nome del report**</span><span class="sxs-lookup"><span data-stu-id="bac15-137">**Report Name**</span></span>  
 <span data-ttu-id="bac15-138">Indica il nome del report.</span><span class="sxs-lookup"><span data-stu-id="bac15-138">Shows the name of the report.</span></span> <span data-ttu-id="bac15-139">Le sottoscrizioni sono identificate tramite le rispettive descrizioni.</span><span class="sxs-lookup"><span data-stu-id="bac15-139">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="bac15-140">**Percorso report**</span><span class="sxs-lookup"><span data-stu-id="bac15-140">**Report Path**</span></span>  
 <span data-ttu-id="bac15-141">Indica il percorso del report nella gerarchia di cartelle del server di report.</span><span class="sxs-lookup"><span data-stu-id="bac15-141">Shows the path of the report in the report server folder hierarchy.</span></span>  
  
 <span data-ttu-id="bac15-142">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="bac15-142">**Start Time**</span></span>  
 <span data-ttu-id="bac15-143">Indica l'ora di inizio del processo.</span><span class="sxs-lookup"><span data-stu-id="bac15-143">Shows when the process started.</span></span>  
  
 <span data-ttu-id="bac15-144">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="bac15-144">**User Name**</span></span>  
 <span data-ttu-id="bac15-145">Per i processi avviati da un utente, in questa colonna viene indicato il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bac15-145">For processes initiated by a user, this column shows the name of the user.</span></span> <span data-ttu-id="bac15-146">Per i processi di sistema, si tratta del nome del server di report.</span><span class="sxs-lookup"><span data-stu-id="bac15-146">For system jobs, this is the name of the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac15-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bac15-147">See Also</span></span>  
 <span data-ttu-id="bac15-148">[Guida sensibile al contesto del server di report in Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="bac15-148">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="bac15-149">[Eseguire la connessione a un server di report in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="bac15-149">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="bac15-150">Gestire un processo in esecuzione</span><span class="sxs-lookup"><span data-stu-id="bac15-150">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
