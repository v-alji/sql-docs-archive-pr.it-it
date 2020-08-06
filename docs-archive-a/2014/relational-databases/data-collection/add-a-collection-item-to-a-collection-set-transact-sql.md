---
title: Aggiungere un elemento della raccolta a un set di raccolta (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection items [SQL Server]
- collection sets [SQL Server], adding items
ms.assetid: 9fe6454e-8c0e-4b50-937b-d9871b20fd13
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0b21508761bdfbaf8918242b074f78203c1bcaed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637896"
---
# <a name="add-a-collection-item-to-a-collection-set-transact-sql"></a><span data-ttu-id="b50ed-102">Aggiunta di un elemento della raccolta a un set di raccolta (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b50ed-102">Add a Collection Item to a Collection Set (Transact-SQL)</span></span>
  <span data-ttu-id="b50ed-103">È possibile aggiungere un elemento della raccolta a un set di raccolta esistente utilizzando le stored procedure fornite con l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="b50ed-103">You can add a collection item to an existing collection set using the stored procedures that are provided with the data collector.</span></span>  
  
 <span data-ttu-id="b50ed-104">Eseguire i seguenti passaggi utilizzando l'Editor di query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b50ed-104">Carry out the following steps using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="add-a-collection-item-to-a-collection-set"></a><span data-ttu-id="b50ed-105">Aggiunta di un elemento della raccolta a un set di raccolte</span><span class="sxs-lookup"><span data-stu-id="b50ed-105">Add a collection item to a collection set</span></span>  
  
1.  <span data-ttu-id="b50ed-106">Arrestare il set di raccolta a cui aggiungere l'elemento eseguendo la stored procedure **sp_syscollector_stop_collection_set** .</span><span class="sxs-lookup"><span data-stu-id="b50ed-106">Stop the collection set that you want to add the item to by running the **sp_syscollector_stop_collection_set** stored procedure.</span></span> <span data-ttu-id="b50ed-107">Ad esempio, per arrestare un set di raccolta denominato "Test Collection Set", eseguire le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b50ed-107">For example, to stop a collection set that is named "Test Collection Set", run the following statements:</span></span>  
  
    ```sql  
    USE msdb  
    DECLARE @csid int  
    SELECT @csid = collection_set_id  
    FROM syscollector_collection_sets  
    WHERE name = 'Test Collection Set'  
    SELECT @csid  
    EXEC dbo.sp_syscollector_stop_collection_set @collection_set_id = @csid  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="b50ed-108">È anche possibile arrestare il set di raccolta utilizzando Esplora oggetti in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b50ed-108">You can also stop the collection set by using Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b50ed-109">Per altre informazioni, vedere [Avviare o arrestare un set di raccolta](start-or-stop-a-collection-set.md).</span><span class="sxs-lookup"><span data-stu-id="b50ed-109">For more information, see [Start or Stop a Collection Set](start-or-stop-a-collection-set.md).</span></span>  
  
2.  <span data-ttu-id="b50ed-110">Dichiarare il set di raccolta al quale si desidera aggiungere l'elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="b50ed-110">Declare the collection set that you want to add the collection item to.</span></span> <span data-ttu-id="b50ed-111">Nel codice seguente viene fornito un esempio su come dichiarare l'ID del set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="b50ed-111">The following code provides an example of how to declare the collection set ID.</span></span>  
  
    ```sql  
    DECLARE @collection_set_id_1 int  
    SELECT @collection_set_id_1 = collection_set_id FROM [msdb].[dbo].[syscollector_collection_sets]  
    WHERE name = N'Test Collection Set'; -- name of collection set  
    ```  
  
3.  <span data-ttu-id="b50ed-112">Dichiarare il tipo di agente di raccolta.</span><span class="sxs-lookup"><span data-stu-id="b50ed-112">Declare the collector type.</span></span> <span data-ttu-id="b50ed-113">Nel codice seguente viene fornito un esempio su come dichiarare il tipo di agente di raccolta Query T-SQL generico.</span><span class="sxs-lookup"><span data-stu-id="b50ed-113">The following code provides an example of how to declare the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid_1 uniqueidentifier  
    SELECT @collector_type_uid_1 = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
       WHERE name = N'Generic T-SQL Query Collector Type';  
    ```  
  
     <span data-ttu-id="b50ed-114">È possibile eseguire il codice seguente per ottenere un elenco dei tipi di agente di raccolta installati:</span><span class="sxs-lookup"><span data-stu-id="b50ed-114">You can run the following code to obtain a list of the installed collector types:</span></span>  
  
    ```sql  
    USE msdb  
    SELECT * from syscollector_collector_types  
    GO  
    ```  
  
4.  <span data-ttu-id="b50ed-115">Eseguire la stored procedure **sp_syscollector_create_collection_item** per creare l'elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="b50ed-115">Run the **sp_syscollector_create_collection_item** stored procedure to create the collection item.</span></span> <span data-ttu-id="b50ed-116">È necessario dichiarare lo schema per l'elemento della raccolta in modo tale da eseguirne il mapping allo schema richiesto per il tipo di agente di raccolta desiderato.</span><span class="sxs-lookup"><span data-stu-id="b50ed-116">You must declare the schema for the collection item so that it maps to the required schema for the desired collector type.</span></span> <span data-ttu-id="b50ed-117">Nell'esempio seguente viene utilizzato lo schema di input Query T-SQL generico.</span><span class="sxs-lookup"><span data-stu-id="b50ed-117">The following example uses the Generic T-SQL Query input schema.</span></span>  
  
    ```sql  
    DECLARE @collection_item_id int;  
    EXEC [msdb].[dbo].[sp_syscollector_create_collection_item]   
    @name=N'OS Wait Stats', --name of collection item  
    @parameters=N'  
    <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
     <Query>  
      <Value>select * from sys.dm_os_wait_stats</Value>  
      <OutputTable>os_wait_stats</OutputTable>  
    </Query>  
    </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 60,  
    @collection_set_id = @collection_set_id_1, --- Provides the collection set ID number  
    @collector_type_uid = @collector_type_uid_1 -- Provides the collector type UID  
    SELECT @collection_item_id     
    ```  
  
5.  <span data-ttu-id="b50ed-118">Prima di avviare il set di raccolta aggiornato, eseguire la query seguente per verificare che il nuovo elemento della raccolta sia stato creato:</span><span class="sxs-lookup"><span data-stu-id="b50ed-118">Before starting the updated collection set, run the following query to verify that the new collection item has been created:</span></span>  
  
    ```xaml  
    USE msdb  
    SELECT * from syscollector_collection_sets  
    SELECT * from syscollector_collection_items  
    GO  
    ```  
  
     <span data-ttu-id="b50ed-119">I set di raccolta e i rispettivi elementi della raccolta sono visualizzati nella scheda **Risultati** .</span><span class="sxs-lookup"><span data-stu-id="b50ed-119">The collection sets and their collection items are displayed in the **Results** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b50ed-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b50ed-120">See Also</span></span>  
 <span data-ttu-id="b50ed-121">[Creare un set di raccolta personalizzato che usa il tipo agente di raccolta Query T-SQL generico &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span><span class="sxs-lookup"><span data-stu-id="b50ed-121">[Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span></span>  
 [<span data-ttu-id="b50ed-122">Stored procedure dell'agente di raccolta dati &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b50ed-122">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
