---
title: Caratteristiche del database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 04518abb-8581-47c8-a601-ee9136c3c0eb
author: rothja
ms.author: jroth
ms.openlocfilehash: 56b9f9ba9cc6e11ea82b822ae10b31710c8617b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629867"
---
# <a name="database-features"></a><span data-ttu-id="d0679-102">Caratteristiche del database</span><span class="sxs-lookup"><span data-stu-id="d0679-102">Database Features</span></span>
  <span data-ttu-id="d0679-103">In questa sezione sono contenute le caratteristiche e le attività associate a database, oggetti di database, tipi di dati e i meccanismi necessari per utilizzare o gestire dati.</span><span class="sxs-lookup"><span data-stu-id="d0679-103">This section contains the features and tasks associated with databases, database objects, data types, and the mechanisms used to work with or manage data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0679-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d0679-104">In This Section</span></span>  
  
|||
|--|--|
|[<span data-ttu-id="d0679-105">Database</span><span class="sxs-lookup"><span data-stu-id="d0679-105">Databases</span></span>](databases/databases.md)|[<span data-ttu-id="d0679-106">Backup e ripristino di database SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0679-106">Back Up and Restore of SQL Server Databases</span></span>](backup-restore/back-up-and-restore-of-sql-server-databases.md)|  
|[<span data-ttu-id="d0679-107">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0679-107">Tables</span></span>](tables/tables.md)|[<span data-ttu-id="d0679-108">Numeri di sequenza</span><span class="sxs-lookup"><span data-stu-id="d0679-108">Sequence Numbers</span></span>](sequence-numbers/sequence-numbers.md)|[<span data-ttu-id="d0679-109">Informazioni sull'importazione ed esportazione bulk di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-109">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](import-export/bulk-import-and-export-of-data-sql-server.md)|  
|[<span data-ttu-id="d0679-110">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-110">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp/in-memory-oltp-in-memory-optimization.md)|[<span data-ttu-id="d0679-111">Trigger DDL</span><span class="sxs-lookup"><span data-stu-id="d0679-111">DDL Triggers</span></span>](triggers/ddl-triggers.md)|[<span data-ttu-id="d0679-112">Compressione dei dati</span><span class="sxs-lookup"><span data-stu-id="d0679-112">Data Compression</span></span>](data-compression/data-compression.md)|  
|[<span data-ttu-id="d0679-113">Indici</span><span class="sxs-lookup"><span data-stu-id="d0679-113">Indexes</span></span>](indexes/indexes.md)|[<span data-ttu-id="d0679-114">Trigger DML</span><span class="sxs-lookup"><span data-stu-id="d0679-114">DML Triggers</span></span>](triggers/dml-triggers.md)|[<span data-ttu-id="d0679-115">Oggetti di automazione OLE in Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0679-115">OLE Automation Objects in Transact-SQL</span></span>](stored-procedures/ole-automation-objects-in-transact-sql.md)|  
|[<span data-ttu-id="d0679-116">Tabelle e indici partizionati</span><span class="sxs-lookup"><span data-stu-id="d0679-116">Partitioned Tables and Indexes</span></span>](partitions/partitioned-tables-and-indexes.md)|[<span data-ttu-id="d0679-117">Sinonimi &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-117">Synonyms &#40;Database Engine&#41;</span></span>](synonyms/synonyms-database-engine.md)|[<span data-ttu-id="d0679-118">Notifiche degli eventi</span><span class="sxs-lookup"><span data-stu-id="d0679-118">Event Notifications</span></span>](service-broker/event-notifications.md)|  
|[<span data-ttu-id="d0679-119">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="d0679-119">Views</span></span>](views/views.md)|[<span data-ttu-id="d0679-120">Dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-120">XML Data &#40;SQL Server&#41;</span></span>](xml/xml-data-sql-server.md)|[<span data-ttu-id="d0679-121">Monitoraggio e ottimizzazione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="d0679-121">Monitor and Tune for Performance</span></span>](performance/monitor-and-tune-for-performance.md)|  
|[<span data-ttu-id="d0679-122">Stored procedure &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-122">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures/stored-procedures-database-engine.md)|[<span data-ttu-id="d0679-123">Dati spaziali &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial/spatial-data-sql-server.md)||  
|[<span data-ttu-id="d0679-124">Cerca &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-124">Search &#40;SQL Server&#41;</span></span>](../database-engine/search-sql-server.md)|[<span data-ttu-id="d0679-125">Dati BLOB &#40;Binary Large Object&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-125">Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;</span></span>](blob/binary-large-object-blob-data-sql-server.md)||  
|[<span data-ttu-id="d0679-126">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="d0679-126">User-Defined Functions</span></span>](user-defined-functions/user-defined-functions.md)|[<span data-ttu-id="d0679-127">Applicazioni livello dati</span><span class="sxs-lookup"><span data-stu-id="d0679-127">Data-tier Applications</span></span>](data-tier-applications/data-tier-applications.md)||  
|[<span data-ttu-id="d0679-128">Statistiche</span><span class="sxs-lookup"><span data-stu-id="d0679-128">Statistics</span></span>](statistics/statistics.md)|[<span data-ttu-id="d0679-129">Log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-129">The Transaction Log &#40;SQL Server&#41;</span></span>](logs/the-transaction-log-sql-server.md)||  
|[<span data-ttu-id="d0679-130">Guide di piano</span><span class="sxs-lookup"><span data-stu-id="d0679-130">Plan Guides</span></span>](performance/plan-guides.md)|[<span data-ttu-id="d0679-131">Checkpoint di database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0679-131">Database Checkpoints &#40;SQL Server&#41;</span></span>](logs/database-checkpoints-sql-server.md)||  
  
  
