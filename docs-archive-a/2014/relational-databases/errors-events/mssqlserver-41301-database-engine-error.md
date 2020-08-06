---
title: MSSQLSERVER_41301 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41301 (Database Engine error)
ms.assetid: c6127e1e-2846-4ee9-bc42-2d896ea9730e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d4fa78b334f32033f96df002aeaf039994b396cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629853"
---
# <a name="mssqlserver_41301"></a><span data-ttu-id="0df30-102">MSSQLSERVER_41301</span><span class="sxs-lookup"><span data-stu-id="0df30-102">MSSQLSERVER_41301</span></span>
    
## <a name="details"></a><span data-ttu-id="0df30-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0df30-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0df30-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0df30-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0df30-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="0df30-105">Event ID</span></span>|<span data-ttu-id="0df30-106">41301</span><span class="sxs-lookup"><span data-stu-id="0df30-106">41301</span></span>|  
|<span data-ttu-id="0df30-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0df30-107">Event Source</span></span>|<span data-ttu-id="0df30-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0df30-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0df30-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0df30-109">Component</span></span>|<span data-ttu-id="0df30-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0df30-110">SQLEngine</span></span>|  
|<span data-ttu-id="0df30-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0df30-111">Symbolic Name</span></span>|<span data-ttu-id="0df30-112">COMMIT_DEPENDENCY_FAILURE</span><span class="sxs-lookup"><span data-stu-id="0df30-112">COMMIT_DEPENDENCY_FAILURE</span></span>|  
|<span data-ttu-id="0df30-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0df30-113">Message Text</span></span>|<span data-ttu-id="0df30-114">Una transazione precedente da cui dipende la transazione corrente è stata interrotta. Impossibile eseguire il commit della transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="0df30-114">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0df30-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0df30-115">Explanation</span></span>  
 <span data-ttu-id="0df30-116">La transazione ha rilevato un errore di dipendenza ed è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="0df30-116">The transaction encountered a dependency failure, and is now doomed.</span></span>  
  
 <span data-ttu-id="0df30-117">Questo errore può essere causato anche da troppe transazioni dipendenti.</span><span class="sxs-lookup"><span data-stu-id="0df30-117">This error can also be caused by too many dependent transactions.</span></span> <span data-ttu-id="0df30-118">Qualsiasi transazione di scrittura può presentare un numero limitato di transazioni dipendenti.</span><span class="sxs-lookup"><span data-stu-id="0df30-118">Any write transaction can have a limited number of dependent transactions.</span></span> <span data-ttu-id="0df30-119">Ad esempio, questo errore si può verificare se tramite troppe transazioni di lettura si tenta di accettare una dipendenza dalla transazione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0df30-119">For example, this error can occur if too many read transactions try to take a dependency on the update transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0df30-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0df30-120">User Action</span></span>  
 <span data-ttu-id="0df30-121">Non eseguire operazioni sulla transazione.</span><span class="sxs-lookup"><span data-stu-id="0df30-121">Don't do any work on the transaction.</span></span> <span data-ttu-id="0df30-122">Chiamare ROLLBACK TRAN per eseguire il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="0df30-122">Call ROLLBACK TRAN to roll back the transaction.</span></span> <span data-ttu-id="0df30-123">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="0df30-123">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df30-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0df30-124">See Also</span></span>  
 [<span data-ttu-id="0df30-125">Abilitare e disabilitare la funzionalità Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0df30-125">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md)  
  
  
