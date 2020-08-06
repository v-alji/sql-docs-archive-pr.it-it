---
title: Sospendere una traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- pausing traces
- temporarily stopping traces
- traces [SQL Server], pausing
- stopping traces
ms.assetid: 432b9b0c-b5e7-47f3-a71b-310fb3bf2445
author: stevestein
ms.author: sstein
ms.openlocfilehash: cdc9dbbd01099b1d33787a72b0bd59b65cea722e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711248"
---
# <a name="pause-a-trace-sql-server-profiler"></a><span data-ttu-id="eb02c-102">Sospendere una traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="eb02c-102">Pause a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="eb02c-103">La sospensione di una traccia consente di impedire l'ulteriore acquisizione dei dati evento fino al riavvio della traccia.</span><span class="sxs-lookup"><span data-stu-id="eb02c-103">Pausing a trace prevents further event data from being captured until the trace is restarted.</span></span>  
  
 <span data-ttu-id="eb02c-104">Quando si sospende una traccia, è possibile impedire l'acquisizione dei dati evento fino al riavvio della traccia.</span><span class="sxs-lookup"><span data-stu-id="eb02c-104">When you pause a trace, you prevent event data from being captured until the trace is restarted.</span></span> <span data-ttu-id="eb02c-105">Il riavvio di una traccia consente di riprendere le operazioni di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="eb02c-105">Restarting a trace lets trace operations resume.</span></span> <span data-ttu-id="eb02c-106">Dopo il riavvio, gli eventuali dati acquisiti in precedenza non andranno perduti.</span><span class="sxs-lookup"><span data-stu-id="eb02c-106">No previously captured data is lost after a restart.</span></span> <span data-ttu-id="eb02c-107">Quando si riavvia la traccia, l'acquisizione dei dati riprende dal momento del riavvio.</span><span class="sxs-lookup"><span data-stu-id="eb02c-107">When the trace is restarted, data capturing resumes from that point onward.</span></span> <span data-ttu-id="eb02c-108">Durante la sospensione di una traccia è possibile modificarne il nome, gli eventi, le colonne e i filtri.</span><span class="sxs-lookup"><span data-stu-id="eb02c-108">While a trace is paused, you can change the name, events, columns, and filters.</span></span> <span data-ttu-id="eb02c-109">Non è invece possibile modificare le destinazioni di invio dei dati della traccia o la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="eb02c-109">However, you cannot change the destinations to which you are sending the trace data, nor change the server connection.</span></span>  
  
### <a name="to-pause-a-trace"></a><span data-ttu-id="eb02c-110">Per sospendere una traccia</span><span class="sxs-lookup"><span data-stu-id="eb02c-110">To pause a trace</span></span>  
  
1.  <span data-ttu-id="eb02c-111">Selezionare una finestra contenente una traccia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eb02c-111">Select a window that contains a running trace.</span></span>  
  
2.  <span data-ttu-id="eb02c-112">Nel menu **File** fare clic su **Sospendi traccia**.</span><span class="sxs-lookup"><span data-stu-id="eb02c-112">On the **File** menu, click **Pause Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb02c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb02c-113">See Also</span></span>  
 [<span data-ttu-id="eb02c-114">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="eb02c-114">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
