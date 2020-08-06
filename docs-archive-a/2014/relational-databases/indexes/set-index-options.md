---
title: Impostare le opzioni di indice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- ALLOW_ROW_LOCKS option
- SORT_IN_TEMPDB option
- DROP_EXISTING clause
- large data, indexes
- PAD_INDEX
- STATISTICS_NORECOMPUTE
- MAXDOP index option, setting
- index options [SQL Server]
- MAXDOP index option
- IGNORE_DUP_KEY option
- ALLOW_PAGE_LOCKS option
- ONLINE
ms.assetid: 7969af33-e94c-41f7-ab89-9d9a2747cd5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9f2d7f0bbbf0d152d3f510ae9ddbe3168634ef96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723871"
---
# <a name="set-index-options"></a><span data-ttu-id="4522a-102">Impostare le opzioni di indice</span><span class="sxs-lookup"><span data-stu-id="4522a-102">Set Index Options</span></span>
  <span data-ttu-id="4522a-103">In questo argomento si illustra come modificare le proprietà di un indice in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4522a-103">This topic describes how to modify the properties of an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4522a-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4522a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4522a-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4522a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4522a-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4522a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4522a-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4522a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4522a-108">**Per modificare le proprietà di un indice utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="4522a-108">**To modify the properties of an index, using:**</span></span>  
  
     [<span data-ttu-id="4522a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4522a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4522a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4522a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4522a-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4522a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4522a-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4522a-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4522a-113">Le opzioni ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY e STATISTICS_NORECOMPUTE vengono applicate immediatamente all'indice tramite la clausola SET nell'istruzione ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="4522a-113">The following options are immediately applied to the index by using the SET clause in the ALTER INDEX statement: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY, and STATISTICS_NORECOMPUTE.</span></span>  
  
-   <span data-ttu-id="4522a-114">Le opzioni seguenti possono essere impostate quando si ricompila un indice tramite ALTER INDEX REBUILD o CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP e DROP_EXISTING (solo CREATE INDEX).</span><span class="sxs-lookup"><span data-stu-id="4522a-114">The following options can be set when you rebuild an index by using either ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP, and DROP_EXISTING (CREATE INDEX only).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4522a-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4522a-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4522a-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4522a-116">Permissions</span></span>  
 <span data-ttu-id="4522a-117">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="4522a-117">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4522a-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4522a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-table-designer"></a><span data-ttu-id="4522a-119">Per modificare le proprietà di un indice in Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="4522a-119">To modify the properties of an index in Table Designer</span></span>  
  
1.  <span data-ttu-id="4522a-120">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera modificare le proprietà di un indice.</span><span class="sxs-lookup"><span data-stu-id="4522a-120">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="4522a-121">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="4522a-121">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4522a-122">Fare clic con il pulsante destro del mouse sulla tabella in cui si vogliono modificare le proprietà di un indice e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="4522a-122">Right-click the table on which you want to modify an index's properties and select **Design**.</span></span>  
  
4.  <span data-ttu-id="4522a-123">Scegliere **Indici/chiavi** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="4522a-123">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="4522a-124">Selezionare l'indice che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="4522a-124">Select the index that you want to modify.</span></span> <span data-ttu-id="4522a-125">Le relative proprietà saranno visualizzate nella griglia principale.</span><span class="sxs-lookup"><span data-stu-id="4522a-125">Its properties will show up in the main grid.</span></span>  
  
6.  <span data-ttu-id="4522a-126">Modificare le impostazioni di tutte le proprietà per personalizzare l'indice.</span><span class="sxs-lookup"><span data-stu-id="4522a-126">Change the settings of any and all properties to customize the index.</span></span>  
  
7.  <span data-ttu-id="4522a-127">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="4522a-127">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="4522a-128">Selezionare **Salva** table_name **dal menu**_File_.</span><span class="sxs-lookup"><span data-stu-id="4522a-128">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-object-explorer"></a><span data-ttu-id="4522a-129">Per modificare le proprietà di un indice in Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="4522a-129">To modify the properties of an index in Object Explorer</span></span>  
  
1.  <span data-ttu-id="4522a-130">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera modificare le proprietà di un indice.</span><span class="sxs-lookup"><span data-stu-id="4522a-130">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="4522a-131">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="4522a-131">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4522a-132">Fare clic sul segno più per espandere la tabella nella quale modificare le proprietà di un indice.</span><span class="sxs-lookup"><span data-stu-id="4522a-132">Click the plus sign to expand the table on which you want to modify an index's properties.</span></span>  
  
4.  <span data-ttu-id="4522a-133">Fare clic sul segno più per espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="4522a-133">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="4522a-134">Fare clic con il pulsante destro del mouse sull'indice di cui si vogliono modificare le proprietà e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4522a-134">Right-click the index of which you want to modify the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="4522a-135">In **Selezione pagina**selezionare **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="4522a-135">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="4522a-136">Modificare le impostazioni di tutte le proprietà per personalizzare l'indice.</span><span class="sxs-lookup"><span data-stu-id="4522a-136">Change the settings of any and all properties to customize the index.</span></span>  
  
8.  <span data-ttu-id="4522a-137">Per aggiungere, rimuovere o modificare la posizione di una colonna dell'indice, selezionare la pagina **Generale** della finestra di dialogo **Proprietà indice -** _nome_indice_.</span><span class="sxs-lookup"><span data-stu-id="4522a-137">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties -** _index_name_ dialog box.</span></span> <span data-ttu-id="4522a-138">Per altre informazioni, vedere [Index Properties F1 Help](index-properties-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="4522a-138">For more information, see [Index Properties F1 Help](index-properties-f1-help.md)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4522a-139">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4522a-139">Using Transact-SQL</span></span>  
  
#### <a name="to-see-the-properties-of-all-the-indexes-in-a-table"></a><span data-ttu-id="4522a-140">Per visualizzare le proprietà di tutti gli indici in una tabella</span><span class="sxs-lookup"><span data-stu-id="4522a-140">To see the properties of all the indexes in a table</span></span>  
  
1.  <span data-ttu-id="4522a-141">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4522a-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4522a-142">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4522a-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4522a-143">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4522a-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT i.name AS index_name,   
        i.type_desc,   
        i.is_unique,   
        ds.type_desc AS filegroup_or_partition_scheme,   
        ds.name AS filegroup_or_partition_scheme_name,   
        i.ignore_dup_key,   
        i.is_primary_key,   
        i.is_unique_constraint,   
        i.fill_factor,   
        i.is_padded,   
        i.is_disabled,   
        i.allow_row_locks,   
        i.allow_page_locks,   
        i.has_filter,   
        i.filter_definition  
    FROM sys.indexes AS i  
       INNER JOIN sys.data_spaces AS ds ON i.data_space_id = ds.data_space_id  
    WHERE is_hypothetical = 0 AND i.index_id <> 0   
       AND i.object_id = OBJECT_ID('HumanResources.Employee');   
    GO  
  
    ```  
  
#### <a name="to-set-the-properties-of-an-index"></a><span data-ttu-id="4522a-144">Per visualizzare le proprietà di un indice</span><span class="sxs-lookup"><span data-stu-id="4522a-144">To set the properties of an index</span></span>  
  
1.  <span data-ttu-id="4522a-145">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4522a-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4522a-146">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4522a-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4522a-147">Copiare e incollare gli esempi seguenti nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4522a-147">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="4522a-148">Per altre informazioni, vedere [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4522a-148">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
