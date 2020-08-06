---
title: Archiviazione XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 4070580b-880d-4f4c-abcc-626a4fe0c9a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: efd4a9eba36060d3d4bab9b371678ab2b2c409ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629378"
---
# <a name="xtp-storage"></a><span data-ttu-id="90262-102">Archiviazione XTP</span><span class="sxs-lookup"><span data-stu-id="90262-102">XTP Storage</span></span>
  <span data-ttu-id="90262-103">Nell'oggetto prestazione dell'archiviazione XTP sono inclusi i contatori correlati all'archiviazione XTP di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90262-103">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="90262-104">Questa tabella descrive i contatori di **archiviazione XTP** .</span><span class="sxs-lookup"><span data-stu-id="90262-104">This table describes the **XTP Storage** counters.</span></span>  
  
|<span data-ttu-id="90262-105">Contatore</span><span class="sxs-lookup"><span data-stu-id="90262-105">Counter</span></span>|<span data-ttu-id="90262-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90262-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90262-107">**Checkpoint chiusi**</span><span class="sxs-lookup"><span data-stu-id="90262-107">**Checkpoints Closed**</span></span>|<span data-ttu-id="90262-108">Conteggio di checkpoint chiusi eseguiti dall'agente online.</span><span class="sxs-lookup"><span data-stu-id="90262-108">Count of checkpoints closed done by online agent.</span></span>|  
|<span data-ttu-id="90262-109">**Checkpoint completati**</span><span class="sxs-lookup"><span data-stu-id="90262-109">**Checkpoints Completed**</span></span>|<span data-ttu-id="90262-110">Conteggio di checkpoint elaborati dal thread offline dei checkpoint.</span><span class="sxs-lookup"><span data-stu-id="90262-110">Count of checkpoints processed by offline checkpoint thread.</span></span>|  
|<span data-ttu-id="90262-111">**Operazioni di unioni principali completate**</span><span class="sxs-lookup"><span data-stu-id="90262-111">**Core Merges Completed**</span></span>|<span data-ttu-id="90262-112">Numero di operazioni di unioni principali completate dal thread di lavoro di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="90262-112">The number of core merges completed by the merge worker thread.</span></span> <span data-ttu-id="90262-113">Queste operazioni devono ancora essere installate.</span><span class="sxs-lookup"><span data-stu-id="90262-113">These merges still need to be installed.</span></span>|  
|<span data-ttu-id="90262-114">**Valutazioni dei criteri di unione**</span><span class="sxs-lookup"><span data-stu-id="90262-114">**Merge Policy Evaluations**</span></span>|<span data-ttu-id="90262-115">Numero di valutazioni dei criteri di unione dall'avvio del server.</span><span class="sxs-lookup"><span data-stu-id="90262-115">The number of merge policy evaluations since the server started.</span></span>|  
|<span data-ttu-id="90262-116">**Richieste di tipo merge in sospeso**</span><span class="sxs-lookup"><span data-stu-id="90262-116">**Merge Requests Outstanding**</span></span>|<span data-ttu-id="90262-117">Numero di richieste di tipo merge in sospeso dall'avvio del server.</span><span class="sxs-lookup"><span data-stu-id="90262-117">The number of merge requests outstanding since the server started.</span></span>|  
|<span data-ttu-id="90262-118">**Operazioni di unione abbandonate**</span><span class="sxs-lookup"><span data-stu-id="90262-118">**Merges Abandoned**</span></span>|<span data-ttu-id="90262-119">Numero di operazioni di unione abbandonate a causa di un errore.</span><span class="sxs-lookup"><span data-stu-id="90262-119">The number of merges abandoned due to failure.</span></span>|  
|<span data-ttu-id="90262-120">**Operazioni di unione installate**</span><span class="sxs-lookup"><span data-stu-id="90262-120">**Merges Installed**</span></span>|<span data-ttu-id="90262-121">Numero di operazioni di unione installate correttamente.</span><span class="sxs-lookup"><span data-stu-id="90262-121">The number of merges successfully installed.</span></span>|  
|<span data-ttu-id="90262-122">**File totali uniti**</span><span class="sxs-lookup"><span data-stu-id="90262-122">**Total Files Merged**</span></span>|<span data-ttu-id="90262-123">Numero totale di file di origine uniti.</span><span class="sxs-lookup"><span data-stu-id="90262-123">The total number of source files merged.</span></span> <span data-ttu-id="90262-124">Questo numero può essere utilizzato per trovare il numero medio di file di origine nell'unione.</span><span class="sxs-lookup"><span data-stu-id="90262-124">This count can be used to find the average number of source files in the merge.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90262-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90262-125">See Also</span></span>  
 [<span data-ttu-id="90262-126">XTP &#40;i contatori delle prestazioni di OLTP in memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="90262-126">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
