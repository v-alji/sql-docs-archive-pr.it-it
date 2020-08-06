---
title: Disabilitare la pubblicazione e la distribuzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- disabling publishing
- publishing [SQL Server replication], disabling
- distribution disabling [SQL Server replication]
- removing replication
- replication [SQL Server], removing
- disabling replication
- disabling distribution
ms.assetid: 6d4a1474-4d13-4826-8be2-80050fafa8a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8843dac310d1e023fe7ce63eded02c9e1bed3731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624632"
---
# <a name="disable-publishing-and-distribution"></a><span data-ttu-id="d57cd-102">Disabilitazione della pubblicazione e della distribuzione</span><span class="sxs-lookup"><span data-stu-id="d57cd-102">Disable Publishing and Distribution</span></span>
  <span data-ttu-id="d57cd-103">In questo argomento viene descritto come disabilitare la pubblicazione e la distribuzione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="d57cd-103">This topic describes how to disable publishing and distribution in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="d57cd-104">È possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d57cd-104">You can do the following:</span></span>  
  
-   <span data-ttu-id="d57cd-105">Eliminare tutti i database di distribuzione dal database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-105">Delete all distribution databases on the Distributor.</span></span>  
  
-   <span data-ttu-id="d57cd-106">Disabilitare tutti i server di pubblicazione che utilizzano il server di distribuzione ed eliminare da tali server tutte le pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="d57cd-106">Disable all Publishers that use the Distributor and delete all publications on those Publishers.</span></span>  
  
-   <span data-ttu-id="d57cd-107">Eliminare tutte le sottoscrizioni delle pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="d57cd-107">Delete all subscriptions to the publications.</span></span> <span data-ttu-id="d57cd-108">I dati dei database di pubblicazione e sottoscrizione non vengono eliminati, ma la relazione di sincronizzazione con i database di pubblicazione andrà perduta.</span><span class="sxs-lookup"><span data-stu-id="d57cd-108">Data in the publication and subscription databases will not be deleted; however, it loses its synchronization relationship to any publication databases.</span></span> <span data-ttu-id="d57cd-109">L'eliminazione dei dati nel Sottoscrittore deve essere eseguita in modo manuale.</span><span class="sxs-lookup"><span data-stu-id="d57cd-109">If you want the data at the Subscriber to be deleted, you must delete it manually.</span></span>  
  
 <span data-ttu-id="d57cd-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d57cd-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d57cd-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="d57cd-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d57cd-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d57cd-112">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="d57cd-113">**Per disabilitare la pubblicazione e la distribuzione, utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="d57cd-113">**To disable publishing and distribution, using:**</span></span>  
  
     [<span data-ttu-id="d57cd-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d57cd-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d57cd-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d57cd-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="d57cd-116">Oggetti RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="d57cd-116">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d57cd-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d57cd-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d57cd-118">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d57cd-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="d57cd-119">Per disabilitare la pubblicazione e la distribuzione, è necessario che tutti i database di distribuzione e pubblicazione siano online.</span><span class="sxs-lookup"><span data-stu-id="d57cd-119">To disable publishing and distribution, all distribution and publication databases must be online.</span></span> <span data-ttu-id="d57cd-120">Se esistono *snapshot del database* per i database di distribuzione o di pubblicazione, è necessario eliminarli prima di disabilitare la pubblicazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-120">If any *database snapshots* exist for distribution or publication databases, they must be dropped before disabling publishing and distribution.</span></span> <span data-ttu-id="d57cd-121">Uno snapshot di database rappresenta una copia offline di sola lettura di un database e non è correlato a uno snapshot di replica.</span><span class="sxs-lookup"><span data-stu-id="d57cd-121">A database snapshot is a read-only offline copy of a database and is not related to a replication snapshot.</span></span> <span data-ttu-id="d57cd-122">Per altre informazioni, vedere [Snapshot del database &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d57cd-122">For more information, see [Database Snapshots &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d57cd-123">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d57cd-123">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d57cd-124">È possibile disabilitare la pubblicazione e la distribuzione utilizzando la Disabilitazione guidata pubblicazione e distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-124">Disable publishing and distribution by using the Disable Publishing and Distribution Wizard.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="d57cd-125">Per disabilitare la pubblicazione e la distribuzione</span><span class="sxs-lookup"><span data-stu-id="d57cd-125">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="d57cd-126">Connettersi al server di pubblicazione o al server di distribuzione da disabilitare in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="d57cd-126">Connect to the Publisher or Distributor you want to disable in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="d57cd-127">Fare clic con il pulsante destro del mouse sulla cartella **Replica** e quindi scegliere **Disabilita pubblicazione e distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="d57cd-127">Right-click the **Replication** folder, and then click **Disable Publishing and Distribution**.</span></span>  
  
3.  <span data-ttu-id="d57cd-128">Eseguire i vari passaggi della Disabilitazione guidata pubblicazione e distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-128">Complete the steps in the Disable Publishing and Distribution Wizard.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d57cd-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d57cd-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="d57cd-130">La pubblicazione e la distribuzione della replica possono essere disabilitate a livello di programmazione tramite le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="d57cd-130">Publishing and distributing can be disabled programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="d57cd-131">Per disabilitare la pubblicazione e la distribuzione</span><span class="sxs-lookup"><span data-stu-id="d57cd-131">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="d57cd-132">Arrestare tutti i processi correlati alla replica.</span><span class="sxs-lookup"><span data-stu-id="d57cd-132">Stop all replication-related jobs.</span></span> <span data-ttu-id="d57cd-133">Per un elenco di nomi di processo, vedere la sezione "Sicurezza agente in SQL Server Agent" sezione di [Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="d57cd-133">For a list of job names, see the "Agent Security Under SQL Server Agent" section of [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
2.  <span data-ttu-id="d57cd-134">Nel database di sottoscrizione di ogni Sottoscrittore eseguire [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) per rimuovere gli oggetti di replica dal database.</span><span class="sxs-lookup"><span data-stu-id="d57cd-134">At each Subscriber on the subscription database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span> <span data-ttu-id="d57cd-135">Questa stored procedure non rimuoverà i processi di replica nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-135">This stored procedure will not remove replication jobs at the Distributor.</span></span>  
  
3.  <span data-ttu-id="d57cd-136">Nel database di pubblicazione del server di pubblicazione eseguire [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) per rimuovere gli oggetti di replica dal database.</span><span class="sxs-lookup"><span data-stu-id="d57cd-136">At the Publisher on the publication database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span>  
  
4.  <span data-ttu-id="d57cd-137">Se il database di pubblicazione utilizza un server di distribuzione remoto, eseguire [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d57cd-137">If the Publisher uses a remote Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span></span>  
  
5.  <span data-ttu-id="d57cd-138">Nel server di distribuzione eseguire [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d57cd-138">At the Distributor, execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span> <span data-ttu-id="d57cd-139">Questa stored procedure deve essere eseguita una volta per ogni server di pubblicazione registrato nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-139">This stored procedure should be run once for each Publisher registered at the Distributor.</span></span>  
  
6.  <span data-ttu-id="d57cd-140">Nel database di distribuzione eseguire [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) per eliminare il database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-140">At the Distributor, execute [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) to delete the distribution database.</span></span> <span data-ttu-id="d57cd-141">Questa stored procedure deve essere eseguita una volta per ogni server di pubblicazione registrato nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-141">This stored procedure should be run once for each distribution database at the Distributor.</span></span> <span data-ttu-id="d57cd-142">Verranno anche rimossi gli eventuali processi dell'agente di lettura coda associati al database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-142">This also removes any Queue Reader Agent jobs associated with the distribution database.</span></span>  
  
7.  <span data-ttu-id="d57cd-143">Nel server di distribuzione eseguire [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) per rimuovere la designazione di server di distribuzione dal server.</span><span class="sxs-lookup"><span data-stu-id="d57cd-143">At the Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) to remove the Distributor designation from the server.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d57cd-144">Se prima dell'esecuzione di [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) e [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql)non vengono eliminati tutti gli oggetti di pubblicazione e distribuzione della replica, queste procedure restituiranno un errore.</span><span class="sxs-lookup"><span data-stu-id="d57cd-144">If all replication publishing and distribution objects are not dropped before you execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) and [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), these procedures will return an error.</span></span> <span data-ttu-id="d57cd-145">Per eliminare tutti gli oggetti correlati alla replica quando un server di pubblicazione o un server di distribuzione viene eliminato, è necessario impostare il parametro \*\* \@ no_checks\*\* su **1**.</span><span class="sxs-lookup"><span data-stu-id="d57cd-145">To drop all replication-related objects when a Publisher or Distributor is dropped, the **\@no_checks** parameter must be set to **1**.</span></span> <span data-ttu-id="d57cd-146">Se un server di pubblicazione o un server di distribuzione è offline o non raggiungibile, è possibile impostare il parametro \*\* \@ ignore_distributor\*\* su **1** in modo che sia possibile eliminarlo. Tuttavia, tutti gli oggetti di pubblicazione e distribuzione rimanenti devono essere rimossi manualmente.</span><span class="sxs-lookup"><span data-stu-id="d57cd-146">If a Publisher or Distributor is offline or unreachable, the **\@ignore_distributor** parameter can be set to **1** so that they can be dropped; however, any publishing and distributing objects left behind must be removed manually.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="d57cd-147">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d57cd-147">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="d57cd-148">In questo esempio di script vengono rimossi oggetti della replica dal database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-148">This example script removes replication objects from the subscription database.</span></span>  
  
 [!code-sql[HowTo#sp_removedbreplication](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_removedbreplication)]  
  
 <span data-ttu-id="d57cd-149">In questo esempio di script vengono disabilitate la pubblicazione e la distribuzione in un server che è un server di pubblicazione e un database di distribuzione e il database di distribuzione viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="d57cd-149">This example script disables publishing and distribution on a server that is a Publisher and Distributor and drops the distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_DropDistPub](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_dropdistpub)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="d57cd-150">Utilizzo di RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="d57cd-150">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="d57cd-151">Per disabilitare la pubblicazione e la distribuzione</span><span class="sxs-lookup"><span data-stu-id="d57cd-151">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="d57cd-152">Rimuovere tutte le sottoscrizioni di pubblicazioni che utilizzano il database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-152">Remove all subscriptions to publications that use the Distributor.</span></span> <span data-ttu-id="d57cd-153">Per ulteriori informazioni, vedere [Delete a Pull Subscription](delete-a-pull-subscription.md) e [Delete a Push Subscription](delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="d57cd-153">For more information, see [Delete a Pull Subscription](delete-a-pull-subscription.md) and [Delete a Push Subscription](delete-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="d57cd-154">Rimuovere tutte le pubblicazioni che utilizzano il server di distribuzione e disabilitare la pubblicazione per tutti i database se il server di pubblicazione e il server di distribuzione si trovano nello stesso server.</span><span class="sxs-lookup"><span data-stu-id="d57cd-154">Remove all publications that use the Distributor, and disable publishing for all databases if the Publisher and Distributor are on the same server.</span></span> <span data-ttu-id="d57cd-155">Per altre informazioni, vedere [Delete a Publication](publish/delete-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="d57cd-155">For more information, see [Delete a Publication](publish/delete-a-publication.md).</span></span>  
  
3.  <span data-ttu-id="d57cd-156">Creare una connessione al server di distribuzione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="d57cd-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
4.  <span data-ttu-id="d57cd-157">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="d57cd-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="d57cd-158">Specificare la proprietà <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> e passare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> ottenuto al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d57cd-158">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property, and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
5.  <span data-ttu-id="d57cd-159">(Facoltativo) Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per ottenere le proprietà dell'oggetto e verificare che il server di pubblicazione esista.</span><span class="sxs-lookup"><span data-stu-id="d57cd-159">(Optional) Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object and verify that the Publisher exists.</span></span> <span data-ttu-id="d57cd-160">Se il metodo restituisce `false`, il nome del server di pubblicazione impostato al passaggio 4 non è corretto oppure il server di pubblicazione non è utilizzato da questo server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-160">If this method returns `false`, the Publisher name set in step 4 was incorrect or the Publisher is not used by this Distributor.</span></span>  
  
6.  <span data-ttu-id="d57cd-161">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="d57cd-161">Call the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> method.</span></span> <span data-ttu-id="d57cd-162">Passare un valore di `true` per *Force* se il server di pubblicazione e il server di distribuzione si trovano in server diversi e quando il server di pubblicazione deve essere disinstallato dal server di distribuzione senza prima verificare che le pubblicazioni non esistano più nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-162">Pass a value of `true` for *force* if the Publisher and Distributor are on different servers, and when the Publisher should be uninstalled at the Distributor without first verifying that publications no longer exist at the Publisher.</span></span>  
  
7.  <span data-ttu-id="d57cd-163">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="d57cd-163">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="d57cd-164">Passare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> indicato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d57cd-164">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
8.  <span data-ttu-id="d57cd-165">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> .</span><span class="sxs-lookup"><span data-stu-id="d57cd-165">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> method.</span></span> <span data-ttu-id="d57cd-166">Passare il valore `true` per *Force* per rimuovere tutti gli oggetti di replica nel server di distribuzione senza prima verificare che tutti i database di pubblicazione locali siano stati disabilitati e che i database di distribuzione siano stati disinstallati.</span><span class="sxs-lookup"><span data-stu-id="d57cd-166">Pass a value of `true` for *force* to remove all replication objects at the Distributor without first verifying that all local publication databases have been disabled, and distribution databases have been uninstalled.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="d57cd-167">Esempi (RMO)</span><span class="sxs-lookup"><span data-stu-id="d57cd-167">Examples (RMO)</span></span>  
 <span data-ttu-id="d57cd-168">In questo esempio viene rimossa la registrazione del server di pubblicazione nel database di distribuzione, viene eliminato il database di distribuzione e viene disinstallato il database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-168">This example removes the Publisher registration at the Distributor, drops the distribution database, and uninstalls the Distributor.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpub)]  
  
 <span data-ttu-id="d57cd-169">In questo esempio viene disinstallato il server di distribuzione senza prima disabilitare i database di pubblicazione locali o eliminare il database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d57cd-169">This example uninstalls the Distributor without first disabling local publication databases or dropping the distribution database.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPubForce](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpubforce)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPubForce](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpubforce)]  
  
## <a name="see-also"></a><span data-ttu-id="d57cd-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d57cd-170">See Also</span></span>  
 <span data-ttu-id="d57cd-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="d57cd-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 [<span data-ttu-id="d57cd-172">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="d57cd-172">Replication System Stored Procedures Concepts</span></span>](concepts/replication-system-stored-procedures-concepts.md)  
  
  
