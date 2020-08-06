---
title: Contatori delle prestazioni XTP (OLTP in memoria) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: fe3cbaf4-65f4-44c5-acc6-7b735cda0c5d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4363a526ada3694e92d18cac0d7abe8a26f6a92f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714251"
---
# <a name="xtp-in-memory-oltp-performance-counters"></a><span data-ttu-id="cf022-102">Contatori delle prestazioni XTP (OLTP in memoria)</span><span class="sxs-lookup"><span data-stu-id="cf022-102">XTP (In-Memory OLTP) Performance Counters</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cf022-103">fornisce oggetti e contatori utilizzabili da Performance Monitor per il monitoraggio dell'attività OLTP in memoria.</span><span class="sxs-lookup"><span data-stu-id="cf022-103">provides objects and counters that can be used by Performance Monitor to monitor In-Memory OLTP activity.</span></span>  
  
##  <a name="xtp-in-memory-oltp-performance-objects"></a><a name="SQLServerPOs"></a><span data-ttu-id="cf022-104">Oggetti prestazioni XTP (OLTP in memoria)</span><span class="sxs-lookup"><span data-stu-id="cf022-104">XTP (In-Memory OLTP) Performance Objects</span></span>  
 <span data-ttu-id="cf022-105">Nella seguente tabella vengono descritti gli oggetti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf022-105">The following table describes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span>  
  
|<span data-ttu-id="cf022-106">Oggetto prestazione</span><span class="sxs-lookup"><span data-stu-id="cf022-106">Performance object</span></span>|<span data-ttu-id="cf022-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf022-107">Description</span></span>|  
|------------------------|-----------------|  
|[<span data-ttu-id="cf022-108">XTP Cursors</span><span class="sxs-lookup"><span data-stu-id="cf022-108">XTP Cursors</span></span>](../cursors.md)|<span data-ttu-id="cf022-109">L'oggetto prestazione XTP Cursors contiene contatori correlati ai cursori interni del motore XTP.</span><span class="sxs-lookup"><span data-stu-id="cf022-109">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="cf022-110">I cursori sono i blocchi predefiniti di basso livello utilizzati dal motore XTP per elaborare query [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf022-110">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="cf022-111">Di conseguenza, in genere non si ha controllo diretto su di essi.</span><span class="sxs-lookup"><span data-stu-id="cf022-111">As such, you do not typically have direct control over them.</span></span>|  
|[<span data-ttu-id="cf022-112">XTP Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="cf022-112">XTP Garbage Collection</span></span>](sql-server-xtp-garbage-collection.md)|<span data-ttu-id="cf022-113">L'oggetto prestazione XTP Garbage Collection contiene contatori correlati al Garbage Collector del motore XTP.</span><span class="sxs-lookup"><span data-stu-id="cf022-113">The XTP Garbage Collection performance object contains counters related to the XTP engine's garbage collector.</span></span>|  
|[<span data-ttu-id="cf022-114">XTP Phantom Processor</span><span class="sxs-lookup"><span data-stu-id="cf022-114">XTP Phantom Processor</span></span>](sql-server-xtp-phantom-processor.md)|<span data-ttu-id="cf022-115">L'oggetto prestazione XTP Phantom Processor contiene contatori correlati al sottosistema di elaborazione fantasma del motore XTP.</span><span class="sxs-lookup"><span data-stu-id="cf022-115">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="cf022-116">Con questo componente è possibile rilevare le righe fantasma nelle transazioni in esecuzione a livello di isolamento SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="cf022-116">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>|  
|[<span data-ttu-id="cf022-117">Archiviazione XTP</span><span class="sxs-lookup"><span data-stu-id="cf022-117">XTP Storage</span></span>](sql-server-xtp-storage.md)|<span data-ttu-id="cf022-118">Nell'oggetto prestazione dell'archiviazione XTP sono inclusi i contatori correlati all'archiviazione XTP di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf022-118">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="cf022-119">XTP Transaction Log</span><span class="sxs-lookup"><span data-stu-id="cf022-119">XTP Transaction Log</span></span>](sql-server-xtp-transaction-log.md)|<span data-ttu-id="cf022-120">L'oggetto prestazione XTP Transaction Log contiene contatori correlati alla registrazione delle transazioni XTP in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf022-120">The XTP Transaction Log performance object contains counters related to XTP transaction logging in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="cf022-121">XTP Transactions</span><span class="sxs-lookup"><span data-stu-id="cf022-121">XTP Transactions</span></span>](sql-server-xtp-transactions.md)|<span data-ttu-id="cf022-122">L'oggetto prestazione XTP Transactions contiene contatori correlati alle transazioni del motore XTP in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf022-122">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
  
