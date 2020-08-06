---
title: Visualizzare e modificare le proprietà delle sottoscrizioni push | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- push subscriptions [SQL Server replication], properties
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], modifying
- modifying replication properties, push subscriptions
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 801d2995-7aa5-4626-906e-c8190758ec71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1506d4f83fcfb94d62efd01c4d6447048fecfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722680"
---
# <a name="view-and-modify-push-subscription-properties"></a><span data-ttu-id="9dfa8-102">Visualizzazione e modifica delle proprietà delle sottoscrizioni push</span><span class="sxs-lookup"><span data-stu-id="9dfa8-102">View and Modify Push Subscription Properties</span></span>
  <span data-ttu-id="9dfa8-103">In questo argomento viene descritto come modificare le proprietà delle sottoscrizioni push in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="9dfa8-103">This topic describes how to view and modify push subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="9dfa8-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="9dfa8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9dfa8-105">**Per visualizzare e modificare le proprietà delle sottoscrizioni push, utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="9dfa8-105">**To view and modify push subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="9dfa8-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9dfa8-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9dfa8-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9dfa8-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="9dfa8-108">Oggetti RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="9dfa8-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9dfa8-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9dfa8-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9dfa8-110">Visualizzare e modificare le proprietà della sottoscrizione push dal server di pubblicazione nella:</span><span class="sxs-lookup"><span data-stu-id="9dfa8-110">View and modify push subscription properties from the Publisher in:</span></span>  
  
-   <span data-ttu-id="9dfa8-111">Finestra di dialogo **Proprietà sottoscrizione - \<Publisher>: \<PublicationDatabase>** , disponibile in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9dfa8-111">The **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="9dfa8-112">Scheda **Tutte le sottoscrizioni** , disponibile in Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-112">The **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="9dfa8-113">Per informazioni sull'avvio di Monitoraggio replica, vedere [Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9dfa8-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-management-studio"></a><span data-ttu-id="9dfa8-114">Per visualizzare e modificare le proprietà della sottoscrizione push in Management Studio</span><span class="sxs-lookup"><span data-stu-id="9dfa8-114">To view and modify push subscription properties in Management Studio</span></span>  
  
1.  <span data-ttu-id="9dfa8-115">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="9dfa8-116">Espandere la cartella **Replica** e quindi la cartella **Pubblicazioni locali** .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="9dfa8-117">Espandere la pubblicazione appropriata, fare clic con il pulsante destro del mouse su una sottoscrizione, quindi su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="9dfa8-118">Se necessario, modificare le proprietà e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-118">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-replication-monitor"></a><span data-ttu-id="9dfa8-119">Per visualizzare e modificare le proprietà della sottoscrizione push in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="9dfa8-119">To view and modify push subscription properties in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="9dfa8-120">Espandere un gruppo di server di pubblicazione nel riquadro a sinistra di Monitoraggio replica, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-120">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="9dfa8-121">Fare clic sulla scheda **Tutte le sottoscrizioni** .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-121">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="9dfa8-122">Fare clic con il pulsante destro del mouse su una sottoscrizione e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="9dfa8-123">Se necessario, modificare le proprietà e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9dfa8-124">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9dfa8-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="9dfa8-125">È possibile modificare le sottoscrizioni push e accedere alle relative proprietà a livello di programmazione utilizzando stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-125">Push subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="9dfa8-126">Le stored procedure utilizzate dipendono dal tipo di pubblicazione a cui appartiene la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-126">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="9dfa8-127">Per visualizzare le proprietà di una sottoscrizione push di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="9dfa8-127">To view the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="9dfa8-128">Nel database di pubblicazione del server di pubblicazione eseguire [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9dfa8-128">At the Publisher on the publication database, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="9dfa8-129">Specificare **@publication** , **@subscriber** e il valore **All** per **@article** .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-129">Specify **@publication**, **@subscriber**, and a value of **all** for **@article**.</span></span>  
  
2.  <span data-ttu-id="9dfa8-130">Nel database di pubblicazione del server di pubblicazione eseguire [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql)specificando **@subscriber**.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-130">At the Publisher on the publication database, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="9dfa8-131">Per modificare le proprietà di una sottoscrizione push di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="9dfa8-131">To change the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="9dfa8-132">Nel database di pubblicazione del server di pubblicazione eseguire [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql)specificando **@subscriber** e gli eventuali parametri per le proprietà del Sottoscrittore da modificare.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-132">At the Publisher on the publication database, execute [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), specifying **@subscriber** and any parameters for the Subscriber properties being changed.</span></span>  
  
2.  <span data-ttu-id="9dfa8-133">Nel database di pubblicazione del server di pubblicazione eseguire [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9dfa8-133">At the Publisher on the publication database, execute [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span></span> <span data-ttu-id="9dfa8-134">Specificare **@publication** , **@subscriber** , **@destination_db** , il valore **All** per **@article** , la proprietà della sottoscrizione da modificare come **@property** e il nuovo valore come **@value** .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-134">Specify **@publication**, **@subscriber**, **@destination_db**, a value of **all** for **@article**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span> <span data-ttu-id="9dfa8-135">In questo modo vengono modificate le impostazioni di sicurezza per la sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-135">This changes security settings for the push subscription.</span></span>  
  
3.  <span data-ttu-id="9dfa8-136">(Facoltativo) Per modificare le proprietà del pacchetto DTS (Data Transformation Services) di una sottoscrizione, eseguire [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) nel database di sottoscrizione del Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-136">(Optional) To change the Data Transformation Services (DTS) package properties of a subscription, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="9dfa8-137">Specificare l'ID del processo di agente di distribuzione per **@jobid** e le proprietà del pacchetto DTS seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dfa8-137">Specify the ID of the Distribution Agent job for **@jobid** and the following DTS package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="9dfa8-138">In questo modo le proprietà del pacchetto DTS di una sottoscrizione verranno modificate.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-138">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9dfa8-139">Per ottenere l'ID del processo, eseguire [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9dfa8-139">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="9dfa8-140">Per visualizzare le proprietà di una sottoscrizione push di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="9dfa8-140">To view the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="9dfa8-141">Nel database di pubblicazione del server di pubblicazione eseguire [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9dfa8-141">At the Publisher on the publication database, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span></span> <span data-ttu-id="9dfa8-142">Specificare **@publication** e **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-142">Specify **@publication** and **@subscriber**.</span></span>  
  
2.  <span data-ttu-id="9dfa8-143">Nel server di pubblicazione eseguire [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specificando **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-143">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="9dfa8-144">Per modificare le proprietà di una sottoscrizione push di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="9dfa8-144">To change the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="9dfa8-145">Nel database di pubblicazione del server di pubblicazione eseguire [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9dfa8-145">At the Publisher on the publication database, execute [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span></span> <span data-ttu-id="9dfa8-146">Specificare **@publication** , **@subscriber** , **@subscriber_db** , la proprietà della sottoscrizione da modificare come **@property** e il nuovo valore come **@value** .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-146">Specify **@publication**, **@subscriber**, **@subscriber_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9dfa8-147">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9dfa8-147">Example (Transact-SQL)</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="9dfa8-148">Utilizzo di RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="9dfa8-148">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="9dfa8-149">Le classi RMO utilizzate per la visualizzazione o la modifica delle proprietà di una sottoscrizione push dipendono dal tipo di pubblicazione per cui viene creata la sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-149">The RMO classes you use to view or modify push subscription properties depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="9dfa8-150">Per visualizzare o modificare le proprietà di una sottoscrizione push di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="9dfa8-150">To view or modify properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="9dfa8-151">Creare una connessione al server di pubblicazione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9dfa8-152">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="9dfa8-153">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>e <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-153">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="9dfa8-154">Impostare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del passaggio 1 per l'impostazione della proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-154">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="9dfa8-155">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per recuperare le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-155">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="9dfa8-156">Se questo metodo restituisce `false`, le proprietà della sottoscrizione sono state definite in modo non corretto nel passaggio 3 oppure la sottoscrizione non esiste.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-156">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="9dfa8-157">(Facoltativo) Per modificare le proprietà, specificare un nuovo valore per una delle proprietà dell'oggetto <xref:Microsoft.SqlServer.Replication.TransSubscription> che è possibile impostare, quindi chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-157">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="9dfa8-158">(Facoltativo) Per visualizzare le nuove impostazioni, chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> per ricaricare le proprietà per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-158">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="9dfa8-159">Per visualizzare o modificare le proprietà di una sottoscrizione push di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="9dfa8-159">To view or modify properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="9dfa8-160">Creare una connessione al Sottoscrittore tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-160">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9dfa8-161">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-161">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="9dfa8-162">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>e <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-162">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="9dfa8-163">Impostare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del passaggio 1 per l'impostazione della proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-163">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="9dfa8-164">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per recuperare le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-164">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="9dfa8-165">Se questo metodo restituisce `false`, le proprietà della sottoscrizione sono state definite in modo non corretto nel passaggio 3 oppure la sottoscrizione non esiste.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-165">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="9dfa8-166">(Facoltativo) Per modificare le proprietà, specificare un nuovo valore per una delle proprietà dell'oggetto <xref:Microsoft.SqlServer.Replication.MergeSubscription> che è possibile impostare, quindi chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="9dfa8-166">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="9dfa8-167">(Facoltativo) Per visualizzare le nuove impostazioni, chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> per ricaricare le proprietà per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="9dfa8-167">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dfa8-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dfa8-168">See Also</span></span>  
 <span data-ttu-id="9dfa8-169">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9dfa8-169">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="9dfa8-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="9dfa8-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="9dfa8-171">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="9dfa8-171">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
