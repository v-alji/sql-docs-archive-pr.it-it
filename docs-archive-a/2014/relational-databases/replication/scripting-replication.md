---
title: Creazione di script di replica | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server replication], replication objects
- merge replication scripting [SQL Server replication]
- replication [SQL Server], scripting
- snapshot replication [SQL Server], scripting
- scripts [SQL Server replication]
- transactional replication, scripting
ms.assetid: e50fac44-54c0-470c-a4ea-9c111fa4322b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e865e2664a399bca4738c1fc157bef176f35e96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624020"
---
# <a name="scripting-replication"></a><span data-ttu-id="8d837-102">Creazione di script di replica</span><span class="sxs-lookup"><span data-stu-id="8d837-102">Scripting Replication</span></span>
  <span data-ttu-id="8d837-103">Gli script di tutti i componenti di replica inclusi in una topologia devono essere creati come parte di un piano di ripristino di emergenza. Gli script possono inoltre essere utilizzati per automatizzare attività ripetitive.</span><span class="sxs-lookup"><span data-stu-id="8d837-103">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="8d837-104">Uno script contiene le stored procedure di sistema Transact-SQL necessarie per l'implementazione dei componenti di replica, ad esempio una pubblicazione o una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="8d837-104">A script contains the Transact-SQL system stored procedures necessary to implement the replication component(s) scripted, such as a publication or subscription.</span></span> <span data-ttu-id="8d837-105">È possibile creare gli script tramite una procedura guidata, come la Creazione guidata nuova pubblicazione, o in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dopo aver creato un componente.</span><span class="sxs-lookup"><span data-stu-id="8d837-105">Scripts can be created in a wizard (such as the New Publication Wizard) or in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] after you create a component.</span></span> <span data-ttu-id="8d837-106">È possibile visualizzare, modificare ed eseguire lo script utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="8d837-106">You can view, modify, and run the script using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or **sqlcmd**.</span></span> <span data-ttu-id="8d837-107">Gli script possono essere memorizzati con file di backup da utilizzare nel caso in cui sia necessario riconfigurare una topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="8d837-107">Scripts can be stored with backup files to be used in case a replication topology must be reconfigured.</span></span>  
  
 <span data-ttu-id="8d837-108">È necessario creare un nuovo script per un componente se vengono apportate modifiche alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="8d837-108">A component should be re-scripted if any property changes are made.</span></span> <span data-ttu-id="8d837-109">Se si utilizzano stored procedure personalizzate con la replica transazionale, è consigliabile archiviare una copia di ogni procedura con gli script, aggiornando la copia in caso di modifica della procedura. Le procedure vengono in genere aggiornate in seguito a modifiche dello schema o a nuove esigenze applicative.</span><span class="sxs-lookup"><span data-stu-id="8d837-109">If you use custom stored procedures with transactional replication, a copy of each procedure should be stored with the scripts; the copy should be updated if the procedure changes (procedures are typically updated due to schema changes or changing application requirements).</span></span> <span data-ttu-id="8d837-110">Per altre informazioni sulle procedure personalizzate, vedere [Specificare la modalità di propagazione delle modifiche per gli articoli transazionali](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="8d837-110">For more information about custom procedures, see [Specify How Changes Are Propagated for Transactional Articles](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
 <span data-ttu-id="8d837-111">Per le pubblicazioni di tipo merge che utilizzano filtri con parametri, gli script di pubblicazione contengono le chiamate alle stored procedure per la creazione di partizioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="8d837-111">For merge publications that use parameterized filters, publication scripts contain the stored procedure calls to create data partitions.</span></span> <span data-ttu-id="8d837-112">Lo script offre un riferimento per le partizioni create e un modo per ricreare, se necessario, una o più partizioni.</span><span class="sxs-lookup"><span data-stu-id="8d837-112">The script provides a reference for the partitions created and a way in which to re-create one or more partitions if necessary.</span></span>  
  
## <a name="example-of-automating-a-task-with-scripts"></a><span data-ttu-id="8d837-113">Esempio di automazione di un'attività tramite script</span><span class="sxs-lookup"><span data-stu-id="8d837-113">Example of Automating a Task with Scripts</span></span>  
 <span data-ttu-id="8d837-114">Si consideri [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], che implementa la replica di tipo merge per distribuire dati alla forza vendita remota.</span><span class="sxs-lookup"><span data-stu-id="8d837-114">Consider [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], which implements merge replication to distribute data to its remote sales force.</span></span> <span data-ttu-id="8d837-115">Una rappresentante scarica tutti i dati relativi ai clienti nella propria zona utilizzando sottoscrizioni pull.</span><span class="sxs-lookup"><span data-stu-id="8d837-115">A sales representative downloads all the data that pertains to the customers in her territory using pull subscriptions.</span></span> <span data-ttu-id="8d837-116">Lavorando offline, la rappresentante aggiorna i dati e immette nuovi clienti e ordini.</span><span class="sxs-lookup"><span data-stu-id="8d837-116">When working offline, the sales representative updates data and enters new customers and orders.</span></span> <span data-ttu-id="8d837-117">Poiché [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] dispone di oltre cinquanta rappresentanti in zone diverse, la creazione delle diverse sottoscrizioni in ogni Sottoscrittore mediante la Creazione guidata nuova sottoscrizione richiederebbe una notevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="8d837-117">Because [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] has more than fifty sales representatives in different territories, it would be time-consuming to create the different subscriptions at each Subscriber with the New Subscription Wizard.</span></span> <span data-ttu-id="8d837-118">L'amministratore della replica può invece eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="8d837-118">Instead, the replication administrator can follow these steps:</span></span>  
  
1.  <span data-ttu-id="8d837-119">Impostare le pubblicazioni di tipo merge necessarie con partizioni basate sul rappresentante o sulla zona.</span><span class="sxs-lookup"><span data-stu-id="8d837-119">Set up the necessary merge publications with partitions based on the sales representative or their territory.</span></span>  
  
2.  <span data-ttu-id="8d837-120">Creare una sottoscrizione pull per un Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="8d837-120">Create a pull subscription for one Subscriber.</span></span>  
  
3.  <span data-ttu-id="8d837-121">Generare uno script basato su tale sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="8d837-121">Generate a script based on that pull subscription.</span></span>  
  
4.  <span data-ttu-id="8d837-122">Modificare lo script, modificando valori come il nome del Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="8d837-122">Modify the script, changing such values as the name of the Subscriber.</span></span>  
  
5.  <span data-ttu-id="8d837-123">Eseguire lo script in più Sottoscrittori per generare le sottoscrizioni pull necessarie.</span><span class="sxs-lookup"><span data-stu-id="8d837-123">Run the script at multiple Subscribers to generate the required pull subscriptions.</span></span>  
  
## <a name="script-replication-objects"></a><span data-ttu-id="8d837-124">Creazione di script per gli oggetti di replica</span><span class="sxs-lookup"><span data-stu-id="8d837-124">Script Replication Objects</span></span>  
 <span data-ttu-id="8d837-125">Creare script per gli oggetti di replica tramite le procedure guidate per la replica o dalla cartella **Replica** in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d837-125">Script replication objects from the replication wizards or from the **Replication** folder in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8d837-126">Se si utilizzano le procedure guidate, è possibile scegliere di creare oggetti e includerli in script o solo di includerli in script.</span><span class="sxs-lookup"><span data-stu-id="8d837-126">If you script from the wizards, you can choose to create objects and script them, or you can choose only to script them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8d837-127">Negli script tutte le password sono impostate come NULL.</span><span class="sxs-lookup"><span data-stu-id="8d837-127">All passwords are scripted as NULL.</span></span> <span data-ttu-id="8d837-128">Se possibile, richiedere agli utenti di immettere le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8d837-128">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="8d837-129">Se si archiviano le credenziali in un file di script, è necessario proteggere il file per impedire l'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="8d837-129">If you store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="8d837-130">Per ulteriori informazioni sull'utilizzo delle procedure guidate di replica, vedere:</span><span class="sxs-lookup"><span data-stu-id="8d837-130">For more information about using the replication wizards, see:</span></span>  
  
-   [<span data-ttu-id="8d837-131">Configurare la pubblicazione e la distribuzione</span><span class="sxs-lookup"><span data-stu-id="8d837-131">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
-   [<span data-ttu-id="8d837-132">Creare una pubblicazione</span><span class="sxs-lookup"><span data-stu-id="8d837-132">Create a Publication</span></span>](publish/create-a-publication.md)  
  
-   [<span data-ttu-id="8d837-133">Creare una sottoscrizione push</span><span class="sxs-lookup"><span data-stu-id="8d837-133">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
-   [<span data-ttu-id="8d837-134">Create a Pull Subscription</span><span class="sxs-lookup"><span data-stu-id="8d837-134">Create a Pull Subscription</span></span>](create-a-pull-subscription.md)  
  
#### <a name="to-script-an-object-from-a-replication-wizard"></a><span data-ttu-id="8d837-135">Per creare script per un oggetto da una procedura guidata di replica</span><span class="sxs-lookup"><span data-stu-id="8d837-135">To script an object from a replication wizard</span></span>  
  
1.  <span data-ttu-id="8d837-136">Nella pagina **Azioni procedura guidata** della procedura guidata selezionare la casella di controllo appropriata:</span><span class="sxs-lookup"><span data-stu-id="8d837-136">On the **Wizard Actions** page of a wizard, select the check box appropriate for the wizard:</span></span>  
  
    -   <span data-ttu-id="8d837-137">**Genera un file script con i passaggi per la creazione della pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="8d837-137">**Generate a script file with steps to create a publication**</span></span>  
  
    -   <span data-ttu-id="8d837-138">**Genera un file script con i passaggi per la creazione delle sottoscrizioni**</span><span class="sxs-lookup"><span data-stu-id="8d837-138">**Generate a script file with steps to create the subscription(s)**</span></span>  
  
    -   <span data-ttu-id="8d837-139">**Genera un file script con i passaggi per la configurazione della distribuzione**</span><span class="sxs-lookup"><span data-stu-id="8d837-139">**Generate a script file with steps to configure distribution**</span></span>  
  
2.  <span data-ttu-id="8d837-140">Specificare le opzioni nella pagina **Proprietà file script** .</span><span class="sxs-lookup"><span data-stu-id="8d837-140">Specify options on the **Script File Properties** page.</span></span>  
  
3.  <span data-ttu-id="8d837-141">Completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8d837-141">Complete the wizard.</span></span>  
  
#### <a name="to-script-an-object-from-management-studio"></a><span data-ttu-id="8d837-142">Per creare script per un oggetto da Management Studio</span><span class="sxs-lookup"><span data-stu-id="8d837-142">To script an object from Management Studio</span></span>  
  
1.  <span data-ttu-id="8d837-143">Connettersi al server di distribuzione, al server di pubblicazione o al Sottoscrittore in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="8d837-143">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="8d837-144">Espandere la cartella **Replica** e quindi la cartella **Pubblicazioni locali** o la cartella **Sottoscrizioni locali** .</span><span class="sxs-lookup"><span data-stu-id="8d837-144">Expand the **Replication** folder, and then expand the **Local Publications** folder or the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="8d837-145">Fare clic con il pulsante destro del mouse su una pubblicazione o una sottoscrizione e quindi scegliere **Genera script**.</span><span class="sxs-lookup"><span data-stu-id="8d837-145">Right-click a publication or subscription, and then click **Generate Scripts**.</span></span>  
  
4.  <span data-ttu-id="8d837-146">Specificare le opzioni nella finestra di dialogo **Genera script SQL - \<ReplicationObject>** .</span><span class="sxs-lookup"><span data-stu-id="8d837-146">Specify options in the **Generate SQL Script - \<ReplicationObject>** dialog box.</span></span>  
  
5.  <span data-ttu-id="8d837-147">Fare clic su **Genera script nel file**.</span><span class="sxs-lookup"><span data-stu-id="8d837-147">Click **Script to File**.</span></span>  
  
6.  <span data-ttu-id="8d837-148">Immettere un nome di file nella finestra di dialogo **Percorso file script** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8d837-148">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="8d837-149">Viene visualizzato un messaggio di stato.</span><span class="sxs-lookup"><span data-stu-id="8d837-149">A status message is displayed.</span></span>  
  
7.  <span data-ttu-id="8d837-150">Fare clic su **OK**, quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8d837-150">Click **OK**, and then click **Close**.</span></span>  
  
#### <a name="to-script-multiple-objects-from-management-studio"></a><span data-ttu-id="8d837-151">Per creare script per più oggetti da Management Studio</span><span class="sxs-lookup"><span data-stu-id="8d837-151">To script multiple objects from Management Studio</span></span>  
  
1.  <span data-ttu-id="8d837-152">Connettersi al server di distribuzione, al server di pubblicazione o al Sottoscrittore in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="8d837-152">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="8d837-153">Fare clic con il pulsante destro del mouse sulla cartella **Replica** e quindi scegliere **Genera script**.</span><span class="sxs-lookup"><span data-stu-id="8d837-153">Right-click the **Replication** folder, and then click **Generate Scripts**.</span></span>  
  
3.  <span data-ttu-id="8d837-154">Specificare le opzioni nella finestra di dialogo **Genera script SQL** .</span><span class="sxs-lookup"><span data-stu-id="8d837-154">Specify options in the **Generate SQL Script** dialog box.</span></span>  
  
4.  <span data-ttu-id="8d837-155">Fare clic su **Genera script nel file**.</span><span class="sxs-lookup"><span data-stu-id="8d837-155">Click **Script to File**.</span></span>  
  
5.  <span data-ttu-id="8d837-156">Immettere un nome di file nella finestra di dialogo **Percorso file script** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8d837-156">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="8d837-157">Viene visualizzato un messaggio di stato.</span><span class="sxs-lookup"><span data-stu-id="8d837-157">A status message is displayed.</span></span>  
  
6.  <span data-ttu-id="8d837-158">Fare clic su **OK** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8d837-158">Click **OK, and then** click **Close**.</span></span>  
  
  
