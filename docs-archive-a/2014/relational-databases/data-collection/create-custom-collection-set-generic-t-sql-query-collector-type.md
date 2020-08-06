---
title: Creare un set di raccolta personalizzato che utilizza il tipo di agente di raccolta query T-SQL generico (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- T-SQL Query collector type
- collection sets [SQL Server], creating custom
ms.assetid: 6b06db5b-cfdc-4ce0-addd-ec643460605b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab21ad5fd65556dec639fd5ca6999d23e2de673b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635085"
---
# <a name="create-a-custom-collection-set-that-uses-the-generic-t-sql-query-collector-type-transact-sql"></a><span data-ttu-id="2dbc2-102">Creazione di un set di raccolta personalizzato che utilizza il tipo agente di raccolta Query T-SQL generico (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2dbc2-102">Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type (Transact-SQL)</span></span>
  <span data-ttu-id="2dbc2-103">È possibile creare un set di raccolta personalizzato con elementi della raccolta che utilizzano il tipo di agente di raccolta Query T-SQL generico tramite le stored procedure fornite con l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-103">You can create a custom collection set with collection items that use the Generic T-SQL Query collector type by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="2dbc2-104">Il completamento di questa attività comporta l'utilizzo dell'Editor di query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per eseguire le procedure descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="2dbc2-104">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedures:</span></span>  
  
-   <span data-ttu-id="2dbc2-105">Configurazione delle pianificazioni di caricamento.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-105">Configure upload schedules.</span></span>  
  
-   <span data-ttu-id="2dbc2-106">Definizione e creazione del set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-106">Define and create the collection set.</span></span>  
  
-   <span data-ttu-id="2dbc2-107">Definizione e creazione di un elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-107">Define and create a collection item.</span></span>  
  
-   <span data-ttu-id="2dbc2-108">Verifica dell'esistenza del set di raccolta e degli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-108">Verify that the collection set and collection items exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2dbc2-109">Prima di creare un set di raccolta personalizzato è necessario configurare i parametri della raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-109">Before you create a custom collection set, you must configure data collection parameters.</span></span> <span data-ttu-id="2dbc2-110">Per altre informazioni, vedere [Configurazione dei parametri per la raccolta dati &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2dbc2-110">For more information, see [Configure Data Collection Parameters &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span></span>  
  
### <a name="define-and-create-the-collection-set"></a><span data-ttu-id="2dbc2-111">Definizione e creazione del set di raccolta</span><span class="sxs-lookup"><span data-stu-id="2dbc2-111">Define and create the collection set</span></span>  
  
1.  <span data-ttu-id="2dbc2-112">Definire un nuovo set di raccolta utilizzando la stored procedure sp_syscollector_create_collection_set.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-112">Define a new collection set using the sp_syscollector_create_collection_set stored procedure.</span></span>  
  
    ```  
    USE msdb;  
    DECLARE @collection_set_id int;  
    DECLARE @collection_set_uid uniqueidentifier;  
    EXEC sp_syscollector_create_collection_set   
        @name=N'DMV Test 1',   
        @collection_mode=0,   
        @description=N'This is a test collection set',   
        @logging_level=1,   
        @days_until_expiration=14,   
        @schedule_name=N'CollectorSchedule_Every_15min',   
        @collection_set_id=@collection_set_id OUTPUT,   
        @collection_set_uid=@collection_set_uid OUTPUT;  
    SELECT @collection_set_id, @collection_set_uid;  
    ```  
  
     <span data-ttu-id="2dbc2-113">È possibile impostare la modalità di raccolta su 0 (in cache) o su 1 (non in cache).</span><span class="sxs-lookup"><span data-stu-id="2dbc2-113">The collection mode can be set to either 0 (cached) or to 1 (non-cached).</span></span>  
  
     <span data-ttu-id="2dbc2-114">Il livello di registrazione può essere impostato su 0, 1 o 2.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-114">The logging level can be set to 0, 1 or 2.</span></span>  
  
     <span data-ttu-id="2dbc2-115">Le seguenti pianificazioni preconfigurate vengono fornite con l'agente di raccolta dati:</span><span class="sxs-lookup"><span data-stu-id="2dbc2-115">The following preconfigured schedules are provided with the data collector:</span></span>  
  
    -   <span data-ttu-id="2dbc2-116">CollectorSchedule_Every_5min</span><span class="sxs-lookup"><span data-stu-id="2dbc2-116">CollectorSchedule_Every_5min</span></span>  
  
    -   <span data-ttu-id="2dbc2-117">CollectorSchedule_Every_10min</span><span class="sxs-lookup"><span data-stu-id="2dbc2-117">CollectorSchedule_Every_10min</span></span>  
  
    -   <span data-ttu-id="2dbc2-118">CollectorSchedule_Every_15min</span><span class="sxs-lookup"><span data-stu-id="2dbc2-118">CollectorSchedule_Every_15min</span></span>  
  
    -   <span data-ttu-id="2dbc2-119">CollectorSchedule_Every_30min</span><span class="sxs-lookup"><span data-stu-id="2dbc2-119">CollectorSchedule_Every_30min</span></span>  
  
    -   <span data-ttu-id="2dbc2-120">CollectorSchedule_Every_60min</span><span class="sxs-lookup"><span data-stu-id="2dbc2-120">CollectorSchedule_Every_60min</span></span>  
  
    -   <span data-ttu-id="2dbc2-121">CollectorSchedule_Every_6h</span><span class="sxs-lookup"><span data-stu-id="2dbc2-121">CollectorSchedule_Every_6h</span></span>  
  
     <span data-ttu-id="2dbc2-122">Se non si desidera utilizzare una delle pianificazioni fornite è possibile creare una nuova pianificazione e utilizzarla per il set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-122">If you do not want to use one of the schedules that are provided, you can create a new schedule and use it for the collection set.</span></span> <span data-ttu-id="2dbc2-123">Per altre informazioni, vedere [Creare e collegare le pianificazioni ai processi](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="2dbc2-123">For more information, see [Create and Attach Schedules to Jobs](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span></span>  
  
### <a name="define-and-create-a-collection-item"></a><span data-ttu-id="2dbc2-124">Definizione e creazione di un elemento della raccolta</span><span class="sxs-lookup"><span data-stu-id="2dbc2-124">Define and create a collection item</span></span>  
  
1.  <span data-ttu-id="2dbc2-125">Poiché il nuovo elemento della raccolta è basato su un tipo di agente di raccolta generico già installato, è possibile eseguire il codice seguente per impostare il GUID in modo che corrisponda al tipo di agente di raccolta Query T-SQL generico.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-125">Because the new collection item is based on a generic collector type that is already installed, you can run the following code to set the GUID to correspond to the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid uniqueidentifier;  
    SELECT @collector_type_uid = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
    WHERE name = N'Generic T-SQL Query Collector Type';  
    DECLARE @collection_item_id int;  
    ```  
  
2.  <span data-ttu-id="2dbc2-126">Utilizzare la stored procedure sp_syscollector_create_collection_item per creare l'elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-126">Use the sp_syscollector_create_collection_item stored procedure to create the collection item.</span></span> <span data-ttu-id="2dbc2-127">Dichiarare lo schema per l'elemento della raccolta in modo che ne venga eseguito il mapping allo schema richiesto per il tipo di agente di raccolta Query T-SQL generico.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-127">Declare the schema for the collection item so it maps to the schema that is required for the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    EXEC sp_syscollector_create_collection_item   
        @name=N'Query Stats - Test 1',   
        @parameters=N'  
            <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
            <Query>  
            <Value>SELECT * FROM sys.dm_exec_query_stats</Value>  
            <OutputTable>dm_exec_query_stats</OutputTable>  
            </Query>  
            </ns:TSQLQueryCollector>',   
        @collection_item_id=@collection_item_id OUTPUT,   
        @frequency=5,   
        @collection_set_id=@collection_set_id,   
        @collector_type_uid=@collector_type_uid;  
    SELECT @collection_item_id;  
    ```  
  
### <a name="verify-that-the-new-collection-set-and-collection-item-exist"></a><span data-ttu-id="2dbc2-128">Verifica dell'esistenza del nuovo set di raccolta a dell'elemento della raccolta</span><span class="sxs-lookup"><span data-stu-id="2dbc2-128">Verify that the new collection set and collection item exist</span></span>  
  
1.  <span data-ttu-id="2dbc2-129">Prima di avviare il nuovo set di raccolta, eseguire la query seguente per verificare che il nuovo set di raccolta e l'elemento della raccolta siano stati creati.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-129">Before starting the new collection set, run the following query to verify that the new collection set and its collection item have been created.</span></span>  
  
    ```sql  
    USE msdb;  
    SELECT * FROM syscollector_collection_sets;  
    SELECT * FROM syscollector_collection_items;  
    GO  
    ```  
  
     <span data-ttu-id="2dbc2-130">È anche possibile effettuare un controllo visivo in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dbc2-130">You can also do a visual check in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2dbc2-131">In Esplora oggetti espandere il nodo **Gestione** , quindi **Raccolta dati**.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-131">In Object Explorer, expand the **Management** node, and then expand **Data Collection**.</span></span> <span data-ttu-id="2dbc2-132">Verrà visualizzato il nuovo set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-132">The new collection set will be displayed.</span></span> <span data-ttu-id="2dbc2-133">L'icona con il cerchio rosso per il set di raccolta indica che quest'ultimo è arrestato.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-133">The red circle icon for the collection set indicates that the collection set is stopped.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dbc2-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="2dbc2-134">Example</span></span>  
 <span data-ttu-id="2dbc2-135">Nell'esempio di codice seguente vengono combinati gli esempi documentati nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="2dbc2-135">The following code sample combines the examples that are documented in the previous steps.</span></span> <span data-ttu-id="2dbc2-136">Si noti che la frequenza di raccolta impostata per l'elemento della raccolta (5 secondi) viene ignorata, poiché la modalità di raccolta del set di raccolta è impostata su 0 (modalità cache).</span><span class="sxs-lookup"><span data-stu-id="2dbc2-136">Note that the collection frequency that is set for the collection item (5 seconds) is ignored because the collection set collection mode is set to 0, which is cached mode.</span></span> <span data-ttu-id="2dbc2-137">Per altre informazioni, vedere [Data Collection](data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="2dbc2-137">For more information, see [Data Collection](data-collection.md).</span></span>  
  
```sql  
USE msdb;  
  
DECLARE @collection_set_id int;  
DECLARE @collection_set_uid uniqueidentifier  
  
EXEC dbo.sp_syscollector_create_collection_set  
    @name = N'DMV Stats Test 1',  
    @collection_mode = 0,  
    @description = N'This is a test collection set',  
    @logging_level=1,  
    @days_until_expiration = 14,  
    @schedule_name=N'CollectorSchedule_Every_15min',  
    @collection_set_id = @collection_set_id OUTPUT,  
    @collection_set_uid = @collection_set_uid OUTPUT;  
SELECT @collection_set_id,@collection_set_uid;  
  
DECLARE @collector_type_uid uniqueidentifier;  
SELECT @collector_type_uid = collector_type_uid FROM syscollector_collector_types   
WHERE name = N'Generic T-SQL Query Collector Type';  
  
DECLARE @collection_item_id int;  
EXEC sp_syscollector_create_collection_item  
@name= N'Query Stats - Test 1',  
@parameters=N'  
<ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
<Query>  
  <Value>select * from sys.dm_exec_query_stats</Value>  
  <OutputTable>dm_exec_query_stats</OutputTable>  
</Query>  
 </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 5, -- This parameter is ignored in cached mode  
    @collection_set_id = @collection_set_id,  
    @collector_type_uid = @collector_type_uid;  
SELECT @collection_item_id;  
  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="2dbc2-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dbc2-138">See Also</span></span>  
 <span data-ttu-id="2dbc2-139">[Stored procedure dell'agente di raccolta dati &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2dbc2-139">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="2dbc2-140">[Gestione pianificazioni](../../ssms/agent/manage-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="2dbc2-140">[Manage Schedules](../../ssms/agent/manage-schedules.md) </span></span>  
 [<span data-ttu-id="2dbc2-141">Avviare o arrestare un set di raccolta</span><span class="sxs-lookup"><span data-stu-id="2dbc2-141">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
  
