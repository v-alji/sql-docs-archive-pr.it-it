---
title: Utilità tablediff | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- comparing data
- tablediff utility
- tables [SQL Server replication]
- table comparisons [SQL Server]
- command prompt utilities [SQL Server], tablediff
- troubleshooting [SQL Server replication], non-convergence
- non-convergence [SQL Server]
ms.assetid: 3c3cb865-7a4d-4d66-98f2-5935e28929fc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a23465a7d2c7db53475a6dca81a8471a3b78b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720598"
---
# <a name="tablediff-utility"></a><span data-ttu-id="2520c-102">utilità tablediff</span><span class="sxs-lookup"><span data-stu-id="2520c-102">tablediff Utility</span></span>
  <span data-ttu-id="2520c-103">L'utilità **tablediff** viene usata per confrontare i dati in due tabelle per rilevarne l'eventuale non convergenza e risulta particolarmente utile per la risoluzione dei problemi relativi alla non convergenza in una topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="2520c-103">The **tablediff** utility is used to compare the data in two tables for non-convergence, and is particularly useful for troubleshooting non-convergence in a replication topology.</span></span> <span data-ttu-id="2520c-104">Questa utilità può essere utilizzata dal prompt dei comandi oppure in un file batch per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2520c-104">This utility can be used from the command prompt or in a batch file to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="2520c-105">Confronto riga per riga tra una tabella di origine in un'istanza di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] che funge da server di pubblicazione per la replica e una tabella di destinazione in una o più istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] che fungono da sottoscrittori della replica.</span><span class="sxs-lookup"><span data-stu-id="2520c-105">A row by row comparison between a source table in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as a replication Publisher and the destination table at one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as replication Subscribers.</span></span>  
  
-   <span data-ttu-id="2520c-106">Esegue un confronto rapido mediante il confronto solo dei conteggi delle righe e degli schemi.</span><span class="sxs-lookup"><span data-stu-id="2520c-106">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
-   <span data-ttu-id="2520c-107">Confronti a livello di colonna.</span><span class="sxs-lookup"><span data-stu-id="2520c-107">Perform column-level comparisons.</span></span>  
  
-   <span data-ttu-id="2520c-108">Generazione di uno script [!INCLUDE[tsql](../includes/tsql-md.md)] per correggere le discrepanze nel server di destinazione e rendere convergenti le tabelle di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2520c-108">Generate a [!INCLUDE[tsql](../includes/tsql-md.md)] script to fix discrepancies at the destination server to bring the source and destination tables into convergence.</span></span>  
  
-   <span data-ttu-id="2520c-109">Registrazione dei risultati in un file di output oppure in una tabella nel database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2520c-109">Log results to an output file or into a table in the destination database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2520c-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2520c-110">Syntax</span></span>  
  
```  
  
      tablediff   
[ -? ] |   
{  
        -sourceserversource_server_name[\instance_name]  
        -sourcedatabasesource_database-sourcetablesource_table_name   
    [ -sourceschemasource_schema_name ]  
    [ -sourcepasswordsource_password ]  
    [ -sourceusersource_login ]  
    [ -sourcelocked ]  
        -destinationserverdestination_server_name[\instance_name]  
        -destinationdatabasesubscription_database-destinationtabledestination_table   
    [ -destinationschemadestination_schema_name ]  
    [ -destinationpassworddestination_password ]  
    [ -destinationuserdestination_login ]  
    [ -destinationlocked ]  
    [ -blarge_object_bytes ]   
    [ -bfnumber_of_statements ]   
    [ -c ]   
    [ -dt ]   
    [ -ettable_name ]   
    [ -f [ file_name ] ]   
    [ -ooutput_file_name ]   
    [ -q ]   
    [ -rcnumber_of_retries ]   
    [ -riretry_interval ]   
    [ -strict ]  
    [ -tconnection_timeouts ]   
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="2520c-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2520c-111">Arguments</span></span>  
 <span data-ttu-id="2520c-112">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="2520c-112">[ **-?**</span></span> <span data-ttu-id="2520c-113">]</span><span class="sxs-lookup"><span data-stu-id="2520c-113">]</span></span>  
 <span data-ttu-id="2520c-114">Restituisce l'elenco dei parametri supportati.</span><span class="sxs-lookup"><span data-stu-id="2520c-114">Returns the list of supported parameters.</span></span>  
  
 <span data-ttu-id="2520c-115">**-sourceServer** *source_server_name*[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="2520c-115">**-sourceserver** *source_server_name*[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="2520c-116">Nome del server di origine.</span><span class="sxs-lookup"><span data-stu-id="2520c-116">Is the name of the source server.</span></span> <span data-ttu-id="2520c-117">Specificare _il \_ \_ nome del server di origine_ per l'istanza predefinita di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2520c-117">Specify _source\_server\_name_ for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2520c-118">Specificare il nome dell'istanza del _ \_ \_ nome del server di origine_ **\\** per un'istanza denominata di_ \_ _ [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2520c-118">Specify _source\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2520c-119">**-sourcedatabase** *source_database*</span><span class="sxs-lookup"><span data-stu-id="2520c-119">**-sourcedatabase** *source_database*</span></span>  
 <span data-ttu-id="2520c-120">Nome del database di origine.</span><span class="sxs-lookup"><span data-stu-id="2520c-120">Is the name of the source database.</span></span>  
  
 <span data-ttu-id="2520c-121">**-sourcetable** *source_table_name*</span><span class="sxs-lookup"><span data-stu-id="2520c-121">**-sourcetable** *source_table_name*</span></span>  
 <span data-ttu-id="2520c-122">Nome della tabella di origine sottoposta al controllo.</span><span class="sxs-lookup"><span data-stu-id="2520c-122">Is the name of the source table being checked.</span></span>  
  
 <span data-ttu-id="2520c-123">**-sourceschema** *source_schema_name*</span><span class="sxs-lookup"><span data-stu-id="2520c-123">**-sourceschema** *source_schema_name*</span></span>  
 <span data-ttu-id="2520c-124">Proprietario dello schema della tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="2520c-124">The schema owner of the source table.</span></span> <span data-ttu-id="2520c-125">Per impostazione predefinita, dbo viene considerato il proprietario della tabella.</span><span class="sxs-lookup"><span data-stu-id="2520c-125">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="2520c-126">**-sourcepassword** *source_password*</span><span class="sxs-lookup"><span data-stu-id="2520c-126">**-sourcepassword** *source_password*</span></span>  
 <span data-ttu-id="2520c-127">Password di accesso usata per connettersi al server di origine mediante l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2520c-127">Is the password for the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2520c-128">Se possibile, specificare le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2520c-128">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="2520c-129">Se è necessario archiviare le credenziali in un file script, è consigliabile proteggere il file per evitare accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2520c-129">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="2520c-130">**-sourceuser** *source_login*</span><span class="sxs-lookup"><span data-stu-id="2520c-130">**-sourceuser** *source_login*</span></span>  
 <span data-ttu-id="2520c-131">Account di accesso usato per connettersi al server di origine mediante l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2520c-131">Is the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="2520c-132">Se non si specifica il parametro *source_login* , durante la connessione al server di origine viene usata l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2520c-132">If *source_login* is not supplied, then Windows Authentication is used when connecting to the source server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="2520c-133">**-sourcelocked**</span><span class="sxs-lookup"><span data-stu-id="2520c-133">**-sourcelocked**</span></span>  
 <span data-ttu-id="2520c-134">La tabella di origine viene bloccata durante il confronto mediante gli hint di tabella TABLOCK e HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="2520c-134">The source table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="2520c-135">**-DestinationServer** *destination_server_name*[ **\\** _ \_ nome istanza_]</span><span class="sxs-lookup"><span data-stu-id="2520c-135">**-destinationserver** *destination_server_name*[**\\**_instance\_name_]</span></span>  
 <span data-ttu-id="2520c-136">Nome del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2520c-136">Is the name of the destination server.</span></span> <span data-ttu-id="2520c-137">Specificare *destination_server_name* per l'istanza predefinita di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2520c-137">Specify *destination_server_name* for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2520c-138">Specificare il nome dell'istanza del _ \_ \_ nome del server di destinazione_ **\\** per un'istanza denominata di_ \_ _ [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2520c-138">Specify _destination\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2520c-139">**-destinationdatabase** *subscription_database*</span><span class="sxs-lookup"><span data-stu-id="2520c-139">**-destinationdatabase** *subscription_database*</span></span>  
 <span data-ttu-id="2520c-140">Nome del database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2520c-140">Is the name of the destination database.</span></span>  
  
 <span data-ttu-id="2520c-141">**-destinationtable** *destination_table*</span><span class="sxs-lookup"><span data-stu-id="2520c-141">**-destinationtable** *destination_table*</span></span>  
 <span data-ttu-id="2520c-142">Nome della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2520c-142">Is the name of the destination table.</span></span>  
  
 <span data-ttu-id="2520c-143">**-destinationschema** *destination_schema_name*</span><span class="sxs-lookup"><span data-stu-id="2520c-143">**-destinationschema** *destination_schema_name*</span></span>  
 <span data-ttu-id="2520c-144">Proprietario dello schema della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2520c-144">The schema owner of the destination table.</span></span> <span data-ttu-id="2520c-145">Per impostazione predefinita, dbo viene considerato il proprietario della tabella.</span><span class="sxs-lookup"><span data-stu-id="2520c-145">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="2520c-146">**-destinationpassword** *destination_password*</span><span class="sxs-lookup"><span data-stu-id="2520c-146">**-destinationpassword** *destination_password*</span></span>  
 <span data-ttu-id="2520c-147">Password di accesso usata per connettersi al server di destinazione mediante l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2520c-147">Is the password for the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2520c-148">Se possibile, specificare le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2520c-148">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="2520c-149">Se è necessario archiviare le credenziali in un file script, è consigliabile proteggere il file per evitare accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2520c-149">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="2520c-150">**-destinationuser** *destination_login*</span><span class="sxs-lookup"><span data-stu-id="2520c-150">**-destinationuser** *destination_login*</span></span>  
 <span data-ttu-id="2520c-151">Account di accesso usato per connettersi al server di destinazione mediante l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2520c-151">Is the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="2520c-152">Se non si specifica il parametro *destination_login* , durante la connessione al server viene usata l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2520c-152">If *destination_login* is not supplied, then Windows Authentication is used when connecting to the server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="2520c-153">**-destinationlocked**</span><span class="sxs-lookup"><span data-stu-id="2520c-153">**-destinationlocked**</span></span>  
 <span data-ttu-id="2520c-154">La tabella di destinazione viene bloccata durante il confronto mediante gli hint di tabella TABLOCK e HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="2520c-154">The destination table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="2520c-155">**-b** *large_object_bytes*</span><span class="sxs-lookup"><span data-stu-id="2520c-155">**-b** *large_object_bytes*</span></span>  
 <span data-ttu-id="2520c-156">Numero di byte per confrontare le colonne con tipo di dati LOB, ovvero `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` e `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="2520c-156">Is the number of bytes to compare for large object data type columns, which includes: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` and `varbinary(max)`.</span></span> <span data-ttu-id="2520c-157">L'impostazione predefinita di*large_object_bytes* corrisponde alle dimensioni della colonna.</span><span class="sxs-lookup"><span data-stu-id="2520c-157">*large_object_bytes* defaults to the size of the column.</span></span> <span data-ttu-id="2520c-158">I dati che superano il valore di *large_object_bytes* non verranno confrontati.</span><span class="sxs-lookup"><span data-stu-id="2520c-158">Any data above *large_object_bytes* will not be compared.</span></span>  
  
 <span data-ttu-id="2520c-159">**-bf**  *number_of_statements*</span><span class="sxs-lookup"><span data-stu-id="2520c-159">**-bf**  *number_of_statements*</span></span>  
 <span data-ttu-id="2520c-160">Numero di istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] da scrivere nel file script [!INCLUDE[tsql](../includes/tsql-md.md)] corrente quando si usa l'opzione **-f** .</span><span class="sxs-lookup"><span data-stu-id="2520c-160">Is the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements to write to the current [!INCLUDE[tsql](../includes/tsql-md.md)] script file when the **-f** option is used.</span></span> <span data-ttu-id="2520c-161">Se il numero di istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] supera il valore di *number_of_statements*, viene creato un nuovo file script [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2520c-161">When the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements exceeds *number_of_statements*, a new [!INCLUDE[tsql](../includes/tsql-md.md)] script file is created.</span></span>  
  
 <span data-ttu-id="2520c-162">**-c**</span><span class="sxs-lookup"><span data-stu-id="2520c-162">**-c**</span></span>  
 <span data-ttu-id="2520c-163">Esegue il confronto per individuare eventuali differenze a livello di colonna.</span><span class="sxs-lookup"><span data-stu-id="2520c-163">Compare column-level differences.</span></span>  
  
 <span data-ttu-id="2520c-164">**-dt**</span><span class="sxs-lookup"><span data-stu-id="2520c-164">**-dt**</span></span>  
 <span data-ttu-id="2520c-165">Elimina la tabella dei risultati specificata da *table_name*se la tabella esiste già.</span><span class="sxs-lookup"><span data-stu-id="2520c-165">Drop the result table specified by *table_name*, if the table already exists.</span></span>  
  
 <span data-ttu-id="2520c-166">**-et** *table_name*</span><span class="sxs-lookup"><span data-stu-id="2520c-166">**-et** *table_name*</span></span>  
 <span data-ttu-id="2520c-167">Specifica il nome della tabella dei risultati da creare.</span><span class="sxs-lookup"><span data-stu-id="2520c-167">Specifies the name of the result table to create.</span></span> <span data-ttu-id="2520c-168">Se questa tabella esiste già, è necessario usare l'opzione **-DT** . In caso contrario, l'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2520c-168">If this table already exists, **-DT** must be used or the operation will fail.</span></span>  
  
 <span data-ttu-id="2520c-169">**-f** [ *file_name* ]</span><span class="sxs-lookup"><span data-stu-id="2520c-169">**-f** [ *file_name* ]</span></span>  
 <span data-ttu-id="2520c-170">Genera uno script [!INCLUDE[tsql](../includes/tsql-md.md)] per ripristinare la convergenza tra la tabella nel server di destinazione e quella nel server di origine.</span><span class="sxs-lookup"><span data-stu-id="2520c-170">Generates a [!INCLUDE[tsql](../includes/tsql-md.md)] script to bring the table at the destination server into convergence with the table at the source server.</span></span> <span data-ttu-id="2520c-171">È possibile specificare facoltativamente un nome e un percorso per il file script [!INCLUDE[tsql](../includes/tsql-md.md)] generato.</span><span class="sxs-lookup"><span data-stu-id="2520c-171">You can optionally specify a name and path for the generated [!INCLUDE[tsql](../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="2520c-172">Se *file_name* viene omesso, il file script [!INCLUDE[tsql](../includes/tsql-md.md)] verrà generato nella directory in cui si esegue l'utilità.</span><span class="sxs-lookup"><span data-stu-id="2520c-172">If *file_name* is not specified, the [!INCLUDE[tsql](../includes/tsql-md.md)] script file is generated in the directory where the utility runs.</span></span>  
  
 <span data-ttu-id="2520c-173">**-o** *output_file_name*</span><span class="sxs-lookup"><span data-stu-id="2520c-173">**-o** *output_file_name*</span></span>  
 <span data-ttu-id="2520c-174">Nome e percorso completi del file di output.</span><span class="sxs-lookup"><span data-stu-id="2520c-174">Is the full name and path of the output file.</span></span>  
  
 <span data-ttu-id="2520c-175">**-q**</span><span class="sxs-lookup"><span data-stu-id="2520c-175">**-q**</span></span>  
 <span data-ttu-id="2520c-176">Esegue un confronto rapido mediante il confronto solo dei conteggi delle righe e degli schemi.</span><span class="sxs-lookup"><span data-stu-id="2520c-176">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
 <span data-ttu-id="2520c-177">**-rc** *number_of_retries*</span><span class="sxs-lookup"><span data-stu-id="2520c-177">**-rc** *number_of_retries*</span></span>  
 <span data-ttu-id="2520c-178">Numero di tentativi di esecuzione di un'operazione non riuscita compiuti dall'utilità.</span><span class="sxs-lookup"><span data-stu-id="2520c-178">Number of times that the utility retries a failed operation.</span></span>  
  
 <span data-ttu-id="2520c-179">**-ri**  *retry_interval*</span><span class="sxs-lookup"><span data-stu-id="2520c-179">**-ri**  *retry_interval*</span></span>  
 <span data-ttu-id="2520c-180">Intervallo espresso in secondi tra i vari tentativi.</span><span class="sxs-lookup"><span data-stu-id="2520c-180">Interval, in seconds, to wait between retries.</span></span>  
  
 <span data-ttu-id="2520c-181">**-strict**</span><span class="sxs-lookup"><span data-stu-id="2520c-181">**-strict**</span></span>  
 <span data-ttu-id="2520c-182">Gli schemi di origine e di destinazione vengono confrontati rigorosamente.</span><span class="sxs-lookup"><span data-stu-id="2520c-182">Source and destination schema are strictly compared.</span></span>  
  
 <span data-ttu-id="2520c-183">**-t** *connection_timeouts*</span><span class="sxs-lookup"><span data-stu-id="2520c-183">**-t** *connection_timeouts*</span></span>  
 <span data-ttu-id="2520c-184">Imposta il periodo di timeout della connessione, espresso in secondi, per le connessioni al server di origine e al server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2520c-184">Sets the connection timeout period, in seconds, for connections to the source server and destination server.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2520c-185">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2520c-185">Return Value</span></span>  
  
|<span data-ttu-id="2520c-186">valore</span><span class="sxs-lookup"><span data-stu-id="2520c-186">Value</span></span>|<span data-ttu-id="2520c-187">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2520c-187">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2520c-188">**0**</span><span class="sxs-lookup"><span data-stu-id="2520c-188">**0**</span></span>|<span data-ttu-id="2520c-189">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="2520c-189">Success</span></span>|  
|<span data-ttu-id="2520c-190">**1**</span><span class="sxs-lookup"><span data-stu-id="2520c-190">**1**</span></span>|<span data-ttu-id="2520c-191">Errore critico</span><span class="sxs-lookup"><span data-stu-id="2520c-191">Critical error</span></span>|  
|<span data-ttu-id="2520c-192">**2**</span><span class="sxs-lookup"><span data-stu-id="2520c-192">**2**</span></span>|<span data-ttu-id="2520c-193">Differenze tra tabelle</span><span class="sxs-lookup"><span data-stu-id="2520c-193">Table differences</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2520c-194">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2520c-194">Remarks</span></span>  
 <span data-ttu-id="2520c-195">L'utilità **tablediff** non può essere usata con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Server non.</span><span class="sxs-lookup"><span data-stu-id="2520c-195">The **tablediff** utility cannot be used with non-[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="2520c-196">Le tabelle contenenti colonne con il tipo di dati `sql_variant` non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="2520c-196">Tables with `sql_variant` data type columns are not supported.</span></span>  
  
 <span data-ttu-id="2520c-197">Per impostazione predefinita, l'utilità **tablediff** supporta i mapping dei tipi di dati tra colonne di origine e di destinazione elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="2520c-197">By default, the **tablediff** utility supports the following data type mappings between source and destination columns.</span></span>  
  
|<span data-ttu-id="2520c-198">Tipo di dati di origine</span><span class="sxs-lookup"><span data-stu-id="2520c-198">Source data type</span></span>|<span data-ttu-id="2520c-199">Tipo di dati di destinazione</span><span class="sxs-lookup"><span data-stu-id="2520c-199">Destination data type</span></span>|  
|----------------------|---------------------------|  
|`tinyint`|<span data-ttu-id="2520c-200">`smallint`, `int` o `bigint`</span><span class="sxs-lookup"><span data-stu-id="2520c-200">`smallint`, `int`, or `bigint`</span></span>|  
|`smallint`|<span data-ttu-id="2520c-201">`int` o `bigint`</span><span class="sxs-lookup"><span data-stu-id="2520c-201">`int` or `bigint`</span></span>|  
|`int`|`bigint`|  
|`timestamp`|`varbinary`|  
|`varchar(max)`|`text`|  
|`nvarchar(max)`|`ntext`|  
|`varbinary(max)`|`image`|  
|`text`|`varchar(max)`|  
|`ntext`|`nvarchar(max)`|  
|`image`|`varbinary(max)`|  
  
 <span data-ttu-id="2520c-202">Usare l'opzione **-strict** per disabilitare questi mapping ed eseguire una convalida di tipo strict.</span><span class="sxs-lookup"><span data-stu-id="2520c-202">Use the **-strict** option to disallow these mappings and perform a strict validation.</span></span>  
  
 <span data-ttu-id="2520c-203">La tabella di origine utilizzata per il confronto deve contenere almeno una chiave primaria, un'identità o una colonna ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="2520c-203">The source table in the comparison must contain at least one primary key, identity, or ROWGUID column.</span></span> <span data-ttu-id="2520c-204">Se si usa l'opzione **-strict** , anche la tabella di destinazione deve contenere una chiave primaria, un'identità o una colonna ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="2520c-204">When you use the **-strict** option, the destination table must also have a primary key, identity, or ROWGUID column.</span></span>  
  
 <span data-ttu-id="2520c-205">Lo script [!INCLUDE[tsql](../includes/tsql-md.md)] generato per rendere convergente la tabella di destinazione non include i tipi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="2520c-205">The [!INCLUDE[tsql](../includes/tsql-md.md)] script generated to bring the destination table into convergence does not include the following data types:</span></span>  
  
-   `varchar(max)`  
  
-   `nvarchar(max)`  
  
-   `varbinary(max)`  
  
-   `timestamp`  
  
-   <span data-ttu-id="2520c-206">**xml**</span><span class="sxs-lookup"><span data-stu-id="2520c-206">**xml**</span></span>  
  
-   `text`  
  
-   `ntext`  
  
-   `image`  
  
## <a name="permissions"></a><span data-ttu-id="2520c-207">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2520c-207">Permissions</span></span>  
 <span data-ttu-id="2520c-208">Per confrontare tabelle, è necessario disporre delle autorizzazioni SELECT ALL sugli oggetti tabella da confrontare.</span><span class="sxs-lookup"><span data-stu-id="2520c-208">To compare tables, you need SELECT ALL permissions on the table objects being compared.</span></span>  
  
 <span data-ttu-id="2520c-209">Per usare l'opzione **-et** , è necessario essere membro del ruolo predefinito del database db_owner oppure disporre almeno dell'autorizzazione CREATE TABLE nel database di sottoscrizione e dell'autorizzazione ALTER per lo schema del proprietario della destinazione nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2520c-209">To use the **-et** option, you must be a member of the db_owner fixed database role, or at least have CREATE TABLE permission in the subscription database and ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="2520c-210">Per usare l'opzione **-dt** , è necessario essere membro del ruolo predefinito del database db_owner oppure disporre almeno dell'autorizzazione ALTER per lo schema del proprietario della destinazione nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2520c-210">To use the **-dt** option, you must be a member of the db_owner fixed database role, or at least have ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="2520c-211">Per usare l'opzione **-o** oppure **-f** , è necessario avere autorizzazioni di scrittura per il percorso della directory di file specificato.</span><span class="sxs-lookup"><span data-stu-id="2520c-211">To use the **-o** or **-f** options, you must have write permissions to the specified file directory location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2520c-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2520c-212">See Also</span></span>  
 [<span data-ttu-id="2520c-213">Confronto di tabelle replicate al fine di individuare le differenze &#40;programmazione della replica&#41;</span><span class="sxs-lookup"><span data-stu-id="2520c-213">Compare Replicated Tables for Differences &#40;Replication Programming&#41;</span></span>](../relational-databases/replication/administration/compare-replicated-tables-for-differences-replication-programming.md)  
  
  
