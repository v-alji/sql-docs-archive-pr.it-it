---
title: Distribuire i criteri pianificati in più istanze | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: f551b8e8-3668-4ed4-852f-bae826254f4f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 30faf94c2033be43ac035517e58d5a18c0c68ab8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712664"
---
# <a name="deploy-scheduled-policies-to-multiple-instances"></a><span data-ttu-id="11e8a-102">Distribuzione di criteri pianificati in istanze multiple</span><span class="sxs-lookup"><span data-stu-id="11e8a-102">Deploy Scheduled Policies to Multiple Instances</span></span>
  <span data-ttu-id="11e8a-103">Tramite Server registrati è possibile distribuire criteri pianificati a server gestiti da una posizione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="11e8a-103">By using Registered Servers, you can deploy scheduled policies to managed servers from a central location.</span></span> <span data-ttu-id="11e8a-104">È possibile distribuire i criteri pianificati da un gruppo di server locali o da un server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="11e8a-104">You can deploy scheduled policies from either a local server group, or from a Central Management Server.</span></span>  
  
 <span data-ttu-id="11e8a-105">In questa attività, verranno effettuate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="11e8a-105">In this task, you will do the following:</span></span>  
  
1.  <span data-ttu-id="11e8a-106">Esportazione in una cartella dei criteri pianificati nell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="11e8a-106">Export the policies that you scheduled in the previous task to a folder.</span></span>  
  
2.  <span data-ttu-id="11e8a-107">Distribuzione dei criteri pianificati a istanze di destinazione gestite mediante Server registrati.</span><span class="sxs-lookup"><span data-stu-id="11e8a-107">Deploy the scheduled policies to target instances that are managed through Registered Servers.</span></span>  
  
 <span data-ttu-id="11e8a-108">Tali attività verranno eseguite nel computer utilizzato per completare le attività precedenti di questa lezione.</span><span class="sxs-lookup"><span data-stu-id="11e8a-108">You will perform these tasks on the computer where you completed the previous tasks in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="11e8a-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="11e8a-109">Prerequisites</span></span>  
 <span data-ttu-id="11e8a-110">Di seguito vengono indicati i prerequisiti di questa attività:</span><span class="sxs-lookup"><span data-stu-id="11e8a-110">This task has the following prerequisites:</span></span>  
  
-   <span data-ttu-id="11e8a-111">È necessario avere completato le attività precedenti di questa lezione.</span><span class="sxs-lookup"><span data-stu-id="11e8a-111">You must have completed the previous tasks in this lesson.</span></span>  
  
-   <span data-ttu-id="11e8a-112">È necessario che nelle istanze in cui si desidera distribuire i criteri pianificati sia in esecuzione [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="11e8a-112">The instances where you want to deploy the scheduled policies must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="11e8a-113">Ai fini dell'automazione è necessario che i criteri siano archiviati localmente, operazione non supportata nelle versioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11e8a-113">Automation requires the policies to be stored locally, which is not supported on versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
-   <span data-ttu-id="11e8a-114">I server in cui si desidera distribuire i criteri pianificati devono essere registrati in Server registrati nel nodo **gruppi di server locali** o **server di gestione centrale** .</span><span class="sxs-lookup"><span data-stu-id="11e8a-114">The servers where you want to deploy the scheduled policies must be registered in Registered Servers in either the **Local Server Groups** or the **Central Management Servers** node.</span></span> <span data-ttu-id="11e8a-115">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="11e8a-115">For more information, see the following topics:</span></span>  
  
    -   [<span data-ttu-id="11e8a-116">Creare o modificare un gruppo di server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="11e8a-116">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
    -   <span data-ttu-id="11e8a-117">[Registrare un server connesso &#40;&#41;SQL Server Management Studio ](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="11e8a-117">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
    -   [<span data-ttu-id="11e8a-118">Creare un server di gestione centrale e un gruppo di server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="11e8a-118">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-export-the-scheduled-policies-as-xml-files"></a><span data-ttu-id="11e8a-119">Per esportare i criteri pianificati come file xml</span><span class="sxs-lookup"><span data-stu-id="11e8a-119">To export the scheduled policies as .xml files</span></span>  
  
1.  <span data-ttu-id="11e8a-120">Nel server in cui sono stati configurati i criteri pianificati nell'attività precedente espandere **gestione**, **Gestione criteri**, quindi fare clic su **criteri**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-120">On the server where you configured scheduled policies in the previous task, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span>  
  
2.  <span data-ttu-id="11e8a-121">Scegliere **Dettagli Esplora oggetti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-121">On the **View** menu, click **Object Explorer Details**.</span></span>  
  
3.  <span data-ttu-id="11e8a-122">Nel riquadro **dettagli Esplora oggetti** selezionare tutti i criteri per procedure consigliate pianificati che si desidera distribuire in altri server tramite Server registrati.</span><span class="sxs-lookup"><span data-stu-id="11e8a-122">In the **Object Explorer Details** pane, select all the scheduled best practices policies that you want to deploy to other servers through Registered Servers.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="11e8a-123">È possibile fare clic sull'intestazione **categoria** per ordinare i criteri per categoria.</span><span class="sxs-lookup"><span data-stu-id="11e8a-123">You can click the **Category** heading to sort the policies by category.</span></span>  
  
4.  <span data-ttu-id="11e8a-124">Fare clic con il pulsante destro del mouse sulla selezione, quindi scegliere **Esporta criteri**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-124">Right-click the selection, and then click **Export Policy**.</span></span>  
  
5.  <span data-ttu-id="11e8a-125">Se sono stati selezionati più criteri da esportare, nella finestra di dialogo **Sfoglia per cartelle** selezionare una cartella di destinazione o creare una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="11e8a-125">If you selected multiple policies to export, in the **Browse For Folder** dialog box, select a destination folder, or create a new folder.</span></span> <span data-ttu-id="11e8a-126">Per questa lezione, creare una nuova cartella con il percorso **c:\ Scheduled_BP_Policies**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-126">For this lesson, create a new folder with the path **C:\Scheduled_BP_Policies**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="11e8a-127">Se è stato selezionato un solo criterio da esportare, nella finestra di dialogo **Esporta criteri** creare una nuova cartella con il percorso **c:\ Scheduled_BP_Policies**, fare clic su **Apri**e quindi su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-127">If you only selected one policy to export, in the **Export Policy** dialog box, create a new folder with the path **C:\Scheduled_BP_Policies**, click **Open**, and then click **Save**.</span></span>  
  
     <span data-ttu-id="11e8a-128">I file xml dei criteri vengono creati nel percorso della cartella.</span><span class="sxs-lookup"><span data-stu-id="11e8a-128">The .xml policy files are created in the folder location.</span></span>  
  
### <a name="to-deploy-the-scheduled-policies-to-servers-that-are-managed-through-registered-servers"></a><span data-ttu-id="11e8a-129">Per distribuire i criteri pianificati in server gestiti mediante Server registrati</span><span class="sxs-lookup"><span data-stu-id="11e8a-129">To deploy the scheduled policies to servers that are managed through Registered Servers</span></span>  
  
1.  <span data-ttu-id="11e8a-130">Scegliere **Server registrati** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-130">On the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="11e8a-131">Espandere **motore di database**, espandere **gruppi di server locali** o **server di gestione centrale**, fare clic con il pulsante destro del mouse sul nodo in cui si desidera distribuire i criteri e quindi fare clic su **Importa criteri**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-131">Expand **Database Engine**, expand either **Local Server Groups** or **Central Management Servers**, right-click the node that you want to deploy the policies to, and then click **Import Policies**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="11e8a-132">Se si fa clic con il pulsante destro del mouse su **gruppi di server locali** o sul server di gestione centrale stesso, i criteri verranno distribuiti in tutti i server gestiti.</span><span class="sxs-lookup"><span data-stu-id="11e8a-132">If you right-click **Local Server Groups** or the Central Management Server itself, the policies will be deployed to all managed servers.</span></span> <span data-ttu-id="11e8a-133">Se si fa clic con il pulsante destro del mouse su un gruppo di server specifico, i criteri verranno distribuiti solo in tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="11e8a-133">If you right-click a specific server group, the policies will only be deployed to servers in that group.</span></span> <span data-ttu-id="11e8a-134">Se si fa clic con il pulsante destro del mouse su un server registrato specifico, i criteri verranno distribuiti solo in tale server.</span><span class="sxs-lookup"><span data-stu-id="11e8a-134">If you right-click a specific registered server, the policies will only be deployed to that server.</span></span>  
  
3.  <span data-ttu-id="11e8a-135">Accanto a **file da importare**fare clic sul pulsante con i puntini di sospensione (**...**).</span><span class="sxs-lookup"><span data-stu-id="11e8a-135">Next to **Files to import**, click the ellipsis button (**...**).</span></span>  
  
4.  <span data-ttu-id="11e8a-136">Nella finestra di dialogo **Seleziona criterio** passare al percorso della cartella in cui sono stati salvati i criteri pianificati.</span><span class="sxs-lookup"><span data-stu-id="11e8a-136">In the **Select Policy** dialog box, browse to the folder location where you saved the scheduled policies.</span></span> <span data-ttu-id="11e8a-137">Per questo esempio, passare al percorso **c:\ Scheduled_BP_Policies**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-137">For this example, browse to the location **C:\Scheduled_BP_Policies**.</span></span>  
  
5.  <span data-ttu-id="11e8a-138">Selezionare i criteri che si desidera importare nelle istanze di destinazione, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-138">Select the policies that you want to import to the target instances, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="11e8a-139">Nella finestra di dialogo **Importa** selezionare lo stato dei criteri desiderato nell'elenco **stato criteri** .</span><span class="sxs-lookup"><span data-stu-id="11e8a-139">In the **Import** dialog box, in the **Policy state** list, select the desired policy state.</span></span> <span data-ttu-id="11e8a-140">È possibile scegliere di mantenere lo stato dei criteri, abilitare o disabilitare i criteri durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="11e8a-140">You can choose to preserve the policy state, enable, or disable the policies on import.</span></span> <span data-ttu-id="11e8a-141">Tenere presente che i criteri devono essere abilitati per poter essere eseguiti in base a una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="11e8a-141">Be aware that the policies must be enabled to run on a schedule.</span></span>  
  
7.  <span data-ttu-id="11e8a-142">Fare clic su **OK** per importare i criteri in tutte le istanze di destinazione.</span><span class="sxs-lookup"><span data-stu-id="11e8a-142">Click **OK** to import the policies to all the target instances.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="11e8a-143">Se si verificano errori, la finestra di dialogo **Importa** non scomparirà.</span><span class="sxs-lookup"><span data-stu-id="11e8a-143">If there are any errors, the **Import** dialog box does not disappear.</span></span> <span data-ttu-id="11e8a-144">Fare clic sulla pagina **log** per esaminare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="11e8a-144">Click the **Log** page to review the messages.</span></span> <span data-ttu-id="11e8a-145">Fare clic su **Annulla**per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="11e8a-145">Click **Cancel** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="11e8a-146">Per visualizzare i criteri da un'istanza di destinazione, connettersi all'istanza di, aprire Esplora oggetti, espandere **gestione**, quindi espandere **criteri**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-146">To view the policies from a target instance, connect to the instance, open Object Explorer, expand **Management**, and then expand **Policies**.</span></span> <span data-ttu-id="11e8a-147">Verranno visualizzati i criteri importati nel nodo **criteri** .</span><span class="sxs-lookup"><span data-stu-id="11e8a-147">You should see the imported policies in the **Policies** node.</span></span> <span data-ttu-id="11e8a-148">Se si fa doppio clic su ciascuno dei criteri, è possibile visualizzare la pianificazione o modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="11e8a-148">If you double-click each policy, you can view the schedule, or change the settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="11e8a-149">Per visualizzare i risultati di valutazione dopo l'esecuzione di criteri pianificati, aprire il log Cronologia criteri nell'istanza di destinazione.</span><span class="sxs-lookup"><span data-stu-id="11e8a-149">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="11e8a-150">Per aprire il log, fare clic con il pulsante destro del mouse su **Gestione criteri**, quindi scegliere **Visualizza cronologia**.</span><span class="sxs-lookup"><span data-stu-id="11e8a-150">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="11e8a-151">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="11e8a-151">Summary</span></span>  
 <span data-ttu-id="11e8a-152">In questa esercitazione è stato illustrato come eseguire valutazioni su richiesta e pianificate dei criteri per procedure consigliate per una o più istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11e8a-152">This tutorial has shown you how to perform both on-demand and scheduled evaluations of the best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="next"></a><span data-ttu-id="11e8a-153">Prossima</span><span class="sxs-lookup"><span data-stu-id="11e8a-153">Next</span></span>  
 <span data-ttu-id="11e8a-154">L'esercitazione è completata.</span><span class="sxs-lookup"><span data-stu-id="11e8a-154">This tutorial is finished.</span></span> <span data-ttu-id="11e8a-155">Per tornare all'inizio, vedere [esercitazione: valutazione delle procedure consigliate tramite la gestione basata su criteri](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="11e8a-155">To return to the start, see [Tutorial: Evaluating Best Practices by Using Policy-Based Management](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="11e8a-156">Per visualizzare un elenco delle [!INCLUDE[ssDE](../includes/ssde-md.md)] esercitazioni, fare clic su [motore di database esercitazioni](../relational-databases/database-engine-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="11e8a-156">To see a list of [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorials, click [Database Engine Tutorials](../relational-databases/database-engine-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e8a-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11e8a-157">See Also</span></span>  
 [<span data-ttu-id="11e8a-158">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="11e8a-158">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
