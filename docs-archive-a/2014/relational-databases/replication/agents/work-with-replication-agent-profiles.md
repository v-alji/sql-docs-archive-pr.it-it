---
title: Usare i profili agenti di replica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], agents and profiles
- replication agent profiles [SQL Server]
- agents [SQL Server replication], profiles
- profiles [SQL Server], replication agents
ms.assetid: 9c290a88-4e9f-4a7e-aab5-4442137a9918
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fc20451edfb1096fca7e468effb14df78b51f758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624649"
---
# <a name="work-with-replication-agent-profiles"></a><span data-ttu-id="9c300-102">Utilizzo dei profili agenti di replica</span><span class="sxs-lookup"><span data-stu-id="9c300-102">Work with Replication Agent Profiles</span></span>
  <span data-ttu-id="9c300-103">In questo argomento viene descritto come utilizzare i profili degli agenti di replica in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="9c300-103">This topic describes how to work with Replication Agent Profiles in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span> <span data-ttu-id="9c300-104">Il comportamento di ogni agente di replica è controllato da un set di parametri che è possibile impostare tramite i profili agenti.</span><span class="sxs-lookup"><span data-stu-id="9c300-104">The behavior of each replication agent is controlled by a set of parameters that can be set through agent profiles.</span></span> <span data-ttu-id="9c300-105">Ogni agente dispone di un profilo predefinito e alcuni anche di profili predefiniti aggiuntivi. In un momento specifico, per un agente è attivo un solo profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-105">Each agent has a default profile, and some have additional predefined profiles; at a given time, only one profile is active for an agent.</span></span>  
  
 <span data-ttu-id="9c300-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="9c300-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9c300-107">**Per utilizzare i profili degli agenti di replica, utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="9c300-107">**To work with Replication Agent Profiles, using:**</span></span>  
  
     [<span data-ttu-id="9c300-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c300-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   <span data-ttu-id="9c300-109">Accedere alla finestra di dialogo Profili agenti</span><span class="sxs-lookup"><span data-stu-id="9c300-109">Access the Agent Profiles dialog box</span></span>  
  
    -   <span data-ttu-id="9c300-110">Specificare un profilo per un agente</span><span class="sxs-lookup"><span data-stu-id="9c300-110">Specify a profile for an agent</span></span>  
  
    -   <span data-ttu-id="9c300-111">Creare un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-111">Create a profile</span></span>  
  
    -   <span data-ttu-id="9c300-112">Modificare un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-112">Modify a profile</span></span>  
  
    -   <span data-ttu-id="9c300-113">Eliminare un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-113">Delete a profile</span></span>  
  
     [<span data-ttu-id="9c300-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9c300-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   <span data-ttu-id="9c300-115">Creare un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-115">Create a profile</span></span>  
  
    -   <span data-ttu-id="9c300-116">Modificare un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-116">Modify a profile</span></span>  
  
    -   <span data-ttu-id="9c300-117">Eliminare un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-117">Delete a profile</span></span>  
  
    -   <span data-ttu-id="9c300-118">Utilizzare i profili agenti durante la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="9c300-118">Use agent profiles during synchronization</span></span>  
  
    -   <span data-ttu-id="9c300-119">Esempio Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9c300-119">Transact-SQL example</span></span>  
  
     [<span data-ttu-id="9c300-120">oggetti RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="9c300-120">Replication Management Objects</span></span>](#RMOProcedure)  
  
    -   <span data-ttu-id="9c300-121">Creare un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-121">Create a profile</span></span>  
  
    -   <span data-ttu-id="9c300-122">Modificare un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-122">Modify a profile</span></span>  
  
    -   <span data-ttu-id="9c300-123">Eliminare un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-123">Delete a profile</span></span>  
  
-   <span data-ttu-id="9c300-124">**Completamento:**  [dopo avere modificato i parametri degli agenti](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="9c300-124">**Follow Up:**  [After Changing Agent Parameters](#FollowUp)</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9c300-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c300-125">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-access-the-agent-profiles-dialog-box-from-sql-server-management-studio"></a><a name="Access_SSMS"></a> <span data-ttu-id="9c300-126">Per accedere alla finestra di dialogo Profili agenti da SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c300-126">To access the Agent Profiles dialog box from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="9c300-127">Nella pagina **Generale** della finestra di dialogo **Proprietà database di distribuzione - \<Distributor>** fare clic su **Impostazioni predefinite profili**.</span><span class="sxs-lookup"><span data-stu-id="9c300-127">On the **General** page of the **Distributor Properties - \<Distributor>** dialog box, click **Profile Defaults**.</span></span>  
  
#### <a name="to-access-the-agent-profiles-dialog-box-from-replication-monitor"></a><span data-ttu-id="9c300-128">Per accedere alla finestra di dialogo Profili agenti da Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="9c300-128">To access the Agent Profiles dialog box from Replication Monitor</span></span>  
  
-   <span data-ttu-id="9c300-129">Per aprire la finestra di dialogo per tutti gli agenti, fare clic con il pulsante destro del mouse su un server di pubblicazione e quindi scegliere **Profili agenti**.</span><span class="sxs-lookup"><span data-stu-id="9c300-129">To open the dialog box for all agents, right-click a Publisher, and then click **Agent Profiles**.</span></span>  
  
-   <span data-ttu-id="9c300-130">Per aprire la finestra di dialogo per un singolo agente:</span><span class="sxs-lookup"><span data-stu-id="9c300-130">To open the dialog box for a single agent:</span></span>  
  
    1.  <span data-ttu-id="9c300-131">Espandere un gruppo di server di pubblicazione nel riquadro a sinistra di Monitoraggio replica, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9c300-131">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="9c300-132">Per i profili dell'agente di distribuzione e dell'agente di merge, fare clic con il pulsante destro del mouse su una sottoscrizione nella scheda **Tutte le sottoscrizioni** e quindi scegliere **Profilo agente**.</span><span class="sxs-lookup"><span data-stu-id="9c300-132">For Distribution Agent and Merge Agent profiles, right-click a subscription on the **All Subscriptions** tab, and then click **Agent Profile**.</span></span> <span data-ttu-id="9c300-133">Per gli altri agenti, fare clic con il pulsante destro del mouse sull'agente nella scheda **Agenti** , quindi scegliere **Profilo agente**.</span><span class="sxs-lookup"><span data-stu-id="9c300-133">For other agents, right-click the agent on the **Agents** tab, and then click **Agent Profile**.</span></span>  
  
###  <a name="to-specify-a-profile-for-an-agent"></a><a name="Specify_SSMS"></a> <span data-ttu-id="9c300-134">Per specificare un profilo per un agente</span><span class="sxs-lookup"><span data-stu-id="9c300-134">To specify a profile for an agent</span></span>  
  
1.  <span data-ttu-id="9c300-135">Se nella finestra di dialogo **Profili agenti** vengono visualizzati i profili di più agenti, selezionare un agente.</span><span class="sxs-lookup"><span data-stu-id="9c300-135">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="9c300-136">Selezionare un profilo nella colonna **Predefinito per i nuovi agenti** della griglia **Profili agenti** .</span><span class="sxs-lookup"><span data-stu-id="9c300-136">Select a profile in the **Default for new** column of the **Agent profiles** grid.</span></span> <span data-ttu-id="9c300-137">Per impostazione predefinita, il profilo viene applicato solo agli agenti per le nuove pubblicazioni e sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="9c300-137">By default, the profile is only applied to agents for new publications and subscriptions.</span></span>  
  
3.  <span data-ttu-id="9c300-138">Per specificare che tutti gli agenti del tipo selezionato per le pubblicazioni o le sottoscrizioni esistenti devono utilizzare questo profilo, fare clic su **Modifica agenti esistenti**.</span><span class="sxs-lookup"><span data-stu-id="9c300-138">To specify that all agents of the selected type for existing publications or subscriptions should use this profile, click **Change existing agents**.</span></span>  
  
###  <a name="to-view-and-edit-the-parameters-associated-with-a-profile"></a><a name="Modify_SSMS"></a> <span data-ttu-id="9c300-139">Per visualizzare e modificare i parametri associati a un profilo</span><span class="sxs-lookup"><span data-stu-id="9c300-139">To view and edit the parameters associated with a profile</span></span>  
  
1.  <span data-ttu-id="9c300-140">Se nella finestra di dialogo **Profili agenti** vengono visualizzati i profili di più agenti, selezionare un agente.</span><span class="sxs-lookup"><span data-stu-id="9c300-140">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="9c300-141">Fare clic sul pulsante delle proprietà ( **...** ) accanto a un profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-141">Click the properties button (**...**) next to a profile.</span></span>  
  
3.  <span data-ttu-id="9c300-142">Visualizzare i parametri e i valori nella finestra di dialogo **Proprietà profilo \<ProfileName>** .</span><span class="sxs-lookup"><span data-stu-id="9c300-142">View the parameters and values in the **\<ProfileName> Profile Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="9c300-143">È possibile modificare i parametri nei profili definiti dall'utente, ma non quelli nei profili di sistema predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9c300-143">Parameters in user-defined profiles can be edited; parameters in predefined system profiles cannot.</span></span>  
  
    -   <span data-ttu-id="9c300-144">Per visualizzare tutti i parametri per un agente, deselezionare la casella di controllo **Mostra solo i parametri utilizzati in questo profilo** .</span><span class="sxs-lookup"><span data-stu-id="9c300-144">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="9c300-145">Per informazioni sui parametri degli agenti, vedere i collegamenti alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9c300-145">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
4.  <span data-ttu-id="9c300-146">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="9c300-146">Click **Close**.</span></span>  
  
###  <a name="to-create-a-user-defined-profile"></a><a name="Create_SSMS"></a> <span data-ttu-id="9c300-147">Per creare un profilo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="9c300-147">To create a user-defined profile</span></span>  
  
1.  <span data-ttu-id="9c300-148">Se nella finestra di dialogo **Profili agenti** vengono visualizzati i profili di più agenti, selezionare un agente.</span><span class="sxs-lookup"><span data-stu-id="9c300-148">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="9c300-149">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="9c300-149">Click **New**.</span></span>  
  
3.  <span data-ttu-id="9c300-150">Nella finestra di dialogo di inizializzazione **Nuovo profilo agente** selezionare un profilo esistente su cui basare il nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-150">In the **New Agent Profile** initialization dialog box, select an existing profile on which to base the new profile.</span></span>  
  
4.  <span data-ttu-id="9c300-151">Nella finestra di dialogo **Nuovo profilo agente** immettere i valori nelle caselle di testo **Nome** e **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="9c300-151">In the **New Agent Profile** dialog box, enter values in the **Name** and **Description** text boxes.</span></span>  
  
5.  <span data-ttu-id="9c300-152">Modificare i parametri per personalizzare il profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-152">Modify parameters to tailor the profile.</span></span> <span data-ttu-id="9c300-153">Per visualizzare tutti i parametri per un agente, deselezionare la casella di controllo **Mostra solo i parametri utilizzati in questo profilo** .</span><span class="sxs-lookup"><span data-stu-id="9c300-153">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="9c300-154">Per informazioni sui parametri degli agenti, vedere i collegamenti alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9c300-154">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
###  <a name="to-delete-a-user-defined-profile"></a><a name="Delete_SSMS"></a> <span data-ttu-id="9c300-155">Per eliminare un profilo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="9c300-155">To delete a user-defined profile</span></span>  
  
1.  <span data-ttu-id="9c300-156">Se nella finestra di dialogo **Profili agenti** vengono visualizzati i profili di più agenti, selezionare un agente.</span><span class="sxs-lookup"><span data-stu-id="9c300-156">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="9c300-157">Se un profilo è associato a uno o più agenti, modificare il profilo per tali agenti:</span><span class="sxs-lookup"><span data-stu-id="9c300-157">If a profile is associated with one or more agents, change the profile for those agents:</span></span>  
  
    1.  <span data-ttu-id="9c300-158">Selezionare un altro profilo nella griglia **Profili agenti** .</span><span class="sxs-lookup"><span data-stu-id="9c300-158">Select a different profile in the **Agent profiles** grid.</span></span>  
  
    2.  <span data-ttu-id="9c300-159">Fare clic su **Modifica agenti esistenti**.</span><span class="sxs-lookup"><span data-stu-id="9c300-159">Click **Change existing agents**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9c300-160">Verrà modificato il profilo di tutti gli agenti del tipo selezionato per le pubblicazioni o le sottoscrizioni esistenti e non solo di quelli che utilizzano il profilo che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="9c300-160">This will change the profile for all agents of the selected type for existing publications or subscriptions, not only the ones using the profile you want to delete.</span></span>  
  
3.  <span data-ttu-id="9c300-161">Selezionare il profilo che si desidera eliminare, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9c300-161">Select the profile you want to delete, and then click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9c300-162">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9c300-162">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_tsql"></a> <span data-ttu-id="9c300-163">Per creare un nuovo profilo agente</span><span class="sxs-lookup"><span data-stu-id="9c300-163">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="9c300-164">Nel database di distribuzione eseguire [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c300-164">At the Distributor, execute [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span></span> <span data-ttu-id="9c300-165">Specificare **@name** , il valore **1** per **@profile_type** e uno dei valori seguenti per **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="9c300-165">Specify **@name**, a value of **1** for **@profile_type**, and one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="9c300-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="9c300-171">Se si desidera impostare il profilo come nuovo profilo predefinito per il tipo di agente di replica, specificare il valore **1** per **@default**.</span><span class="sxs-lookup"><span data-stu-id="9c300-171">If this profile will become the new default profile for its type of replication agent, specify a value of **1** for **@default**.</span></span> <span data-ttu-id="9c300-172">L'identificatore per il nuovo profilo viene restituito mediante il **@profile_id** parametro di output.</span><span class="sxs-lookup"><span data-stu-id="9c300-172">The identifier for the new profile is returned using the **@profile_id** output parameter.</span></span> <span data-ttu-id="9c300-173">Viene creato un nuovo profilo con un set di parametri del profilo basato sul profilo predefinito per il tipo di agente specificato.</span><span class="sxs-lookup"><span data-stu-id="9c300-173">This creates a new profile with a set of profile parameters based on the default profile for the given agent type.</span></span>  
  
2.  <span data-ttu-id="9c300-174">Una volta creato il nuovo profilo, è possibile personalizzarlo aggiungendo, rimuovendo o modificando i parametri predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9c300-174">After the new profile has been created, add, remove, or modify the default parameters to customize the profile.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_tsql"></a> <span data-ttu-id="9c300-175">Per modificare un profilo agente esistente</span><span class="sxs-lookup"><span data-stu-id="9c300-175">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="9c300-176">Nel database di distribuzione eseguire [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c300-176">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="9c300-177">Specificare uno dei valori seguenti per **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="9c300-177">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="9c300-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="9c300-183">Vengono restituiti tutti i profili per il tipo di agente specificato.</span><span class="sxs-lookup"><span data-stu-id="9c300-183">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="9c300-184">Tenere presente il valore di **profile_id** nel set di risultati del profilo da modificare.</span><span class="sxs-lookup"><span data-stu-id="9c300-184">Note the value of **profile_id** in the result set for the profile to change.</span></span>  
  
2.  <span data-ttu-id="9c300-185">Nel database di distribuzione eseguire [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c300-185">At the Distributor, execute [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span></span> <span data-ttu-id="9c300-186">Specificare l'identificatore del profilo al passaggio 1 per **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="9c300-186">Specify the profile identifier from step 1 for **@profile_id**.</span></span> <span data-ttu-id="9c300-187">Vengono restituiti tutti i parametri per il profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-187">This returns all parameters for the profile.</span></span> <span data-ttu-id="9c300-188">Tenere presente il nome dei parametri del profilo da modificare o rimuovere.</span><span class="sxs-lookup"><span data-stu-id="9c300-188">Note the name of any parameters to modify or remove from the profile.</span></span>  
  
3.  <span data-ttu-id="9c300-189">Per modificare il valore di un parametro in un profilo, eseguire [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c300-189">To change the value of a parameter in a profile, execute [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span></span> <span data-ttu-id="9c300-190">Specificare l'identificatore del profilo dal passaggio 1 per **@profile_id** , il nome del parametro da modificare per **@property** e un nuovo valore per il parametro **@value** .</span><span class="sxs-lookup"><span data-stu-id="9c300-190">Specify the profile identifier from step 1 for **@profile_id**, the name of the parameter to change for **@property**, and a new value for the parameter for **@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9c300-191">Non è possibile modificare un profilo agente esistente in modo da impostarlo come profilo predefinito di un agente.</span><span class="sxs-lookup"><span data-stu-id="9c300-191">You cannot change an existing agent profile to become the default profile for an agent.</span></span> <span data-ttu-id="9c300-192">A tale scopo, è necessario creare un nuovo profilo come profilo predefinito, come indicato nella procedura indicata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9c300-192">You must instead create a new profile as the default profile, as shown in the previous procedure.</span></span>  
  
4.  <span data-ttu-id="9c300-193">Per rimuovere un parametro da un profilo, eseguire [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c300-193">To remove a parameter from a profile, execute [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span></span> <span data-ttu-id="9c300-194">Specificare l'identificatore del profilo al passaggio 1 per **@profile_id** e il nome del parametro da rimuovere per **@parameter_name** .</span><span class="sxs-lookup"><span data-stu-id="9c300-194">Specify the profile identifier from step 1 for **@profile_id** and the name of the parameter to remove for **@parameter_name**.</span></span>  
  
5.  <span data-ttu-id="9c300-195">Per aggiungere un nuovo parametro a un profilo è necessario effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="9c300-195">To add a new parameter to a profile, you must do the following:</span></span>  
  
    -   <span data-ttu-id="9c300-196">Eseguire una query sulla tabella [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) nel database di distribuzione per determinare i parametri del profilo che è possibile impostare per ogni tipo di agente.</span><span class="sxs-lookup"><span data-stu-id="9c300-196">Query the [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) table at the Distributor to determine which profile parameters can be set for each agent type.</span></span>  
  
    -   <span data-ttu-id="9c300-197">Nel database di distribuzione eseguire [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c300-197">At the Distributor, execute [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span></span> <span data-ttu-id="9c300-198">Specificare l'identificatore del profilo dal passaggio 1 per **@profile_id** , il nome di un parametro valido da aggiungere per **@parameter_name** e il valore del parametro per **@parameter_value** .</span><span class="sxs-lookup"><span data-stu-id="9c300-198">Specify the profile identifier from step 1 for **@profile_id**, the name of a valid parameter to add for **@parameter_name**, and the value of the parameter for **@parameter_value**.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_tsql"></a> <span data-ttu-id="9c300-199">Per eliminare un profilo agente</span><span class="sxs-lookup"><span data-stu-id="9c300-199">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="9c300-200">Nel database di distribuzione eseguire [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c300-200">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="9c300-201">Specificare uno dei valori seguenti per **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="9c300-201">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="9c300-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="9c300-207">Vengono restituiti tutti i profili per il tipo di agente specificato.</span><span class="sxs-lookup"><span data-stu-id="9c300-207">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="9c300-208">Tenere presente il valore di **profile_id** nel set di risultati del profilo da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="9c300-208">Note the value of **profile_id** in the result set for the profile to remove.</span></span>  
  
2.  <span data-ttu-id="9c300-209">Nel database di distribuzione eseguire [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c300-209">At the Distributor, execute [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span></span> <span data-ttu-id="9c300-210">Specificare l'identificatore del profilo al passaggio 1 per **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="9c300-210">Specify the profile identifier from step 1 for **@profile_id**.</span></span>  
  
###  <a name="to-use-agent-profiles-during-synchronization"></a><a name="Synch_tsql"></a> <span data-ttu-id="9c300-211">Per utilizzare i profili agenti durante la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="9c300-211">To use agent profiles during synchronization</span></span>  
  
1.  <span data-ttu-id="9c300-212">Nel database di distribuzione eseguire [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c300-212">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="9c300-213">Specificare uno dei valori seguenti per **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="9c300-213">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="9c300-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="9c300-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="9c300-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="9c300-219">Vengono restituiti tutti i profili per il tipo di agente specificato.</span><span class="sxs-lookup"><span data-stu-id="9c300-219">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="9c300-220">Si noti il valore di `profile_name` nel set di risultati del profilo da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="9c300-220">Note the value of `profile_name` in the result set for the profile to use.</span></span>  
  
2.  <span data-ttu-id="9c300-221">Se l'agente viene avviato da un processo di Agent, modificare il passaggio del processo che avvia l'agente per specificare il valore `profile_name` ottenuto nel passaggio 1 dopo il parametro della riga **di comando-ProfileName** .</span><span class="sxs-lookup"><span data-stu-id="9c300-221">If the agent is started from an agent job, edit the job step that starts the agent to specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span> <span data-ttu-id="9c300-222">Per altre informazioni, vedere [Visualizzare e modificare i parametri del prompt dei comandi dell'agente di replica &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9c300-222">For more information, see [View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span></span>  
  
3.  <span data-ttu-id="9c300-223">Quando si avvia l'agente dal prompt dei comandi, specificare il valore `profile_name` ottenuto nel passaggio 1 dopo il parametro della riga **di comando-ProfileName** .</span><span class="sxs-lookup"><span data-stu-id="9c300-223">When starting the agent from the command prompt, specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9c300-224">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9c300-224">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="9c300-225">In questo esempio viene creato un profilo personalizzato per l'agente di merge denominato **custom_merge**, viene modificato il valore del parametro **-UploadReadChangesPerBatch** , viene aggiunto un nuovo parametro **-ExchangeType** e vengono restituite informazioni sul profilo creato.</span><span class="sxs-lookup"><span data-stu-id="9c300-225">This example creates a custom profile for the Merge Agent named **custom_merge**, changes the value of the **-UploadReadChangesPerBatch** parameter, adds a new **-ExchangeType** parameter, and returns information on the profile that is created.</span></span>  
  
 [!code-sql[HowTo#sp_addagentprofileparam](../../../snippets/tsql/SQL15/replication/howto/tsql/createperfparammerge.sql#sp_addagentprofileparam)]  
  
##  <a name="using-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="9c300-226">Utilizzo di RMO</span><span class="sxs-lookup"><span data-stu-id="9c300-226">Using RMO</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_RMO"></a> <span data-ttu-id="9c300-227">Per creare un nuovo profilo agente</span><span class="sxs-lookup"><span data-stu-id="9c300-227">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="9c300-228">Creare una connessione al database di distribuzione tramite un'istanza della classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9c300-228">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9c300-229">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="9c300-229">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span>  
  
3.  <span data-ttu-id="9c300-230">Impostare le proprietà indicate di seguito nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9c300-230">Set the following properties on the object:</span></span>  
  
    -   <span data-ttu-id="9c300-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> : nome del profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> - the name for the profile.</span></span>  
  
    -   <span data-ttu-id="9c300-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> : valore di <xref:Microsoft.SqlServer.Replication.AgentType> che specifica il tipo di agente di replica per il quale viene creato il profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> - an <xref:Microsoft.SqlServer.Replication.AgentType> value that specifies the type of replication agent for which the profile is being created.</span></span>  
  
    -   <span data-ttu-id="9c300-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> : oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="9c300-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> created in step 1.</span></span>  
  
    -   <span data-ttu-id="9c300-234">(Facoltativo) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> : descrizione del profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-234">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> - a description of the profile.</span></span>  
  
    -   <span data-ttu-id="9c300-235">(Facoltativo) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A>: impostare questa proprietà su `true` se tutti i processi del nuovo agente per <xref:Microsoft.SqlServer.Replication.AgentType> utilizzeranno questo profilo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9c300-235">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A> - set this property to `true` if all new agent jobs for this <xref:Microsoft.SqlServer.Replication.AgentType> will use this profile by default.</span></span>  
  
4.  <span data-ttu-id="9c300-236">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> per creare il profilo nel server.</span><span class="sxs-lookup"><span data-stu-id="9c300-236">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> method to create the profile on the server.</span></span>  
  
5.  <span data-ttu-id="9c300-237">Una volta reso disponibile il profilo nel server, è possibile personalizzarlo aggiungendo, rimuovendo o modificando i valori dei parametri dell'agente di replica.</span><span class="sxs-lookup"><span data-stu-id="9c300-237">Once the profile exists on the server, you can customize it by adding, removing, or changing the values of replication agent parameters.</span></span>  
  
6.  <span data-ttu-id="9c300-238">Per assegnare il profilo a un processo dell'agente di replica esistente, chiamare il metodo <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> .</span><span class="sxs-lookup"><span data-stu-id="9c300-238">To assign the profile to an existing replication agent job, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> method.</span></span> <span data-ttu-id="9c300-239">Passare il nome del database di distribuzione per *distributionDBName* e l'ID del processo per *agentID*.</span><span class="sxs-lookup"><span data-stu-id="9c300-239">Pass the name of the distribution database for *distributionDBName* and the ID of the job for *agentID*.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_RMO"></a> <span data-ttu-id="9c300-240">Per modificare un profilo agente esistente</span><span class="sxs-lookup"><span data-stu-id="9c300-240">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="9c300-241">Creare una connessione al database di distribuzione tramite un'istanza della classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9c300-241">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9c300-242">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="9c300-242">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="9c300-243">Passare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="9c300-243">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object created in step 1.</span></span>  
  
3.  <span data-ttu-id="9c300-244">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="9c300-244">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="9c300-245">Se il metodo restituisce `false`, verificare che il server di distribuzione esista.</span><span class="sxs-lookup"><span data-stu-id="9c300-245">If this method returns `false`, verify that the Distributor exists.</span></span>  
  
4.  <span data-ttu-id="9c300-246">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> .</span><span class="sxs-lookup"><span data-stu-id="9c300-246">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> method.</span></span> <span data-ttu-id="9c300-247">Passare un valore di <xref:Microsoft.SqlServer.Replication.AgentType> per limitare i profili restituiti a un tipo specifico di agente di replica.</span><span class="sxs-lookup"><span data-stu-id="9c300-247">Pass an <xref:Microsoft.SqlServer.Replication.AgentType> value to narrow down the returned profiles to a specific type of replication agent.</span></span>  
  
5.  <span data-ttu-id="9c300-248">Ottenere l'oggetto <xref:Microsoft.SqlServer.Replication.AgentProfile> desiderato dall'oggetto <xref:System.Collections.ArrayList>restituito, dove la proprietà <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> dell'oggetto corrisponde al nome del profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-248">Get the desired <xref:Microsoft.SqlServer.Replication.AgentProfile> object from the returned <xref:System.Collections.ArrayList>, where the <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> property of the object matches the profile name.</span></span>  
  
6.  <span data-ttu-id="9c300-249">Chiamare uno dei metodi di <xref:Microsoft.SqlServer.Replication.AgentProfile> indicati di seguito per modificare il profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-249">Call one of the following methods of <xref:Microsoft.SqlServer.Replication.AgentProfile> to change the profile:</span></span>  
  
    -   <span data-ttu-id="9c300-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> : aggiunge un parametro supportato al profilo, dove *name* è il nome del parametro dell'agente di replica e *value* è il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="9c300-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> - adds a supported parameter to the profile, where *name* is the name of the replication agent parameter and *value* is the specified value.</span></span> <span data-ttu-id="9c300-251">Per enumerare tutti i parametri dell'agente supportati per un tipo di agente specificato, chiamare il metodo <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="9c300-251">To enumerate all supported agent parameters for a given agent type, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="9c300-252">Questo metodo restituisce una classe <xref:System.Collections.ArrayList> di oggetti <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> che rappresentano tutti i parametri supportati.</span><span class="sxs-lookup"><span data-stu-id="9c300-252">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent all supported parameters.</span></span>  
  
    -   <span data-ttu-id="9c300-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> : rimuove un parametro esistente dal profilo, dove *name* è il nome del parametro dell'agente di replica.</span><span class="sxs-lookup"><span data-stu-id="9c300-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> - removes an existing parameter from the profile, where *name* is the name of the replication agent parameter.</span></span> <span data-ttu-id="9c300-254">Per enumerare tutti i parametri dell'agente corrente definiti per il profilo, chiamare il metodo <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="9c300-254">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="9c300-255">Questo metodo restituisce una classe <xref:System.Collections.ArrayList> di oggetti <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> che rappresentano il parametro esistente per il profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-255">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span>  
  
    -   <span data-ttu-id="9c300-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> : modifica l'impostazione di un parametro esistente nel profilo, dove *name* è il nome del parametro dell'agente e *newValue* è il valore nel quale viene modificato il parametro.</span><span class="sxs-lookup"><span data-stu-id="9c300-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> - changes the setting of an existing parameter in the profile, where *name* is the name of the agent parameter and *newValue* is the value to which the parameter is being changed.</span></span> <span data-ttu-id="9c300-257">Per enumerare tutti i parametri dell'agente corrente definiti per il profilo, chiamare il metodo <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="9c300-257">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="9c300-258">Questo metodo restituisce una classe <xref:System.Collections.ArrayList> di oggetti <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> che rappresentano il parametro esistente per il profilo.</span><span class="sxs-lookup"><span data-stu-id="9c300-258">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span> <span data-ttu-id="9c300-259">Per enumerare tutte le impostazioni del parametro dell'agente supportate, chiamare il metodo <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="9c300-259">To enumerate all supported agent parameter settings, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="9c300-260">Questo metodo restituisce una classe <xref:System.Collections.ArrayList> di oggetti <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> che rappresentano i valori supportati per tutti i parametri.</span><span class="sxs-lookup"><span data-stu-id="9c300-260">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent the supported values for all parameters.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_RMO"></a> <span data-ttu-id="9c300-261">Per eliminare un profilo agente</span><span class="sxs-lookup"><span data-stu-id="9c300-261">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="9c300-262">Creare una connessione al database di distribuzione tramite un'istanza della classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9c300-262">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9c300-263">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="9c300-263">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span> <span data-ttu-id="9c300-264">Impostare il nome del profilo per la proprietà <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> e l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> creato nel passaggio 1 per la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c300-264">Set the name of the profile for <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="9c300-265">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="9c300-265">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="9c300-266">Se il metodo restituisce `false`, il nome specificato non è corretto o il profilo non esiste nel server.</span><span class="sxs-lookup"><span data-stu-id="9c300-266">If this method returns `false`, either the specified name was incorrect or the profile does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="9c300-267">Verificare che la proprietà <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> sia impostata su <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, in modo da indicare un profilo del cliente.</span><span class="sxs-lookup"><span data-stu-id="9c300-267">Verify that the <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> property is set to <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, which indicates a customer profile.</span></span> <span data-ttu-id="9c300-268">Non è necessario rimuovere un profilo con valore <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> per <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c300-268">You should not remove a profile that has a value of <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> for <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span></span>  
  
5.  <span data-ttu-id="9c300-269">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> per rimuovere dal server il profilo definito dall'utente rappresentato da questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="9c300-269">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> method to remove the user-defined profile represented by this object from the server.</span></span>  
  
##  <a name="follow-up-after-changing-agent-parameters"></a><a name="FollowUp"></a> <span data-ttu-id="9c300-270">Completamento: dopo avere modificato i parametri degli agenti</span><span class="sxs-lookup"><span data-stu-id="9c300-270">Follow Up: After Changing Agent Parameters</span></span>  
 <span data-ttu-id="9c300-271">Le modifiche apportate al parametro dell'agente verranno applicate al successivo avvio dell'agente.</span><span class="sxs-lookup"><span data-stu-id="9c300-271">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="9c300-272">Se l'agente viene eseguito in modo continuo, è necessario arrestarlo e riavviarlo.</span><span class="sxs-lookup"><span data-stu-id="9c300-272">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c300-273">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c300-273">See Also</span></span>  
 <span data-ttu-id="9c300-274">[Profili degli agenti di replica](replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="9c300-274">[Replication Agent Profiles](replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="9c300-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span><span class="sxs-lookup"><span data-stu-id="9c300-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span></span>  
 <span data-ttu-id="9c300-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="9c300-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="9c300-277">[Replication Distribution Agent](replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="9c300-277">[Replication Distribution Agent](replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="9c300-278">[Replication Merge Agent](replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="9c300-278">[Replication Merge Agent](replication-merge-agent.md) </span></span>  
 [<span data-ttu-id="9c300-279">Agente di lettura coda repliche</span><span class="sxs-lookup"><span data-stu-id="9c300-279">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)  
  
  
