---
title: Rimuovere un database primario da un gruppo di disponibilità (SQL Server) | Microsoft docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeprimarydb.f1
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 6d4ca31e-ddf0-44bf-be5e-a5da060bf096
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6fafaf6464431d68f8cfdf9dc9d8fa844a42a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626311"
---
# <a name="remove-a-primary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="9ee75-102">Rimuovere un database primario da un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9ee75-102">Remove a Primary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="9ee75-103">In questo argomento viene illustrato come rimuovere il database primario e il database o i database secondari corrispondenti da un gruppo di disponibilità AlwaysOn tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ee75-103">This topic describes how to remove both the primary database and the corresponding secondary database(s) from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="9ee75-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="9ee75-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9ee75-105">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="9ee75-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="9ee75-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9ee75-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9ee75-107">**Per rimuovere un database di disponibilità utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="9ee75-107">**To remove an availability database, using:**</span></span>  
  
     [<span data-ttu-id="9ee75-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ee75-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9ee75-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ee75-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="9ee75-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ee75-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="9ee75-111">**Completamento:**  [Dopo la rimozione di un database di disponibilità da un gruppo di disponibilità](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="9ee75-111">**Follow Up:**  [After Removing an Availability Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9ee75-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9ee75-112">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="9ee75-113">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="9ee75-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="9ee75-114">Questa attività può essere eseguita solo sulle repliche primarie.</span><span class="sxs-lookup"><span data-stu-id="9ee75-114">This task is supported only on primary replicas.</span></span> <span data-ttu-id="9ee75-115">È necessario essere connessi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="9ee75-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9ee75-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9ee75-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9ee75-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="9ee75-117">Permissions</span></span>  
 <span data-ttu-id="9ee75-118">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="9ee75-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9ee75-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ee75-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9ee75-120">**Per rimuovere un database di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="9ee75-120">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="9ee75-121">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria del database o dei database da rimuovere ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="9ee75-121">In Object Explorer, connect to the server instance that hosts the primary replica of the database or databases to be removed, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9ee75-122">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="9ee75-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="9ee75-123">Selezionare il gruppo di disponibilità ed espandere il nodo **Database di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="9ee75-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="9ee75-124">Questo passaggio dipende dalla scelta di rimuovere uno o più database:</span><span class="sxs-lookup"><span data-stu-id="9ee75-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="9ee75-125">Per rimuovere più database, utilizzare il riquadro **Dettagli Esplora oggetti** per visualizzare e selezionare tutti i database che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="9ee75-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="9ee75-126">Per altre informazioni, vedere [Utilizzare Dettagli Esplora oggetti per monitorare Gruppi di disponibilità &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9ee75-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="9ee75-127">Per rimuovere un singolo database, selezionarlo nel riquadro **Esplora oggetti** o **Dettagli Esplora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="9ee75-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="9ee75-128">Fare clic con il pulsante destro del mouse sul database o sui database selezionati e scegliere **Rimuovere il database dal gruppo di disponibilità** nel menu dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9ee75-128">Right-click the selected database or databases, and select **Remove Database from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="9ee75-129">Nella finestra di dialogo **Rimuovi i database dal gruppo di disponibilità** scegliere **OK**per rimuovere tutti i database elencati.</span><span class="sxs-lookup"><span data-stu-id="9ee75-129">In the **Remove Databases from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="9ee75-130">Se non si desidera rimuoverli tutti, scegliere **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="9ee75-130">If you do not want to remove all them, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9ee75-131">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ee75-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="9ee75-132">**Per rimuovere un database di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="9ee75-132">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="9ee75-133">Connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="9ee75-133">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="9ee75-134">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ee75-134">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="9ee75-135">ALTER AVAILABILITY GROUP *group_name* REMOVE DATABASE *availability_database_name*</span><span class="sxs-lookup"><span data-stu-id="9ee75-135">ALTER AVAILABILITY GROUP *group_name* REMOVE DATABASE *availability_database_name*</span></span>  
  
     <span data-ttu-id="9ee75-136">dove *group_name* è il nome del gruppo di disponibilità e *database_name* è il nome di un database da aggiungere al gruppo.</span><span class="sxs-lookup"><span data-stu-id="9ee75-136">where *group_name* is the name of the availability group and *database_name* is the name of the database to be removed.</span></span>  
  
     <span data-ttu-id="9ee75-137">Nell'esempio seguente viene rimosso un database denominato `Db6` dal gruppo di disponibilità `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="9ee75-137">The following example removes a databases named `Db6` from the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE DATABASE Db6;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9ee75-138">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ee75-138">Using PowerShell</span></span>  
 <span data-ttu-id="9ee75-139">**Per rimuovere un database di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="9ee75-139">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="9ee75-140">Spostarsi nella directory (`cd`) dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="9ee75-140">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="9ee75-141">Utilizzare il `Remove-SqlAvailabilityDatabase` specificando il nome del database di disponibilità da rimuovere dal gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="9ee75-141">Use the `Remove-SqlAvailabilityDatabase` cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="9ee75-142">Quando si è connessi all'istanza del server che ospita la replica primaria, il database primario e i database secondari corrispondenti vengono tutti rimossi dal gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="9ee75-142">When you are connected to the server instance that hosts the primary replica, the primary database and its corresponding secondary databases are all removed from the availability group.</span></span>  
  
     <span data-ttu-id="9ee75-143">Ad esempio, il seguente comando rimuove il database di disponibilità `MyDb9` dal gruppo di disponibilità denominato `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="9ee75-143">For example, the following command removes the availability database `MyDb9` from the availability group named `MyAg`.</span></span> <span data-ttu-id="9ee75-144">Dal momento che il comando viene eseguito nell'istanza del server che ospita la replica primaria, il database primario e tutti i relativi database secondari corrispondenti vengono rimossi dal gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="9ee75-144">Because the command is executed on the server instance that hosts the primary replica, the primary database and all its corresponding secondary databases are removed from the availability group.</span></span> <span data-ttu-id="9ee75-145">La sincronizzazione dei dati non verrà più eseguita per questo database in nessuna replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="9ee75-145">Data synchronization will no longer occur for this database on any secondary replica.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\PrimaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb9  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="9ee75-146">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ee75-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="9ee75-147">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9ee75-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="9ee75-148">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9ee75-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="9ee75-149">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ee75-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-an-availability-database-from-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="9ee75-150">Completamento: dopo la rimozione di un database di disponibilità da un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="9ee75-150">Follow Up: After Removing an Availability Database from an Availability Group</span></span>  
 <span data-ttu-id="9ee75-151">La rimozione di un database di disponibilità dal relativo gruppo di disponibilità termina la sincronizzazione dati tra il database primario precedente e i database secondari corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="9ee75-151">Removing an availability database from its availability group ends data synchronization between the former primary database and the corresponding secondary databases.</span></span> <span data-ttu-id="9ee75-152">Il database primario precedente rimane online.</span><span class="sxs-lookup"><span data-stu-id="9ee75-152">The former primary database remains online.</span></span> <span data-ttu-id="9ee75-153">Ogni database secondario corrispondente viene posto nello stato RESTORING.</span><span class="sxs-lookup"><span data-stu-id="9ee75-153">Every corresponding secondary database is placed in the RESTORING state.</span></span>  
  
 <span data-ttu-id="9ee75-154">A questo punto sono disponibili modi alternativi per gestire un database secondario rimosso:</span><span class="sxs-lookup"><span data-stu-id="9ee75-154">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="9ee75-155">Se un determinato database secondario non è più necessario, è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="9ee75-155">If you no longer need a given secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="9ee75-156">Per altre informazioni, vedere [Eliminare un database](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="9ee75-156">For more information, see [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="9ee75-157">Se si desidera accedere a un database secondario dopo che è stato rimosso dal gruppo di disponibilità, è possibile recuperare il database.</span><span class="sxs-lookup"><span data-stu-id="9ee75-157">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="9ee75-158">Tuttavia, se si recupera un database secondario rimosso, saranno online due database indipendenti e divergenti con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="9ee75-158">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="9ee75-159">È necessario assicurarsi che i client possano accedere a uno solo di essi, di solito al database primario più recente.</span><span class="sxs-lookup"><span data-stu-id="9ee75-159">You must make sure that clients can access only one of them, typically the most recent primary database.</span></span>  
  
     <span data-ttu-id="9ee75-160">Per altre informazioni, vedere [Recupero di un database senza ripristino dei dati &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9ee75-160">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee75-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ee75-161">See Also</span></span>  
 <span data-ttu-id="9ee75-162">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ee75-162">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="9ee75-163">Rimuovere un database secondario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ee75-163">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
