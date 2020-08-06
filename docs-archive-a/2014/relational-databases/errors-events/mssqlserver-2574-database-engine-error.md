---
title: MSSQLSERVER_2574 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2574 (Database Engine error)
ms.assetid: efba507a-b5ad-4f1d-b0c8-f73b663a0562
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fd103f8c651ca968ae997ae9c3d544b41cbf3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713191"
---
# <a name="mssqlserver_2574"></a><span data-ttu-id="7bed3-102">MSSQLSERVER_2574</span><span class="sxs-lookup"><span data-stu-id="7bed3-102">MSSQLSERVER_2574</span></span>
    
## <a name="details"></a><span data-ttu-id="7bed3-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7bed3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7bed3-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="7bed3-104">Product Name</span></span>|<span data-ttu-id="7bed3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7bed3-105">SQL Server</span></span>|  
|<span data-ttu-id="7bed3-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="7bed3-106">Event ID</span></span>|<span data-ttu-id="7bed3-107">2574</span><span class="sxs-lookup"><span data-stu-id="7bed3-107">2574</span></span>|  
|<span data-ttu-id="7bed3-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="7bed3-108">Event Source</span></span>|<span data-ttu-id="7bed3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7bed3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7bed3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7bed3-110">Component</span></span>|<span data-ttu-id="7bed3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7bed3-111">SQLEngine</span></span>|  
|<span data-ttu-id="7bed3-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="7bed3-112">Symbolic Name</span></span>|<span data-ttu-id="7bed3-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span><span class="sxs-lookup"><span data-stu-id="7bed3-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span></span>|  
|<span data-ttu-id="7bed3-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="7bed3-114">Message Text</span></span>|<span data-ttu-id="7bed3-115">Errore di tabella: pagina ID_P vuota nell'oggetto con ID O_ID, ID di indice I_ID, ID di partizione PN_ID e ID di unità di allocazione A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="7bed3-115">Table error: Page P_ID is empty in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="7bed3-116">Tale condizione non è consentita al livello LEVEL dell'albero B.</span><span class="sxs-lookup"><span data-stu-id="7bed3-116">This is not permitted at level LEVEL of the B-tree.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7bed3-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="7bed3-117">Explanation</span></span>  
 <span data-ttu-id="7bed3-118">Una pagina dell'albero B superiore al livello foglia dell'indice specificato è vuota, ovvero non contiene righe.</span><span class="sxs-lookup"><span data-stu-id="7bed3-118">A B-tree page above the leaf level of the specified index is empty, that is it has no rows.</span></span> <span data-ttu-id="7bed3-119">Questo comportamento è possibile per le pagine del livello foglia in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], ma non è mai consentito nei livelli albero.</span><span class="sxs-lookup"><span data-stu-id="7bed3-119">This behavior is possible for leaf-level pages in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but has never been possible in tree levels.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7bed3-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7bed3-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="7bed3-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="7bed3-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="7bed3-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="7bed3-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="7bed3-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="7bed3-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="7bed3-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="7bed3-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="7bed3-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="7bed3-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="7bed3-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="7bed3-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="7bed3-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="7bed3-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="7bed3-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="7bed3-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="7bed3-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7bed3-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="7bed3-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="7bed3-130">Restore from Backup</span></span>  
 <span data-ttu-id="7bed3-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="7bed3-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="7bed3-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="7bed3-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="7bed3-133">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="7bed3-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="7bed3-134">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="7bed3-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="7bed3-135">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="7bed3-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7bed3-136">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="7bed3-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="7bed3-137">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="7bed3-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="7bed3-138">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="7bed3-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="7bed3-139">L'istruzione DBCC ricompila l'indice.</span><span class="sxs-lookup"><span data-stu-id="7bed3-139">DBCC will rebuild the index.</span></span>  
  
  
