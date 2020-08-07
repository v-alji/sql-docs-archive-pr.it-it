---
title: Modificare i ruoli tra i server primario e secondario per il log shipping (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], role changes
- secondary data files [SQL Server], roles changed between
- primary databases [SQL Server]
- initial role changes [SQL Server]
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: 2d7cc40a-47e8-4419-9b2b-7c69f700e806
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 52ddb89bfd18eef4cd2140bc67cf93d1800138f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718671"
---
# <a name="change-roles-between-primary-and-secondary-log-shipping-servers-sql-server"></a><span data-ttu-id="63397-102">Modificare i ruoli tra i server primario e secondario per il log shipping (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="63397-102">Change Roles Between Primary and Secondary Log Shipping Servers (SQL Server)</span></span>
  <span data-ttu-id="63397-103">Dopo aver eseguito il failover di una configurazione per il log shipping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] su un server secondario, è possibile configurare il database secondario per operare come database primario.</span><span class="sxs-lookup"><span data-stu-id="63397-103">After you have failed over a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log shipping configuration to a secondary server, you can configure your secondary database to act as the primary database.</span></span> <span data-ttu-id="63397-104">Sarà quindi possibile scambiare il database primario e quello secondario in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="63397-104">Then, you will be able to swap primary and secondary databases as needed.</span></span>  
  
## <a name="performing-the-initial-role-change"></a><span data-ttu-id="63397-105">Esecuzione della modifica iniziale del ruolo</span><span class="sxs-lookup"><span data-stu-id="63397-105">Performing the Initial Role Change</span></span>  
 <span data-ttu-id="63397-106">La prima volta che si desidera eseguire il failover al database secondario e impostarlo come nuovo database primario, è necessario eseguire alcuni passaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="63397-106">The first time you want to fail over to the secondary database and make it your new primary database, there is a series of steps you must take.</span></span> <span data-ttu-id="63397-107">Dopo avere eseguito tali passaggi iniziali, sarà possibile scambiare i ruoli tra database primario e secondario in modo semplice.</span><span class="sxs-lookup"><span data-stu-id="63397-107">After you have followed these initial steps, you will be able to swap roles between the primary database and the secondary database easily.</span></span>  
  
1.  <span data-ttu-id="63397-108">Eseguire manualmente il failover dal database primario a un database secondario.</span><span class="sxs-lookup"><span data-stu-id="63397-108">Manually fail over from the primary database to a secondary database.</span></span> <span data-ttu-id="63397-109">Eseguire il backup del log delle transazioni attive nel server primario con l'opzione NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="63397-109">Be sure to back up the active transaction log on your primary server with NORECOVERY.</span></span> <span data-ttu-id="63397-110">Per altre informazioni, vedere [Failover su un database secondario per il log shipping &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="63397-110">For more information, see [Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="63397-111">Disabilitare il processo di backup per il log shipping nel server primario originale e i processi di copia e ripristino nel server secondario originale.</span><span class="sxs-lookup"><span data-stu-id="63397-111">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="63397-112">Nel database secondario, che si desidera impostare come nuovo database primario, configurare il log shipping usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63397-112">On your secondary database (the database you want to be the new primary), configure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="63397-113">Per altre informazioni, vedere [Configurare il log shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="63397-113">For more information, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span> <span data-ttu-id="63397-114">Eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="63397-114">Include the following steps:</span></span>  
  
    1.  <span data-ttu-id="63397-115">Per la creazione di backup, usare la stessa condivisione creata per il server primario originale.</span><span class="sxs-lookup"><span data-stu-id="63397-115">Use the same share for creating backups that you created for the original primary server.</span></span>  
  
    2.  <span data-ttu-id="63397-116">Quando si aggiunge il database secondario, nella casella **Database secondario** della finestra di dialogo **Impostazioni database secondario** immettere il nome del database primario originale.</span><span class="sxs-lookup"><span data-stu-id="63397-116">When adding the secondary database, in the **Secondary Database Settings** dialog box, enter the name of the original primary database in the **Secondary database** box.</span></span>  
  
    3.  <span data-ttu-id="63397-117">Nella finestra di dialogo **Impostazioni database secondario** selezionare **No, il database secondario è già inizializzato**.</span><span class="sxs-lookup"><span data-stu-id="63397-117">In the **Secondary Database Settings** dialog box, select **No, the secondary database is initialized**.</span></span>  
  
4.  <span data-ttu-id="63397-118">Se il monitoraggio del log shipping era abilitato nella relativa configurazione precedente, riconfigurare il monitoraggio per controllare la nuova configurazione per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="63397-118">If log shipping monitoring was enabled on your former log shipping configuration, reconfigure log shipping monitoring to monitor the new log shipping configuration.</span></span>  <span data-ttu-id="63397-119">Eseguire i comandi riportati di seguito, sostituendo *database_name* con il nome del database in uso:</span><span class="sxs-lookup"><span data-stu-id="63397-119">Execute the following commands, replacing *database_name* with the name of your database:</span></span>  
  
    1.  <span data-ttu-id="63397-120">**Nel nuovo server primario**</span><span class="sxs-lookup"><span data-stu-id="63397-120">**On the new primary server**</span></span>  
  
         <span data-ttu-id="63397-121">Eseguire le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="63397-121">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new primary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_secondary_database @secondary_database = N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
    2.  <span data-ttu-id="63397-122">**Nel nuovo server secondario**</span><span class="sxs-lookup"><span data-stu-id="63397-122">**On the new secondary server**</span></span>  
  
         <span data-ttu-id="63397-123">Eseguire le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="63397-123">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new secondary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_primary_database @database=N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
## <a name="swapping-roles"></a><span data-ttu-id="63397-124">Scambio di ruoli</span><span class="sxs-lookup"><span data-stu-id="63397-124">Swapping Roles</span></span>  
 <span data-ttu-id="63397-125">Dopo avere completato i passaggi descritti in precedenza per la modifica iniziale dei ruoli, è possibile scambiare i ruoli tra il database primario e quello secondario eseguendo i passaggi indicati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="63397-125">After you have completed the steps above for the initial role change, you can change roles between the primary database and the secondary database by following the steps in this section.</span></span> <span data-ttu-id="63397-126">Per modificare i ruoli, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="63397-126">To perform a role change, follow these general steps:</span></span>  
  
1.  <span data-ttu-id="63397-127">Portare online il database secondario, eseguendo il backup del log delle transazioni nel server primario con l'opzione NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="63397-127">Bring the secondary database online, backing up the transaction log on the primary server with NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="63397-128">Disabilitare il processo di backup per il log shipping nel server primario originale e i processi di copia e ripristino nel server secondario originale.</span><span class="sxs-lookup"><span data-stu-id="63397-128">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="63397-129">Abilitare il processo di backup per il log shipping nel server secondario, ovvero il nuovo server primario, e i processi di copia e ripristino nel server primario, ovvero il nuovo server secondario.</span><span class="sxs-lookup"><span data-stu-id="63397-129">Enable the log shipping backup job on the secondary server (the new primary server), and the copy and restore jobs on the primary server (the new secondary server).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="63397-130">Se si modifica un database secondario in database primario per offrire a utenti e applicazioni un sistema più coerente, potrebbe essere necessario ricreare alcuni o tutti i metadati del database, ad esempio account di accesso e processi, nell'istanza del nuovo server primario.</span><span class="sxs-lookup"><span data-stu-id="63397-130">When you change a secondary database to the primary database, to provide a consistent experience to users and applications, you might have to re-create some or all of the metadata for the database, such as logins and jobs, on the new primary server instance.</span></span> <span data-ttu-id="63397-131">Per altre informazioni, vedere [Gestione dei metadati quando si rende disponibile un database in un'altra istanza del server &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="63397-131">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="63397-132">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="63397-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="63397-133">Failover su un database secondario per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63397-133">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="63397-134">Gestione di account di accesso e di processi dopo un cambio di ruolo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63397-134">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="63397-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63397-135">See Also</span></span>  
 [<span data-ttu-id="63397-136">Tabelle e stored procedure relative al log shipping</span><span class="sxs-lookup"><span data-stu-id="63397-136">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
