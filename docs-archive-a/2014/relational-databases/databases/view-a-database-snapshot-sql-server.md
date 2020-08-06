---
title: Visualizzare uno snapshot del database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], viewing
- displaying database snapshots
- viewing database snapshots
ms.assetid: 123f19b2-0850-4033-8507-59ebdfb368ee
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92c5c557656e87be562e9d5477f14f66b2c39e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724755"
---
# <a name="view-a-database-snapshot-sql-server"></a><span data-ttu-id="30653-102">Visualizzazione di uno snapshot del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="30653-102">View a Database Snapshot (SQL Server)</span></span>
  <span data-ttu-id="30653-103">In questo argomento viene illustrato come visualizzare uno snapshot del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30653-103">This topic explains how to view a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30653-104">Per creare, ripristinare o eliminare uno snapshot del database, è necessario utilizzare [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30653-104">To create, revert to, or delete a database snapshot, you must use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="30653-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="30653-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="30653-106">**Per visualizzare uno snapshot del database mediante:**</span><span class="sxs-lookup"><span data-stu-id="30653-106">**To view a database snapshot, using:**</span></span>  
  
     [<span data-ttu-id="30653-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30653-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="30653-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30653-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="30653-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30653-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="30653-110">**Per visualizzare uno snapshot del database**</span><span class="sxs-lookup"><span data-stu-id="30653-110">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="30653-111">In Esplora oggetti connettersi all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza in questione.</span><span class="sxs-lookup"><span data-stu-id="30653-111">In Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="30653-112">Espandere **Database.**</span><span class="sxs-lookup"><span data-stu-id="30653-112">Expand **Databases.**</span></span>  
  
3.  <span data-ttu-id="30653-113">Espandere **Snapshot database**e selezionare lo snapshot da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="30653-113">Expand **Database Snapshots**, and select the snapshot you want to view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="30653-114">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30653-114">Using Transact-SQL</span></span>  
 <span data-ttu-id="30653-115">**Per visualizzare uno snapshot del database**</span><span class="sxs-lookup"><span data-stu-id="30653-115">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="30653-116">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30653-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="30653-117">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="30653-117">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="30653-118">Per elencare gli snapshot del database dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], eseguire una query sulla colonna **source_database_id** della vista del catalogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) per valori non NULL.</span><span class="sxs-lookup"><span data-stu-id="30653-118">To list the database snapshots of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], query the **source_database_id** column of the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view for non-NULL values.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="30653-119">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="30653-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="30653-120">Creare uno snapshot del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="30653-120">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="30653-121">Ripristinare un database a uno snapshot del database</span><span class="sxs-lookup"><span data-stu-id="30653-121">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="30653-122">Eliminare uno snapshot del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="30653-122">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="30653-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30653-123">See Also</span></span>  
 [<span data-ttu-id="30653-124">Snapshot del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="30653-124">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
