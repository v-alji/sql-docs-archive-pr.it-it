---
title: MSSQLSERVER_1222 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1222 (Database Engine error)
ms.assetid: c5b1c2f4-f591-4cc1-aa17-204636a27f29
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ac3fe9314386836633a11f17d6775c75019de93a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623316"
---
# <a name="mssqlserver_1222"></a><span data-ttu-id="aa784-102">MSSQLSERVER_1222</span><span class="sxs-lookup"><span data-stu-id="aa784-102">MSSQLSERVER_1222</span></span>
    
## <a name="details"></a><span data-ttu-id="aa784-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="aa784-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa784-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="aa784-104">Product Name</span></span>|<span data-ttu-id="aa784-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa784-105">SQL Server</span></span>|  
|<span data-ttu-id="aa784-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="aa784-106">Event ID</span></span>|<span data-ttu-id="aa784-107">1222</span><span class="sxs-lookup"><span data-stu-id="aa784-107">1222</span></span>|  
|<span data-ttu-id="aa784-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="aa784-108">Event Source</span></span>|<span data-ttu-id="aa784-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aa784-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aa784-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aa784-110">Component</span></span>|<span data-ttu-id="aa784-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aa784-111">SQLEngine</span></span>|  
|<span data-ttu-id="aa784-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="aa784-112">Symbolic Name</span></span>|<span data-ttu-id="aa784-113">LK_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aa784-113">LK_TIMEOUT</span></span>|  
|<span data-ttu-id="aa784-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="aa784-114">Message Text</span></span>|<span data-ttu-id="aa784-115">Timeout della richiesta di blocco.</span><span class="sxs-lookup"><span data-stu-id="aa784-115">Lock request time out period exceeded.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa784-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="aa784-116">Explanation</span></span>  
 <span data-ttu-id="aa784-117">Una risorsa necessaria viene mantenuta in blocco da un'altra transazione per un periodo superiore al tempo di attesa ammesso dalla query.</span><span class="sxs-lookup"><span data-stu-id="aa784-117">Another transaction held a lock on a required resource longer than this query could wait for it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa784-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="aa784-118">User Action</span></span>  
 <span data-ttu-id="aa784-119">Per risolvere il problema, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa784-119">Perform the following tasks to alleviate the problem:</span></span>  
  
1.  <span data-ttu-id="aa784-120">Se possibile, individuare la transazione che blocca la risorsa necessaria.</span><span class="sxs-lookup"><span data-stu-id="aa784-120">Locate the transaction that is holding the lock on the required resource, if possible.</span></span> <span data-ttu-id="aa784-121">Usare le viste a gestione dinamica **sys.dm_os_waiting_tasks** e **sys.dm_tran_locks**.</span><span class="sxs-lookup"><span data-stu-id="aa784-121">Use **sys.dm_os_waiting_tasks** and **sys.dm_tran_locks** dynamic management views.</span></span>  
  
2.  <span data-ttu-id="aa784-122">Se la transazione continua a mantenere il blocco, terminarla se appropriato.</span><span class="sxs-lookup"><span data-stu-id="aa784-122">If the transaction is still holding the lock, terminate that transaction if appropriate.</span></span>  
  
3.  <span data-ttu-id="aa784-123">Eseguire nuovamente la query.</span><span class="sxs-lookup"><span data-stu-id="aa784-123">Execute the query again.</span></span>  
  
 <span data-ttu-id="aa784-124">Se l'errore si verifica spesso, modificare il periodo di timeout del blocco oppure le transazioni all'origine del problema in modo che mantengano il blocco per un periodo di tempo inferiore.</span><span class="sxs-lookup"><span data-stu-id="aa784-124">If this error occurs frequently change the lock time-out period or modify the offending transactions so that they hold the lock for less time.</span></span>  
  
  
