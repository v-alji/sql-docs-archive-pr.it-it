---
title: Disattivare il log shipping [SQL Server] | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], removing
- removing log shipping
- deleting log shipping
ms.assetid: 859373db-c744-4a4b-8479-45163f61e8cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 14fdc36c66073e89dcc2014aed4319a2ce78a98f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628953"
---
# <a name="remove-log-shipping-sql-server"></a><span data-ttu-id="fc5b2-102">Disattivare il log shipping [SQL Server]</span><span class="sxs-lookup"><span data-stu-id="fc5b2-102">Remove Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="fc5b2-103">In questo argomento viene descritto come rimuovere il log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc5b2-103">This topic describes how to remove log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fc5b2-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="fc5b2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fc5b2-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="fc5b2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fc5b2-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fc5b2-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fc5b2-107">**Per rimuovere il log shipping utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="fc5b2-107">**To remove log shipping, using:**</span></span>  
  
     [<span data-ttu-id="fc5b2-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fc5b2-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fc5b2-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fc5b2-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="fc5b2-110">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="fc5b2-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fc5b2-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="fc5b2-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fc5b2-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fc5b2-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fc5b2-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="fc5b2-113">Permissions</span></span>  
 <span data-ttu-id="fc5b2-114">Le stored procedure per il log shipping richiedono l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="fc5b2-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fc5b2-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fc5b2-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="fc5b2-116">Per rimuovere il log shipping</span><span class="sxs-lookup"><span data-stu-id="fc5b2-116">To remove log shipping</span></span>  
  
1.  <span data-ttu-id="fc5b2-117">Connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che rappresenta attualmente il server primario di log shipping ed espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="fc5b2-118">Espandere **Database**, fare clic con il pulsante destro del mouse sul database primario per il log shipping, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="fc5b2-119">Nella casella **Selezionare una pagina**fare clic su **Log shipping delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="fc5b2-120">Deselezionare la casella di controllo **Abilita come database primario in una configurazione per il log shipping** .</span><span class="sxs-lookup"><span data-stu-id="fc5b2-120">Clear the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
5.  <span data-ttu-id="fc5b2-121">Fare clic su **OK** per rimuovere il log shipping dal database primario.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-121">Click **OK** to remove log shipping from this primary database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fc5b2-122">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fc5b2-122">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="fc5b2-123">Per rimuovere il log shipping</span><span class="sxs-lookup"><span data-stu-id="fc5b2-123">To Remove Log Shipping</span></span>  
  
1.  <span data-ttu-id="fc5b2-124">Nel server primario di log shipping eseguire [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) per eliminare le informazioni relative al database secondario.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-124">On the log shipping primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="fc5b2-125">Nel server secondario di log shipping eseguire [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) per eliminare il database secondario.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-125">On the log shipping secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fc5b2-126">Se non sono disponibili altri database secondari con lo stesso ID secondario, **sp_delete_log_shipping_secondary_primary** viene richiamata da **sp_delete_log_shipping_secondary_database** e tramite essa vengono eliminati la voce relativa all'ID secondario e i processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-126">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="fc5b2-127">Nel server primario di log shipping eseguire **sp_delete_log_shipping_primary_database** per eliminare le informazioni relative alla configurazione per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-127">On the log shipping primary server, execute **sp_delete_log_shipping_primary_database** to delete information about the log shipping configuration from the primary server.</span></span> <span data-ttu-id="fc5b2-128">In questo modo verrà eliminato anche il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-128">This also deletes the backup job.</span></span>  
  
4.  <span data-ttu-id="fc5b2-129">Nel server primario di log shipping disabilitare il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-129">On the log shipping primary server, disable the backup job.</span></span> <span data-ttu-id="fc5b2-130">Per altre informazioni, vedere [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="fc5b2-130">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
5.  <span data-ttu-id="fc5b2-131">Nel server secondario di log shipping disabilitare i processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-131">On the log shipping secondary server, disable the copy and restore jobs.</span></span>  
  
6.  <span data-ttu-id="fc5b2-132">Facoltativamente, se non si utilizza più un database secondario per il log shipping, è possibile eliminarlo dal server secondario.</span><span class="sxs-lookup"><span data-stu-id="fc5b2-132">Optionally, if you are no longer using the log shipping secondary database, you can delete it from the secondary server.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fc5b2-133">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="fc5b2-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fc5b2-134">Aggiornare il log shipping a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fc5b2-134">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="fc5b2-135">Configurare il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fc5b2-135">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="fc5b2-136">Aggiungere un database secondario a una configurazione per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fc5b2-136">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="fc5b2-137">Rimuovere un database secondario da una configurazione per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fc5b2-137">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="fc5b2-138">Monitorare il log shipping &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fc5b2-138">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="fc5b2-139">Failover su un database secondario per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fc5b2-139">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="fc5b2-140">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="fc5b2-140">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc5b2-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc5b2-141">See Also</span></span>  
 <span data-ttu-id="fc5b2-142">[Informazioni sul log shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fc5b2-142">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="fc5b2-143">Tabelle e stored procedure relative al log shipping</span><span class="sxs-lookup"><span data-stu-id="fc5b2-143">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
