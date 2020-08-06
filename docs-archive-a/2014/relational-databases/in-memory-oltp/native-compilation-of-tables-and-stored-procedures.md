---
title: Compilazione nativa di tabelle e stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5880fbd9-a23e-464a-8b44-09750eeb2dad
author: rothja
ms.author: jroth
ms.openlocfilehash: 32c5b04610d894e06278fbeecdaf3bbebe850d60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629825"
---
# <a name="native-compilation-of-tables-and-stored-procedures"></a><span data-ttu-id="7356f-102">Compilazione nativa di tabelle e stored procedure</span><span class="sxs-lookup"><span data-stu-id="7356f-102">Native Compilation of Tables and Stored Procedures</span></span>
  <span data-ttu-id="7356f-103">Con OLTP in memoria viene introdotto il concetto di compilazione nativa.</span><span class="sxs-lookup"><span data-stu-id="7356f-103">In-Memory OLTP introduces the concept of native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7356f-104">può compilare in modo nativo stored procedure che accedono alle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="7356f-104">can natively compile stored procedures that access memory-optimized tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7356f-105">è anche in grado di compilare in modo nativo tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="7356f-105">is also able to natively compile memory-optimized tables.</span></span> <span data-ttu-id="7356f-106">Con la compilazione nativa si accede ai dati più velocemente e si eseguono le query in modo più efficiente rispetto al tradizionale [!INCLUDE[tsql](../../includes/tsql-md.md)]interpretato.</span><span class="sxs-lookup"><span data-stu-id="7356f-106">Native compilation allows faster data access and more efficient query execution than interpreted (traditional) [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7356f-107">La compilazione nativa di tabelle e stored procedure produce DLL.</span><span class="sxs-lookup"><span data-stu-id="7356f-107">Native compilation of tables and stored procedures produce DLLs.</span></span>  
  
 <span data-ttu-id="7356f-108">È anche supportata la compilazione nativa dei tipi di tabella con ottimizzazione per la memoria.</span><span class="sxs-lookup"><span data-stu-id="7356f-108">Native compilation of memory optimized table types is also supported.</span></span> <span data-ttu-id="7356f-109">Per altre informazioni, vedere [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span><span class="sxs-lookup"><span data-stu-id="7356f-109">For more information, see [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span></span>  
  
 <span data-ttu-id="7356f-110">La compilazione nativa si riferisce al processo di conversione dei costrutti di programmazione in codice nativo, costituito da istruzioni del processore senza la necessità di ulteriore compilazione o interpretazione.</span><span class="sxs-lookup"><span data-stu-id="7356f-110">Native compilation refers to the process of converting programming constructs to native code, consisting of processor instructions without the need for further compilation or interpretation.</span></span>  
  
 <span data-ttu-id="7356f-111">OLTP in memoria compila le tabelle ottimizzate per la memoria quando vengono create e le stored procedure compilate in modo nativo quando vengono caricate nelle DLL native.</span><span class="sxs-lookup"><span data-stu-id="7356f-111">In-Memory OLTP compiles memory-optimized tables when they are created, and natively compiled stored procedures when they are loaded to native DLLs.</span></span> <span data-ttu-id="7356f-112">Inoltre, le DLL vengono ricompilate dopo il riavvio di un database o di un server.</span><span class="sxs-lookup"><span data-stu-id="7356f-112">In addition, the DLLs are recompiled after a database or server restart.</span></span> <span data-ttu-id="7356f-113">Le informazioni necessarie per ricreare le DLL vengono archiviate nei metadati del database.</span><span class="sxs-lookup"><span data-stu-id="7356f-113">The information necessary to recreate the DLLs is stored in the database metadata.</span></span> <span data-ttu-id="7356f-114">Le DLL non fanno parte del database, sebbene siano associate al database.</span><span class="sxs-lookup"><span data-stu-id="7356f-114">The DLLs are not part of the database, though they are associated with the database.</span></span> <span data-ttu-id="7356f-115">Ad esempio, le DLL non sono incluse nei backup del database.</span><span class="sxs-lookup"><span data-stu-id="7356f-115">For example, the DLLs are not included in database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7356f-116">Le tabelle con ottimizzazione per la memoria vengono ricompilate durante un riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="7356f-116">Memory-optimized tables are recompiled during a server restart.</span></span> <span data-ttu-id="7356f-117">Per velocizzare il recupero del database, le stored procedure compilate in modo nativo non vengono ricompilate durante un riavvio del server, ma vengono compilate al momento della prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7356f-117">To speed up database recovery, natively compiled stored procedures are not recompiled during a server restart, they are compiled at the time of first execution.</span></span> <span data-ttu-id="7356f-118">A causa di questa compilazione posticipata, le stored procedure compilate in modo nativo vengono visualizzate solo quando si chiama [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) dopo la prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7356f-118">As a result of this deferred compilation, natively compiled stored procedures only appear when calling [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) after first execution.</span></span>  
  
## <a name="maintenance-of-in-memory-oltp-dlls"></a><span data-ttu-id="7356f-119">Manutenzione delle DLL di OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="7356f-119">Maintenance of In-Memory OLTP DLLs</span></span>  
 <span data-ttu-id="7356f-120">La query seguente indica che tutte le DLL di tabelle e stored procedure vengono attualmente caricate in memoria nel server:</span><span class="sxs-lookup"><span data-stu-id="7356f-120">The following query shows all table and stored procedure DLLs currently loaded in memory on the server:</span></span>  
  
```sql  
SELECT name, description FROM sys.dm_os_loaded_modules  
where description = 'XTP Native DLL'  
```  
  
 <span data-ttu-id="7356f-121">Gli amministratori di database non devono gestire i file generati da una compilazione nativa.</span><span class="sxs-lookup"><span data-stu-id="7356f-121">Database administrators do not need to maintain files that are generated by a native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7356f-122">rimuove automaticamente i file generati non più necessari.</span><span class="sxs-lookup"><span data-stu-id="7356f-122">automatically removes generated files that are no longer needed.</span></span> <span data-ttu-id="7356f-123">Ad esempio, i file generati verranno eliminati quando una tabella e una stored procedure vengono eliminate o nel caso in cui un database venga eliminato.</span><span class="sxs-lookup"><span data-stu-id="7356f-123">For example, generated files will be deleted when a table and stored procedure is deleted, or if a database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7356f-124">Se la compilazione ha esito negativo o viene interrotta, alcuni file generati non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="7356f-124">If compilation fails or is interrupted, some generated files are not removed.</span></span> <span data-ttu-id="7356f-125">Questi file vengono lasciati intenzionalmente per motivi di supporto e vengono rimossi quando il database viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="7356f-125">These files are intentionally left behind for supportability and are removed when the database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7356f-126">Durante l'avvio del database, SQL Server compila file DLL per tutte le tabelle necessarie per il ripristino del database.</span><span class="sxs-lookup"><span data-stu-id="7356f-126">During database startup, SQL Server compiles DLLs for all tables needed for database recovery.</span></span> <span data-ttu-id="7356f-127">Se una tabella è stata eliminata immediatamente prima di un riavvio del database, è possibile che i file checkpoint o i log delle transazioni includano ancora residui della tabella. È quindi possibile ricompilare il file DLL della tabella durante l'avvio del database.</span><span class="sxs-lookup"><span data-stu-id="7356f-127">If a table was dropped just prior to a database restart there can still be remnants of the table in the checkpoint files or the transaction log so the DLL for the table might be recompiled during database startup.</span></span> <span data-ttu-id="7356f-128">Dopo il riavvio, il file DLL verrà scaricato e i file verranno rimossi durante il normale processo di pulitura.</span><span class="sxs-lookup"><span data-stu-id="7356f-128">After restart the DLL will be unloaded and the files will be removed by the normal cleanup process.</span></span>  
  
## <a name="native-compilation-of-tables"></a><span data-ttu-id="7356f-129">Compilazione nativa di tabelle</span><span class="sxs-lookup"><span data-stu-id="7356f-129">Native Compilation of Tables</span></span>  
 <span data-ttu-id="7356f-130">Tramite la creazione di una tabella ottimizzata per la memoria mediante un'istruzione `CREATE TABLE` vengono restituite le informazioni della tabella scritte nei metadati del database e le strutture di indice e di tabella create in memoria.</span><span class="sxs-lookup"><span data-stu-id="7356f-130">Creating a memory-optimized table using the `CREATE TABLE` statement results in the table information being written to the database metadata and the table and index structures created in memory.</span></span> <span data-ttu-id="7356f-131">La tabella verrà compilata in una DLL.</span><span class="sxs-lookup"><span data-stu-id="7356f-131">The table will also be compiled to a DLL.</span></span>  
  
 <span data-ttu-id="7356f-132">Considerare il seguente script di esempio che crea un database e una tabella ottimizzata per la memoria:</span><span class="sxs-lookup"><span data-stu-id="7356f-132">Consider the following sample script, which creates a database and a memory-optimized table:</span></span>  
  
```sql  
use master  
go  
create database db1  
go  
alter database db1 add filegroup db1_mod contains memory_optimized_data  
go  
-- adapt filename as needed  
alter database db1 add file (name='db1_mod', filename='c:\data\db1_mod') to filegroup db1_mod  
go  
use db1  
go  
create table dbo.t1  
   (c1 int not null primary key nonclustered,  
    c2 INT)  
with (memory_optimized=on)  
go  
-- retrieve the path of the DLL for table t1  
select name, description FROM sys.dm_os_loaded_modules  
where name like '%xtp_t_' + cast(db_id() as varchar(10)) + '_' + cast(object_id('dbo.t1') as varchar(10)) + '.dll'  
go  
```  
  
 <span data-ttu-id="7356f-133">La creazione della tabella comporta anche la creazione della corrispondente DLL e il caricamento della DLL in memoria.</span><span class="sxs-lookup"><span data-stu-id="7356f-133">Creating the table also creates the table DLL and loads the DLL in memory.</span></span> <span data-ttu-id="7356f-134">La query DMV immediatamente dopo l'istruzione CREATE TABLE recupera il percorso della DLL della tabella.</span><span class="sxs-lookup"><span data-stu-id="7356f-134">The DMV query immediately after the CREATE TABLE statement retrieves the path of the table DLL.</span></span>  
  
 <span data-ttu-id="7356f-135">La DLL della tabella interpreta le strutture di indice e il formato di riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="7356f-135">The table DLL understands the index structures and row format of the table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7356f-136">usano la DLL per attraversare indici, recuperare righe e archiviare il contenuto delle righe.</span><span class="sxs-lookup"><span data-stu-id="7356f-136">uses the DLL for traversing indexes, retrieving rows, as well as storing the contents of the rows.</span></span>  
  
## <a name="native-compilation-of-stored-procedures"></a><span data-ttu-id="7356f-137">Compilazione nativa di stored procedure</span><span class="sxs-lookup"><span data-stu-id="7356f-137">Native Compilation of Stored Procedures</span></span>  
 <span data-ttu-id="7356f-138">Le stored procedure che sono contrassegnate con NATIVE_COMPILATION vengono compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="7356f-138">Stored procedures that are marked with NATIVE_COMPILATION are natively compiled.</span></span> <span data-ttu-id="7356f-139">Pertanto, le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] nella procedura vengono tutte compilate nel codice nativo per l'esecuzione efficiente della logica di business critica per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7356f-139">This means the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure are all compiled to native code for efficient execution of performance-critical business logic.</span></span>  
  
 <span data-ttu-id="7356f-140">Per altre informazioni sulle stored procedure compilate in modo nativo, vedere [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7356f-140">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="7356f-141">Considerare la seguente stored procedure di esempio che inserisce righe nella tabella t1 dell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="7356f-141">Consider the following sample stored procedure, which inserts rows in the table t1 from the previous example:</span></span>  
  
```sql  
create procedure dbo.native_sp  
with native_compilation, schemabinding, execute as owner  
as  
begin atomic  
with (transaction isolation level=snapshot, language=N'us_english')  
  
  declare @i int = 1000000  
  while @i > 0  
  begin  
    insert dbo.t1 values (@i, @i+1)  
    set @i -= 1  
  end  
  
end  
go  
exec dbo.native_sp  
go  
-- reset  
delete from dbo.t1  
go  
```  
  
 <span data-ttu-id="7356f-142">La DLL di native_sp può interagire direttamente con la DLL di t1 e con il motore di archiviazione di OLTP in memoria per inserire le righe il più rapidamente possibile.</span><span class="sxs-lookup"><span data-stu-id="7356f-142">The DLL for native_sp can interact directly with the DLL for t1, as well as the In-Memory OLTP storage engine, to insert the rows as fast as possible.</span></span>  
  
 <span data-ttu-id="7356f-143">Il compilatore di OLTP in memoria usano Query Optimizer per creare un piano di esecuzione efficiente per ogni query della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7356f-143">The In-Memory OLTP compiler leverages the query optimizer to create an efficient execution plan for each of the queries in the stored procedure.</span></span> <span data-ttu-id="7356f-144">Si noti che le stored procedure compilate in modo nativo non vengono automaticamente ricompilate se i dati della tabella cambiano.</span><span class="sxs-lookup"><span data-stu-id="7356f-144">Note that natively compiled stored procedures are not automatically recompiled if the data in the table changes.</span></span> <span data-ttu-id="7356f-145">Per altre informazioni sulla gestione delle statistiche e delle stored procedure con OLTP in memoria, vedere [Statistiche per tabelle con ottimizzazione per la memoria](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7356f-145">For more information on maintaining statistics and stored procedures with In-Memory OLTP see [Statistics for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="security-considerations-for-native-compilation"></a><span data-ttu-id="7356f-146">Considerazioni sulla sicurezza della compilazione nativa</span><span class="sxs-lookup"><span data-stu-id="7356f-146">Security Considerations for Native Compilation</span></span>  
 <span data-ttu-id="7356f-147">Per la compilazione nativa di tabelle e stored procedure viene usato il compilatore di OLTP in memoria.</span><span class="sxs-lookup"><span data-stu-id="7356f-147">Native compilation of tables and stored procedures uses the In-Memory OLTP compiler.</span></span> <span data-ttu-id="7356f-148">Il compilatore genera file che vengono scritti su disco e caricati in memoria.</span><span class="sxs-lookup"><span data-stu-id="7356f-148">This compiler produces files that are written to disk and loaded into memory.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7356f-149">vengono usati i seguenti meccanismi per limitare l'accesso a tali file.</span><span class="sxs-lookup"><span data-stu-id="7356f-149">uses the following mechanisms to limit access to these files.</span></span>  
  
### <a name="native-compiler"></a><span data-ttu-id="7356f-150">Compilatore nativo</span><span class="sxs-lookup"><span data-stu-id="7356f-150">Native Compiler</span></span>  
 <span data-ttu-id="7356f-151">Il file eseguibile del compilatore, nonché i file binari e i file di intestazione necessari per la compilazione nativa, vengono installati come parte dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nella cartella MSSQL\Binn\Xtp.</span><span class="sxs-lookup"><span data-stu-id="7356f-151">The compiler executable, as well as binaries and header files required for native compilation are installed as part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance under the folder MSSQL\Binn\Xtp.</span></span> <span data-ttu-id="7356f-152">Quindi, se l'istanza predefinita viene installata in c:\Program Files, i file del compilatore vengono installati in c:\Programmi \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. MSSQLSERVER\MSSQL\Binn\Xtp.</span><span class="sxs-lookup"><span data-stu-id="7356f-152">So, if the default instance is installed under C:\Program Files, the compiler files are installed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\Binn\Xtp.</span></span>  
  
 <span data-ttu-id="7356f-153">Per limitare l'accesso al compilatore, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono usati gli elenchi di controllo di accesso (ACL) per limitare l'accesso ai file binari.</span><span class="sxs-lookup"><span data-stu-id="7356f-153">To limit access to the compiler, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses access control lists (ACLs) to restrict access to binary files.</span></span> <span data-ttu-id="7356f-154">Tutti i file binari di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono protetti dalla modifica o dalla manomissione tramite gli ACL.</span><span class="sxs-lookup"><span data-stu-id="7356f-154">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries are protected against modification or tampering through ACLs.</span></span> <span data-ttu-id="7356f-155">Gli ACL del compilatore nativo limitano anche l'utilizzo del compilatore; solo gli amministratori di sistema e l'account del servizio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dispongono delle autorizzazioni di lettura ed esecuzione per i file del compilatore nativo.</span><span class="sxs-lookup"><span data-stu-id="7356f-155">The native compiler's ACLs also limit use of the compiler; only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators have read and execute permissions for native compiler files.</span></span>  
  
### <a name="files-generated-by-a-native-compilation"></a><span data-ttu-id="7356f-156">File generati da una compilazione nativa</span><span class="sxs-lookup"><span data-stu-id="7356f-156">Files Generated by a Native Compilation</span></span>  
 <span data-ttu-id="7356f-157">I file generati quando una tabella o una stored procedure viene compilata includono file DLL e file intermedi compresi i file con le estensioni seguenti: c, obj, xml e pdb.</span><span class="sxs-lookup"><span data-stu-id="7356f-157">The files produced when a table or stored procedure is compiled include the DLL and intermediate files including files with the following extensions: .c, .obj, .xml, and .pdb.</span></span> <span data-ttu-id="7356f-158">I file generati vengono salvati in una sottocartella della cartella dati predefinita.</span><span class="sxs-lookup"><span data-stu-id="7356f-158">The generated files are saved in a subfolder of the default data folder.</span></span> <span data-ttu-id="7356f-159">La sottocartella viene denominata Xtp.</span><span class="sxs-lookup"><span data-stu-id="7356f-159">The subfolder is called Xtp.</span></span> <span data-ttu-id="7356f-160">Quando si installa l'istanza predefinita con la cartella dei dati predefinita, i file generati vengono inseriti in c:\Programmi \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. MSSQLSERVER\MSSQL\DATA\Xtp.</span><span class="sxs-lookup"><span data-stu-id="7356f-160">When installing the default instance with the default data folder, the generated files are placed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\DATA\Xtp.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7356f-161">la manomissione dei file DLL generati viene impedita in tre modi:</span><span class="sxs-lookup"><span data-stu-id="7356f-161">prevents tampering with the generated DLLs in three ways:</span></span>  
  
-   <span data-ttu-id="7356f-162">Quando una tabella o una stored procedure viene compilata in una DLL, tale DLL viene immediatamente caricata in memoria e collegata al processo sqlserver.exe.</span><span class="sxs-lookup"><span data-stu-id="7356f-162">When a table or stored procedure is compiled to a DLL, this DLL is immediately loaded into memory and linked to the sqlserver.exe process.</span></span> <span data-ttu-id="7356f-163">Non è possibile modificare una DLL mentre è collegata a un processo.</span><span class="sxs-lookup"><span data-stu-id="7356f-163">A DLL cannot be modified while it is linked to a process.</span></span>  
  
-   <span data-ttu-id="7356f-164">Quando un database viene riavviato, tutte le tabelle e le stored procedure vengono ricompilate (rimosse e ricreate) in base ai metadati del database.</span><span class="sxs-lookup"><span data-stu-id="7356f-164">When a database is restarted, all tables and stored procedures are recompiled (removed and recreated) based on the database metadata.</span></span> <span data-ttu-id="7356f-165">In questo modo verranno rimosse tutte le modifiche apportate a un file generato da un agente dannoso.</span><span class="sxs-lookup"><span data-stu-id="7356f-165">This will remove any changes made to a generated file by a malicious agent.</span></span>  
  
-   <span data-ttu-id="7356f-166">I file generati sono considerati parte dei dati utente e dispongono delle stesse restrizioni di sicurezza, tramite ACL, dei file di database: solo gli amministratori di sistema e l'account del servizio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono accedere a tali file.</span><span class="sxs-lookup"><span data-stu-id="7356f-166">The generated files are considered part of user data, and have the same security restrictions, via ACLs, as database files: only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators can access these files.</span></span>  
  
 <span data-ttu-id="7356f-167">Per gestire tali file, non sono necessarie interazioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7356f-167">No user interaction is needed to manage these files.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7356f-168">verranno creati e rimossi automaticamente in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="7356f-168">will create and remove the files as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7356f-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7356f-169">See Also</span></span>  
 <span data-ttu-id="7356f-170">[Tabelle con ottimizzazione per la memoria](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="7356f-170">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="7356f-171">Stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="7356f-171">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
