---
title: Spostare i database di sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- moving system databases
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- tempdb database [SQL Server], moving
- system databases [SQL Server], moving
- scheduled disk maintenace [SQL Server]
- moving databases
- msdb database [SQL Server], moving
- moving database files
- relocating database files
- planned database relocations [SQL Server]
- master database [SQL Server], moving
- model database [SQL Server], moving
- Resource database [SQL Server]
- databases [SQL Server], moving
ms.assetid: 72bb62ee-9602-4f71-be51-c466c1670878
author: stevestein
ms.author: sstein
ms.openlocfilehash: 748d781d6bbefb0dc710427a34ebd71ec7037fdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727008"
---
# <a name="move-system-databases"></a><span data-ttu-id="23b7d-102">Spostare i database di sistema</span><span class="sxs-lookup"><span data-stu-id="23b7d-102">Move System Databases</span></span>
  <span data-ttu-id="23b7d-103">In questo argomento viene descritta la procedura per lo spostamento dei database di sistema in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23b7d-103">This topic describes how to move system databases in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="23b7d-104">Lo spostamento dei database di sistema può risultare utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="23b7d-104">Moving system databases may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="23b7d-105">Recupero da errore.</span><span class="sxs-lookup"><span data-stu-id="23b7d-105">Failure recovery.</span></span> <span data-ttu-id="23b7d-106">Ad esempio, il database è in modalità sospetta oppure viene chiuso a causa di un errore hardware.</span><span class="sxs-lookup"><span data-stu-id="23b7d-106">For example, the database is in suspect mode or has shut down because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="23b7d-107">Rilocazione pianificata.</span><span class="sxs-lookup"><span data-stu-id="23b7d-107">Planned relocation.</span></span>  
  
-   <span data-ttu-id="23b7d-108">Rilocazione per una manutenzione pianificata del disco.</span><span class="sxs-lookup"><span data-stu-id="23b7d-108">Relocation for scheduled disk maintenance.</span></span>  
  
 <span data-ttu-id="23b7d-109">Le procedure seguenti consentono di spostare i file di database all'interno della stessa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23b7d-109">The following procedures apply to moving database files within the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="23b7d-110">Per spostare un database in un'altra istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o in un altro server, utilizzare le operazioni di [backup e ripristino](../backup-restore/back-up-and-restore-of-sql-server-databases.md) o di [collegamento e scollegamento](move-a-database-using-detach-and-attach-transact-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="23b7d-110">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use the [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach](move-a-database-using-detach-and-attach-transact-sql.md) operations.</span></span>  
  
 <span data-ttu-id="23b7d-111">Le procedure descritte in questo argomento richiedono il nome logico dei file di database.</span><span class="sxs-lookup"><span data-stu-id="23b7d-111">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="23b7d-112">Per ottenere il nome, eseguire una query sulla colonna name della vista del catalogo [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="23b7d-112">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="23b7d-113">Se si sposta un database di sistema e successivamente si ricompila il database master, è necessario spostare nuovamente il database di sistema, in quanto l'operazione di ricompilazione ha come conseguenza l'installazione di tutti i database di sistema nei rispettivi percorsi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="23b7d-113">If you move a system database and later rebuild the master database, you must move the system database again because the rebuild operation installs all system databases to their default location.</span></span>  
  
##  <a name="in-this-topic"></a><a name="Intro"></a> <span data-ttu-id="23b7d-114">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="23b7d-114">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="23b7d-115">Procedura di rilocazione pianificata e manutenzione pianificata del disco</span><span class="sxs-lookup"><span data-stu-id="23b7d-115">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>](#Planned)  
  
-   [<span data-ttu-id="23b7d-116">Procedura di ripristino non riuscita</span><span class="sxs-lookup"><span data-stu-id="23b7d-116">Failure Recovery Procedure</span></span>](#Failure)  
  
-   [<span data-ttu-id="23b7d-117">Trasferimento del database master</span><span class="sxs-lookup"><span data-stu-id="23b7d-117">Moving the master Database</span></span>](#master)  
  
-   [<span data-ttu-id="23b7d-118">Trasferimento del database delle risorse</span><span class="sxs-lookup"><span data-stu-id="23b7d-118">Moving the Resource Database</span></span>](#Resource)  
  
-   [<span data-ttu-id="23b7d-119">Completamento: dopo aver spostato tutti i database di sistema</span><span class="sxs-lookup"><span data-stu-id="23b7d-119">Follow-up: After Moving All System Databases</span></span>](#Follow)  
  
-   [<span data-ttu-id="23b7d-120">esempi</span><span class="sxs-lookup"><span data-stu-id="23b7d-120">Examples</span></span>](#Examples)  
  
##  <a name="planned-relocation-and-scheduled-disk-maintenance-procedure"></a><a name="Planned"></a> <span data-ttu-id="23b7d-121">Procedura di rilocazione pianificata e manutenzione pianificata del disco</span><span class="sxs-lookup"><span data-stu-id="23b7d-121">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>  
 <span data-ttu-id="23b7d-122">Per spostare un file di dati o di log del database di sistema nell'ambito di un'operazione di rilocazione pianificata o di manutenzione pianificata, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="23b7d-122">To move a system database data or log file as part of a planned relocation or scheduled maintenance operation, follow these steps.</span></span> <span data-ttu-id="23b7d-123">Questa procedura è valida per tutti i database di sistema ad eccezione dei database master e Resource.</span><span class="sxs-lookup"><span data-stu-id="23b7d-123">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
1.  <span data-ttu-id="23b7d-124">Per ogni file che si desidera spostare, eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="23b7d-124">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
2.  <span data-ttu-id="23b7d-125">Arrestare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o arrestare il sistema per eseguire la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="23b7d-125">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="23b7d-126">Per altre informazioni, vedere [Avviare, arrestare, sospendere, riprendere, riavviare i servizi SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="23b7d-126">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="23b7d-127">Spostare il file o i file nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="23b7d-127">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="23b7d-128">Riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o il server.</span><span class="sxs-lookup"><span data-stu-id="23b7d-128">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="23b7d-129">Per altre informazioni, vedere [Avviare, arrestare, sospendere, riprendere, riavviare i servizi SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="23b7d-129">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
5.  <span data-ttu-id="23b7d-130">Verificare la modifica ai file eseguendo la query riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="23b7d-130">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
 <span data-ttu-id="23b7d-131">Se il database msdb viene spostato e l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è configurata per [Posta elettronica database](../database-mail/database-mail.md), completare i passaggi aggiuntivi seguenti.</span><span class="sxs-lookup"><span data-stu-id="23b7d-131">If the msdb database is moved and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for [Database Mail](../database-mail/database-mail.md), complete these additional steps.</span></span>  
  
1.  <span data-ttu-id="23b7d-132">Verificare che [!INCLUDE[ssSB](../../../includes/sssb-md.md)] sia abilitato per il database msdb eseguendo la query seguente.</span><span class="sxs-lookup"><span data-stu-id="23b7d-132">Verify that [!INCLUDE[ssSB](../../../includes/sssb-md.md)] is enabled for the msdb database by running the following query.</span></span>  
  
    ```  
    SELECT is_broker_enabled   
    FROM sys.databases  
    WHERE name = N'msdb';  
    ```  
  
     <span data-ttu-id="23b7d-133">Per altre informazioni su come abilitare [!INCLUDE[ssSB](../../../includes/sssb-md.md)], vedere [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="23b7d-133">For more information about enabling [!INCLUDE[ssSB](../../../includes/sssb-md.md)], see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
2.  <span data-ttu-id="23b7d-134">Verificare il funzionamento di Posta elettronica database inviando un messaggio di prova.</span><span class="sxs-lookup"><span data-stu-id="23b7d-134">Verify that Database Mail is working by sending a test mail.</span></span>  
  
##  <a name="failure-recovery-procedure"></a><a name="Failure"></a> <span data-ttu-id="23b7d-135">Procedura di recupero da errore</span><span class="sxs-lookup"><span data-stu-id="23b7d-135">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="23b7d-136">Se è necessario spostare un file a causa di un errore hardware, eseguire la procedura seguente per rilocare il file in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="23b7d-136">If a file must be moved because of a hardware failure, follow these steps to relocate the file to a new location.</span></span> <span data-ttu-id="23b7d-137">Questa procedura è valida per tutti i database di sistema ad eccezione dei database master e Resource.</span><span class="sxs-lookup"><span data-stu-id="23b7d-137">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="23b7d-138">Se non è possibile avviare il database, ovvero se il database è in modalità sospetta o in stato non recuperato, il file può essere spostato solo dai membri del ruolo predefinito sysadmin.</span><span class="sxs-lookup"><span data-stu-id="23b7d-138">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="23b7d-139">Arrestare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se avviata.</span><span class="sxs-lookup"><span data-stu-id="23b7d-139">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="23b7d-140">Avviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modalità di recupero del solo database master digitando uno dei comandi seguenti al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="23b7d-140">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span> <span data-ttu-id="23b7d-141">I parametri specificati in questi comandi fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="23b7d-141">The parameters specified in these commands are case sensitive.</span></span> <span data-ttu-id="23b7d-142">I comandi hanno esito negativo se i parametri non vengono specificati come illustrato.</span><span class="sxs-lookup"><span data-stu-id="23b7d-142">The commands fail when the parameters are not specified as shown.</span></span>  
  
    -   <span data-ttu-id="23b7d-143">Per l'istanza predefinita (MSSQLSERVER), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="23b7d-143">For the default (MSSQLSERVER) instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="23b7d-144">Per un'istanza denominata, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="23b7d-144">For a named instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="23b7d-145">Per altre informazioni, vedere [Avviare, arrestare, sospendere, riprendere, riavviare i servizi SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="23b7d-145">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="23b7d-146">Per ogni file da spostare, usare i comandi **sqlcmd** oppure [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] per eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="23b7d-146">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
     <span data-ttu-id="23b7d-147">Per altre informazioni su come usare l'utilità **sqlcmd** , vedere [Usare l'utilità sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="23b7d-147">For more information about using the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="23b7d-148">Uscire dall'utilità **sqlcmd** o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23b7d-148">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="23b7d-149">Arrestare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23b7d-149">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="23b7d-150">Eseguire, ad esempio, `NET STOP MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="23b7d-150">For example, run `NET STOP MSSQLSERVER`.</span></span>  
  
6.  <span data-ttu-id="23b7d-151">Spostare il file o i file nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="23b7d-151">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="23b7d-152">Riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23b7d-152">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="23b7d-153">Eseguire, ad esempio, `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="23b7d-153">For example, run `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="23b7d-154">Verificare la modifica ai file eseguendo la query riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="23b7d-154">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
##  <a name="moving-the-master-database"></a><a name="master"></a> <span data-ttu-id="23b7d-155">Spostamento del database master</span><span class="sxs-lookup"><span data-stu-id="23b7d-155">Moving the master Database</span></span>  
 <span data-ttu-id="23b7d-156">Per spostare il database master, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="23b7d-156">To move the master database, follow these steps.</span></span>  
  
1.  <span data-ttu-id="23b7d-157">Fare clic sul menu **Start** , scegliere **Tutti i programmi**, **Microsoft SQL Server**, **Strumenti di configurazione**e quindi fare clic su **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="23b7d-157">From the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="23b7d-158">Nel nodo **Servizi di SQL Server** fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad esempio **SQL Server (MSSQLSERVER)** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="23b7d-158">In the **SQL Server Services** node, right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (for example, **SQL Server (MSSQLSERVER)**) and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="23b7d-159">Nella finestra di dialogo \*\*Proprietà ( \*\*\*nome_istanza \***) di SQL Server** fare clic sulla scheda **Parametri di avvio** .</span><span class="sxs-lookup"><span data-stu-id="23b7d-159">In the **SQL Server (***instance_name***) Properties** dialog box, click the **Startup Parameters** tab.</span></span>  
  
4.  <span data-ttu-id="23b7d-160">Nella casella **Parametri esistenti** selezionare il parametro -d per spostare il file di dati master.</span><span class="sxs-lookup"><span data-stu-id="23b7d-160">In the **Existing parameters** box, select the -d parameter to move the master data file.</span></span> <span data-ttu-id="23b7d-161">Per salvare le modifiche, fare clic su **Aggiorna** .</span><span class="sxs-lookup"><span data-stu-id="23b7d-161">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="23b7d-162">Nella casella **Specificare un parametro di avvio** impostare il parametro sul nuovo percorso del database master.</span><span class="sxs-lookup"><span data-stu-id="23b7d-162">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
5.  <span data-ttu-id="23b7d-163">Nella casella **Parametri esistenti** selezionare il parametro -l per spostare il file di log master.</span><span class="sxs-lookup"><span data-stu-id="23b7d-163">In the **Existing parameters** box, select the -l parameter to move the master log file.</span></span> <span data-ttu-id="23b7d-164">Per salvare le modifiche, fare clic su **Aggiorna** .</span><span class="sxs-lookup"><span data-stu-id="23b7d-164">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="23b7d-165">Nella casella **Specificare un parametro di avvio** impostare il parametro sul nuovo percorso del database master.</span><span class="sxs-lookup"><span data-stu-id="23b7d-165">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
     <span data-ttu-id="23b7d-166">Il valore del parametro per il file di dati deve seguire il parametro `-d` e il valore per il file di log deve seguire il parametro `-l` .</span><span class="sxs-lookup"><span data-stu-id="23b7d-166">The parameter value for the data file must follow the `-d` parameter and the value for the log file must follow the `-l` parameter.</span></span> <span data-ttu-id="23b7d-167">L'esempio seguente illustra i valori dei parametri per il percorso predefinito del file di dati master.</span><span class="sxs-lookup"><span data-stu-id="23b7d-167">The following example shows the parameter values for the default location of the master data file.</span></span>  
  
     `-dC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\master.mdf`  
  
     `-lC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\mastlog.ldf`  
  
     <span data-ttu-id="23b7d-168">Se la rilocazione pianificata del file di dati master è `E:\SQLData`, i valori dei parametri verranno modificati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="23b7d-168">If the planned relocation for the master data file is `E:\SQLData`, the parameter values would be changed as follows:</span></span>  
  
     `-dE:\SQLData\master.mdf`  
  
     `-lE:\SQLData\mastlog.ldf`  
  
6.  <span data-ttu-id="23b7d-169">Arrestare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] facendo clic con il pulsante destro del mouse sul nome dell'istanza e scegliendo **Arresta**.</span><span class="sxs-lookup"><span data-stu-id="23b7d-169">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by right-clicking the instance name and choosing **Stop**.</span></span>  
  
7.  <span data-ttu-id="23b7d-170">Spostare i file master.mdf e mastlog.ldf nel nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="23b7d-170">Move the master.mdf and mastlog.ldf files to the new location.</span></span>  
  
8.  <span data-ttu-id="23b7d-171">Riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23b7d-171">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="23b7d-172">Verificare la modifica dei file per il database master eseguendo la query seguente.</span><span class="sxs-lookup"><span data-stu-id="23b7d-172">Verify the file change for the master database by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID('master');  
    GO  
    ```  
  
##  <a name="moving-the-resource-database"></a><a name="Resource"></a> <span data-ttu-id="23b7d-173">Spostamento del database delle risorse</span><span class="sxs-lookup"><span data-stu-id="23b7d-173">Moving the Resource Database</span></span>  
 <span data-ttu-id="23b7d-174">Il percorso del database Resource è \<*drive*>:\Programmi\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span><span class="sxs-lookup"><span data-stu-id="23b7d-174">The location of the Resource database is \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span></span> <span data-ttu-id="23b7d-175">Il database non può essere spostato.</span><span class="sxs-lookup"><span data-stu-id="23b7d-175">The database cannot be moved.</span></span>  
  
##  <a name="follow-up-after-moving-all-system-databases"></a><a name="Follow"></a> <span data-ttu-id="23b7d-176">Completamento: Dopo lo spostamento di tutti i database di sistema</span><span class="sxs-lookup"><span data-stu-id="23b7d-176">Follow-up: After Moving All System Databases</span></span>  
 <span data-ttu-id="23b7d-177">Se tutti i database di sistema sono stati spostati in un nuovo volume o unità oppure in un altro server con una lettera di unità diversa, effettuare gli aggiornamenti riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="23b7d-177">If you have moved all of the system databases to a new drive or volume or to another server with a different drive letter, make the following updates.</span></span>  
  
-   <span data-ttu-id="23b7d-178">Modificare il percorso del log di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="23b7d-178">Change the SQL Server Agent log path.</span></span> <span data-ttu-id="23b7d-179">Se non si aggiorna questo percorso, non sarà possibile avviare SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="23b7d-179">If you do not update this path, SQL Server Agent will fail to start.</span></span>  
  
-   <span data-ttu-id="23b7d-180">Modificare il percorso predefinito del database.</span><span class="sxs-lookup"><span data-stu-id="23b7d-180">Change the database default location.</span></span> <span data-ttu-id="23b7d-181">La creazione di un nuovo database potrebbe non venir completata correttamente se la lettera di unità e il percorso specificati come posizione predefinita non esistono.</span><span class="sxs-lookup"><span data-stu-id="23b7d-181">Creating a new database may fail if the drive letter and path specified as the default location do not exist.</span></span>  
  
#### <a name="change-the-sql-server-agent-log-path"></a><span data-ttu-id="23b7d-182">Modificare il percorso del log di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="23b7d-182">Change the SQL Server Agent Log Path</span></span>  
  
1.  <span data-ttu-id="23b7d-183">In Esplora oggetti di SQL Server Management Studio espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="23b7d-183">From SQL Server Management Studio, in Object Explorer, expand **SQL Server Agent**.</span></span>  
  
2.  <span data-ttu-id="23b7d-184">Fare clic con il pulsante destro del mouse su **Log degli errori** e scegliere **Configura**.</span><span class="sxs-lookup"><span data-stu-id="23b7d-184">Right-click **Error Logs** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="23b7d-185">Nella finestra di dialogo **Configura log degli errori di SQL Server Agent** specificare il nuovo percorso del file SQLAGENT.OUT.</span><span class="sxs-lookup"><span data-stu-id="23b7d-185">In the **Configure SQL Server Agent Error Logs** dialog box, specify the new location of the SQLAGENT.OUT file.</span></span> <span data-ttu-id="23b7d-186">Il percorso predefinito è c:\Programmi\Microsoft SQL Server\MSSQL12. <instance_name> \MSSQL\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="23b7d-186">The default location is C:\Program Files\Microsoft SQL Server\MSSQL12.<instance_name>\MSSQL\Log\\.</span></span>  
  
#### <a name="change-the-database-default-location"></a><span data-ttu-id="23b7d-187">Modificare il percorso predefinito del database</span><span class="sxs-lookup"><span data-stu-id="23b7d-187">Change the database default location</span></span>  
  
1.  <span data-ttu-id="23b7d-188">In Esplora oggetti di SQL Server Management Studio fare clic con il pulsante destro del mouse sul server SQL Server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="23b7d-188">From SQL Server Management Studio, in Object Explorer, right-click the SQL Server server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="23b7d-189">Nella finestra di dialogo **Proprietà server** selezionare **Impostazioni database**.</span><span class="sxs-lookup"><span data-stu-id="23b7d-189">In the **Server Properties** dialog box, select **Database Settings**.</span></span>  
  
3.  <span data-ttu-id="23b7d-190">In **Percorsi predefiniti database**selezionare il nuovo percorso sia per i file di dati sia per quelli di log.</span><span class="sxs-lookup"><span data-stu-id="23b7d-190">Under **Database Default Locations**, browse to the new location for both the data and log files.</span></span>  
  
4.  <span data-ttu-id="23b7d-191">Per completare la modifica, avviare e arrestare il servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23b7d-191">Stop and start the SQL Server service to complete the change.</span></span>  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="23b7d-192">Esempi</span><span class="sxs-lookup"><span data-stu-id="23b7d-192">Examples</span></span>  
  
### <a name="a-moving-the-tempdb-database"></a><span data-ttu-id="23b7d-193">R.</span><span class="sxs-lookup"><span data-stu-id="23b7d-193">A.</span></span> <span data-ttu-id="23b7d-194">Spostamento del database tempdb</span><span class="sxs-lookup"><span data-stu-id="23b7d-194">Moving the tempdb database</span></span>  
 <span data-ttu-id="23b7d-195">Nell'esempio seguente i file dei dati e di log del database `tempdb` vengono spostati in un nuovo percorso nell'ambito di una rilocazione pianificata.</span><span class="sxs-lookup"><span data-stu-id="23b7d-195">The following example moves the `tempdb` data and log files to a new location as part of a planned relocation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23b7d-196">Poiché tempdb viene ricreato a ogni avvio dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , non è necessario spostare fisicamente i file di dati e di log.</span><span class="sxs-lookup"><span data-stu-id="23b7d-196">Because tempdb is re-created each time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, you do not have to physically move the data and log files.</span></span> <span data-ttu-id="23b7d-197">I file vengono creati nella nuova posizione quando il servizio viene riavviato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="23b7d-197">The files are created in the new location when the service is restarted in step 3.</span></span> <span data-ttu-id="23b7d-198">Fino al riavvio del servizio, il database tempdb continuerà a utilizzare i file di dati e di log nella posizione esistente.</span><span class="sxs-lookup"><span data-stu-id="23b7d-198">Until the service is restarted, tempdb continues to use the data and log files in existing location.</span></span>  
  
1.  <span data-ttu-id="23b7d-199">Determinare i nomi dei file logici del database `tempdb` e la relativa posizione corrente sul disco.</span><span class="sxs-lookup"><span data-stu-id="23b7d-199">Determine the logical file names of the `tempdb` database and their current location on the disk.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    GO  
    ```  
  
2.  <span data-ttu-id="23b7d-200">Modificare il percorso di ogni file tramite `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="23b7d-200">Change the location of each file by using `ALTER DATABASE`.</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = tempdev, FILENAME = 'E:\SQLData\tempdb.mdf');  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = templog, FILENAME = 'F:\SQLLog\templog.ldf');  
    GO  
    ```  
  
3.  <span data-ttu-id="23b7d-201">Arrestare e riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23b7d-201">Stop and restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="23b7d-202">Verificare la modifica ai file.</span><span class="sxs-lookup"><span data-stu-id="23b7d-202">Verify the file change.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    ```  
  
5.  <span data-ttu-id="23b7d-203">Eliminare i file `tempdb.mdf` e `templog.ldf` dal percorso originale.</span><span class="sxs-lookup"><span data-stu-id="23b7d-203">Delete the `tempdb.mdf` and `templog.ldf` files from the original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b7d-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23b7d-204">See Also</span></span>  
 <span data-ttu-id="23b7d-205">[Database Resource](resource-database.md) </span><span class="sxs-lookup"><span data-stu-id="23b7d-205">[Resource Database](resource-database.md) </span></span>  
 <span data-ttu-id="23b7d-206">[Database tempdb](tempdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="23b7d-206">[tempdb Database](tempdb-database.md) </span></span>  
 <span data-ttu-id="23b7d-207">[Database master](master-database.md) </span><span class="sxs-lookup"><span data-stu-id="23b7d-207">[master Database](master-database.md) </span></span>  
 <span data-ttu-id="23b7d-208">[Database msdb](msdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="23b7d-208">[msdb Database](msdb-database.md) </span></span>  
 <span data-ttu-id="23b7d-209">[Database model](model-database.md) </span><span class="sxs-lookup"><span data-stu-id="23b7d-209">[model Database](model-database.md) </span></span>  
 <span data-ttu-id="23b7d-210">[Spostare database utente](move-user-databases.md) </span><span class="sxs-lookup"><span data-stu-id="23b7d-210">[Move User Databases](move-user-databases.md) </span></span>  
 <span data-ttu-id="23b7d-211">[Spostare file del database](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="23b7d-211">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="23b7d-212">[Avviare, arrestare, sospendere, riprendere, riavviare il motore di database, SQL Server Agent o SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="23b7d-212">[Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span></span>  
 <span data-ttu-id="23b7d-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23b7d-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="23b7d-214">Ricompilare database di sistema</span><span class="sxs-lookup"><span data-stu-id="23b7d-214">Rebuild System Databases</span></span>](system-databases.md)  
  
  
