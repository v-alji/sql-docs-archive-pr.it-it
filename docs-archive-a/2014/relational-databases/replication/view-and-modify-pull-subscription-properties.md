---
title: Visualizzare e modificare le proprietà delle sottoscrizioni pull | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- modifying subscriptions
- viewing replication properties
- modifying replication properties, pull subscriptions
- pull subscriptions [SQL Server replication], modifying
- subscriptions [SQL Server replication], pull
- pull subscriptions [SQL Server replication], properties
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 1601e54f-86f0-49e8-b023-87a5d1def033
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b847a22d31bbf3ea7540c55339fe27531134125
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624010"
---
# <a name="view-and-modify-pull-subscription-properties"></a><span data-ttu-id="b2dab-102">Visualizzazione e modifica delle proprietà delle sottoscrizioni pull</span><span class="sxs-lookup"><span data-stu-id="b2dab-102">View and Modify Pull Subscription Properties</span></span>
  <span data-ttu-id="b2dab-103">In questo argomento viene descritto come modificare le proprietà delle sottoscrizioni pull in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="b2dab-103">This topic describes how to view and modify pull subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="b2dab-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b2dab-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b2dab-105">**Per visualizzare e modificare le proprietà delle sottoscrizioni pull tramite:**</span><span class="sxs-lookup"><span data-stu-id="b2dab-105">**To view and modify pull subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="b2dab-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2dab-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b2dab-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2dab-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b2dab-108">Oggetti RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="b2dab-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b2dab-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2dab-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b2dab-110">Visualizzare le proprietà delle sottoscrizioni pull dal server di pubblicazione o dal Sottoscrittore nella finestra di dialogo **Proprietà sottoscrizione - \<Publisher>: \<PublicationDatabase>** , disponibile in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2dab-110">View pull subscription properties from the Publisher or the Subscriber in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b2dab-111">Nel Sottoscrittore è disponibile un numero maggiore di proprietà ed è inoltre possibile modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="b2dab-111">More properties are visible from the Subscriber, and properties can be modified at the Subscriber.</span></span> <span data-ttu-id="b2dab-112">Le proprietà possono inoltre essere visualizzate sul server di pubblicazione nella scheda **Tutte le sottoscrizioni** , disponibile in Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="b2dab-112">You can also view properties from the Publisher on the **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="b2dab-113">Per informazioni sull'avvio di Monitoraggio replica, vedere [Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b2dab-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-management-studio"></a><span data-ttu-id="b2dab-114">Per visualizzare le proprietà delle sottoscrizioni pull dal server di pubblicazione in Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2dab-114">To view pull subscription properties from the Publisher in Management Studio</span></span>  
  
1.  <span data-ttu-id="b2dab-115">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="b2dab-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b2dab-116">Espandere la cartella **Replica** e quindi la cartella **Pubblicazioni locali** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="b2dab-117">Espandere la pubblicazione appropriata, fare clic con il pulsante destro del mouse su una sottoscrizione, quindi su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b2dab-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b2dab-118">Visualizzare le proprietà e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2dab-118">View properties, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-pull-subscription-properties-from-the-subscriber-in-management-studio"></a><span data-ttu-id="b2dab-119">Per visualizzare e modificare le proprietà delle sottoscrizioni pull dal Sottoscrittore in Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2dab-119">To view and modify pull subscription properties from the Subscriber in Management Studio</span></span>  
  
1.  <span data-ttu-id="b2dab-120">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="b2dab-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b2dab-121">Espandere la cartella **Replica** e quindi la cartella **Sottoscrizioni locali** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="b2dab-122">Fare clic con il pulsante destro del mouse su una sottoscrizione e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b2dab-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b2dab-123">Se necessario, modificare le proprietà e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2dab-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-replication-monitor"></a><span data-ttu-id="b2dab-124">Per visualizzare le proprietà delle sottoscrizioni pull dal server di pubblicazione in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="b2dab-124">To view pull subscription properties from the Publisher in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="b2dab-125">Espandere un gruppo di server di pubblicazione nel riquadro a sinistra di Monitoraggio replica, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b2dab-125">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="b2dab-126">Fare clic sulla scheda **Tutte le sottoscrizioni** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-126">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="b2dab-127">Fare clic con il pulsante destro del mouse su una sottoscrizione e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b2dab-127">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b2dab-128">Visualizzare le proprietà e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2dab-128">View properties, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b2dab-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2dab-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="b2dab-130">È possibile modificare le sottoscrizioni pull e accedere alle relative proprietà a livello di programmazione utilizzando stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="b2dab-130">Pull subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="b2dab-131">Le stored procedure utilizzate dipendono dal tipo di pubblicazione a cui appartiene la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b2dab-131">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b2dab-132">Per visualizzare le proprietà di una sottoscrizione pull di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="b2dab-132">To view the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b2dab-133">Nel Sottoscrittore eseguire [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2dab-133">At the Subscriber, execute [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span></span> <span data-ttu-id="b2dab-134">Specificare **@publisher** , **@publisher_db** e **@publication** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-134">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="b2dab-135">In tal modo verranno restituite le informazioni sulla sottoscrizione archiviate nelle tabelle di sistema del Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="b2dab-135">This returns information about the subscription that is stored in system tables at the Subscriber.</span></span>  
  
2.  <span data-ttu-id="b2dab-136">Nel Sottoscrittore eseguire [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2dab-136">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="b2dab-137">Specificare **@publisher** , **@publisher_db** , **@publication** e uno dei valori seguenti per **@publication_type** :</span><span class="sxs-lookup"><span data-stu-id="b2dab-137">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@publication_type**:</span></span>  
  
    -   <span data-ttu-id="b2dab-138">**0** : la sottoscrizione appartiene a una pubblicazione transazionale.</span><span class="sxs-lookup"><span data-stu-id="b2dab-138">**0** - Subscription belongs to a transactional publication.</span></span>  
  
    -   <span data-ttu-id="b2dab-139">**1** : la sottoscrizione appartiene a una pubblicazione snapshot.</span><span class="sxs-lookup"><span data-stu-id="b2dab-139">**1** - Subscription belongs to a snapshot publication.</span></span>  
  
3.  <span data-ttu-id="b2dab-140">Nel server di pubblicazione eseguire [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2dab-140">At the Publisher, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="b2dab-141">Specificare **@publication** e **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-141">Specify **@publication** and **@subscriber**.</span></span>  
  
4.  <span data-ttu-id="b2dab-142">Nel server di pubblicazione eseguire [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specificando **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-142">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="b2dab-143">In tal modo verranno visualizzate le informazioni sul Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="b2dab-143">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b2dab-144">Per modificare le proprietà di una sottoscrizione pull di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="b2dab-144">To change the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b2dab-145">Nel Sottoscrittore eseguire [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), specificando **@publisher** ,,, il **@publisher_db** **@publication** valore **0** (transazionale) o **1** (snapshot) per **@publication_type** , la proprietà della sottoscrizione da modificare come **@property** e il nuovo valore come **@value** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-145">At the Subscriber, execute [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), specifying **@publisher**, **@publisher_db**, **@publication**, a value of either **0** (transactional) or **1** (snapshot) for **@publication_type**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
2.  <span data-ttu-id="b2dab-146">(Facoltativo) Nel database di sottoscrizione del Sottoscrittore eseguire [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2dab-146">(Optional) At the Subscriber on the subscription database, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span></span> <span data-ttu-id="b2dab-147">Specificare l'ID del processo di agente di distribuzione per **@jobid** e le proprietà del pacchetto DTS (Data Transformation Services) seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2dab-147">Specify the ID of the Distribution Agent job for **@jobid**, and the following Data Transformation Services (DTS) package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="b2dab-148">In questo modo le proprietà del pacchetto DTS di una sottoscrizione verranno modificate.</span><span class="sxs-lookup"><span data-stu-id="b2dab-148">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b2dab-149">Per ottenere l'ID del processo, eseguire [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2dab-149">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="b2dab-150">Per visualizzare le proprietà di una sottoscrizione pull di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="b2dab-150">To view the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b2dab-151">Nel Sottoscrittore eseguire [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2dab-151">At the Subscriber, execute [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span></span> <span data-ttu-id="b2dab-152">Specificare **@publisher** , **@publisher_db** e **@publication** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-152">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span>  
  
2.  <span data-ttu-id="b2dab-153">Nel Sottoscrittore eseguire [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2dab-153">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="b2dab-154">Specificare **@publisher** , **@publisher_db** , **@publication** e il valore 2 per **@publication_type** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-154">Specify **@publisher**, **@publisher_db**, **@publication**, and a value of 2 for **@publication_type**.</span></span>  
  
3.  <span data-ttu-id="b2dab-155">Nel server di pubblicazione eseguire [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) per visualizzare le informazioni sulla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b2dab-155">At the Publisher, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) to display subscription information.</span></span> <span data-ttu-id="b2dab-156">Per restituire informazioni su una sottoscrizione specifica, è necessario specificare **@publication** , **@subscriber** e il valore **pull** per **@subscription_type** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-156">To return information on a specific subscription, you must specify **@publication**, **@subscriber**, and a value of **pull** for **@subscription_type**.</span></span>  
  
4.  <span data-ttu-id="b2dab-157">Nel server di pubblicazione eseguire [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specificando **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-157">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="b2dab-158">In tal modo verranno visualizzate le informazioni sul Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="b2dab-158">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="b2dab-159">Per modificare le proprietà di una sottoscrizione pull di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="b2dab-159">To change the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b2dab-160">Nel Sottoscrittore eseguire [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2dab-160">At the Subscriber, execute [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span></span> <span data-ttu-id="b2dab-161">Specificare **@publication** , **@publisher** , **@publisher_db** , la proprietà della sottoscrizione da modificare come **@property** e il nuovo valore come **@value** .</span><span class="sxs-lookup"><span data-stu-id="b2dab-161">Specify **@publication**, **@publisher**, **@publisher_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="b2dab-162">Utilizzo di RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="b2dab-162">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="b2dab-163">Le classi RMO utilizzate per la visualizzazione o la modifica delle proprietà di una sottoscrizione pull dipendono dal tipo di pubblicazione per cui viene creata la sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="b2dab-163">The RMO classes you use to view or modify pull subscription properties depend on the type of publication to which the pull subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b2dab-164">Per visualizzare o modificare le proprietà di una sottoscrizione pull di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="b2dab-164">To view or modify properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b2dab-165">Creare una connessione al Sottoscrittore tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="b2dab-165">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="b2dab-166">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.TransPullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="b2dab-166">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="b2dab-167">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>e <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="b2dab-167">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="b2dab-168">Impostare la connessione del passaggio 1 per la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="b2dab-168">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="b2dab-169">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per recuperare le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b2dab-169">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="b2dab-170">Se questo metodo restituisce `false`, le proprietà della sottoscrizione sono state definite in modo non corretto nel passaggio 3 oppure la sottoscrizione non esiste nel server.</span><span class="sxs-lookup"><span data-stu-id="b2dab-170">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="b2dab-171">(Facoltativo) Per modificare le proprietà, specificare un nuovo valore per una delle proprietà dell'oggetto <xref:Microsoft.SqlServer.Replication.TransPullSubscription> che è possibile impostare, quindi chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="b2dab-171">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="b2dab-172">(Facoltativo) Per visualizzare le nuove impostazioni, chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> per ricaricare le proprietà per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="b2dab-172">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="b2dab-173">Chiudere tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="b2dab-173">Close all connections.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="b2dab-174">Per visualizzare o modificare le proprietà di una sottoscrizione pull di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="b2dab-174">To view or modify properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b2dab-175">Creare una connessione al Sottoscrittore tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="b2dab-175">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="b2dab-176">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.MergePullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="b2dab-176">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="b2dab-177">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>e <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="b2dab-177">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="b2dab-178">Impostare la connessione del passaggio 1 per la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="b2dab-178">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="b2dab-179">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per recuperare le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b2dab-179">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="b2dab-180">Se questo metodo restituisce `false`, le proprietà della sottoscrizione sono state definite in modo non corretto nel passaggio 3 oppure la sottoscrizione non esiste nel server.</span><span class="sxs-lookup"><span data-stu-id="b2dab-180">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="b2dab-181">(Facoltativo) Per modificare le proprietà, specificare un nuovo valore per una delle proprietà dell'oggetto <xref:Microsoft.SqlServer.Replication.MergePullSubscription> che è possibile impostare, quindi chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="b2dab-181">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="b2dab-182">(Facoltativo) Per visualizzare le nuove impostazioni, chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> per ricaricare le proprietà per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="b2dab-182">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="b2dab-183">Chiudere tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="b2dab-183">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2dab-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2dab-184">See Also</span></span>  
 <span data-ttu-id="b2dab-185">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="b2dab-185">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="b2dab-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="b2dab-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="b2dab-187">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="b2dab-187">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
