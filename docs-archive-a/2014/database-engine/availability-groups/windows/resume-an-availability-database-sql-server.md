---
title: Riprendere un database di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.resumedatamove.f1
helpviewer_keywords:
- Availability Groups [SQL Server], resuming a database
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], databases
ms.assetid: 20e9147b-e985-4caa-910e-fc4b38dbf9a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a2279940c2502a310e9dac4448bd6029b6e13dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724216"
---
# <a name="resume-an-availability-database-sql-server"></a><span data-ttu-id="5e358-102">Riprendere un database di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5e358-102">Resume an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="5e358-103">In [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] è possibile riprendere un database di disponibilità sospeso utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e358-103">You can resume a suspended availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="5e358-104">Quando si riprende un database sospeso, viene attivato lo stato SYNCHRONIZING per il database.</span><span class="sxs-lookup"><span data-stu-id="5e358-104">Resuming a suspended database puts the database into the SYNCHRONIZING state.</span></span> <span data-ttu-id="5e358-105">Con la ripresa del database primario vengono inoltre ripresi anche eventuali database secondari sospesi in seguito alla sospensione del database primario.</span><span class="sxs-lookup"><span data-stu-id="5e358-105">Resuming the primary database also resumes any of its secondary databases that were suspended as the result of suspending the primary database.</span></span> <span data-ttu-id="5e358-106">Se un database secondario è stato sospeso in locale, dall'istanza del server che ospita la replica secondaria, è necessario riprendere tale database secondario in locale.</span><span class="sxs-lookup"><span data-stu-id="5e358-106">If any secondary database was suspended locally, from the server instance that hosts the secondary replica, that secondary database must be resumed locally.</span></span> <span data-ttu-id="5e358-107">Quando un database secondario e il database primario corrispondente sono nello stato SYNCHRONIZING, la sincronizzazione dei dati viene ripresa nel database secondario.</span><span class="sxs-lookup"><span data-stu-id="5e358-107">Once a given secondary database and the corresponding primary database are in the SYNCHRONIZING state, data synchronization resumes on the secondary database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e358-108">La sospensione e la ripresa di un database secondario AlwaysOn non incide direttamente sulla disponibilità del database primario.</span><span class="sxs-lookup"><span data-stu-id="5e358-108">Suspending and resuming an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="5e358-109">Tuttavia, la sospensione di un database secondario può avere un impatto sulle funzionalità di ridondanza e failover del database primario, finché il database secondario sospeso non viene ripreso.</span><span class="sxs-lookup"><span data-stu-id="5e358-109">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database, until the suspended secondary database is resumed.</span></span> <span data-ttu-id="5e358-110">Questo comportamento è diverso rispetto al mirroring del database, in cui lo stato del mirroring risulta sospeso sia sul database mirror che sul database principale, finché il mirroring non viene ripreso.</span><span class="sxs-lookup"><span data-stu-id="5e358-110">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database until mirroring is resumed.</span></span> <span data-ttu-id="5e358-111">La sospensione di un database primario AlwaysOn comporta la sospensione dello spostamento di dati su tutti i database secondari corrispondenti, mentre le funzionalità di ridondanza e failover cessano per tale database finché il database primario non viene ripreso.</span><span class="sxs-lookup"><span data-stu-id="5e358-111">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="5e358-112">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5e358-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5e358-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5e358-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5e358-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5e358-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="5e358-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5e358-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5e358-116">**Per riprendere un database secondario tramite:**</span><span class="sxs-lookup"><span data-stu-id="5e358-116">**To resume a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="5e358-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e358-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5e358-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e358-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="5e358-119">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e358-119">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="5e358-120">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="5e358-120">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5e358-121">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5e358-121">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5e358-122">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5e358-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5e358-123">Un comando RESUME viene restituito non appena è stato accettato dalla replica che ospita il database di destinazione, ma la ripresa effettiva del database avviene in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="5e358-123">A RESUME command returns as soon as it has been accepted by the replica that hosts the target database, but actually resuming the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="5e358-124">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5e358-124">Prerequisites</span></span>  
  
-   <span data-ttu-id="5e358-125">È necessario essere connessi all'istanza del server che ospita il database da riprendere.</span><span class="sxs-lookup"><span data-stu-id="5e358-125">You must be connected to the server instance that hosts the database to be resumed.</span></span>  
  
-   <span data-ttu-id="5e358-126">Il gruppo di disponibilità deve essere online.</span><span class="sxs-lookup"><span data-stu-id="5e358-126">The availability group must be online.</span></span>  
  
-   <span data-ttu-id="5e358-127">Il database primario deve essere online e disponibile.</span><span class="sxs-lookup"><span data-stu-id="5e358-127">The primary database must be online and available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5e358-128">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5e358-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5e358-129">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5e358-129">Permissions</span></span>  
 <span data-ttu-id="5e358-130">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="5e358-130">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="5e358-131">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="5e358-131">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5e358-132">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e358-132">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5e358-133">**Per riprendere un database secondario**</span><span class="sxs-lookup"><span data-stu-id="5e358-133">**To resume a secondary database**</span></span>  
  
1.  <span data-ttu-id="5e358-134">In Esplora oggetti connettersi all'istanza del server che ospita la replica di disponibilità in cui si desidera riprendere un database ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="5e358-134">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to resume a database, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="5e358-135">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="5e358-135">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="5e358-136">Espandere il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="5e358-136">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="5e358-137">Espandere il nodo **Database di disponibilità** , fare clic con il pulsante destro del mouse sul database e fare clic su **Riprendi spostamento dati**.</span><span class="sxs-lookup"><span data-stu-id="5e358-137">Expand the **Availability Databases** node, right-click the database, and click **Resume Data Movement**.</span></span>  
  
5.  <span data-ttu-id="5e358-138">Nella finestra di dialogo **Riprendi spostamento dati** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e358-138">In the **Resume Data Movement** dialog box, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e358-139">Per riprendere database aggiuntivi in questo percorso di replica, ripetere i passaggi 4 e 5 per ogni database.</span><span class="sxs-lookup"><span data-stu-id="5e358-139">To resume additional databases on this replica location, repeat steps 4 and 5 for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5e358-140">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e358-140">Using Transact-SQL</span></span>  
 <span data-ttu-id="5e358-141">**Per riprendere un database secondario sospeso in locale**</span><span class="sxs-lookup"><span data-stu-id="5e358-141">**To resume a secondary database that was suspended locally**</span></span>  
  
1.  <span data-ttu-id="5e358-142">Connettersi all'istanza del server che ospita la replica secondaria di cui si desidera riprendere il database.</span><span class="sxs-lookup"><span data-stu-id="5e358-142">Connect to the server instance that hosts the secondary replica whose database you want to resume.</span></span>  
  
2.  <span data-ttu-id="5e358-143">Riprendere il database secondario usando l'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)seguente:</span><span class="sxs-lookup"><span data-stu-id="5e358-143">Resume the secondary database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="5e358-144">ALTER DATABASE *database_name* SET HADR Resume</span><span class="sxs-lookup"><span data-stu-id="5e358-144">ALTER DATABASE *database_name* SET HADR RESUME</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="5e358-145">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e358-145">Using PowerShell</span></span>  

### <a name="to-resume-a-secondary-database"></a><span data-ttu-id="5e358-146">Per riprendere un database secondario</span><span class="sxs-lookup"><span data-stu-id="5e358-146">To resume a secondary database</span></span>
  
1.  <span data-ttu-id="5e358-147">Impostare la directory (`cd`) sull'istanza del server che ospita la replica di cui si desidera riprendere il database.</span><span class="sxs-lookup"><span data-stu-id="5e358-147">Change directory (`cd`) to the server instance that hosts the replica whose database you want to resume.</span></span> <span data-ttu-id="5e358-148">Per altre informazioni, vedere la sessione [Prerequisiti](#Prerequisites)più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5e358-148">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="5e358-149">Usare il cmdlet **Resume-SqlAvailabilityDatabase** per riprendere il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="5e358-149">Use the **Resume-SqlAvailabilityDatabase** cmdlet to resume the availability group.</span></span>  
  
     <span data-ttu-id="5e358-150">Ad esempio, il seguente comando riprende la sincronizzazione dati per il database di disponibilità `MyDb3` nel gruppo di disponibilità `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="5e358-150">For example, the following command resumes data synchronization for the availability database `MyDb3` in the availability group `MyAg`.</span></span>  
  
    ```powershell
    Resume-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="5e358-151">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e358-151">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="5e358-152">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5e358-152">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="5e358-153">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5e358-153">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="5e358-154">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="5e358-154">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5e358-155">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="5e358-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="5e358-156">Sospendere un database di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5e358-156">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="5e358-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e358-157">See Also</span></span>  
 [<span data-ttu-id="5e358-158">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5e358-158">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
