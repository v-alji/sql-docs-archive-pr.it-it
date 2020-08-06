---
title: Modifica di tabelle con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 690b70b7-5be1-4014-af97-54e531997839
author: rothja
ms.author: jroth
ms.openlocfilehash: 4eedc6fdb45efc6c87765cd2208ead90c1887c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636717"
---
# <a name="altering-memory-optimized-tables"></a><span data-ttu-id="f875f-102">Modifica di tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="f875f-102">Altering Memory-Optimized Tables</span></span>
  <span data-ttu-id="f875f-103">L'esecuzione di operazioni ALTER nelle tabelle ottimizzate per la memoria non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f875f-103">Performing ALTER operations on memory-optimized tables is not supported.</span></span> <span data-ttu-id="f875f-104">Sono incluse le operazioni come la modifica di bucket_count oppure l'aggiunta e la rimozione di un indice o di una colonna.</span><span class="sxs-lookup"><span data-stu-id="f875f-104">This includes such operations as changing the bucket_count, adding or removing an index, and adding or removing a column.</span></span> <span data-ttu-id="f875f-105">In questo argomento vengono fornite le linee guida su come aggiornare le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="f875f-105">This topic provides guidelines on how to update memory-optimized tables.</span></span>  
  
## <a name="updating-the-definition-of-a-memory-optimized-table"></a><span data-ttu-id="f875f-106">Aggiornamento della definizione di una tabella con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="f875f-106">Updating the Definition of a Memory-Optimized Table</span></span>  
 <span data-ttu-id="f875f-107">L'aggiornamento della definizione di una tabella ottimizzata per la memoria richiede la creazione di una nuova tabella con la definizione della tabella aggiornata e la copia dei dati nella nuova tabella, quindi sarà possibile utilizzare la nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="f875f-107">Updating the definition of a memory-optimized table requires you to create a new table with the updated table definition, copy the data to the new table, and start using the new table.</span></span> <span data-ttu-id="f875f-108">A meno che la tabella sia di sola lettura, questa operazione richiede l'arresto del carico di lavoro nella tabella per essere certi che non vengano apportate modifiche alla tabella mentre viene eseguita la copia dei dati.</span><span class="sxs-lookup"><span data-stu-id="f875f-108">Unless the table is read-only, this requires stopping the workload on the table, to ensure no changes are made to the table while the data copy is performed.</span></span>  
  
 <span data-ttu-id="f875f-109">Nella procedura riportata di seguito vengono illustrati i passaggi necessari per aggiornare una tabella.</span><span class="sxs-lookup"><span data-stu-id="f875f-109">The following procedure outlines the steps required to update a table.</span></span> <span data-ttu-id="f875f-110">In questo esempio, l'aggiornamento aggiunge un indice.</span><span class="sxs-lookup"><span data-stu-id="f875f-110">In this example, the update adds an index.</span></span> <span data-ttu-id="f875f-111">In questa procedura viene mantenuto il nome della tabella e vengono richieste due operazioni di copia di dati: una volta in una tabella temporanea e una volta nella nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="f875f-111">This procedure preserves the name of the table and requires two data copy operations: once to a temporary table, and once to the new table.</span></span> <span data-ttu-id="f875f-112">La modifica dell'elemento bucket_count di un indice oppure l'aggiunta o la rimozione di una colonna viene eseguita nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="f875f-112">Changing the bucket_count of an index or adding or removing a column is performed the same way.</span></span>  
  
1.  <span data-ttu-id="f875f-113">Arrestare il carico di lavoro nella tabella.</span><span class="sxs-lookup"><span data-stu-id="f875f-113">Stop the workload on the table.</span></span>  
  
2.  <span data-ttu-id="f875f-114">Generare lo script per la tabella e aggiungere il nuovo indice allo script.</span><span class="sxs-lookup"><span data-stu-id="f875f-114">Generate script for the table and add the new index to the script.</span></span>  
  
3.  <span data-ttu-id="f875f-115">Generare lo script per gli oggetti associati allo schema (principalmente stored procedure compilate in modo nativo) che fanno riferimento a T e alle relative autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f875f-115">Generate script for the schema-bound objects (mainly natively compiled stored procedures) referencing T and their permissions.</span></span>  
  
     <span data-ttu-id="f875f-116">Per trovare gli oggetti associati allo schema che fanno riferimento alla tabella utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="f875f-116">The schema-bound objects referencing the table can be found using the following query:</span></span>  
  
    ```sql  
    declare @t nvarchar(255) = N'<table name>'  
  
    select r.referencing_schema_name, r.referencing_entity_name  
    from sys.dm_sql_referencing_entities (@t, 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
    where r.is_caller_dependent = 0 and m.is_schema_bound=1;  
    ```  
  
     <span data-ttu-id="f875f-117">È possibile generare uno script delle autorizzazioni di una stored procedure utilizzando la seguente query [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f875f-117">The permissions of a stored procedure can be scripted using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
    ```sql  
    declare @sp nvarchar(255) = N'<procedure name>'  
    declare @permissions nvarchar(max) = N''  
  
    select @permissions += dp.state_desc + N' ' + dp.permission_name + N' ON ' +   
       quotename(schema_name(o.schema_id)) + N'.' + quotename(o.name) + N' TO ' +  
       quotename(u.name) + N'; ' + char(13)  
    from sys.database_permissions as dp  
  
    join sys.database_principals as u  
       on u.principal_id = dp.grantee_principal_id  
  
    join sys.objects as o  
       on o.object_id = dp.major_id  
    where dp.class = 1 /* object */  
       and dp.minor_id = 0 and o.object_id=object_id(@sp);  
  
    select @permissions  
    ```  
  
4.  <span data-ttu-id="f875f-118">Creare una copia della tabella e copiare i dati dalla tabella originale alla copia della tabella.</span><span class="sxs-lookup"><span data-stu-id="f875f-118">Create a copy of the table and copy the data from the original table to the copy of the table.</span></span> <span data-ttu-id="f875f-119">La copia può essere creata utilizzando il seguente [!INCLUDE[tsql](../../includes/tsql-md.md)] <sup>1</sup>.</span><span class="sxs-lookup"><span data-stu-id="f875f-119">The copy can be created using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]<sup>1</sup>.</span></span>  
  
    ```sql  
    select * into dbo.T_copy from dbo.T  
    ```  
  
     <span data-ttu-id="f875f-120">Se la memoria disponibile è sufficiente, `T_copy` può essere una tabella ottimizzata per la memoria, che rende più veloce la copia dei dati.<sup> 2</sup></span><span class="sxs-lookup"><span data-stu-id="f875f-120">If there is enough available memory, `T_copy` could be a memory-optimized table, which makes the data copy faster.<sup>2</sup></span></span>  
  
5.  <span data-ttu-id="f875f-121">Eliminare gli oggetti associati allo schema che fanno riferimento alla tabella originale.</span><span class="sxs-lookup"><span data-stu-id="f875f-121">Drop the schema-bound objects referencing the original table.</span></span>  
  
6.  <span data-ttu-id="f875f-122">Eliminare la tabella originale.</span><span class="sxs-lookup"><span data-stu-id="f875f-122">Drop the original table.</span></span>  
  
7.  <span data-ttu-id="f875f-123">Creare la nuova tabella (`T`) con lo script che contiene il nuovo indice.</span><span class="sxs-lookup"><span data-stu-id="f875f-123">Create the new table (`T`) with the script containing the new index.</span></span>  
  
8.  <span data-ttu-id="f875f-124">Copiare i dati da `T_copy` a `T`.</span><span class="sxs-lookup"><span data-stu-id="f875f-124">Copy the data from `T_copy` to `T`.</span></span>  
  
9. <span data-ttu-id="f875f-125">Ricreare gli oggetti associati allo schema a cui si fa riferimento e applicare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f875f-125">Recreate the referencing schema-bound objects and apply the permissions.</span></span>  
  
10. <span data-ttu-id="f875f-126">Avviare il carico di lavoro su `T`.</span><span class="sxs-lookup"><span data-stu-id="f875f-126">Start the workload on `T`.</span></span>  
  
 <span data-ttu-id="f875f-127"><sup>1</sup> si noti che `T_copy` in questo esempio è salvato in modo permanente su disco.</span><span class="sxs-lookup"><span data-stu-id="f875f-127"><sup>1</sup> Note that `T_copy` is persisted to disk in this example.</span></span> <span data-ttu-id="f875f-128">Se un backup di `T` è disponibile, l'utilità `T_copy` può essere una tabella temporanea o non durevole.</span><span class="sxs-lookup"><span data-stu-id="f875f-128">If a backup of `T` is available, `T_copy` could be a temporary or a non-durable table.</span></span>  
  
 <span data-ttu-id="f875f-129"><sup>2</sup> è necessario disporre di memoria sufficiente per `T_copy` .</span><span class="sxs-lookup"><span data-stu-id="f875f-129"><sup>2</sup> There must be enough memory for `T_copy`.</span></span> <span data-ttu-id="f875f-130">La memoria non viene liberata immediatamente con `DROP TABLE`.</span><span class="sxs-lookup"><span data-stu-id="f875f-130">Memory is not freed immediately on `DROP TABLE`.</span></span> <span data-ttu-id="f875f-131">Se `T_copy` è con ottimizzazione per la memoria, deve essere disponibile la memoria sufficiente per due copie aggiuntive di `T`.</span><span class="sxs-lookup"><span data-stu-id="f875f-131">If `T_copy` is memory optimized, there needs to be enough memory for two additional copies of `T`.</span></span> <span data-ttu-id="f875f-132">Se `T_copy` è basata su disco, deve essere disponibile la memoria sufficiente per una sola copia aggiuntiva di `T`, perché Garbage Collector richiede l'aggiornamento dopo l'eliminazione della versione precedente di `T`.</span><span class="sxs-lookup"><span data-stu-id="f875f-132">If `T_copy` is a disk-based table, there only needs to be enough memory for one additional copy of `T`, due to the garbage collector needing to catch up after dropping the old version of `T`.</span></span>  
  
## <a name="changing-schema-powershell"></a><span data-ttu-id="f875f-133">Modifica dello schema (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f875f-133">Changing Schema (PowerShell)</span></span>  
 <span data-ttu-id="f875f-134">Gli script di PowerShell seguenti preparano e generano le modifiche dello schema creando lo script della tabella e delle autorizzazioni associate.</span><span class="sxs-lookup"><span data-stu-id="f875f-134">The following PowerShell scripts prepare and generate for schema changes by scripting the table and associated permissions.</span></span>  
  
```powershell
prepare_schema_change.ps1 <serverName> <databaseName> <schemaName> <tableName>
```
  
 <span data-ttu-id="f875f-135">Questo script accetta come argomento una tabella e crea lo script dell'oggetto e delle relative autorizzazioni nonché degli oggetti associati allo schema a cui si fa riferimento e delle relative autorizzazioni nella cartella corrente.</span><span class="sxs-lookup"><span data-stu-id="f875f-135">This script takes as arguments a table, and scripts the object and its permissions and referencing schema-bound objects and their permissions in the current folder.</span></span> <span data-ttu-id="f875f-136">In totale vengono generati 7 script per aggiornare lo schema della tabella di input:</span><span class="sxs-lookup"><span data-stu-id="f875f-136">A total of 7 scripts are generated for updating the schema of the input table:</span></span>  
  
-   <span data-ttu-id="f875f-137">Copiare i dati in una tabella temporanea (heap).</span><span class="sxs-lookup"><span data-stu-id="f875f-137">Copy data to a temporary table (a heap).</span></span>  
  
-   <span data-ttu-id="f875f-138">Eliminare gli oggetti associati allo schema che fanno riferimento alla tabella.</span><span class="sxs-lookup"><span data-stu-id="f875f-138">Drop schema-bound objects referencing the table.</span></span>  
  
-   <span data-ttu-id="f875f-139">Eliminare la tabella.</span><span class="sxs-lookup"><span data-stu-id="f875f-139">Drop the table.</span></span>  
  
-   <span data-ttu-id="f875f-140">Ricreare la tabella con il nuovo schema e riapplicare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f875f-140">Recreate the table with the new schema and reapply permissions.</span></span>  
  
-   <span data-ttu-id="f875f-141">Copiare i dati dalla tabella temporanea nella tabella ricreata.</span><span class="sxs-lookup"><span data-stu-id="f875f-141">Copy data from the temporary table to the recreated table.</span></span>  
  
-   <span data-ttu-id="f875f-142">Ricreare gli oggetti associati allo schema che fanno riferimento alla tabella e alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f875f-142">Recreate schema-bound objects referencing the table and their permissions.</span></span>  
  
-   <span data-ttu-id="f875f-143">Eliminare la tabella temporanea.</span><span class="sxs-lookup"><span data-stu-id="f875f-143">Drop the temporary table.</span></span>  
  
 <span data-ttu-id="f875f-144">Lo script per il passaggio 4 deve essere aggiornato per riflettere le modifiche apportate allo schema.</span><span class="sxs-lookup"><span data-stu-id="f875f-144">The script for step 4 should be updated to reflect the desired schema changes.</span></span> <span data-ttu-id="f875f-145">Se sono state apportate modifiche alle colonne della tabella, gli script per i passaggi 5 (copiare i dati dalla tabella temporanea) e 6 (ricreare le stored procedure) devono essere aggiornati in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="f875f-145">If there are any changes in the columns of the table, the scripts for steps 5 (copy data from temporary table) and 6 (recreate stored procedures) should be updated as necessary.</span></span>  
  
```powershell
# Prepare for schema changes by scripting out the table, as well as associated permissions
# Usage: prepare_schema_change.ps1 server_name db_name schema_name table_name  
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage prepare_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
$object_heap = "$object$(Get-Random)"  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$scripter = New-Object ("Microsoft.SqlServer.Management.SMO.Scripter") ($server)  
  
## initialize table variable  
$tableUrn = $server.Databases[$database].Tables[$object, $schema]  
if($tableUrn.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
## initialize scripting object  
$scriptingOptions = New-Object ("Microsoft.SqlServer.Management.SMO.ScriptingOptions")
$scriptingOptions.Permissions = $True  
$scriptingOptions.ScriptDrops = $True  
  
$scripter.Options = $scriptingOptions;  
  
Write-Host "(1) Scripting SELECT INTO $object_heap for table [$object] to 1_copy_to_heap_for_$schema`_$object.sql"  
Echo "SELECT * INTO $schema.$object_heap FROM $schema.$object WITH (SNAPSHOT)" | Out-File "1_copy_to_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Scripting DROP for procs schema-bound to [$object] 2_drop_procs_$schema`_$object.sql"  
## query referencing schema-bound objects  
$dt = $server.Databases[$database].ExecuteWithResults("select r.referencing_schema_name, r.referencing_entity_name  
from sys.dm_sql_referencing_entities ('$schema.$object', 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
where r.is_caller_dependent = 0 and m.is_schema_bound=1;")  
  
## initialize out file  
Echo "" | Out-File "2_drop_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script object   
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      $scripter.Script($so) | Out-File -Append "2_drop_procs_$schema`_$object.sql"  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
Write-Host "(3) Scripting DROP table for [$object] to 3_drop_table_$schema`_$object.sql"
$scripter.Script($tableUrn) | Out-File "3_drop_table_$schema`_$object.sql";
Write-Host "--done--"  
Write-Host ""  
  
## now script creates  
$scriptingOptions.ScriptDrops = $False  
  
Write-Host "(4) Scripting CREATE table and permissions for [$object] to !please_edit_4_create_table_$schema`_$object.sql"  
Write-Host "***** rename this script to 4_create_table.sql after completing the updates to the schema"
$scripter.Script($tableUrn) | Out-File "!please_edit_4_create_table_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Scripting INSERT INTO table from heap and UPDATE STATISTICS for [$object] to 5_copy_from_heap_$schema`_$object.sql"  
Write-Host "[update this script if columns are added to or removed from the table]"  
Echo "INSERT INTO [$schema].[$object] SELECT * FROM [$schema].[$object_heap]; UPDATE STATISTICS [$schema].[$object] WITH FULLSCAN, NORECOMPUTE" | Out-File "5_copy_from_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Scripting CREATE PROC and permissions for procedures schema-bound to [$object] to 6_create_procs_$schema`_$object.sql"  
Write-Host "[update the procedure definitions if columns are renamed or removed]"  
## initialize out file  
Echo "" | Out-File "6_create_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script the schema-bound object  
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      ForEach($s In $scripter.Script($so))  
        {  
            Echo $s | Out-File -Append "6_create_procs_$schema`_$object.sql"  
            Echo "GO" | Out-File -Append "6_create_procs_$schema`_$object.sql"  
        }  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Scripting DROP $object_heap to 7_drop_heap_$schema`_$object.sql"  
Echo "DROP TABLE $schema.$object_heap" | Out-File "7_drop_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
```  
  
 <span data-ttu-id="f875f-146">Il seguente script di PowerShell esegue le modifiche dello schema che erano state inserite nello script nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="f875f-146">The following PowerShell script executes the schema changes that were scripted in the previous sample.</span></span> <span data-ttu-id="f875f-147">Questo script accetta come argomento una tabella ed esegue gli script delle modifiche dello schema generate per la tabella e le stored procedure associate.</span><span class="sxs-lookup"><span data-stu-id="f875f-147">This script takes as argument a table, and executes the schema change scripts that were generated for that table and the associated stored procedures.</span></span>  
  
 <span data-ttu-id="f875f-148">Utilizzo: execute_schema_change.ps1 *server_name \* \* db_name `schema_name` table_name*</span><span class="sxs-lookup"><span data-stu-id="f875f-148">Usage: execute_schema_change.ps1 *server_name\*\*db_name`schema_name`table_name*</span></span>  
  
```powershell
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage execute_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$database = $server.Databases[$database]  
$table = $database.Tables[$object, $schema]  
if($table.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
$1 = Get-Item "1_copy_to_heap_$schema`_$object.sql"  
$2 = Get-Item "2_drop_procs_$schema`_$object.sql"  
$3 = Get-Item "3_drop_table_$schema`_$object.sql"  
$4 = Get-Item "4_create_table_$schema`_$object.sql"  
$5 = Get-Item "5_copy_from_heap_$schema`_$object.sql"  
$6 = Get-Item "6_create_procs_$schema`_$object.sql"  
$7 = Get-Item "7_drop_heap_$schema`_$object.sql"  
  
Write-Host "(1) Running SELECT INTO heap for table [$object] from 1_copy_to_heap_for_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $1.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Running DROP for procs schema-bound from [$object] 2_drop_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $2.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(3) Running DROP table for [$object] to 4_drop_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $3.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(4) Running CREATE table and permissions for [$object] from 4_create_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $4.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Running INSERT INTO table from heap for [$object] and UPDATE STATISTICS from 5_copy_from_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $5.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Running CREATE PROC and permissions for procedures schema-bound to [$object] from 6_create_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $6.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Running DROP heap from 7_drop_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $7.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
```  
  
## <a name="see-also"></a><span data-ttu-id="f875f-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f875f-149">See Also</span></span>  
 [<span data-ttu-id="f875f-150">Tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="f875f-150">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
