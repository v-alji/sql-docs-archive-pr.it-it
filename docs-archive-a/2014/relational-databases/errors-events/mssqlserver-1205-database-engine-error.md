---
title: MSSQLSERVER_1205 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1205 (Database Engine error)
ms.assetid: 9fe3f67c-df3c-4642-a3a4-ccc0e138b632
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6afa81a05eea37bc67cd2e9ac2433b6c82f35b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623317"
---
# <a name="mssqlserver_1205"></a><span data-ttu-id="321de-102">MSSQLSERVER_1205</span><span class="sxs-lookup"><span data-stu-id="321de-102">MSSQLSERVER_1205</span></span>
    
## <a name="details"></a><span data-ttu-id="321de-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="321de-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="321de-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="321de-104">Product Name</span></span>|<span data-ttu-id="321de-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="321de-105">SQL Server</span></span>|  
|<span data-ttu-id="321de-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="321de-106">Event ID</span></span>|<span data-ttu-id="321de-107">1205</span><span class="sxs-lookup"><span data-stu-id="321de-107">1205</span></span>|  
|<span data-ttu-id="321de-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="321de-108">Event Source</span></span>|<span data-ttu-id="321de-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="321de-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="321de-110">Componente</span><span class="sxs-lookup"><span data-stu-id="321de-110">Component</span></span>|<span data-ttu-id="321de-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="321de-111">SQLEngine</span></span>|  
|<span data-ttu-id="321de-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="321de-112">Symbolic Name</span></span>|<span data-ttu-id="321de-113">LK_VICTIM</span><span class="sxs-lookup"><span data-stu-id="321de-113">LK_VICTIM</span></span>|  
|<span data-ttu-id="321de-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="321de-114">Message Text</span></span>|<span data-ttu-id="321de-115">La transazione (ID di processo %d) è stata interrotta a causa di un deadlock delle risorse %.\*ls con un altro processo.</span><span class="sxs-lookup"><span data-stu-id="321de-115">Transaction (Process ID %d) was deadlocked on %.\*ls resources with another process and has been chosen as the deadlock victim.</span></span> <span data-ttu-id="321de-116">Ripetere la transazione.</span><span class="sxs-lookup"><span data-stu-id="321de-116">Rerun the transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="321de-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="321de-117">Explanation</span></span>  
 <span data-ttu-id="321de-118">Accesso alle risorse in ordine conflittuale in transazioni distinte, con conseguente deadlock.</span><span class="sxs-lookup"><span data-stu-id="321de-118">Resources are accessed in conflicting order on separate transactions, causing a deadlock.</span></span> <span data-ttu-id="321de-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="321de-119">For example:</span></span>  
  
-   <span data-ttu-id="321de-120">Transaction1 aggiorna **Table1.Row1**, mentre Transaction2 aggiorna **Table2.Row2**.</span><span class="sxs-lookup"><span data-stu-id="321de-120">Transaction1 updates **Table1.Row1**, while Transaction2 updates **Table2.Row2**.</span></span>  
  
-   <span data-ttu-id="321de-121">Transaction1 tenta di aggiornare **Table2.Row2** ma viene bloccata perché non è ancora stato eseguito il commit di Transaction2.</span><span class="sxs-lookup"><span data-stu-id="321de-121">Transaction1 tries to update **Table2.Row2** but is blocked because Transaction2 has not yet committed.</span></span>  
  
-   <span data-ttu-id="321de-122">Transaction2 tenta quindi di aggiornare **Table1.Row1** ma viene bloccata perché non è stato eseguito il commit di Transaction1.</span><span class="sxs-lookup"><span data-stu-id="321de-122">Transaction2 now tries to update **Table1.Row1** but is blocked because Transaction1 has not committed.</span></span>  
  
-   <span data-ttu-id="321de-123">Si verifica un deadlock perché Transaction1 è in attesa del completamento di Transaction2 e Transaction2 è in attesa a sua volta del completamento di Transaction1.</span><span class="sxs-lookup"><span data-stu-id="321de-123">A deadlock occurs because Transaction1 is waiting for Transaction2 to complete, but Transaction2 is waiting for Transaction1 to complete.</span></span>  
  
 <span data-ttu-id="321de-124">Il sistema rileva il deadlock e sceglie una delle transazioni interessate come "vittima" e genera questo messaggio. Eseguire il rollback della transazione vittima.</span><span class="sxs-lookup"><span data-stu-id="321de-124">The system will detect this deadlock and will choose one of the transactions involved as a 'victim' and will issue this message, rolling back the victim's transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="321de-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="321de-125">User Action</span></span>  
 <span data-ttu-id="321de-126">Eseguire nuovamente la transazione.</span><span class="sxs-lookup"><span data-stu-id="321de-126">Execute the transaction again.</span></span> <span data-ttu-id="321de-127">È inoltre possibile modificare l'applicazione per evitare i deadlock.</span><span class="sxs-lookup"><span data-stu-id="321de-127">You can also revise the application to avoid deadlocks.</span></span> <span data-ttu-id="321de-128">È possibile tentare di eseguire nuovamente la transazione scelta come vittima. In base alle operazioni che verranno eseguite simultaneamente, è probabile che la transazione abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="321de-128">The transaction that was chosen as a victim can be retried and will likely succeed, depending on what operations are being executed simultaneously.</span></span>  
  
 <span data-ttu-id="321de-129">Per impedire che si verifichino deadlock, è consigliabile che tutte le transazioni accedano alle righe nello stesso ordine (**Table1**, quindi **Table2**). In questo modo, sebbene sia possibile che si verifichi un blocco, non si verificherà un deadlock.</span><span class="sxs-lookup"><span data-stu-id="321de-129">To prevent or avoid deadlocks from occurring, consider having all transactions access rows in the same order (**Table1**, then **Table2**); this way, although blocking might occur, a deadlock will not occur.</span></span>  
  
  
