---
title: MSSQLSERVER_3961 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3961 (Database Engine error)
ms.assetid: 3bbc6965-6445-400c-940a-2d85b037513f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f55be9288b3c2e559633d0f67709829466fc8815
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636726"
---
# <a name="mssqlserver_3961"></a><span data-ttu-id="d6bf7-102">MSSQLSERVER_3961</span><span class="sxs-lookup"><span data-stu-id="d6bf7-102">MSSQLSERVER_3961</span></span>
    
## <a name="details"></a><span data-ttu-id="d6bf7-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d6bf7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6bf7-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="d6bf7-104">Product Name</span></span>|<span data-ttu-id="d6bf7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6bf7-105">SQL Server</span></span>|  
|<span data-ttu-id="d6bf7-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="d6bf7-106">Event ID</span></span>|<span data-ttu-id="d6bf7-107">3961</span><span class="sxs-lookup"><span data-stu-id="d6bf7-107">3961</span></span>|  
|<span data-ttu-id="d6bf7-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="d6bf7-108">Event Source</span></span>|<span data-ttu-id="d6bf7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d6bf7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d6bf7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d6bf7-110">Component</span></span>|<span data-ttu-id="d6bf7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d6bf7-111">SQLEngine</span></span>|  
|<span data-ttu-id="d6bf7-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="d6bf7-112">Symbolic Name</span></span>|<span data-ttu-id="d6bf7-113">XACT_METADATA_INVALID</span><span class="sxs-lookup"><span data-stu-id="d6bf7-113">XACT_METADATA_INVALID</span></span>|  
|<span data-ttu-id="d6bf7-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="d6bf7-114">Message Text</span></span>|<span data-ttu-id="d6bf7-115">Transazione di isolamento snapshot non riuscita nel database '%. \* ls' perché l'oggetto a cui accede l'istruzione è stato modificato da un'istruzione DDL in un'altra transazione simultanea fin dall'inizio di questa transazione.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-115">Snapshot isolation transaction failed in database '%.\*ls' because the object accessed by the statement has been modified by a DDL statement in another concurrent transaction since the start of this transaction.</span></span>  <span data-ttu-id="d6bf7-116">È stata respinta perché i metadati non sono sottoposti al controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-116">It is disallowed because the metadata is not versioned.</span></span> <span data-ttu-id="d6bf7-117">Un aggiornamento simultaneo ai metadati può causare incoerenze se combinato con l'isolamento dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-117">A concurrent update to metadata can lead to inconsistency if mixed with snapshot isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d6bf7-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="d6bf7-118">Explanation</span></span>  
 <span data-ttu-id="d6bf7-119">Questo errore può verificarsi se si esegue una query nei metadati nell'isolamento dello snapshot ed è presente un'istruzione DDL simultanea che aggiorna i metadati a cui si accede nell'isolamento dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-119">This error can occur if you are querying metadata under snapshot isolation and there is a concurrent DDL statement that updates the metadata that is being accessed under snapshot isolation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d6bf7-120">non supporta il controllo delle versioni dei metadati.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-120">does not support versioning of metadata.</span></span> <span data-ttu-id="d6bf7-121">Per questo motivo, esistono restrizioni sulle operazioni DDL che è possibile eseguire all'interno di una transazione esplicita in esecuzione nell'isolamento dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-121">For this reason, there are restrictions on what DDL operations can be performed within an explicit transaction running under snapshot isolation.</span></span> <span data-ttu-id="d6bf7-122">Per definizione, una transazione implicita è una singola istruzione che rende possibile applicare la semantica dell'isolamento dello snapshot anche con istruzioni DDL.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-122">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span> <span data-ttu-id="d6bf7-123">Le istruzioni DDL seguenti non sono consentite con l'isolamento snapshot dopo un'istruzione BEGIN TRANSACTION: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME o qualsiasi istruzione DDL di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d6bf7-123">The following DDL statements are not permitted under snapshot isolation after a BEGIN TRANSACTION statement: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME, or any common language runtime (CLR) DDL statement.</span></span> <span data-ttu-id="d6bf7-124">Queste istruzioni sono consentite quando si usa l'isolamento dello snapshot all'interno di transazioni implicite.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-124">These statements are permitted when you are using snapshot isolation within implicit transactions.</span></span> <span data-ttu-id="d6bf7-125">Per definizione, una transazione implicita è una singola istruzione che rende possibile applicare la semantica dell'isolamento dello snapshot anche con istruzioni DDL.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-125">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6bf7-126">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="d6bf7-126">User Action</span></span>  
 <span data-ttu-id="d6bf7-127">Spostare il livello di isolamento dello snapshot su un livello di isolamento non snapshot ad esempio Read committed prima di eseguire una query sui metadati.</span><span class="sxs-lookup"><span data-stu-id="d6bf7-127">Change the snapshot isolation level to a non-snapshot isolation level such as read committed before querying metadata.</span></span>  
  
  
