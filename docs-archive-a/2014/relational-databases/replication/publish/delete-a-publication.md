---
title: Eliminare una pubblicazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing publications
- publications [SQL Server replication], deleting
- articles [SQL Server replication], deleting
- deleting publications
ms.assetid: 408a1360-12ee-4896-ac94-482ae839593b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d2b39a326d59333868b4f8015eb9a2e59d59e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725460"
---
# <a name="delete-a-publication"></a><span data-ttu-id="2a454-102">Eliminazione di una pubblicazione</span><span class="sxs-lookup"><span data-stu-id="2a454-102">Delete a Publication</span></span>
  <span data-ttu-id="2a454-103">In questo argomento viene descritto come eliminare una pubblicazione in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="2a454-103">This topic describes how to delete a publication in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="2a454-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2a454-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2a454-105">**Per eliminare una pubblicazione, utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="2a454-105">**To delete a publication, using:**</span></span>  
  
     [<span data-ttu-id="2a454-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a454-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2a454-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a454-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="2a454-108">Oggetti RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="2a454-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2a454-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a454-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2a454-110">Eliminare le pubblicazioni dalla cartella **Pubblicazioni locali** in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a454-110">Delete publications from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-a-publication"></a><span data-ttu-id="2a454-111">Per eliminare una pubblicazione</span><span class="sxs-lookup"><span data-stu-id="2a454-111">To delete a publication</span></span>  
  
1.  <span data-ttu-id="2a454-112">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="2a454-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="2a454-113">Espandere la cartella **Replica** e quindi la cartella **Pubblicazioni locali** .</span><span class="sxs-lookup"><span data-stu-id="2a454-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="2a454-114">Fare clic con il pulsante destro del mouse sulla pubblicazione che si desidera eliminare e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="2a454-114">Right-click the publication you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2a454-115">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a454-115">Using Transact-SQL</span></span>  
 <span data-ttu-id="2a454-116">È possibile eliminare pubblicazioni a livello di programmazione tramite le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="2a454-116">Publications can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="2a454-117">Le stored procedure utilizzate dipendono dal tipo di pubblicazione eliminato.</span><span class="sxs-lookup"><span data-stu-id="2a454-117">The stored procedures that you use depend on the type of publication being deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a454-118">L'eliminazione di una pubblicazione non comporta la rimozione degli oggetti pubblicati dal database di pubblicazione o degli oggetti corrispondenti dal database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="2a454-118">Deleting a publication does not remove published objects from the publication database or the corresponding objects from the subscription database.</span></span> <span data-ttu-id="2a454-119">Utilizzare il comando `DROP <object>` per rimuovere manualmente questi oggetti, se necessario.</span><span class="sxs-lookup"><span data-stu-id="2a454-119">Use the `DROP <object>` command to manually remove these objects if necessary.</span></span>  
  
#### <a name="to-delete-a-snapshot-or-transactional-publication"></a><span data-ttu-id="2a454-120">Per eliminare una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="2a454-120">To delete a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="2a454-121">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a454-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="2a454-122">Per eliminare una singola pubblicazione, eseguire [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) nel database di pubblicazione del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="2a454-122">To delete a single publication, execute [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="2a454-123">Per eliminare tutte le pubblicazioni e rimuovere tutti gli oggetti di replica da un database pubblicato, eseguire [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="2a454-123">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="2a454-124">Specificare un valore `tran` per \*\* \@ tipo\*\*.</span><span class="sxs-lookup"><span data-stu-id="2a454-124">Specify a value of `tran` for **\@type**.</span></span> <span data-ttu-id="2a454-125">(Facoltativo) Se il server di distribuzione non è accessibile oppure se lo stato del database è sospetto oppure offline, specificare il valore **1** per **\@force**.</span><span class="sxs-lookup"><span data-stu-id="2a454-125">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="2a454-126">(Facoltativo) Specificare il nome del database per **\@dbname** se [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) non viene eseguita nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="2a454-126">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2a454-127">Specificando il valore **1** per **\@force**, è possibile che nel database rimangano oggetti di pubblicazione correlati alla replica.</span><span class="sxs-lookup"><span data-stu-id="2a454-127">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="2a454-128">(Facoltativo) Se il database non contiene altre pubblicazioni, eseguire [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) per disabilitare la pubblicazione del database corrente usando la replica snapshot o transazionale.</span><span class="sxs-lookup"><span data-stu-id="2a454-128">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using snapshot or transactional replication.</span></span>  
  
3.  <span data-ttu-id="2a454-129">(Facoltativo) Nel database di sottoscrizione del Sottoscrittore eseguire [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) per rimuovere gli eventuali metadati di replica rimanenti nel database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="2a454-129">(Optional) At the Subscriber on the subscription database, execute [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-merge-publication"></a><span data-ttu-id="2a454-130">Per eliminare una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="2a454-130">To delete a merge publication</span></span>  
  
1.  <span data-ttu-id="2a454-131">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a454-131">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="2a454-132">Per eliminare una singola pubblicazione, eseguire [sp_dropmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) nel database di pubblicazione del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="2a454-132">To delete a single publication, execute [sp_dropmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="2a454-133">Per eliminare tutte le pubblicazioni e rimuovere tutti gli oggetti di replica da un database pubblicato, eseguire [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="2a454-133">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="2a454-134">Specificare un valore `merge` per \*\* \@ tipo\*\*.</span><span class="sxs-lookup"><span data-stu-id="2a454-134">Specify a value of `merge` for **\@type**.</span></span> <span data-ttu-id="2a454-135">(Facoltativo) Se il server di distribuzione non è accessibile oppure se lo stato del database è sospetto oppure offline, specificare il valore **1** per **\@force**.</span><span class="sxs-lookup"><span data-stu-id="2a454-135">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="2a454-136">(Facoltativo) Specificare il nome del database per **\@dbname** se [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) non viene eseguita nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="2a454-136">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2a454-137">Specificando il valore **1** per **\@force**, è possibile che nel database rimangano oggetti di pubblicazione correlati alla replica.</span><span class="sxs-lookup"><span data-stu-id="2a454-137">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="2a454-138">(Facoltativo) Se il database non contiene altre pubblicazioni, eseguire [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) per disabilitare la pubblicazione del database corrente usando la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="2a454-138">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using merge replication.</span></span>  
  
3.  <span data-ttu-id="2a454-139">(Facoltativo) Nel database di sottoscrizione del Sottoscrittore eseguire [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) per rimuovere gli eventuali metadati di replica rimanenti nel database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="2a454-139">(Optional) At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="2a454-140">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a454-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="2a454-141">In questo esempio viene illustrato come rimuovere una pubblicazione transazionale e disabilitare la pubblicazione transazionale per un database.</span><span class="sxs-lookup"><span data-stu-id="2a454-141">This example shows how to remove a transactional publication and disable transactional publishing for a database.</span></span> <span data-ttu-id="2a454-142">Si presuppone che in precedenza siano state rimosse tutte le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="2a454-142">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="2a454-143">Per ulteriori informazioni, vedere [Delete a Pull Subscription](../delete-a-pull-subscription.md) o [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="2a454-143">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_droppublication](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droppublication)]  
  
 <span data-ttu-id="2a454-144">In questo esempio viene illustrato come rimuovere una pubblicazione di tipo merge e disabilitare la pubblicazione di tipo merge per un database.</span><span class="sxs-lookup"><span data-stu-id="2a454-144">This example shows how to remove a merge publication and disable merge publishing for a database.</span></span> <span data-ttu-id="2a454-145">Si presuppone che in precedenza siano state rimosse tutte le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="2a454-145">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="2a454-146">Per ulteriori informazioni, vedere [Delete a Pull Subscription](../delete-a-pull-subscription.md) o [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="2a454-146">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_dropmergepublication](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergepublication)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="2a454-147">Utilizzo di RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="2a454-147">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="2a454-148">È possibile eliminare pubblicazioni a livello di programmazione tramite gli oggetti RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="2a454-148">You can delete publications programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="2a454-149">Le classi RMO utilizzate per rimuovere una pubblicazione dipendono dal tipo di pubblicazione rimossa.</span><span class="sxs-lookup"><span data-stu-id="2a454-149">The RMO classes that you use to remove a publication depend on the type of publication you remove.</span></span>  
  
#### <a name="to-remove-a-snapshot-or-transactional-publication"></a><span data-ttu-id="2a454-150">Per rimuovere una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="2a454-150">To remove a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="2a454-151">Creare una connessione al server di pubblicazione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="2a454-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="2a454-152">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.TransPublication>.</span><span class="sxs-lookup"><span data-stu-id="2a454-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPublication> class.</span></span>  
  
3.  <span data-ttu-id="2a454-153">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> e <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> per la pubblicazione, quindi impostare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> sulla connessione creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="2a454-153">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="2a454-154">Controllare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> per verificare che la pubblicazione sia esistente.</span><span class="sxs-lookup"><span data-stu-id="2a454-154">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="2a454-155">Se il valore di questa proprietà è `false`, le proprietà di pubblicazione sono state definite in modo non corretto nel passaggio 3 oppure la pubblicazione non esiste.</span><span class="sxs-lookup"><span data-stu-id="2a454-155">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="2a454-156">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="2a454-156">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="2a454-157">(Facoltativo) Se per il database non esistono altre pubblicazioni transazionali, è possibile disabilitare il database per la pubblicazione transazionale come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2a454-157">(Optional) If no other transactional publications exist for this database, the database can be disabled for transactional publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="2a454-158">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="2a454-158">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="2a454-159">Impostare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> sull'istanza di <xref:Microsoft.SqlServer.Management.Common.ServerConnection> restituita al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="2a454-159">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1.</span></span>  
  
    2.  <span data-ttu-id="2a454-160">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="2a454-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="2a454-161">Se il metodo restituisce `false`, verificare che il database esista.</span><span class="sxs-lookup"><span data-stu-id="2a454-161">If this method returns `false`, confirm that the database exists.</span></span>  
  
    3.  <span data-ttu-id="2a454-162">Impostare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="2a454-162">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="2a454-163">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="2a454-163">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="2a454-164">Chiudere le connessioni.</span><span class="sxs-lookup"><span data-stu-id="2a454-164">Close the connections.</span></span>  
  
#### <a name="to-remove-a-merge-publication"></a><span data-ttu-id="2a454-165">Per rimuovere una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="2a454-165">To remove a merge publication</span></span>  
  
1.  <span data-ttu-id="2a454-166">Creare una connessione al server di pubblicazione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="2a454-166">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="2a454-167">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.MergePublication>.</span><span class="sxs-lookup"><span data-stu-id="2a454-167">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePublication> class.</span></span>  
  
3.  <span data-ttu-id="2a454-168">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> e <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> per la pubblicazione, quindi impostare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> sulla connessione creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="2a454-168">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="2a454-169">Controllare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> per verificare che la pubblicazione sia esistente.</span><span class="sxs-lookup"><span data-stu-id="2a454-169">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="2a454-170">Se il valore di questa proprietà è `false`, le proprietà di pubblicazione sono state definite in modo non corretto nel passaggio 3 oppure la pubblicazione non esiste.</span><span class="sxs-lookup"><span data-stu-id="2a454-170">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="2a454-171">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="2a454-171">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="2a454-172">(Facoltativo) Se per il database non esistono altre pubblicazioni di tipo merge, è possibile disabilitare il database per la pubblicazione di tipo merge come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2a454-172">(Optional) If no other merge publications exist for this database, the database can be disabled for merge publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="2a454-173">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="2a454-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="2a454-174">Impostare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> sull'istanza di <xref:Microsoft.SqlServer.Management.Common.ServerConnection> restituita al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="2a454-174">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from Step 1.</span></span>  
  
    2.  <span data-ttu-id="2a454-175">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="2a454-175">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="2a454-176">Se il metodo restituisce `false`, verificare che il database esista.</span><span class="sxs-lookup"><span data-stu-id="2a454-176">If this method returns `false`, verify that the database exists.</span></span>  
  
    3.  <span data-ttu-id="2a454-177">Impostare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="2a454-177">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="2a454-178">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="2a454-178">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="2a454-179">Chiudere le connessioni.</span><span class="sxs-lookup"><span data-stu-id="2a454-179">Close the connections.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="2a454-180">Esempi (RMO)</span><span class="sxs-lookup"><span data-stu-id="2a454-180">Examples (RMO)</span></span>  
 <span data-ttu-id="2a454-181">Nell'esempio seguente viene eliminata una pubblicazione transazionale.</span><span class="sxs-lookup"><span data-stu-id="2a454-181">The following example deletes a transactional publication.</span></span> <span data-ttu-id="2a454-182">Se per il database non esistono altre pubblicazioni transazionali, verrà anche disabilitata la pubblicazione transazionale.</span><span class="sxs-lookup"><span data-stu-id="2a454-182">If no other transactional publications exist for this database, transactional publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpub)]  
  
 <span data-ttu-id="2a454-183">Nell'esempio seguente viene eliminata una pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="2a454-183">The following example deletes a merge publication.</span></span> <span data-ttu-id="2a454-184">Se per il database non esistono altre pubblicazioni di tipo merge, verrà anche disabilitata la pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="2a454-184">If no other merge publications exist for this database, merge publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropMergePub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropmergepub)]  
  
 [!code-vb[HowTo#rmo_vb_DropMergePub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropmergepub)]  
  
## <a name="see-also"></a><span data-ttu-id="2a454-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a454-185">See Also</span></span>  
 <span data-ttu-id="2a454-186">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="2a454-186">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="2a454-187">Pubblicare dati e oggetti di database</span><span class="sxs-lookup"><span data-stu-id="2a454-187">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
