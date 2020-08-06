---
title: Recuperare informazioni sui trigger DDL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- status information [SQL Server], DDL triggers
- DDL triggers, metadata
ms.assetid: 462becea-292a-4b9e-bb98-533e89733911
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cd71d188c2f53bd9872359199c07d700688552d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637141"
---
# <a name="get-information-about-ddl-triggers"></a><span data-ttu-id="c86ab-102">Ottieni informazioni sui trigger DDL</span><span class="sxs-lookup"><span data-stu-id="c86ab-102">Get Information About DDL Triggers</span></span>
  <span data-ttu-id="c86ab-103">Le viste del catalogo elencate in questa sezione possono essere utilizzate per ottenere informazioni sui trigger DDL.</span><span class="sxs-lookup"><span data-stu-id="c86ab-103">The catalog views listed in this section can be used to get information about DDL Triggers.</span></span>  
  
 <span data-ttu-id="c86ab-104">**Per ottenere informazioni sugli eventi o sui gruppi di eventi che possono essere attivati da un trigger DDL.**</span><span class="sxs-lookup"><span data-stu-id="c86ab-104">**To get information about the events or event groups on which a DDL trigger can fire.**</span></span>  
  
-   [<span data-ttu-id="c86ab-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-event-types-transact-sql)  
  
 <span data-ttu-id="c86ab-106">**Per visualizzare le dipendenze di un trigger**</span><span class="sxs-lookup"><span data-stu-id="c86ab-106">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="c86ab-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="c86ab-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="c86ab-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="database-scoped-ddl-triggers"></a><span data-ttu-id="c86ab-110">Trigger DDL con ambito database</span><span class="sxs-lookup"><span data-stu-id="c86ab-110">Database-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="c86ab-111">**Per ottenere informazioni sui trigger con ambito database**</span><span class="sxs-lookup"><span data-stu-id="c86ab-111">**To get information about database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="c86ab-112">sys.triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-112">sys.triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql)  
  
 <span data-ttu-id="c86ab-113">**Per ottenere informazioni sugli eventi di database che attivano i trigger**</span><span class="sxs-lookup"><span data-stu-id="c86ab-113">**To get information about database events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="c86ab-114">sys.trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-114">sys.trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql)  
  
 <span data-ttu-id="c86ab-115">**Per visualizzare la definizione di un trigger con ambito database**</span><span class="sxs-lookup"><span data-stu-id="c86ab-115">**To view the definition of a database-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="c86ab-116">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-116">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
 <span data-ttu-id="c86ab-117">**Per ottenere informazioni sui trigger CLR con ambito database**</span><span class="sxs-lookup"><span data-stu-id="c86ab-117">**To get information about CLR database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="c86ab-118">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-118">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
## <a name="server-scoped-ddl-triggers"></a><span data-ttu-id="c86ab-119">Trigger DDL con ambito server</span><span class="sxs-lookup"><span data-stu-id="c86ab-119">Server-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="c86ab-120">**Per ottenere informazioni sui trigger con ambito server**</span><span class="sxs-lookup"><span data-stu-id="c86ab-120">**To get information about server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="c86ab-121">sys.server_triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-121">sys.server_triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql)  
  
 <span data-ttu-id="c86ab-122">**Per ottenere informazioni sugli eventi del server che attivano i trigger**</span><span class="sxs-lookup"><span data-stu-id="c86ab-122">**To get information about server events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="c86ab-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql)  
  
 <span data-ttu-id="c86ab-124">**Per visualizzare la definizione di un trigger con ambito server**</span><span class="sxs-lookup"><span data-stu-id="c86ab-124">**To view the definition of a server-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="c86ab-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql)  
  
 <span data-ttu-id="c86ab-126">**Per ottenere informazioni sui trigger CLR con ambito server**</span><span class="sxs-lookup"><span data-stu-id="c86ab-126">**To get information about CLR server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="c86ab-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c86ab-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="c86ab-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c86ab-128">See Also</span></span>  
 [<span data-ttu-id="c86ab-129">Trigger DDL</span><span class="sxs-lookup"><span data-stu-id="c86ab-129">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
