---
title: Processore fantasma XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 0f691b3d-a8fd-4459-ad21-2cfc8574a8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14158b7097427b6704cf5e747fa998a11217ecd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714248"
---
# <a name="xtp-phantom-processor"></a><span data-ttu-id="6feff-102">XTP Phantom Processor</span><span class="sxs-lookup"><span data-stu-id="6feff-102">XTP Phantom Processor</span></span>
  <span data-ttu-id="6feff-103">L'oggetto prestazione XTP Phantom Processor contiene contatori correlati al sottosistema di elaborazione fantasma del motore XTP.</span><span class="sxs-lookup"><span data-stu-id="6feff-103">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="6feff-104">Con questo componente è possibile rilevare le righe fantasma nelle transazioni in esecuzione a livello di isolamento SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="6feff-104">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>  
  
 <span data-ttu-id="6feff-105">Questa tabella descrive i contatori **XTP Phantom Processor** .</span><span class="sxs-lookup"><span data-stu-id="6feff-105">This table describes the **XTP Phantom Processor** counters.</span></span>  
  
|<span data-ttu-id="6feff-106">Contatore</span><span class="sxs-lookup"><span data-stu-id="6feff-106">Counter</span></span>|<span data-ttu-id="6feff-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6feff-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6feff-108">**Tentativi di analisi di elementi nascosti/sec (eseguiti dal processore fantasma)**</span><span class="sxs-lookup"><span data-stu-id="6feff-108">**Dusty corner scan retries/sec (Phantom-issued)**</span></span>|<span data-ttu-id="6feff-109">Numero medio di tentativi di analisi dovuti a conflitti di scrittura durante le operazioni su elementi nascosti eseguite dal processore fantasma, al secondo.</span><span class="sxs-lookup"><span data-stu-id="6feff-109">The number of scan retries due to write conflicts during dusty corner sweeps issued by the phantom processor (on average), per second.</span></span> <span data-ttu-id="6feff-110">Si tratta di un contatore di livello molto basso, non destinato all'uso da parte del cliente.</span><span class="sxs-lookup"><span data-stu-id="6feff-110">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="6feff-111">**Righe fantasma scadute rimosse/sec**</span><span class="sxs-lookup"><span data-stu-id="6feff-111">**Phantom expired rows removed/sec**</span></span>|<span data-ttu-id="6feff-112">Numero medio di righe scadute rimosse dalle analisi fantasma, al secondo.</span><span class="sxs-lookup"><span data-stu-id="6feff-112">The number of expired rows removed by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="6feff-113">**Righe fantasma scadute interessate/sec**</span><span class="sxs-lookup"><span data-stu-id="6feff-113">**Phantom expired rows touched/sec**</span></span>|<span data-ttu-id="6feff-114">Numero medio di righe scadute interessate dalle analisi fantasma, al secondo.</span><span class="sxs-lookup"><span data-stu-id="6feff-114">The number of expired rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="6feff-115">**Righe fantasma in scadenza interessate/sec**</span><span class="sxs-lookup"><span data-stu-id="6feff-115">**Phantom expiring rows touched/sec**</span></span>|<span data-ttu-id="6feff-116">Numero medio di righe in scadenza interessate dalle analisi fantasma, al secondo.</span><span class="sxs-lookup"><span data-stu-id="6feff-116">The number of expiring rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="6feff-117">**Righe fantasma interessate/sec**</span><span class="sxs-lookup"><span data-stu-id="6feff-117">**Phantom rows touched/sec**</span></span>|<span data-ttu-id="6feff-118">Numero medio di righe interessate dalle analisi fantasma, al secondo.</span><span class="sxs-lookup"><span data-stu-id="6feff-118">The number of rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="6feff-119">**Analisi fantasma avviate/sec**</span><span class="sxs-lookup"><span data-stu-id="6feff-119">**Phantom scans started/sec**</span></span>|<span data-ttu-id="6feff-120">Numero medio di analisi fantasma avviate, al secondo.</span><span class="sxs-lookup"><span data-stu-id="6feff-120">The number of phantom scans started (on average), per second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6feff-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6feff-121">See Also</span></span>  
 [<span data-ttu-id="6feff-122">XTP &#40;i contatori delle prestazioni di OLTP in memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="6feff-122">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
