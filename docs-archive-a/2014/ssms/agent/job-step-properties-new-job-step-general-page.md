---
title: 'Proprietà passaggio processo: nuovo passaggio di processo (pagina generale) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepgeneral.f1
ms.assetid: 8d1885ba-4386-4528-8f2b-68c16852720c
author: stevestein
ms.author: sstein
ms.openlocfilehash: c76e1ecb69a1475ec102f143a6a1ca34fbf91e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635320"
---
# <a name="job-step-properties-new-job-step-general-page"></a><span data-ttu-id="f0134-102">Proprietà passaggio processo: Nuovo passaggio di processo (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="f0134-102">Job Step Properties: New Job Step (General Page)</span></span>
  <span data-ttu-id="f0134-103">Utilizzare questa pagina per visualizzare e modificare le proprietà di un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passaggio di processo di Agent oppure per definire un nuovo passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step, or to define a new job step.</span></span>  
  
 <span data-ttu-id="f0134-104">Per passare a questa pagina, in Esplora oggetti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] espandere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, fare clic con il pulsante destro del mouse su **Processi**, scegliere **Nuovo processo**, selezionare la pagina **Passaggi** e scegliere **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f0134-104">To navigate to this page, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, click **New Jobs**, select the **Steps** page, and click **New**.</span></span> <span data-ttu-id="f0134-105">È anche possibile passare a questa pagina facendo clic con il pulsante destro del mouse su un processo in Esplora oggetti, scegliendo **Proprietà**, selezionando la pagina **Passaggi** e scegliendo **Nuovo**, **Inserisci**o **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f0134-105">You can also navigate to this page by right-clicking a job in Object Explorer, clicking **Properties**, selecting the **Steps** page, and clicking **New**, **Insert**, or **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0134-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f0134-106">Options</span></span>  
 <span data-ttu-id="f0134-107">**Nome passaggio**</span><span class="sxs-lookup"><span data-stu-id="f0134-107">**Step name**</span></span>  
 <span data-ttu-id="f0134-108">Consente di impostare il nome del passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-108">Set the name of the job step.</span></span>  
  
 <span data-ttu-id="f0134-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f0134-109">**Type**</span></span>  
 <span data-ttu-id="f0134-110">Consente di impostare il sottosistema utilizzato dal passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-110">Set the subsystem that the job step uses.</span></span> <span data-ttu-id="f0134-111">In base al sottosistema scelto, le opzioni visualizzate per la definizione del passaggio del processo sono diverse.</span><span class="sxs-lookup"><span data-stu-id="f0134-111">Based on the subsystem you choose, the options displayed for defining the job step change.</span></span>  
  
 <span data-ttu-id="f0134-112">**Esegui come**</span><span class="sxs-lookup"><span data-stu-id="f0134-112">**Run as**</span></span>  
 <span data-ttu-id="f0134-113">Consente di impostare l'account proxy per il passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-113">Set the proxy account for the job step.</span></span> <span data-ttu-id="f0134-114">I membri del ruolo predefinito del server sysadmin possono specificare anche l' **account del servizio SQL Agent**.</span><span class="sxs-lookup"><span data-stu-id="f0134-114">Members of the sysadmin fixed server role may also specify the **SQL Agent Service Account**.</span></span>  
  
 <span data-ttu-id="f0134-115">**Database**</span><span class="sxs-lookup"><span data-stu-id="f0134-115">**Database**</span></span>  
 <span data-ttu-id="f0134-116">Imposta il database in cui viene eseguito il passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-116">Set the database that the job step runs in.</span></span> <span data-ttu-id="f0134-117">Questa opzione non è disponibile per tutti i tipi di passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-117">This option is not available for all job step types.</span></span>  
  
 <span data-ttu-id="f0134-118">**Comando**</span><span class="sxs-lookup"><span data-stu-id="f0134-118">**Command**</span></span>  
 <span data-ttu-id="f0134-119">Consente di impostare il comando eseguito dal passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-119">Set the command that the job step runs.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="f0134-120">Opzioni per i passaggi del processo Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0134-120">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="f0134-121">**Apri**</span><span class="sxs-lookup"><span data-stu-id="f0134-121">**Open**</span></span>  
 <span data-ttu-id="f0134-122">Consente di caricare il comando da un file.</span><span class="sxs-lookup"><span data-stu-id="f0134-122">Load the command from a file.</span></span>  
  
 <span data-ttu-id="f0134-123">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-123">**Select All**</span></span>  
 <span data-ttu-id="f0134-124">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-124">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-125">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-125">**Copy**</span></span>  
 <span data-ttu-id="f0134-126">Consente di copiare il testo selezionato negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-126">Copy the selected text to the Clipboard.</span></span>  
  
 <span data-ttu-id="f0134-127">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-127">**Paste**</span></span>  
 <span data-ttu-id="f0134-128">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-128">Paste the contents of the Clipboard.</span></span>  
  
 <span data-ttu-id="f0134-129">**Parse**.</span><span class="sxs-lookup"><span data-stu-id="f0134-129">**Parse**</span></span>  
 <span data-ttu-id="f0134-130">Consente di verificare la sintassi del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-130">Check the syntax of the command.</span></span>  
  
## <a name="options-for-activex-script-job-steps"></a><span data-ttu-id="f0134-131">Opzioni per i passaggi del processo Script ActiveX</span><span class="sxs-lookup"><span data-stu-id="f0134-131">Options for ActiveX Script Job Steps</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f0134-132">Il sottosistema di scripting ActiveX verrà rimosso da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in una versione futura di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0134-132">The ActiveX Scripting subsystem will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f0134-133">Evitare di usare questa funzionalità in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui è attualmente implementata.</span><span class="sxs-lookup"><span data-stu-id="f0134-133">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="f0134-134">**VBScript**</span><span class="sxs-lookup"><span data-stu-id="f0134-134">**VBScript**</span></span>  
 <span data-ttu-id="f0134-135">Consente di specificare [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition come linguaggio per i passaggi del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-135">Specify [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition as the language for the job steps.</span></span>  
  
 <span data-ttu-id="f0134-136">**JScript**</span><span class="sxs-lookup"><span data-stu-id="f0134-136">**JScript**</span></span>  
 <span data-ttu-id="f0134-137">Consente di specificare JScript come linguaggio per i passaggi del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-137">Specify JScript as the language for the job steps.</span></span>  
  
 <span data-ttu-id="f0134-138">**Altri**</span><span class="sxs-lookup"><span data-stu-id="f0134-138">**Other**</span></span>  
 <span data-ttu-id="f0134-139">Consente di digitare il nome del linguaggio per i passaggi del processo scritti in un altro linguaggio di scripting.</span><span class="sxs-lookup"><span data-stu-id="f0134-139">Type the name of the language for job steps written in another scripting language.</span></span>  
  
 <span data-ttu-id="f0134-140">**Apri**</span><span class="sxs-lookup"><span data-stu-id="f0134-140">**Open**</span></span>  
 <span data-ttu-id="f0134-141">Consente di caricare il comando da un file.</span><span class="sxs-lookup"><span data-stu-id="f0134-141">Load the command from a file.</span></span>  
  
 <span data-ttu-id="f0134-142">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-142">**Select All**</span></span>  
 <span data-ttu-id="f0134-143">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-143">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-144">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-144">**Copy**</span></span>  
 <span data-ttu-id="f0134-145">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-145">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-146">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-146">**Paste**</span></span>  
 <span data-ttu-id="f0134-147">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-147">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="f0134-148">Opzioni per i passaggi del processo Sistema operativo (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="f0134-148">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="f0134-149">**Elabora codice di uscita di un comando eseguito correttamente**</span><span class="sxs-lookup"><span data-stu-id="f0134-149">**Process exit code of a successful command**</span></span>  
 <span data-ttu-id="f0134-150">Consente di digitare il codice di uscita restituito dal comando per indicare il corretto completamento.</span><span class="sxs-lookup"><span data-stu-id="f0134-150">Type the exit code that the command returns to indicate success.</span></span>  
  
 <span data-ttu-id="f0134-151">**Apri**</span><span class="sxs-lookup"><span data-stu-id="f0134-151">**Open**</span></span>  
 <span data-ttu-id="f0134-152">Consente di caricare il comando da un file.</span><span class="sxs-lookup"><span data-stu-id="f0134-152">Load the command from a file.</span></span>  
  
 <span data-ttu-id="f0134-153">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-153">**Select All**</span></span>  
 <span data-ttu-id="f0134-154">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-154">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-155">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-155">**Copy**</span></span>  
 <span data-ttu-id="f0134-156">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-156">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-157">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-157">**Paste**</span></span>  
 <span data-ttu-id="f0134-158">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-158">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="f0134-159">Opzioni per i passaggi di processo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0134-159">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="f0134-160">**Apri**</span><span class="sxs-lookup"><span data-stu-id="f0134-160">**Open**</span></span>  
 <span data-ttu-id="f0134-161">Consente di caricare lo script da un file.</span><span class="sxs-lookup"><span data-stu-id="f0134-161">Load the script from a file.</span></span>  
  
 <span data-ttu-id="f0134-162">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-162">**Select All**</span></span>  
 <span data-ttu-id="f0134-163">Consente di selezionare il testo dello script.</span><span class="sxs-lookup"><span data-stu-id="f0134-163">Select the text of the script.</span></span>  
  
 <span data-ttu-id="f0134-164">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-164">**Copy**</span></span>  
 <span data-ttu-id="f0134-165">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-165">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-166">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-166">**Paste**</span></span>  
 <span data-ttu-id="f0134-167">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-167">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-distributor-job-steps"></a><span data-ttu-id="f0134-168">Opzioni per i passaggi del processo Server di distribuzione repliche</span><span class="sxs-lookup"><span data-stu-id="f0134-168">Options for Replication Distributor Job Steps</span></span>  
 <span data-ttu-id="f0134-169">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-169">**Select All**</span></span>  
 <span data-ttu-id="f0134-170">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-170">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-171">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-171">**Copy**</span></span>  
 <span data-ttu-id="f0134-172">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-172">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-173">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-173">**Paste**</span></span>  
 <span data-ttu-id="f0134-174">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-174">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-merge-job-steps"></a><span data-ttu-id="f0134-175">Opzioni per i passaggi del processo Merge repliche</span><span class="sxs-lookup"><span data-stu-id="f0134-175">Options for Replication Merge Job Steps</span></span>  
 <span data-ttu-id="f0134-176">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-176">**Select All**</span></span>  
 <span data-ttu-id="f0134-177">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-177">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-178">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-178">**Copy**</span></span>  
 <span data-ttu-id="f0134-179">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-179">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-180">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-180">**Paste**</span></span>  
 <span data-ttu-id="f0134-181">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-181">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="f0134-182">Opzioni per i passaggi del processo Lettura coda repliche</span><span class="sxs-lookup"><span data-stu-id="f0134-182">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="f0134-183">**Database**</span><span class="sxs-lookup"><span data-stu-id="f0134-183">**Database**</span></span>  
 <span data-ttu-id="f0134-184">Database da utilizzare per il passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-184">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="f0134-185">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-185">**Select All**</span></span>  
 <span data-ttu-id="f0134-186">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-186">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-187">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-187">**Copy**</span></span>  
 <span data-ttu-id="f0134-188">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-188">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-189">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-189">**Paste**</span></span>  
 <span data-ttu-id="f0134-190">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-190">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-snapshot-job-steps"></a><span data-ttu-id="f0134-191">Opzioni per i passaggi del processo Snapshot repliche</span><span class="sxs-lookup"><span data-stu-id="f0134-191">Options for Replication Snapshot Job Steps</span></span>  
 <span data-ttu-id="f0134-192">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-192">**Select All**</span></span>  
 <span data-ttu-id="f0134-193">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-193">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-194">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-194">**Copy**</span></span>  
 <span data-ttu-id="f0134-195">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-195">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-196">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-196">**Paste**</span></span>  
 <span data-ttu-id="f0134-197">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-197">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-transaction-log-reader-job-steps"></a><span data-ttu-id="f0134-198">Opzioni per i passaggi del processo Lettura log delle transazioni di replica</span><span class="sxs-lookup"><span data-stu-id="f0134-198">Options for Replication Transaction-Log Reader Job Steps</span></span>  
 <span data-ttu-id="f0134-199">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-199">**Select All**</span></span>  
 <span data-ttu-id="f0134-200">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-200">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-201">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-201">**Copy**</span></span>  
 <span data-ttu-id="f0134-202">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-202">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-203">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-203">**Paste**</span></span>  
 <span data-ttu-id="f0134-204">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-204">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-command-job-steps"></a><span data-ttu-id="f0134-205">Opzioni per i passaggi del processo Comando di SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f0134-205">Options for SQL Server Analysis Services Command Job Steps</span></span>  
 <span data-ttu-id="f0134-206">**Server**</span><span class="sxs-lookup"><span data-stu-id="f0134-206">**Server**</span></span>  
 <span data-ttu-id="f0134-207">Consente di selezionare il server in cui viene eseguito il passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-207">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="f0134-208">**Apri**</span><span class="sxs-lookup"><span data-stu-id="f0134-208">**Open**</span></span>  
 <span data-ttu-id="f0134-209">Consente di caricare il comando da un file.</span><span class="sxs-lookup"><span data-stu-id="f0134-209">Load the command from a file.</span></span>  
  
 <span data-ttu-id="f0134-210">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-210">**Select All**</span></span>  
 <span data-ttu-id="f0134-211">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-211">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-212">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-212">**Copy**</span></span>  
 <span data-ttu-id="f0134-213">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-213">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-214">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-214">**Paste**</span></span>  
 <span data-ttu-id="f0134-215">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-215">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-query-job-steps"></a><span data-ttu-id="f0134-216">Opzioni per i passaggi del processo Query di SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f0134-216">Options for SQL Server Analysis Services Query Job Steps</span></span>  
 <span data-ttu-id="f0134-217">**Server**</span><span class="sxs-lookup"><span data-stu-id="f0134-217">**Server**</span></span>  
 <span data-ttu-id="f0134-218">Consente di selezionare il server in cui viene eseguito il passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-218">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="f0134-219">**Database**</span><span class="sxs-lookup"><span data-stu-id="f0134-219">**Database**</span></span>  
 <span data-ttu-id="f0134-220">Database da utilizzare per il passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-220">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="f0134-221">**Apri**</span><span class="sxs-lookup"><span data-stu-id="f0134-221">**Open**</span></span>  
 <span data-ttu-id="f0134-222">Consente di caricare il comando da un file.</span><span class="sxs-lookup"><span data-stu-id="f0134-222">Load the command from a file.</span></span>  
  
 <span data-ttu-id="f0134-223">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="f0134-223">**Select All**</span></span>  
 <span data-ttu-id="f0134-224">Consente di selezionare il testo del comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-224">Select the text of the command.</span></span>  
  
 <span data-ttu-id="f0134-225">**Copia**</span><span class="sxs-lookup"><span data-stu-id="f0134-225">**Copy**</span></span>  
 <span data-ttu-id="f0134-226">Consente di copiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-226">Copy the selected text.</span></span>  
  
 <span data-ttu-id="f0134-227">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="f0134-227">**Paste**</span></span>  
 <span data-ttu-id="f0134-228">Consente di incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f0134-228">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-integration-services-package-execution-job-steps"></a><span data-ttu-id="f0134-229">Opzioni per i passaggi del processo di esecuzione del pacchetto Integration Services</span><span class="sxs-lookup"><span data-stu-id="f0134-229">Options for Integration Services Package Execution Job Steps</span></span>  
  
### <a name="general-tab"></a><span data-ttu-id="f0134-230">Scheda Generale</span><span class="sxs-lookup"><span data-stu-id="f0134-230">General Tab</span></span>  
 <span data-ttu-id="f0134-231">Consente di specificare la posizione del pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) e il metodo di autenticazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f0134-231">Specify where the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package is located and what authentication method to use.</span></span> <span data-ttu-id="f0134-232">In questa scheda sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f0134-232">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="f0134-233">**Origine pacchetto**</span><span class="sxs-lookup"><span data-stu-id="f0134-233">**Package source**</span></span>  
 <span data-ttu-id="f0134-234">Consente di specificare la posizione in cui è archiviato il pacchetto [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0134-234">Specify where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="f0134-235">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0134-235">Choose one of the following:</span></span>  
  
-   <span data-ttu-id="f0134-236">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f0134-236">**SQL Server**</span></span>  
  
-   <span data-ttu-id="f0134-237">**File system**</span><span class="sxs-lookup"><span data-stu-id="f0134-237">**File system**</span></span>  
  
-   <span data-ttu-id="f0134-238">**Archivio pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="f0134-238">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="f0134-239">**Server**</span><span class="sxs-lookup"><span data-stu-id="f0134-239">**Server**</span></span>  
 <span data-ttu-id="f0134-240">Consente di digitare il nome del server in cui è archiviato il pacchetto [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0134-240">Type the server name where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="f0134-241">Questa opzione è disponibile solo se è impostato **SQL Server** o **Archivio pacchetti SSIS** come **Origine pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="f0134-241">This option is only available when **SQL Server** or **SSIS Package Store** is specified for **Package Source**.</span></span>  
  
 <span data-ttu-id="f0134-242">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="f0134-242">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="f0134-243">Consente di accedere a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="f0134-243">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="f0134-244">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f0134-244">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="f0134-245">Consente di accedere a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0134-245">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="f0134-246">Se si seleziona questo metodo di autenticazione, immettere il **Nome utente** e la **Password corretti**.</span><span class="sxs-lookup"><span data-stu-id="f0134-246">If this method of authentication is selected, enter the appropriate **User name** and **Password**.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f0134-247">L'autenticazione è disponibile per garantire la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="f0134-247">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="f0134-248">Per un livello di sicurezza migliore, utilizzare l'autenticazione di Windows, se possibile.</span><span class="sxs-lookup"><span data-stu-id="f0134-248">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="f0134-249">**Pacchetto**</span><span class="sxs-lookup"><span data-stu-id="f0134-249">**Package**</span></span>  
 <span data-ttu-id="f0134-250">Consente di digitare la posizione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-250">Type the location of the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f0134-251">Per pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] protetti da password, fare clic sulla scheda **Configurazioni** e immettere la password nella finestra di dialogo **Password pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="f0134-251">For password-protected [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages, click the **Configurations** tab to enter the password in the **Package Password** dialog box.</span></span> <span data-ttu-id="f0134-252">In caso contrario, il processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in cui viene eseguito il pacchetto protetto da password avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f0134-252">Otherwise, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that executes the password-protected package will fail.</span></span>  
  
### <a name="configurations-tab"></a><span data-ttu-id="f0134-253">Scheda Configurazioni</span><span class="sxs-lookup"><span data-stu-id="f0134-253">Configurations Tab</span></span>  
 <span data-ttu-id="f0134-254">Consente di specificare le opzioni di configurazione per il pacchetto [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0134-254">Specify configuration options for the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span> <span data-ttu-id="f0134-255">In questa scheda sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f0134-255">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="f0134-256">**File di configurazione**</span><span class="sxs-lookup"><span data-stu-id="f0134-256">**Configuration files**</span></span>  
 <span data-ttu-id="f0134-257">Consente di elencare i file di configurazione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-257">Lists the configuration files for the package.</span></span>  
  
 <span data-ttu-id="f0134-258">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="f0134-258">**Add**</span></span>  
 <span data-ttu-id="f0134-259">Consente di aggiungere un file di configurazione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-259">Add a configuration file for the package.</span></span>  
  
 <span data-ttu-id="f0134-260">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="f0134-260">**Remove**</span></span>  
 <span data-ttu-id="f0134-261">Consente di rimuovere un file di configurazione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-261">Remove a configuration file for the package.</span></span>  
  
 <span data-ttu-id="f0134-262">**Sposta su**</span><span class="sxs-lookup"><span data-stu-id="f0134-262">**Move Up**</span></span>  
 <span data-ttu-id="f0134-263">Consente di spostare il file di configurazione selezionato verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="f0134-263">Move the selected configuration file up.</span></span>  
  
 <span data-ttu-id="f0134-264">**Sposta giù**</span><span class="sxs-lookup"><span data-stu-id="f0134-264">**Move Down**</span></span>  
 <span data-ttu-id="f0134-265">Consente di spostare il file di configurazione selezionato verso il basso.</span><span class="sxs-lookup"><span data-stu-id="f0134-265">Move the selected configuration file down.</span></span>  
  
### <a name="command-files-tab"></a><span data-ttu-id="f0134-266">Scheda File di comando</span><span class="sxs-lookup"><span data-stu-id="f0134-266">Command Files Tab</span></span>  
 <span data-ttu-id="f0134-267">Consente di selezionare i file di comando per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-267">Select command files for the package.</span></span> <span data-ttu-id="f0134-268">I file di comando vengono elaborati in base all'ordine in cui vengono visualizzati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f0134-268">Command files are processed in the order in which they appear in the list.</span></span> <span data-ttu-id="f0134-269">In questa scheda sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f0134-269">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="f0134-270">**File di comando**</span><span class="sxs-lookup"><span data-stu-id="f0134-270">**Command files**</span></span>  
 <span data-ttu-id="f0134-271">Consente di elencare i file di comando per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-271">Lists the command files for the package.</span></span>  
  
 <span data-ttu-id="f0134-272">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="f0134-272">**Add**</span></span>  
 <span data-ttu-id="f0134-273">Consente di aggiungere un file di comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-273">Add a command file.</span></span>  
  
 <span data-ttu-id="f0134-274">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="f0134-274">**Remove**</span></span>  
 <span data-ttu-id="f0134-275">Consente di rimuovere il file di comando selezionato.</span><span class="sxs-lookup"><span data-stu-id="f0134-275">Remove the selected command file.</span></span>  
  
 <span data-ttu-id="f0134-276">**Sposta su**</span><span class="sxs-lookup"><span data-stu-id="f0134-276">**Move Up**</span></span>  
 <span data-ttu-id="f0134-277">Consente di spostare il file di comando selezionato verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="f0134-277">Move the selected command file up.</span></span>  
  
 <span data-ttu-id="f0134-278">**Sposta giù**</span><span class="sxs-lookup"><span data-stu-id="f0134-278">**Move Down**</span></span>  
 <span data-ttu-id="f0134-279">Consente di spostare il file di comando selezionato verso il basso.</span><span class="sxs-lookup"><span data-stu-id="f0134-279">Move the selected command file down.</span></span>  
  
### <a name="data-sources-tab"></a><span data-ttu-id="f0134-280">Scheda Origini dati</span><span class="sxs-lookup"><span data-stu-id="f0134-280">Data Sources Tab</span></span>  
 <span data-ttu-id="f0134-281">Consente di visualizzare le origini dei dati specificate nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-281">View the data sources specified in the package on this tab.</span></span>  
  
 <span data-ttu-id="f0134-282">**Gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="f0134-282">**Connection Manager**</span></span>  
 <span data-ttu-id="f0134-283">Consente di visualizzare il nome dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="f0134-283">View the name of the data source.</span></span>  
  
 <span data-ttu-id="f0134-284">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f0134-284">**Description**</span></span>  
 <span data-ttu-id="f0134-285">Consente di visualizzare la descrizione dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="f0134-285">View the description of the data source.</span></span>  
  
 <span data-ttu-id="f0134-286">**Stringa di connessione**</span><span class="sxs-lookup"><span data-stu-id="f0134-286">**Connection String**</span></span>  
 <span data-ttu-id="f0134-287">Consente di visualizzare la stringa di connessione per l'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="f0134-287">View the connection string for the data source.</span></span>  
  
### <a name="execution-options-tab"></a><span data-ttu-id="f0134-288">Scheda Opzioni di esecuzione</span><span class="sxs-lookup"><span data-stu-id="f0134-288">Execution Options Tab</span></span>  
 <span data-ttu-id="f0134-289">Consente di visualizzare o modificare le opzioni di esecuzione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-289">View or change the execution options for the package on this tab.</span></span>  
  
 <span data-ttu-id="f0134-290">**Interrompi il pacchetto in caso di avvisi di convalida**</span><span class="sxs-lookup"><span data-stu-id="f0134-290">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="f0134-291">Selezionare questa opzione per interrompere l'esecuzione del pacchetto in caso di avvisi di convalida.</span><span class="sxs-lookup"><span data-stu-id="f0134-291">Select this option for package execution to fail if validation warnings occur.</span></span>  
  
 <span data-ttu-id="f0134-292">**Convalida pacchetto senza esecuzione**</span><span class="sxs-lookup"><span data-stu-id="f0134-292">**Validate package without executing**</span></span>  
 <span data-ttu-id="f0134-293">Selezionare questa opzione affinché il passaggio del processo esegua la convalida, ma non l'esecuzione, del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-293">Select this option for the job step to validate, but not execute, the package.</span></span>  
  
 <span data-ttu-id="f0134-294">**Numero massimo di file eseguibili simultanei**</span><span class="sxs-lookup"><span data-stu-id="f0134-294">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="f0134-295">Numero massimo di file eseguibili che è possibile eseguire simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f0134-295">Maximum number of executable files that can run at one time.</span></span>  
  
 <span data-ttu-id="f0134-296">**Abilita checkpoint pacchetto**</span><span class="sxs-lookup"><span data-stu-id="f0134-296">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="f0134-297">Selezionare questa opzione affinché il passaggio del processo utilizzi i checkpoint del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-297">Select this option for the job step to use package checkpoints.</span></span>  
  
 <span data-ttu-id="f0134-298">**File del checkpoint**</span><span class="sxs-lookup"><span data-stu-id="f0134-298">**Checkpoint file**</span></span>  
 <span data-ttu-id="f0134-299">Consente di digitare il nome del file del checkpoint del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-299">Type the name of the package checkpoint file.</span></span>  
  
 <span data-ttu-id="f0134-300">**...**</span><span class="sxs-lookup"><span data-stu-id="f0134-300">**...**</span></span>  
 <span data-ttu-id="f0134-301">Scegliere Sfoglia per individuare il file del checkpoint del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-301">Browse to find the package checkpoint file.</span></span>  
  
 <span data-ttu-id="f0134-302">**Ignora opzioni di riavvio**</span><span class="sxs-lookup"><span data-stu-id="f0134-302">**Override restart options**</span></span>  
 <span data-ttu-id="f0134-303">Selezionare questa opzione per specificare opzioni di riavvio per il passaggio del processo diverse da quelle specificate nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-303">Select this option to specify restart options for this job step that are different from the restart options specified in the package.</span></span>  
  
 <span data-ttu-id="f0134-304">**Opzione di riavvio**</span><span class="sxs-lookup"><span data-stu-id="f0134-304">**Restart option**</span></span>  
 <span data-ttu-id="f0134-305">Consente di selezionare l'azione da intraprendere al riavvio del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-305">Select the action to take when the package restarts.</span></span>  
  
### <a name="logging-tab"></a><span data-ttu-id="f0134-306">Scheda Registrazione</span><span class="sxs-lookup"><span data-stu-id="f0134-306">Logging Tab</span></span>  
 <span data-ttu-id="f0134-307">Consente di visualizzare o modificare i provider di log per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-307">View or change the log providers for the package on this tab.</span></span>  
  
 <span data-ttu-id="f0134-308">**Provider di log**</span><span class="sxs-lookup"><span data-stu-id="f0134-308">**Log Provider**</span></span>  
 <span data-ttu-id="f0134-309">Consente di selezionare il ClassID per il provider di log.</span><span class="sxs-lookup"><span data-stu-id="f0134-309">Select the ClassID for the log provider.</span></span>  
  
 <span data-ttu-id="f0134-310">**Stringa di configurazione**</span><span class="sxs-lookup"><span data-stu-id="f0134-310">**Configuration String**</span></span>  
 <span data-ttu-id="f0134-311">Consente di digitare la stringa di configurazione per il provider di log.</span><span class="sxs-lookup"><span data-stu-id="f0134-311">Type the configuration string for the log provider.</span></span>  
  
 <span data-ttu-id="f0134-312">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="f0134-312">**Remove**</span></span>  
 <span data-ttu-id="f0134-313">Consente di rimuovere il provider di log.</span><span class="sxs-lookup"><span data-stu-id="f0134-313">Removes the log provider.</span></span>  
  
### <a name="set-values-tab"></a><span data-ttu-id="f0134-314">Scheda Imposta valori</span><span class="sxs-lookup"><span data-stu-id="f0134-314">Set Values Tab</span></span>  
 <span data-ttu-id="f0134-315">Consente di visualizzare o modificare i valori delle proprietà per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-315">View or change property values for the package on this tab.</span></span>  
  
 <span data-ttu-id="f0134-316">**Percorso proprietà**</span><span class="sxs-lookup"><span data-stu-id="f0134-316">**Property path**</span></span>  
 <span data-ttu-id="f0134-317">Consente di visualizzare o modificare il percorso per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="f0134-317">View or change the path for the property.</span></span>  
  
 <span data-ttu-id="f0134-318">**Valore**</span><span class="sxs-lookup"><span data-stu-id="f0134-318">**Value**</span></span>  
 <span data-ttu-id="f0134-319">Consente di visualizzare o modificare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f0134-319">View or change the value for the property.</span></span>  
  
 <span data-ttu-id="f0134-320">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="f0134-320">**Remove**</span></span>  
 <span data-ttu-id="f0134-321">Consente di rimuovere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="f0134-321">Removes the property.</span></span>  
  
### <a name="verification-tab"></a><span data-ttu-id="f0134-322">Scheda Verifica</span><span class="sxs-lookup"><span data-stu-id="f0134-322">Verification Tab</span></span>  
 <span data-ttu-id="f0134-323">Consente di selezionare le opzioni di verifica per il passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f0134-323">Select the verification options for the job step on this tab.</span></span>  
  
 <span data-ttu-id="f0134-324">**Esegui solo pacchetti firmati**</span><span class="sxs-lookup"><span data-stu-id="f0134-324">**Execute only signed packages**</span></span>  
 <span data-ttu-id="f0134-325">Consente di eseguire solo i pacchetti firmati.</span><span class="sxs-lookup"><span data-stu-id="f0134-325">Run only packages that have been signed.</span></span> <span data-ttu-id="f0134-326">Se questa opzione è selezionata, il passaggio del processo viene interrotto se il pacchetto non è firmato.</span><span class="sxs-lookup"><span data-stu-id="f0134-326">When this option is selected, the job step fails if the package is unsigned.</span></span>  
  
 <span data-ttu-id="f0134-327">**Verificare la compilazione del pacchetto**</span><span class="sxs-lookup"><span data-stu-id="f0134-327">**Verify package build**</span></span>  
 <span data-ttu-id="f0134-328">Consente di eseguire solo i pacchetti con un numero di build specifico.</span><span class="sxs-lookup"><span data-stu-id="f0134-328">Run only packages with a specific build number.</span></span> <span data-ttu-id="f0134-329">Se questa opzione è selezionata, il passaggio del processo viene interrotto se il pacchetto non dispone del numero di build specifico.</span><span class="sxs-lookup"><span data-stu-id="f0134-329">When this option is selected, the job step fails if the package does not have the specified build number.</span></span>  
  
 <span data-ttu-id="f0134-330">**Build**</span><span class="sxs-lookup"><span data-stu-id="f0134-330">**Build**</span></span>  
 <span data-ttu-id="f0134-331">Consente di digitare il numero di build del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-331">Type the build number of the package.</span></span>  
  
 <span data-ttu-id="f0134-332">**Verifica ID pacchetto**</span><span class="sxs-lookup"><span data-stu-id="f0134-332">**Verify package ID**</span></span>  
 <span data-ttu-id="f0134-333">Consente di eseguire solo i pacchetti con un ID specifico.</span><span class="sxs-lookup"><span data-stu-id="f0134-333">Run only packages with a specific ID.</span></span> <span data-ttu-id="f0134-334">Se questa opzione è selezionata, il passaggio del processo viene interrotto se il pacchetto non dispone dell'ID specificato.</span><span class="sxs-lookup"><span data-stu-id="f0134-334">When this option is selected, the job step fails if the package does not have the specified ID.</span></span>  
  
 <span data-ttu-id="f0134-335">**ID pacchetto**</span><span class="sxs-lookup"><span data-stu-id="f0134-335">**Package ID**</span></span>  
 <span data-ttu-id="f0134-336">Consente di digitare l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-336">Type the package ID.</span></span>  
  
 <span data-ttu-id="f0134-337">**Verifica ID versione**</span><span class="sxs-lookup"><span data-stu-id="f0134-337">**Verify version ID**</span></span>  
 <span data-ttu-id="f0134-338">Consente di eseguire solo i pacchetti con un ID versione specifico.</span><span class="sxs-lookup"><span data-stu-id="f0134-338">Run only packages with a specific version ID.</span></span> <span data-ttu-id="f0134-339">Se questa opzione è selezionata, il passaggio del processo viene interrotto se il pacchetto non dispone dell'ID versione specificato.</span><span class="sxs-lookup"><span data-stu-id="f0134-339">When this option is selected, the job step fails if the package does not have the specified version ID.</span></span>  
  
 <span data-ttu-id="f0134-340">**ID versione**</span><span class="sxs-lookup"><span data-stu-id="f0134-340">**Version ID**</span></span>  
 <span data-ttu-id="f0134-341">Consente di digitare l'ID di versione.</span><span class="sxs-lookup"><span data-stu-id="f0134-341">Type the version ID.</span></span>  
  
### <a name="command-line-tab"></a><span data-ttu-id="f0134-342">Scheda Riga di comando</span><span class="sxs-lookup"><span data-stu-id="f0134-342">Command Line Tab</span></span>  
 <span data-ttu-id="f0134-343">Consente di specificare le opzioni della riga di comando per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-343">Specify command-line options for the package.</span></span> <span data-ttu-id="f0134-344">In questa scheda sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f0134-344">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="f0134-345">**Ripristina opzioni originali**</span><span class="sxs-lookup"><span data-stu-id="f0134-345">**Restore the original options**</span></span>  
 <span data-ttu-id="f0134-346">Consente di utilizzare le opzioni della riga di comando impostate in questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f0134-346">Use the command-line options set in this dialog.</span></span>  
  
 <span data-ttu-id="f0134-347">**Modifica riga di comando manualmente**</span><span class="sxs-lookup"><span data-stu-id="f0134-347">**Edit the command line manually**</span></span>  
 <span data-ttu-id="f0134-348">Consente di specificare le opzioni nella finestra della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f0134-348">Specify options in the command-line window.</span></span>  
  
 <span data-ttu-id="f0134-349">**Riga di comando**</span><span class="sxs-lookup"><span data-stu-id="f0134-349">**Command line**</span></span>  
 <span data-ttu-id="f0134-350">Consente di digitare le opzioni della riga di comando da utilizzare per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f0134-350">Type the command line options to use for this package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0134-351">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0134-351">See Also</span></span>  
 <span data-ttu-id="f0134-352">[Gestire passaggi di processo](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="f0134-352">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="f0134-353">[SQL Server Agent processi per i pacchetti](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span><span class="sxs-lookup"><span data-stu-id="f0134-353">[SQL Server Agent Jobs for Packages](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span></span>  
 [<span data-ttu-id="f0134-354">Amministrazione dell'agente di replica</span><span class="sxs-lookup"><span data-stu-id="f0134-354">Replication Agent Administration</span></span>](../../relational-databases/replication/agents/replication-agent-administration.md)  
  
  
