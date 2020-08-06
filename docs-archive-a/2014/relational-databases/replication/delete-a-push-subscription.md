---
title: Eliminare una sottoscrizione push | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing subscriptions
- push subscriptions [SQL Server replication], deleting
- deleting subscriptions
- subscriptions [SQL Server replication], push
ms.assetid: 3c4847e2-aed9-4488-b45d-8164422bdb10
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 912958e00d117f51c5dc95c0dc1247d278acb0ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624636"
---
# <a name="delete-a-push-subscription"></a><span data-ttu-id="77af4-102">Eliminazione di una sottoscrizione push</span><span class="sxs-lookup"><span data-stu-id="77af4-102">Delete a Push Subscription</span></span>
  <span data-ttu-id="77af4-103">In questo argomento viene descritto come eliminare una sottoscrizione push in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="77af4-103">This topic describes how to delete a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="77af4-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="77af4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="77af4-105">**Per eliminare una sottoscrizione push, utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="77af4-105">**To delete a push subscription, using:**</span></span>  
  
     [<span data-ttu-id="77af4-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77af4-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="77af4-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77af4-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="77af4-108">Oggetti RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="77af4-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="77af4-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77af4-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="77af4-110">Eliminare una sottoscrizione push dal server di pubblicazione (dalla cartella **Pubblicazioni locali** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) o dal Sottoscrittore (dalla cartella **Sottoscrizioni locali** ).</span><span class="sxs-lookup"><span data-stu-id="77af4-110">Delete a push subscription at the Publisher (from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) or the Subscriber (from the **Local Subscriptions** folder).</span></span> <span data-ttu-id="77af4-111">Se si elimina una sottoscrizione, gli oggetti o i dati non vengono rimossi automaticamente dalla sottoscrizione, ma è necessario rimuoverli manualmente.</span><span class="sxs-lookup"><span data-stu-id="77af4-111">Deleting a subscription does not remove objects or data from the subscription; they must be removed manually.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-publisher"></a><span data-ttu-id="77af4-112">Per eliminare una sottoscrizione push dal server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="77af4-112">To delete a push subscription at the Publisher</span></span>  
  
1.  <span data-ttu-id="77af4-113">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="77af4-113">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="77af4-114">Espandere la cartella **Replica** e quindi la cartella **Pubblicazioni locali** .</span><span class="sxs-lookup"><span data-stu-id="77af4-114">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="77af4-115">Espandere la pubblicazione associata alla sottoscrizione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="77af4-115">Expand the publication associated with the subscription you want to delete.</span></span>  
  
4.  <span data-ttu-id="77af4-116">Fare clic con il pulsante destro del mouse sulla sottoscrizione e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="77af4-116">Right-click the subscription, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="77af4-117">Nella finestra di dialogo di conferma specificare se connettersi al Sottoscrittore per eliminare le informazioni sulla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="77af4-117">In the confirmation dialog box, select whether to connect to the Subscriber to delete subscription information.</span></span> <span data-ttu-id="77af4-118">Se si deseleziona la casella di controllo **Connetti al Sottoscrittore** , è necessario connettersi al Sottoscrittore in un secondo momento per eliminare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="77af4-118">If you clear the **Connect to Subscriber** checkbox, you should connect to the Subscriber later to delete the information.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-subscriber"></a><span data-ttu-id="77af4-119">Per eliminare una sottoscrizione push dal Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="77af4-119">To delete a push subscription at the Subscriber</span></span>  
  
1.  <span data-ttu-id="77af4-120">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="77af4-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="77af4-121">Espandere la cartella **Replica** e quindi la cartella **Sottoscrizioni locali** .</span><span class="sxs-lookup"><span data-stu-id="77af4-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="77af4-122">Fare clic con il pulsante destro del mouse sulla sottoscrizione che si desidera eliminare e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="77af4-122">Right-click the subscription you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="77af4-123">Nella finestra di dialogo di conferma specificare se connettersi al server di pubblicazione per eliminare le informazioni sulla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="77af4-123">In the confirmation dialog box, select whether to connect to the Publisher to delete subscription information.</span></span> <span data-ttu-id="77af4-124">Se si deseleziona la casella di controllo **Connetti al server di pubblicazione** , sarà necessario connettersi al server di pubblicazione in seguito per eliminare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="77af4-124">If you clear the **Connect to Publisher** check box, you should connect to the Publisher later to delete the information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="77af4-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77af4-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="77af4-126">È possibile eliminare sottoscrizioni push a livello di programmazione tramite le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="77af4-126">Push subscriptions can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="77af4-127">Le stored procedure utilizzate dipendono dal tipo di pubblicazione a cui appartiene la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="77af4-127">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="77af4-128">Per eliminare una sottoscrizione push di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="77af4-128">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="77af4-129">Nel database di pubblicazione del server di pubblicazione eseguire [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77af4-129">At the Publisher on the publication database, execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span> <span data-ttu-id="77af4-130">Specificare **@publication** e **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="77af4-130">Specify **@publication** and **@subscriber**.</span></span> <span data-ttu-id="77af4-131">Specificare il valore **all** per il parametro **@article**.</span><span class="sxs-lookup"><span data-stu-id="77af4-131">Specify a value of **all** for **@article**.</span></span> <span data-ttu-id="77af4-132">(Facoltativo) Se non è possibile accedere al database di distribuzione, specificare il valore **1** per il parametro **@ignore_distributor** per eliminare la sottoscrizione senza rimuovere gli oggetti correlati nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="77af4-132">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="77af4-133">Nel database di sottoscrizione del Sottoscrittore eseguire [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) per rimuovere i metadati di replica nel database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="77af4-133">At the Subscriber on the subscription database, execute [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="77af4-134">Per eliminare una sottoscrizione push di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="77af4-134">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="77af4-135">Nel server di pubblicazione eseguire [sp_dropmergesubscription &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), specificando **@publication** **@subscriber** e **@subscriber_db** .</span><span class="sxs-lookup"><span data-stu-id="77af4-135">At the Publisher, execute [sp_dropmergesubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), specifying **@publication**, **@subscriber** and **@subscriber_db**.</span></span> <span data-ttu-id="77af4-136">(Facoltativo) Se non è possibile accedere al database di distribuzione, specificare il valore **1** per il parametro **@ignore_distributor** per eliminare la sottoscrizione senza rimuovere gli oggetti correlati nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="77af4-136">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="77af4-137">Nel database di sottoscrizione del Sottoscrittore eseguire [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77af4-137">At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span></span> <span data-ttu-id="77af4-138">Specificare **@publisher** , **@publisher_db** e **@publication** .</span><span class="sxs-lookup"><span data-stu-id="77af4-138">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="77af4-139">per rimuovere i metadati di merge dal database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="77af4-139">This removes merge metadata from the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="77af4-140">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="77af4-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="77af4-141">In questo esempio viene eliminata una sottoscrizione push di una pubblicazione transazionale.</span><span class="sxs-lookup"><span data-stu-id="77af4-141">This example deletes a push subscription to a transactional publication.</span></span>  
  
 [!code-sql[HowTo#sp_droptransubscription](../../snippets/tsql/SQL15/replication/howto/tsql/droptranpullsub.sql#sp_droptransubscription)]  
  
 <span data-ttu-id="77af4-142">In questo esempio viene eliminata una sottoscrizione push di una pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="77af4-142">This example deletes a push subscription to a merge publication.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergesubscription](../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepullsub.sql#sp_dropmergesubscription)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="77af4-143">Utilizzo di RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="77af4-143">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="77af4-144">Le classi RMO utilizzate per l'eliminazione di una sottoscrizione push dipendono dal tipo di pubblicazione per cui viene creata la sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="77af4-144">The RMO classes that you use to delete a push subscription depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="77af4-145">Per eliminare una sottoscrizione push di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="77af4-145">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="77af4-146">Creare una connessione al Sottoscrittore tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="77af4-146">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="77af4-147">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="77af4-147">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="77af4-148">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>e <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="77af4-148">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="77af4-149">Impostare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del passaggio 1 per la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="77af4-149">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="77af4-150">Controllare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> per verificare che la sottoscrizione sia esistente.</span><span class="sxs-lookup"><span data-stu-id="77af4-150">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="77af4-151">Se il valore di questa proprietà è `false`, le proprietà di sottoscrizioni sono state definite in modo non corretto nel passaggio 2 oppure la sottoscrizione non esiste.</span><span class="sxs-lookup"><span data-stu-id="77af4-151">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="77af4-152">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="77af4-152">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="77af4-153">Per eliminare una sottoscrizione push di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="77af4-153">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="77af4-154">Creare una connessione al Sottoscrittore tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="77af4-154">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="77af4-155">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="77af4-155">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="77af4-156">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>e <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="77af4-156">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="77af4-157">Impostare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del passaggio 1 per la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="77af4-157">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="77af4-158">Controllare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> per verificare che la sottoscrizione sia esistente.</span><span class="sxs-lookup"><span data-stu-id="77af4-158">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="77af4-159">Se il valore di questa proprietà è `false`, le proprietà di sottoscrizioni sono state definite in modo non corretto nel passaggio 2 oppure la sottoscrizione non esiste.</span><span class="sxs-lookup"><span data-stu-id="77af4-159">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="77af4-160">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="77af4-160">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="77af4-161">Esempi (RMO)</span><span class="sxs-lookup"><span data-stu-id="77af4-161">Examples (RMO)</span></span>  
 <span data-ttu-id="77af4-162">È possibile eliminare sottoscrizioni push a livello di programmazione tramite gli oggetti RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="77af4-162">You can delete push subscriptions programmatically by using Replication Management Objects (RMO).</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="77af4-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77af4-163">See Also</span></span>  
 <span data-ttu-id="77af4-164">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="77af4-164">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="77af4-165">Procedure consigliate per la sicurezza della replica</span><span class="sxs-lookup"><span data-stu-id="77af4-165">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
