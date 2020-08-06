---
title: MSSQLSERVER_8993 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8993 (Database Engine error)
ms.assetid: 06aac110-a41c-4853-bc8e-a83e8535b8be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5ee9497e9c4484fd885803c0feff20362a159ff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624222"
---
# <a name="mssqlserver_8993"></a><span data-ttu-id="17092-102">MSSQLSERVER_8993</span><span class="sxs-lookup"><span data-stu-id="17092-102">MSSQLSERVER_8993</span></span>
    
## <a name="details"></a><span data-ttu-id="17092-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="17092-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17092-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="17092-104">Product Name</span></span>|<span data-ttu-id="17092-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="17092-105">SQL Server</span></span>|  
|<span data-ttu-id="17092-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="17092-106">Event ID</span></span>|<span data-ttu-id="17092-107">8993</span><span class="sxs-lookup"><span data-stu-id="17092-107">8993</span></span>|  
|<span data-ttu-id="17092-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="17092-108">Event Source</span></span>|<span data-ttu-id="17092-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="17092-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="17092-110">Componente</span><span class="sxs-lookup"><span data-stu-id="17092-110">Component</span></span>|<span data-ttu-id="17092-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="17092-111">SQLEngine</span></span>|  
|<span data-ttu-id="17092-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="17092-112">Symbolic Name</span></span>|<span data-ttu-id="17092-113">DBCC3_MISSING_FORWARDED_ROW</span><span class="sxs-lookup"><span data-stu-id="17092-113">DBCC3_MISSING_FORWARDED_ROW</span></span>|  
|<span data-ttu-id="17092-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="17092-114">Message Text</span></span>|<span data-ttu-id="17092-115">L'ID di oggetto O_ID, nella pagina della riga da inoltrare P_ID1, slot S_ID1 punta alla pagina P_ID2, slot S_ID2.</span><span class="sxs-lookup"><span data-stu-id="17092-115">Object ID O_ID, forwarding row page P_ID1, slot S_ID1 points to page P_ID2, slot S_ID2.</span></span> <span data-ttu-id="17092-116">Impossibile trovare la riga inoltrata.</span><span class="sxs-lookup"><span data-stu-id="17092-116">Did not encounter forwarded row.</span></span> <span data-ttu-id="17092-117">Possibile errore di allocazione.</span><span class="sxs-lookup"><span data-stu-id="17092-117">Possible allocation error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="17092-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="17092-118">Explanation</span></span>  
 <span data-ttu-id="17092-119">Una riga da inoltrare in un heap punta a una riga inoltrata non esistente.</span><span class="sxs-lookup"><span data-stu-id="17092-119">A forwarding row in a heap points to a nonexistent forwarded row.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="17092-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="17092-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="17092-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="17092-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="17092-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="17092-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="17092-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="17092-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="17092-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="17092-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="17092-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="17092-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="17092-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="17092-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="17092-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="17092-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="17092-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="17092-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="17092-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="17092-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="17092-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="17092-130">Restore from Backup</span></span>  
 <span data-ttu-id="17092-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="17092-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="17092-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="17092-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="17092-133">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="17092-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="17092-134">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="17092-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="17092-135">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="17092-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="17092-136">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="17092-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="17092-137">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="17092-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="17092-138">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="17092-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="17092-139">La riga da inoltrare verrà eliminata e tutti gli indici non cluster verranno ricompilati.</span><span class="sxs-lookup"><span data-stu-id="17092-139">The forwarding row will be deleted and any nonclustered indexes will be rebuilt.</span></span>  
  
  
