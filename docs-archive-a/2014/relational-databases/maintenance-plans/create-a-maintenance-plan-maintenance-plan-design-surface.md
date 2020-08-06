---
title: Creare un piano di manutenzione (area di progettazione del piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Maintenance Plan Design Surface
ms.assetid: 2ef803ee-a9f8-454a-ad63-fedcbe6838d1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77e347720824198ba7d6abaddedd7a581ace98a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635570"
---
# <a name="create-a-maintenance-plan-maintenance-plan-design-surface"></a><span data-ttu-id="973c2-102">Creare un piano di manutenzione (area di progettazione del piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="973c2-102">Create a Maintenance Plan (Maintenance Plan Design Surface)</span></span>
  <span data-ttu-id="973c2-103">In questo argomento viene descritto come creare un piano di manutenzione multiserver o di un singolo server utilizzando l'area di progettazione del piano di manutenzione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="973c2-103">This topic describes how to create a single server or multiserver maintenance plan using the Maintenance Plan Design Surface in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="973c2-104">Mentre la **Creazione guidata piano di manutenzione** è ideale per la creazione di piani di manutenzione di base, la creazione di un piano tramite l'area di progettazione consente di utilizzare un flusso di lavoro avanzato.</span><span class="sxs-lookup"><span data-stu-id="973c2-104">While the **Maintenance Plan Wizard** is best for creating basic maintenance plans, creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="973c2-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="973c2-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="973c2-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="973c2-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="973c2-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="973c2-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="973c2-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="973c2-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="973c2-109">Creazione di un piano di manutenzione tramite l'area di progettazione del piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="973c2-109">Creating a maintenance plan using the Maintenance Plan Design Surface</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="973c2-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="973c2-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="973c2-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="973c2-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="973c2-112">Per creare un piano di manutenzione multiserver, è necessario configurare un ambiente multiserver composto da un server master e uno o più server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="973c2-112">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="973c2-113">I piani di manutenzione multiserver devono essere creati e gestiti nel server master.</span><span class="sxs-lookup"><span data-stu-id="973c2-113">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="973c2-114">Questi piani possono essere visualizzati, ma non gestiti, nei server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="973c2-114">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
-   <span data-ttu-id="973c2-115">I membri dei ruoli **db_ssisadmin** e **dc_admin** possono essere in grado di elevare i privilegi a **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="973c2-115">Members of the **db_ssisadmin** and **dc_admin** roles may be able to elevate their privileges to **sysadmin**.</span></span> <span data-ttu-id="973c2-116">Questa elevazione dei privilegi può verificarsi perché tali ruoli possono modificare i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] . I pacchetti possono essere eseguiti in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando il contesto di sicurezza **sysadmin** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="973c2-116">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages; these packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **sysadmin** security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="973c2-117">Per impedire questa elevazione dei privilegi durante l'esecuzione di piani di manutenzione, set di raccolta dati e altri pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , configurare i processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che eseguono pacchetti in modo che usino un account proxy con privilegi limitati o aggiungere solo i membri **sysadmin** ai ruoli **db_ssisadmin** e **dc_admin** .</span><span class="sxs-lookup"><span data-stu-id="973c2-117">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add **sysadmin** members to the **db_ssisadmin** and **dc_admin** roles.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="973c2-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="973c2-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="973c2-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="973c2-119">Permissions</span></span>  
 <span data-ttu-id="973c2-120">Per creare o gestire piani di manutenzione, è necessario essere membro del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="973c2-120">To create or manage maintenance plans, you must be a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="973c2-121">In Esplora oggetti il nodo **Piani di manutenzione** viene visualizzato solo per gli utenti membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="973c2-121">Object Explorer only displays the **Maintenance Plans** node for users who are members of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-maintenance-plan-design-surface"></a><a name="SSMSProcedure"></a> <span data-ttu-id="973c2-122">Utilizzo dell'area di progettazione del piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="973c2-122">Using Maintenance Plan Design Surface</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="973c2-123">Per creare un piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="973c2-123">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="973c2-124">In Esplora oggetti fare clic sul segno più per espandere il server in cui si desidera creare un piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="973c2-124">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="973c2-125">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="973c2-125">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="973c2-126">Fare clic con il pulsante destro del mouse sulla cartella **Piani di manutenzione** e scegliere **Nuovo piano di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="973c2-126">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="973c2-127">Nella finestra di dialogo **Nuovo piano di manutenzione** digitare un nome per il piano nella casella **Nome** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="973c2-127">In the **New Maintenance Plan** dialog box, in the **Name** box, type a name for the plan and click **OK**.</span></span> <span data-ttu-id="973c2-128">Verranno visualizzate la casella degli strumenti e l'area _nome_piano_manutenzione_ **[Progettazione]** con il sottopiano **Sottopiano_1** creato nella griglia principale.</span><span class="sxs-lookup"><span data-stu-id="973c2-128">This opens the  Toolbox and the _maintenance_plan_name_ **[Design]** surface with the **Subplan_1** subplan created in the main grid.</span></span>  
  
     <span data-ttu-id="973c2-129">Nell'intestazione dell'area di progettazione sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="973c2-129">The following options are available in the design space's header.</span></span>  
  
     <span data-ttu-id="973c2-130">**Aggiungi sottopiano**</span><span class="sxs-lookup"><span data-stu-id="973c2-130">**Add Subplan**</span></span>  
     <span data-ttu-id="973c2-131">Consente di aggiungere un sottopiano configurabile.</span><span class="sxs-lookup"><span data-stu-id="973c2-131">Adds a subplan that you can configure.</span></span>  
  
     <span data-ttu-id="973c2-132">**Proprietà sottopiano**</span><span class="sxs-lookup"><span data-stu-id="973c2-132">**Subplan Properties**</span></span>  
     <span data-ttu-id="973c2-133">Consente di visualizzare la finestra di dialogo **Proprietà sottopiano** per il sottopiano selezionato nella griglia principale.</span><span class="sxs-lookup"><span data-stu-id="973c2-133">Displays the **Subplan Properties** dialog box for the selected subplan in the main grid.</span></span> <span data-ttu-id="973c2-134">In alternativa, è possibile fare doppio clic su un sottopiano nella griglia per visualizzare la finestra di dialogo **Proprietà sottopiano** .</span><span class="sxs-lookup"><span data-stu-id="973c2-134">Alternately, double-click a subplan in the grid to display the **Subplan Properties** dialog box.</span></span> <span data-ttu-id="973c2-135">Per ulteriori informazioni su questa finestra di dialogo, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="973c2-135">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="973c2-136">**Elimina sottopiano selezionato**</span><span class="sxs-lookup"><span data-stu-id="973c2-136">**Delete Selected Subplan**</span></span>  
     <span data-ttu-id="973c2-137">Consente di eliminare il sottopiano selezionato.</span><span class="sxs-lookup"><span data-stu-id="973c2-137">Deletes the selected subplan.</span></span>  
  
     <span data-ttu-id="973c2-138">**Pianificazione sottopiano**</span><span class="sxs-lookup"><span data-stu-id="973c2-138">**Subplan Schedule**</span></span>  
     <span data-ttu-id="973c2-139">Consente di visualizzare la finestra di dialogo **Nuova pianificazione processo** per il sottopiano selezionato.</span><span class="sxs-lookup"><span data-stu-id="973c2-139">Displays the **New Job Schedule** dialog box for the selected subplan.</span></span>  
  
     <span data-ttu-id="973c2-140">**Rimuovi pianificazione**</span><span class="sxs-lookup"><span data-stu-id="973c2-140">**Remove Schedule**</span></span>  
     <span data-ttu-id="973c2-141">Consente di rimuovere una pianificazione dal sottopiano selezionato.</span><span class="sxs-lookup"><span data-stu-id="973c2-141">Removes a schedule from the selected subplan.</span></span>  
  
     <span data-ttu-id="973c2-142">**Gestire le connessioni**</span><span class="sxs-lookup"><span data-stu-id="973c2-142">**Manage Connections**</span></span>  
     <span data-ttu-id="973c2-143">Consente di visualizzare la finestra di dialogo **Gestisci connessioni** .</span><span class="sxs-lookup"><span data-stu-id="973c2-143">Displays the **Manage Connections** dialog box.</span></span> <span data-ttu-id="973c2-144">Questa finestra di dialogo viene utilizzata per aggiungere ulteriori connessioni a istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="973c2-144">Used to add additional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance connections to the maintenance plan.</span></span> <span data-ttu-id="973c2-145">Per ulteriori informazioni su questa finestra di dialogo, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="973c2-145">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="973c2-146">**Report e registrazione**</span><span class="sxs-lookup"><span data-stu-id="973c2-146">**Reporting and Logging**</span></span>  
     <span data-ttu-id="973c2-147">Consente di visualizzare la finestra di dialogo **Report e registrazione** .</span><span class="sxs-lookup"><span data-stu-id="973c2-147">Displays the **Reporting and Logging** dialog box.</span></span> <span data-ttu-id="973c2-148">Per ulteriori informazioni su questa finestra di dialogo, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="973c2-148">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="973c2-149">**Server**</span><span class="sxs-lookup"><span data-stu-id="973c2-149">**Servers**</span></span>  
     <span data-ttu-id="973c2-150">Visualizza la finestra di dialogo **Server** usata per selezionare i server in cui verranno eseguite le attività del sottopiano.</span><span class="sxs-lookup"><span data-stu-id="973c2-150">Display the **Servers** dialog box, which is used to select the servers where the subplan tasks will be run.</span></span> <span data-ttu-id="973c2-151">Questa opzione è abilitata solo nei server master in ambienti multiserver.</span><span class="sxs-lookup"><span data-stu-id="973c2-151">This option is enabled only on master servers in multiserver environments.</span></span> <span data-ttu-id="973c2-152">Per altre informazioni, vedere [Creazione di un ambiente multiserver](../../ssms/agent/create-a-multiserver-environment.md) e [Piano di manutenzione & #40;Server& #41;](maintenance-plan-servers.md).</span><span class="sxs-lookup"><span data-stu-id="973c2-152">For more information, see [Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) and [Maintenance Plan &#40;Servers&#41;](maintenance-plan-servers.md).</span></span>  
  
     <span data-ttu-id="973c2-153">**Nome**</span><span class="sxs-lookup"><span data-stu-id="973c2-153">**Name**</span></span>  
     <span data-ttu-id="973c2-154">Consente di visualizzare il nome del piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="973c2-154">Display the maintenance plan name.</span></span> <span data-ttu-id="973c2-155">Il nome dei nuovi piani di manutenzione viene indicato in una finestra di dialogo visualizzata prima dell'apertura della finestra di progettazione dei piani di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="973c2-155">For new maintenance plans, the name is specified in a dialog box before the maintenance plan designer opens.</span></span> <span data-ttu-id="973c2-156">Per rinominare un piano di manutenzione, fare clic con il pulsante destro del mouse sul piano in Esplora oggetti e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="973c2-156">To rename a maintenance plan, right-click the plan in Object Explorer, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="973c2-157">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="973c2-157">**Description**</span></span>  
     <span data-ttu-id="973c2-158">Consente di visualizzare o specificare una descrizione per il piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="973c2-158">View or specify a description for the maintenance plan.</span></span> <span data-ttu-id="973c2-159">La lunghezza massima consentita per una descrizione è 512 caratteri.</span><span class="sxs-lookup"><span data-stu-id="973c2-159">The maximum length for a description is 512 characters.</span></span>  
  
     <span data-ttu-id="973c2-160">**Area di progettazione**</span><span class="sxs-lookup"><span data-stu-id="973c2-160">**Designer Surface**</span></span>  
     <span data-ttu-id="973c2-161">Consente di progettare e gestire i piani di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="973c2-161">Design and maintain maintenance plans.</span></span> <span data-ttu-id="973c2-162">Utilizzare l'area di progettazione per aggiungere attività di manutenzione a un piano, rimuovere attività da un piano, specificare collegamenti di precedenza tra le attività e indicare le diramazioni e i parallelismi delle attività.</span><span class="sxs-lookup"><span data-stu-id="973c2-162">Use the designer surface to add maintenance tasks to a plan, remove tasks from a plan, specify precedence links between the tasks, and indicate task branching and parallelism.</span></span>  
  
     <span data-ttu-id="973c2-163">Un collegamento di precedenza tra due attività stabilisce una relazione tra le attività.</span><span class="sxs-lookup"><span data-stu-id="973c2-163">A precedence link between two tasks establishes a relationship between the tasks.</span></span> <span data-ttu-id="973c2-164">La seconda attività, ovvero *l'attività dipendente*, viene eseguita solo se il risultato dell'esecuzione della prima attività, ovvero *l'attività precedente*, soddisfa i criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="973c2-164">The second task (the *dependent task*) executes only if the execution result of the first task (the *precedent task*) matches specified criteria.</span></span> <span data-ttu-id="973c2-165">In genere, il risultato dell'esecuzione è **Esito positivo**, **Esito negativo**o **Completamento**.</span><span class="sxs-lookup"><span data-stu-id="973c2-165">Typically the execution result specified is **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="973c2-166">Per ulteriori informazioni, vedere il passaggio **8** di seguito.</span><span class="sxs-lookup"><span data-stu-id="973c2-166">For more information, see step **8** below.</span></span>  
  
5.  <span data-ttu-id="973c2-167">Nell'intestazione dell'area di progettazione fare doppio clic su **Sottopiano_1** e immettere un nome e una descrizione per il sottopiano nella finestra di dialogo **Proprietà sottopiano** .</span><span class="sxs-lookup"><span data-stu-id="973c2-167">In the design space's header, double-click **Subplan_1** and enter a name and description for the subplan in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="973c2-168">Nella finestra di dialogo **Proprietà sottopiano** sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="973c2-168">The following options are available in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="973c2-169">**Nome**</span><span class="sxs-lookup"><span data-stu-id="973c2-169">**Name**</span></span>  
     <span data-ttu-id="973c2-170">Nome del sottopiano.</span><span class="sxs-lookup"><span data-stu-id="973c2-170">The name of the subplan.</span></span>  
  
     <span data-ttu-id="973c2-171">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="973c2-171">**Description**</span></span>  
     <span data-ttu-id="973c2-172">Breve descrizione del sottopiano.</span><span class="sxs-lookup"><span data-stu-id="973c2-172">A brief description of the subplan.</span></span>  
  
     <span data-ttu-id="973c2-173">**Pianificare**</span><span class="sxs-lookup"><span data-stu-id="973c2-173">**Schedule**</span></span>  
     <span data-ttu-id="973c2-174">Indica la pianificazione in base alla quale verrà eseguito il sottopiano.</span><span class="sxs-lookup"><span data-stu-id="973c2-174">Indicates on what schedule the subplan will be run.</span></span> <span data-ttu-id="973c2-175">Fare clic su **Pianificazione sottopiano** per aprire la finestra di dialogo **Nuova pianificazione processo** .</span><span class="sxs-lookup"><span data-stu-id="973c2-175">Click **Subplan Schedule** to open the **New Job Schedule** dialog box.</span></span> <span data-ttu-id="973c2-176">Fare clic su **Rimuovi pianificazione** per eliminare la pianificazione dal sottopiano.</span><span class="sxs-lookup"><span data-stu-id="973c2-176">Click **Remove Schedule** to delete the schedule from the subplan.</span></span>  
  
     <span data-ttu-id="973c2-177">Elenco**Esegui come**</span><span class="sxs-lookup"><span data-stu-id="973c2-177">**Run as** list</span></span>  
     <span data-ttu-id="973c2-178">Consente di selezionare l'account da utilizzare per l'esecuzione di questa sottoattività.</span><span class="sxs-lookup"><span data-stu-id="973c2-178">Select the account to use to run this subtask.</span></span>  
  
6.  <span data-ttu-id="973c2-179">Fare clic su **Pianificazione sottopiano** per immettere i dettagli della pianificazione nella finestra di dialogo **Nuova pianificazione processo** .</span><span class="sxs-lookup"><span data-stu-id="973c2-179">Click **Subplan Schedule** to enter schedule details in the **New Job Schedule** dialog box.</span></span>  
  
7.  <span data-ttu-id="973c2-180">Per compilare il sottopiano, trascinare elementi del flusso di attività dalla **Casella degli strumenti** all'area di progettazione del piano.</span><span class="sxs-lookup"><span data-stu-id="973c2-180">To build the subplan, drag and drop task flow elements from the **Toolbox** to the plan design surface.</span></span> <span data-ttu-id="973c2-181">Fare doppio clic sulle attività per aprire le finestre di dialogo per la configurazione delle relative opzioni.</span><span class="sxs-lookup"><span data-stu-id="973c2-181">Double-click tasks to open dialog boxes to configure the task options.</span></span>  
  
     <span data-ttu-id="973c2-182">Nella **Casella degli strumenti**sono disponibili le attività del piano di manutenzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="973c2-182">The following maintenance plan tasks are available in the **Toolbox**:</span></span>  
  
    -   <span data-ttu-id="973c2-183">**Attività Backup database**</span><span class="sxs-lookup"><span data-stu-id="973c2-183">**Back up Database Task**</span></span>  
  
    -   <span data-ttu-id="973c2-184">**Attività Controlla integrità database**</span><span class="sxs-lookup"><span data-stu-id="973c2-184">**Check Database Integrity Task**</span></span>  
  
    -   <span data-ttu-id="973c2-185">**Attività Esegui processo di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="973c2-185">**Execute SQL Server Agent Job Task**</span></span>  
  
    -   <span data-ttu-id="973c2-186">**Attività Esegui istruzione T-SQL**</span><span class="sxs-lookup"><span data-stu-id="973c2-186">**Execute T-SQL Statement Task**</span></span>  
  
    -   <span data-ttu-id="973c2-187">**Attività Pulizia contenuto cronologia**</span><span class="sxs-lookup"><span data-stu-id="973c2-187">**History Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="973c2-188">**Attività Pulizia file manutenzione**</span><span class="sxs-lookup"><span data-stu-id="973c2-188">**Maintenance Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="973c2-189">**Attività Notifica operatori**</span><span class="sxs-lookup"><span data-stu-id="973c2-189">**Notify Operator Task**</span></span>  
  
    -   <span data-ttu-id="973c2-190">**Attività Ricompila indice**</span><span class="sxs-lookup"><span data-stu-id="973c2-190">**Rebuild Index Task**</span></span>  
  
    -   <span data-ttu-id="973c2-191">**Attività Riorganizza indice**</span><span class="sxs-lookup"><span data-stu-id="973c2-191">**Reorganize Index Task**</span></span>  
  
    -   <span data-ttu-id="973c2-192">**Attività Compatta database**</span><span class="sxs-lookup"><span data-stu-id="973c2-192">**Shrink Database Task**</span></span>  
  
    -   <span data-ttu-id="973c2-193">**Attività Aggiorna statistiche**</span><span class="sxs-lookup"><span data-stu-id="973c2-193">**Update Statistics Task**</span></span>  
  
     <span data-ttu-id="973c2-194">Per aggiungere attività alla **Casella degli strumenti**:</span><span class="sxs-lookup"><span data-stu-id="973c2-194">To add tasks to the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="973c2-195">Scegliere **Scegli elementi della Casella degli strumenti** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="973c2-195">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="973c2-196">Selezionare gli strumenti che si desidera visualizzare nella **Casella degli strumenti**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="973c2-196">Select the tools you want to appear in the **Toolbox**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="973c2-197">Le attività del piano di manutenzione aggiunte alla **Casella degli strumenti** vengono rese disponibili anche nella **Creazione guidata piano di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="973c2-197">Adding maintenance plan tasks to the **Toolbox** also makes them available in the **Maintenance Plan Wizard**.</span></span> <span data-ttu-id="973c2-198">Per altre informazioni sulle singole attività illustrate in precedenza, vedere [Utilizzo della Creazione guidata piano di manutenzione](use-the-maintenance-plan-wizard.md#SSMSProcedure) nell'argomento relativo alla **Creazione guidata piano di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="973c2-198">For more information on the individual tasks above, see [Using Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md#SSMSProcedure) under **Start the Maintenance Plan Wizard**.</span></span>  
  
8.  <span data-ttu-id="973c2-199">Per definire un flusso di lavoro tra attività:</span><span class="sxs-lookup"><span data-stu-id="973c2-199">To define a workflow between tasks:</span></span>  
  
    1.  <span data-ttu-id="973c2-200">Fare clic con il pulsante destro del mouse sull'attività precedente e scegliere **Aggiungi vincolo di precedenza**.</span><span class="sxs-lookup"><span data-stu-id="973c2-200">Right-click the precedent task and select **Add Precedence Constraint**.</span></span>  
  
    2.  <span data-ttu-id="973c2-201">Nella finestra di dialogo **Flusso di controllo** selezionare l'attività dipendente nell'elenco **A** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="973c2-201">In the **Control Flow** dialog box, in the **To** list, select the dependent task and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="973c2-202">Fare doppio clic sul connettore tra le due attività per aprire la finestra di dialogo **Editor vincoli di precedenza** .</span><span class="sxs-lookup"><span data-stu-id="973c2-202">Double click the connector between the two tasks to open the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="973c2-203">Nella finestra di dialogo **Editor vincoli di precedenza** sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="973c2-203">The following options are available in the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="973c2-204">**Opzioni vincolo**</span><span class="sxs-lookup"><span data-stu-id="973c2-204">**Constraint option**</span></span>  
         <span data-ttu-id="973c2-205">Consente di definire il funzionamento di un vincolo tra due attività.</span><span class="sxs-lookup"><span data-stu-id="973c2-205">Defines how a constraint works between two tasks.</span></span>  
  
         <span data-ttu-id="973c2-206">Elenco**Operazione valutazione**</span><span class="sxs-lookup"><span data-stu-id="973c2-206">**Evaluation operation**  list</span></span>  
         <span data-ttu-id="973c2-207">Consente di specificare l'operazione di valutazione utilizzata dal vincolo di precedenza.</span><span class="sxs-lookup"><span data-stu-id="973c2-207">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="973c2-208">Le operazioni sono: **Vincolo**, **Espressione**, **Espressione e vincolo** e **Espressione o vincolo**.</span><span class="sxs-lookup"><span data-stu-id="973c2-208">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
         <span data-ttu-id="973c2-209">Elenco**Valore**</span><span class="sxs-lookup"><span data-stu-id="973c2-209">**Value** list</span></span>  
         <span data-ttu-id="973c2-210">Specificare il valore del vincolo: **Esito positivo**, **Esito negativo** o **Completamento**.</span><span class="sxs-lookup"><span data-stu-id="973c2-210">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="973c2-211">Il valore predefinito è**Esito positivo** .</span><span class="sxs-lookup"><span data-stu-id="973c2-211">**Success** is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="973c2-212">La riga del vincolo di precedenza è verde in caso di **Esito positivo**, rossa in caso di **Esito negativo**e blu in caso di **Completamento**.</span><span class="sxs-lookup"><span data-stu-id="973c2-212">The precedence constraint line is green for **Success**, red for **Failure**, and blue for **Completion**.</span></span>  
  
         <span data-ttu-id="973c2-213">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="973c2-213">**Expression**</span></span>  
         <span data-ttu-id="973c2-214">Se si usano le operazioni **Espressione**, **Espressione e vincolo**oppure **Espressione o vincolo**, digitare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="973c2-214">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression.</span></span> <span data-ttu-id="973c2-215">L'espressione deve restituire un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="973c2-215">The expression must evaluate to a Boolean.</span></span>  
  
         <span data-ttu-id="973c2-216">**Test**</span><span class="sxs-lookup"><span data-stu-id="973c2-216">**Test**</span></span>  
         <span data-ttu-id="973c2-217">Consente di convalidare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="973c2-217">Validate the expression.</span></span>  
  
         <span data-ttu-id="973c2-218">**Più vincoli**</span><span class="sxs-lookup"><span data-stu-id="973c2-218">**Multiple constraints**</span></span>  
         <span data-ttu-id="973c2-219">Consente di definire l'interoperabilità di più vincoli e di controllare l'esecuzione dell'attività vincolata.</span><span class="sxs-lookup"><span data-stu-id="973c2-219">Define how multiple constraints interoperate to control the execution of the constrained task.</span></span>  
  
         <span data-ttu-id="973c2-220">**AND logico**</span><span class="sxs-lookup"><span data-stu-id="973c2-220">**Logical AND**</span></span>  
         <span data-ttu-id="973c2-221">Selezionare questa opzione per specificare che devono essere valutati contemporaneamente più vincoli di precedenza nello stesso file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="973c2-221">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="973c2-222">Tutti i vincoli devono restituire True.</span><span class="sxs-lookup"><span data-stu-id="973c2-222">All constraints must evaluate to True.</span></span> <span data-ttu-id="973c2-223">Questa opzione è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="973c2-223">This option is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="973c2-224">Questo tipo di vincolo di precedenza viene visualizzato come riga di colore verde, rosso o blu continua.</span><span class="sxs-lookup"><span data-stu-id="973c2-224">This type of precedence constraint appears as a solid green, red, or blue line.</span></span>  
  
         <span data-ttu-id="973c2-225">**OR logico**</span><span class="sxs-lookup"><span data-stu-id="973c2-225">**Logical OR**</span></span>  
         <span data-ttu-id="973c2-226">Selezionare questa opzione per specificare che devono essere valutati contemporaneamente più vincoli di precedenza nello stesso file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="973c2-226">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="973c2-227">Almeno un vincolo deve restituire True.</span><span class="sxs-lookup"><span data-stu-id="973c2-227">At least one constraint must evaluate to True.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="973c2-228">Questo tipo di vincolo di precedenza viene visualizzato come riga di colore verde, rosso o blu tratteggiata.</span><span class="sxs-lookup"><span data-stu-id="973c2-228">This type of precedence constraint appears as a dotted green, red, or blue line.</span></span>  
  
9. <span data-ttu-id="973c2-229">Per aggiungere un altro sottopiano contenente attività eseguite in base a una pianificazione diversa, fare clic su **Aggiungi sottopiano** sulla barra degli strumenti per aprire la finestra di dialogo **Proprietà sottopiano** .</span><span class="sxs-lookup"><span data-stu-id="973c2-229">To add another subplan that contains tasks run on a different schedule, click **Add Subplan** on the toolbar to open the **Subplan Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="973c2-230">Per aggiungere connessioni a server diversi:</span><span class="sxs-lookup"><span data-stu-id="973c2-230">To add connections to different servers:</span></span>  
  
    1.  <span data-ttu-id="973c2-231">Nella barra degli strumenti dell'area di progettazione fare clic su **Gestisci connessioni**.</span><span class="sxs-lookup"><span data-stu-id="973c2-231">In the design space's toolbar, click **Manage Connections**.</span></span>  
  
    2.  <span data-ttu-id="973c2-232">Nella finestra di dialogo **Gestisci connessioni** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="973c2-232">In the **Manage Connections** dialog box, click **Add**.</span></span>  
  
    3.  <span data-ttu-id="973c2-233">Nella casella **Nome connessione** nella finestra di dialogo **Proprietà connessione** immettere il nome della connessione che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="973c2-233">In the **Connection Properties** dialog box, in the **Connection name** box, enter the name of the connection you are creating.</span></span>  
  
    4.  <span data-ttu-id="973c2-234">Nella finestra di dialogo **Selezionare o immettere il nome di un server** in **Specificare le informazioni seguenti per connettersi ai dati di SQL Server** immettere il nome del server SQL che si intende usare o fare clic sui puntini di sospensione **(...)** e selezionare un server nella finestra di dialogo **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="973c2-234">Under **Specify the following to connect to SQL Server data**, in the **Select or enter a server name** box, either enter the name of the SQL server you want to use or click the ellipsis **(...)** and select a server in the **SQL Server** dialog box.</span></span> <span data-ttu-id="973c2-235">Se si seleziona un server nella finestra di dialogo **SQL Server** , fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="973c2-235">If you select a server from the **SQL Server** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="973c2-236">In **Immettere le informazioni per l'accesso al server**selezionare **Usa sicurezza integrata di Windows NT** o **Usa nome utente e password specifici**.</span><span class="sxs-lookup"><span data-stu-id="973c2-236">Under **Enter information to log on to the server**, select either **Use Windows NT Integrated security** or **Use a specific user name and password**.</span></span> <span data-ttu-id="973c2-237">Se si sceglie di utilizzare un nome utente e una password specifici, immettere tali informazioni rispettivamente nelle caselle **Nome utente** e **Password** .</span><span class="sxs-lookup"><span data-stu-id="973c2-237">If you elect to use a specific user name and password, enter that information in the **User name** and **Password** boxes, respectively.</span></span>  
  
    6.  <span data-ttu-id="973c2-238">Nella finestra di dialogo **Proprietà connessione** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="973c2-238">In the **Connection Properties** dialog box, click **OK**.</span></span>  
  
    7.  <span data-ttu-id="973c2-239">Nella finestra di dialogo **Gestisci connessioni** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="973c2-239">In the **Manage Connections** dialog box, click **Close**.</span></span>  
  
11. <span data-ttu-id="973c2-240">Per specificare le opzioni dei report:</span><span class="sxs-lookup"><span data-stu-id="973c2-240">To specify reporting options:</span></span>  
  
    1.  <span data-ttu-id="973c2-241">Nella barra degli strumenti dell'area di progettazione fare clic su **Report e registrazione**.</span><span class="sxs-lookup"><span data-stu-id="973c2-241">In the design space's toolbar, click **Reporting and Logging**.</span></span>  
  
    2.  <span data-ttu-id="973c2-242">Nella finestra di dialogo **Report e registrazione** selezionare **Genera report in un file di testo**, **Invia report a destinatario di posta elettronica** o entrambe le opzioni in **Report** .</span><span class="sxs-lookup"><span data-stu-id="973c2-242">In the **Reporting and Logging** dialog box, under **Reporting**, select **Generate a text file report** or **Send report to an email recipient** or both.</span></span>  
  
        1.  <span data-ttu-id="973c2-243">Se si seleziona **Genera report in un file di testo**, selezionare **Crea nuovo file** o **Accoda a file**.</span><span class="sxs-lookup"><span data-stu-id="973c2-243">If you select **Generate a text file report**, select either **Create a new file** or **Append to file**.</span></span>  
  
        2.  <span data-ttu-id="973c2-244">A seconda della selezione effettuata nel passaggio precedente, immettere il nome e il percorso completo del nuovo file o del file da accodare nella casella **Cartella** o **Nome file** .</span><span class="sxs-lookup"><span data-stu-id="973c2-244">Depending on the selection above, enter the name and full path of the new file or file to be appended by entering the information in the **Folder** or **File name** boxes.</span></span> <span data-ttu-id="973c2-245">In alternativa, fare clic sui puntini di sospensione **(...)** e selezionare il percorso della cartella o il nome del file nelle finestre di dialogo **Individua cartella-**_server_name_ o **Individua file di database-**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="973c2-245">Alternately, click on the ellipsis **(...)** and select the path to the folder or file name from the **Locate Folder -**_server_name_ or **Locate Database Files -**_server_name_ dialog boxes.</span></span>  
  
        3.  <span data-ttu-id="973c2-246">Se si seleziona **Invia report a destinatario di posta elettronica**, nell'elenco **Operatore agente** selezionare il destinatario del report da inviare tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="973c2-246">If you select **Send report to an email recipient**, on the **Agent operator** list, select the recipient of the emailed report.</span></span>  
  
            > [!NOTE]  
            >  <span data-ttu-id="973c2-247">È necessario configurare SQL Server Agent per l'utilizzo di Posta elettronica database per inviare il report tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="973c2-247">SQL Server Agent must be configured to use Database Mail in order to send mail.</span></span> <span data-ttu-id="973c2-248">Per altre informazioni, vedere [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)</span><span class="sxs-lookup"><span data-stu-id="973c2-248">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)</span></span>  
  
    3.  <span data-ttu-id="973c2-249">Per salvare informazioni più dettagliate, in **Registrazione**selezionare **Registra informazioni estese**.</span><span class="sxs-lookup"><span data-stu-id="973c2-249">To save more detailed information, under **Logging**, select **Log extended information**.</span></span>  
  
    4.  <span data-ttu-id="973c2-250">Per scrivere le informazioni relative ai risultati del piano di manutenzione in un altro server, selezionare **Registra in server remoto** e quindi selezionare una connessione server nell'elenco **Connessione** oppure fare clic su **Nuovo** e immettere le informazioni sulla connessione nella finestra di dialogo **Proprietà connessione** .</span><span class="sxs-lookup"><span data-stu-id="973c2-250">To write maintenance plan results information to another server, select **Log to remote server** and either select a server connection from the **Connection** list or click **New** and enter the connection information in the **Connection Properties** dialog box.</span></span>  
  
    5.  <span data-ttu-id="973c2-251">Nella finestra di dialogo **Report e registrazione** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="973c2-251">In the **Reporting and Logging** dialog box, click **OK**.</span></span>  
  
12. <span data-ttu-id="973c2-252">Per visualizzare i risultati nel visualizzatore file di log, in **Esplora oggetti**fare clic con il pulsante destro del mouse sulla cartella **Piani di manutenzione** o sul piano di manutenzione specifico e selezionare **Visualizza cronologia**.</span><span class="sxs-lookup"><span data-stu-id="973c2-252">To view the results in the log file viewer, in **Object Explorer**, right-click either the **Maintenance Plans** folder or the specific maintenance plan and select **View History**.</span></span>  
  
     <span data-ttu-id="973c2-253">Le opzioni seguenti sono disponibili nella finestra di dialogo **Visualizzatore file di log-**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="973c2-253">The following options are available on the **Log File Viewer -**_server_name_ dialog box.</span></span>  
  
     <span data-ttu-id="973c2-254">**Carica log**</span><span class="sxs-lookup"><span data-stu-id="973c2-254">**Load Log**</span></span>  
     <span data-ttu-id="973c2-255">Consente di aprire una finestra di dialogo in cui è possibile specificare un file di log da caricare.</span><span class="sxs-lookup"><span data-stu-id="973c2-255">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="973c2-256">**Export**</span><span class="sxs-lookup"><span data-stu-id="973c2-256">**Export**</span></span>  
     <span data-ttu-id="973c2-257">Consente di aprire una finestra di dialogo in cui è possibile esportare in un file di testo le informazioni visualizzate nella griglia **Riepilogo file di log** .</span><span class="sxs-lookup"><span data-stu-id="973c2-257">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="973c2-258">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="973c2-258">**Refresh**</span></span>  
     <span data-ttu-id="973c2-259">Consente di aggiornare la visualizzazione dei log selezionati.</span><span class="sxs-lookup"><span data-stu-id="973c2-259">Refresh the view of the selected logs.</span></span> <span data-ttu-id="973c2-260">Il pulsante **Aggiorna** consente di leggere nuovamente i log selezionati dal server di destinazione applicando qualsiasi impostazione di filtro.</span><span class="sxs-lookup"><span data-stu-id="973c2-260">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="973c2-261">**Filter**</span><span class="sxs-lookup"><span data-stu-id="973c2-261">**Filter**</span></span>  
     <span data-ttu-id="973c2-262">Consente di aprire una finestra di dialogo in cui è possibile specificare le impostazioni usate per filtrare il file di log, ad esempio **Connessione**, **Data**o altri criteri di filtro **generali** .</span><span class="sxs-lookup"><span data-stu-id="973c2-262">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="973c2-263">**Ricerca**</span><span class="sxs-lookup"><span data-stu-id="973c2-263">**Search**</span></span>  
     <span data-ttu-id="973c2-264">Consente di cercare testo specifico nel file di log.</span><span class="sxs-lookup"><span data-stu-id="973c2-264">Search the log file for specific text.</span></span> <span data-ttu-id="973c2-265">La ricerca con caratteri jolly non è supportata.</span><span class="sxs-lookup"><span data-stu-id="973c2-265">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="973c2-266">**Stop**</span><span class="sxs-lookup"><span data-stu-id="973c2-266">**Stop**</span></span>  
     <span data-ttu-id="973c2-267">Consente di arrestare il caricamento delle voci del file di log.</span><span class="sxs-lookup"><span data-stu-id="973c2-267">Stops loading the log file entries.</span></span> <span data-ttu-id="973c2-268">È ad esempio possibile utilizzare questa opzione se il caricamento di un file di log remoto o offline richiede parecchio tempo e si desidera visualizzare solo le voci più recenti.</span><span class="sxs-lookup"><span data-stu-id="973c2-268">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="973c2-269">**Riepilogo file di log**</span><span class="sxs-lookup"><span data-stu-id="973c2-269">**Log file summary**</span></span>  
     <span data-ttu-id="973c2-270">Consente di visualizzare un riepilogo dei filtri del file di log.</span><span class="sxs-lookup"><span data-stu-id="973c2-270">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="973c2-271">Se non è stato applicato alcun filtro al file, verrà visualizzato il testo **Nessun filtro applicato**.</span><span class="sxs-lookup"><span data-stu-id="973c2-271">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="973c2-272">Se è stato applicato un filtro al log, verrà visualizzato il testo **Filtra voci del log in cui:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="973c2-272">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="973c2-273">**Data**</span><span class="sxs-lookup"><span data-stu-id="973c2-273">**Date**</span></span>  
     <span data-ttu-id="973c2-274">Visualizza la data dell'evento.</span><span class="sxs-lookup"><span data-stu-id="973c2-274">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="973c2-275">**Origine**</span><span class="sxs-lookup"><span data-stu-id="973c2-275">**Source**</span></span>  
     <span data-ttu-id="973c2-276">Consente di visualizzare la funzionalità di origine da cui è stato creato l'evento, ad esempio il nome del servizio, come MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="973c2-276">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="973c2-277">Questa opzione non viene visualizzata per tutti i tipi di log.</span><span class="sxs-lookup"><span data-stu-id="973c2-277">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="973c2-278">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="973c2-278">**Message**</span></span>  
     <span data-ttu-id="973c2-279">Consente di visualizzare i messaggi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="973c2-279">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="973c2-280">**Tipo log**</span><span class="sxs-lookup"><span data-stu-id="973c2-280">**Log Type**</span></span>  
     <span data-ttu-id="973c2-281">Consente di visualizzare il tipo di log cui appartiene l'evento.</span><span class="sxs-lookup"><span data-stu-id="973c2-281">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="973c2-282">Tutti i log selezionati vengono visualizzati nella finestra di riepilogo dei log.</span><span class="sxs-lookup"><span data-stu-id="973c2-282">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="973c2-283">**Origine log**</span><span class="sxs-lookup"><span data-stu-id="973c2-283">**Log Source**</span></span>  
     <span data-ttu-id="973c2-284">Visualizza una descrizione del log di origine in cui viene acquisito l'evento.</span><span class="sxs-lookup"><span data-stu-id="973c2-284">Displays a description of the source log in which the event is captured.</span></span>  
  
     <span data-ttu-id="973c2-285">**Dettagli riga selezionata**</span><span class="sxs-lookup"><span data-stu-id="973c2-285">**Selected row details**</span></span>  
     <span data-ttu-id="973c2-286">Consente di selezionare una riga di evento nella parte inferiore della pagina per visualizzare dettagli aggiuntivi sulla riga.</span><span class="sxs-lookup"><span data-stu-id="973c2-286">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="973c2-287">È possibile riordinare le colonne trascinandole su nuove posizioni all'interno della griglia.</span><span class="sxs-lookup"><span data-stu-id="973c2-287">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="973c2-288">Le colonne possono inoltre essere ridimensionate trascinando verso destra o verso sinistra le corrispondenti barre di separazione nell'intestazione della griglia.</span><span class="sxs-lookup"><span data-stu-id="973c2-288">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="973c2-289">Per adattare automaticamente le dimensioni della colonna al contenuto, fare doppio clic sulle barre di separazione nell'intestazione della griglia.</span><span class="sxs-lookup"><span data-stu-id="973c2-289">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="973c2-290">**Istanza**</span><span class="sxs-lookup"><span data-stu-id="973c2-290">**Instance**</span></span>  
     <span data-ttu-id="973c2-291">Nome dell'istanza in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="973c2-291">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="973c2-292">Viene visualizzato come *nome computer*\\*nome istanza*.</span><span class="sxs-lookup"><span data-stu-id="973c2-292">This is displayed as *computer name*\\*instance name*.</span></span>  
  
  
