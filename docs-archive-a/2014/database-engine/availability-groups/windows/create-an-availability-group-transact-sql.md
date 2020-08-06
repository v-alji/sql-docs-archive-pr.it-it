---
title: Creare un gruppo di disponibilità (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: 8b0a6301-8b79-4415-b608-b40876f30066
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57a494af168a8f5572bafe93f8fb47b22a954a19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727132"
---
# <a name="create-an-availability-group-transact-sql"></a><span data-ttu-id="36110-102">Creare un gruppo di disponibilità (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="36110-102">Create an Availability Group (Transact-SQL)</span></span>
  <span data-ttu-id="36110-103">In questo argomento viene descritto come utilizzare [!INCLUDE[tsql](../../../includes/tsql-md.md)] per creare e configurare un gruppo di disponibilità su istanze di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] nelle quali è abilitata la funzionalità [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36110-103">This topic describes how to use [!INCLUDE[tsql](../../../includes/tsql-md.md)] to create and configure an availability group on instances of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] on which the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature is enabled.</span></span> <span data-ttu-id="36110-104">Tramite un *gruppo di disponibilità* vengono definiti un set di database utente di cui verrà eseguito il failover come unità singola e un set di partner di failover, noti come *repliche di disponibilità*, che supportano il failover.</span><span class="sxs-lookup"><span data-stu-id="36110-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, that support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36110-105">Per un'introduzione ai gruppi di disponibilità, vedere [Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="36110-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="36110-106">In alternativa all'utilizzo di [!INCLUDE[tsql](../../../includes/tsql-md.md)], è possibile utilizzare la procedura guidata Crea gruppo di disponibilità o i cmdlet di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36110-106">As an alternative to using [!INCLUDE[tsql](../../../includes/tsql-md.md)], you can use the Create Availability Group wizard or [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell cmdlets.</span></span> <span data-ttu-id="36110-107">Per altre informazioni, vedere [Usare la Creazione guidata Gruppo di disponibilità &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Usare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md), o [Creare un gruppo di disponibilità &#40; SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="36110-107">For more information, see [Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md), or [Create an Availability Group &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="36110-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="36110-108">Before You Begin</span></span>  
 <span data-ttu-id="36110-109">Prima di iniziare a creare il primo gruppo di disponibilità, è consigliabile leggere questa sezione.</span><span class="sxs-lookup"><span data-stu-id="36110-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a><span data-ttu-id="36110-110">Prerequisiti, restrizioni e raccomandazioni</span><span class="sxs-lookup"><span data-stu-id="36110-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="36110-111">Prima di creare un gruppo di disponibilità, verificare che le istanze di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che ospitano repliche di disponibilità si trovino in un nodo del Clustering di failover di Windows Server (Windows Server Failover Clustering, WSFC) diverso all'interno dello stesso cluster di failover WSFC.</span><span class="sxs-lookup"><span data-stu-id="36110-111">Before creating an availability group, verify that the instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that host availability replicas reside on different Windows Server Failover Clustering (WSFC) node within the same WSFC failover cluster.</span></span> <span data-ttu-id="36110-112">Inoltre, verificare che ciascuna delle istanze del server soddisfi tutti gli altri prerequisiti [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36110-112">Also, verify that each of the server instance meets all other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites.</span></span> <span data-ttu-id="36110-113">Per altre informazioni è consigliabile leggere [Prerequisiti, restrizioni e consigli per i gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="36110-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="36110-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="36110-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="36110-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="36110-115">Permissions</span></span>  
 <span data-ttu-id="36110-116">Sono necessarie l'appartenenza al ruolo predefinito del server **sysadmin** e l'autorizzazione server CREATE AVAILABILITY GROUP oppure l'autorizzazione ALTER ANY AVAILABILITY GROUP o CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="36110-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-transact-sql-statements"></a><a name="SummaryTsqlStatements"></a> <span data-ttu-id="36110-117">Riepilogo delle attività e istruzioni Transact-SQL corrispondenti</span><span class="sxs-lookup"><span data-stu-id="36110-117">Summary of Tasks and Corresponding Transact-SQL Statements</span></span>  
 <span data-ttu-id="36110-118">Nella tabella seguente sono elencate le attività di base necessarie per la creazione e la configurazione di un gruppo di disponibilità e vengono indicate le istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] da utilizzare per queste attività.</span><span class="sxs-lookup"><span data-stu-id="36110-118">The following table lists the basic tasks involved in creating and configuring an availability group and indicates which [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements to use for these tasks.</span></span> <span data-ttu-id="36110-119">È necessario eseguire le attività [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] nell'ordine con cui sono elencate nella tabella.</span><span class="sxs-lookup"><span data-stu-id="36110-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="36110-120">Attività</span><span class="sxs-lookup"><span data-stu-id="36110-120">Task</span></span>|<span data-ttu-id="36110-121">Istruzione/i Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="36110-121">Transact-SQL Statement(s)</span></span>|<span data-ttu-id="36110-122">Posizione in cui eseguire l'attività**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="36110-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|----------------------------------|-------------------------------------------|  
|<span data-ttu-id="36110-123">Creare un endpoint del mirroring del database (una volta per ogni istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="36110-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|<span data-ttu-id="36110-124">[Crea](/sql/t-sql/statements/create-endpoint-transact-sql) *EndpointName..* . PER DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="36110-124">[CREATE ENDPOINT](/sql/t-sql/statements/create-endpoint-transact-sql) *endpointName* ... FOR DATABASE_MIRRORING</span></span>|<span data-ttu-id="36110-125">Eseguire in ogni istanza del server in cui non è presente l'endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="36110-125">Execute on each server instance that lacks database mirroring endpoint.</span></span>|  
|<span data-ttu-id="36110-126">Creare un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="36110-126">Create availability group</span></span>|[<span data-ttu-id="36110-127">CREATE AVAILABILITY GROUP</span><span class="sxs-lookup"><span data-stu-id="36110-127">CREATE AVAILABILITY GROUP</span></span>](/sql/t-sql/statements/create-availability-group-transact-sql)|<span data-ttu-id="36110-128">Eseguire nell'istanza del server che dovrà ospitare la replica primaria iniziale.</span><span class="sxs-lookup"><span data-stu-id="36110-128">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="36110-129">Creare un join della replica secondaria al gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="36110-129">Join secondary replica to availability group</span></span>|<span data-ttu-id="36110-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *nome_gruppo* JOIN</span><span class="sxs-lookup"><span data-stu-id="36110-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *group_name* JOIN</span></span>|<span data-ttu-id="36110-131">Eseguire in ogni istanza del server in cui è ospitata una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="36110-131">Execute on each server instance that hosts a secondary replica.</span></span>|  
|<span data-ttu-id="36110-132">Preparare il database secondario</span><span class="sxs-lookup"><span data-stu-id="36110-132">Prepare the secondary database</span></span>|<span data-ttu-id="36110-133">[Backup](/sql/t-sql/statements/backup-transact-sql) e [ripristino](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="36110-133">[BACKUP](/sql/t-sql/statements/backup-transact-sql) and [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>|<span data-ttu-id="36110-134">Creare i backup nell'istanza del server in cui è ospitata la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="36110-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="36110-135">Ripristinare i backup in ogni istanza del server che ospita una replica secondaria, utilizzando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="36110-135">Restore backups on each server instance that hosts a secondary replica, using RESTORE WITH NORECOVERY.</span></span>|  
|<span data-ttu-id="36110-136">Avviare la sincronizzazione dei dati creando un join di ogni database secondario al gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="36110-136">Start data synchronization by joining each secondary database to availability group</span></span>|<span data-ttu-id="36110-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *nome_database* SET HADR AVAILABILITY GROUP = *nome_gruppo*</span><span class="sxs-lookup"><span data-stu-id="36110-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>|<span data-ttu-id="36110-138">Eseguire in ogni istanza del server in cui è ospitata una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="36110-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="36110-139">**<sup>\*</sup>** Per eseguire un'attività specifica, connettersi all'istanza o alle istanze del server indicate.</span><span class="sxs-lookup"><span data-stu-id="36110-139">**<sup>\*</sup>**  To perform a given task, connect to the indicated server instance or instances.</span></span>  
  
##  <a name="using-transact-sql-to-create-and-configure-an-availability-group"></a><a name="TsqlProcedure"></a> <span data-ttu-id="36110-140">Utilizzo di Transact-SQL per creare e configurare un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="36110-140">Using Transact-SQL to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36110-141"> Per una procedura di configurazione di esempio contenente esempi di codice di ognuna di queste istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] , vedere [Esempio: Configurazione di un gruppo di disponibilità in cui viene utilizzata l'autenticazione di Windows](#ExampleConfigAGWinAuth).</span><span class="sxs-lookup"><span data-stu-id="36110-141">For a sample configuration procedure containing code examples of each these [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements, see [Example: Configuring an Availability Group that Uses Windows Authentication](#ExampleConfigAGWinAuth).</span></span>  
  
1.  <span data-ttu-id="36110-142">Connettersi all'istanza del server che dovrà ospitare la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="36110-142">Connect to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="36110-143">Creare il gruppo di disponibilità usando l'istruzione [create Availability Group](/sql/t-sql/statements/create-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36110-143">Create the availability group by using the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
3.  <span data-ttu-id="36110-144">Creare un join della nuova replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="36110-144">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="36110-145">Per altre informazioni, vedere [Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="36110-145">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="36110-146">Per ogni database nel gruppo di disponibilità, creare un database secondario ripristinando i backup recenti del database primario, usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="36110-146">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="36110-147">Per altre informazioni, vedere [Esempio: Configurazione di un gruppo di disponibilità in cui viene usata l'autenticazione di Windows (Transact-SQL)](create-an-availability-group-transact-sql.md), a partire dal passaggio per il ripristino del backup di database.</span><span class="sxs-lookup"><span data-stu-id="36110-147">For more information, see [Example: Setting Up an Availability Group Using Windows Authentication (Transact-SQL)](create-an-availability-group-transact-sql.md), starting with the step that restores the database backup.</span></span>  
  
5.  <span data-ttu-id="36110-148">Creare un join di ogni nuovo database secondario al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="36110-148">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="36110-149">Per altre informazioni, vedere [Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="36110-149">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="example-configuring-an-availability-group-that-uses-windows-authentication"></a><a name="ExampleConfigAGWinAuth"></a> <span data-ttu-id="36110-150">Esempio: Configurazione di un gruppo di disponibilità in cui viene usata l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="36110-150">Example: Configuring an Availability Group that Uses Windows Authentication</span></span>  
 <span data-ttu-id="36110-151">In questo esempio viene creata una procedura di configurazione [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] di esempio in cui viene utilizzato [!INCLUDE[tsql](../../../includes/tsql-md.md)] per configurare endpoint del mirroring del database in cui viene utilizzata l'autenticazione di Windows, nonché per creare e configurare un gruppo di disponibilità e i relativi database secondari.</span><span class="sxs-lookup"><span data-stu-id="36110-151">This example creates a sample [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration procedure that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to set up database mirroring endpoints that use Windows Authentication and to create and configure an availability group and its secondary databases.</span></span>  
  
 <span data-ttu-id="36110-152">In questo esempio sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36110-152">This example contains the following sections:</span></span>  
  
-   [<span data-ttu-id="36110-153">Prerequisiti per l'utilizzo della procedura di configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="36110-153">Prerequisites for Using the Sample Configuration Procedure</span></span>](#PrerequisitesForExample)  
  
-   [<span data-ttu-id="36110-154">Procedura di configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="36110-154">Sample Configuration Procedure</span></span>](#SampleProcedure)  
  
-   [<span data-ttu-id="36110-155">Esempio di codice completo per la procedura di configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="36110-155">Complete Code Example for Sample Configuration Procedure</span></span>](#CompleteCodeExample)  
  
###  <a name="prerequisites-for-using-the-sample-configuration-procedure"></a><a name="PrerequisitesForExample"></a> <span data-ttu-id="36110-156">Prerequisiti per l'utilizzo della procedura di configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="36110-156">Prerequisites for Using the Sample Configuration Procedure</span></span>  
 <span data-ttu-id="36110-157">Questa procedura di esempio prevede i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="36110-157">This sample procedure has the following requirements:</span></span>  
  
-   <span data-ttu-id="36110-158">Le istanze del server devono supportare [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36110-158">The server instances must support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="36110-159">Per altre informazioni, vedere [Prerequisiti, restrizioni e consigli per i gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="36110-159">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
-   <span data-ttu-id="36110-160">Devono essere presenti due database di esempio, *MyDb1* e *MyDb2*, nell'istanza del server che ospiterà la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="36110-160">Two sample databases, *MyDb1* and *MyDb2*, must exist on the server instance that will host the primary replica.</span></span> <span data-ttu-id="36110-161">Gli esempi di codice seguenti consentono di creare e configurare questi due database, nonché di creare un backup completo di ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="36110-161">The following code examples create and configure these two databases and create a full backup of each.</span></span> <span data-ttu-id="36110-162">Eseguire questi esempi di codice nell'istanza del server in cui si desidera creare il gruppo di disponibilità di esempio.</span><span class="sxs-lookup"><span data-stu-id="36110-162">Execute these code examples on the server instance on which you intend to create the sample availability group.</span></span> <span data-ttu-id="36110-163">Questa istanza del server ospiterà la replica primaria iniziale del gruppo di disponibilità di esempio.</span><span class="sxs-lookup"><span data-stu-id="36110-163">This server instance will host the initial primary replica of the sample availability group.</span></span>  
  
    1.  <span data-ttu-id="36110-164">L'esempio [!INCLUDE[tsql](../../../includes/tsql-md.md)] seguente consente di creare questi database e di modificarli in modo da utilizzare il modello di recupero con registrazione completa:</span><span class="sxs-lookup"><span data-stu-id="36110-164">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] example creates these databases and alters them to use the full recovery model:</span></span>  
  
        ```sql
        -- Create sample databases:  
        CREATE DATABASE MyDb1;  
        GO  
        ALTER DATABASE MyDb1 SET RECOVERY FULL;  
        GO  
  
        CREATE DATABASE MyDb2;  
        GO  
        ALTER DATABASE MyDb2 SET RECOVERY FULL;  
        GO  
        ```  
  
    2.  <span data-ttu-id="36110-165">Nell'esempio di codice seguente viene creato un backup completo del database di *MyDb1* e *MyDb2*.</span><span class="sxs-lookup"><span data-stu-id="36110-165">The following code example creates a full database backup of *MyDb1* and *MyDb2*.</span></span> <span data-ttu-id="36110-166">Questo esempio di codice usa una condivisione di backup fittizia, \\ \\ *Fileserver* \\ *sqlbackups*.</span><span class="sxs-lookup"><span data-stu-id="36110-166">This code example uses a fictional backup share, \\\\*FILESERVER*\\*SQLbackups*.</span></span>  
  
        ```sql
        -- Backup sample databases:  
        BACKUP DATABASE MyDb1   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
            WITH FORMAT  
        GO  
  
        BACKUP DATABASE MyDb2   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
            WITH FORMAT  
        GO
        ```  
  
###  <a name="sample-configuration-procedure"></a><a name="SampleProcedure"></a> <span data-ttu-id="36110-167">Procedura di configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="36110-167">Sample Configuration Procedure</span></span>  
 <span data-ttu-id="36110-168">In questa configurazione di esempio sarà creata la replica di disponibilità in due istanze del server autonome i cui account del servizio vengono eseguiti in domini differenti, ma trusted,`DOMAIN1` e `DOMAIN2`.</span><span class="sxs-lookup"><span data-stu-id="36110-168">In this sample configuration, the availability replica will be created on two stand-alone server instances whose service accounts run under different, but trusted, domains (`DOMAIN1` and `DOMAIN2`).</span></span>  
  
 <span data-ttu-id="36110-169">Nella tabella seguente sono riepilogati i valori utilizzati in questa configurazione di esempio.</span><span class="sxs-lookup"><span data-stu-id="36110-169">The following table summarizes the values used in this sample configuration.</span></span>  
  
|<span data-ttu-id="36110-170">Ruolo iniziale</span><span class="sxs-lookup"><span data-stu-id="36110-170">Initial role</span></span>|<span data-ttu-id="36110-171">Sistema</span><span class="sxs-lookup"><span data-stu-id="36110-171">System</span></span>|<span data-ttu-id="36110-172">Istanza host di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36110-172">Host [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Instance</span></span>|  
|------------------|------------|---------------------------------------------|  
|<span data-ttu-id="36110-173">Primaria</span><span class="sxs-lookup"><span data-stu-id="36110-173">Primary</span></span>|`COMPUTER01`|`AgHostInstance`|  
|<span data-ttu-id="36110-174">Secondari</span><span class="sxs-lookup"><span data-stu-id="36110-174">Secondary</span></span>|`COMPUTER02`|<span data-ttu-id="36110-175">Istanza predefinita</span><span class="sxs-lookup"><span data-stu-id="36110-175">Default instance.</span></span>|  
  
1.  <span data-ttu-id="36110-176">Creare un endpoint del mirroring del database denominato *dbm_endpoint* nell'istanza del server in cui si intende creare il gruppo di disponibilità. Si tratta di un'istanza denominata `AgHostInstance` in `COMPUTER01`.</span><span class="sxs-lookup"><span data-stu-id="36110-176">Create a database mirroring endpoint named *dbm_endpoint* on the server instance on which you plan to create the availability group (this is an instance named `AgHostInstance` on `COMPUTER01`).</span></span> <span data-ttu-id="36110-177">In questo endpoint si usa la porta 7022.</span><span class="sxs-lookup"><span data-stu-id="36110-177">This endpoint uses port 7022.</span></span> <span data-ttu-id="36110-178">Si noti che la replica primaria sarà ospitata nell'istanza del server in cui si crea il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="36110-178">Note that the server instance on which you create the availability group will host the primary replica.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the primary replica:  
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
2.  <span data-ttu-id="36110-179">Creare un endpoint *dbm_endpoint* nell'istanza del server in cui sarà ospitata la replica secondaria. Si tratta dell'istanza del server predefinita in `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="36110-179">Create an endpoint *dbm_endpoint* on the server instance that will host the secondary replica (this is the default server instance on `COMPUTER02`).</span></span> <span data-ttu-id="36110-180">In questo endpoint si utilizza la porta 5022.</span><span class="sxs-lookup"><span data-stu-id="36110-180">This endpoint uses port 5022.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the secondary replica:   
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=5022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
3.  > [!NOTE]  
    >  <span data-ttu-id="36110-181">Se gli account del servizio delle istanze del server in cui dovranno essere ospitate le repliche di disponibilità sono eseguiti con lo stesso account di dominio, questo passaggio non è necessario.</span><span class="sxs-lookup"><span data-stu-id="36110-181">If the service accounts of the server instances that are to host your availability replicas run under the same domain account this step is unnecessary.</span></span> <span data-ttu-id="36110-182">Ignorarlo e passare direttamente al successivo.</span><span class="sxs-lookup"><span data-stu-id="36110-182">Skip it and go directly to the next step.</span></span>  
  
     <span data-ttu-id="36110-183">Se gli account del servizio delle istanze del server vengono eseguiti con utenti di dominio diversi, in ogni istanza del server creare un account di accesso per l'altra istanza del server e concedere a questo account l'autorizzazione per l'accesso all'endpoint del mirroring del database locale.</span><span class="sxs-lookup"><span data-stu-id="36110-183">If the service accounts of the server instances run under different domain users, on each server instance, create a login for the other server instance and grant this login permission to access the local database mirroring endpoint.</span></span>  
  
     <span data-ttu-id="36110-184">Nell'esempio di codice seguente vengono illustrate le istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] per la creazione di un account di accesso e la concessione dell'autorizzazione in un endpoint.</span><span class="sxs-lookup"><span data-stu-id="36110-184">The following code example shows the [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements for creating a login and granting it permission on an endpoint.</span></span> <span data-ttu-id="36110-185">L'account di dominio dell'istanza del server remoto è rappresentato come *nome_dominio*\\*nome_utente*.</span><span class="sxs-lookup"><span data-stu-id="36110-185">The domain account of the remote server instance is represented here as *domain_name*\\*user_name*.</span></span>  
  
    ```sql
    -- If necessary, create a login for the service account, domain_name\user_name  
    -- of the server instance that will host the other replica:  
    USE master;  
    GO  
    CREATE LOGIN [domain_name\user_name] FROM WINDOWS;  
    GO  
    -- And Grant this login connect permissions on the endpoint:  
    GRANT CONNECT ON ENDPOINT::dbm_endpoint   
       TO [domain_name\user_name];  
    GO  
    ```  
  
4.  <span data-ttu-id="36110-186">Nell'istanza del server in cui si trovano i database utente creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="36110-186">On the server instance where the user databases reside, create the availability group.</span></span>  
  
     <span data-ttu-id="36110-187">Nell'esempio di codice seguente si crea un gruppo di disponibilità denominato *MyAG* nell'istanza del server in cui sono stati creati i database di esempio, *MyDb1* e *MyDb2*.</span><span class="sxs-lookup"><span data-stu-id="36110-187">The following code example creates an availability group named *MyAG* on the server instance on which the sample databases, *MyDb1* and *MyDb2*, were created.</span></span> <span data-ttu-id="36110-188">Si specifica innanzitutto l'istanza del server locale, `AgHostInstance`, su *COMPUTER01* .</span><span class="sxs-lookup"><span data-stu-id="36110-188">The local server instance, `AgHostInstance`, on *COMPUTER01* is specified first.</span></span> <span data-ttu-id="36110-189">Questa istanza ospiterà la replica primaria iniziale.</span><span class="sxs-lookup"><span data-stu-id="36110-189">This instance will host the initial primary replica.</span></span> <span data-ttu-id="36110-190">Si specifica un'istanza del server remota, l'istanza del server predefinita in *COMPUTER02*, in cui viene ospitata una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="36110-190">A remote server instance, the default server instance on *COMPUTER02*, is specified to host a secondary replica.</span></span> <span data-ttu-id="36110-191">Entrambe le repliche di disponibilità sono configurate per utilizzare la modalità con commit asincrono con failover manuale. Per le repliche con commit asincrono il failover manuale indica un failover forzato con possibile perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="36110-191">Both availability replica are configured to use asynchronous-commit mode with manual failover (for asynchronous-commit replicas manual failover means  forced failover with possible data loss).</span></span>  
  
    ```sql
    -- Create the availability group, MyAG:   
    CREATE AVAILABILITY GROUP MyAG   
       FOR   
          DATABASE MyDB1, MyDB2   
       REPLICA ON   
          'COMPUTER01\AgHostInstance' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',   
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             ),  
          'COMPUTER02' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );   
    GO  
    ```  
  
     <span data-ttu-id="36110-192">Per altri esempi di codice [!INCLUDE[tsql](../../../includes/tsql-md.md)] per la creazione di un gruppo di disponibilità, vedere [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="36110-192">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
5.  <span data-ttu-id="36110-193">Nell'istanza del server in cui viene ospitata la replica secondaria creare un join della replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="36110-193">On the server instance that hosts the secondary replica, join the secondary replica to the availability group.</span></span>  
  
     <span data-ttu-id="36110-194">Nell'esempio di codice seguente viene creato un join della replica secondaria in `COMPUTER02` al gruppo di disponibilità `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="36110-194">The following code example joins the secondary replica on `COMPUTER02` to the `MyAG` availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join the secondary replica to the availability group:  
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    GO  
    ```  
  
6.  <span data-ttu-id="36110-195">Nell'istanza del server che ospita la replica secondaria creare i database secondari.</span><span class="sxs-lookup"><span data-stu-id="36110-195">On the server instance that hosts the secondary replica, create the secondary databases.</span></span>  
  
     <span data-ttu-id="36110-196">L'esempio di codice seguente crea i database secondari *MyDb1* e *MyDb2* ripristinando i backup dei database tramite RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="36110-196">The following code example creates the *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- Restore database backups using the WITH NORECOVERY option:  
    RESTORE DATABASE MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NORECOVERY  
    GO  
  
    RESTORE DATABASE MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH NORECOVERY  
    GO
    ```  
  
7.  <span data-ttu-id="36110-197">Nell'istanza del server in cui viene ospitata la replica primaria eseguire il backup del log delle transazioni in ognuno dei database primari.</span><span class="sxs-lookup"><span data-stu-id="36110-197">On the server instance that hosts the primary replica, back up the transaction log on each of the primary databases.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="36110-198">Quando si configura un gruppo di disponibilità reale, prima di eseguire questo backup del log è consigliabile sospendere le attività di backup del log per i database primari fino a quando non è stato creato un join dei database secondari corrispondenti al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="36110-198">When you are configuring a real availability group, we recommend that, before taking this log backup, you suspend log backup tasks for your primary databases until you have joined the corresponding secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="36110-199">Nell'esempio di codice seguente viene creato un backup del log delle transazioni in MyDb1 e MyDb2.</span><span class="sxs-lookup"><span data-stu-id="36110-199">The following code example creates a transaction log backup on MyDb1 and on MyDb2.</span></span>  
  
    ```sql
    -- On the server instance that hosts the primary replica,   
    -- Backup the transaction log on each primary database:  
    BACKUP LOG MyDb1   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NOFORMAT  
    GO  
  
    BACKUP LOG MyDb2   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITHNOFORMAT  
    GO
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="36110-200">In genere, è necessario eseguire un backup del log in ogni database primario, quindi ripristinare tale backup nel database secondario corrispondente utilizzando WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="36110-200">Typically, a log backup must be taken on each primary database and then restored on the corresponding secondary database (using WITH NORECOVERY).</span></span> <span data-ttu-id="36110-201">Questo backup del log potrebbe tuttavia non essere necessario se il database è stato appena creato e non è ancora stato eseguito alcun backup del log oppure se il modello di recupero è stato appena modificato da SIMPLE a FULL.</span><span class="sxs-lookup"><span data-stu-id="36110-201">However, this log backup might be unnecessary if the database has just been created and no log backup has been taken yet or the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
8.  <span data-ttu-id="36110-202">Nell'istanza del server che ospita la replica secondaria applicare i backup del log ai database secondari.</span><span class="sxs-lookup"><span data-stu-id="36110-202">On the server instance that hosts the secondary replica, apply log backups to the secondary databases.</span></span>  
  
     <span data-ttu-id="36110-203">L'esempio di codice seguente applica backup ai database secondari *MyDb1* e *MyDb2* ripristinando i backup dei database tramite RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="36110-203">The following code example applies backups to *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="36110-204">Quando si prepara un database secondario reale, è necessario applicare ogni backup del log eseguito dopo il backup del database da cui è stato creato il database secondario, a partire da quello meno recente e utilizzando sempre RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="36110-204">When you are preparing a real secondary database, you need to apply every log backup taken since the database backup from which you created the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="36110-205">Naturalmente, se si ripristinano sia il backup completo del database che il backup differenziale, è necessario applicare solo i backup del log eseguiti dopo il backup differenziale.</span><span class="sxs-lookup"><span data-stu-id="36110-205">Of course, if you restore both full and differential database backups, you would only need to apply the log backups taken after the differential backup.</span></span>  
  
    ```sql
    -- Restore the transaction log on each secondary database,  
    -- using the WITH NORECOVERY option:  
    RESTORE LOG MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    RESTORE LOG MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
9. <span data-ttu-id="36110-206">Nell'istanza del server che ospita la replica secondaria creare un join dei nuovi database secondari al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="36110-206">On the server instance that hosts the secondary replica, join the new secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="36110-207">L'esempio di codice seguente crea i join dei database secondari *MyDb1* e *MyDb2* al gruppo di disponibilità *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="36110-207">The following code example, joins the *MyDb1* secondary database and then the *MyDb2* secondary databases to the *MyAG* availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join each secondary database to the availability group:  
    ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
    GO  
  
    ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
    GO
    ```  
  
###  <a name="complete-code-example-for-sample-configuration-procedure"></a><a name="CompleteCodeExample"></a> <span data-ttu-id="36110-208">Esempio di codice completo per la procedura di configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="36110-208">Complete Code Example for Sample Configuration Procedure</span></span>  
 <span data-ttu-id="36110-209">Nell'esempio seguente vengono uniti gli esempi di codice di tutti i passaggi della procedura di configurazione di esempio.</span><span class="sxs-lookup"><span data-stu-id="36110-209">The following example merges the code examples from all the steps of the sample configuration procedure.</span></span> <span data-ttu-id="36110-210">Nella tabella seguente sono riepilogati i valori segnaposto utilizzati nell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="36110-210">The following table summarized the placeholder values used in this code example.</span></span> <span data-ttu-id="36110-211">Per ulteriori informazioni sui passaggi di questo esempio di codice, vedere [Prerequisiti per l'utilizzo della procedura di configurazione di esempio](#PrerequisitesForExample) e [Procedura di configurazione di esempio](#SampleProcedure), precedentemente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="36110-211">For more information about the steps in this code example, see [Prerequisites for Using the Sample Configuration Procedure](#PrerequisitesForExample) and [Sample Configuration Procedure](#SampleProcedure), earlier in this topic.</span></span>  
  
|<span data-ttu-id="36110-212">Segnaposto</span><span class="sxs-lookup"><span data-stu-id="36110-212">Placeholder</span></span>|<span data-ttu-id="36110-213">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36110-213">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="36110-214">\\\\*FILESERVER*\\*SQLbackups*</span><span class="sxs-lookup"><span data-stu-id="36110-214">\\\\*FILESERVER*\\*SQLbackups*</span></span>|<span data-ttu-id="36110-215">Condivisione di backup fittizia.</span><span class="sxs-lookup"><span data-stu-id="36110-215">Fictional backup share.</span></span>|  
|<span data-ttu-id="36110-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span><span class="sxs-lookup"><span data-stu-id="36110-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span></span>|<span data-ttu-id="36110-217">File di backup per MyDb1.</span><span class="sxs-lookup"><span data-stu-id="36110-217">Backup file for MyDb1.</span></span>|  
|<span data-ttu-id="36110-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span><span class="sxs-lookup"><span data-stu-id="36110-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span></span>|<span data-ttu-id="36110-219">File di backup per MyDb2.</span><span class="sxs-lookup"><span data-stu-id="36110-219">Backup file for MyDb2.</span></span>|  
|<span data-ttu-id="36110-220">*7022*</span><span class="sxs-lookup"><span data-stu-id="36110-220">*7022*</span></span>|<span data-ttu-id="36110-221">Numero di porta assegnato a ogni endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="36110-221">Port number assigned to each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="36110-222">*COMPUTER01\AgHostInstance*</span><span class="sxs-lookup"><span data-stu-id="36110-222">*COMPUTER01\AgHostInstance*</span></span>|<span data-ttu-id="36110-223">Istanza del server che ospita la replica primaria iniziale.</span><span class="sxs-lookup"><span data-stu-id="36110-223">Server instance that hosts the initial primary replica.</span></span>|  
|<span data-ttu-id="36110-224">*COMPUTER02*</span><span class="sxs-lookup"><span data-stu-id="36110-224">*COMPUTER02*</span></span>|<span data-ttu-id="36110-225">Istanza del server in cui viene ospitata la replica secondaria iniziale.</span><span class="sxs-lookup"><span data-stu-id="36110-225">Server instance that hosts the initial secondary replica.</span></span> <span data-ttu-id="36110-226">Si tratta dell'istanza del server predefinita in `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="36110-226">This is the default server instance on `COMPUTER02`.</span></span>|  
|<span data-ttu-id="36110-227">*dbm_endpoint*</span><span class="sxs-lookup"><span data-stu-id="36110-227">*dbm_endpoint*</span></span>|<span data-ttu-id="36110-228">Nome specificato per ogni endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="36110-228">Name specified for each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="36110-229">*MyAG*</span><span class="sxs-lookup"><span data-stu-id="36110-229">*MyAG*</span></span>|<span data-ttu-id="36110-230">Nome del gruppo di disponibilità di esempio.</span><span class="sxs-lookup"><span data-stu-id="36110-230">Name of sample availability group.</span></span>|  
|<span data-ttu-id="36110-231">*MyDb1*</span><span class="sxs-lookup"><span data-stu-id="36110-231">*MyDb1*</span></span>|<span data-ttu-id="36110-232">Nome del primo database di esempio.</span><span class="sxs-lookup"><span data-stu-id="36110-232">Name of first sample database.</span></span>|  
|<span data-ttu-id="36110-233">*MyDb2*</span><span class="sxs-lookup"><span data-stu-id="36110-233">*MyDb2*</span></span>|<span data-ttu-id="36110-234">Nome del secondo database di esempio.</span><span class="sxs-lookup"><span data-stu-id="36110-234">Name of second sample database.</span></span>|  
|<span data-ttu-id="36110-235">*DOMAIN1\user1*</span><span class="sxs-lookup"><span data-stu-id="36110-235">*DOMAIN1\user1*</span></span>|<span data-ttu-id="36110-236">Account del servizio dell'istanza del server che dovrà ospitare la replica primaria iniziale.</span><span class="sxs-lookup"><span data-stu-id="36110-236">Service account of the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="36110-237">*DOMAIN2\user2*</span><span class="sxs-lookup"><span data-stu-id="36110-237">*DOMAIN2\user2*</span></span>|<span data-ttu-id="36110-238">Account del servizio dell'istanza del server in cui dovrà essere ospitata la replica secondaria iniziale.</span><span class="sxs-lookup"><span data-stu-id="36110-238">Service account of the server instance that is to host the initial secondary replica.</span></span>|  
|<span data-ttu-id="36110-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span><span class="sxs-lookup"><span data-stu-id="36110-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span></span>|<span data-ttu-id="36110-240">URL dell'endpoint dell'istanza AgHostInstance di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in COMPUTER01.</span><span class="sxs-lookup"><span data-stu-id="36110-240">Endpoint URL of the AgHostInstance instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER01.</span></span>|  
|<span data-ttu-id="36110-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span><span class="sxs-lookup"><span data-stu-id="36110-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span></span>|<span data-ttu-id="36110-242">URL dell'endpoint dell'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in COMPUTER02.</span><span class="sxs-lookup"><span data-stu-id="36110-242">Endpoint URL of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER02.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="36110-243">Per altri esempi di codice [!INCLUDE[tsql](../../../includes/tsql-md.md)] per la creazione di un gruppo di disponibilità, vedere [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="36110-243">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
```sql
-- on the server instance that will host the primary replica,   
-- create sample databases:  
CREATE DATABASE MyDb1;  
GO  
ALTER DATABASE MyDb1 SET RECOVERY FULL;  
GO  
  
CREATE DATABASE MyDb2;  
GO  
ALTER DATABASE MyDb2 SET RECOVERY FULL;  
GO  
  
-- Backup sample databases:  
BACKUP DATABASE MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FORMAT  
GO  
  
BACKUP DATABASE MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FORMAT  
GO  
  
-- Create the endpoint on the server instance that will host the primary replica:  
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- Create the endpoint on the server instance that will host the secondary replica:   
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the primary replica,   
-- create a login for the service account   
-- of the server instance that will host the secondary replica, DOMAIN2\user2,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
CREATE LOGIN [DOMAIN2\user2] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN2\user2];  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the secondary replica,  
-- create a login for the service account   
-- of the server instance that will host the primary replica, DOMAIN1\user1,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
  
CREATE LOGIN [DOMAIN1\user1] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN1\user1];  
GO  
  
-- On the server instance that will host the primary replica,   
-- create the availability group, MyAG:  
CREATE AVAILABILITY GROUP MyAG   
   FOR   
      DATABASE MyDB1, MyDB2   
   REPLICA ON   
      'COMPUTER01\AgHostInstance' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         ),  
      'COMPUTER02' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         );   
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join the secondary replica to the availability group:  
ALTER AVAILABILITY GROUP MyAG JOIN;  
GO  
  
-- Restore database backups onto this server instance, using RESTORE WITH NORECOVERY:  
RESTORE DATABASE MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NORECOVERY  
GO  
  
RESTORE DATABASE MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH NORECOVERY  
GO  
  
-- Back up the transaction log on each primary database:  
BACKUP LOG MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NOFORMAT  
GO  
  
BACKUP LOG MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITHNOFORMAT  
GO  
  
-- Restore the transaction log on each secondary database,  
-- using the WITH NORECOVERY option:  
RESTORE LOG MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FILE=1, NORECOVERY  
GO  
RESTORE LOG MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FILE=1, NORECOVERY  
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join each secondary database to the availability group:  
ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
GO  
  
ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
GO
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="36110-244">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="36110-244">Related Tasks</span></span>  
 <span data-ttu-id="36110-245">**Per configurare le proprietà della replica e del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="36110-245">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="36110-246">Modificare la modalità di disponibilità di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-246">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="36110-247">Modificare la modalità di failover di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-247">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="36110-248">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-248">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="36110-249">Configurare i criteri di failover flessibili per controllare le condizioni per il failover automatico (Gruppi di disponibilità AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="36110-249">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="36110-250">Specifica dell'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-250">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="36110-251">Configurare il backup su repliche di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-251">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="36110-252">Configurare l'accesso in sola lettura in una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-252">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="36110-253">Configurare il routing di sola lettura per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-253">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="36110-254">Modificare il periodo di timeout della sessione per una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-254">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="36110-255">**Per completare la configurazione del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="36110-255">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="36110-256">Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-256">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="36110-257">Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-257">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="36110-258">Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-258">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="36110-259">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-259">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="36110-260">**Modalità alternative di creazione di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="36110-260">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="36110-261">Usare la Creazione guidata Gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-261">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="36110-262">Utilizzare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-262">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="36110-263">Creare un gruppo di disponibilità &#40;PowerShell SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-263">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
 <span data-ttu-id="36110-264">**Per abilitare Gruppi di disponibilità AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="36110-264">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="36110-265">Abilitare e disabilitare la funzionalità Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-265">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="36110-266">**Per configurare un endpoint del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="36110-266">**To configure a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="36110-267">Creazione di un endpoint del mirroring del database per Gruppi di disponibilità AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-267">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="36110-268">Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-268">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="36110-269">Utilizzare certificati per un endpoint del mirroring del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-269">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
-   [<span data-ttu-id="36110-270">Specifica dell'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-270">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="36110-271">**Per risolvere i problemi relativi alla configurazione di Gruppi di disponibilità AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="36110-271">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="36110-272">Risolvere i problemi di configurazione Gruppi di disponibilità AlwaysOn (SQL Server) eliminati</span><span class="sxs-lookup"><span data-stu-id="36110-272">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="36110-273">Risolvere i problemi relativi a un'operazione di aggiunta file non riuscita &#40;Gruppi di disponibilità AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-273">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="36110-274">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="36110-274">Related Content</span></span>  
  
-   <span data-ttu-id="36110-275">**Blog:**</span><span class="sxs-lookup"><span data-stu-id="36110-275">**Blogs:**</span></span>  
  
     [<span data-ttu-id="36110-276">Serie di informazioni su AlwaysON - HADRON: Utilizzo del pool di lavoro per database abilitati HADRON</span><span class="sxs-lookup"><span data-stu-id="36110-276">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="36110-277">Blog del team di SQL Server AlwaysOn: Blog ufficiale del team di SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="36110-277">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="36110-278">Pagina relativa ai blog del Servizio Supporto Tecnico Clienti per gli ingegneri di SQL Server</span><span class="sxs-lookup"><span data-stu-id="36110-278">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="36110-279">**Video:**</span><span class="sxs-lookup"><span data-stu-id="36110-279">**Videos:**</span></span>  
  
     [<span data-ttu-id="36110-280">Pagina relativa alla prima parte riguardante l'introduzione della soluzione a disponibilità elevata di prossima generazione della serie AlwaysOn di Microsoft SQL Server nome in codice "Denali"</span><span class="sxs-lookup"><span data-stu-id="36110-280">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="36110-281">Pagina relativa alla seconda parte riguardante la compilazione di una soluzione a disponibilità elevata critica tramite AlwasyOn della serie AlwaysOn di Microsoft SQL Server nome in codice "Denali"</span><span class="sxs-lookup"><span data-stu-id="36110-281">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="36110-282">**White paper:**</span><span class="sxs-lookup"><span data-stu-id="36110-282">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="36110-283">Pagina relativa alla guida alle soluzioni AlwaysOn di Microsoft SQL Server per la disponibilità elevata e il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="36110-283">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="36110-284">Pagina relativa ai white paper Microsoft per SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="36110-284">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="36110-285">Pagina relativa ai white paper del team di consulenza clienti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="36110-285">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="36110-286">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36110-286">See Also</span></span>  
 <span data-ttu-id="36110-287">[Endpoint del mirroring del database &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="36110-287">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="36110-288">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="36110-288">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="36110-289">Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36110-289">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)   
