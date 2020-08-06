---
title: SQL Server destinazioni degli eventi estesi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events]
- extended events [SQL Server], targets
ms.assetid: e281684c-40d1-4cf9-a0d4-7ea1ecffa384
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 010b7cc29543f266b77aaf180c50173ef9f70346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624316"
---
# <a name="sql-server-extended-events-targets"></a><span data-ttu-id="17faf-102">SQL Server Extended Events Targets</span><span class="sxs-lookup"><span data-stu-id="17faf-102">SQL Server Extended Events Targets</span></span>
  <span data-ttu-id="17faf-103">Le destinazioni degli eventi estesi di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sono consumer di eventi.</span><span class="sxs-lookup"><span data-stu-id="17faf-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events targets are event consumers.</span></span> <span data-ttu-id="17faf-104">Le destinazioni possono scrivere in un file, archiviare dati evento in un buffer di memoria o dati degli eventi di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="17faf-104">Targets can write to a file, store event data in a memory buffer, or aggregate event data.</span></span> <span data-ttu-id="17faf-105">Le destinazioni possono elaborare i dati in modo sincrono o asincrono.</span><span class="sxs-lookup"><span data-stu-id="17faf-105">Targets can process data synchronously or asynchronously.</span></span>  
  
 <span data-ttu-id="17faf-106">La progettazione degli eventi estesi assicura che per le destinazioni sia garantita la ricezione degli eventi solo una volta per sessione.</span><span class="sxs-lookup"><span data-stu-id="17faf-106">The Extended Events design ensures that targets are guaranteed to receive events once and only once per session.</span></span>  
  
 <span data-ttu-id="17faf-107">Gli eventi estesi forniscono le seguenti destinazioni che è possibile utilizzare per una sessione relativa ad essi:</span><span class="sxs-lookup"><span data-stu-id="17faf-107">Extended Events provide the following targets that you can use for an Extended Events session:</span></span>  
  
-   [<span data-ttu-id="17faf-108">Contatore eventi</span><span class="sxs-lookup"><span data-stu-id="17faf-108">Event counter</span></span>](../../2014/database-engine/event-counter-target.md)  
  
     <span data-ttu-id="17faf-109">Conta tutti gli eventi specificati che si verificano durante una sessione di eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="17faf-109">Counts all specified events that occur during an Extended Events session.</span></span> <span data-ttu-id="17faf-110">Consente di ottenere informazioni sulle funzionalità del carico di lavoro senza aggiungere l'overhead di un'intera raccolta di eventi.</span><span class="sxs-lookup"><span data-stu-id="17faf-110">Use to obtain information about workload characteristics without adding the overhead of full event collection.</span></span> <span data-ttu-id="17faf-111">Si tratta di una destinazione sincrona.</span><span class="sxs-lookup"><span data-stu-id="17faf-111">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="17faf-112">File di evento</span><span class="sxs-lookup"><span data-stu-id="17faf-112">Event file</span></span>](../../2014/database-engine/event-file-target.md)  
  
     <span data-ttu-id="17faf-113">Consente di scrivere l'output della sessione eventi restituito dai buffer di memoria completi su disco.</span><span class="sxs-lookup"><span data-stu-id="17faf-113">Use to write event session output from complete memory buffers to disk.</span></span> <span data-ttu-id="17faf-114">Si tratta di una destinazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="17faf-114">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="17faf-115">Abbinamento degli eventi</span><span class="sxs-lookup"><span data-stu-id="17faf-115">Event pairing</span></span>](../../2014/database-engine/event-pairing-target.md)  
  
     <span data-ttu-id="17faf-116">Molti tipi di eventi si verificano a coppie, ad esempio le acquisizioni e i rilasci del blocco.</span><span class="sxs-lookup"><span data-stu-id="17faf-116">Many kinds of events occur in pairs, such as lock acquires and lock releases.</span></span> <span data-ttu-id="17faf-117">Consente di determinare quando un evento associato specificato non si verifica in un set corrispondente.</span><span class="sxs-lookup"><span data-stu-id="17faf-117">Use to determine when a specified paired event does not occur in a matched set.</span></span> <span data-ttu-id="17faf-118">Si tratta di una destinazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="17faf-118">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="17faf-119">Event Tracing for Windows (ETW)</span><span class="sxs-lookup"><span data-stu-id="17faf-119">Event Tracing for Windows (ETW)</span></span>](../relational-databases/extended-events/event-tracing-for-windows-target.md)  
  
     <span data-ttu-id="17faf-120">Consente di correlare gli eventi di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con dati evento del sistema operativo Windows o dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="17faf-120">Use to correlate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events with Windows operating system or application event data.</span></span> <span data-ttu-id="17faf-121">Si tratta di una destinazione sincrona.</span><span class="sxs-lookup"><span data-stu-id="17faf-121">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="17faf-122">Istogramma</span><span class="sxs-lookup"><span data-stu-id="17faf-122">Histogram</span></span>](../../2014/database-engine/histogram-target.md)  
  
     <span data-ttu-id="17faf-123">Consente di calcolare il numero di volte in cui si verifica un evento specificato, in base a un'azione o una colonna di evento specificata.</span><span class="sxs-lookup"><span data-stu-id="17faf-123">Use to count the number of times that a specified event occurs, based on a specified event column or action.</span></span> <span data-ttu-id="17faf-124">Si tratta di una destinazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="17faf-124">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="17faf-125">Buffer circolare</span><span class="sxs-lookup"><span data-stu-id="17faf-125">Ring buffer</span></span>](../../2014/database-engine/ring-buffer-target.md)  
  
     <span data-ttu-id="17faf-126">Consente di mantenere i dati degli eventi in memoria secondo una modalità FIFO o secondo una modalità FIFO basata sul tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="17faf-126">Use to hold the event data in memory on a first-in first-out (FIFO) basis, or on a per-event FIFO basis.</span></span> <span data-ttu-id="17faf-127">Si tratta di una destinazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="17faf-127">This is an asynchronous target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17faf-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17faf-128">See Also</span></span>  
 <span data-ttu-id="17faf-129">[Eventi estesi](../relational-databases/extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="17faf-129">[Extended Events](../relational-databases/extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="17faf-130">[SQL Server pacchetti di eventi estesi](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span><span class="sxs-lookup"><span data-stu-id="17faf-130">[SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span></span>  
 <span data-ttu-id="17faf-131">[SQL Server sessioni eventi estesi](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="17faf-131">[SQL Server Extended Events Sessions](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span></span>  
 [<span data-ttu-id="17faf-132">Motore degli eventi estesi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="17faf-132">SQL Server Extended Events Engine</span></span>](../relational-databases/extended-events/sql-server-extended-events-engine.md)  
  
  
