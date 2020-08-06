---
title: Creare un gruppo di disponibilità (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: bc69a7df-20fa-41e1-9301-11317c5270d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3af9bf896b954e6849c0d491f9ed267655369ccb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727139"
---
# <a name="create-an-availability-group-sql-server-powershell"></a><span data-ttu-id="ae289-102">Creare un gruppo di disponibilità (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="ae289-102">Create an Availability Group (SQL Server PowerShell)</span></span>
  <span data-ttu-id="ae289-103">In questo argomento si illustra come usare i cmdlet di PowerShell per creare e configurare un gruppo di disponibilità AlwaysOn usando PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae289-103">This topic describes how to use PowerShell cmdlets to create and configure an AlwaysOn availability group by using PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="ae289-104">Un *gruppo di disponibilità* permette di definire un set di database utente di cui sarà eseguito il failover come unità singola e un set di partner di failover, noti come *repliche di disponibilità*, che supportano il failover.</span><span class="sxs-lookup"><span data-stu-id="ae289-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, which support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae289-105">Per un'introduzione ai gruppi di disponibilità, vedere [Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ae289-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="ae289-106">In alternativa all'uso dei cmdlet di PowerShell, è possibile usare la procedura guidata Crea gruppo di disponibilità o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae289-106">As an alternative to using PowerShell cmdlets, you can use the Create Availability Group wizard or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ae289-107">Per altre informazioni, vedere [Usare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) o [Creare un gruppo di disponibilità &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ae289-107">For more information, see [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) or [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ae289-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ae289-108">Before You Begin</span></span>  
 <span data-ttu-id="ae289-109">Prima di iniziare a creare il primo gruppo di disponibilità, è consigliabile leggere questa sezione.</span><span class="sxs-lookup"><span data-stu-id="ae289-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="ae289-110">Prerequisiti, restrizioni e raccomandazioni</span><span class="sxs-lookup"><span data-stu-id="ae289-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="ae289-111">Prima di creare un gruppo di disponibilità, verificare che le istanze host di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] si trovino ognuna in un nodo WSCF (Windows Server Failover Clustering) diverso di un singolo cluster di failover WSFC.</span><span class="sxs-lookup"><span data-stu-id="ae289-111">Before creating an availability group, verify that the host instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] each resides on a different Windows Server Failover Clustering (WSFC) node of a single WSFC failover cluster.</span></span> <span data-ttu-id="ae289-112">Inoltre, verificare che le istanze del server abbiano soddisfatto gli altri prerequisiti dell'istanza del server, che tutti gli altri requisiti di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] siano soddisfatti e che si tengano presenti i consigli.</span><span class="sxs-lookup"><span data-stu-id="ae289-112">Also, verify that your server instances met the other server-instance prerequisites and that all of the other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] requirements are meet and that you are aware of the recommendations.</span></span> <span data-ttu-id="ae289-113">Per altre informazioni è consigliabile leggere [Prerequisiti, restrizioni e consigli per i gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="ae289-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ae289-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ae289-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ae289-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ae289-115">Permissions</span></span>  
 <span data-ttu-id="ae289-116">Sono necessarie l'appartenenza al ruolo predefinito del server **sysadmin** e l'autorizzazione server CREATE AVAILABILITY GROUP oppure l'autorizzazione ALTER ANY AVAILABILITY GROUP o CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ae289-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-powershell-cmdlets"></a><a name="SummaryPSStatements"></a><span data-ttu-id="ae289-117">Riepilogo delle attività e cmdlet di PowerShell corrispondenti</span><span class="sxs-lookup"><span data-stu-id="ae289-117">Summary of Tasks and Corresponding PowerShell Cmdlets</span></span>  
 <span data-ttu-id="ae289-118">Nella tabella seguente sono elencate le attività di base necessarie per la configurazione di un gruppo di disponibilità e sono indicate le attività supportate dai cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae289-118">The following table lists the basic tasks involved in configuring an availability group and indicates those that are supported by PowerShell cmdlets.</span></span> <span data-ttu-id="ae289-119">È necessario eseguire le attività [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] nell'ordine con cui sono elencate nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ae289-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="ae289-120">Attività</span><span class="sxs-lookup"><span data-stu-id="ae289-120">Task</span></span>|<span data-ttu-id="ae289-121">Cmdlet di PowerShell (se disponibile) o istruzione Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ae289-121">PowerShell Cmdlets (if Available) or Transact-SQL Statement</span></span>|<span data-ttu-id="ae289-122">Posizione in cui eseguire l'attività**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="ae289-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|--------------------------------------------------------------------|-------------------------------------------|  
|<span data-ttu-id="ae289-123">Creare un endpoint del mirroring del database (una volta per ogni istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="ae289-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|`New-SqlHadrEndPoint`|<span data-ttu-id="ae289-124">Eseguire in ogni istanza del server in cui non è presente l'endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="ae289-124">Execute on each server instance that lacks database mirroring endpoint.</span></span><br /><br /> <span data-ttu-id="ae289-125">Nota: per modificare un endpoint del mirroring del database esistente, usare `Set-SqlHadrEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="ae289-125">Note: To alter an existing database mirroring endpoint, use `Set-SqlHadrEndpoint`.</span></span>|  
|<span data-ttu-id="ae289-126">Creare un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="ae289-126">Create availability group</span></span>|<span data-ttu-id="ae289-127">Usare innanzitutto il cmdlet `New-SqlAvailabilityReplica` con il parametro `-AsTemplate` per creare un oggetto della replica di disponibilità in memoria per ognuna delle due repliche di disponibilità che si desidera includere nel gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ae289-127">First, use the `New-SqlAvailabilityReplica` cmdlet with the `-AsTemplate` parameter to create an in-memory availability-replica object for each of the two availability replicas that you plan to include in the availability group.</span></span><br /><br /> <span data-ttu-id="ae289-128">Creare quindi il gruppo di disponibilità tramite il cmdlet `New-SqlAvailabilityGroup` e facendo riferimento agli oggetti replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ae289-128">Then, create the availability group by using the `New-SqlAvailabilityGroup` cmdlet and referencing your availability-replica objects.</span></span>|<span data-ttu-id="ae289-129">Eseguire nell'istanza del server che dovrà ospitare la replica primaria iniziale.</span><span class="sxs-lookup"><span data-stu-id="ae289-129">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="ae289-130">Creare un join della replica secondaria al gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="ae289-130">Join secondary replica to availability group</span></span>|`Join-SqlAvailabilityGroup`|<span data-ttu-id="ae289-131">Eseguire in ogni istanza del server in cui è ospitata una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="ae289-131">Execute on each server instance that is hosts a secondary replica.</span></span>|  
|<span data-ttu-id="ae289-132">Preparare il database secondario</span><span class="sxs-lookup"><span data-stu-id="ae289-132">Prepare the secondary database</span></span>|<span data-ttu-id="ae289-133">`Backup-SqlDatabase` e `Restore-SqlDatabase`</span><span class="sxs-lookup"><span data-stu-id="ae289-133">`Backup-SqlDatabase` and `Restore-SqlDatabase`</span></span>|<span data-ttu-id="ae289-134">Creare i backup nell'istanza del server in cui è ospitata la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="ae289-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="ae289-135">Ripristinare i backup in ogni istanza del server in cui è ospitata una replica secondaria, usando il parametro di ripristino `NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="ae289-135">Restore backups on each server instance that hosts a secondary replica, using the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="ae289-136">Se i percorsi di file differiscono tra i computer in cui sono ospitate la replica primaria e la replica secondaria di destinazione, usare anche il parametro di ripristino `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="ae289-136">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>|  
|<span data-ttu-id="ae289-137">Avviare la sincronizzazione dei dati creando un join di ogni database secondario al gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="ae289-137">Start data synchronization by joining each secondary database to availability group</span></span>|`Add-SqlAvailabilityDatabase`|<span data-ttu-id="ae289-138">Eseguire in ogni istanza del server in cui è ospitata una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="ae289-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="ae289-139">**<sup>\*</sup>** Per eseguire un'attività specifica, impostare la directory ( `cd` ) sull'istanza o sulle istanze del server indicate.</span><span class="sxs-lookup"><span data-stu-id="ae289-139">**<sup>\*</sup>**  To perform a given task, change directory (`cd`) to the indicated server instance or instances.</span></span>  
  
###  <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><a name="PsProviderLinks"></a><span data-ttu-id="ae289-140">Per configurare e usare il provider di SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae289-140">To Set Up and Use the SQL Server PowerShell Provider</span></span>  
  
-   [<span data-ttu-id="ae289-141">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae289-141">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="ae289-142">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae289-142">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="using-powershell-to-create-and-configure-an-availability-group"></a><a name="PowerShellProcedure"></a><span data-ttu-id="ae289-143">Uso di PowerShell per creare e configurare un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="ae289-143">Using PowerShell to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae289-144">Per visualizzare la sintassi e un esempio di un cmdlet specifico, usare il cmdlet `Get-Help` nell'ambiente PowerShell [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae289-144">To view the syntax and an example of a given cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="ae289-145">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ae289-145">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
1.  <span data-ttu-id="ae289-146">Spostarsi nella directory (`cd`) dell'istanza del server che deve ospitare la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="ae289-146">Change directory (`cd`) to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="ae289-147">Creare un oggetto replica di disponibilità in memoria per la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="ae289-147">Create an in-memory availability-replica object for the primary replica.</span></span>  
  
3.  <span data-ttu-id="ae289-148">Creare un oggetto replica di disponibilità in memoria per ognuna delle repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="ae289-148">Create an in-memory availability-replica object for each of the secondary replicas.</span></span>  
  
4.  <span data-ttu-id="ae289-149">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ae289-149">Create the availability group.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ae289-150">La lunghezza massima consentita per il nome del gruppo di disponibilità è 128 caratteri.</span><span class="sxs-lookup"><span data-stu-id="ae289-150">The maximum length for an availability group name is 128 characters.</span></span>  
  
5.  <span data-ttu-id="ae289-151">Creare un join della nuova replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ae289-151">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="ae289-152">Per altre informazioni, vedere [Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ae289-152">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
6.  <span data-ttu-id="ae289-153">Per ogni database nel gruppo di disponibilità, creare un database secondario ripristinando i backup recenti del database primario, usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="ae289-153">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span>  
  
7.  <span data-ttu-id="ae289-154">Creare un join di ogni nuovo database secondario al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ae289-154">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="ae289-155">Per altre informazioni, vedere [Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ae289-155">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="ae289-156">Facoltativamente, usare il comando `dir` di Windows per verificare il contenuto del nuovo gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ae289-156">Optionally, use the Windows `dir` command to verify the contents of the new availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae289-157">Se gli account del servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] delle istanze del server sono eseguiti con account utente di dominio diversi, in ogni istanza del server creare un account di accesso per l'altra istanza del server e concedere a questo account l'autorizzazione CONNECT per l'endpoint del mirroring del database locale.</span><span class="sxs-lookup"><span data-stu-id="ae289-157">If the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service accounts of the server instances run under different domain user accounts, on each server instance, create a login for the other server instance and grant this login CONNECT permission to the local database mirroring endpoint.</span></span>  
  
##  <a name="example-using-powershell-to-create-an-availability-group"></a><a name="ExampleConfigureGroup"></a><span data-ttu-id="ae289-158">Esempio: uso di PowerShell per creare un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="ae289-158">Example: Using PowerShell to Create an Availability Group</span></span>  
 <span data-ttu-id="ae289-159">Nell'esempio di PowerShell seguente si crea e si configura un gruppo di disponibilità semplice denominato `MyAG` con due repliche di disponibilità e un database di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ae289-159">The following PowerShell example creates and configures a simple availability group named `MyAG` with two availability replicas and one availability database.</span></span> <span data-ttu-id="ae289-160">Esempio:</span><span class="sxs-lookup"><span data-stu-id="ae289-160">The example:</span></span>  
  
1.  <span data-ttu-id="ae289-161">Viene eseguito il backup di `MyDatabase` e del relativo log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ae289-161">Backs up `MyDatabase` and its transaction log.</span></span>  
  
2.  <span data-ttu-id="ae289-162">Vengono ripristinati `MyDatabase` e il relativo log delle transazioni, usando l'opzione `-NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="ae289-162">Restores `MyDatabase` and its transaction log, using the `-NoRecovery` option.</span></span>  
  
3.  <span data-ttu-id="ae289-163">Viene creata una rappresentazione in memoria della replica primaria, che sarà ospitata dall'istanza locale di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (denominata `PrimaryComputer\Instance`).</span><span class="sxs-lookup"><span data-stu-id="ae289-163">Creates an in-memory representation of the primary replica, which will be hosted by the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `PrimaryComputer\Instance`).</span></span>  
  
4.  <span data-ttu-id="ae289-164">Viene creata una rappresentazione in memoria della replica secondaria, che sarà ospitata da un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (denominata `SecondaryComputer\Instance`).</span><span class="sxs-lookup"><span data-stu-id="ae289-164">Creates an in-memory representation of the secondary replica, which will be hosted by an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `SecondaryComputer\Instance`).</span></span>  
  
5.  <span data-ttu-id="ae289-165">Viene creato un nuovo gruppo di disponibilità denominato `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="ae289-165">Creates an availability group named `MyAG`.</span></span>  
  
6.  <span data-ttu-id="ae289-166">Viene creato un join della replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ae289-166">Joins the secondary replica to the availability group.</span></span>  
  
7.  <span data-ttu-id="ae289-167">Viene creato un join del database secondario al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ae289-167">Joins the secondary database to the availability group.</span></span>  
  
```powershell
# Backup my database and its log on the primary  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "PrimaryComputer\Instance"  
  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "PrimaryComputer\Instance" `  
    -BackupAction Log   
  
# Restore the database and log on the secondary (using NO RECOVERY)  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -NoRecovery  
  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -RestoreAction Log `  
    -NoRecovery  
  
# Create an in-memory representation of the primary replica.  
$primaryReplica = New-SqlAvailabilityReplica `  
    -Name "PrimaryComputer\Instance" `  
    -EndpointURL "TCP://PrimaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create an in-memory representation of the secondary replica.  
$secondaryReplica = New-SqlAvailabilityReplica `  
    -Name "SecondaryComputer\Instance" `  
    -EndpointURL "TCP://SecondaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create the availability group  
New-SqlAvailabilityGroup `  
    -Name "MyAG" `  
    -Path "SQLSERVER:\SQL\PrimaryComputer\Instance" `  
    -AvailabilityReplica @($primaryReplica,$secondaryReplica) `  
    -Database "MyDatabase"  
  
# Join the secondary replica to the availability group.  
Join-SqlAvailabilityGroup -Path "SQLSERVER:\SQL\SecondaryComputer\Instance" -Name "MyAG"  
  
# Join the secondary database to the availability group.  
Add-SqlAvailabilityDatabase -Path "SQLSERVER:\SQL\SecondaryComputer\Instance\AvailabilityGroups\MyAG" -Database "MyDatabase"  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ae289-168">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="ae289-168">Related Tasks</span></span>  
 <span data-ttu-id="ae289-169">**Per configurare un'istanza del server per i gruppi di disponibilità AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="ae289-169">**To configure a server instance for AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="ae289-170">Abilitare e disabilitare la funzionalità Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-170">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="ae289-171">Creazione di un endpoint del mirroring del database per Gruppi di disponibilità AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-171">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
 <span data-ttu-id="ae289-172">**Per configurare le proprietà della replica e del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="ae289-172">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="ae289-173">Modificare la modalità di disponibilità di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-173">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="ae289-174">Modificare la modalità di failover di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-174">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="ae289-175">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-175">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="ae289-176">Configurare i criteri di failover flessibili per controllare le condizioni per il failover automatico (Gruppi di disponibilità AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="ae289-176">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="ae289-177">Specifica dell'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-177">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="ae289-178">Configurare il backup su repliche di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-178">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="ae289-179">Configurare l'accesso in sola lettura in una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-179">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="ae289-180">Configurare il routing di sola lettura per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-180">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="ae289-181">Modificare il periodo di timeout della sessione per una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-181">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="ae289-182">**Per completare la configurazione del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="ae289-182">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="ae289-183">Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-183">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="ae289-184">Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-184">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="ae289-185">Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-185">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="ae289-186">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-186">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="ae289-187">**Modalità alternative di creazione di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="ae289-187">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="ae289-188">Usare la Creazione guidata Gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-188">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ae289-189">Utilizzare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-189">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ae289-190">Creare un gruppo di disponibilità &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-190">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
 <span data-ttu-id="ae289-191">**Per risolvere i problemi relativi alla configurazione di Gruppi di disponibilità AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="ae289-191">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="ae289-192">Risolvere i problemi di configurazione Gruppi di disponibilità AlwaysOn (SQL Server) eliminati</span><span class="sxs-lookup"><span data-stu-id="ae289-192">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="ae289-193">Risolvere i problemi relativi a un'operazione di aggiunta file non riuscita &#40;Gruppi di disponibilità AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-193">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="ae289-194">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="ae289-194">Related Content</span></span>  
  
-   <span data-ttu-id="ae289-195">**Blog:**</span><span class="sxs-lookup"><span data-stu-id="ae289-195">**Blogs:**</span></span>  
  
     [<span data-ttu-id="ae289-196">Serie di informazioni su AlwaysON - HADRON: Utilizzo del pool di lavoro per database abilitati HADRON</span><span class="sxs-lookup"><span data-stu-id="ae289-196">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="ae289-197">Pagina relativa alla configurazione di AlwaysOn con SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae289-197">Configuring AlwaysOn with SQL Server PowerShell</span></span>](https://blogs.msdn.com/b/sqlalwayson/archive/2012/02/03/configuring-alwayson-with-sql-server-powershell.aspx)  
  
     [<span data-ttu-id="ae289-198">Blog del team di SQL Server AlwaysOn: Blog ufficiale del team di SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="ae289-198">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="ae289-199">Pagina relativa ai blog del Servizio Supporto Tecnico Clienti per gli ingegneri di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae289-199">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="ae289-200">**Video:**</span><span class="sxs-lookup"><span data-stu-id="ae289-200">**Videos:**</span></span>  
  
     [<span data-ttu-id="ae289-201">Pagina relativa alla prima parte riguardante l'introduzione della soluzione a disponibilità elevata di prossima generazione della serie AlwaysOn di Microsoft SQL Server nome in codice "Denali"</span><span class="sxs-lookup"><span data-stu-id="ae289-201">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="ae289-202">Pagina relativa alla seconda parte riguardante la compilazione di una soluzione a disponibilità elevata critica tramite AlwasyOn della serie AlwaysOn di Microsoft SQL Server nome in codice "Denali"</span><span class="sxs-lookup"><span data-stu-id="ae289-202">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="ae289-203">**White paper:**</span><span class="sxs-lookup"><span data-stu-id="ae289-203">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="ae289-204">Pagina relativa alla guida alle soluzioni AlwaysOn di Microsoft SQL Server per la disponibilità elevata e il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="ae289-204">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="ae289-205">Pagina relativa ai white paper Microsoft per SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ae289-205">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="ae289-206">Pagina relativa ai white paper del team di consulenza clienti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae289-206">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="ae289-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae289-207">See Also</span></span>  
 [<span data-ttu-id="ae289-208">Endpoint del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ae289-208">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)   
