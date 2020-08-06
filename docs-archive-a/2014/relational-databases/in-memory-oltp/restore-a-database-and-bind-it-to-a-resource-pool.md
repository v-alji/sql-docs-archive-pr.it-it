---
title: Ripristinare un database e associarlo a un pool di risorse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0d20a569-8a27-409c-bcab-0effefb48013
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0b518c93ca9d5e7157ceaa20d9548d7b6061017d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623269"
---
# <a name="restore-a-database-and-bind-it-to-a-resource-pool"></a><span data-ttu-id="5f695-102">Ripristinare un database e associarlo a un pool di risorse</span><span class="sxs-lookup"><span data-stu-id="5f695-102">Restore a Database and Bind it to a Resource Pool</span></span>
  <span data-ttu-id="5f695-103">Anche se si dispone di memoria sufficiente per ripristinare un database con tabelle ottimizzate per la memoria, è possibile seguire le procedure consigliate e associare il database a un pool di risorse denominato.</span><span class="sxs-lookup"><span data-stu-id="5f695-103">Even though you have enough memory to restore a database with memory-optimized tables, you want to follow best practices and bind the database to a named resource pool.</span></span> <span data-ttu-id="5f695-104">Poiché il database deve essere già presente per poter essere associato al pool, il ripristino del database è un processo costituito da più passaggi.</span><span class="sxs-lookup"><span data-stu-id="5f695-104">Since the database must exist before you can bind it to the pool restoring your database is a multi-step process.</span></span> <span data-ttu-id="5f695-105">In questo argomento viene illustrato tale processo.</span><span class="sxs-lookup"><span data-stu-id="5f695-105">This topic walks you through that process.</span></span>  
  
##  <a name="restore-with-norecovery"></a><span data-ttu-id="5f695-106">Ripristino con NORECOVERY</span><span class="sxs-lookup"><span data-stu-id="5f695-106">Restore with NORECOVERY</span></span>  
 <span data-ttu-id="5f695-107">Il ripristino di un database con NORECOVERY comporta la creazione del database e il ripristino dell'immagine disco senza l'uso di memoria.</span><span class="sxs-lookup"><span data-stu-id="5f695-107">When you restore a database, NORECOVERY causes the database to be created and the disk image restored without consuming memory.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   FROM DISK = 'C:\IMOLTP_test\IMOLTP_DB.bak'  
   WITH NORECOVERY  
```  
  
##  <a name="create-the-resource-pool"></a><span data-ttu-id="5f695-108">Creazione del pool di risorse</span><span class="sxs-lookup"><span data-stu-id="5f695-108">Create the resource pool</span></span>  
 <span data-ttu-id="5f695-109">Il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente consente di creare un pool di risorse denominato Pool_IMOLTP con il 50% della memoria disponibile per l'uso.</span><span class="sxs-lookup"><span data-stu-id="5f695-109">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a resource pool named Pool_IMOLTP with 50% of memory available for its use.</span></span>  <span data-ttu-id="5f695-110">Dopo la creazione del pool, Resource Governor viene riconfigurato in modo da includere Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="5f695-110">After the pool is created, the Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
CREATE RESOURCE POOL Pool_IMOLTP WITH (MAX_MEMORY_PERCENT = 50);  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
##  <a name="bind-the-database-and-resource-pool"></a><span data-ttu-id="5f695-111">Associazione del database e del pool di risorse</span><span class="sxs-lookup"><span data-stu-id="5f695-111">Bind the database and resource pool</span></span>  
 <span data-ttu-id="5f695-112">Usare la funzione di sistema `sp_xtp_bind_db_resource_pool` per associare il database al pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="5f695-112">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="5f695-113">La funzione accetta due parametri: il nome del database seguito dal nome del pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="5f695-113">The function takes two parameters: the database name followed by the resource pool name.</span></span>  
  
 <span data-ttu-id="5f695-114">Con l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente viene definita un'associazione del database IMOLTP_DB al pool di risorse Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="5f695-114">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="5f695-115">L'associazione non diventa effettiva finché non viene completato il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="5f695-115">The binding does not become effective until you complete the next step.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
##  <a name="restore-with-recovery"></a><span data-ttu-id="5f695-116">Ripristino con RECOVERY</span><span class="sxs-lookup"><span data-stu-id="5f695-116">Restore with RECOVERY</span></span>  
 <span data-ttu-id="5f695-117">Quando si ripristina il database con recupero, il database viene portato online e vengono ripristinati tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="5f695-117">When you restore the database with recovery the database is brought online and all the data restored.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   WITH RECOVERY  
```  
  
##  <a name="monitor-the-resource-pool-performance"></a><span data-ttu-id="5f695-118">Monitoraggio delle prestazioni del pool di risorse</span><span class="sxs-lookup"><span data-stu-id="5f695-118">Monitor the resource pool performance</span></span>  
 <span data-ttu-id="5f695-119">Dopo l'associazione del database al pool di risorse denominato e il ripristino con RECOVERY, monitorare l'oggetto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Statistiche del pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="5f695-119">Once the database is bound to the named resource pool and restored with recovery, monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Resource Pool Stats Object.</span></span> <span data-ttu-id="5f695-120">Per ulteriori informazioni, vedere [SQL Server - Oggetto Statistiche del pool di risorse](../performance-monitor/sql-server-resource-pool-stats-object.md).</span><span class="sxs-lookup"><span data-stu-id="5f695-120">For more information see [SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f695-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f695-121">See Also</span></span>  
 <span data-ttu-id="5f695-122">[a un pool di risorse, vedere l'argomento](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="5f695-122">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span></span>  
 <span data-ttu-id="5f695-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5f695-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="5f695-124">[SQL Server - Oggetto Statistiche del pool di risorse](../performance-monitor/sql-server-resource-pool-stats-object.md) </span><span class="sxs-lookup"><span data-stu-id="5f695-124">[SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md) </span></span>  
 [<span data-ttu-id="5f695-125">sys.dm_resource_governor_resource_pools</span><span class="sxs-lookup"><span data-stu-id="5f695-125">sys.dm_resource_governor_resource_pools</span></span>](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql)  
  
  
