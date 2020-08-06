---
title: MSSQLSERVER_2576 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2576 (Database Engine error)
ms.assetid: b727cc2f-c76c-46f8-bbbe-5e7a05a6eabf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f378051c7844bf08d617db56666d69b22ecf732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626789"
---
# <a name="mssqlserver_2576"></a><span data-ttu-id="2824a-102">MSSQLSERVER_2576</span><span class="sxs-lookup"><span data-stu-id="2824a-102">MSSQLSERVER_2576</span></span>
    
## <a name="details"></a><span data-ttu-id="2824a-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2824a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2824a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="2824a-104">Product Name</span></span>|<span data-ttu-id="2824a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2824a-105">SQL Server</span></span>|  
|<span data-ttu-id="2824a-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="2824a-106">Event ID</span></span>|<span data-ttu-id="2824a-107">2576</span><span class="sxs-lookup"><span data-stu-id="2824a-107">2576</span></span>|  
|<span data-ttu-id="2824a-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="2824a-108">Event Source</span></span>|<span data-ttu-id="2824a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2824a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2824a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2824a-110">Component</span></span>|<span data-ttu-id="2824a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2824a-111">SQLEngine</span></span>|  
|<span data-ttu-id="2824a-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="2824a-112">Symbolic Name</span></span>|<span data-ttu-id="2824a-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="2824a-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="2824a-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="2824a-114">Message Text</span></span>|<span data-ttu-id="2824a-115">Il puntatore di pagina precedente della pagina IAM (Index Allocation Map) P_ID2 nell'oggetto con ID O_ID, ID di indice I_ID, ID di partizione PN_ID e ID di unità di allocazione A_ID (tipo TYPE) punta alla pagina IAM P_ID1, che non è stata rilevata durante l'analisi.</span><span class="sxs-lookup"><span data-stu-id="2824a-115">The Index Allocation Map (IAM) page P_ID1 is pointed to by the previous pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2824a-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="2824a-116">Explanation</span></span>  
 <span data-ttu-id="2824a-117">Una pagina IAM o una voce di metadati non è stata individuata, nonostante esista un riferimento alla pagina come collegamento a un'altra pagina IAM precedente in una catena IAM.</span><span class="sxs-lookup"><span data-stu-id="2824a-117">An Index Allocation Map (IAM) page or metadata entry was not located, even though a reference to the page exists as the previous page link on another IAM page in an IAM chain.</span></span> <span data-ttu-id="2824a-118">Se la pagina *P_ID1* è (0:0), la pagina IAM *P_ID2* è l'inizio di una catena IAM e la voce di metadati della catena IAM è mancante.</span><span class="sxs-lookup"><span data-stu-id="2824a-118">If the *P_ID1* page is (0:0), the IAM page, *P_ID2*, is the start of an IAM chain, and the metadata entry for the IAM chain is missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2824a-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="2824a-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="2824a-120">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="2824a-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="2824a-121">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="2824a-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="2824a-122">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="2824a-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="2824a-123">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="2824a-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="2824a-124">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="2824a-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="2824a-125">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="2824a-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="2824a-126">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="2824a-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="2824a-127">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="2824a-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="2824a-128">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2824a-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="2824a-129">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="2824a-129">Restore from Backup</span></span>  
 <span data-ttu-id="2824a-130">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="2824a-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="2824a-131">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="2824a-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="2824a-132">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="2824a-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="2824a-133">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="2824a-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="2824a-134">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="2824a-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2824a-135">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="2824a-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="2824a-136">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="2824a-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="2824a-137">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="2824a-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="2824a-138">L'istruzione REPAIR tenterà di ricompilare la catena IAM che interessa la pagina *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="2824a-138">REPAIR will try to rebuild the IAM chain involving the *P_ID2* page.</span></span> <span data-ttu-id="2824a-139">La ricompilazione della catena può comportare la rimozione di alcune pagine dalla stessa catena o la rimozione dell'intera catena se i metadati sono danneggiati.</span><span class="sxs-lookup"><span data-stu-id="2824a-139">Rebuilding the chain may involve removing pages from the chain, or removing the whole chain if the metadata is corrupted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2824a-140">L'operazione di correzione può comportare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="2824a-140">This repair may cause data loss.</span></span>  
  
  
