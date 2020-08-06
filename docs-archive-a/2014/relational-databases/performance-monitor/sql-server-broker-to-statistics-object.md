---
title: Oggetto Broker TO Statistics di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Broker Transmission Object object
- 'SQL Server: Broker Transmission Object'
ms.assetid: b5bc5dde-e540-4848-8aa3-5735c51df2fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 93d9c24a175dedfee171eccfccb34673501660ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636027"
---
# <a name="sql-server-broker-to-statistics-object"></a><span data-ttu-id="0753a-102">Oggetto Statistiche Broker TO di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0753a-102">SQL Server, Broker TO Statistics Object</span></span>
  <span data-ttu-id="0753a-103">L'oggetto prestazione SQLServer:Broker TO Statistics contiene informazioni sul numero di volte in cui le finestre di dialogo di [!INCLUDE[ssSB](../../includes/sssb-md.md)] richiedono oggetti trasmissione e sulla frequenza di scrittura degli oggetti trasmissione in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0753a-103">The SQLServer:Broker TO Statistics performance object reports information about how many times [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialogs request transmission objects, and how often transmission objects are written to **tempdb**.</span></span>  
  
 <span data-ttu-id="0753a-104">Gli oggetti di trasmissione registrano lo stato delle trasmissioni di messaggi per una finestra di dialogo [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0753a-104">Transmission objects record the state of message transmissions for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialog.</span></span> <span data-ttu-id="0753a-105">Poiché vengono archiviati in memoria,</span><span class="sxs-lookup"><span data-stu-id="0753a-105">They are stored in memory.</span></span> <span data-ttu-id="0753a-106">Per liberare memoria, [!INCLUDE[ssSB](../../includes/sssb-md.md)] scrive periodicamente batch di oggetti trasmissione inattivi nelle tabelle di lavoro di **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0753a-106">To free memory, [!INCLUDE[ssSB](../../includes/sssb-md.md)] periodically writes batches of inactive transmission objects to work tables in **tempdb**.</span></span>  
  
 <span data-ttu-id="0753a-107">Nella tabella seguente sono elencati i contatori inclusi nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0753a-107">The following table lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="0753a-108">Contatori dell'oggetto Statistiche Broker TO di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0753a-108">SQL Server Broker TO Statistics counters</span></span>|<span data-ttu-id="0753a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0753a-109">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<span data-ttu-id="0753a-110">**Byte media scritture in batch**</span><span class="sxs-lookup"><span data-stu-id="0753a-110">**Avg. Length of Batched Writes**</span></span>|<span data-ttu-id="0753a-111">La quantità media di oggetti di trasmissione salvati in un batch.</span><span class="sxs-lookup"><span data-stu-id="0753a-111">The average number of transmission objects saved in a batch.</span></span>|  
|<span data-ttu-id="0753a-112">**Byte medio scrittura in batch (ms)**</span><span class="sxs-lookup"><span data-stu-id="0753a-112">**Avg. Time To Write Batch (ms)**</span></span>|<span data-ttu-id="0753a-113">Il tempo medio espresso in millisecondi richiesto per salvare un batch di oggetti di trasmissione.</span><span class="sxs-lookup"><span data-stu-id="0753a-113">The average number of milliseconds required to save a batch of transmission objects.</span></span>|  
|<span data-ttu-id="0753a-114">**Byte medio tra batch (ms)**</span><span class="sxs-lookup"><span data-stu-id="0753a-114">**Avg. Time Between Batches (ms)**</span></span>|<span data-ttu-id="0753a-115">Il tempo medio espresso in millisecondi tra le scritture di batch di oggetti di trasmissione.</span><span class="sxs-lookup"><span data-stu-id="0753a-115">The average number of milliseconds between writes of transmission object batches.</span></span>|  
|<span data-ttu-id="0753a-116">**Get TO/sec**</span><span class="sxs-lookup"><span data-stu-id="0753a-116">**Tran Object Gets/sec**</span></span>|<span data-ttu-id="0753a-117">Quante volte le finestre di dialogo richiedono oggetti di trasmissione in un secondo.</span><span class="sxs-lookup"><span data-stu-id="0753a-117">The number of times per second that dialogs requested transmission objects.</span></span>|  
|<span data-ttu-id="0753a-118">**TO dirty/sec**</span><span class="sxs-lookup"><span data-stu-id="0753a-118">**Tran Objects Marked Dirty/sec**</span></span>|<span data-ttu-id="0753a-119">Quante volte gli oggetti di trasmissione sono stati contrassegnati come dirty in un secondo.</span><span class="sxs-lookup"><span data-stu-id="0753a-119">The number of times per second that transmission objects were marked as dirty.</span></span> <span data-ttu-id="0753a-120">Gli oggetti trasmissione sono contrassegnati come dirty dalla prima modifica che rende la copia in memoria diversa dalla copia archiviata in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0753a-120">Transmission objects are marked as dirty by the first modification that causes the in-memory copy to differ from the copy stored in **tempdb**.</span></span> <span data-ttu-id="0753a-121">Gli oggetti trasmissione vengono modificati quando [!INCLUDE[ssSB](../../includes/sssb-md.md)] deve registrare una modifica nello stato della trasmissione di messaggio per la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0753a-121">Transmission objects are modified when [!INCLUDE[ssSB](../../includes/sssb-md.md)] has to record a change in the state of message transmissions for the dialog.</span></span>|  
|<span data-ttu-id="0753a-122">**Scritture TO/sec**</span><span class="sxs-lookup"><span data-stu-id="0753a-122">**Tran Object Writes/sec**</span></span>|<span data-ttu-id="0753a-123">Il numero di volte al secondo in cui un batch di oggetti trasmissione viene scritto nelle tabelle di lavoro di **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="0753a-123">The number of times per second that a batch of transmission objects were written to **tempdb** work tables.</span></span> <span data-ttu-id="0753a-124">Un elevata quantità di scritture può indicare che quella memoria [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è sotto sforzo.</span><span class="sxs-lookup"><span data-stu-id="0753a-124">Large numbers of writes could indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory is being stressed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0753a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0753a-125">See Also</span></span>  
 <span data-ttu-id="0753a-126">[Oggetto Metodi di accesso di SQL Server](sql-server-access-methods-object.md) </span><span class="sxs-lookup"><span data-stu-id="0753a-126">[SQL Server, Access Methods Object](sql-server-access-methods-object.md) </span></span>  
 <span data-ttu-id="0753a-127">[Oggetto Memory Manager di SQL Server](sql-server-memory-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="0753a-127">[SQL Server, Memory Manager Object](sql-server-memory-manager-object.md) </span></span>  
 [<span data-ttu-id="0753a-128">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="0753a-128">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
