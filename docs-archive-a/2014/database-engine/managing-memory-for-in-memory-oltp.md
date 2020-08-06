---
title: Gestione della memoria per OLTP in memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: d82f21fa-6be1-4723-a72e-f2526fafd1b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90f9b638697d59a0a573a9a31c0a5faade23e870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723020"
---
# <a name="managing-memory-for-in-memory-oltp"></a><span data-ttu-id="db8e5-102">Gestione della memoria per OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="db8e5-102">Managing Memory for In-Memory OLTP</span></span>
  <span data-ttu-id="db8e5-103">Le tabelle con ottimizzazione per la memoria richiedono memoria sufficiente per mantenere tutte le righe e tutti gli indici in memoria.</span><span class="sxs-lookup"><span data-stu-id="db8e5-103">Memory-optimized tables require that sufficient memory exist to keep all of the rows and indexes in memory.</span></span> <span data-ttu-id="db8e5-104">Poiché la memoria è una risorsa limitata, è importante conoscere e gestire l'utilizzo di memoria nel sistema.</span><span class="sxs-lookup"><span data-stu-id="db8e5-104">Because memory is a finite resource, it is important that you understand and manage memory usage on your system.</span></span> <span data-ttu-id="db8e5-105">Negli argomenti di questa sezione vengono illustrati gli scenari comuni di utilizzo e gestione della memoria.</span><span class="sxs-lookup"><span data-stu-id="db8e5-105">The topics in this section cover common memory use and management scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db8e5-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="db8e5-106">In this section</span></span>  
  
|<span data-ttu-id="db8e5-107">Sezione</span><span class="sxs-lookup"><span data-stu-id="db8e5-107">Section</span></span>|<span data-ttu-id="db8e5-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db8e5-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db8e5-109">Stimare i requisiti di memoria delle tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="db8e5-109">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)|<span data-ttu-id="db8e5-110">Stimare le esigenze di memoria di una tabella.</span><span class="sxs-lookup"><span data-stu-id="db8e5-110">Estimate a table's memory needs.</span></span>|  
|[<span data-ttu-id="db8e5-111">Associare un database con tabelle con ottimizzazione per la memoria a un pool di risorse</span><span class="sxs-lookup"><span data-stu-id="db8e5-111">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md)|<span data-ttu-id="db8e5-112">Procedura dettagliata per associare un database a un pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="db8e5-112">Step by step walkthrough to bind a database with a resource pool.</span></span>|  
|[<span data-ttu-id="db8e5-113">Monitorare e risolvere i problemi relativi all'utilizzo della memoria</span><span class="sxs-lookup"><span data-stu-id="db8e5-113">Monitor and Troubleshoot Memory Usage</span></span>](../relational-databases/in-memory-oltp/monitor-and-troubleshoot-memory-usage.md)|<span data-ttu-id="db8e5-114">Strumenti che è possibile utilizzare per monitorare l'utilizzo di memoria.</span><span class="sxs-lookup"><span data-stu-id="db8e5-114">Tools you can use to monitor your memory usage.</span></span> <span data-ttu-id="db8e5-115">Viene illustrata anche la risoluzione dei problemi nel caso in cui l'utilizzo di memoria diventi troppo elevato.</span><span class="sxs-lookup"><span data-stu-id="db8e5-115">Also covers troubleshooting if memory usage gets too high.</span></span>|  
|[<span data-ttu-id="db8e5-116">Risolvere i problemi di memoria insufficiente</span><span class="sxs-lookup"><span data-stu-id="db8e5-116">Resolve Out Of Memory Issues</span></span>](../relational-databases/in-memory-oltp/resolve-out-of-memory-issues.md)|<span data-ttu-id="db8e5-117">Passaggi per recuperare da una situazione di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="db8e5-117">Steps to recover from an OOM (Out of Memory) situation.</span></span>|  
|[<span data-ttu-id="db8e5-118">Ripristinare un database e associarlo a un pool di risorse</span><span class="sxs-lookup"><span data-stu-id="db8e5-118">Restore a Database and Bind it to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md)|<span data-ttu-id="db8e5-119">Passaggi per ripristinare un database di [!INCLUDE[hek_2](../includes/hek-2-md.md)] e associarlo a un pool di risorse denominato.</span><span class="sxs-lookup"><span data-stu-id="db8e5-119">Steps to restore an [!INCLUDE[hek_2](../includes/hek-2-md.md)] database and bind it to a named resource pool.</span></span>|  
|[<span data-ttu-id="db8e5-120">Garbage Collection per OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="db8e5-120">In-Memory OLTP Garbage Collection</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-garbage-collection.md)|<span data-ttu-id="db8e5-121">Informazioni sul funzionamento di Garbage Collection su righe eliminate.</span><span class="sxs-lookup"><span data-stu-id="db8e5-121">Understand how garbage collection operates on deleted rows.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db8e5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db8e5-122">See Also</span></span>  
 [<span data-ttu-id="db8e5-123">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="db8e5-123">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
