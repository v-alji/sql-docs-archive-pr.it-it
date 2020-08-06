---
title: MSSQLSERVER_844 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 844 (Database Engine error)
ms.assetid: 2060c886-1226-4066-bc0c-de90a1cfb82b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4870d6e43ec12b49033ea3b5f88fa0d0cdd597a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627278"
---
# <a name="mssqlserver_844"></a><span data-ttu-id="53d57-102">MSSQLSERVER_844</span><span class="sxs-lookup"><span data-stu-id="53d57-102">MSSQLSERVER_844</span></span>
    
## <a name="details"></a><span data-ttu-id="53d57-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="53d57-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53d57-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="53d57-104">Product Name</span></span>|<span data-ttu-id="53d57-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="53d57-105">SQL Server</span></span>|  
|<span data-ttu-id="53d57-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="53d57-106">Event ID</span></span>|<span data-ttu-id="53d57-107">844</span><span class="sxs-lookup"><span data-stu-id="53d57-107">844</span></span>|  
|<span data-ttu-id="53d57-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="53d57-108">Event Source</span></span>|<span data-ttu-id="53d57-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="53d57-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="53d57-110">Componente</span><span class="sxs-lookup"><span data-stu-id="53d57-110">Component</span></span>|<span data-ttu-id="53d57-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="53d57-111">SQLEngine</span></span>|  
|<span data-ttu-id="53d57-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="53d57-112">Symbolic Name</span></span>|<span data-ttu-id="53d57-113">BUFLATCH_TIMEOUT_CONTINUE</span><span class="sxs-lookup"><span data-stu-id="53d57-113">BUFLATCH_TIMEOUT_CONTINUE</span></span>|  
|<span data-ttu-id="53d57-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="53d57-114">Message Text</span></span>|<span data-ttu-id="53d57-115">Timeout durante l'attesa del latch del buffer: tipo %d, bp %p, pagina %d:%d, stat %#x, ID database: %d, ID unità di allocazione:%I64d%ls, attività 0x%p: %d, attesa %d, flag 0x%I64x, attività proprietaria 0x%p.</span><span class="sxs-lookup"><span data-stu-id="53d57-115">Time-out occurred while waiting for buffer latch -- type %d, bp %p, page %d:%d, stat %#x, database id: %d, allocation unit id: %I64d%ls, task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span>  <span data-ttu-id="53d57-116">L'attesa verrà protratta.</span><span class="sxs-lookup"><span data-stu-id="53d57-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53d57-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="53d57-117">Explanation</span></span>  
 <span data-ttu-id="53d57-118">Un processo è in attesa di acquisire un latch.</span><span class="sxs-lookup"><span data-stu-id="53d57-118">A process is waiting to acquire a latch.</span></span> <span data-ttu-id="53d57-119">Il problema può essere causato da un'operazione di I/O il cui completamento richiede troppo tempo.</span><span class="sxs-lookup"><span data-stu-id="53d57-119">This problem can be caused by an I/O operation taking too long to complete.</span></span> <span data-ttu-id="53d57-120">Questo tipo di errore in genere è dovuto ad altre attività che bloccano i processi di sistema.</span><span class="sxs-lookup"><span data-stu-id="53d57-120">Typically this type of error is the result of other tasks blocking system processes.</span></span> <span data-ttu-id="53d57-121">In alcuni casi, tuttavia, può essere dovuto a un errore hardware.</span><span class="sxs-lookup"><span data-stu-id="53d57-121">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53d57-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="53d57-122">User Action</span></span>  
 <span data-ttu-id="53d57-123">Per evitare che si verifichi questo errore, provare le soluzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="53d57-123">Try the following to prevent this error from occurring:</span></span>  
  
-   <span data-ttu-id="53d57-124">Ridurre il carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="53d57-124">Reduce workload.</span></span>  
  
-   <span data-ttu-id="53d57-125">Verificare la presenza di errori di I/O associati nel log degli errori o nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="53d57-125">Check for associated I/O failures in error log or event log.</span></span> <span data-ttu-id="53d57-126">Gli errori di I/O in genere sono dovuti a un malfunzionamento del disco.</span><span class="sxs-lookup"><span data-stu-id="53d57-126">I/O failures typically point to a disk malfunction.</span></span>  
  
-   <span data-ttu-id="53d57-127">Controllare nel log degli errori la presenza di attività che non cedono la precedenza e di altri errori critici.</span><span class="sxs-lookup"><span data-stu-id="53d57-127">Check the error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="53d57-128">Se si verificano spesso errori critici, ad esempio di asserzione, risolvere tali problemi.</span><span class="sxs-lookup"><span data-stu-id="53d57-128">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="53d57-129">Se l'errore persiste, contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53d57-129">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
