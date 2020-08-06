---
title: Configurare la replica per i gruppi di disponibilità AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 4e001426-5ae0-4876-85ef-088d6e3fb61c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 916458d2d6b8fbba81940257ee85ffe014d1f12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713511"
---
# <a name="configure-replication-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="033b6-102">Configurare la replica per i gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="033b6-102">Configure Replication for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="033b6-103">La configurazione della replica in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e dei gruppi di disponibilità AlwaysOn richiede sette passaggi.</span><span class="sxs-lookup"><span data-stu-id="033b6-103">Configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replication and AlwaysOn availability groups involves seven steps.</span></span> <span data-ttu-id="033b6-104">Ogni passaggio è descritto in dettaglio nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="033b6-104">Each step is described in more detail in the following sections.</span></span>  

##  <a name="1-configure-the-database-publications-and-subscriptions"></a><a name="step1"></a> <span data-ttu-id="033b6-105">1. Configurare le pubblicazioni e le sottoscrizioni del database</span><span class="sxs-lookup"><span data-stu-id="033b6-105">1. Configure the Database Publications and Subscriptions</span></span>  

### <a name="configure-the-distributor"></a><span data-ttu-id="033b6-106">Configurare il server di distribuzione</span><span class="sxs-lookup"><span data-stu-id="033b6-106">Configure the distributor</span></span>
  
 <span data-ttu-id="033b6-107">Il server di distribuzione non deve essere un host per una qualsiasi delle repliche correnti (o previste) del gruppo di disponibilità di cui il database di pubblicazione è (o diventerà) un membro.</span><span class="sxs-lookup"><span data-stu-id="033b6-107">The distributor should not be a host for any of the current (or intended) replicas of the availability group that the publishing database is (or will become) a member of.</span></span>  
  
1.  <span data-ttu-id="033b6-108">Configurare la distribuzione sul server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="033b6-108">Configure distribution at the distributor.</span></span> <span data-ttu-id="033b6-109">Se per la configurazione vengono utilizzate stored procedure, eseguire `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="033b6-109">If stored procedures are being used for configuration, run `sp_adddistributor`.</span></span> <span data-ttu-id="033b6-110">Utilizzare il *@password* parametro per identificare la password che verrà utilizzata quando un server di pubblicazione remoto si connette al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="033b6-110">Use the *@password* parameter to identify the password that will be used when a remote publisher connects to the distributor.</span></span> <span data-ttu-id="033b6-111">La password sarà necessaria anche per ogni server di pubblicazione remoto quando viene configurato il server di distribuzione remoto.</span><span class="sxs-lookup"><span data-stu-id="033b6-111">The password will also be needed at each remote publisher when the remote distributor is set up.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = '**Strong password for distributor**';  
    ```  
  
2.  <span data-ttu-id="033b6-112">Creare il database di distribuzione nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="033b6-112">Create the distribution database at the distributor.</span></span> <span data-ttu-id="033b6-113">Se per la configurazione vengono utilizzate stored procedure, eseguire `sp_adddistributiondb`.</span><span class="sxs-lookup"><span data-stu-id="033b6-113">If stored procedures are being used for configuration, run `sp_adddistributiondb`.</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sys.sp_adddistributiondb  
        @database = 'distribution',  
        @security_mode = 1;  
    ```  
  
3.  <span data-ttu-id="033b6-114">Configurare il server di pubblicazione remoto.</span><span class="sxs-lookup"><span data-stu-id="033b6-114">Configure the remote publisher.</span></span> <span data-ttu-id="033b6-115">Se per la configurazione del server di distribuzione vengono utilizzate stored procedure, eseguire `sp_adddistpublisher`.</span><span class="sxs-lookup"><span data-stu-id="033b6-115">If stored procedures are being used to configure the distributor, run `sp_adddistpublisher`.</span></span> <span data-ttu-id="033b6-116">Il *@security_mode* parametro viene utilizzato per determinare il modo in cui la convalida del server di pubblicazione stored procedure eseguita dagli agenti di replica, si connette al database primario corrente.</span><span class="sxs-lookup"><span data-stu-id="033b6-116">The *@security_mode* parameter is used to determine how the publisher validation stored procedure that is run from the replication agents, connects to the current primary.</span></span> <span data-ttu-id="033b6-117">Se impostato su 1, per connettersi alla replica primaria corrente viene utilizzata l'Autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="033b6-117">If set to 1 Windows authentication is used to connect to the current primary.</span></span> <span data-ttu-id="033b6-118">Se impostato su 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] viene utilizzata l'autenticazione con i *@login* valori e specificati *@password* .</span><span class="sxs-lookup"><span data-stu-id="033b6-118">If set to 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authentication is used with the specified *@login* and *@password* values.</span></span> <span data-ttu-id="033b6-119">L'account di accesso e la password specificati devono essere validi per ogni replica secondaria per consentire alla stored procedure di convalida di connettersi a tale replica.</span><span class="sxs-lookup"><span data-stu-id="033b6-119">The login and password specified must be valid at each secondary replica for the validation stored procedure to successfully connect to that replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="033b6-120">Se gli eventuali agenti di replica modificati vengono eseguiti in un computer diverso dal server di distribuzione, l'utilizzo dell'Autenticazione di Windows per la connessione alla replica primaria richiederà l'autenticazione Kerberos per consentire la configurazione per la comunicazione tra i computer host della replica.</span><span class="sxs-lookup"><span data-stu-id="033b6-120">If any modified replication agents run on a computer other than the distributor, use of Windows authentication for the connection to the primary will require Kerberos authentication to be configured for the communication between the replica host computers.</span></span> <span data-ttu-id="033b6-121">L'utilizzo di un account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per la connessione alla replica primaria corrente non richiede l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="033b6-121">Use of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login for the connection to the current primary will not require Kerberos authentication.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistpublisher  
        @publisher = 'AGPrimaryReplicaHost',  
        @distribution_db = 'distribution',  
        @working_directory = '\\MyReplShare\WorkingDir',  
        @login = 'MyPubLogin',  
        @password = '**Strong password for publisher**';  
    ```  
  
 <span data-ttu-id="033b6-122">Per altre informazioni, vedere [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="033b6-122">For more information, see [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span></span>  
  
### <a name="configure-the-publisher-at-the-original-publisher"></a><span data-ttu-id="033b6-123">Configurare il server di pubblicazione nel server di pubblicazione originale</span><span class="sxs-lookup"><span data-stu-id="033b6-123">Configure the publisher at the original publisher</span></span>
  
1.  <span data-ttu-id="033b6-124">Configurare la distribuzione remota.</span><span class="sxs-lookup"><span data-stu-id="033b6-124">Configure remote distribution.</span></span> <span data-ttu-id="033b6-125">Se per la configurazione del server di pubblicazione vengono utilizzate stored procedure, eseguire `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="033b6-125">If stored procedures are being used to configure the publisher, run `sp_adddistributor`.</span></span> <span data-ttu-id="033b6-126">Specificare lo stesso valore per *@password* utilizzato quando `sp_adddistrbutor` è stato eseguito nel server di distribuzione per configurare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="033b6-126">Specify the same value for *@password* as that used when `sp_adddistrbutor` was run at the distributor to set up distribution.</span></span>  
  
    ```sql
    exec sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = 'MyDistPass'  
    ```  
  
2.  <span data-ttu-id="033b6-127">Abilitare il database per la replica.</span><span class="sxs-lookup"><span data-stu-id="033b6-127">Enable the database for replication.</span></span> <span data-ttu-id="033b6-128">Se per la configurazione del server di pubblicazione vengono utilizzate stored procedure, eseguire `sp_replicationdboption`.</span><span class="sxs-lookup"><span data-stu-id="033b6-128">If stored procedures are being used to configure the publisher, run `sp_replicationdboption`.</span></span> <span data-ttu-id="033b6-129">Se è necessario configurare la replica transazionale e di tipo merge per il database, è necessario abilitarne ognuna.</span><span class="sxs-lookup"><span data-stu-id="033b6-129">If both transactional and merge replication are to be configured for the database, each must be enabled.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'true';  
  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'merge publish',  
        @value = 'true';  
    ```  
  
3.  <span data-ttu-id="033b6-130">Creare la pubblicazione di replica, articoli e sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="033b6-130">Create the replication publication, articles, and subscriptions.</span></span> <span data-ttu-id="033b6-131">Per ulteriori informazioni sulla configurazione della replica, vedere Pubblicazione di dati e oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="033b6-131">For more information about how to configure replication, see Publishing Data and Database objects.</span></span>  
  
##  <a name="2-configure-the-alwayson-availability-group"></a><a name="step2"></a><span data-ttu-id="033b6-132">2. configurare il gruppo di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="033b6-132">2. Configure the AlwaysOn Availability Group</span></span>  
 <span data-ttu-id="033b6-133">Nella replica primaria prevista creare il gruppo di disponibilità con il database pubblicato (o da pubblicare) come database membro.</span><span class="sxs-lookup"><span data-stu-id="033b6-133">At the intended primary, create the availability group with the published (or to be published) database as a member database.</span></span> <span data-ttu-id="033b6-134">In caso di utilizzo della Creazione guidata Gruppo di disponibilità, è possibile consentire alla procedura guidata di sincronizzare inizialmente i database di tipo replica secondaria o eseguire manualmente l'inizializzazione mediante backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="033b6-134">If using the Availability Group Wizard, you can either allow the wizard to initially synchronize the secondary replica databases or you can perform the initialization manually by using backup and restore.</span></span>  
  
 <span data-ttu-id="033b6-135">Creare un listener DNS per il gruppo di disponibilità che sarà utilizzato dagli agenti di replica per connettersi alla replica primaria corrente.</span><span class="sxs-lookup"><span data-stu-id="033b6-135">Create a DNS listener for the availability group that will be used by the replication agents to connect to the current primary.</span></span> <span data-ttu-id="033b6-136">Il nome del listener specificato sarà utilizzato come destinazione di reindirizzamento per la coppia server di pubblicazione originale/database pubblicato.</span><span class="sxs-lookup"><span data-stu-id="033b6-136">The listener name that is specified will be used as the target of redirection for the original publisher/published database pair.</span></span> <span data-ttu-id="033b6-137">Ad esempio, se si utilizza DDL per configurare il gruppo di disponibilità, è possibile utilizzare l'esempio di codice seguente per specificare un listener per un gruppo di disponibilità esistente denominato `MyAG`:</span><span class="sxs-lookup"><span data-stu-id="033b6-137">For example, if you are using DDL to configure the availability group, the following code example can be used to specify an availability group listener for an existing availability group named `MyAG`:</span></span>  
  
```sql
ALTER AVAILABILITY GROUP 'MyAG'   
    ADD LISTENER 'MyAGListenerName' (WITH IP (('10.120.19.155', '255.255.254.0')));  
```  
  
 <span data-ttu-id="033b6-138">Per altre informazioni, vedere [Creazione e configurazione di gruppi di disponibilità &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="033b6-138">For more information, see [Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span></span>  
  
##  <a name="3-insure-that-all-of-the-secondary-replica-hosts-are-configured-for-replication"></a><a name="step3"></a><span data-ttu-id="033b6-139">3. Assicurarsi che tutti gli host della replica secondaria siano configurati per la replica</span><span class="sxs-lookup"><span data-stu-id="033b6-139">3. Insure that all of the Secondary Replica Hosts are Configured for Replication</span></span>  
 <span data-ttu-id="033b6-140">In ogni host della replica secondaria verificare che [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sia stato configurato per supportare la replica.</span><span class="sxs-lookup"><span data-stu-id="033b6-140">At each secondary replica host, verify that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been configured to support replication.</span></span> <span data-ttu-id="033b6-141">È possibile eseguire la query seguente in ogni host della replica secondaria per determinare se la replica è installata:</span><span class="sxs-lookup"><span data-stu-id="033b6-141">The following query can be run at each secondary replica host to determine whether replication is installed:</span></span>  
  
```sql
USE master;  
GO  
DECLARE @installed int;  
EXEC @installed = sys.sp_MS_replication_installed;  
SELECT @installed;  
```  
  
 <span data-ttu-id="033b6-142">Se *@installed* è 0, è necessario aggiungere la replica all' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installazione.</span><span class="sxs-lookup"><span data-stu-id="033b6-142">If *@installed* is 0, replication must be added to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span>  
  
##  <a name="4-configure-the-secondary-replica-hosts-as-replication-publishers"></a><a name="step4"></a> <span data-ttu-id="033b6-143">4. Configurare gli host della replica secondaria come server di pubblicazione di replica</span><span class="sxs-lookup"><span data-stu-id="033b6-143">4. Configure the Secondary Replica Hosts as Replication Publishers</span></span>  
 <span data-ttu-id="033b6-144">Una replica secondaria non può essere utilizzata come server di pubblicazione o di ripubblicazione della replica, ma è necessario configurare la replica in modo che dopo un failover possa essere utilizzata la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="033b6-144">A secondary replica cannot act as a replication publisher or republisher but replication must be configured so that the secondary can take over after a failover.</span></span> <span data-ttu-id="033b6-145">Nel server di distribuzione configurare la distribuzione per ogni host della replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="033b6-145">At the distributor, configure distribution for each secondary replica host.</span></span> <span data-ttu-id="033b6-146">Specificare lo stesso database di distribuzione e la stessa directory di lavoro specificati quando il server di pubblicazione originale è aggiunto al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="033b6-146">Specify the same distribution database and working directory as was specified when the original publisher was added to the distributor.</span></span> <span data-ttu-id="033b6-147">Se si utilizzano stored procedure per configurare la distribuzione, utilizzare `sp_adddistpublisher` per associare i server di pubblicazione remoti al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="033b6-147">If you are using stored procedures to configure distribution, use `sp_adddistpublisher` to associate the remote publishers with the distributor.</span></span> <span data-ttu-id="033b6-148">Se *@login* e *@password* sono stati utilizzati per il server di pubblicazione originale, specificare gli stessi valori per ognuno quando si aggiungono gli host della replica secondaria come server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="033b6-148">If *@login* and *@password* were used for the original publisher, specify the same values for each when you add the secondary replica hosts as publishers.</span></span>  
  
```sql
EXEC sys.sp_adddistpublisher  
    @publisher = 'AGSecondaryReplicaHost',  
    @distribution_db = 'distribution',  
    @working_directory = '\\MyReplShare\WorkingDir',  
    @login = 'MyPubLogin',  
    @password = '**Strong password for publisher**';  
```  
  
 <span data-ttu-id="033b6-149">Configurare la distribuzione per ogni host della replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="033b6-149">At each secondary replica host, configure distribution.</span></span> <span data-ttu-id="033b6-150">Identificare il server di distribuzione del server di pubblicazione originale come server di distribuzione remoto.</span><span class="sxs-lookup"><span data-stu-id="033b6-150">Identify the distributor of the original publisher as the remote distributor.</span></span> <span data-ttu-id="033b6-151">Utilizzare la password specificata quando `sp_adddistributor` è stato eseguito inizialmente nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="033b6-151">Use the same password as that used when `sp_adddistributor` was run originally at the distributor.</span></span> <span data-ttu-id="033b6-152">Se per la configurazione della distribuzione vengono usate stored procedure, il *@password* parametro di `sp_adddistributor` viene usato per specificare la password.</span><span class="sxs-lookup"><span data-stu-id="033b6-152">If stored procedures are being used to configure distribution, the *@password* parameter of `sp_adddistributor` is used to specify the password.</span></span>  
  
```sql
EXEC sp_adddistributor   
    @distributor = 'MyDistributor',  
    @password = '**Strong password for distributor**';  
```  
  
 <span data-ttu-id="033b6-153">In ogni host della replica secondaria verificare che i Sottoscrittori push delle pubblicazioni del database vengano visualizzati come server collegati.</span><span class="sxs-lookup"><span data-stu-id="033b6-153">At each secondary replica host, make sure that the push subscribers of the database publications appear as linked servers.</span></span> <span data-ttu-id="033b6-154">Se per la configurazione dei server di pubblicazione remoti vengono utilizzate stored procedure, eseguire `sp_addlinkedserver` per aggiungere i Sottoscrittori (se non già presenti) come server collegati ai server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="033b6-154">If stored procedures are being used to configure the remote publishers, use `sp_addlinkedserver` to add the subscribers (if not already present) as linked servers to the publishers.</span></span>  
  
```sql
EXEC sys.sp_addlinkedserver   
    @server = 'MySubscriber';  
```  
  
##  <a name="5-redirect-the-original-publisher-to-the-ag-listener-name"></a><a name="step5"></a> <span data-ttu-id="033b6-155">5. Reindirizzare il server di pubblicazione originale al nome del listener gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="033b6-155">5. Redirect the Original Publisher to the AG Listener Name</span></span>  
 <span data-ttu-id="033b6-156">Nel database di distribuzione sul server di distribuzione eseguire la stored procedure `sp_redirect_publisher` per associare il server di pubblicazione originale e il database pubblicato al nome del listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="033b6-156">At the distributor, in the distribution database, run the stored procedure `sp_redirect_publisher` to associate the original publisher and the published database with the availability group listener name of the availability group.</span></span>  
  
```sql
USE distribution;  
GO  
EXEC sys.sp_redirect_publisher   
@original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = 'MyAGListenerName';  
```  
  
##  <a name="6-run-the-replication-validation-stored-procedure-to-verify-the-configuration"></a><a name="step6"></a> <span data-ttu-id="033b6-157">6. Eseguire la stored procedure di convalida della replica per verificare la configurazione</span><span class="sxs-lookup"><span data-stu-id="033b6-157">6. Run the Replication Validation Stored Procedure to Verify the Configuration</span></span>  
 <span data-ttu-id="033b6-158">Nel database di distribuzione del server di distribuzione eseguire la stored procedure `sp_validate_replica_hosts_as_publishers` per verificare che tutti gli host della replica siano configurati come server di pubblicazione per il database pubblicato.</span><span class="sxs-lookup"><span data-stu-id="033b6-158">At the distributor, in the distribution database, run the stored procedure `sp_validate_replica_hosts_as_publishers` to verify that all replica hosts are now configured to serve as publishers for the published database.</span></span>  
  
```sql
USE distribution;  
GO  
DECLARE @redirected_publisher sysname;  
EXEC sys.sp_validate_replica_hosts_as_publishers  
    @original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = @redirected_publisher output;  
```  
  
 <span data-ttu-id="033b6-159">La stored procedure `sp_validate_replica_hosts_as_publishers` deve essere eseguita da un account di accesso con autorizzazione sufficiente in ogni host di replica del gruppo di disponibilità per richiedere informazioni sul gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="033b6-159">The stored procedure `sp_validate_replica_hosts_as_publishers` should be run from a login with sufficient authorization at each availability group replica host to query for information about the availability group.</span></span> <span data-ttu-id="033b6-160">A differenza di `sp_validate_redirected_publisher` , USA le credenziali del chiamante e non usa l'account di accesso mantenuto in msdb. dbo. MSdistpublishers per connettersi alle repliche del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="033b6-160">Unlike `sp_validate_redirected_publisher`, it uses the credentials of the caller and does not use the login retained in msdb.dbo.MSdistpublishers to connect to the availability group replicas.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="033b6-161">`sp_validate_replica_hosts_as_publishers` non riuscirà e verrà visualizzato il seguente errore durante la convalida degli host della replica secondaria che non consentono l'accesso in lettura o richiedono che venga specificata la finalità di lettura.</span><span class="sxs-lookup"><span data-stu-id="033b6-161">`sp_validate_replica_hosts_as_publishers` will fail with the following error when validating secondary replica hosts that do not allow read access, or require read intent to be specified.</span></span>  
>   
>  <span data-ttu-id="033b6-162">Msg 21899, Livello 11, Stato 1, Procedura `sp_hadr_verify_subscribers_at_publisher`, Riga 109</span><span class="sxs-lookup"><span data-stu-id="033b6-162">Msg 21899, Level 11, State 1, Procedure `sp_hadr_verify_subscribers_at_publisher`, Line 109</span></span>  
>   
>  <span data-ttu-id="033b6-163">Impossibile eseguire la query sul server di pubblicazione reindirizzato "MyReplicaHostName" per determinare la presenza di voci sysserver per i sottoscrittori del server di pubblicazione originale "MyOriginalPublisher", errore "976", messaggio di errore "Errore 976, Livello 14, Stato 1". Messaggio: Il database di destinazione, "MyPublishedDB", fa parte di un gruppo di disponibilità e non è attualmente accessibile per le query.</span><span class="sxs-lookup"><span data-stu-id="033b6-163">The query at the redirected publisher 'MyReplicaHostName' to determine whether there were sysserver entries for the subscribers of the original publisher 'MyOriginalPublisher' failed with error '976', error message 'Error 976, Level 14, State 1, Message: The target database, 'MyPublishedDB', is participating in an availability group and is currently not accessible for queries.</span></span> <span data-ttu-id="033b6-164">Lo spostamento dei dati è sospeso o la replica di disponibilità non è abilitata per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="033b6-164">Either data movement is suspended or the availability replica is not enabled for read access.</span></span> <span data-ttu-id="033b6-165">Per consentire l'accesso in sola lettura a questo e ad altri database nel gruppo di disponibilità, abilitare l'accesso in lettura a una o più repliche di disponibilità secondarie nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="033b6-165">To allow read-only access to this and other databases in the availability group, enable read access to one or more secondary availability replicas in the group.</span></span>  <span data-ttu-id="033b6-166">Per ulteriori informazioni, vedere l'istruzione `ALTER AVAILABILITY GROUP` nella documentazione online di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="033b6-166">For more information, see the `ALTER AVAILABILITY GROUP` statement in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.'.</span></span>  
>   
>  <span data-ttu-id="033b6-167">Sono stati rilevati uno o più errori di convalida del server di pubblicazione per l'host della replica 'MyReplicaHostName'.</span><span class="sxs-lookup"><span data-stu-id="033b6-167">One or more publisher validation errors were encountered for replica host 'MyReplicaHostName'.</span></span>  
  
 <span data-ttu-id="033b6-168">Si tratta di un comportamento previsto.</span><span class="sxs-lookup"><span data-stu-id="033b6-168">This is expected behavior.</span></span> <span data-ttu-id="033b6-169">È necessario verificare la presenza delle voci del Sottoscrittore in questi host della replica secondaria eseguendo una query per le voci sysserver direttamente sull'host.</span><span class="sxs-lookup"><span data-stu-id="033b6-169">You must verify the presence of the subscriber server entries at these secondary replica hosts by querying for the sysserver entries directly at the host.</span></span>  
  
##  <a name="7-add-the-original-publisher-to-replication-monitor"></a><a name="step7"></a> <span data-ttu-id="033b6-170">7. Aggiungere il server di pubblicazione originale a Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="033b6-170">7. Add the Original Publisher to Replication Monitor</span></span>  
 <span data-ttu-id="033b6-171">In ogni replica del gruppo di disponibilità aggiungere il server di pubblicazione originale a Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="033b6-171">At each availability group replica, add the original publisher to Replication Monitor.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="033b6-172">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="033b6-172">Related Tasks</span></span>  
 <span data-ttu-id="033b6-173">**Replica**</span><span class="sxs-lookup"><span data-stu-id="033b6-173">**Replication**</span></span>  
  
-   [<span data-ttu-id="033b6-174">Gestione di un database di pubblicazione AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-174">Maintaining an AlwaysOn Publication Database &#40;SQL Server&#41;</span></span>](maintaining-an-always-on-publication-database-sql-server.md)  
  
-   [<span data-ttu-id="033b6-175">Replica, Rilevamento modifiche, Change Data Capture e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-175">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="033b6-176">Domande frequenti sull'amministrazione della replica</span><span class="sxs-lookup"><span data-stu-id="033b6-176">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
 <span data-ttu-id="033b6-177">**Per creare e configurare un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="033b6-177">**To create and configure an availability group**</span></span>  
  
-   [<span data-ttu-id="033b6-178">Usare la Creazione guidata Gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-178">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="033b6-179">Utilizzare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-179">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="033b6-180">Creare un gruppo di disponibilità &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-180">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="033b6-181">Creare un gruppo di disponibilità &#40;PowerShell SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-181">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="033b6-182">Specifica dell'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-182">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="033b6-183">Creazione di un endpoint del mirroring del database per Gruppi di disponibilità AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-183">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="033b6-184">Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-184">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="033b6-185">Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-185">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="033b6-186">Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-186">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="033b6-187">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="033b6-187">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="033b6-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="033b6-188">See Also</span></span>  
 <span data-ttu-id="033b6-189">[Prerequisiti, restrizioni e consigli per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="033b6-189">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="033b6-190">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="033b6-190">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="033b6-191">[Gruppi di disponibilità AlwaysOn: interoperabilità (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="033b6-191">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="033b6-192">Replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="033b6-192">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
