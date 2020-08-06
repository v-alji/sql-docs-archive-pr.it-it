---
title: MSSQLSERVER_17884 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17884 (Database Engine error)
ms.assetid: 8d05ba05-3f71-4dc3-bd81-2ea5ac9fe843
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd5beca2a7dfd20afbf9eff196d89452ef3533d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718203"
---
# <a name="mssqlserver_17884"></a><span data-ttu-id="c54b4-102">MSSQLSERVER_17884</span><span class="sxs-lookup"><span data-stu-id="c54b4-102">MSSQLSERVER_17884</span></span>
    
## <a name="details"></a><span data-ttu-id="c54b4-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c54b4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c54b4-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="c54b4-104">Product Name</span></span>|<span data-ttu-id="c54b4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c54b4-105">SQL Server</span></span>|  
|<span data-ttu-id="c54b4-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="c54b4-106">Event ID</span></span>|<span data-ttu-id="c54b4-107">17884</span><span class="sxs-lookup"><span data-stu-id="c54b4-107">17884</span></span>|  
|<span data-ttu-id="c54b4-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="c54b4-108">Event Source</span></span>|<span data-ttu-id="c54b4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c54b4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c54b4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c54b4-110">Component</span></span>|<span data-ttu-id="c54b4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c54b4-111">SQLEngine</span></span>|  
|<span data-ttu-id="c54b4-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="c54b4-112">Symbolic Name</span></span>|<span data-ttu-id="c54b4-113">SRV_SCHEDULER_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="c54b4-113">SRV_SCHEDULER_DEADLOCK</span></span>|  
|<span data-ttu-id="c54b4-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="c54b4-114">Message Text</span></span>|<span data-ttu-id="c54b4-115">Nessun thread di lavoro ha prelevato nuove query assegnate al processo nel nodo % negli ultimi %d secondi.</span><span class="sxs-lookup"><span data-stu-id="c54b4-115">New queries assigned to process on Node %d have not been picked  up by a worker thread in the last %d seconds.</span></span> <span data-ttu-id="c54b4-116">La situazione potrebbe essere causata da query bloccate o con esecuzione prolungata che possono peggiorare i tempi di risposta del client.</span><span class="sxs-lookup"><span data-stu-id="c54b4-116">Blocking or long-running queries can contribute to this condition, and may degrade client response time.</span></span> <span data-ttu-id="c54b4-117">Utilizzare l'opzione di configurazione "max worker thread" per aumentare il numero di thread consentiti oppure ottimizzare le query in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c54b4-117">Use the "max worker threads" configuration option to increase number  of allowable threads, or optimize current running queries.</span></span>  <span data-ttu-id="c54b4-118">Utilizzo processo SQL: %d%%.</span><span class="sxs-lookup"><span data-stu-id="c54b4-118">SQL Process Utilization: %d%%.</span></span> <span data-ttu-id="c54b4-119">Inattività del sistema: %d%%.</span><span class="sxs-lookup"><span data-stu-id="c54b4-119">System Idle: %d%%.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c54b4-120">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="c54b4-120">Explanation</span></span>  
 <span data-ttu-id="c54b4-121">Non è presente alcun segnale relativo allo stato di avanzamento in alcuna utilità di pianificazione. Questa situazione potrebbe essere causata da deadlock per cui nessun thread può avanzare e/o nessun lavoro può essere scelto ed elaborato.</span><span class="sxs-lookup"><span data-stu-id="c54b4-121">There is no sign of progress in each of the schedulers and could be caused by deadlocks where none of the threads can advance and/or no new work can be picked up and processed.</span></span> <span data-ttu-id="c54b4-122">Se l'utilizzo del processo è basso, gli altri processi presenti nel computer potrebbero provocare l'esaurimento delle risorse della CPU relative ai processi del server.</span><span class="sxs-lookup"><span data-stu-id="c54b4-122">If process utilization is low then other processes on the machine may be causing the server process CPU starvation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c54b4-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="c54b4-123">User Action</span></span>  
 <span data-ttu-id="c54b4-124">Determinare il motivo del blocco e del mancato avanzamento e risolvere di conseguenza la situazione.</span><span class="sxs-lookup"><span data-stu-id="c54b4-124">Determine why there is blocking and no progress being made and resolve situation accordingly.</span></span> <span data-ttu-id="c54b4-125">Se l'utilizzo del processo è basso, controllare il carico nel sistema provocato dagli altri processi.</span><span class="sxs-lookup"><span data-stu-id="c54b4-125">If process utilization is low check the load on the system caused by other processes.</span></span>  
  
  
