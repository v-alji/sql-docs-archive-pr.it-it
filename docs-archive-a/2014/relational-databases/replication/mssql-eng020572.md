---
title: MSSQL_ENG020572 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020572 error
ms.assetid: 636566db-ffcf-4109-8c11-15b8c7cb9cd9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5762f160e119012f4fdc0ca1a205ba0ecf690378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637797"
---
# <a name="mssql_eng020572"></a><span data-ttu-id="3790f-102">MSSQL_ENG020572</span><span class="sxs-lookup"><span data-stu-id="3790f-102">MSSQL_ENG020572</span></span>
    
## <a name="message-details"></a><span data-ttu-id="3790f-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="3790f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3790f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3790f-104">Product Name</span></span>|<span data-ttu-id="3790f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3790f-105">SQL Server</span></span>|  
|<span data-ttu-id="3790f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="3790f-106">Event ID</span></span>|<span data-ttu-id="3790f-107">20572</span><span class="sxs-lookup"><span data-stu-id="3790f-107">20572</span></span>|  
|<span data-ttu-id="3790f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3790f-108">Event Source</span></span>|<span data-ttu-id="3790f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3790f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3790f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3790f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="3790f-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3790f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="3790f-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3790f-112">Message Text</span></span>|<span data-ttu-id="3790f-113">La sottoscrizione del Sottoscrittore '%s' dell'articolo '%s' della pubblicazione '%s' è stata reinizializzata dopo un errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="3790f-113">Subscriber '%s' subscription to article '%s' in publication '%s' has been reinitialized after a validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3790f-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="3790f-114">Explanation</span></span>  
 <span data-ttu-id="3790f-115">I dati nel Sottoscrittore sono stati convalidati in base a quelli nel server di pubblicazione e non corrispondono, pertanto la convalida non è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="3790f-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="3790f-116">Quando è stato specificato che è necessario eseguire la convalida, è stata selezionata l'opzione che prevede la reinizializzazione di una sottoscrizione in caso di mancata convalida.</span><span class="sxs-lookup"><span data-stu-id="3790f-116">When you specified that validation should be performed, you selected the option that a subscription should be reinitialized if validation failed.</span></span> <span data-ttu-id="3790f-117">La reinizializzazione di una sottoscrizione implica l'applicazione di un nuovo snapshot nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="3790f-117">Reinitializing a subscription involves applying a new snapshot at the Subscriber.</span></span> <span data-ttu-id="3790f-118">Per ulteriori informazioni sulla convalida, vedere [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="3790f-118">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3790f-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3790f-119">User Action</span></span>  
 <span data-ttu-id="3790f-120">I dati nel server di pubblicazione e nel Sottoscrittore corrisponderanno dopo l'applicazione del nuovo snapshot nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="3790f-120">Data at the Publisher and Subscriber will match after the new snapshot is applied at the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3790f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3790f-121">See Also</span></span>  
 [<span data-ttu-id="3790f-122">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="3790f-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
