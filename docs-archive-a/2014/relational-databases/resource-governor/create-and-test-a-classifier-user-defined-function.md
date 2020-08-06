---
title: Creare e testare una funzione di classificazione definita dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function create
- classifier function [SQL Server], test
- classifier function [SQL Server], create
- Resource Governor, classifier function test
ms.assetid: 7866b3c9-385b-40c6-aca5-32d3337032be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1b8e5371762e38cf2b3ac8c1d506b467dcfa7e3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715164"
---
# <a name="create-and-test-a-classifier-user-defined-function"></a><span data-ttu-id="1a4b2-102">Creare e testare una funzione di classificazione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="1a4b2-102">Create and Test a Classifier User-Defined Function</span></span>
  <span data-ttu-id="1a4b2-103">In questo argomento viene illustrato come creare e testare una funzione di classificazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-103">This topic shows how to create and test a classifier user-defined function (UDF).</span></span> <span data-ttu-id="1a4b2-104">La procedura prevede l'esecuzione di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] nell'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a4b2-104">The steps involve executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="1a4b2-105">Nell'esempio incluso nella procedura seguente vengono illustrate le diverse opzioni disponibili per la creazione di una funzione di classificazione definita dall'utente piuttosto complessa.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-105">The example shown in the following procedure illustrates the possibilities for creating a fairly complex classifier user-defined function.</span></span>  
  
 <span data-ttu-id="1a4b2-106">Nell'esempio:</span><span class="sxs-lookup"><span data-stu-id="1a4b2-106">In our example:</span></span>  
  
-   <span data-ttu-id="1a4b2-107">Vengono creati un pool di risorse (pProductionProcessing) e un gruppo del carico di lavoro (gProductionProcessing) per l'elaborazione in un ambiente di produzione durante un intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-107">A resource pool (pProductionProcessing) and workload group (gProductionProcessing) are created for production processing during a specified time range.</span></span>  
  
-   <span data-ttu-id="1a4b2-108">Vengono creati un pool di risorse (pOffHoursProcessing) e un gruppo del carico di lavoro (gOffHoursProcessing) per la gestione delle connessioni che non soddisfano i requisiti per l'elaborazione in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-108">A resource pool (pOffHoursProcessing) and workload group (gOffHoursProcessing) are created for handling connections that do not meet the requirements for production processing.</span></span>  
  
-   <span data-ttu-id="1a4b2-109">Viene creata una tabella (TblClassificationTimeTable) nel database master per indicare date e ore di inizio e di fine da valutare rispetto a una data e un'ora di accesso.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-109">A table (TblClassificationTimeTable) is created in master to hold start and end times that can be evaluated against a login time.</span></span> <span data-ttu-id="1a4b2-110">Tale tabella deve essere creata nel database master perché per le funzioni di classificazione Resource Governor utilizza l'associazione allo schema.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-110">This must be created in master because Resource Governor uses schema binding for classifier functions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1a4b2-111">Come procedura ottimale, è consigliabile non archiviare nel database master tabelle di grandi dimensioni aggiornate di frequente.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-111">As a best practice, you should not store large, frequently updated tables in master.</span></span>  
  
 <span data-ttu-id="1a4b2-112">La funzione di classificazione prolunga i tempi di accesso.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-112">The classifier function extends the login time.</span></span> <span data-ttu-id="1a4b2-113">Una funzione eccessivamente complessa può provocare il timeout degli accessi o rallentare connessioni veloci.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-113">An overly complex function can cause logins to time out or slow down fast connections.</span></span>  
  
### <a name="to-create-the-classifier-user-defined-function"></a><span data-ttu-id="1a4b2-114">Per creare la funzione di classificazione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="1a4b2-114">To create the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="1a4b2-115">Creare e configurare i nuovi pool di risorse e i nuovi gruppi del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-115">Create and configure the new resource pools and workload groups.</span></span> <span data-ttu-id="1a4b2-116">Assegnare ogni gruppo del carico di lavoro al pool di risorse appropriato.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-116">Assign each workload group to the appropriate resource pool.</span></span>  
  
    ```  
    --- Create a resource pool for production processing  
    --- and set limits.  
    USE master  
    GO  
    CREATE RESOURCE POOL pProductionProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 100,  
         MIN_CPU_PERCENT = 50  
    )  
    GO  
    --- Create a workload group for production processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gProductionProcessing  
    WITH  
    (  
         IMPORTANCE = MEDIUM  
    )  
    --- Assign the workload group to the production processing  
    --- resource pool.  
    USING pProductionProcessing  
    GO  
    --- Create a resource pool for off-hours processing  
    --- and set limits.  
  
    CREATE RESOURCE POOL pOffHoursProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 50,  
         MIN_CPU_PERCENT = 0  
    )  
    GO  
    --- Create a workload group for off-hours processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gOffHoursProcessing  
    WITH  
    (  
         IMPORTANCE = LOW  
    )  
    --- Assign the workload group to the off-hours processing  
    --- resource pool.  
    USING pOffHoursProcessing  
    GO  
    ```  
  
2.  <span data-ttu-id="1a4b2-117">Aggiornare la configurazione in memoria.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-117">Update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
3.  <span data-ttu-id="1a4b2-118">Creare una tabella e definire le ore di inizio e di fine per l'intervallo di tempo di elaborazione nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-118">Create a table and define the start and end times for the production processing time range.</span></span>  
  
    ```  
    USE master  
    GO  
    CREATE TABLE tblClassificationTimeTable  
    (  
         strGroupName     sysname          not null,  
         tStartTime       time              not null,  
         tEndTime         time              not null  
    )  
    GO  
    --- Add time values that the classifier will use to  
    --- determine the workload group for a session.  
    INSERT into tblClassificationTimeTable VALUES('gProductionProcessing', '6:35 AM', '6:15 PM')  
    go  
    ```  
  
4.  <span data-ttu-id="1a4b2-119">Creare la funzione di classificazione in modo che utilizzi funzioni e valori di data e ora da valutare rispetto ai valori di data e ora specificati nella tabella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-119">Create the classifier function that uses time functions and values that can be evaluated against the times in the lookup table.</span></span> <span data-ttu-id="1a4b2-120">Per informazioni sull'utilizzo di tabelle di ricerca in una funzione di classificazione, vedere "Procedure consigliate per l'utilizzo di tabelle di ricerca in una funzione di classificazione" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-120">For information about using Lookup Tables in a classifier function, see "Best practices for using Lookup Tables in a classifier function" in this topic.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="1a4b2-121">include un set più ampio di tipi di dati e funzioni di data e ora.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-121">introduced an expanded set of date and time data types and functions.</span></span> <span data-ttu-id="1a4b2-122">Per altre informazioni, vedere [Funzioni e tipi di dati di data e ora &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a4b2-122">For more information, see [Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
    ```  
    CREATE FUNCTION fnTimeClassifier()  
    RETURNS sysname  
    WITH SCHEMABINDING  
    AS  
    BEGIN  
         DECLARE @strGroup sysname  
         DECLARE @loginTime time  
         SET @loginTime = CONVERT(time,GETDATE())  
         SELECT TOP 1 @strGroup = strGroupName  
              FROM dbo.tblClassificationTimeTable  
              WHERE tStartTime <= @loginTime and tEndTime >= @loginTime  
         IF(@strGroup is not null)  
         BEGIN  
              RETURN @strGroup  
         END  
    --- Use the default workload group if there is no match  
    --- on the lookup.  
         RETURN N'gOffHoursProcessing'  
    END  
    GO  
    ```  
  
5.  <span data-ttu-id="1a4b2-123">Registrare la funzione di classificazione e aggiornare la configurazione in memoria.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-123">Register the classifier function and update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR with (CLASSIFIER_FUNCTION = dbo.fnTimeClassifier)  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
### <a name="to-verify-the-resource-pools-workload-groups-and-the-classifier-user-defined-function"></a><span data-ttu-id="1a4b2-124">Per verificare i pool di risorse, i gruppi del carico di lavoro e la funzione di classificazione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="1a4b2-124">To verify the resource pools, workload groups, and the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="1a4b2-125">Ottenere la configurazione dei pool di risorse e dei gruppi del carico di lavoro utilizzando la query seguente.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-125">Obtain the resource pool and workload group configuration by using the following query.</span></span>  
  
    ```  
    USE master  
    SELECT * FROM sys.resource_governor_resource_pools  
    SELECT * FROM sys.resource_governor_workload_groups  
    GO  
    ```  
  
2.  <span data-ttu-id="1a4b2-126">Verificare che la funzione di classificazione sia presente e abilitata utilizzando le query seguenti.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-126">Verify that the classifier function exists and is enabled by using the following queries.</span></span>  
  
    ```  
    --- Get the classifier function Id and state (enabled).  
    SELECT * FROM sys.resource_governor_configuration  
    GO  
    --- Get the classifer function name and the name of the schema  
    --- that it is bound to.  
    SELECT   
          object_schema_name(classifier_function_id) AS [schema_name],  
          object_name(classifier_function_id) AS [function_name]  
    FROM sys.dm_resource_governor_configuration  
  
    ```  
  
3.  <span data-ttu-id="1a4b2-127">Ottenere i dati di runtime correnti per i pool di risorse e i gruppi del carico di lavoro utilizzando la query seguente.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-127">Obtain the current runtime data for the resource pools and workload groups by using the following query.</span></span>  
  
    ```  
    SELECT * FROM sys.dm_resource_governor_resource_pools  
    SELECT * FROM sys.dm_resource_governor_workload_groups  
    GO  
    ```  
  
4.  <span data-ttu-id="1a4b2-128">Individuare le sessioni incluse in ciascun gruppo utilizzando la query seguente.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-128">Find out what sessions are in each group by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, CAST(g.name as nvarchar(20)), s.session_id, s.login_time, CAST(s.host_name as nvarchar(20)), CAST(s.program_name AS nvarchar(20))  
              FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
              ON g.group_id = s.group_id  
    ORDER BY g.name  
    GO  
    ```  
  
5.  <span data-ttu-id="1a4b2-129">Individuare le richieste incluse in ciascun gruppo utilizzando la query seguente.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-129">Find out which requests are in each group by using the following query.</span></span>  
  
    ```  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
                ON g.group_id = r.group_id  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
6.  <span data-ttu-id="1a4b2-130">Individuare le richieste in esecuzione nella funzione di classificazione utilizzando la query seguente.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-130">Find out what requests are running in the classifier by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, g.name, s.session_id, s.login_time, s.host_name, s.program_name   
               FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = s.group_id  
                     AND 'preconnect' = s.status  
    ORDER BY g.name  
    GO  
  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = r.group_id  
                     AND 'preconnect' = r.status  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
### <a name="best-practices-for-using-lookup-tables-in-a-classifier-function"></a><span data-ttu-id="1a4b2-131">Procedure consigliate per l'utilizzo di tabelle di ricerca in una funzione di classificazione</span><span class="sxs-lookup"><span data-stu-id="1a4b2-131">Best practices for using Lookup Tables in a classifier function</span></span>  
  
1.  <span data-ttu-id="1a4b2-132">Non utilizzare una tabella di ricerca, a meno che non sia strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-132">Do not use a lookup table unless it is absolutely necessary.</span></span> <span data-ttu-id="1a4b2-133">Se è necessario utilizzare una tabella di ricerca, può essere specificata a livello di codice nella funzione stessa. È necessario tuttavia tenere presente la complessità e le modifiche dinamiche della funzione di classificazione.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-133">If you need to use a lookup table, it can be hard coded into the function itself; however, this needs to be balanced with the complexity and dynamic changes of the classifier function.</span></span>  
  
2.  <span data-ttu-id="1a4b2-134">Limitare l'I/O eseguito per le tabelle di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-134">Limit the I/O performed for lookup tables.</span></span>  
  
    1.  <span data-ttu-id="1a4b2-135">Utilizzare TOP 1 per restituire solo una riga.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-135">Use the TOP 1 to return only one row.</span></span>  
  
    2.  <span data-ttu-id="1a4b2-136">Ridurre al minimo il numero di righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-136">Minimize the number of rows in the table.</span></span>  
  
    3.  <span data-ttu-id="1a4b2-137">Includere tutte le righe della tabella in una sola pagina o in un numero ridotto di pagine.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-137">Make all rows of the table exist on a single page, or a small number of pages.</span></span>  
  
    4.  <span data-ttu-id="1a4b2-138">Verificare che le righe individuate utilizzando le operazioni Index Seek utilizzino il numero massimo consentito di colonne di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-138">Confirm that rows found using the Index Seek operations use as many seeking columns as possible.</span></span>  
  
    5.  <span data-ttu-id="1a4b2-139">Se si prevede di utilizzare più tabelle con join, eseguire la denormalizzazione in una sola tabella.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-139">De-normalize to a single table if you are considering using multiple tables with joins.</span></span>  
  
3.  <span data-ttu-id="1a4b2-140">Evitare blocchi nella tabella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-140">Prevent blocking on the lookup table.</span></span>  
  
    1.  <span data-ttu-id="1a4b2-141">Utilizzare l'hint `NOLOCK` per evitare i blocchi o utilizzare `SET LOCK_TIMEOUT` nella funzione con un valore massimo di 1.000 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-141">Use the `NOLOCK` hint to prevent blocking or use `SET LOCK_TIMEOUT` in the function with a maximum value of 1000 milliseconds.</span></span>  
  
    2.  <span data-ttu-id="1a4b2-142">Nel database master devono essere presenti una o più tabelle.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-142">Table(s) must exist in the master database.</span></span> <span data-ttu-id="1a4b2-143">Si tratta dell'unico database che verrà recuperato in caso di tentativo di connessione dei computer client.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-143">(The master database is the only database that is guaranteed to be recovered when the client computers attempt to connect).</span></span>  
  
    3.  <span data-ttu-id="1a4b2-144">Fornire sempre un nome completo per la tabella con lo schema.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-144">Always fully-qualify the table name with the schema.</span></span> <span data-ttu-id="1a4b2-145">Non è necessario specificare il nome del database, poiché deve essere utilizzato il database master.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-145">The database name is not necessary since it has to be the master database.</span></span>  
  
    4.  <span data-ttu-id="1a4b2-146">Nessun trigger nella tabella.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-146">No triggers on the table.</span></span>  
  
    5.  <span data-ttu-id="1a4b2-147">In fase di aggiornamento dei contenuti della tabella, accertarsi di utilizzare una transazione a livello di isolamento dello snapshot per evitare che il Writer blocchi i lettori.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-147">If you are updating the table contents, make sure to use a snapshot isolation level transaction to prevent Writer blocking Readers.</span></span> <span data-ttu-id="1a4b2-148">Un altro metodo per evitare questo problema consiste nell'utilizzare l'hint `NOLOCK` .</span><span class="sxs-lookup"><span data-stu-id="1a4b2-148">Note that using the `NOLOCK` hint should also mitigate this.</span></span>  
  
    6.  <span data-ttu-id="1a4b2-149">Se possibile, disabilitare la funzione di classificazione in fase di modifica dei contenuti della tabella.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-149">If possible, disable the classifier function when changing the table contents.</span></span>  
  
        > [!WARNING]  
        >  <span data-ttu-id="1a4b2-150">È consigliabile attenersi scrupolosamente a queste procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-150">We highly recommend following these best practices.</span></span> <span data-ttu-id="1a4b2-151">In caso non sia possibile seguire le procedure, contattare il supporto Microsoft per evitare in modo proattivo che si verifichino problemi in futuro.</span><span class="sxs-lookup"><span data-stu-id="1a4b2-151">If there are issues that prevent you from following the best practices, we recommend that you contact Microsoft Support so that you can proactively prevent any future problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a4b2-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a4b2-152">See Also</span></span>  
 <span data-ttu-id="1a4b2-153">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-153">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="1a4b2-154">[Abilitare Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-154">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="1a4b2-155">[Pool di risorse di Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-155">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="1a4b2-156">[Gruppo di carico di lavoro di Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-156">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="1a4b2-157">[Configurare Resource Governor utilizzando un modello](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-157">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="1a4b2-158">[Visualizzare proprietà di Resource Governor](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-158">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="1a4b2-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span></span>  
 <span data-ttu-id="1a4b2-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="1a4b2-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="1a4b2-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a4b2-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="1a4b2-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a4b2-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
