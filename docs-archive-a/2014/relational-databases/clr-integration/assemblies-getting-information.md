---
title: Recupero di informazioni sugli assembly | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], metadata
- status information [SQL Server], assemblies
- metadata [SQL Server], assemblies
ms.assetid: 6aa7f18e-baad-4481-9777-8c3b230b392f
author: rothja
ms.author: jroth
ms.openlocfilehash: ec559ba5ccbb53dd92f3a5e1175a10a59fbaf43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720070"
---
# <a name="getting-information-about-assemblies"></a><span data-ttu-id="64181-102">Recupero di informazioni sugli assembly</span><span class="sxs-lookup"><span data-stu-id="64181-102">Getting Information About Assemblies</span></span>
  <span data-ttu-id="64181-103">È possibile recuperare metadati sugli assembly eseguendo query sulle funzioni e sulle viste del catalogo seguenti.</span><span class="sxs-lookup"><span data-stu-id="64181-103">The following catalog views and functions can be queried for metadata about assemblies.</span></span>  
  
 <span data-ttu-id="64181-104">**Per ottenere informazioni su singoli assembly**</span><span class="sxs-lookup"><span data-stu-id="64181-104">**To get information about individual assemblies**</span></span>  
  
-   [<span data-ttu-id="64181-105">ASSEMBLYPROPERTY &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="64181-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/assemblyproperty-transact-sql)  
  
 <span data-ttu-id="64181-106">**Per ottenere informazioni su tutti gli assembly contenuti nel database**</span><span class="sxs-lookup"><span data-stu-id="64181-106">**To get information about all assemblies in the database**</span></span>  
  
-   [<span data-ttu-id="64181-107">sys.assemblies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64181-107">sys.assemblies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assemblies-transact-sql)  
  
 <span data-ttu-id="64181-108">**Per ottenere informazioni sui file di assembly, inclusi i file binari, di origine e di debug**</span><span class="sxs-lookup"><span data-stu-id="64181-108">**To get information about assembly files, including assembly binaries, source files, and debug files**</span></span>  
  
-   [<span data-ttu-id="64181-109">sys.assembly_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64181-109">sys.assembly_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-files-transact-sql)  
  
 <span data-ttu-id="64181-110">**Per ottenere informazioni sui riferimenti tra assembly**</span><span class="sxs-lookup"><span data-stu-id="64181-110">**To get information about cross-assembly references**</span></span>  
  
-   [<span data-ttu-id="64181-111">sys.assembly_references &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64181-111">sys.assembly_references &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-references-transact-sql)  
  
 <span data-ttu-id="64181-112">**Per ottenere informazioni sui tipi definiti dall'utente utilizzati negli assembly**</span><span class="sxs-lookup"><span data-stu-id="64181-112">**To get assembly information about user-defined types**</span></span>  
  
-   [<span data-ttu-id="64181-113">sys.assembly_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64181-113">sys.assembly_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-types-transact-sql)  
  
-   [<span data-ttu-id="64181-114">sys.types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64181-114">sys.types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-types-transact-sql)  
  
 <span data-ttu-id="64181-115">**Per ottenere informazioni sulle stored procedure, i trigger e le funzioni di Common Language Runtime (CLR) utilizzati negli assembly**</span><span class="sxs-lookup"><span data-stu-id="64181-115">**To get assembly information about common language runtime (CLR) stored procedures, triggers, and functions**</span></span>  
  
-   [<span data-ttu-id="64181-116">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64181-116">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
 <span data-ttu-id="64181-117">**Per ottenere informazioni su oggetti non CLR**</span><span class="sxs-lookup"><span data-stu-id="64181-117">**To get information about non-CLR objects**</span></span>  
  
-   [<span data-ttu-id="64181-118">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64181-118">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="64181-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64181-119">See Also</span></span>  
 <span data-ttu-id="64181-120">[Assembly &#40;motore di database&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="64181-120">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="64181-121">[Progettazione di assembly](../../relational-databases/clr-integration/assemblies-designing.md) </span><span class="sxs-lookup"><span data-stu-id="64181-121">[Designing Assemblies](../../relational-databases/clr-integration/assemblies-designing.md) </span></span>  
 [<span data-ttu-id="64181-122">Implementazione di assembly</span><span class="sxs-lookup"><span data-stu-id="64181-122">Implementing Assemblies</span></span>](assemblies-implementing.md)  
  
  
