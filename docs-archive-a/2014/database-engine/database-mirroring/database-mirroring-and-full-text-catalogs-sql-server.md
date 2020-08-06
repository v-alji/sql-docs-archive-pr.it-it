---
title: Mirroring di database e cataloghi full-text (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- full-text catalogs [SQL Server], database mirroring
- catalogs [SQL Server], database mirroring
ms.assetid: e34072ae-fe8a-462d-bb03-02fa0987f793
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 39929f4bed6edbd1e8ec5c1b72dbe8f7aefeec68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626277"
---
# <a name="database-mirroring-and-full-text-catalogs-sql-server"></a><span data-ttu-id="d06c5-102">Mirroring di database e cataloghi full-text (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d06c5-102">Database Mirroring and Full-Text Catalogs (SQL Server)</span></span>
  <span data-ttu-id="d06c5-103">Per eseguire il mirroring di un database che include un catalogo full-text, eseguire le consuete operazioni di backup per creare un backup completo del database principale e quindi ripristinare il backup per copiare il database nel server mirror.</span><span class="sxs-lookup"><span data-stu-id="d06c5-103">To mirror a database that has a full-text catalog, use backup as usual to create a full database backup of the principal database, and then restore the backup to copy the database to the mirror server.</span></span> <span data-ttu-id="d06c5-104">Per altre informazioni, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d06c5-104">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
## <a name="full-text-catalog-and-indexes-before-failover"></a><span data-ttu-id="d06c5-105">Catalogo e indici full-text prima del failover</span><span class="sxs-lookup"><span data-stu-id="d06c5-105">Full-Text Catalog and Indexes Before Failover</span></span>  
 <span data-ttu-id="d06c5-106">Il catalogo full-text di un nuovo database mirror corrisponde a quello disponibile al momento del backup del database.</span><span class="sxs-lookup"><span data-stu-id="d06c5-106">In a newly created mirror database, the full-text catalog is the same as when the database was backed up.</span></span> <span data-ttu-id="d06c5-107">Dopo l'avvio del mirroring del database, tutte le modifiche a livello di catalogo apportate dall'istruzione (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) vengono registrare e inviate al server mirror per la riproduzione nel database mirror.</span><span class="sxs-lookup"><span data-stu-id="d06c5-107">After database mirroring starts, any catalog-level changes that were made by DDL statements (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) are logged and sent to the mirror server to be replayed on the mirror database.</span></span> <span data-ttu-id="d06c5-108">Le modifiche a livello di indice, invece, non vengono replicate nel database mirror perché non vengono registrate nel server principale.</span><span class="sxs-lookup"><span data-stu-id="d06c5-108">However, index-level changes are not reproduced on the mirror database because it is not logged on to the principal server.</span></span> <span data-ttu-id="d06c5-109">Pertanto, quando cambia il contenuto del catalogo full-text nel database principale, il contenuto del catalogo full-text nel database mirror non sarà sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="d06c5-109">Therefore, as the contents of the full-text catalog change on the principal database, the contents of the full-text catalog on the mirror database are unsynchronized.</span></span>  
  
## <a name="full-text-indexes-after-failover"></a><span data-ttu-id="d06c5-110">Indici full-text dopo il failover</span><span class="sxs-lookup"><span data-stu-id="d06c5-110">Full-Text Indexes After Failover</span></span>  
 <span data-ttu-id="d06c5-111">Dopo un failover, la ricerca completa di un indice full-text sul nuovo server principale può risultare utile o necessaria nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d06c5-111">After a failover, a full crawl of a full-text index on the new principal server might be required or useful in the following situations:</span></span>  
  
-   <span data-ttu-id="d06c5-112">Se è disabilitato il rilevamento delle modifiche su un indice full-text, è necessario avviare una ricerca per indicizzazione completa utilizzando l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="d06c5-112">If change-tracking is turned OFF on a full text index, you must start a full crawl on that index by using the following statement:</span></span>  
  
     <span data-ttu-id="d06c5-113">ALTER FULLTEXT INDEX ON *nome_tabella* START FULL POPULATION</span><span class="sxs-lookup"><span data-stu-id="d06c5-113">ALTER FULLTEXT INDEX ON *table_name* START FULL POPULATION</span></span>  
  
-   <span data-ttu-id="d06c5-114">Se un indice full-text è configurato per il rilevamento automatico delle modifiche, l'indice viene sincronizzato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d06c5-114">If a full-text index is configured for automatic change tracking, the full-text index is automatically synchronized.</span></span> <span data-ttu-id="d06c5-115">La sincronizzazione, tuttavia, determina un rallentamento delle prestazioni full-text.</span><span class="sxs-lookup"><span data-stu-id="d06c5-115">However, synchronization slows full-text performance somewhat.</span></span> <span data-ttu-id="d06c5-116">In caso di rallentamento eccessivo delle prestazioni, è possibile eseguire una ricerca per indicizzazione completa disattivando il rilevamento delle modifiche e quindi reimpostando il rilevamento automatico:</span><span class="sxs-lookup"><span data-stu-id="d06c5-116">If performance is too slow, you can cause a full crawl by setting change tracking off and then resetting it to automatic:</span></span>  
  
    -   <span data-ttu-id="d06c5-117">Per disattivare il rilevamento delle modifiche:</span><span class="sxs-lookup"><span data-stu-id="d06c5-117">To set change tracking off:</span></span>  
  
         <span data-ttu-id="d06c5-118">ALTER FULLTEXT INDEX ON *nome_tabella* SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="d06c5-118">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING OFF</span></span>  
  
    -   <span data-ttu-id="d06c5-119">Per impostare il rilevamento automatico delle modifiche:</span><span class="sxs-lookup"><span data-stu-id="d06c5-119">To set on automatic change tracking to automatic:</span></span>  
  
         <span data-ttu-id="d06c5-120">ALTER FULLTEXT INDEX ON *nome_tabella* SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="d06c5-120">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING AUTO</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d06c5-121">Per determinare se il rilevamento automatico delle modifiche è attivo, è possibile usare la funzione [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) per eseguire una query sulla proprietà **TableFullTextBackgroundUpdateIndexOn** della tabella.</span><span class="sxs-lookup"><span data-stu-id="d06c5-121">To see whether auto change tracking is on, you can use the [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) function to query the **TableFullTextBackgroundUpdateIndexOn** property of the table.</span></span>  
  
 <span data-ttu-id="d06c5-122">Per altre informazioni, vedere [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d06c5-122">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d06c5-123">L'avvio di una ricerca per indicizzazione dopo un failover viene eseguito esattamente come l'avvio di una ricerca per indicizzazione dopo un ripristino.</span><span class="sxs-lookup"><span data-stu-id="d06c5-123">Starting a crawl after failover works the same as starting a crawl after a restore.</span></span>  
  
## <a name="after-forcing-service"></a><span data-ttu-id="d06c5-124">Dopo la forzatura del servizio</span><span class="sxs-lookup"><span data-stu-id="d06c5-124">After Forcing Service</span></span>  
 <span data-ttu-id="d06c5-125">Dopo la forzatura del servizio nel server mirror, con possibile perdita di dati, avviare una ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="d06c5-125">After service is forced to the mirror server (with possible data loss), start a full crawl.</span></span> <span data-ttu-id="d06c5-126">Il metodo da utilizzare per l'avvio di una ricerca per indicizzazione completa dipende dall'attivazione o disattivazione del rilevamento delle modifiche nell'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="d06c5-126">The method to use for starting a full crawl depends on whether the full-text index is change tracked.</span></span> <span data-ttu-id="d06c5-127">Per ulteriori informazioni, vedere "Indici full-text dopo il failover" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d06c5-127">For more information, see "Full-Text Indexes After Failover," earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d06c5-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d06c5-128">See Also</span></span>  
 <span data-ttu-id="d06c5-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d06c5-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="d06c5-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d06c5-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="d06c5-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d06c5-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="d06c5-132">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d06c5-132">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="d06c5-133">Backup e ripristino di indici e cataloghi full-text</span><span class="sxs-lookup"><span data-stu-id="d06c5-133">Back Up and Restore Full-Text Catalogs and Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
  
