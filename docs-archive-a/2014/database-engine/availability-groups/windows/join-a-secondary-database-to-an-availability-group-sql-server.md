---
title: Creare un join di un database secondario a un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joindbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: fd7efe79-c1f9-497d-bfe7-b2a2b2321cf5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0d79325bcde33d13688003de079a42a9601cc41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627974"
---
# <a name="join-a-secondary-database-to-an-availability-group-sql-server"></a><span data-ttu-id="7ead9-102">Creare un join di un database secondario a un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7ead9-102">Join a Secondary Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="7ead9-103">In questo argomento si spiega come creare un join di un database secondario a un gruppo di disponibilità AlwaysOn utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ead9-103">This topic explains how to join a secondary database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="7ead9-104">Dopo aver preparato un database secondario per una replica di secondaria, è necessario creare un join del database al gruppo di disponibilità non appena possibile.</span><span class="sxs-lookup"><span data-stu-id="7ead9-104">After you prepare a secondary database for a secondary replica, you need to join the database to the availability group as soon as possible.</span></span> <span data-ttu-id="7ead9-105">In questo modo verrà avviato lo spostamento di dati dal database primario corrispondente al database secondario.</span><span class="sxs-lookup"><span data-stu-id="7ead9-105">This will start data movement from the corresponding primary database to the secondary database.</span></span>  
  
-   <span data-ttu-id="7ead9-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="7ead9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7ead9-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7ead9-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="7ead9-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7ead9-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7ead9-109">**Per preparare un database secondario tramite:**</span><span class="sxs-lookup"><span data-stu-id="7ead9-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="7ead9-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ead9-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7ead9-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ead9-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="7ead9-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ead9-112">PowerShell</span></span>](#PowerShellProcedure)  
  
> [!NOTE]  
>  <span data-ttu-id="7ead9-113">Per informazioni sulle operazioni eseguite dopo l'aggiunta di un database secondario al gruppo, vedere [Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ead9-113">For information about what happens after a secondary database joins the group, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7ead9-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7ead9-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7ead9-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7ead9-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="7ead9-116">È necessario essere connessi all'istanza del server che ospita la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="7ead9-116">You must be connected to the server instance that hosts the secondary replica.</span></span>  
  
-   <span data-ttu-id="7ead9-117">È necessario avere già creato un join della replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="7ead9-117">The secondary replica must already be joined to the availability group.</span></span> <span data-ttu-id="7ead9-118">Per altre informazioni, vedere [Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ead9-118">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
-   <span data-ttu-id="7ead9-119">Il database secondario deve essere stato preparato recentemente.</span><span class="sxs-lookup"><span data-stu-id="7ead9-119">The secondary database must have been prepared recently.</span></span> <span data-ttu-id="7ead9-120">Per altre informazioni, vedere [Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ead9-120">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7ead9-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7ead9-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7ead9-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7ead9-122">Permissions</span></span>  
 <span data-ttu-id="7ead9-123">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="7ead9-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7ead9-124">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ead9-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7ead9-125">**Per creare un join di un database secondario a un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="7ead9-125">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="7ead9-126">In Esplora oggetti connettersi all'istanza del server in cui viene ospitata la replica secondaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="7ead9-126">In Object Explorer, connect to the server instance that hosts the secondary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="7ead9-127">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="7ead9-127">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="7ead9-128">Espandere il gruppo di disponibilità che si desidera modificare, quindi espandere il nodo **Database disponibili** .</span><span class="sxs-lookup"><span data-stu-id="7ead9-128">Expand the availability group that you want to change, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="7ead9-129">Fare clic con il pulsante destro del mouse sul database e scegliere **Crea un join del gruppo di disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="7ead9-129">Right-click the database, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="7ead9-130">In questo modo verrà aperta la finestra di dialogo **Creare un join dei database al gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="7ead9-130">This opens the **Join Databases to Availability Group** dialog box.</span></span> <span data-ttu-id="7ead9-131">Verificare il nome del gruppo di disponibilità, visualizzato sulla barra del titolo, e il nome o i nomi dei database visualizzati nella griglia, quindi fare clic su **OK**o su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="7ead9-131">Verify the availability group name, which is displayed on the title bar, and database name or names displayed in the grid, and click **OK**, or click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7ead9-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ead9-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="7ead9-133">**Per creare un join di un database secondario a un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="7ead9-133">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="7ead9-134">Connettersi all'istanza del server che ospita la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="7ead9-134">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="7ead9-135">Utilizzare la [clausola SET HADR dell'istruzione ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7ead9-135">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="7ead9-136">ALTER DATABASE *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span><span class="sxs-lookup"><span data-stu-id="7ead9-136">ALTER DATABASE *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>  
  
     <span data-ttu-id="7ead9-137">dove *database_name* è il nome del database di cui creare il join e *group_name* è il nome del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="7ead9-137">where *database_name* is the name of a database to be joined and *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="7ead9-138">Nell'esempio seguente viene creato un join del database secondario, `Db1`, alla replica secondaria locale del gruppo di disponibilità `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="7ead9-138">The following example joins the secondary database, `Db1`, to the local secondary replica of the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER DATABASE Db1 SET HADR AVAILABILITY GROUP = MyAG;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ead9-139">Per un esempio di questa istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] impiegata in un contesto, vedere [Creare un gruppo di disponibilità &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7ead9-139">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="7ead9-140">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ead9-140">Using PowerShell</span></span>  
 <span data-ttu-id="7ead9-141">**Per creare un join di un database secondario a un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="7ead9-141">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="7ead9-142">Impostare la directory (`cd`) sull'istanza del server in cui viene ospitata la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="7ead9-142">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="7ead9-143">Utilizzare il cmdlet `Add-SqlAvailabilityDatabase` per creare un join di uno o più database secondari al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="7ead9-143">Use the `Add-SqlAvailabilityDatabase` cmdlet to join one or more secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="7ead9-144">Ad esempio, il seguente comando crea un join di un database secondario, `Db1`, al gruppo di disponibilità `MyAG` in una delle istanze del server che ospita una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="7ead9-144">For example, the following command joins a secondary database, `Db1`, to the availability group `MyAG` on one of the server instances that hosts a secondary replica.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase -Path SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAG -Database "Db1"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ead9-145">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ead9-145">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="7ead9-146">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="7ead9-146">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="7ead9-147">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="7ead9-147">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="7ead9-148">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ead9-148">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7ead9-149">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7ead9-149">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7ead9-150">Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ead9-150">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="7ead9-151">Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ead9-151">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ead9-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ead9-152">See Also</span></span>  
 <span data-ttu-id="7ead9-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7ead9-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="7ead9-154">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ead9-154">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="7ead9-155">Risolvere i problemi di Gruppi di disponibilità AlwaysOn &#40;di configurazione SQL Server eliminati&#41;</span><span class="sxs-lookup"><span data-stu-id="7ead9-155">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
