---
title: Concetti di base relativi alle stored procedure del sistema di replica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- stored procedures [SQL Server replication], programming
- programming [SQL Server replication], system stored procedures
- programming interfaces [SQL Server replication]
- system stored procedures [SQL Server replication]
- replication [SQL Server], how-to topics
ms.assetid: 816d2bda-ed72-43ec-aa4d-7ee3dc25fd8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 50536e5b6816c84dff26c9c9f99c46d02272b7de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725532"
---
# <a name="replication-system-stored-procedures-concepts"></a><span data-ttu-id="2c91b-102">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="2c91b-102">Replication System Stored Procedures Concepts</span></span>
  <span data-ttu-id="2c91b-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'accesso a livello di codice a tutte le funzionalità configurabili dall'utente in una topologia di replica viene fornito da stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="2c91b-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], programmatic access to all of the user-configurable functionality in a replication topology is provided by system stored procedures.</span></span> <span data-ttu-id="2c91b-104">Mentre le stored procedure possono essere eseguite singolarmente utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o l'utilità della riga di comando sqlcmd, può rivelarsi vantaggioso scrivere file script [!INCLUDE[tsql](../../../includes/tsql-md.md)] che consentono di eseguire una sequenza logica di attività di replica.</span><span class="sxs-lookup"><span data-stu-id="2c91b-104">While stored procedures may be executed individually using the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or the sqlcmd command-line utility, it may be beneficial to write [!INCLUDE[tsql](../../../includes/tsql-md.md)] script files that can be executed to perform a logical sequence of replication tasks.</span></span>  
  
 <span data-ttu-id="2c91b-105">L'esecuzione di attività di replica tramite script offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c91b-105">Scripting replication tasks provides the following benefits:</span></span>  
  
-   <span data-ttu-id="2c91b-106">Consente di conservare una copia permanente dei passaggi utilizzati per distribuire la topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="2c91b-106">Keeps a permanent copy of the steps used to deploy your replication topology.</span></span>  
  
-   <span data-ttu-id="2c91b-107">Consente di utilizzare un unico script per configurare più sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="2c91b-107">Uses a single script to configure multiple Subscribers.</span></span>  
  
-   <span data-ttu-id="2c91b-108">Consente di formare in breve tempo nuovi amministratori di database permettendo loro di valutare, comprendere e modificare il codice, nonché di risolvere i problemi a livello del codice.</span><span class="sxs-lookup"><span data-stu-id="2c91b-108">Quickly educates new database administrators by enabling them to evaluate, understand, change, or troubleshoot the code.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="2c91b-109">È possibile che gli script siano all'origine di vulnerabilità nella sicurezza, in quanto possono richiamare funzioni di sistema all'insaputa dell'utente e senza richiederne l'intervento, nonché contenere credenziali di sicurezza in testo normale.</span><span class="sxs-lookup"><span data-stu-id="2c91b-109">Scripts can be the source of security vulnerabilities; they can invoke system functions without user knowledge or intervention and may contain security credentials in plain text.</span></span> <span data-ttu-id="2c91b-110">Prima di utilizzarli, verificare gli script in modo da individuare possibili problemi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2c91b-110">Review scripts for security issues before you use them.</span></span>  
  
## <a name="creating-replication-scripts"></a><span data-ttu-id="2c91b-111">Creazione di script di replica</span><span class="sxs-lookup"><span data-stu-id="2c91b-111">Creating Replication Scripts</span></span>  
 <span data-ttu-id="2c91b-112">Dal punto di vista della replica, uno script è una serie di una o più istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] in cui ogni istruzione esegue una stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="2c91b-112">From the standpoint of replication, a script is a series of one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements where each statement executes a replication stored procedure.</span></span> <span data-ttu-id="2c91b-113">Gli script sono file di testo, spesso con l'estensione di file sql, che possono essere eseguiti utilizzando l'utilità sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="2c91b-113">Scripts are text files, often with a .sql file extension, that can be run using the sqlcmd utility.</span></span> <span data-ttu-id="2c91b-114">Quando un file script viene eseguito, l'utilità esegue le istruzioni SQL archiviate nel file.</span><span class="sxs-lookup"><span data-stu-id="2c91b-114">When a script file is run, the utility executes the SQL statements stored in the file.</span></span> <span data-ttu-id="2c91b-115">Allo stesso modo, uno script può essere archiviato come oggetto query in un progetto di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c91b-115">Similarly, a script can be stored as a query object in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span>  
  
 <span data-ttu-id="2c91b-116">Per creare script di replica è possibile procedere nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c91b-116">Replication scripts can be created in the following ways:</span></span>  
  
-   <span data-ttu-id="2c91b-117">Creare lo script in modo manuale.</span><span class="sxs-lookup"><span data-stu-id="2c91b-117">Manually create the script.</span></span>  
  
-   <span data-ttu-id="2c91b-118">Utilizzare le caratteristiche di generazione degli script fornite nelle procedure guidate per la replica oppure</span><span class="sxs-lookup"><span data-stu-id="2c91b-118">Use the script generation features that are provided in the replication wizards or</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="2c91b-119">.</span><span class="sxs-lookup"><span data-stu-id="2c91b-119">.</span></span> <span data-ttu-id="2c91b-120">Per altre informazioni, vedere [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="2c91b-120">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
-   <span data-ttu-id="2c91b-121">Utilizzare RMO (Replication Management Objects) per generare lo script a livello di codice per la creazione di un oggetto RMO.</span><span class="sxs-lookup"><span data-stu-id="2c91b-121">Use Replication Management Objects (RMOs) to programmatically generate the script to create an RMO object.</span></span>  
  
 <span data-ttu-id="2c91b-122">Quando si creano manualmente script di replica, tenere presente le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c91b-122">When you manually create replication scripts, keep the following considerations in mind:</span></span>  
  
-   <span data-ttu-id="2c91b-123">Gli script [!INCLUDE[tsql](../../../includes/tsql-md.md)] possono contenere uno o più batch.</span><span class="sxs-lookup"><span data-stu-id="2c91b-123">[!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts have one or more batches.</span></span> <span data-ttu-id="2c91b-124">Il comando GO indica la fine di un batch.</span><span class="sxs-lookup"><span data-stu-id="2c91b-124">The GO command signals the end of a batch.</span></span> <span data-ttu-id="2c91b-125">Uno script [!INCLUDE[tsql](../../../includes/tsql-md.md)] che non include alcun comando GO viene eseguito come batch singolo.</span><span class="sxs-lookup"><span data-stu-id="2c91b-125">If a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script does not have any GO commands, it is executed as a single batch.</span></span>  
  
-   <span data-ttu-id="2c91b-126">Quando si eseguono più stored procedure di replica in un solo batch, tutte le procedure successive alla prima procedura nel batch devono essere precedute dalla parola chiave EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="2c91b-126">When executing multiple replication stored procedures in a single batch, after the first procedure, all subsequent procedures in the batch must be preceded by the EXECUTE keyword.</span></span>  
  
-   <span data-ttu-id="2c91b-127">Tutte le stored procedure in un batch devono essere compilate prima che un batch venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="2c91b-127">All stored procedures in a batch must compile before a batch will execute.</span></span> <span data-ttu-id="2c91b-128">Tuttavia, dopo aver compilato il batch e creato un piano di esecuzione, potrebbe o meno verificarsi un errore di run-time.</span><span class="sxs-lookup"><span data-stu-id="2c91b-128">However, once the batch has been compiled, and an execution plan has been created, a run-time error may or may not occur.</span></span>  
  
-   <span data-ttu-id="2c91b-129">Quando si creano script per la configurazione della replica, è necessario utilizzare l'autenticazione di Windows per evitare di archiviare le credenziali di sicurezza nel file script.</span><span class="sxs-lookup"><span data-stu-id="2c91b-129">When creating scripts to configure replication, you should use Windows Authentication to avoid storing security credentials in the script file.</span></span> <span data-ttu-id="2c91b-130">Se è necessario archiviare le credenziali in un file script, è fondamentale proteggere il file per evitare accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2c91b-130">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
## <a name="sample-replication-script"></a><span data-ttu-id="2c91b-131">Script di replica di esempio</span><span class="sxs-lookup"><span data-stu-id="2c91b-131">Sample Replication Script</span></span>  
 <span data-ttu-id="2c91b-132">Lo script seguente può essere eseguito per configurare la pubblicazione e la distribuzione in un server.</span><span class="sxs-lookup"><span data-stu-id="2c91b-132">The following script can be executed to setup publishing and distribution on a server.</span></span>  
  
```  
-- This script uses sqlcmd scripting variables. They are in the form  
-- $(MyVariable). For information about how to use scripting variables    
-- on the command line and in SQL Server Management Studio, see the   
-- "Executing Replication Scripts" section in the topic  
-- "Programming Replication Using System Stored Procedures".  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
-- Specify the replication working directory.  
SET @directory = N'\\' + $(DistPubServer) + '\repldata';  
-- Specify the publication database.  
SET @publicationDB = N'AdventureWorks2012';   
  
-- Install the server MYDISTPUB as a Distributor using the defaults,  
-- including autogenerating the distributor password.  
USE master  
EXEC sp_adddistributor @distributor = @distributor;  
  
-- Create a new distribution database using the defaults, including  
-- using Windows Authentication.  
USE master  
EXEC sp_adddistributiondb @database = @distributionDB,   
    @security_mode = 1;  
GO  
  
-- Create a Publisher and enable AdventureWorks2012 for replication.  
-- Add MYDISTPUB as a publisher with MYDISTPUB as a local distributor  
-- and use Windows Authentication.  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
USE [distribution]  
EXEC sp_adddistpublisher @publisher=@publisher,   
    @distribution_db=@distributionDB,   
    @security_mode = 1;  
GO  
  
```  
  
 <span data-ttu-id="2c91b-133">È quindi possibile salvare questo script localmente come `instdistpub.sql` in modo da poterlo eseguire più volte in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="2c91b-133">This script can then be saved locally as `instdistpub.sql` so that it can be run or rerun when needed.</span></span>  
  
 <span data-ttu-id="2c91b-134">Lo script precedente include variabili di scripting **sqlcmd** usate in molti degli esempi di codice di replica presenti nella documentazione online di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c91b-134">The previous script includes **sqlcmd** scripting variables, which are used in many of the replication code samples in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="2c91b-135">Le variabili di scripting vengono definite mediante la sintassi `$(MyVariable)`.</span><span class="sxs-lookup"><span data-stu-id="2c91b-135">Scripting variables are defined by using `$(MyVariable)` syntax.</span></span> <span data-ttu-id="2c91b-136">I valori per le variabili possono essere passati a uno script dalla riga di comando o in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c91b-136">Values for variables can be passed to a script at the command line or in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2c91b-137">Per ulteriori informazioni, vedere la sezione successiva in questo argomento, "Esecuzione di script di replica".</span><span class="sxs-lookup"><span data-stu-id="2c91b-137">For more information, see the next section in this topic, "Executing Replication Scripts."</span></span>  
  
## <a name="executing-replication-scripts"></a><span data-ttu-id="2c91b-138">Esecuzione di script di replica</span><span class="sxs-lookup"><span data-stu-id="2c91b-138">Executing Replication Scripts</span></span>  
 <span data-ttu-id="2c91b-139">Dopo averlo creato, uno script di replica può essere eseguito in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c91b-139">Once created, a replication script can be executed in one of the following ways:</span></span>  
  
### <a name="creating-a-sql-query-file-in-sql-server-management-studio"></a><span data-ttu-id="2c91b-140">Creazione di un file query SQL in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c91b-140">Creating a SQL Query File in SQL Server Management Studio</span></span>  
 <span data-ttu-id="2c91b-141">Un file script di replica di [!INCLUDE[tsql](../../../includes/tsql-md.md)] può essere creato come file query SQL in un progetto di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c91b-141">A replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] script file can be created as a SQL Query file in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span> <span data-ttu-id="2c91b-142">Dopo aver scritto lo script, è possibile stabilire una connessione al database per questo file query ed eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="2c91b-142">After the script is written, a connection can be made to the database for this query file and the script can be executed.</span></span> <span data-ttu-id="2c91b-143">Per altre informazioni su come creare [!INCLUDE[tsql](../../../includes/tsql-md.md)] script usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , vedere Editor di [query e di testo &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span><span class="sxs-lookup"><span data-stu-id="2c91b-143">For more information about how to create [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], see [Query and Text Editors &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span></span>  
  
 <span data-ttu-id="2c91b-144">Per usare uno script che include variabili di scripting, è necessario che [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] sia in esecuzione in modalità **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="2c91b-144">To use a script that includes scripting variables, [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] must be running in **sqlcmd** mode.</span></span> <span data-ttu-id="2c91b-145">In modalità **sqlcmd**, l'editor di query accetta la sintassi aggiuntiva specifica di **sqlcmd**, ad esempio il comando `:setvar` usato per assegnare un valore a una variabile.</span><span class="sxs-lookup"><span data-stu-id="2c91b-145">In **sqlcmd** mode, the Query Editor accepts additional syntax specific to **sqlcmd**, such as `:setvar`, which is used to a value for a variable.</span></span> <span data-ttu-id="2c91b-146">Per altre informazioni sulla modalità **sqlcmd**, vedere [Modificare script SQLCMD con l'editor di query](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2c91b-146">For more information about **sqlcmd** mode, see [Edit SQLCMD Scripts with Query Editor](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span> <span data-ttu-id="2c91b-147">Nello script seguente il comando `:setvar` viene usato per fornire un valore per la variabile `$(DistPubServer)`.</span><span class="sxs-lookup"><span data-stu-id="2c91b-147">In the following script, `:setvar` is used to provide a value for the `$(DistPubServer)` variable.</span></span>  
  
```  
:setvar DistPubServer N'MyPublisherAndDistributor';  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
--  
-- Additional code goes here  
--  
```  
  
### <a name="using-the-sqlcmd-utility-from-the-command-line"></a><span data-ttu-id="2c91b-148">Utilizzo dell'utilità sqlcmd dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="2c91b-148">Using the sqlcmd Utility from the Command Line</span></span>  
 <span data-ttu-id="2c91b-149">L'esempio seguente mostra come usare la riga di comando per eseguire il file di script `instdistpub.sql` con l'[utilità sqlcmd](../../../tools/sqlcmd-utility.md):</span><span class="sxs-lookup"><span data-stu-id="2c91b-149">The following example shows how the command line is used to execute the `instdistpub.sql` script file using the [sqlcmd utility](../../../tools/sqlcmd-utility.md):</span></span>  
  
```  
sqlcmd.exe -E -S sqlserverinstance -i C:\instdistpub.sql -o C:\output.log -v DistPubServer="N'MyDistributorAndPublisher'"  
```  
  
 <span data-ttu-id="2c91b-150">In questo esempio, l'opzione `-E` indica che viene utilizzata l'autenticazione di Windows per la connessione a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c91b-150">In this example, the `-E` switch indicates that Windows Authentication is used when connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2c91b-151">Quando si utilizza l'autenticazione di Windows, non è necessario archiviare un nome utente e una password nel file script.</span><span class="sxs-lookup"><span data-stu-id="2c91b-151">When using Windows Authentication, there is no need to store a username and password in the script file.</span></span> <span data-ttu-id="2c91b-152">Il nome e il percorso del file script vengono specificati dall'opzione `-i` e il nome del file di output viene specificato dall'opzione `-o`. Quando viene utilizzata questa opzione, l'output da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] viene scritto in questo file anziché indirizzato alla console.</span><span class="sxs-lookup"><span data-stu-id="2c91b-152">The name and path of the script file is specified by the `-i` switch and the name of the output file is specified by the `-o` switch (output from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is written to this file instead of the console when this switch is used).</span></span> <span data-ttu-id="2c91b-153">L'utilità `sqlcmd` consente di passare variabili di scripting a uno script di [!INCLUDE[tsql](../../../includes/tsql-md.md)] durante l'esecuzione utilizzando l'opzione `-v`.</span><span class="sxs-lookup"><span data-stu-id="2c91b-153">The `sqlcmd` utility enables you to pass scripting variables to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script at runtime using the `-v` switch.</span></span> <span data-ttu-id="2c91b-154">In questo esempio, `sqlcmd` sostituisce ogni istanza di `$(DistPubServer)` nello script con il valore `N'MyDistributorAndPublisher'` prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2c91b-154">In this example, `sqlcmd` replaces every instance of `$(DistPubServer)` in the script with the value `N'MyDistributorAndPublisher'` before execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c91b-155">L'opzione `-X` disabilita le variabili di scripting.</span><span class="sxs-lookup"><span data-stu-id="2c91b-155">The `-X` switch disables scripting variables.</span></span>  
  
### <a name="automating-tasks-in-a-batch-file"></a><span data-ttu-id="2c91b-156">Automatizzazione di attività in un file batch</span><span class="sxs-lookup"><span data-stu-id="2c91b-156">Automating Tasks in a Batch File</span></span>  
 <span data-ttu-id="2c91b-157">L'utilizzo di un file batch consente di automatizzare le attività di amministrazione della replica, le attività di sincronizzazione della replica e altre attività nello stesso file batch.</span><span class="sxs-lookup"><span data-stu-id="2c91b-157">By using a batch file, replication administration tasks, replication synchronization tasks, and other tasks can be automated in the same batch file.</span></span> <span data-ttu-id="2c91b-158">Il file batch seguente usa l'utilità **sqlcmd** per eliminare e ricreare il database di sottoscrizione e aggiungere una sottoscrizione pull di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="2c91b-158">The following batch file uses the **sqlcmd** utility to drop and recreate the subscription database and add a merge pull subscription.</span></span> <span data-ttu-id="2c91b-159">Il file richiama quindi l'agente di merge per sincronizzare la nuova sottoscrizione:</span><span class="sxs-lookup"><span data-stu-id="2c91b-159">Then the file invokes the merge agent to synchronize the new subscription:</span></span>  
  
```  
REM ----------------------Script to synchronize merge subscription ----------------------  
REM -- Creates subscription database and   
REM -- synchronizes the subscription to MergeSalesPerson.  
REM -- Current computer acts as both Publisher and Subscriber.  
REM -------------------------------------------------------------------------------------  
  
SET Publisher=%computername%  
SET Subscriber=%computername%  
SET PubDb=AdventureWorks  
SET SubDb=AdventureWorksReplica  
SET PubName=AdvWorksSalesOrdersMerge  
  
REM -- Drop and recreate the subscription database at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE master IF EXISTS (SELECT * FROM sysdatabases WHERE name='%SubDb%' ) DROP DATABASE %SubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE master CREATE DATABASE %SubDb%"  
  
REM -- Add a pull subscription at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb% EXEC sp_addmergepullsubscription @publisher = %Publisher%, @publication = %PubName%, @publisher_db = %PubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb%  EXEC sp_addmergepullsubscription_agent @publisher = %Publisher%, @publisher_db = %PubDb%, @publication = %PubName%, @subscriber = %Subscriber%, @subscriber_db = %SubDb%, @distributor = %Publisher%"  
  
REM -- This batch file starts the merge agent at the Subscriber to   
REM -- synchronize a pull subscription to a merge publication.  
REM -- The following must be supplied on one line.  
"\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher  %Publisher% -Subscriber  %Subscriber%  -Distributor %Publisher%  -PublisherDB  %PubDb% -SubscriberDB %SubDb% -Publication %PubName% -PublisherSecurityMode 1 -OutputVerboseLevel 1  -Output  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1 -Validate 3  
  
```  
  
## <a name="scripting-common-replication-tasks"></a><span data-ttu-id="2c91b-160">Generazione di script per attività di replica comuni</span><span class="sxs-lookup"><span data-stu-id="2c91b-160">Scripting Common Replication Tasks</span></span>  
 <span data-ttu-id="2c91b-161">Di seguito vengono illustrate alcune delle attività di replica più comuni per le quali è possibile generare script utilizzando stored procedure di sistema:</span><span class="sxs-lookup"><span data-stu-id="2c91b-161">The following are some of the most common replication tasks can be scripted using system stored procedures:</span></span>  
  
-   <span data-ttu-id="2c91b-162">Configurazione della pubblicazione e della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2c91b-162">Configuring publishing and distribution</span></span>  
  
-   <span data-ttu-id="2c91b-163">Modifica delle proprietà del server di pubblicazione e del server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2c91b-163">Modifying Publisher and Distributor properties</span></span>  
  
-   <span data-ttu-id="2c91b-164">Disabilitazione della pubblicazione e della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2c91b-164">Disabling publishing and distribution</span></span>  
  
-   <span data-ttu-id="2c91b-165">Creazione di pubblicazioni e definizione di articoli.</span><span class="sxs-lookup"><span data-stu-id="2c91b-165">Creating publications and defining articles</span></span>  
  
-   <span data-ttu-id="2c91b-166">Eliminazione di pubblicazioni e articoli.</span><span class="sxs-lookup"><span data-stu-id="2c91b-166">Deleting publications and articles</span></span>  
  
-   <span data-ttu-id="2c91b-167">Creazione di una sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="2c91b-167">Creating a pull subscription</span></span>  
  
-   <span data-ttu-id="2c91b-168">Modifica di una sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="2c91b-168">Modifying a pull subscription</span></span>  
  
-   <span data-ttu-id="2c91b-169">Eliminazione di una sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="2c91b-169">Deleting a pull subscription</span></span>  
  
-   <span data-ttu-id="2c91b-170">Creazione di una sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="2c91b-170">Creating a push subscription</span></span>  
  
-   <span data-ttu-id="2c91b-171">Modifica di una sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="2c91b-171">Modifying a push subscription</span></span>  
  
-   <span data-ttu-id="2c91b-172">Eliminazione di una sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="2c91b-172">Deleting a push subscription</span></span>  
  
-   <span data-ttu-id="2c91b-173">Sincronizzazione di una sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="2c91b-173">Synchronizing a pull subscription</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c91b-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c91b-174">See Also</span></span>  
 <span data-ttu-id="2c91b-175">[Concetti di base relativi alla programmazione della replica](replication-programming-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="2c91b-175">[Replication Programming Concepts](replication-programming-concepts.md) </span></span>  
 <span data-ttu-id="2c91b-176">[Stored procedure per la replica &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2c91b-176">[Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="2c91b-177">Creazione di script di replica</span><span class="sxs-lookup"><span data-stu-id="2c91b-177">Scripting Replication</span></span>](../scripting-replication.md)  
  
  
