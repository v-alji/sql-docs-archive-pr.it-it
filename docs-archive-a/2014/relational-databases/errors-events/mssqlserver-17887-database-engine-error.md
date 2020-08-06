---
title: MSSQLSERVER_17887 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17887 (Database Engine error)
ms.assetid: ad0806e6-3296-4c32-b103-fccf0f8a8d3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 006e616d80ef7e8d083f60675b02b4e6a4e8dc24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624242"
---
# <a name="mssqlserver_17887"></a><span data-ttu-id="bc97f-102">MSSQLSERVER_17887</span><span class="sxs-lookup"><span data-stu-id="bc97f-102">MSSQLSERVER_17887</span></span>
    
## <a name="details"></a><span data-ttu-id="bc97f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bc97f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc97f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="bc97f-104">Product Name</span></span>|<span data-ttu-id="bc97f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc97f-105">SQL Server</span></span>|  
|<span data-ttu-id="bc97f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="bc97f-106">Event ID</span></span>|<span data-ttu-id="bc97f-107">17887</span><span class="sxs-lookup"><span data-stu-id="bc97f-107">17887</span></span>|  
|<span data-ttu-id="bc97f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="bc97f-108">Event Source</span></span>|<span data-ttu-id="bc97f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bc97f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bc97f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bc97f-110">Component</span></span>|<span data-ttu-id="bc97f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bc97f-111">SQLEngine</span></span>|  
|<span data-ttu-id="bc97f-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="bc97f-112">Symbolic Name</span></span>|<span data-ttu-id="bc97f-113">SRV_IO_COMP_LISTENER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="bc97f-113">SRV_IO_COMP_LISTENER_NONYIELDING</span></span>|  
|<span data-ttu-id="bc97f-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="bc97f-114">Message Text</span></span>|<span data-ttu-id="bc97f-115">Listener completamento I/O (0x%lx) È possibile che il thread di lavoro 0x%p non ceda la precedenza del nodo %ld.</span><span class="sxs-lookup"><span data-stu-id="bc97f-115">IO Completion Listener (0x%lx) Worker 0x%p appears to be non-yielding on Node %ld.</span></span> <span data-ttu-id="bc97f-116">Utilizzo CPU (circa): kernel %I64d ms, utente %I64d ms, intervallo: %I64d.</span><span class="sxs-lookup"><span data-stu-id="bc97f-116">Approx CPU Used: kernel %I64d ms, user %I64d ms, Interval: %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bc97f-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bc97f-117">Explanation</span></span>  
 <span data-ttu-id="bc97f-118">Indica l'esistenza di un possibile problema con il Listener porta completamento I/O sul nodo specificato durante l'esecuzione della routine Completamento I/O per un evento di lettura/scrittura di rete.</span><span class="sxs-lookup"><span data-stu-id="bc97f-118">Indicates that there is a possible problem with the I/O Completion Port Listener on the specified node when executing the I/O Completion routine for a network read/write event.</span></span> <span data-ttu-id="bc97f-119">Questo errore non viene più visualizzato quando viene restituito il Listener della porta di completamento I/O in seguito all'esecuzione della routine Completamento I/O.</span><span class="sxs-lookup"><span data-stu-id="bc97f-119">This error will go away when the I/O Completion Port Listener returns from executing the I/O Completion routine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bc97f-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="bc97f-120">User Action</span></span>  
 <span data-ttu-id="bc97f-121">Contattare il Servizio Supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc97f-121">Contact Microsoft Customer Support Services (CSS).</span></span>  
  
  
