---
title: Arrestare una traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], stopping
- stopping traces
ms.assetid: 47c4f33d-63e0-4444-bec8-4c1c91f8e25c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 501ea4a4838f8e2ea42fc475c486466d48020a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719146"
---
# <a name="stop-a-trace-sql-server-profiler"></a><span data-ttu-id="12a36-102">Arrestare una traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="12a36-102">Stop a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="12a36-103">In questo argomento viene illustrato l'arresto di una traccia in esecuzione utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12a36-103">This topic describes how to stop a trace that is running by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="12a36-104">L'arresto di una traccia comporta l'arresto dell'acquisizione dei dati.</span><span class="sxs-lookup"><span data-stu-id="12a36-104">Stopping a trace stops data from being captured.</span></span> <span data-ttu-id="12a36-105">Dopo l'arresto, non è possibile riavviare una traccia senza perdere i dati acquisiti in precedenza, a meno che non siano stati acquisiti in un file o in una tabella.</span><span class="sxs-lookup"><span data-stu-id="12a36-105">After a trace is stopped, it cannot be restarted without losing previously captured data, unless the data has been captured to a trace file or trace table.</span></span> <span data-ttu-id="12a36-106">È inoltre possibile salvare i dati raccolti in una tabella o file dopo l'arresto di una traccia.</span><span class="sxs-lookup"><span data-stu-id="12a36-106">You can also save the collected data to a table or file after stopping a trace.</span></span> <span data-ttu-id="12a36-107">Tutte le proprietà della traccia precedentemente impostate vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="12a36-107">All trace properties that were previously selected are preserved when a trace is stopped.</span></span> <span data-ttu-id="12a36-108">In caso di arresto di una traccia, sarà possibile modificarne il nome, gli eventi, le colonne e i filtri.</span><span class="sxs-lookup"><span data-stu-id="12a36-108">When a trace is stopped, you can change the name, events, columns, and filters.</span></span>  
  
### <a name="to-stop-a-trace"></a><span data-ttu-id="12a36-109">Per arrestare una traccia</span><span class="sxs-lookup"><span data-stu-id="12a36-109">To stop a trace</span></span>  
  
1.  <span data-ttu-id="12a36-110">Selezionare una traccia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="12a36-110">Select a trace that is running.</span></span>  
  
2.  <span data-ttu-id="12a36-111">Nel menu **File** fare clic su **Arresta traccia**.</span><span class="sxs-lookup"><span data-stu-id="12a36-111">On the **File** menu, click **Stop Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a36-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12a36-112">See Also</span></span>  
 [<span data-ttu-id="12a36-113">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="12a36-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
