---
title: Attività Compatta database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.shrinkdatabasetask.f1
helpviewer_keywords:
- Shrink Database task
- database shrinking [Integration Services]
- shrinking databases
ms.assetid: e66286f8-97b1-4e5a-86b4-e56f1932b7d5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 587777928e362e87e4b691e3c46167c1239984cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636339"
---
# <a name="shrink-database-task"></a><span data-ttu-id="79342-102">Compatta database - attività</span><span class="sxs-lookup"><span data-stu-id="79342-102">Shrink Database Task</span></span>
  <span data-ttu-id="79342-103">Con l'attività Compatta database è possibile ridurre le dimensioni dei file di log e di dati del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79342-103">The Shrink Database task reduces the size of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database data and log files.</span></span>  
  
 <span data-ttu-id="79342-104">Tramite l'attività Compatta database un pacchetto può compattare file per uno o più database.</span><span class="sxs-lookup"><span data-stu-id="79342-104">By using the Shrink Database task, a package can shrink files for a single database or multiple databases.</span></span>  
  
 <span data-ttu-id="79342-105">Compattando i file di dati si recupera spazio spostando le pagine di dati dalla fine del file allo spazio non occupato più vicino all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="79342-105">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="79342-106">Quando alla fine del file viene creato sufficiente spazio libero, le pagine di dati possono essere deallocate e restituite al file system.</span><span class="sxs-lookup"><span data-stu-id="79342-106">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="79342-107">I dati spostati per ridurre un file possono essere dispersi in qualsiasi percorso disponibile nel file,</span><span class="sxs-lookup"><span data-stu-id="79342-107">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="79342-108">provocando la frammentazione dell'indice e rallentando le prestazioni di query che eseguono ricerche in un intervallo dell'indice</span><span class="sxs-lookup"><span data-stu-id="79342-108">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="79342-109">Per eliminare la frammentazione, valutare la possibilità di ricompilare gli indici sul file dopo la compattazione.</span><span class="sxs-lookup"><span data-stu-id="79342-109">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="commands"></a><span data-ttu-id="79342-110">Comandi:</span><span class="sxs-lookup"><span data-stu-id="79342-110">Commands</span></span>  
 <span data-ttu-id="79342-111">L'attività Compatta database incapsula un comando DBCC SHRINKDATABASE, che include gli argomenti e le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="79342-111">The Shrink Database task encapsulates a DBCC SHRINKDATABASE command, including the following arguments and options:</span></span>  
  
-   <span data-ttu-id="79342-112">*database_name*</span><span class="sxs-lookup"><span data-stu-id="79342-112">*database_name*</span></span>  
  
-   <span data-ttu-id="79342-113">*target_percent*</span><span class="sxs-lookup"><span data-stu-id="79342-113">*target_percent*</span></span>  
  
-   <span data-ttu-id="79342-114">NOTRUNCATE o TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="79342-114">NOTRUNCATE or TRUNCATEONLY.</span></span>  
  
 <span data-ttu-id="79342-115">Se si utilizza l'attività Compatta database per compattare più database, verranno eseguiti più comandi SHRINKDATABASE, uno per ogni database.</span><span class="sxs-lookup"><span data-stu-id="79342-115">If the Shrink Database task shrinks multiple databases, the task runs multiple SHRINKDATABASE commands, one for each database.</span></span> <span data-ttu-id="79342-116">Vengono usati gli stessi argomenti per tutte le istanze del comando SHRINKDATABASE, ad eccezione dell'argomento *database_name* .</span><span class="sxs-lookup"><span data-stu-id="79342-116">All instances of the SHRINKDATABASE command use the same argument values, except for the *database_name* argument.</span></span> <span data-ttu-id="79342-117">Per altre informazioni, vedere [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="79342-117">For more information, see [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span></span>  
  
## <a name="configuration-of-the-shrink-database-task"></a><span data-ttu-id="79342-118">Configurazione dell'attività Compatta database</span><span class="sxs-lookup"><span data-stu-id="79342-118">Configuration of the Shrink Database Task</span></span>  
 <span data-ttu-id="79342-119">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79342-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="79342-120">Questa attività è disponibile nella sezione **Attività di manutenzione** della **casella degli strumenti** di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79342-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="79342-121">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="79342-121">For more information about the properties that you can set in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="79342-122">Attività Compatta database &#40;Piano di manutenzione&#41;</span><span class="sxs-lookup"><span data-stu-id="79342-122">Shrink Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/shrink-database-task-maintenance-plan.md)  
  
 <span data-ttu-id="79342-123">Per ulteriori informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="79342-123">For more information about setting these properties in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="79342-124">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="79342-124">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
