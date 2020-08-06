---
title: Uso di indici columnstore non cluster | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
ms.assetid: 4c341fb8-7cb1-4cab-921b-e80b751d6c19
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c876eb6fdd466349ac369dcff8e292bc0839c669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715683"
---
# <a name="using-nonclustered-columnstore-indexes"></a><span data-ttu-id="a5b0c-102">Utilizzo di indici columnstore non cluster</span><span class="sxs-lookup"><span data-stu-id="a5b0c-102">Using Nonclustered Columnstore Indexes</span></span>
  <span data-ttu-id="a5b0c-103">Vengono descritte le attività principali per l'utilizzo di un indice columnstore non cluster in una tabella di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5b0c-103">Describes key tasks for using a nonclustered columnstore index on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="a5b0c-104">Per una panoramica di indici columnstore, vedere [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="a5b0c-104">For an overview of columnstore indexes, see [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span></span>

 <span data-ttu-id="a5b0c-105">Per informazioni sugli indici columnstore cluster, vedere [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="a5b0c-105">For information about clustered columnstore indexes, see [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span></span>

## <a name="contents"></a><span data-ttu-id="a5b0c-106">Contenuto</span><span class="sxs-lookup"><span data-stu-id="a5b0c-106">Contents</span></span>

-   [<span data-ttu-id="a5b0c-107">Creare un indice columnstore non cluster</span><span class="sxs-lookup"><span data-stu-id="a5b0c-107">Create a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#load)

-   [<span data-ttu-id="a5b0c-108">Modificare i dati in un indice columnstore non cluster</span><span class="sxs-lookup"><span data-stu-id="a5b0c-108">Change the Data in a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#change)

##  <a name="create-a-nonclustered-columnstore-index"></a><a name="load"></a><span data-ttu-id="a5b0c-109">Creare un indice columnstore non cluster</span><span class="sxs-lookup"><span data-stu-id="a5b0c-109">Create a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="a5b0c-110">Per caricare i dati in un indice columnstore non cluster, caricare innanzitutto i dati in una tabella rowstore tradizionale archiviata come heap o indice cluster e quindi usare [create columnstore index &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) per creare un indice columnstore.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-110">To load data into a nonclustered columnstore index, first load data into a traditional rowstore table stored as a heap or clustered index, and then use [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) to create a columnstore index.</span></span>

 <span data-ttu-id="a5b0c-111">![Caricamento dati in un indice columnstore](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Caricamento dati in un indice columnstore")</span><span class="sxs-lookup"><span data-stu-id="a5b0c-111">![Loading data into a columnstore index](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Loading data into a columnstore index")</span></span>

##  <a name="change-the-data-in-a-nonclustered-columnstore-index"></a><a name="change"></a><span data-ttu-id="a5b0c-112">Modificare i dati in un indice columnstore non cluster</span><span class="sxs-lookup"><span data-stu-id="a5b0c-112">Change the Data in a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="a5b0c-113">Dopo aver creato un indice columnstore non cluster in una tabella, non è possibile modificare i dati direttamente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-113">Once you create a nonclustered columnstore index on a table, you cannot directly modify the data in that table.</span></span> <span data-ttu-id="a5b0c-114">Se si esegue una query con INSERT, UPDATE, DELETE o MERGE viene restituito un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-114">A query with INSERT, UPDATE, DELETE, or MERGE will fail and return an error message.</span></span> <span data-ttu-id="a5b0c-115">Per aggiungere o modificare i dati nella tabella, è possibile effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5b0c-115">To add or modify the data in the table, you can do one of the following:</span></span>

-   <span data-ttu-id="a5b0c-116">Disabilitare l'indice columnstore.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-116">Disable the columnstore index.</span></span> <span data-ttu-id="a5b0c-117">È possibile aggiornare i dati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-117">You can then update the data in the table.</span></span> <span data-ttu-id="a5b0c-118">Se si disabilita l'indice columnstore, è possibile ricompilare l'indice columnstore al termine dell'aggiornamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-118">If you disable the columnstore index, you can rebuild the columnstore index when you finish updating the data.</span></span> <span data-ttu-id="a5b0c-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5b0c-119">For example:</span></span>

    ```
    ALTER INDEX mycolumnstoreindex ON mytable DISABLE;
    -- update mytable --
    ALTER INDEX mycolumnstoreindex on mytable REBUILD
    ```

-   <span data-ttu-id="a5b0c-120">Eliminare l'indice columnstore, aggiornare la tabella, quindi ricreare l'indice columnstore con CREATE COLUMNStore INDEX.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-120">Drop the columnstore index, update the table, and then re-create the columnstore index with CREATE COLUMNSTORE INDEX.</span></span> <span data-ttu-id="a5b0c-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5b0c-121">For example:</span></span>

    ```
    DROP INDEX mycolumnstoreindex ON mytable
    -- update mytable --
    CREATE NONCLUSTERED COLUMNSTORE INDEX mycolumnstoreindex ON mytable;

    ```

-   <span data-ttu-id="a5b0c-122">Caricare i dati in una tabella di staging che non dispone di un indice columnstore.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-122">Load data into a staging table that does not have a columnstore index.</span></span> <span data-ttu-id="a5b0c-123">Compilare un indice columnstore nella tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-123">Build a columnstore index on the staging table.</span></span> <span data-ttu-id="a5b0c-124">Passare la tabella di staging in una partizione vuota della tabella principale.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-124">Switch the staging table into an empty partition of the main table.</span></span>

-   <span data-ttu-id="a5b0c-125">Passare una partizione della tabella con l'indice columnstore in una tabella di staging vuota.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-125">Switch a partition from the table with the columnstore index into an empty staging table.</span></span> <span data-ttu-id="a5b0c-126">Se è presente un indice columnstore nella tabella di staging, disabilitare l'indice columnstore.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-126">If there is a columnstore index on the staging table, disable the columnstore index.</span></span> <span data-ttu-id="a5b0c-127">Eseguire gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-127">Perform any updates.</span></span> <span data-ttu-id="a5b0c-128">Compilare o ricompilare l'indice columnstore.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-128">Build (or rebuild) the columnstore index.</span></span> <span data-ttu-id="a5b0c-129">Passare la tabella di staging nuovamente nella partizione (ora vuota) della tabella principale.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-129">Switch the staging table back into the (now empty) partition of the main table.</span></span>




