---
title: Cursori XTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 84bf4654-3ef7-4d7f-a269-c8bb4ed4acad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 217a1196717492cb92adb24eaf7c06c8867abc2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719859"
---
# <a name="xtp-cursors"></a><span data-ttu-id="c7be1-102">XTP Cursors</span><span class="sxs-lookup"><span data-stu-id="c7be1-102">XTP Cursors</span></span>
  <span data-ttu-id="c7be1-103">L'oggetto prestazione XTP Cursors contiene contatori correlati ai cursori interni del motore XTP.</span><span class="sxs-lookup"><span data-stu-id="c7be1-103">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="c7be1-104">I cursori sono i blocchi predefiniti di basso livello utilizzati dal motore XTP per elaborare query [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7be1-104">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="c7be1-105">Di conseguenza, in genere non si ha controllo diretto su di essi.</span><span class="sxs-lookup"><span data-stu-id="c7be1-105">As such, you do not typically have direct control over them.</span></span>  
  
 <span data-ttu-id="c7be1-106">In questa tabella vengono descritti i contatori **XTP Cursors** .</span><span class="sxs-lookup"><span data-stu-id="c7be1-106">This table describes the **XTP Cursors** counters.</span></span>  
  
|<span data-ttu-id="c7be1-107">Contatore</span><span class="sxs-lookup"><span data-stu-id="c7be1-107">Counter</span></span>|<span data-ttu-id="c7be1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7be1-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7be1-109">**Eliminazioni cursori/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-109">**Cursor deletes/sec**</span></span>|<span data-ttu-id="c7be1-110">Numero medio di eliminazioni di cursori, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-110">The number of cursor deletes (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-111">**Inserimenti cursori/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-111">**Cursor inserts/sec**</span></span>|<span data-ttu-id="c7be1-112">Numero medio di inserimenti di cursori, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-112">The number of cursor inserts (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-113">**Analisi cursore avviate/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-113">**Cursor scans started /sec**</span></span>|<span data-ttu-id="c7be1-114">Numero medio di analisi cursore avviate, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-114">The number of cursor scans started (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-115">**Violazioni UNIQUE del cursore/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-115">**Cursor unique violations/sec**</span></span>|<span data-ttu-id="c7be1-116">Numero medio di violazioni di vincolo UNIQUE, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-116">The number of unique-constraint violations (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-117">**Aggiornamenti cursori/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-117">**Cursor updates/sec**</span></span>|<span data-ttu-id="c7be1-118">Numero medio di aggiornamenti di cursori, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-118">The number of cursor updates (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-119">**Conflitti di scrittura cursore/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-119">**Cursor write   conflicts/sec**</span></span>|<span data-ttu-id="c7be1-120">Numero medio di conflitti di scrittura sulla stessa versione di riga, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-120">The number of write-write conflicts to the same row version (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-121">**Tentativi di analisi di elementi nascosti/sec (immessi dall'utente)**</span><span class="sxs-lookup"><span data-stu-id="c7be1-121">**Dusty corner scan retries/sec (user-issued)**</span></span>|<span data-ttu-id="c7be1-122">Numero medio di tentativi di analisi dovuti a conflitti di scrittura durante le operazioni su elementi nascosti eseguite da un'analisi di tabella completa dell'utente, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-122">The number of scan retries due to write conflicts during dusty corner sweeps issued by a user's full-table scan (on average), per second.</span></span> <span data-ttu-id="c7be1-123">Si tratta di un contatore di livello molto basso, non destinato all'uso da parte del cliente.</span><span class="sxs-lookup"><span data-stu-id="c7be1-123">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="c7be1-124">**Righe scadute rimosse/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-124">**Expired rows removed/sec**</span></span>|<span data-ttu-id="c7be1-125">Numero medio di righe scadute rimosse dai cursori, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-125">The number of expired rows removed by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-126">**Righe scadute interessate/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-126">**Expired rows touched/sec**</span></span>|<span data-ttu-id="c7be1-127">Numero medio di righe scadute interessate dai cursori, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-127">The number of expired rows touched by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-128">**Righe restituite/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-128">**Rows returned/sec**</span></span>|<span data-ttu-id="c7be1-129">Numero medio di righe restituite dai cursori, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-129">The number of rows returned by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-130">**Righe interessate/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-130">**Rows touched/sec**</span></span>|<span data-ttu-id="c7be1-131">Numero medio di righe interessate dai cursori, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-131">The number of rows touched by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="c7be1-132">**Righe provvisoriamente eliminate interessate/sec**</span><span class="sxs-lookup"><span data-stu-id="c7be1-132">**Tentatively-deleted rows touched/sec**</span></span>|<span data-ttu-id="c7be1-133">Numero medio di righe in scadenza interessate dai cursori, al secondo.</span><span class="sxs-lookup"><span data-stu-id="c7be1-133">The number of expiring rows touched by cursors (on average), per second.</span></span> <span data-ttu-id="c7be1-134">Una riga è in scadenza se la transazione che l'ha eliminata è ancora attiva (cioè non ne è stato ancora eseguito il commit o l'interruzione).</span><span class="sxs-lookup"><span data-stu-id="c7be1-134">A row is expiring if the transaction that deleted it is still active (i.e. has not yet committed or aborted.)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7be1-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7be1-135">See Also</span></span>  
 [<span data-ttu-id="c7be1-136">XTP &#40;i contatori delle prestazioni di OLTP in memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="c7be1-136">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
