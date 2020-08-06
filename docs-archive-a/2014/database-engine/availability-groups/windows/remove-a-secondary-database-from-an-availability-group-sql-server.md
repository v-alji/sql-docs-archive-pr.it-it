---
title: Rimuovere un database secondario da un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.unjoindb.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], databases
ms.assetid: 4e51a570-58d7-4f01-9390-4198f3602576
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1c3de0afd73b46ae5594d26d1763f5bd78483efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626309"
---
# <a name="remove-a-secondary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="12d5c-102">Rimuovere un database secondario da un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="12d5c-102">Remove a Secondary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="12d5c-103">In questo argomento viene illustrato come rimuovere un database secondario da un gruppo di disponibilità AlwaysOn utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12d5c-103">This topic describes how to remove a secondary database from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="12d5c-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="12d5c-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="12d5c-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="12d5c-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="12d5c-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="12d5c-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="12d5c-107">**Per rimuovere un database secondario tramite:**</span><span class="sxs-lookup"><span data-stu-id="12d5c-107">**To remove a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="12d5c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="12d5c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="12d5c-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12d5c-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="12d5c-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="12d5c-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="12d5c-111">**Completamento:**  [Dopo la rimozione di un database secondario da un gruppo di disponibilità](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="12d5c-111">**Follow Up:**  [After Removing a Secondary Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="12d5c-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="12d5c-112">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>   
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="12d5c-113">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="12d5c-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="12d5c-114">Questa attività è supportata solo sulle repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="12d5c-114">This task is supported only on secondary replicas.</span></span> <span data-ttu-id="12d5c-115">È necessario essere connessi all'istanza del server che ospita la replica secondaria da cui verrà rimosso il database.</span><span class="sxs-lookup"><span data-stu-id="12d5c-115">You must be connected to the server instance that hosts the secondary replica from which the database is to be removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="12d5c-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="12d5c-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="12d5c-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="12d5c-117">Permissions</span></span>  
 <span data-ttu-id="12d5c-118">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="12d5c-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="12d5c-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="12d5c-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="12d5c-120">**Per rimuovere un database secondario da un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="12d5c-120">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="12d5c-121">In Esplora oggetti connettersi all'istanza del server che ospita la replica secondaria da cui si desidera rimuovere uno o più database secondari ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="12d5c-121">In Object Explorer, connect to the server instance that hosts the secondary replica from which you want to remove one or more secondary databases, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="12d5c-122">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="12d5c-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="12d5c-123">Selezionare il gruppo di disponibilità ed espandere il nodo **Database di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="12d5c-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="12d5c-124">Questo passaggio dipende dalla scelta di rimuovere uno o più database:</span><span class="sxs-lookup"><span data-stu-id="12d5c-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="12d5c-125">Per rimuovere più database, utilizzare il riquadro **Dettagli Esplora oggetti** per visualizzare e selezionare tutti i database che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="12d5c-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="12d5c-126">Per altre informazioni, vedere [Utilizzare Dettagli Esplora oggetti per monitorare Gruppi di disponibilità &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="12d5c-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="12d5c-127">Per rimuovere un singolo database, selezionarlo nel riquadro **Esplora oggetti** o **Dettagli Esplora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="12d5c-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="12d5c-128">Fare clic con il pulsante destro del mouse sul database o sui database selezionati e scegliere **Rimuovi database secondario** nel menu dei comandi.</span><span class="sxs-lookup"><span data-stu-id="12d5c-128">Right-click the selected database or databases, and select **Remove Secondary Database** in the command menu.</span></span>  
  
6.  <span data-ttu-id="12d5c-129">Nella finestra di dialogo **Rimuovi database dal gruppo di disponibilità** scegliere **OK**per rimuovere tutti i database elencati.</span><span class="sxs-lookup"><span data-stu-id="12d5c-129">In the **Remove Database from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="12d5c-130">Se non si desidera rimuovere tutti i database elencati, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="12d5c-130">If you do not want to remove all the listed databases, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="12d5c-131">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12d5c-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="12d5c-132">**Per rimuovere un database secondario da un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="12d5c-132">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="12d5c-133">Connettersi all'istanza del server che ospita la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="12d5c-133">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="12d5c-134">Utilizzare la [clausola SET HADR dell'istruzione ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="12d5c-134">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="12d5c-135">ALTER DATABASE *nome_database* SET HADR OFF</span><span class="sxs-lookup"><span data-stu-id="12d5c-135">ALTER DATABASE *database_name* SET HADR OFF</span></span>  
  
     <span data-ttu-id="12d5c-136">dove *nome_database* è il nome di un database secondario da rimuovere dal gruppo di disponibilità a cui appartiene.</span><span class="sxs-lookup"><span data-stu-id="12d5c-136">where *database_name* is the name of a secondary database to be removed from the availability group to which it belongs.</span></span>  
  
     <span data-ttu-id="12d5c-137">L'esempio seguente mostra come rimuovere il database secondario locale *MyDb2* dal relativo gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="12d5c-137">The following example removes the local secondary database *MyDb2* from its availability group.</span></span>  
  
    ```sql
    ALTER DATABASE MyDb2 SET HADR OFF;  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="12d5c-138">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="12d5c-138">Using PowerShell</span></span>  
 <span data-ttu-id="12d5c-139">**Per rimuovere un database secondario da un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="12d5c-139">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="12d5c-140">Impostare la directory (`cd`) sull'istanza del server in cui viene ospitata la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="12d5c-140">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="12d5c-141">Usare il cmdlet **Remove-SqlAvailabilityDatabase** specificando il nome del database di disponibilità da rimuovere dal gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="12d5c-141">Use the **Remove-SqlAvailabilityDatabase** cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="12d5c-142">Quando si è connessi a un'istanza del server che ospita una replica secondaria, solo il database secondario locale verrà rimosso dal gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="12d5c-142">When you are connected to a server instance that hosts a secondary replica, only the local secondary database is removed from the availability group.</span></span>  
  
     <span data-ttu-id="12d5c-143">Ad esempio, il comando seguente rimuove il database secondario `MyDb8` dalla replica secondaria ospitata dall'istanza del server denominata `SecondaryComputer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="12d5c-143">For example, the following command removes the secondary database `MyDb8` from the secondary replica hosted by the server instance named `SecondaryComputer\Instance`.</span></span> <span data-ttu-id="12d5c-144">La sincronizzazione dei dati con i database secondari rimossi viene terminata.</span><span class="sxs-lookup"><span data-stu-id="12d5c-144">Data synchronization to the removed secondary databases ceases.</span></span> <span data-ttu-id="12d5c-145">Questo comando non influisce sul database primario né su nessun altro database secondario.</span><span class="sxs-lookup"><span data-stu-id="12d5c-145">This command does not affect the primary database or any other secondary databases.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\SecondaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb8  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="12d5c-146">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12d5c-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="12d5c-147">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="12d5c-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="12d5c-148">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="12d5c-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="12d5c-149">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="12d5c-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-database-from-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="12d5c-150">Completamento: dopo la rimozione di un database secondario da un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="12d5c-150">Follow Up: After Removing a Secondary Database from an Availability Group</span></span>  
 <span data-ttu-id="12d5c-151">Quando un database secondario viene rimosso, non è più unito in join al gruppo di disponibilità e tutte le informazioni relative al database secondario rimosso vengono ignorate dal gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="12d5c-151">When a secondary database is removed, it is no longer joined to the availability group and all information about the removed secondary database is discarded by the availability group.</span></span> <span data-ttu-id="12d5c-152">Il database secondario rimosso viene posto nello stato RESTORING.</span><span class="sxs-lookup"><span data-stu-id="12d5c-152">The removed secondary database is placed in the RESTORING state.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="12d5c-153">Per un breve intervallo di tempo dopo avere rimosso un database secondario, è possibile riavviare la sincronizzazione dei dati AlwaysOn sul database creando nuovamente un join al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="12d5c-153">For a short time after removing a secondary database, you might be able to restart AlwaysOn data synchronization on the database by re-joining it to the availability group.</span></span> <span data-ttu-id="12d5c-154">Per altre informazioni, vedere [Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="12d5c-154">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="12d5c-155">A questo punto sono disponibili modi alternativi per gestire un database secondario rimosso:</span><span class="sxs-lookup"><span data-stu-id="12d5c-155">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="12d5c-156">Se il database secondario non è più necessario, è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="12d5c-156">If you no longer need the secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="12d5c-157">Per altre informazioni, vedere [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) o [Eliminare un database](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="12d5c-157">For more information, see [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) or [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="12d5c-158">Se si desidera accedere a un database secondario dopo che è stato rimosso dal gruppo di disponibilità, è possibile recuperare il database.</span><span class="sxs-lookup"><span data-stu-id="12d5c-158">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="12d5c-159">Tuttavia, se si recupera un database secondario rimosso, saranno online due database indipendenti e divergenti con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="12d5c-159">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="12d5c-160">È necessario assicurarsi che i client possano accedere solo al database primario corrente.</span><span class="sxs-lookup"><span data-stu-id="12d5c-160">You must make sure that clients can access only the current primary database.</span></span>  
  
     <span data-ttu-id="12d5c-161">Per altre informazioni, vedere [Recupero di un database senza ripristino dei dati &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="12d5c-161">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d5c-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12d5c-162">See Also</span></span>  
 <span data-ttu-id="12d5c-163">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="12d5c-163">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="12d5c-164">Rimuovere un database primario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="12d5c-164">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
