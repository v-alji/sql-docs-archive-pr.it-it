---
title: Confronto tra normali e connessioni di contesto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: a1dead02-be88-4b16-8cb2-db1284856764
author: rothja
ms.author: jroth
ms.openlocfilehash: ce531129099a8f4908bdc4b29920696d4ba3c505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637914"
---
# <a name="regular-vs-context-connections"></a><span data-ttu-id="4b47e-102">Connessione normale e Connessione di contesto:</span><span class="sxs-lookup"><span data-stu-id="4b47e-102">Regular vs. Context Connections</span></span>
  <span data-ttu-id="4b47e-103">Se si esegue una connessione a un server remoto, utilizzare sempre connessioni normali anziché connessioni di contesto.</span><span class="sxs-lookup"><span data-stu-id="4b47e-103">If you are connecting to a remote server, always use regular connections rather than context connections.</span></span> <span data-ttu-id="4b47e-104">Se è necessario connettersi allo stesso server in cui è in esecuzione la stored procedure o la funzione, utilizzare la connessione di contesto nella maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="4b47e-104">If you need to connect to the same server on which the stored procedure or function is running, use the context connection in most cases.</span></span> <span data-ttu-id="4b47e-105">Questa connessione offre vantaggi quali l'esecuzione nello stesso spazio della transazione e la non necessità di eseguire una nuova autenticazione.</span><span class="sxs-lookup"><span data-stu-id="4b47e-105">This has benefits such as running in the same transaction space and not having to reauthenticate.</span></span>  
  
 <span data-ttu-id="4b47e-106">L'utilizzo della connessione di contesto, inoltre, consente in genere prestazioni migliori e un minore utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="4b47e-106">Additionally, using the context connection typically results in better performance and less resource usage.</span></span> <span data-ttu-id="4b47e-107">La connessione del contesto è una connessione solo in-process, quindi è in grado di contattare il server "direttamente" ignorando il protocollo di rete e i livelli di trasporto per inviare istruzioni Transact-SQL e ricevere risultati.</span><span class="sxs-lookup"><span data-stu-id="4b47e-107">The context connection is an in-process-only connection, so it can contact the server "directly" by bypassing the network protocol and transport layers to send Transact-SQL statements and receive results.</span></span> <span data-ttu-id="4b47e-108">Viene ignorato anche il processo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="4b47e-108">The authentication process is bypassed, as well.</span></span> <span data-ttu-id="4b47e-109">Nella figura seguente vengono illustrati i componenti principali del provider gestito `SqlClient`, nonché l'interazione reciproca dei diversi componenti quando si utilizza una connessione normale e quando si utilizza una connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="4b47e-109">The following figure shows the primary components of the `SqlClient` managed provider, as well as how the different components interact with each other when using a regular connection, and when using the context connection.</span></span>  
  
 <span data-ttu-id="4b47e-110">![Percorsi del codice di una connessione del contesto e una connessione regolare](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Percorsi del codice di una connessione del contesto e una connessione regolare")</span><span class="sxs-lookup"><span data-stu-id="4b47e-110">![Code paths of a context and a regular connnection.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Code paths of a context and a regular connnection.")</span></span>  
  
 <span data-ttu-id="4b47e-111">Poiché la connessione di contesto segue un percorso di codice più corto e interessa un numero minore di componenti, è probabile che le richieste e i risultati vengano trasmessi al e dal server più rapidamente che in una connessione normale.</span><span class="sxs-lookup"><span data-stu-id="4b47e-111">The context connection follows a shorter code path and involves fewer components, so you can expect requests and results to get to and from the server faster than in a regular connection.</span></span> <span data-ttu-id="4b47e-112">I tempi di esecuzione delle query nel server sono uguali per le connessioni normali e di contesto.</span><span class="sxs-lookup"><span data-stu-id="4b47e-112">Query execution time on the server is the same for context and regular connections.</span></span>  
  
 <span data-ttu-id="4b47e-113">In alcuni casi, potrebbe essere necessario aprire una connessione normale separata allo stesso server.</span><span class="sxs-lookup"><span data-stu-id="4b47e-113">There are some cases in which you may need to open a separate regular connection to the same server.</span></span> <span data-ttu-id="4b47e-114">Esistono, ad esempio, alcune restrizioni sull'utilizzo della connessione di contesto, descritte in [restrizioni sulle connessioni normali e di contesto](context-connections-and-regular-connections-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="4b47e-114">For example, there are certain restrictions on using the context connection, described in [Restrictions on Regular and Context Connections](context-connections-and-regular-connections-restrictions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b47e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b47e-115">See Also</span></span>  
 [<span data-ttu-id="4b47e-116">Connessione di contesto</span><span class="sxs-lookup"><span data-stu-id="4b47e-116">Context Connection</span></span>](context-connection.md)  
  
  
