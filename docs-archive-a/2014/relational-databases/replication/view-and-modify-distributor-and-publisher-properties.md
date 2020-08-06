---
title: Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- Distributors [SQL Server replication], modifying
- modifying replication properties, Distributors
- Distributors [SQL Server replication], properties
ms.assetid: 5dae1d59-c377-4c6e-adc9-b68c5b328f79
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 571f6f3a0d44f0fc87c67885249fca441776946d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626625"
---
# <a name="view-and-modify-distributor-and-publisher-properties"></a><span data-ttu-id="daf5d-102">Visualizzazione e modifica delle proprietà del server di pubblicazione e del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="daf5d-102">View and Modify Distributor and Publisher Properties</span></span>
  <span data-ttu-id="daf5d-103">In questo argomento viene descritto come visualizzare e modificare le proprietà del database di distribuzione e del server di pubblicazione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="daf5d-103">This topic describes how to view and modify Distributor and Publisher properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="daf5d-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="daf5d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="daf5d-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="daf5d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="daf5d-106">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="daf5d-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="daf5d-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="daf5d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="daf5d-108">**Per visualizzare e modificare le proprietà di server di pubblicazione e database di distribuzione, utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="daf5d-108">**To view and modify Distributor and Publisher properties, using:**</span></span>  
  
     [<span data-ttu-id="daf5d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daf5d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="daf5d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="daf5d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="daf5d-111">Oggetti RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="daf5d-111">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="daf5d-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="daf5d-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="daf5d-113">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="daf5d-113">Recommendations</span></span>  
  
-   <span data-ttu-id="daf5d-114">Per i server di pubblicazione che eseguono versioni precedenti a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], un utente nel ruolo predefinito del server **sysadmin** può registrare i Sottoscrittori nella pagina **Sottoscrittori**.</span><span class="sxs-lookup"><span data-stu-id="daf5d-114">For Publishers running versions prior to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user in the **sysadmin** fixed server role can register Subscribers on the **Subscribers** page.</span></span> <span data-ttu-id="daf5d-115">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]non è più necessario registrare esplicitamente i Sottoscrittori per la replica.</span><span class="sxs-lookup"><span data-stu-id="daf5d-115">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], it is no longer necessary to explicitly register Subscribers for replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="daf5d-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="daf5d-116">Security</span></span>  
 <span data-ttu-id="daf5d-117">Se possibile, richiedere agli utenti di immettere le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-117">When possible, prompt users to enter security credentials at runtime.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="daf5d-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daf5d-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="daf5d-119">Per visualizzare e modificare le proprietà del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="daf5d-119">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="daf5d-120">Connettersi al database di distribuzione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="daf5d-120">Connect to the Distributor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="daf5d-121">Fare clic con il pulsante destro del mouse sulla cartella **Replica** e quindi scegliere **Proprietà server di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="daf5d-121">Right-click the **Replication** folder, and then click **Distributor Properties**.</span></span>  
  
3.  <span data-ttu-id="daf5d-122">Visualizzare e modificare le proprietà nella finestra di dialogo **Proprietà database di distribuzione - \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="daf5d-122">View and modify properties in the **Distributor Properties - \<Distributor>** dialog box.</span></span>  
  
    -   <span data-ttu-id="daf5d-123">Per visualizzare e modificare le proprietà di un database di distribuzione, fare clic sul pulsante delle proprietà ( **...** ) relativo al database nella pagina **Generale** della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="daf5d-123">To view and modify properties for a distribution database, click the properties button (**...**) for the database on the **General** page of thedialog box.</span></span>  
  
    -   <span data-ttu-id="daf5d-124">Per visualizzare e modificare le proprietà del server di pubblicazione associato al database di distribuzione, fare clic sul pulsante delle proprietà ( **...** ) relativo al server di pubblicazione nella pagina **Server di pubblicazione** della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="daf5d-124">To view and modify Publisher properties associated with the Distributor, click the properties button (**...**) for the Publisher on the **Publishers** page of the dialog box.</span></span>  
  
    -   <span data-ttu-id="daf5d-125">Per accedere ai profili degli agenti di replica, fare clic sul pulsante **Impostazioni predefinite profili** nella pagina **Generale** della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="daf5d-125">To access profiles for replication agents, click the **Profile Defaults** button on the **General** page of the dialog box.</span></span> <span data-ttu-id="daf5d-126">Per altre informazioni, vedere [Replication Agent Profiles](agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="daf5d-126">For more information, see [Replication Agent Profiles](agents/replication-agent-profiles.md).</span></span>  
  
    -   <span data-ttu-id="daf5d-127">Per modificare la password dell'account utilizzato quando stored procedure di amministrazione vengono eseguite sul server di pubblicazione e aggiornano le informazioni sul server di distribuzione, immettere una nuova password nelle caselle **Password** e **Conferma password** della pagina **Server di pubblicazione** della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="daf5d-127">To change the password for the account used when administrative stored procedures execute at the Publisher and update information at the Distributor, enter a new password in the **Password** and **Confirm password** boxes on the **Publishers** page of the dialog box.</span></span> <span data-ttu-id="daf5d-128">Per altre informazioni, vedere [Sicurezza del database di distribuzione](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="daf5d-128">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
4.  <span data-ttu-id="daf5d-129">Se necessario, modificare le proprietà e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="daf5d-129">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="daf5d-130">Per visualizzare e modificare le proprietà del server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="daf5d-130">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="daf5d-131">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="daf5d-131">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="daf5d-132">Fare clic con il pulsante destro del mouse sulla cartella **Replica** e quindi scegliere **Proprietà server di pubblicazione**.</span><span class="sxs-lookup"><span data-stu-id="daf5d-132">Right-click the **Replication** folder, and then click **Publisher Properties**.</span></span>  
  
3.  <span data-ttu-id="daf5d-133">Visualizzare e modificare le proprietà nella finestra di dialogo \*\*Proprietà server di pubblicazione- \< Publisher > \*\* .</span><span class="sxs-lookup"><span data-stu-id="daf5d-133">View and modify properties in the **Publisher Properties - \< Publisher >** dialog box.</span></span>  
  
    -   <span data-ttu-id="daf5d-134">Un utente nel ruolo predefinito del server **sysadmin** può abilitare i database per la replica nella pagina **Database di pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="daf5d-134">A user in the **sysadmin** fixed server role can enable databases for replication on the **Publication Databases** page.</span></span> <span data-ttu-id="daf5d-135">L'abilitazione di un database non ne comporta la pubblicazione, ma piuttosto consente a un utente nel ruolo predefinito del database **db_owner** per il database in questione di creare una o più pubblicazioni nel database.</span><span class="sxs-lookup"><span data-stu-id="daf5d-135">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications in the database.</span></span>  
  
4.  <span data-ttu-id="daf5d-136">Se necessario, modificare le proprietà e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="daf5d-136">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="daf5d-137">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="daf5d-137">Using Transact-SQL</span></span>  
 <span data-ttu-id="daf5d-138">È possibile visualizzare le proprietà del server di pubblicazione e del database di distribuzione a livello di programmazione utilizzando le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="daf5d-138">Publisher and Distributor properties can be viewed programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-view-distributor-and-distribution-database-properties"></a><span data-ttu-id="daf5d-139">Per visualizzare le proprietà del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="daf5d-139">To view Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="daf5d-140">Eseguire [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) per restituire informazioni sul server di distribuzione, il database di distribuzione e la directory di lavoro.</span><span class="sxs-lookup"><span data-stu-id="daf5d-140">Execute [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) to return information about the Distributor, distribution database, and working directory.</span></span>  
  
2.  <span data-ttu-id="daf5d-141">Eseguire [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) per restituire le proprietà di un database di distribuzione specificato.</span><span class="sxs-lookup"><span data-stu-id="daf5d-141">Execute [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) to return properties of a specified distribution database.</span></span>  
  
#### <a name="to-change-distributor-and-distribution-database-properties"></a><span data-ttu-id="daf5d-142">Per modificare le proprietà del server di distribuzione e del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="daf5d-142">To change Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="daf5d-143">Nel server di distribuzione eseguire [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) per modificare le proprietà del server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-143">At the Distributor, execute [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) to modify Distributor properties.</span></span>  
  
2.  <span data-ttu-id="daf5d-144">Nel server di distribuzione eseguire [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) per modificare le proprietà del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-144">At the Distributor, execute [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) to modify distribution database properties.</span></span>  
  
3.  <span data-ttu-id="daf5d-145">Nel database di distribuzione eseguire [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) per modificare la password del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-145">At the Distributor, execute [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) to change the Distributor password.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="daf5d-146">Se possibile, richiedere agli utenti di immettere le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-146">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="daf5d-147">Se è necessario archiviare le credenziali in un file di script, proteggere tale file per impedire l'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="daf5d-147">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
4.  <span data-ttu-id="daf5d-148">Nel database di distribuzione eseguire [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) per modificare le proprietà di un server di pubblicazione utilizzando il database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-148">At the Distributor, execute [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) to change the properties of a Publisher using the Distributor.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="daf5d-149">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="daf5d-149">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="daf5d-150">Lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] di esempio riportato di seguito restituisce informazioni sul database di distribuzione e sul database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-150">The following example [!INCLUDE[tsql](../../includes/tsql-md.md)] script returns information about the Distributor and distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_helpdistributor](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributor)]  
  
 [!code-sql[HowTo#sp_helpdistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributiondb)]  
  
 <span data-ttu-id="daf5d-151">In questo esempio vengono modificati i periodi di memorizzazione per il server di distribuzione, la password utilizzata per la connessione al server di distribuzione e l'intervallo con cui il server di distribuzione verifica lo stato di diversi agenti di replica, noto anche come intervallo di heartbeat.</span><span class="sxs-lookup"><span data-stu-id="daf5d-151">This example changes retention periods for the Distributor, the password used when connecting to the Distributor, and the interval at which the Distributor checks the status of various replication agents (also known as the heartbeat interval).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="daf5d-152">Se possibile, richiedere agli utenti di immettere le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-152">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="daf5d-153">Se è necessario archiviare le credenziali in un file di script, proteggere tale file per impedire l'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="daf5d-153">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_changedistributor_property](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_property)]  
  
 [!code-sql[HowTo#sp_changedistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributiondb)]  
  
 [!code-sql[HowTo#sp_changedistributor_password](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_password)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="daf5d-154">Utilizzo di RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="daf5d-154">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="daf5d-155">Per visualizzare e modificare le proprietà del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="daf5d-155">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="daf5d-156">Creare una connessione al server di distribuzione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="daf5d-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="daf5d-157">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="daf5d-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="daf5d-158">Passare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> indicato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="daf5d-158">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="daf5d-159">(Facoltativo) Controllare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> per verificare che il server attualmente connesso sia un server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-159">(Optional) Check the <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> property to verify that the currently connected server is a Distributor.</span></span>  
  
4.  <span data-ttu-id="daf5d-160">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> per ottenere le proprietà dal server.</span><span class="sxs-lookup"><span data-stu-id="daf5d-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties from the server.</span></span>  
  
5.  <span data-ttu-id="daf5d-161">(Facoltativo) Per modificare le proprietà, specificare un nuovo valore per una o più proprietà del server di distribuzione che è possibile impostare sull'oggetto <xref:Microsoft.SqlServer.Replication.ReplicationServer> .</span><span class="sxs-lookup"><span data-stu-id="daf5d-161">(Optional) To change properties, set a new value for one or more of the Distributor properties that can be set on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object.</span></span>  
  
6.  <span data-ttu-id="daf5d-162">(Facoltativo) Se la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> sull'oggetto <xref:Microsoft.SqlServer.Replication.ReplicationServer> è impostata su `true`, chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> per eseguire il commit delle modifiche nel server.</span><span class="sxs-lookup"><span data-stu-id="daf5d-162">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-distribution-database-properties"></a><span data-ttu-id="daf5d-163">Per visualizzare e modificare le proprietà del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="daf5d-163">To view and modify distribution database properties</span></span>  
  
1.  <span data-ttu-id="daf5d-164">Creare una connessione al server di distribuzione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="daf5d-164">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="daf5d-165">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.DistributionDatabase>.</span><span class="sxs-lookup"><span data-stu-id="daf5d-165">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> class.</span></span> <span data-ttu-id="daf5d-166">Specificare la proprietà relativa al nome e passare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> indicato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="daf5d-166">Specify the name property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="daf5d-167">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per ottenere le proprietà dal server.</span><span class="sxs-lookup"><span data-stu-id="daf5d-167">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties from the server.</span></span> <span data-ttu-id="daf5d-168">Se il metodo restituisce `false`, il database con il nome specificato non esiste nel server.</span><span class="sxs-lookup"><span data-stu-id="daf5d-168">If this method returns `false`, the database with the specified name does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="daf5d-169">(Facoltativo) Per modificare le proprietà, specificare un nuovo valore per una delle proprietà dell'oggetto <xref:Microsoft.SqlServer.Replication.DistributionDatabase> che è possibile impostare.</span><span class="sxs-lookup"><span data-stu-id="daf5d-169">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> properties that can be set.</span></span>  
  
5.  <span data-ttu-id="daf5d-170">(Facoltativo) Se la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> sull'oggetto <xref:Microsoft.SqlServer.Replication.DistributionDatabase> è impostata su `true`, chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> per eseguire il commit delle modifiche nel server.</span><span class="sxs-lookup"><span data-stu-id="daf5d-170">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="daf5d-171">Per visualizzare e modificare le proprietà del server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="daf5d-171">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="daf5d-172">Creare una connessione al server di pubblicazione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="daf5d-172">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="daf5d-173">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="daf5d-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="daf5d-174">Specificare la proprietà <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> e passare l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> indicato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="daf5d-174">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="daf5d-175">(Facoltativo) Per modificare le proprietà, specificare un nuovo valore per una delle proprietà dell'oggetto <xref:Microsoft.SqlServer.Replication.DistributionPublisher> che è possibile impostare.</span><span class="sxs-lookup"><span data-stu-id="daf5d-175">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> properties that can be set.</span></span>  
  
4.  <span data-ttu-id="daf5d-176">(Facoltativo) Se la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> sull'oggetto <xref:Microsoft.SqlServer.Replication.DistributionPublisher> è impostata su `true`, chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> per eseguire il commit delle modifiche nel server.</span><span class="sxs-lookup"><span data-stu-id="daf5d-176">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-change-the-password-for-the-administrative-connection-from-the-publisher-to-the-distributor"></a><span data-ttu-id="daf5d-177">Per modificare la password per la connessione amministrativa dal server di pubblicazione al database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="daf5d-177">To change the password for the administrative connection from the Publisher to the Distributor</span></span>  
  
1.  <span data-ttu-id="daf5d-178">Creare una connessione al server di distribuzione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="daf5d-178">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="daf5d-179">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="daf5d-179">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
3.  <span data-ttu-id="daf5d-180">Impostare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> sulla connessione creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="daf5d-180">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="daf5d-181">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> per recuperare le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="daf5d-181">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
5.  <span data-ttu-id="daf5d-182">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="daf5d-182">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="daf5d-183">Passare il nuovo valore della password per il parametro *password* .</span><span class="sxs-lookup"><span data-stu-id="daf5d-183">Pass the new password value for the *password* parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="daf5d-184">Se possibile, richiedere agli utenti di immettere le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-184">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="daf5d-185">Se è necessario archiviare le credenziali, utilizzare i [servizi di crittografia](https://go.microsoft.com/fwlink/?LinkId=34733) offerti da [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="daf5d-185">If you must store credentials, use the [cryptographic services](https://go.microsoft.com/fwlink/?LinkId=34733) provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span></span>  
  
6.  <span data-ttu-id="daf5d-186">(Facoltativo) Eseguire i passaggi seguenti per modificare la password in ogni server di pubblicazione remoto che utilizza questo server di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="daf5d-186">(Optional) Perform the following steps to change the password at each remote Publisher that uses this Distributor:</span></span>  
  
    1.  <span data-ttu-id="daf5d-187">Creare una connessione al server di pubblicazione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="daf5d-187">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
    2.  <span data-ttu-id="daf5d-188">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="daf5d-188">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
    3.  <span data-ttu-id="daf5d-189">Impostare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> sulla connessione creata nel passaggio 6a.</span><span class="sxs-lookup"><span data-stu-id="daf5d-189">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 6a.</span></span>  
  
    4.  <span data-ttu-id="daf5d-190">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> per recuperare le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="daf5d-190">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
    5.  <span data-ttu-id="daf5d-191">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="daf5d-191">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="daf5d-192">Passare il nuovo valore della password indicato nel passaggio 5 per il parametro *password* .</span><span class="sxs-lookup"><span data-stu-id="daf5d-192">Pass the new password value from Step 5 for the *password* parameter.</span></span>  
  
###  <a name="example-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="daf5d-193">Esempio (RMO)</span><span class="sxs-lookup"><span data-stu-id="daf5d-193">Example (RMO)</span></span>  
 <span data-ttu-id="daf5d-194">In questo esempio viene illustrato come modificare le proprietà del database di distribuzione e del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-194">This example shows how to change Distribution and distribution database properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="daf5d-195">Per evitare di archiviare le credenziali del codice, la nuova password del server di distribuzione viene specificata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="daf5d-195">To avoid storing credentials in the code, the new Distributor password is supplied at runtime.</span></span>  
  
 [!code-csharp[HowTo#rmo_ChangeDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_changedistpub)]  
  
 [!code-vb[HowTo#rmo_vb_ChangeDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_changedistpub)]  
  
## <a name="see-also"></a><span data-ttu-id="daf5d-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daf5d-196">See Also</span></span>  
 <span data-ttu-id="daf5d-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="daf5d-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="daf5d-198">[Disabilitare la pubblicazione e la distribuzione](disable-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="daf5d-198">[Disable Publishing and Distribution](disable-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="daf5d-199">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="daf5d-199">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="daf5d-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="daf5d-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="daf5d-201">[Script di informazioni su database di distribuzione e server di pubblicazione](administration/distributor-and-publisher-information-script.md) </span><span class="sxs-lookup"><span data-stu-id="daf5d-201">[Distributor and Publisher Information Script](administration/distributor-and-publisher-information-script.md) </span></span>  
 <span data-ttu-id="daf5d-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="daf5d-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="daf5d-203">Visualizzazione delle informazioni ed esecuzione di attività tramite Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="daf5d-203">View Information and Perform Tasks using Replication Monitor</span></span>](monitor/view-information-and-perform-tasks-replication-monitor.md)  
  
  
