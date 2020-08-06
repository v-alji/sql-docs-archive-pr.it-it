---
title: MSSQL_ENG020574 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG02574 error
ms.assetid: 4e98f8de-287c-4090-81ee-dc8f80dfa6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e224e9a87d40fa826a05c669216649c45185037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637796"
---
# <a name="mssql_eng020574"></a><span data-ttu-id="e05f5-102">MSSQL_ENG020574</span><span class="sxs-lookup"><span data-stu-id="e05f5-102">MSSQL_ENG020574</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e05f5-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="e05f5-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e05f5-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e05f5-104">Product Name</span></span>|<span data-ttu-id="e05f5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e05f5-105">SQL Server</span></span>|  
|<span data-ttu-id="e05f5-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e05f5-106">Event ID</span></span>|<span data-ttu-id="e05f5-107">20574</span><span class="sxs-lookup"><span data-stu-id="e05f5-107">20574</span></span>|  
|<span data-ttu-id="e05f5-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e05f5-108">Event Source</span></span>|<span data-ttu-id="e05f5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e05f5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e05f5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e05f5-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e05f5-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e05f5-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e05f5-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e05f5-112">Message Text</span></span>|<span data-ttu-id="e05f5-113">La sottoscrizione del Sottoscrittore '%s' dell'articolo '%s' della pubblicazione '%s' non ha superato la convalida dei dati.</span><span class="sxs-lookup"><span data-stu-id="e05f5-113">Subscriber '%s' subscription to article '%s' in publication '%s' failed data validation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e05f5-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e05f5-114">Explanation</span></span>  
 <span data-ttu-id="e05f5-115">I dati nel Sottoscrittore sono stati convalidati in base a quelli nel server di pubblicazione e non corrispondono, pertanto la convalida non è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="e05f5-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="e05f5-116">Per ulteriori informazioni sulla convalida, vedere [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="e05f5-116">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e05f5-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e05f5-117">User Action</span></span>  
 <span data-ttu-id="e05f5-118">È consigliabile eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="e05f5-118">We recommend that you do the following:</span></span>  
  
-   <span data-ttu-id="e05f5-119">Stabilire i motivi per i quali la convalida non è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="e05f5-119">Determine why validation failed.</span></span>  
  
-   <span data-ttu-id="e05f5-120">Risolvere il problema sottostante che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="e05f5-120">Correct the underlying issue that caused the failure.</span></span>  
  
-   <span data-ttu-id="e05f5-121">Ripristinare la convergenza dei dati reinizializzando la sottoscrizione oppure utilizzando un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="e05f5-121">Bring the data into convergence by reinitializing the subscription or through another method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e05f5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e05f5-122">See Also</span></span>  
 [<span data-ttu-id="e05f5-123">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="e05f5-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
