---
title: Oggetto ExecStatistics di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:ExecStatistics
- ExecStatistics object
ms.assetid: 4f8557a8-345f-4622-a8a5-763a0388ad94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d1a50c97add4708a58b9edc45fd49982b97a51ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625341"
---
# <a name="sql-server-execstatistics-object"></a><span data-ttu-id="20668-102">Oggetto ExecStatistics di SQL Server</span><span class="sxs-lookup"><span data-stu-id="20668-102">SQL Server, ExecStatistics Object</span></span>
  <span data-ttu-id="20668-103">L'oggetto **SQLServer:ExecStatistics** di Microsoft SQL Server include contatori che consentono di monitorare diversi tipi di esecuzioni.</span><span class="sxs-lookup"><span data-stu-id="20668-103">The **SQLServer:ExecStatistics** object in Microsoft SQL Server provides counters to monitor various executions.</span></span>  
  
 <span data-ttu-id="20668-104">Nella tabella seguente vengono descritti i contatori **Exec Statistics** di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20668-104">This table describes the SQL Server **Exec Statistics** counters.</span></span>  
  
|<span data-ttu-id="20668-105">Contatori Exec Statistics di SQL Server</span><span class="sxs-lookup"><span data-stu-id="20668-105">SQL Server Exec Statistics counters</span></span>|<span data-ttu-id="20668-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20668-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="20668-107">**Query distribuite**</span><span class="sxs-lookup"><span data-stu-id="20668-107">**Distributed Query**</span></span>|<span data-ttu-id="20668-108">Statistiche relative all'esecuzione di query distribuite.</span><span class="sxs-lookup"><span data-stu-id="20668-108">Statistics relevant to execution of distributed queries.</span></span>|  
|<span data-ttu-id="20668-109">**Chiamate DTC**</span><span class="sxs-lookup"><span data-stu-id="20668-109">**DTC calls**</span></span>|<span data-ttu-id="20668-110">Statistiche relative all'esecuzione di chiamate DTC.</span><span class="sxs-lookup"><span data-stu-id="20668-110">Statistics relevant to execution of DTC calls.</span></span>|  
|<span data-ttu-id="20668-111">**Procedure estese**</span><span class="sxs-lookup"><span data-stu-id="20668-111">**Extended Procedures**</span></span>|<span data-ttu-id="20668-112">Statistiche relative all'esecuzione di procedure estese.</span><span class="sxs-lookup"><span data-stu-id="20668-112">Statistics relevant to execution of extended procedures.</span></span>|  
|<span data-ttu-id="20668-113">**Chiamate OLEDB**</span><span class="sxs-lookup"><span data-stu-id="20668-113">**OLEDB calls**</span></span>|<span data-ttu-id="20668-114">Statistiche relative all'esecuzione di chiamate OLEDB.</span><span class="sxs-lookup"><span data-stu-id="20668-114">Statistics relevant to execution of OLEDB calls.</span></span>|  
  
 <span data-ttu-id="20668-115">Per ogni contatore nell'oggetto sono disponibili le istanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="20668-115">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="20668-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="20668-116">Item</span></span>|<span data-ttu-id="20668-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20668-117">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="20668-118">**Tempo di esecuzione (ms) medio**</span><span class="sxs-lookup"><span data-stu-id="20668-118">**Average execution time (ms)**</span></span>|<span data-ttu-id="20668-119">Durata media per il tipo di esecuzione selezionato.</span><span class="sxs-lookup"><span data-stu-id="20668-119">Average execution time of the selected type of execution.</span></span>|  
|<span data-ttu-id="20668-120">**Tempo di esecuzione (ms) cumulativo al secondo**</span><span class="sxs-lookup"><span data-stu-id="20668-120">**Cumulative execution time (ms) per second**</span></span>|<span data-ttu-id="20668-121">Tempo di esecuzione complessivo al secondo per il tipo di esecuzione selezionato.</span><span class="sxs-lookup"><span data-stu-id="20668-121">Aggregated execution time per second, of the selected type of execution.</span></span>|  
|<span data-ttu-id="20668-122">**Esecuzioni in corso**</span><span class="sxs-lookup"><span data-stu-id="20668-122">**Execs in progress**</span></span>|<span data-ttu-id="20668-123">Numero di esecuzioni in corso per il tipo di esecuzione selezionato.</span><span class="sxs-lookup"><span data-stu-id="20668-123">Number of execs in progress of the selected type of execution.</span></span>|  
|<span data-ttu-id="20668-124">**Esecuzioni avviate al secondo**</span><span class="sxs-lookup"><span data-stu-id="20668-124">**Exec started per second**</span></span>|<span data-ttu-id="20668-125">Numero di esecuzioni avviate al secondo per il tipo di esecuzione selezionato.</span><span class="sxs-lookup"><span data-stu-id="20668-125">Number of exes started per second of the selected type of execution.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20668-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20668-126">See Also</span></span>  
 [<span data-ttu-id="20668-127">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="20668-127">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
