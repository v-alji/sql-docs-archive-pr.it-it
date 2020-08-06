---
title: Eliminare uno snapshot del database (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- removing database snapshots
- deleting database snapshots
- database snapshots [SQL Server], deleting
ms.assetid: ad70ec97-d5fb-41aa-b72a-915e74b61b76
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0d9d912a092e581fad7d3d53504309f63ba1806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623323"
---
# <a name="drop-a-database-snapshot-transact-sql"></a><span data-ttu-id="cce39-102">Eliminare uno snapshot del database (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cce39-102">Drop a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="cce39-103">La rimozione di uno snapshot del database comporta l'eliminazione dello snapshot da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nonché l'eliminazione dei file sparse da esso utilizzati.</span><span class="sxs-lookup"><span data-stu-id="cce39-103">Dropping a database snapshot deletes the database snapshot from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and deletes the sparse files that are used by the snapshot.</span></span> <span data-ttu-id="cce39-104">Quando si elimina uno snapshot del database, tutte le relative connessioni utente vengono interrotte.</span><span class="sxs-lookup"><span data-stu-id="cce39-104">When you drop a database snapshot, all user connections to it are terminated.</span></span>  
  
## <a name="security"></a><span data-ttu-id="cce39-105">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cce39-105">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cce39-106">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cce39-106">Permissions</span></span>  
 <span data-ttu-id="cce39-107">Uno snapshot del database può essere rimosso da qualsiasi utente che disponga delle autorizzazioni DROP DATABASE.</span><span class="sxs-lookup"><span data-stu-id="cce39-107">Any user with DROP DATABASE permissions can drop a database snapshot.</span></span>  
  
##  <a name="how-to-drop-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cce39-108">Come eliminare uno snapshot del database (tramite Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cce39-108">How to Drop a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="cce39-109">**Per eliminare uno snapshot del database**</span><span class="sxs-lookup"><span data-stu-id="cce39-109">**To drop a database snapshot**</span></span>  
  
1.  <span data-ttu-id="cce39-110">Identificare lo snapshot del database da eliminare.</span><span class="sxs-lookup"><span data-stu-id="cce39-110">Identify the database snapshot that you want to drop.</span></span> <span data-ttu-id="cce39-111">È possibile visualizzare gli snapshot di un database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cce39-111">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cce39-112">Per altre informazioni, vedere [Visualizzare uno snapshot del database &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cce39-112">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="cce39-113">Eseguire un'istruzione [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) , specificando il nome dello snapshot del database da eliminare.</span><span class="sxs-lookup"><span data-stu-id="cce39-113">Issue a [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) statement, specifying the name of the database snapshot to be dropped.</span></span> <span data-ttu-id="cce39-114">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="cce39-114">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="cce39-115">DROP DATABASE *database_snapshot_name* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="cce39-115">DROP DATABASE *database_snapshot_name* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="cce39-116">Dove *database_snapshot_name* è il nome dello snapshot del database da eliminare.</span><span class="sxs-lookup"><span data-stu-id="cce39-116">Where *database_snapshot_name* is the name of the database snapshot to be dropped.</span></span>  
  
####  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="cce39-117">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cce39-117">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="cce39-118">Nell'esempio seguente viene rimosso uno snapshot di database, denominato SalesSnapshot0600, senza influire sul database di origine.</span><span class="sxs-lookup"><span data-stu-id="cce39-118">This example drops a database snapshot named SalesSnapshot0600, without affecting the source database.</span></span>  
  
```  
DROP DATABASE SalesSnapshot0600 ;  
```  
  
 <span data-ttu-id="cce39-119">Tutte le connessioni utente a SalesSnapshot0600 vengono terminate e tutti i file sparse del file system NTFS utilizzati dallo snapshot vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="cce39-119">Any user connections to SalesSnapshot0600 are terminated, and all of the NTFS file system sparse files used by the snapshot are deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cce39-120">Per informazioni sull'uso di file sparse con gli snapshot del database, vedere [Snapshot del database &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cce39-120">For information about the use of sparse files by database snapshots, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cce39-121">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="cce39-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="cce39-122">Creare uno snapshot del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cce39-122">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="cce39-123">Visualizzazione di uno snapshot del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cce39-123">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="cce39-124">Ripristinare un database a uno snapshot del database</span><span class="sxs-lookup"><span data-stu-id="cce39-124">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="cce39-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cce39-125">See Also</span></span>  
 <span data-ttu-id="cce39-126">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cce39-126">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 [<span data-ttu-id="cce39-127">Snapshot del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cce39-127">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
