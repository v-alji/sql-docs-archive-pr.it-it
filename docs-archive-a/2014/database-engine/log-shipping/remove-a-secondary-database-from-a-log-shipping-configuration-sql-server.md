---
title: Rimuovere un database secondario da una configurazione per il log shipping (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- deleting secondary databases
- secondary databases [SQL Server], in log shipping
- removing secondary databases
- secondary data files [SQL Server], removing
- log shipping [SQL Server], secondary databases
ms.assetid: ebe368a4-ca1c-45d0-9a71-3ddbd5b26a8e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 119f2762d41d0787b6b3279507e9671e89fddfca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630022"
---
# <a name="remove-a-secondary-database-from-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="0e20c-102">Rimuovere un database secondario da una configurazione per il log shipping (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0e20c-102">Remove a Secondary Database from a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="0e20c-103">In questo argomento viene descritto come rimuovere un database secondario per il log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e20c-103">This topic describes how to remove a log shipping secondary database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0e20c-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="0e20c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0e20c-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0e20c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0e20c-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0e20c-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0e20c-107">**Per rimuovere un database secondario per il log shipping utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="0e20c-107">**To remove a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="0e20c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0e20c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0e20c-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0e20c-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="0e20c-110">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0e20c-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0e20c-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0e20c-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0e20c-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0e20c-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0e20c-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0e20c-113">Permissions</span></span>  
 <span data-ttu-id="0e20c-114">Le stored procedure per il log shipping richiedono l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0e20c-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0e20c-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0e20c-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-a-log-shipping-secondary-database"></a><span data-ttu-id="0e20c-116">Per rimuovere un database secondario per il log shipping</span><span class="sxs-lookup"><span data-stu-id="0e20c-116">To remove a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="0e20c-117">Connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che rappresenta attualmente il server primario di log shipping ed espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="0e20c-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="0e20c-118">Espandere **Database**, fare clic con il pulsante destro del mouse sul database primario per il log shipping, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0e20c-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0e20c-119">Nella casella **Selezionare una pagina**fare clic su **Log shipping delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="0e20c-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="0e20c-120">Nell'area **Istanze del server e database secondari**fare clic sul database da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="0e20c-120">Under **Secondary server instances and databases**, click the database you want to remove.</span></span>  
  
5.  <span data-ttu-id="0e20c-121">Scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="0e20c-121">Click **Remove**.</span></span>  
  
6.  <span data-ttu-id="0e20c-122">Fare clic su **OK** per aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="0e20c-122">Click **OK** to update the configuration.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0e20c-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0e20c-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-secondary-database"></a><span data-ttu-id="0e20c-124">Per rimuovere un database secondario</span><span class="sxs-lookup"><span data-stu-id="0e20c-124">To Remove a Secondary Database</span></span>  
  
1.  <span data-ttu-id="0e20c-125">Nel server primario eseguire [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) per eliminare le informazioni relative al database secondario.</span><span class="sxs-lookup"><span data-stu-id="0e20c-125">On the primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="0e20c-126">Nel server secondario eseguire [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) per eliminare il database secondario.</span><span class="sxs-lookup"><span data-stu-id="0e20c-126">On the secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e20c-127">Se non sono disponibili altri database secondari con lo stesso ID secondario, **sp_delete_log_shipping_secondary_primary** viene richiamata da **sp_delete_log_shipping_secondary_database** e tramite essa vengono eliminati la voce relativa all'ID secondario e i processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="0e20c-127">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="0e20c-128">Nel server secondario disabilitare i processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="0e20c-128">On the secondary server, disable the copy and restore jobs.</span></span> <span data-ttu-id="0e20c-129">Per altre informazioni, vedere [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="0e20c-129">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0e20c-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0e20c-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="0e20c-131">Aggiornare il log shipping a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0e20c-131">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="0e20c-132">Configurare il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e20c-132">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="0e20c-133">Aggiungere un database secondario a una configurazione per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e20c-133">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="0e20c-134">Rimuovere il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e20c-134">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="0e20c-135">Visualizzare il report di log shipping &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0e20c-135">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="0e20c-136">Monitorare il log shipping &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0e20c-136">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="0e20c-137">Failover su un database secondario per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e20c-137">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e20c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e20c-138">See Also</span></span>  
 <span data-ttu-id="0e20c-139">[Informazioni sul log shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0e20c-139">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="0e20c-140">Tabelle e stored procedure relative al log shipping</span><span class="sxs-lookup"><span data-stu-id="0e20c-140">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
