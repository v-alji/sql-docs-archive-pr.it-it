---
title: Aggiungere un database a un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 2a54eef8-9e8e-4e04-909c-6970112d55cc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0907cf711cac65ad77a8948841d92705fdc1eac9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624385"
---
# <a name="add-a-database-to-an-availability-group-sql-server"></a><span data-ttu-id="3259f-102">Aggiungere un database a un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3259f-102">Add a Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="3259f-103">In questo argomento viene illustrato come aggiungere un database a un gruppo di disponibilità AlwaysOn utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3259f-103">This topic describes how to add a database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="3259f-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3259f-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3259f-105">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3259f-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="3259f-106">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3259f-106">Permissions</span></span>](#Permissions)  
  
-   <span data-ttu-id="3259f-107">**Per aggiungere un database a un gruppo di disponibilità utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="3259f-107">**To add a database to an availability group, using:**</span></span>  
  
     [<span data-ttu-id="3259f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3259f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3259f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3259f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="3259f-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3259f-110">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3259f-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3259f-111">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="3259f-112">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3259f-112">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="3259f-113">È necessario essere connessi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="3259f-113">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="3259f-114">È necessario che il database risieda nell'istanza del server che ospita la replica primaria e sia conforme ai prerequisiti e alle restrizioni per i database di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="3259f-114">The database must reside on the server instance that hosts the primary replica and comply with the prerequisites and restrictions for availability databases.</span></span> <span data-ttu-id="3259f-115">Per altre informazioni, vedere [Prerequisiti, restrizioni e consigli per i gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="3259f-115">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3259f-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3259f-116">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3259f-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3259f-117">Permissions</span></span>  
 <span data-ttu-id="3259f-118">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="3259f-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3259f-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3259f-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3259f-120">**Per aggiungere un database a un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="3259f-120">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="3259f-121">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="3259f-121">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="3259f-122">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="3259f-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="3259f-123">Fare clic con il pulsante destro del mouse sul gruppo di disponibilità e selezionare uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3259f-123">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="3259f-124">Per avviare la procedura guidata Aggiungi database a gruppo di disponibilità, selezionare il comando **Aggiungi database** .</span><span class="sxs-lookup"><span data-stu-id="3259f-124">To launch the Add Database to Availability Group Wizard, select the **Add Database** command.</span></span> <span data-ttu-id="3259f-125">Per altre informazioni, vedere [Usare la procedura guidata Aggiungi database a gruppo di disponibilità &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md)</span><span class="sxs-lookup"><span data-stu-id="3259f-125">For more information, see [Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span></span>  
  
    -   <span data-ttu-id="3259f-126">Per aggiungere uno o più database specificandoli nella finestra di dialogo **Proprietà gruppo di disponibilità** , selezionare il comando **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="3259f-126">To add one or more databases by specifying them in the **Availability Group Properties** dialog box, select the **Properties** command.</span></span> <span data-ttu-id="3259f-127">Di seguito sono indicati i passaggi per l'aggiunta di un database:</span><span class="sxs-lookup"><span data-stu-id="3259f-127">The steps for adding a database are as follows:</span></span>  
  
        1.  <span data-ttu-id="3259f-128">Nel riquadro **Database di disponibilità** fare clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="3259f-128">In the **Availability Databases** pane, click the **Add** button.</span></span> <span data-ttu-id="3259f-129">Viene creato e selezionato un campo del database vuoto.</span><span class="sxs-lookup"><span data-stu-id="3259f-129">This creates and selects a blank database field.</span></span>  
  
        2.  <span data-ttu-id="3259f-130">Immettere il nome di un database che soddisfi i prerequisiti dei database di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="3259f-130">Enter the name of a database that meets the availability-databases prerequisites.</span></span>  
  
         <span data-ttu-id="3259f-131">Per aggiungere un altro database, ripetere i passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="3259f-131">To add another database, repeat the preceding steps.</span></span> <span data-ttu-id="3259f-132">Dopo avere specificato i database, fare clic su **OK** per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="3259f-132">When you are done specifying databases, click **OK** to complete the operation.</span></span>  
  
         <span data-ttu-id="3259f-133">Dopo avere utilizzato la finestra di dialogo **Proprietà gruppo di disponibilità** per aggiungere un database a un gruppo di disponibilità, è necessario configurare il database secondario corrispondente su ogni istanza del server che ospita una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="3259f-133">After you use the **Availability Group Properties** dialog box to add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="3259f-134">Per altre informazioni, vedere [Avviare lo spostamento dati su un database secondario AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3259f-134">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3259f-135">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3259f-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="3259f-136">**Per aggiungere un database a un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="3259f-136">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="3259f-137">Connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="3259f-137">Connect to the server instance that hosts the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="3259f-138">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3259f-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="3259f-139">ALTER AVAILABILITY GROUP *nome_gruppo* ADD DATABASE *nome_database* [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="3259f-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span></span>  
  
     <span data-ttu-id="3259f-140">dove *nome_gruppo* è il nome del gruppo di disponibilità e *nome_database* è il nome di un database da aggiungere al gruppo.</span><span class="sxs-lookup"><span data-stu-id="3259f-140">where *group_name* is the name of the availability group and *database_name* is the name of a database to be added to the group.</span></span>  
  
     <span data-ttu-id="3259f-141">Nell'esempio seguente viene aggiunto il database *MyDb3* al gruppo di disponibilità *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="3259f-141">The following example adds the *MyDb3* database to the *MyAG* availability group.</span></span>  
  
    ```  
    -- Connect to the server instance that hosts the primary replica.  
    -- Add an existing database to the availability group.  
    ALTER AVAILABILITY GROUP MyAG ADD DATABASE MyDb3;  
    GO  
    ```  
  
3.  <span data-ttu-id="3259f-142">Dopo avere aggiunto un database a un gruppo di disponibilità, è necessario configurare il database secondario corrispondente su ogni istanza del server che ospita una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="3259f-142">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="3259f-143">Per altre informazioni, vedere [Avviare lo spostamento dati su un database secondario AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3259f-143">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="3259f-144">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3259f-144">Using PowerShell</span></span>  
 <span data-ttu-id="3259f-145">**Per aggiungere un database a un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="3259f-145">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="3259f-146">Spostarsi nella directory (`cd`) dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="3259f-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="3259f-147">Utilizzare il cmdlet `Add-SqlAvailabilityDatabase`.</span><span class="sxs-lookup"><span data-stu-id="3259f-147">Use the `Add-SqlAvailabilityDatabase` cmdlet.</span></span>  
  
     <span data-ttu-id="3259f-148">Ad esempio, con il comando seguente viene aggiunto il database secondario `MyDd` al gruppo di disponibilità `MyAG` la cui replica primaria è ospitata da `PrimaryServer\InstanceName`.</span><span class="sxs-lookup"><span data-stu-id="3259f-148">For example, the following command adds the secondary database `MyDd` to the `MyAG` availability group, whose primary replica is hosted by `PrimaryServer\InstanceName`.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase `   
     -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAG `   
     -Database "MyDb"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="3259f-149">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3259f-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="3259f-150">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3259f-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
3.  <span data-ttu-id="3259f-151">Dopo avere aggiunto un database a un gruppo di disponibilità, è necessario configurare il database secondario corrispondente su ogni istanza del server che ospita una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="3259f-151">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="3259f-152">Per altre informazioni, vedere [Avviare lo spostamento dati su un database secondario AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3259f-152">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="3259f-153">Per configurare e usare il provider di SQL Server PowerShell, vedere [provider di SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3259f-153">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>

 <span data-ttu-id="3259f-154">Nel seguente esempio si illustra il processo completo di preparazione di un database secondario da un database nell'istanza del server che ospita la replica primaria di un gruppo di disponibilità, aggiungendo il database a un gruppo di disponibilità (come database primario), quindi creando un join del database secondario al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="3259f-154">The following example shows the full process for preparing a secondary database from a database on the server instance that hosts the primary replica of an availability group, adding the database to an availability group (as a primary database), and then joining the secondary database to the availability group.</span></span> <span data-ttu-id="3259f-155">Nell'esempio si esegue innanzitutto il backup del database e del relativo log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="3259f-155">First, the example backs up the database and its transaction log.</span></span> <span data-ttu-id="3259f-156">Successivamente si ripristinano i backup del database e del log nelle istanze del server che ospitano una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="3259f-156">Then the example restores the database and log backups to the server instances that host a secondary replica.</span></span>  
  
 <span data-ttu-id="3259f-157">Nell'esempio viene chiamato due volte `Add-SqlAvailabilityDatabase`, la prima volta nella replica primaria per aggiungere il database al gruppo di disponibilità, successivamente nella replica secondaria per creare un join del database secondario in quella replica al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="3259f-157">The example calls `Add-SqlAvailabilityDatabase` twice: first on the primary replica to add the database to the availability group, and then on the secondary replica to join the secondary database on that replica to the availability group.</span></span> <span data-ttu-id="3259f-158">Se si dispone di più di una replica secondaria, ripristinare e creare un join del database secondario in ognuna di esse.</span><span class="sxs-lookup"><span data-stu-id="3259f-158">If you have more than one secondary replica, restore and join the secondary database on each of them.</span></span>  
  
```powershell
$DatabaseBackupFile = "\\share\backups\MyDatabase.bak"  
$LogBackupFile = "\\share\backups\MyDatabase.trn"  
$MyAgPrimaryPath = "SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
$MyAgSecondaryPath = "SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAg"  
  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "PrimaryServer\InstanceName"  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "PrimaryServer\InstanceName" -BackupAction 'Log'  
  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "SecondaryServer\InstanceName" -NoRecovery  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "SecondaryServer\InstanceName" -RestoreAction 'Log' -NoRecovery  
  
Add-SqlAvailabilityDatabase -Path $MyAgPrimaryPath -Database "MyDatabase"  
Add-SqlAvailabilityDatabase -Path $MyAgSecondaryPath -Database "MyDatabase"
```  
  
## <a name="see-also"></a><span data-ttu-id="3259f-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3259f-159">See Also</span></span>  
 <span data-ttu-id="3259f-160">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3259f-160">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="3259f-161">[Creazione e configurazione di gruppi di disponibilità &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3259f-161">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="3259f-162">[Usare il dashboard AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3259f-162">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="3259f-163">Monitorare Gruppi di disponibilità &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3259f-163">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
