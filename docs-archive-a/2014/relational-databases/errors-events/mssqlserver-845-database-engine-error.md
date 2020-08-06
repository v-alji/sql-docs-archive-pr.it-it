---
title: MSSQLSERVER_845 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 845 (Database Engine error)
ms.assetid: 8fff6ad4-234c-44be-b123-e25d5e1cd63e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 24bfb8b3758d0656dad96e4af4ed3b94aa51e07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627274"
---
# <a name="mssqlserver_845"></a><span data-ttu-id="cf20a-102">MSSQLSERVER_845</span><span class="sxs-lookup"><span data-stu-id="cf20a-102">MSSQLSERVER_845</span></span>
    
## <a name="details"></a><span data-ttu-id="cf20a-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cf20a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf20a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="cf20a-104">Product Name</span></span>|<span data-ttu-id="cf20a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cf20a-105">SQL Server</span></span>|  
|<span data-ttu-id="cf20a-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="cf20a-106">Event ID</span></span>|<span data-ttu-id="cf20a-107">845</span><span class="sxs-lookup"><span data-stu-id="cf20a-107">845</span></span>|  
|<span data-ttu-id="cf20a-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="cf20a-108">Event Source</span></span>|<span data-ttu-id="cf20a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cf20a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cf20a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cf20a-110">Component</span></span>|<span data-ttu-id="cf20a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cf20a-111">SQLEngine</span></span>|  
|<span data-ttu-id="cf20a-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="cf20a-112">Symbolic Name</span></span>|<span data-ttu-id="cf20a-113">BUFLATCH_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cf20a-113">BUFLATCH_TIMEOUT</span></span>|  
|<span data-ttu-id="cf20a-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="cf20a-114">Message Text</span></span>|<span data-ttu-id="cf20a-115">Timeout durante l'attesa di un latch del buffer di tipo %d per la pagina %S_PGID, ID di database %d.</span><span class="sxs-lookup"><span data-stu-id="cf20a-115">Time-out occurred while waiting for buffer latch type %d for page %S_PGID, database ID %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cf20a-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="cf20a-116">Explanation</span></span>  
 <span data-ttu-id="cf20a-117">Un processo era in attesa di acquisire un latch, ma ha attesto fino al tempo limite e non ha potuto acquisirne uno.</span><span class="sxs-lookup"><span data-stu-id="cf20a-117">A process was waiting to acquire a latch, but the process waited until the time limit expired and failed to acquire one.</span></span> <span data-ttu-id="cf20a-118">Ciò può verificarsi se il completamento di un'operazione di I/O richiede una quantità di tempo eccessiva, in genere a causa di un blocco dei processi di sistema determinato da altre attività.</span><span class="sxs-lookup"><span data-stu-id="cf20a-118">This can occur if an I/O operation takes too long to complete, usually as a result of other tasks blocking system processes.</span></span> <span data-ttu-id="cf20a-119">In alcuni casi, tuttavia, può essere dovuto a un errore hardware.</span><span class="sxs-lookup"><span data-stu-id="cf20a-119">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cf20a-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="cf20a-120">User Action</span></span>  
 <span data-ttu-id="cf20a-121">È possibile impedire che si verifichi questo errore eseguendo le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf20a-121">Performing the following tasks may prevent this error:</span></span>  
  
-   <span data-ttu-id="cf20a-122">Ridurre il carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf20a-122">Reduce the workload.</span></span>  
  
-   <span data-ttu-id="cf20a-123">Verificare se sono presenti errori di I/O associati nel log degli errori o nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="cf20a-123">Verify whether there are associated I/O failures in the error log or event log.</span></span> <span data-ttu-id="cf20a-124">Gli errori di I/O sono in genere causati da un malfunzionamento del disco.</span><span class="sxs-lookup"><span data-stu-id="cf20a-124">I/O failures are typically caused by disk malfunction.</span></span>  
  
-   <span data-ttu-id="cf20a-125">Verificare nel log degli errori se sono presenti attività che non cedono il controllo e altri errori critici.</span><span class="sxs-lookup"><span data-stu-id="cf20a-125">Check error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="cf20a-126">Se si verificano spesso errori critici, ad esempio di asserzione, risolvere tali problemi.</span><span class="sxs-lookup"><span data-stu-id="cf20a-126">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="cf20a-127">Se l'errore persiste, contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf20a-127">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
