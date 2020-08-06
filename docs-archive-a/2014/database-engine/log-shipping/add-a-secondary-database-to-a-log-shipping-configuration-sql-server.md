---
title: Aggiungere un database secondario a una configurazione per il log shipping (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- adding secondary databases
- secondary databases [SQL Server], in log shipping
- secondary data files [SQL Server], adding
- log shipping [SQL Server], secondary databases
ms.assetid: b02eba13-f8e6-4684-b7e4-75ea038ea473
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 062df1b53ed74321ba0c75c9df763de79a4802bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628954"
---
# <a name="add-a-secondary-database-to-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="ab85a-102">Aggiungere un database secondario a una configurazione per il log shipping (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ab85a-102">Add a Secondary Database to a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="ab85a-103">In questo argomento viene illustrata la procedura per l'aggiunta di un database secondario a una configurazione per il log shipping esistente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab85a-103">This topic describes how to add a secondary database to an existing log shipping configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ab85a-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ab85a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ab85a-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ab85a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ab85a-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ab85a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ab85a-107">**Per aggiungere un database secondario per il log shipping utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="ab85a-107">**To add a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="ab85a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab85a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ab85a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab85a-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="ab85a-110">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="ab85a-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ab85a-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ab85a-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ab85a-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ab85a-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ab85a-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ab85a-113">Permissions</span></span>  
 <span data-ttu-id="ab85a-114">Le stored procedure per il log shipping richiedono l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="ab85a-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ab85a-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab85a-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="ab85a-116">Per aggiungere un database secondario per il log shipping</span><span class="sxs-lookup"><span data-stu-id="ab85a-116">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="ab85a-117">Fare clic con il pulsante destro del mouse sul database che si vuole usare come database primario nella configurazione per il log shipping e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ab85a-117">Right-click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ab85a-118">Nella casella **Selezionare una pagina**fare clic su **Log shipping delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="ab85a-118">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="ab85a-119">In **Istanze del server e database secondari**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ab85a-119">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="ab85a-120">Fare clic su **Connetti** e connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che si intende utilizzare come server secondario.</span><span class="sxs-lookup"><span data-stu-id="ab85a-120">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
5.  <span data-ttu-id="ab85a-121">Nella casella **Database secondario** scegliere un database dall'elenco oppure digitare il nome del database che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="ab85a-121">In the **Secondary database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
6.  <span data-ttu-id="ab85a-122">Nella scheda **Inizializza database secondario** scegliere l'opzione che si intende utilizzare per inizializzare il database secondario.</span><span class="sxs-lookup"><span data-stu-id="ab85a-122">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
7.  <span data-ttu-id="ab85a-123">Nella casella **Cartella di destinazione per i file copiati**della **scheda Copia file** digitare il percorso della cartella nella quale copiare i backup dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ab85a-123">On the **Copy Files tab**, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="ab85a-124">Spesso questa cartella si trova nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="ab85a-124">This folder is often located on the secondary server.</span></span>  
  
8.  <span data-ttu-id="ab85a-125">Si noti la pianificazione di copia presente nella casella **Pianificazione** in **Processo di copia**.</span><span class="sxs-lookup"><span data-stu-id="ab85a-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="ab85a-126">Se si desidera personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione** e quindi modificare la pianificazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in base alle specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="ab85a-126">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="ab85a-127">Questa pianificazione dovrebbe essere abbastanza simile alla pianificazione del backup.</span><span class="sxs-lookup"><span data-stu-id="ab85a-127">This schedule should approximate the backup schedule.</span></span>  
  
9. <span data-ttu-id="ab85a-128">In **Stato del database durante il ripristino dei backup** nella scheda **Ripristino**scegliere l'opzione **Modalità nessun recupero** oppure **Modalità standby** .</span><span class="sxs-lookup"><span data-stu-id="ab85a-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
10. <span data-ttu-id="ab85a-129">Se si sceglie l'opzione **Modalità standby** , scegliere se si desidera disconnettere gli utenti dal database secondario durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="ab85a-129">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
11. <span data-ttu-id="ab85a-130">Se si desidera posticipare il processo di ripristino sul server secondario, scegliere un tempo di ritardo in **Ritardo minimo per il ripristino dei backup**.</span><span class="sxs-lookup"><span data-stu-id="ab85a-130">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
12. <span data-ttu-id="ab85a-131">Scegliere una soglia di avviso in **Invia avviso se il ripristino non viene eseguito entro**.</span><span class="sxs-lookup"><span data-stu-id="ab85a-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
13. <span data-ttu-id="ab85a-132">Si noti la pianificazione di ripristino presente nella casella **Pianificazione** in **Processo di ripristino**.</span><span class="sxs-lookup"><span data-stu-id="ab85a-132">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="ab85a-133">Se si desidera personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione** e quindi modificare la pianificazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in base alle specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="ab85a-133">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="ab85a-134">Questa pianificazione dovrebbe essere abbastanza simile alla pianificazione del backup.</span><span class="sxs-lookup"><span data-stu-id="ab85a-134">This schedule should approximate the backup schedule.</span></span>  
  
14. <span data-ttu-id="ab85a-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab85a-135">Click **OK**.</span></span>  
  
15. <span data-ttu-id="ab85a-136">Fare clic su **OK** nella finestra di dialogo Proprietà database per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ab85a-136">Click **OK** on the Database Properties dialog box to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ab85a-137">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab85a-137">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="ab85a-138">Per aggiungere un database secondario per il log shipping</span><span class="sxs-lookup"><span data-stu-id="ab85a-138">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="ab85a-139">Nel server secondario eseguire [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) specificando i dettagli del server e del database primario.</span><span class="sxs-lookup"><span data-stu-id="ab85a-139">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="ab85a-140">Questa stored procedure restituisce l'ID secondario e gli ID dei processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="ab85a-140">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
2.  <span data-ttu-id="ab85a-141">Nel server secondario eseguire [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) per impostare la pianificazione relativa ai processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="ab85a-141">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="ab85a-142">Nel server secondario eseguire [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) per aggiungere un database secondario.</span><span class="sxs-lookup"><span data-stu-id="ab85a-142">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
4.  <span data-ttu-id="ab85a-143">Nel server primario eseguire [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) per aggiungere le informazioni necessarie relative al nuovo database secondario.</span><span class="sxs-lookup"><span data-stu-id="ab85a-143">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
5.  <span data-ttu-id="ab85a-144">Nel server secondario abilitare i processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="ab85a-144">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="ab85a-145">Per altre informazioni, vedere [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="ab85a-145">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ab85a-146">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="ab85a-146">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ab85a-147">Aggiornare il log shipping a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ab85a-147">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="ab85a-148">Configurare il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ab85a-148">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="ab85a-149">Rimuovere un database secondario da una configurazione per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ab85a-149">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="ab85a-150">Rimuovere il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ab85a-150">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="ab85a-151">Visualizzare il report di log shipping &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ab85a-151">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ab85a-152">Monitorare il log shipping &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ab85a-152">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="ab85a-153">Failover su un database secondario per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ab85a-153">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ab85a-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab85a-154">See Also</span></span>  
 <span data-ttu-id="ab85a-155">[Informazioni sul log shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ab85a-155">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="ab85a-156">Tabelle e stored procedure relative al log shipping</span><span class="sxs-lookup"><span data-stu-id="ab85a-156">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
