---
title: 'Proprietà passaggio processo: nuovo passaggio di processo (pagina Avanzate) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepadvanced.f1
ms.assetid: bdecfd4f-bcd8-4ba2-8ada-fbb636314f40
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42820ffbdbb89261e839b5d1011f3a91b5841c86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722180"
---
# <a name="job-step-properties-new-job-step-advanced-page"></a><span data-ttu-id="0492a-102">Proprietà passaggio processo: Nuovo passaggio di processo (pagina Avanzate)</span><span class="sxs-lookup"><span data-stu-id="0492a-102">Job Step Properties: New Job Step (Advanced Page)</span></span>
  <span data-ttu-id="0492a-103">Utilizzare questa pagina per visualizzare e modificare le proprietà di un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passaggio di processo di Agent.</span><span class="sxs-lookup"><span data-stu-id="0492a-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0492a-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0492a-104">Options</span></span>  
 <span data-ttu-id="0492a-105">**Azione in caso di esito positivo**</span><span class="sxs-lookup"><span data-stu-id="0492a-105">**On success action**</span></span>  
 <span data-ttu-id="0492a-106">Consente di impostare l'azione che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve eseguire in caso di esito positivo del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-106">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step succeeds.</span></span>  
  
 <span data-ttu-id="0492a-107">**Tentativi**</span><span class="sxs-lookup"><span data-stu-id="0492a-107">**Retry attempts**</span></span>  
 <span data-ttu-id="0492a-108">Consente di impostare il numero di tentativi eseguiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per ripetere un passaggio di processo non riuscito.</span><span class="sxs-lookup"><span data-stu-id="0492a-108">Sets the number of times that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent attempts to retry a failed job step.</span></span>  
  
 <span data-ttu-id="0492a-109">**Intervallo tra i tentativi (minuti)**</span><span class="sxs-lookup"><span data-stu-id="0492a-109">**Retry interval (minutes)**</span></span>  
 <span data-ttu-id="0492a-110">Consente di impostare l'intervallo di attesa di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tra l'esecuzione di un tentativo e l'altro.</span><span class="sxs-lookup"><span data-stu-id="0492a-110">Sets the amount of time for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to wait between retry attempts.</span></span>  
  
 <span data-ttu-id="0492a-111">**Azione in caso di esito negativo**</span><span class="sxs-lookup"><span data-stu-id="0492a-111">**On failure action**</span></span>  
 <span data-ttu-id="0492a-112">Consente di impostare l'azione che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve eseguire in caso di esito negativo del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-112">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step fails.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="0492a-113">Opzioni per i passaggi del processo Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0492a-113">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="0492a-114">**File di output**</span><span class="sxs-lookup"><span data-stu-id="0492a-114">**Output file**</span></span>  
 <span data-ttu-id="0492a-115">Consente di impostare il file da utilizzare per l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-115">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="0492a-116">Questa opzione è disponibile solo per i membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0492a-116">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="0492a-117">**...**</span><span class="sxs-lookup"><span data-stu-id="0492a-117">**...**</span></span>  
 <span data-ttu-id="0492a-118">Selezionare il file da utilizzare per l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-118">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="0492a-119">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="0492a-119">**View**</span></span>  
 <span data-ttu-id="0492a-120">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , questo pulsante è disabilitato per la visualizzazione dei file di output.</span><span class="sxs-lookup"><span data-stu-id="0492a-120">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="0492a-121">In alternativa, utilizzare Notepad per visualizzare i file di output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-121">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="0492a-122">**Accoda output a file esistente**</span><span class="sxs-lookup"><span data-stu-id="0492a-122">**Append output to existing file**</span></span>  
 <span data-ttu-id="0492a-123">Consente di accodare l'output al contenuto già esistente nel file.</span><span class="sxs-lookup"><span data-stu-id="0492a-123">Append output to the existing contents of the file.</span></span> <span data-ttu-id="0492a-124">Diversamente, il precedente contenuto del file viene sovrascritto ogni volta che il passaggio di processo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0492a-124">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="0492a-125">**Registra nella tabella**</span><span class="sxs-lookup"><span data-stu-id="0492a-125">**Log to table**</span></span>  
 <span data-ttu-id="0492a-126">Consente di registrare l'output del passaggio di processo nella tabella **sysjobstepslogs** del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="0492a-126">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="0492a-127">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="0492a-127">**View**</span></span>  
 <span data-ttu-id="0492a-128">Dopo avere eseguito almeno una volta il passaggio di processo, fare clic su **Visualizza** per visualizzare l'output corrispondente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0492a-128">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="0492a-129">**Accoda output a voce esistente nella tabella**</span><span class="sxs-lookup"><span data-stu-id="0492a-129">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="0492a-130">Consente di accodare l'output al contenuto già esistente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0492a-130">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="0492a-131">Diversamente, il precedente contenuto della tabella viene sovrascritto ogni volta che il passaggio di processo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0492a-131">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="0492a-132">**Includi output passaggio nella cronologia**</span><span class="sxs-lookup"><span data-stu-id="0492a-132">**Include step output in history**</span></span>  
 <span data-ttu-id="0492a-133">Selezionare questa opzione per includere l'output del passaggio di processo nella cronologia processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-133">Select this option to include output from the job step in the job history.</span></span>  
  
 <span data-ttu-id="0492a-134">**Esegui come utente**</span><span class="sxs-lookup"><span data-stu-id="0492a-134">**Run as user**</span></span>  
 <span data-ttu-id="0492a-135">Se si è membri del ruolo predefinito del server **sysadmin** , è possibile selezionare un altro account di accesso SQL per eseguire questo passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-135">If you are a member of the **sysadmin** fixed server role, you can select another SQL login to run this job step.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="0492a-136">Opzioni per i passaggi del processo Sistema operativo (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="0492a-136">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="0492a-137">**File di output**</span><span class="sxs-lookup"><span data-stu-id="0492a-137">**Output file**</span></span>  
 <span data-ttu-id="0492a-138">Consente di impostare il file da utilizzare per l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-138">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="0492a-139">**...**</span><span class="sxs-lookup"><span data-stu-id="0492a-139">**...**</span></span>  
 <span data-ttu-id="0492a-140">Selezionare il file da utilizzare per l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-140">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="0492a-141">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="0492a-141">**View**</span></span>  
 <span data-ttu-id="0492a-142">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , questo pulsante è disabilitato per la visualizzazione dei file di output.</span><span class="sxs-lookup"><span data-stu-id="0492a-142">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="0492a-143">In alternativa, utilizzare Notepad per visualizzare i file di output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-143">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="0492a-144">**Accoda output a file esistente**</span><span class="sxs-lookup"><span data-stu-id="0492a-144">**Append output to existing file**</span></span>  
 <span data-ttu-id="0492a-145">Consente di accordare l'output del passaggio di processo al precedente contenuto del file ogni volta che il passaggio di processo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0492a-145">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="0492a-146">**Registra nella tabella**</span><span class="sxs-lookup"><span data-stu-id="0492a-146">**Log to table**</span></span>  
 <span data-ttu-id="0492a-147">Consente di registrare l'output del passaggio di processo nella tabella **sysjobstepslogs** del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="0492a-147">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="0492a-148">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="0492a-148">**View**</span></span>  
 <span data-ttu-id="0492a-149">Dopo avere eseguito almeno una volta il passaggio di processo, fare clic su **Visualizza** per visualizzare l'output corrispondente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0492a-149">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="0492a-150">**Accoda output a voce esistente nella tabella**</span><span class="sxs-lookup"><span data-stu-id="0492a-150">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="0492a-151">Consente di accodare l'output al contenuto già esistente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0492a-151">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="0492a-152">Diversamente, il precedente contenuto della tabella viene sovrascritto ogni volta che il passaggio di processo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0492a-152">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="0492a-153">**Includi output passaggio nella cronologia**</span><span class="sxs-lookup"><span data-stu-id="0492a-153">**Include step output in history**</span></span>  
 <span data-ttu-id="0492a-154">Selezionare questa opzione per includere l'output del passaggio di processo nella cronologia processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-154">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="0492a-155">Opzioni per i passaggi di processo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="0492a-155">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="0492a-156">**File di output**</span><span class="sxs-lookup"><span data-stu-id="0492a-156">**Output file**</span></span>  
 <span data-ttu-id="0492a-157">Consente di impostare il file da utilizzare per l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-157">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="0492a-158">**...**</span><span class="sxs-lookup"><span data-stu-id="0492a-158">**...**</span></span>  
 <span data-ttu-id="0492a-159">Selezionare il file da utilizzare per l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-159">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="0492a-160">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="0492a-160">**View**</span></span>  
 <span data-ttu-id="0492a-161">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , questo pulsante è disabilitato per la visualizzazione dei file di output.</span><span class="sxs-lookup"><span data-stu-id="0492a-161">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="0492a-162">In alternativa, utilizzare Notepad per visualizzare i file di output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-162">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="0492a-163">**Accoda output a file esistente**</span><span class="sxs-lookup"><span data-stu-id="0492a-163">**Append output to existing file**</span></span>  
 <span data-ttu-id="0492a-164">Consente di accordare l'output del passaggio di processo al precedente contenuto del file ogni volta che il passaggio di processo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0492a-164">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="0492a-165">**Registra nella tabella**</span><span class="sxs-lookup"><span data-stu-id="0492a-165">**Log to table**</span></span>  
 <span data-ttu-id="0492a-166">Consente di registrare l'output del passaggio di processo nella tabella **sysjobstepslogs** del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="0492a-166">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="0492a-167">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="0492a-167">**View**</span></span>  
 <span data-ttu-id="0492a-168">Dopo avere eseguito almeno una volta il passaggio di processo, fare clic su **Visualizza** per visualizzare l'output corrispondente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0492a-168">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="0492a-169">**Accoda output a voce esistente nella tabella**</span><span class="sxs-lookup"><span data-stu-id="0492a-169">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="0492a-170">Consente di accodare l'output al contenuto già esistente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0492a-170">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="0492a-171">Diversamente, il precedente contenuto della tabella viene sovrascritto ogni volta che il passaggio di processo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0492a-171">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="0492a-172">**Includi output passaggio nella cronologia**</span><span class="sxs-lookup"><span data-stu-id="0492a-172">**Include step output in history**</span></span>  
 <span data-ttu-id="0492a-173">Selezionare questa opzione per includere l'output del passaggio di processo nella cronologia processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-173">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="0492a-174">Opzioni per i passaggi del processo Lettura coda repliche</span><span class="sxs-lookup"><span data-stu-id="0492a-174">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="0492a-175">**Server**</span><span class="sxs-lookup"><span data-stu-id="0492a-175">**Server**</span></span>  
 <span data-ttu-id="0492a-176">Consente di impostare il server da utilizzare per un passaggio di processo Lettura coda repliche.</span><span class="sxs-lookup"><span data-stu-id="0492a-176">Sets the server to use for a replication queue reader job step.</span></span>  
  
 <span data-ttu-id="0492a-177">**Database**</span><span class="sxs-lookup"><span data-stu-id="0492a-177">**Database**</span></span>  
 <span data-ttu-id="0492a-178">Consente di impostare il database da utilizzare per un passaggio di processo Lettura coda repliche.</span><span class="sxs-lookup"><span data-stu-id="0492a-178">Sets the database to use for a replication queue reader job step.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-job-steps"></a><span data-ttu-id="0492a-179">Opzioni per i passaggi del processo SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0492a-179">Options for SQL Server Analysis Services Job Steps</span></span>  
 <span data-ttu-id="0492a-180">**File di output**</span><span class="sxs-lookup"><span data-stu-id="0492a-180">**Output file**</span></span>  
 <span data-ttu-id="0492a-181">Consente di impostare il file da utilizzare per l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-181">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="0492a-182">Questa opzione è disponibile solo per i membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0492a-182">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="0492a-183">**...**</span><span class="sxs-lookup"><span data-stu-id="0492a-183">**...**</span></span>  
 <span data-ttu-id="0492a-184">Selezionare il file da utilizzare per l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-184">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="0492a-185">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="0492a-185">**View**</span></span>  
 <span data-ttu-id="0492a-186">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], questo pulsante è disabilitato per la visualizzazione di file di output.</span><span class="sxs-lookup"><span data-stu-id="0492a-186">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="0492a-187">In alternativa, utilizzare Notepad per visualizzare i file di output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-187">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="0492a-188">**Accoda output a file esistente**</span><span class="sxs-lookup"><span data-stu-id="0492a-188">**Append output to existing file**</span></span>  
 <span data-ttu-id="0492a-189">Consente di accodare l'output al contenuto già esistente nel file.</span><span class="sxs-lookup"><span data-stu-id="0492a-189">Append output to the existing contents of the file.</span></span> <span data-ttu-id="0492a-190">Diversamente, il precedente contenuto del file viene sovrascritto ogni volta che il passaggio di processo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0492a-190">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="0492a-191">**Registra nella tabella**</span><span class="sxs-lookup"><span data-stu-id="0492a-191">**Log to table**</span></span>  
 <span data-ttu-id="0492a-192">Consente di registrare l'output del passaggio di processo nella tabella **sysjobstepslogs** del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="0492a-192">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="0492a-193">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="0492a-193">**View**</span></span>  
 <span data-ttu-id="0492a-194">Dopo avere eseguito almeno una volta il passaggio di processo, fare clic su **Visualizza** per visualizzare l'output corrispondente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0492a-194">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="0492a-195">**Accoda output a voce esistente nella tabella**</span><span class="sxs-lookup"><span data-stu-id="0492a-195">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="0492a-196">Consente di accodare l'output al contenuto già esistente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0492a-196">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="0492a-197">Diversamente, il precedente contenuto della tabella viene sovrascritto ogni volta che il passaggio di processo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0492a-197">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="0492a-198">**Includi output passaggio nella cronologia**</span><span class="sxs-lookup"><span data-stu-id="0492a-198">**Include step output in history**</span></span>  
 <span data-ttu-id="0492a-199">Selezionare questa opzione per includere l'output del passaggio di processo nella cronologia processo.</span><span class="sxs-lookup"><span data-stu-id="0492a-199">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0492a-200">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0492a-200">See Also</span></span>  
 [<span data-ttu-id="0492a-201">Gestire passaggi di processo</span><span class="sxs-lookup"><span data-stu-id="0492a-201">Manage Job Steps</span></span>](manage-job-steps.md)  
  
  
