---
title: Modificare i modelli di traccia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], SQL Server Profiler
- Profiler [SQL Server Profiler], templates
- trace templates [SQL Server]
- modifying trace templates
- SQL Server Profiler, templates
ms.assetid: 75b62a54-8d16-4599-bd2d-c42cfcc209f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a26d0a70f65b6ff60dcf42ffb98e67dc0d2b52d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624486"
---
# <a name="modify-trace-templates"></a><span data-ttu-id="4a47f-102">Modificare modelli di traccia</span><span class="sxs-lookup"><span data-stu-id="4a47f-102">Modify Trace Templates</span></span>
  <span data-ttu-id="4a47f-103">È possibile modificare i modelli salvati in un file nel computer locale che esegue [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a47f-103">You can modify templates that are saved in a file on the local computer on which [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is running.</span></span> <span data-ttu-id="4a47f-104">e inoltre modificare i modelli da essi derivati.</span><span class="sxs-lookup"><span data-stu-id="4a47f-104">You can also modify templates derived from those files.</span></span> <span data-ttu-id="4a47f-105">Per modificare i modelli esistenti, è possibile modificarne le proprietà, ad esempio le classi di evento e le colonne di dati, nell'ordine in cui sono state originariamente impostate nella scheda **Selezione eventi** della finestra di dialogo **Proprietà traccia** .</span><span class="sxs-lookup"><span data-stu-id="4a47f-105">When you modify existing templates, you edit template properties such as event classes and data columns, in the same order that the properties were set originally, on the **Events Selection** tab of the **Trace Properties** dialog box.</span></span> <span data-ttu-id="4a47f-106">È possibile aggiungere o rimuovere classi di evento e colonne di dati, nonché modificare i filtri.</span><span class="sxs-lookup"><span data-stu-id="4a47f-106">Event classes and data columns can be added or removed, and filters can be changed.</span></span> <span data-ttu-id="4a47f-107">Dopo avere modificato il modello, viene creato un modello specifico dell'utente e il modello di sistema originale rimarrà inalterato.</span><span class="sxs-lookup"><span data-stu-id="4a47f-107">After the template is modified, a user-specific template is created and the original system template is left intact.</span></span> <span data-ttu-id="4a47f-108">Per altre informazioni, vedere [Salvare tracce e modelli di traccia](save-traces-and-trace-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4a47f-108">For more information, see [Save Traces and Trace Templates](save-traces-and-trace-templates.md).</span></span>  
  
 <span data-ttu-id="4a47f-109">Potrebbe essere necessario ricavare un modello da un file di traccia esistente nel caso non sia possibile risalire al modello originale utilizzato per creare la traccia oppure se si desidera rieseguire la stessa traccia in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="4a47f-109">You may need to derive a template from an existing trace file if you cannot remember (or have not saved) the original template that was used to create the trace, or if you want to run the same trace at a later date.</span></span> <span data-ttu-id="4a47f-110">Quando si utilizzano tracce esistenti, è possibile visualizzare le proprietà ma non modificarle.</span><span class="sxs-lookup"><span data-stu-id="4a47f-110">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="4a47f-111">Per modificare le proprietà, arrestare o sospendere la traccia.</span><span class="sxs-lookup"><span data-stu-id="4a47f-111">To modify the properties, stop or pause the trace.</span></span> <span data-ttu-id="4a47f-112">Per altre informazioni, vedere [Derivare un modello da un file di traccia o da una tabella di traccia &#40;SQL Server Profiler&#41;](sql-server-profiler.md) e [Ottenere un modello da una traccia in esecuzione &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="4a47f-112">For more information, see [Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](sql-server-profiler.md) and [Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="4a47f-113">**Per creare un modello di traccia**</span><span class="sxs-lookup"><span data-stu-id="4a47f-113">**To create a trace template**</span></span>  
  
 [<span data-ttu-id="4a47f-114">Creare un modello di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4a47f-114">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="4a47f-115">**Per eseguire una traccia da un modello di traccia**</span><span class="sxs-lookup"><span data-stu-id="4a47f-115">**To run a trace from a trace template**</span></span>  
  
 [<span data-ttu-id="4a47f-116">Creare una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4a47f-116">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="4a47f-117">**Per modificare un modello di traccia**</span><span class="sxs-lookup"><span data-stu-id="4a47f-117">**To modify a trace template**</span></span>  
  
 [<span data-ttu-id="4a47f-118">Utilizzo di SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4a47f-118">Using SQL Server Profiler</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
 [<span data-ttu-id="4a47f-119">Utilizzo di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a47f-119">Using Transact-SQL</span></span>](../../relational-databases/sql-trace/modify-an-existing-trace-transact-sql.md)  
  
 <span data-ttu-id="4a47f-120">**Per aggiungere o rimuovere eventi da un modello di traccia o da un file di traccia**</span><span class="sxs-lookup"><span data-stu-id="4a47f-120">**To add or remove events from a trace template or trace file**</span></span>  
  
 [<span data-ttu-id="4a47f-121">Utilizzo di SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4a47f-121">Using SQL Server Profiler</span></span>](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="4a47f-122">Utilizzo di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a47f-122">Using Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="4a47f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a47f-123">See Also</span></span>  
 [<span data-ttu-id="4a47f-124">Avviare una traccia</span><span class="sxs-lookup"><span data-stu-id="4a47f-124">Start a Trace</span></span>](start-a-trace.md)  
  
  
