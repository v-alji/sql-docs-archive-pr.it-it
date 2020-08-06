---
title: Classe di evento CPU Threshold Exceeded | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- CPU Threshold Exceeded Event Class
ms.assetid: eb106f7d-baa3-4a2b-96b2-f9fe0844057d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07b51e1a6f08f48c601b00d2dcb67bc6d09006f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624758"
---
# <a name="cpu-threshold-exceeded-event-class"></a><span data-ttu-id="5a4ba-102">Classe di evento CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="5a4ba-102">CPU Threshold Exceeded Event Class</span></span>
  <span data-ttu-id="5a4ba-103">Questa classe di evento indica il rilevamento di una query che supera il valore soglia della CPU specificato per REQUEST_MAX_CPU_TIME_SEC.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-103">The CPU Threshold Exceeded event class indicates that Resource Governor detects a query that exceeds the CPU threshold specified for REQUEST_MAX_CPU_TIME_SEC.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a4ba-104">L'intervallo di rilevamento per questo evento è cinque secondi.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-104">The detection interval for this event is five seconds.</span></span> <span data-ttu-id="5a4ba-105">È garantita la generazione di un evento se una query supera il limite specificato di almeno cinque secondi.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-105">It is guaranteed that an event will be generated if a query exceeds the specified limit by at least five seconds.</span></span> <span data-ttu-id="5a4ba-106">Tuttavia, se una query supera la soglia specificata di meno di cinque secondi, il rilevamento potrebbe non riuscire a seconda del momento della query e dell'ora dell'ultima operazione di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-106">However, if a query exceeds the specified threshold by less than five seconds, its detection might be missed depending on the timing of the query and the time of last detection sweep.</span></span>  
  
## <a name="cpu-threshold-exceeded-data-columns"></a><span data-ttu-id="5a4ba-107">Colonne di dati di CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="5a4ba-107">CPU Threshold Exceeded Data Columns</span></span>  
  
|<span data-ttu-id="5a4ba-108">Nome colonna di dati</span><span class="sxs-lookup"><span data-stu-id="5a4ba-108">Data column name</span></span>|<span data-ttu-id="5a4ba-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5a4ba-109">Data type</span></span>|<span data-ttu-id="5a4ba-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a4ba-110">Description</span></span>|<span data-ttu-id="5a4ba-111">ID colonna</span><span class="sxs-lookup"><span data-stu-id="5a4ba-111">Column ID</span></span>|<span data-ttu-id="5a4ba-112">Filtrabile</span><span class="sxs-lookup"><span data-stu-id="5a4ba-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="5a4ba-113">CPU</span><span class="sxs-lookup"><span data-stu-id="5a4ba-113">CPU</span></span>|`int`|<span data-ttu-id="5a4ba-114">Utilizzo della CPU in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-114">CPU usage in milliseconds.</span></span>|<span data-ttu-id="5a4ba-115">18</span><span class="sxs-lookup"><span data-stu-id="5a4ba-115">18</span></span>|<span data-ttu-id="5a4ba-116">Sì</span><span class="sxs-lookup"><span data-stu-id="5a4ba-116">Yes</span></span>|  
|<span data-ttu-id="5a4ba-117">EventClass</span><span class="sxs-lookup"><span data-stu-id="5a4ba-117">EventClass</span></span>|`int`|<span data-ttu-id="5a4ba-118">214</span><span class="sxs-lookup"><span data-stu-id="5a4ba-118">214</span></span>|<span data-ttu-id="5a4ba-119">27</span><span class="sxs-lookup"><span data-stu-id="5a4ba-119">27</span></span>|<span data-ttu-id="5a4ba-120">No</span><span class="sxs-lookup"><span data-stu-id="5a4ba-120">No</span></span>|  
|<span data-ttu-id="5a4ba-121">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="5a4ba-121">EventSubClass</span></span>|`int`|<span data-ttu-id="5a4ba-122">Violazione del limite della CPU.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-122">CPU limit violation.</span></span>|<span data-ttu-id="5a4ba-123">21</span><span class="sxs-lookup"><span data-stu-id="5a4ba-123">21</span></span>|<span data-ttu-id="5a4ba-124">Sì</span><span class="sxs-lookup"><span data-stu-id="5a4ba-124">Yes</span></span>|  
|<span data-ttu-id="5a4ba-125">GroupID</span><span class="sxs-lookup"><span data-stu-id="5a4ba-125">GroupID</span></span>|`int`|<span data-ttu-id="5a4ba-126">ID del gruppo in cui si verifica la violazione.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-126">Group ID where the violation occurred.</span></span>|<span data-ttu-id="5a4ba-127">66</span><span class="sxs-lookup"><span data-stu-id="5a4ba-127">66</span></span>|<span data-ttu-id="5a4ba-128">Sì</span><span class="sxs-lookup"><span data-stu-id="5a4ba-128">Yes</span></span>|  
|<span data-ttu-id="5a4ba-129">OwnerID</span><span class="sxs-lookup"><span data-stu-id="5a4ba-129">OwnerID</span></span>|`int`|<span data-ttu-id="5a4ba-130">SPID del processo che provoca la violazione.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-130">SPID of the process that caused the violation.</span></span>|<span data-ttu-id="5a4ba-131">58</span><span class="sxs-lookup"><span data-stu-id="5a4ba-131">58</span></span>|<span data-ttu-id="5a4ba-132">Sì</span><span class="sxs-lookup"><span data-stu-id="5a4ba-132">Yes</span></span>|  
|<span data-ttu-id="5a4ba-133">SPID</span><span class="sxs-lookup"><span data-stu-id="5a4ba-133">SPID</span></span>|`int`|<span data-ttu-id="5a4ba-134">ID del processo del server che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-134">ID of the server process that fires this event.</span></span><br /><br /> <span data-ttu-id="5a4ba-135">Nota: può essere differente dallo SPID effettivo dell'utente se il thread di sistema convalida l'utilizzo della CPU come attività in background.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-135">Note: This can differ from the actual user SPID if a system thread validates CPU usage as a background task.</span></span>|<span data-ttu-id="5a4ba-136">12</span><span class="sxs-lookup"><span data-stu-id="5a4ba-136">12</span></span>|<span data-ttu-id="5a4ba-137">Sì</span><span class="sxs-lookup"><span data-stu-id="5a4ba-137">Yes</span></span>|  
|<span data-ttu-id="5a4ba-138">StartTime</span><span class="sxs-lookup"><span data-stu-id="5a4ba-138">StartTime</span></span>|`datetime`|<span data-ttu-id="5a4ba-139">Ora di generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="5a4ba-139">The time when this event fired.</span></span>|<span data-ttu-id="5a4ba-140">14</span><span class="sxs-lookup"><span data-stu-id="5a4ba-140">14</span></span>|<span data-ttu-id="5a4ba-141">Sì</span><span class="sxs-lookup"><span data-stu-id="5a4ba-141">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a4ba-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a4ba-142">See Also</span></span>  
 [<span data-ttu-id="5a4ba-143">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5a4ba-143">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
