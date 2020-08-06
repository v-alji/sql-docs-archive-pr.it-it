---
title: Configurare il log shipping (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], enabling
- log shipping [SQL Server], configuring
ms.assetid: c42aa04a-4945-4417-b4c7-50589d727e9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269b0ae2980435e507128cc87606f7eb702c2b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713427"
---
# <a name="configure-log-shipping-sql-server"></a><span data-ttu-id="195c7-102">Configurare il log shipping (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="195c7-102">Configure Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="195c7-103">In questo argomento viene descritto come configurare il log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="195c7-103">This topic describes how to configure log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="195c7-104">e le versioni successive supportano la compressione dei backup.</span><span class="sxs-lookup"><span data-stu-id="195c7-104">and later versions support backup compression.</span></span> <span data-ttu-id="195c7-105">Quando si crea una configurazione per il log shipping, è possibile determinare il comportamento della compressione dei backup per i backup del log.</span><span class="sxs-lookup"><span data-stu-id="195c7-105">When creating a log shipping configuration, you can control the backup compression behavior of log backups.</span></span> <span data-ttu-id="195c7-106">Per altre informazioni, vedere [Compressione backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="195c7-106">For more information, see [Backup Compression &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="195c7-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="195c7-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="195c7-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="195c7-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="195c7-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="195c7-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="195c7-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="195c7-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="195c7-111">**Per configurare il log shipping utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="195c7-111">**To configure log shipping, using:**</span></span>  
  
     [<span data-ttu-id="195c7-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="195c7-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="195c7-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="195c7-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="195c7-114">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="195c7-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="195c7-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="195c7-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="195c7-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="195c7-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="195c7-117">Il database primario deve utilizzare il modello di recupero con registrazione completa o registrazione minima delle operazioni bulk. Il passaggio al modello di recupero con registrazione minima comporterà l'arresto del log shipping.</span><span class="sxs-lookup"><span data-stu-id="195c7-117">The primary database must use the full or bulk-logged recovery model; switching the database to simple recovery will cause log shipping to stop functioning.</span></span>  
  
-   <span data-ttu-id="195c7-118">Prima di configurare il log shipping, è necessario creare una condivisione per rendere disponibili i backup dei log delle transazioni al server secondario.</span><span class="sxs-lookup"><span data-stu-id="195c7-118">Before you configure log shipping, you must create a share to make the transaction log backups available to the secondary server.</span></span> <span data-ttu-id="195c7-119">Si tratta di una condivisione della directory in cui verranno generati i backup dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="195c7-119">This is a share of the directory where the transaction log backups will be generated.</span></span> <span data-ttu-id="195c7-120">Se, ad esempio, si esegue il backup dei log delle transazioni nella directory c:\data\tlogs\\, è possibile creare la condivisione \\\\*serverprimario*\tlogs per tale directory.</span><span class="sxs-lookup"><span data-stu-id="195c7-120">For example, if you back up your transaction logs to the directory c:\data\tlogs\\, you could create the \\\\*primaryserver*\tlogs share of that directory.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="195c7-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="195c7-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="195c7-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="195c7-122">Permissions</span></span>  
 <span data-ttu-id="195c7-123">Le stored procedure per il log shipping richiedono l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="195c7-123">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="195c7-124">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="195c7-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="195c7-125">Per configurare il log shipping</span><span class="sxs-lookup"><span data-stu-id="195c7-125">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="195c7-126">Fare clic con il pulsante destro del mouse sul database da utilizzare come primario nella configurazione per il log shipping e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="195c7-126">Right click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="195c7-127">Nella casella **Selezionare una pagina**fare clic su **Log shipping delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="195c7-127">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="195c7-128">Selezionare la casella di controllo **Abilita come database primario in una configurazione per il log shipping** .</span><span class="sxs-lookup"><span data-stu-id="195c7-128">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
4.  <span data-ttu-id="195c7-129">In **Backup log delle transazioni**fare clic su **Impostazioni backup**.</span><span class="sxs-lookup"><span data-stu-id="195c7-129">Under **Transaction log backups**, click **Backup Settings**.</span></span>  
  
5.  <span data-ttu-id="195c7-130">Nella casella **Percorso di rete della cartella di backup** digitare il percorso di rete della condivisione creata per la cartella di backup dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="195c7-130">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>  
  
6.  <span data-ttu-id="195c7-131">Se la cartella di backup si trova nel server primario, digitare il percorso locale della cartella di backup nella casella **Se la cartella di backup si trova nel server primario, digitare il percorso locale della cartella** .</span><span class="sxs-lookup"><span data-stu-id="195c7-131">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="195c7-132">Se la cartella di backup non si trova nel server primario, è possibile lasciare vuota la casella.</span><span class="sxs-lookup"><span data-stu-id="195c7-132">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="195c7-133">Se l'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del server principale viene eseguito utilizzando l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare il percorso locale della cartella.</span><span class="sxs-lookup"><span data-stu-id="195c7-133">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>  
  
7.  <span data-ttu-id="195c7-134">Configurare i parametri **Elimina i file più vecchi di** e **Invia avviso se il backup non viene eseguito entro** .</span><span class="sxs-lookup"><span data-stu-id="195c7-134">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>  
  
8.  <span data-ttu-id="195c7-135">Si noti la pianificazione di backup presente nella casella **Pianificazione** in **Processo di backup**.</span><span class="sxs-lookup"><span data-stu-id="195c7-135">Note the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="195c7-136">Se si desidera personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione** e quindi modificare la pianificazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in base alle specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="195c7-136">If you want to customize the schedule for your installation, then click **Schedule** and adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span>  
  
9. [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="195c7-137">supporta la [compressione dei backup](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="195c7-137">supports [backup compression](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span> <span data-ttu-id="195c7-138">Quando si crea una configurazione per il log shipping, è possibile determinare il comportamento della compressione dei backup per i backup del log scegliendo una delle opzioni seguenti: **Usa l'impostazione predefinita del server**, **Comprimi backup** o **Non comprimere il backup**.</span><span class="sxs-lookup"><span data-stu-id="195c7-138">When creating a log shipping configuration, you can control the backup compression behavior of log backups by choosing one of the following options: **Use the default server setting**, **Compress backup**, or **Do not compress backup**.</span></span> <span data-ttu-id="195c7-139">Per altre informazioni, vedere [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span><span class="sxs-lookup"><span data-stu-id="195c7-139">For more information, see [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span></span>  
  
10. <span data-ttu-id="195c7-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="195c7-140">Click **OK**.</span></span>  
  
11. <span data-ttu-id="195c7-141">In **Istanze del server e database secondari**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="195c7-141">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
12. <span data-ttu-id="195c7-142">Fare clic su **Connetti** e connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che si intende utilizzare come server secondario.</span><span class="sxs-lookup"><span data-stu-id="195c7-142">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
13. <span data-ttu-id="195c7-143">Nella casella **Database secondario** scegliere un database dall'elenco oppure digitare il nome del database che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="195c7-143">In the **Secondary Database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
14. <span data-ttu-id="195c7-144">Nella scheda **Inizializza database secondario** scegliere l'opzione che si intende utilizzare per inizializzare il database secondario.</span><span class="sxs-lookup"><span data-stu-id="195c7-144">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="195c7-145">Se si sceglie di configurare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] in modo da inizializzare il database secondario da un backup di database, i file di dati e di log del database secondario vengono inseriti nello stesso percorso dei file di dati e di log del database **master** .</span><span class="sxs-lookup"><span data-stu-id="195c7-145">If you choose to have [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] initialize the secondary database from a database backup, the data and log files of the secondary database are placed in the same location as the data and log files of the **master** database.</span></span> <span data-ttu-id="195c7-146">Questo percorso sarà probabilmente diverso da quello dei file di dati e di log del database primario.</span><span class="sxs-lookup"><span data-stu-id="195c7-146">This location is likely to be different than the location of the data and log files of the primary database.</span></span>  
  
15. <span data-ttu-id="195c7-147">Nella casella **Cartella di destinazione per i file copiati** della scheda **Copia file** digitare il percorso della cartella in cui copiare i backup dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="195c7-147">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="195c7-148">Spesso questa cartella si trova nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="195c7-148">This folder is often located on the secondary server.</span></span>  
  
16. <span data-ttu-id="195c7-149">Si noti la pianificazione di copia presente nella casella **Pianificazione** in **Processo di copia**.</span><span class="sxs-lookup"><span data-stu-id="195c7-149">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="195c7-150">Se si desidera personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione** e quindi modificare la pianificazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in base alle specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="195c7-150">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="195c7-151">Questa pianificazione dovrebbe essere abbastanza simile alla pianificazione del backup.</span><span class="sxs-lookup"><span data-stu-id="195c7-151">This schedule should approximate the backup schedule.</span></span>  
  
17. <span data-ttu-id="195c7-152">In **Stato del database durante il ripristino dei backup** nella scheda **Ripristino**scegliere l'opzione **Modalità nessun recupero** oppure **Modalità standby** .</span><span class="sxs-lookup"><span data-stu-id="195c7-152">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
18. <span data-ttu-id="195c7-153">Se si sceglie l'opzione **Modalità standby** , scegliere se si desidera disconnettere gli utenti dal database secondario durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="195c7-153">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
19. <span data-ttu-id="195c7-154">Se si desidera posticipare il processo di ripristino sul server secondario, scegliere un tempo di ritardo in **Ritardo minimo per il ripristino dei backup**.</span><span class="sxs-lookup"><span data-stu-id="195c7-154">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
20. <span data-ttu-id="195c7-155">Scegliere una soglia di avviso in **Invia avviso se il ripristino non viene eseguito entro**.</span><span class="sxs-lookup"><span data-stu-id="195c7-155">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
21. <span data-ttu-id="195c7-156">Si noti la pianificazione di ripristino presente nella casella **Pianificazione** in **Processo di ripristino**.</span><span class="sxs-lookup"><span data-stu-id="195c7-156">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="195c7-157">Se si desidera personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione** e quindi modificare la pianificazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in base alle specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="195c7-157">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="195c7-158">Questa pianificazione dovrebbe essere abbastanza simile alla pianificazione del backup.</span><span class="sxs-lookup"><span data-stu-id="195c7-158">This schedule should approximate the backup schedule.</span></span>  
  
22. <span data-ttu-id="195c7-159">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="195c7-159">Click **OK**.</span></span>  
  
23. <span data-ttu-id="195c7-160">In **Istanza server di monitoraggio**selezionare la casella di controllo **Usa un'istanza del server di monitoraggio** e quindi fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="195c7-160">Under **Monitor server instance**, select the **Use a monitor server instance** check box, and then click **Settings**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="195c7-161">Per eseguire il monitoraggio della configurazione per il log shipping, è necessario aggiungere subito il server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="195c7-161">To monitor this log shipping configuration, you must add the monitor server now.</span></span> <span data-ttu-id="195c7-162">Per aggiungere il server di monitoraggio in un momento successivo, sarà necessario rimuovere la configurazione per il log shipping e sostituirla con una configurazione nuova che includa un server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="195c7-162">To add the monitor server later, you would need to remove this log shipping configuration and then replace it with a new configuration that includes a monitor server.</span></span>  
  
24. <span data-ttu-id="195c7-163">Fare clic su **Connetti** e connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che si desidera utilizzare come server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="195c7-163">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your monitor server.</span></span>  
  
25. <span data-ttu-id="195c7-164">In **Connessioni server di monitoraggio**scegliere il metodo che i processi di backup, copia e ripristino devono utilizzare per la connessione al server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="195c7-164">Under **Monitor connections**, choose the connection method to be used by the backup, copy, and restore jobs to connect to the monitor server.</span></span>  
  
26. <span data-ttu-id="195c7-165">In **Periodo memorizzazione cronologia**scegliere il periodo di memorizzazione dei record della cronologia di log shipping.</span><span class="sxs-lookup"><span data-stu-id="195c7-165">Under **History retention**, choose the length of time you want to retain a record of your log shipping history.</span></span>  
  
27. <span data-ttu-id="195c7-166">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="195c7-166">Click **OK**.</span></span>  
  
28. <span data-ttu-id="195c7-167">Nella finestra di dialogo **Proprietà database** fare clic su **OK** per iniziare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="195c7-167">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="195c7-168">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="195c7-168">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="195c7-169">Per configurare il log shipping</span><span class="sxs-lookup"><span data-stu-id="195c7-169">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="195c7-170">Per inizializzare il database secondario, ripristinare un backup completo del database primario sul server secondario.</span><span class="sxs-lookup"><span data-stu-id="195c7-170">Initialize the secondary database by restoring a full backup of the primary database on the secondary server.</span></span>  
  
2.  <span data-ttu-id="195c7-171">Nel server primario eseguire [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) per aggiungere un database primario.</span><span class="sxs-lookup"><span data-stu-id="195c7-171">On the primary server, execute [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) to add a primary database.</span></span> <span data-ttu-id="195c7-172">La stored procedure restituisce l'ID del processo di backup e l'ID primario.</span><span class="sxs-lookup"><span data-stu-id="195c7-172">The stored procedure returns the backup job ID and primary ID.</span></span>  
  
3.  <span data-ttu-id="195c7-173">Nel server primario eseguire [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) per aggiungere una pianificazione per il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="195c7-173">On the primary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to add a schedule for the backup job.</span></span>  
  
4.  <span data-ttu-id="195c7-174">Nel server di monitoraggio eseguire [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) per aggiungere il processo di gestione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="195c7-174">On the monitor server, execute [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) to add the alert job.</span></span>  
  
5.  <span data-ttu-id="195c7-175">Sul server primario abilitare il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="195c7-175">On the primary server, enable the backup job.</span></span>  
  
6.  <span data-ttu-id="195c7-176">Nel server secondario eseguire [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) specificando i dettagli del server e del database primario.</span><span class="sxs-lookup"><span data-stu-id="195c7-176">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="195c7-177">Questa stored procedure restituisce l'ID secondario e gli ID dei processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="195c7-177">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
7.  <span data-ttu-id="195c7-178">Nel server secondario eseguire [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) per impostare la pianificazione relativa ai processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="195c7-178">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
8.  <span data-ttu-id="195c7-179">Nel server secondario eseguire [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) per aggiungere un database secondario.</span><span class="sxs-lookup"><span data-stu-id="195c7-179">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
9. <span data-ttu-id="195c7-180">Nel server primario eseguire [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) per aggiungere le informazioni necessarie relative al nuovo database secondario.</span><span class="sxs-lookup"><span data-stu-id="195c7-180">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
10. <span data-ttu-id="195c7-181">Nel server secondario abilitare i processi di copia e ripristino.</span><span class="sxs-lookup"><span data-stu-id="195c7-181">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="195c7-182">Per altre informazioni, vedere [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="195c7-182">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="195c7-183">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="195c7-183">Related Tasks</span></span>  
  
-   [<span data-ttu-id="195c7-184">Aggiornare il log shipping a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="195c7-184">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="195c7-185">Aggiungere un database secondario a una configurazione per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="195c7-185">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="195c7-186">Rimuovere un database secondario da una configurazione per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="195c7-186">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="195c7-187">Rimuovere il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="195c7-187">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="195c7-188">Visualizzare il report di log shipping &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="195c7-188">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="195c7-189">Monitorare il log shipping &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="195c7-189">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="195c7-190">Failover su un database secondario per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="195c7-190">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="195c7-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="195c7-191">See Also</span></span>  
 <span data-ttu-id="195c7-192">[Informazioni sul log shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="195c7-192">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="195c7-193">Tabelle e stored procedure relative al log shipping</span><span class="sxs-lookup"><span data-stu-id="195c7-193">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
