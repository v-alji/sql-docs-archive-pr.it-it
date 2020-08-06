---
title: Categoria di eventi Transazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Transactions event category
- event classes [SQL Server], Transactions event category
- Transactions event category [SQL Server]
ms.assetid: bfc75c5b-7115-49d8-9148-a0c84ee66a9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b68a91fb166797c220cb0c4f5cf2607ca267538
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635621"
---
# <a name="transactions-event-category"></a><span data-ttu-id="c8038-102">Categoria di eventi Transactions</span><span class="sxs-lookup"><span data-stu-id="c8038-102">Transactions Event Category</span></span>
  <span data-ttu-id="c8038-103">Le classi di eventi della categoria **Transactions** consentono di monitorare lo stato delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="c8038-103">The **Transactions** event classes can be used to monitor the status of transactions.</span></span> <span data-ttu-id="c8038-104">I nomi delle classi di eventi con prefisso **TM:** sono utilizzati per tracciare le operazioni correlate alle transazioni che vengano inviate tramite l'interfaccia di gestione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="c8038-104">The event class names that are prefixed with **TM:** are used to track the transaction-related operations that are sent through the transaction management interface.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8038-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c8038-105">In This Section</span></span>  
  
|<span data-ttu-id="c8038-106">Argomento</span><span class="sxs-lookup"><span data-stu-id="c8038-106">Topic</span></span>|<span data-ttu-id="c8038-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8038-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c8038-108">Classe di evento DTCTransaction</span><span class="sxs-lookup"><span data-stu-id="c8038-108">DTCTransaction Event Class</span></span>](dtctransaction-event-class.md)|<span data-ttu-id="c8038-109">Tiene traccia delle transazioni coordinate da [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="c8038-109">Tracks transactions coordinated by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="c8038-110">Si tratta delle transazioni distribuite tra due o più database o istanze di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8038-110">These are transactions distributed between two or more databases or instances of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c8038-111">Classe di evento SQLTransaction</span><span class="sxs-lookup"><span data-stu-id="c8038-111">SQLTransaction Event Class</span></span>](sqltransaction-event-class.md)|<span data-ttu-id="c8038-112">Tiene traccia delle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN e ROLLBACK TRAN.</span><span class="sxs-lookup"><span data-stu-id="c8038-112">Tracks [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN, and ROLLBACK TRAN statements.</span></span>|  
|[<span data-ttu-id="c8038-113">Classe di evento TM: Begin Tran Completed</span><span class="sxs-lookup"><span data-stu-id="c8038-113">TM: Begin Tran Completed Event Class</span></span>](tm-begin-tran-completed-event-class.md)|<span data-ttu-id="c8038-114">Indica il completamento di una richiesta BEGIN TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-114">Indicates that a BEGIN TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="c8038-115">Classe di evento TM: Begin Tran Starting</span><span class="sxs-lookup"><span data-stu-id="c8038-115">TM: Begin Tran Starting Event Class</span></span>](tm-begin-tran-starting-event-class.md)|<span data-ttu-id="c8038-116">Indica l'avvio di una richiesta BEGIN TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-116">Indicates that a BEGIN TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="c8038-117">Classe di evento TM: Commit Tran Completed</span><span class="sxs-lookup"><span data-stu-id="c8038-117">TM: Commit Tran Completed Event Class</span></span>](tm-commit-tran-completed-event-class.md)|<span data-ttu-id="c8038-118">Indica il completamento di una richiesta COMMIT TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-118">Indicates that a COMMIT TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="c8038-119">Classe di evento TM: Commit Tran Starting</span><span class="sxs-lookup"><span data-stu-id="c8038-119">TM: Commit Tran Starting Event Class</span></span>](tm-commit-tran-starting-event-class.md)|<span data-ttu-id="c8038-120">Indica l'avvio di una richiesta COMMIT TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-120">Indicates that a COMMIT TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="c8038-121">Classe di evento TM: Promote Tran Completed</span><span class="sxs-lookup"><span data-stu-id="c8038-121">TM: Promote Tran Completed Event Class</span></span>](tm-promote-tran-completed-event-class.md)|<span data-ttu-id="c8038-122">Indica il completamento di una richiesta PROMOTE TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-122">Indicates that a PROMOTE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="c8038-123">Classe di evento TM: Promote Tran Starting</span><span class="sxs-lookup"><span data-stu-id="c8038-123">TM: Promote Tran Starting Event Class</span></span>](tm-promote-tran-starting-event-class.md)|<span data-ttu-id="c8038-124">Indica l'avvio di una richiesta PROMOTE TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-124">Indicates that a PROMOTE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="c8038-125">Classe di evento TM: Rollback Tran Completed</span><span class="sxs-lookup"><span data-stu-id="c8038-125">TM: Rollback Tran Completed Event Class</span></span>](tm-rollback-tran-completed-event-class.md)|<span data-ttu-id="c8038-126">Indica il completamento di una richiesta ROLLBACK TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-126">Indicates that a ROLLBACK TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="c8038-127">Classe di evento TM: Rollback Tran Starting</span><span class="sxs-lookup"><span data-stu-id="c8038-127">TM: Rollback Tran Starting Event Class</span></span>](tm-rollback-tran-starting-event-class.md)|<span data-ttu-id="c8038-128">Indica l'avvio di una richiesta ROLLBACK TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-128">Indicates that a ROLLBACK TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="c8038-129">Classe di evento TM: Save Tran Completed</span><span class="sxs-lookup"><span data-stu-id="c8038-129">TM: Save Tran Completed Event Class</span></span>](tm-save-tran-completed-event-class.md)|<span data-ttu-id="c8038-130">Indica il completamento di una richiesta SAVE TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-130">Indicates that a SAVE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="c8038-131">Classe di evento TM: Save Tran Starting</span><span class="sxs-lookup"><span data-stu-id="c8038-131">TM: Save Tran Starting Event Class</span></span>](tm-save-tran-starting-event-class.md)|<span data-ttu-id="c8038-132">Indica l'avvio di una richiesta SAVE TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c8038-132">Indicates that a SAVE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="c8038-133">Classe di evento TransactionLog</span><span class="sxs-lookup"><span data-stu-id="c8038-133">TransactionLog Event Class</span></span>](transactionlog-event-class.md)|<span data-ttu-id="c8038-134">Traccia l'inserimento delle transazioni in un log delle transazioni di database.</span><span class="sxs-lookup"><span data-stu-id="c8038-134">Tracks when transactions are written to a database transaction log.</span></span>|  
  
  
