---
title: Transazioni XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 443d67e4-1c7f-41d7-b18d-2d657f58c22a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 75fa8bc9a673d9e0e018b8578a35af2e46b5044c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714243"
---
# <a name="xtp-transactions"></a><span data-ttu-id="8bc5b-102">XTP Transactions</span><span class="sxs-lookup"><span data-stu-id="8bc5b-102">XTP Transactions</span></span>
  <span data-ttu-id="8bc5b-103">L'oggetto prestazione XTP Transactions contiene contatori correlati alle transazioni del motore XTP in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bc5b-103">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8bc5b-104">In questa tabella vengono descritti i contatori delle **transazioni di XTP** .</span><span class="sxs-lookup"><span data-stu-id="8bc5b-104">This table describes the **XTP Transactions** counters.</span></span>  
  
|<span data-ttu-id="8bc5b-105">Contatore</span><span class="sxs-lookup"><span data-stu-id="8bc5b-105">Counter</span></span>|<span data-ttu-id="8bc5b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8bc5b-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8bc5b-107">**Interruzioni a catena/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-107">**Cascading aborts/sec**</span></span>|<span data-ttu-id="8bc5b-108">Numero medio di transazioni di cui è stato eseguito il rollback a causa di un rollback di dipendenza di commit, al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-108">The number of transactions that rolled back to due a commit dependency rollback (on average), per second.</span></span>|  
|<span data-ttu-id="8bc5b-109">**Dipendenze di commit acquisite/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-109">**Commit dependencies taken/sec**</span></span>|<span data-ttu-id="8bc5b-110">Numero medio delle dipendenze di commit acquisite dalle transazioni, al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-110">The number of commit dependencies taken by transactions (on average), per second.</span></span>|  
|<span data-ttu-id="8bc5b-111">**Transazioni di sola lettura preparate/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-111">**Read-only transactions prepared/sec**</span></span>|<span data-ttu-id="8bc5b-112">Numero di transazioni di sola lettura che sono state preparate per l'elaborazione del commit, al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-112">The number of read-only transactions that were prepared for commit processing, per second.</span></span>|  
|<span data-ttu-id="8bc5b-113">**Aggiornamenti del punto di salvataggio/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-113">**Save point refreshes/sec**</span></span>|<span data-ttu-id="8bc5b-114">Numero medio di volte in cui un punto di salvataggio "è stato aggiornato", al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-114">The number of times a savepoint was "refreshed", (on average), per second.</span></span> <span data-ttu-id="8bc5b-115">L'aggiornamento di un punto di salvataggio avviene quando un punto di salvataggio esistente viene reimpostato sul punto corrente della durata della transazione.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-115">A savepoint refresh is when an existing savepoint is reset to the current point in the transaction's lifetime.</span></span>|  
|<span data-ttu-id="8bc5b-116">**Rollback del punto di salvataggio/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-116">**Save point rollbacks/sec**</span></span>|<span data-ttu-id="8bc5b-117">Numero medio di volte che è stato eseguito il rollback di una transazione a un punto di salvataggio, al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-117">The number of times a transaction rolled back to a save point (on average), per second.</span></span>|  
|<span data-ttu-id="8bc5b-118">**Punti di salvataggio creati/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-118">**Save points created /sec**</span></span>|<span data-ttu-id="8bc5b-119">Numero medio di punti di salvataggio creati, al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-119">The number of save points created (on average), per second.</span></span>|  
|<span data-ttu-id="8bc5b-120">**Errori di convalida delle transazioni/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-120">**Transaction validation failure/sec**</span></span>|<span data-ttu-id="8bc5b-121">Numero medio di transazioni per cui l'elaborazione di convalida ha avito esito negativo, al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-121">The number of transactions that failed validation processing (on average), per second.</span></span>|  
|<span data-ttu-id="8bc5b-122">**Transazioni interrotte dall'utente/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-122">**Transactions aborted by user/sec**</span></span>|<span data-ttu-id="8bc5b-123">Numero medio di transazioni che sono state interrotte dall'utente, al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-123">The number of transactions that were aborted by the user (on average), per second.</span></span>|  
|<span data-ttu-id="8bc5b-124">**Transazioni interrotte/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-124">**Transactions aborted/sec**</span></span>|<span data-ttu-id="8bc5b-125">Numero medio di transazioni che sono state interrotte (sia dall'utente che dal sistema), al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-125">The number of transactions that aborted (both by the user and the system, on average), per second.</span></span>|  
|<span data-ttu-id="8bc5b-126">**Transazioni create/sec**</span><span class="sxs-lookup"><span data-stu-id="8bc5b-126">**Transactions created/sec**</span></span>|<span data-ttu-id="8bc5b-127">Numero medio di transazioni create nel sistema, al secondo.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-127">The number of transactions created in the system (on average), per second.</span></span><br /><br /> <span data-ttu-id="8bc5b-128">Le transazioni XTP sono calcolate in modo diverso rispetto alle transazioni basate su disco (come indicato in Database:Transazioni/sec).</span><span class="sxs-lookup"><span data-stu-id="8bc5b-128">XTP transactions are counted differently than disk-based transactions (as reflected in Databases:Transactions/sec).</span></span> <span data-ttu-id="8bc5b-129">Ad esempio, Transazioni create/sec conteggia le transazioni di sola lettura, a differenza di Database:Transazioni/sec.</span><span class="sxs-lookup"><span data-stu-id="8bc5b-129">For example, Transactions created/sec counts read/only transactions, while Databases:Transactions/sec does not.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bc5b-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bc5b-130">See Also</span></span>  
 [<span data-ttu-id="8bc5b-131">XTP &#40;i contatori delle prestazioni di OLTP in memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="8bc5b-131">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
