---
title: MSSQLSERVER_17883 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17883 (Database Engine error)
ms.assetid: adaf1c04-e397-4a69-90b8-9353a37277ea
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46488fb6f7adac2c1109871f2aad4c79352829ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713203"
---
# <a name="mssqlserver_17883"></a><span data-ttu-id="664ae-102">MSSQLSERVER_17883</span><span class="sxs-lookup"><span data-stu-id="664ae-102">MSSQLSERVER_17883</span></span>
    
## <a name="details"></a><span data-ttu-id="664ae-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="664ae-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="664ae-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="664ae-104">Product Name</span></span>|<span data-ttu-id="664ae-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="664ae-105">SQL Server</span></span>|  
|<span data-ttu-id="664ae-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="664ae-106">Event ID</span></span>|<span data-ttu-id="664ae-107">17883</span><span class="sxs-lookup"><span data-stu-id="664ae-107">17883</span></span>|  
|<span data-ttu-id="664ae-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="664ae-108">Event Source</span></span>|<span data-ttu-id="664ae-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="664ae-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="664ae-110">Componente</span><span class="sxs-lookup"><span data-stu-id="664ae-110">Component</span></span>|<span data-ttu-id="664ae-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="664ae-111">SQLEngine</span></span>|  
|<span data-ttu-id="664ae-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="664ae-112">Symbolic Name</span></span>|<span data-ttu-id="664ae-113">SRV_SCHEDULER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="664ae-113">SRV_SCHEDULER_NONYIELDING</span></span>|  
|<span data-ttu-id="664ae-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="664ae-114">Message Text</span></span>|<span data-ttu-id="664ae-115">Processo %ld:%ld:%ld (0x%lx) È possibile che il thread di lavoro 0x%p non ceda il controllo all'utilità di pianificazione %ld.</span><span class="sxs-lookup"><span data-stu-id="664ae-115">Process %ld:%ld:%ld (0x%lx) Worker 0x%p appears to be non-yielding on Scheduler %ld.</span></span> <span data-ttu-id="664ae-116">Durata creazione thread: %I64d.</span><span class="sxs-lookup"><span data-stu-id="664ae-116">Thread creation time: %I64d.</span></span> <span data-ttu-id="664ae-117">Utilizzo CPU thread (circa): kernel %I64d ms, utente %I64d ms.</span><span class="sxs-lookup"><span data-stu-id="664ae-117">Approx Thread CPU Used: kernel %I64d ms, user %I64d ms.</span></span> <span data-ttu-id="664ae-118">Utilizzo processo %d%%.</span><span class="sxs-lookup"><span data-stu-id="664ae-118">Process Utilization %d%%.</span></span> <span data-ttu-id="664ae-119">Inattività del sistema: %d%%.</span><span class="sxs-lookup"><span data-stu-id="664ae-119">System Idle %d%%.</span></span> <span data-ttu-id="664ae-120">Intervallo: %I64d ms.</span><span class="sxs-lookup"><span data-stu-id="664ae-120">Interval: %I64d ms.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="664ae-121">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="664ae-121">Explanation</span></span>  
 <span data-ttu-id="664ae-122">Indica la presenza di un possibile problema relativo a un thread che non cede il controllo a un'utilità di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="664ae-122">Indicates that there is a possible problem with a thread not yielding on a scheduler.</span></span>  <span data-ttu-id="664ae-123">Il problema potrebbe essere causato da un bug in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o da un numero di cicli insufficienti per l'esecuzione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="664ae-123">This could be caused by a bug in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not getting enough cycles to execute.</span></span>  <span data-ttu-id="664ae-124">L'errore potrebbe risolversi qualora il thread ceda eventualmente il controllo.</span><span class="sxs-lookup"><span data-stu-id="664ae-124">This error could go away if the thread eventually yields.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="664ae-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="664ae-125">User Action</span></span>  
 <span data-ttu-id="664ae-126">Se il carico sul sistema è eccessivo, ridurlo. In caso contrario, contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="664ae-126">If excessive load on system reduce load otherwise contact Microsoft Customer Support Services.</span></span>  
  
  
