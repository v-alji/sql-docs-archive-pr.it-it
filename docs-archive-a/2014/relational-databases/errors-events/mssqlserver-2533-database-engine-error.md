---
title: MSSQLSERVER_2533 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2533 (Database Engine error)
ms.assetid: 0418352c-0ab2-4dc7-b8b9-5c3bad94560c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1eb3e2780693a3a0ffed21ce7b9d7887615536c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715311"
---
# <a name="mssqlserver_2533"></a><span data-ttu-id="84d22-102">MSSQLSERVER_2533</span><span class="sxs-lookup"><span data-stu-id="84d22-102">MSSQLSERVER_2533</span></span>
    
## <a name="details"></a><span data-ttu-id="84d22-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="84d22-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84d22-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="84d22-104">Product Name</span></span>|<span data-ttu-id="84d22-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="84d22-105">SQL Server</span></span>|  
|<span data-ttu-id="84d22-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="84d22-106">Event ID</span></span>|<span data-ttu-id="84d22-107">2533</span><span class="sxs-lookup"><span data-stu-id="84d22-107">2533</span></span>|  
|<span data-ttu-id="84d22-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="84d22-108">Event Source</span></span>|<span data-ttu-id="84d22-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="84d22-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="84d22-110">Componente</span><span class="sxs-lookup"><span data-stu-id="84d22-110">Component</span></span>|<span data-ttu-id="84d22-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="84d22-111">SQLEngine</span></span>|  
|<span data-ttu-id="84d22-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="84d22-112">Symbolic Name</span></span>|<span data-ttu-id="84d22-113">DBCC_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="84d22-113">DBCC_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="84d22-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="84d22-114">Message Text</span></span>|<span data-ttu-id="84d22-115">Errore di tabella: impossibile rilevare la pagina P_ID allocata all'ID di oggetto O_ID, con ID di indice I_ID, ID di partizione PN_ID e ID di unità di allocazione A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="84d22-115">Table error: Page P_ID allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) was not seen.</span></span> <span data-ttu-id="84d22-116">La pagina non è valida oppure l'ID di unità di allocazione contenuto nell'intestazione della pagina non è corretto.</span><span class="sxs-lookup"><span data-stu-id="84d22-116">Page may be invalid or have incorrect alloc unit ID in its header.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="84d22-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="84d22-117">Explanation</span></span>  
 <span data-ttu-id="84d22-118">Una pagina viene allocata all'ID di unità di allocazione *A_ID*, che però non è contenuto nell'intestazione della pagina.</span><span class="sxs-lookup"><span data-stu-id="84d22-118">A page is allocated to the allocation unit ID, *A_ID*, but this allocation unit ID is not in the header of the page.</span></span> <span data-ttu-id="84d22-119">L'intestazione ha un ID di unità di allocazione differente.</span><span class="sxs-lookup"><span data-stu-id="84d22-119">The header has a different allocation unit ID.</span></span> <span data-ttu-id="84d22-120">Se l'ID di unità di allocazione contenuto nell'intestazione della pagina è relativo a un oggetto valido, la pagina può restituire un errore MSQLEngine_2534 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="84d22-120">If the allocation unit ID in the header of the page is for a valid object, the page may have a matching MSSQLEngine_2534 error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="84d22-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="84d22-121">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="84d22-122">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="84d22-122">Look for Hardware Failure</span></span>  
 <span data-ttu-id="84d22-123">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="84d22-123">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="84d22-124">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="84d22-124">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="84d22-125">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="84d22-125">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="84d22-126">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="84d22-126">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="84d22-127">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="84d22-127">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="84d22-128">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="84d22-128">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="84d22-129">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="84d22-129">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="84d22-130">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="84d22-130">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="84d22-131">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="84d22-131">Restore from Backup</span></span>  
 <span data-ttu-id="84d22-132">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="84d22-132">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="84d22-133">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="84d22-133">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="84d22-134">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="84d22-134">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="84d22-135">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="84d22-135">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="84d22-136">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="84d22-136">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="84d22-137">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="84d22-137">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="84d22-138">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="84d22-138">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="84d22-139">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="84d22-139">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="84d22-140">L'istruzione REPAIR dealloca la pagina.</span><span class="sxs-lookup"><span data-stu-id="84d22-140">REPAIR will deallocate the page.</span></span> <span data-ttu-id="84d22-141">Se la pagina è relativa a un'unità di allocazione di dati all'interno di righe, l'indice, se esistente, verrà ricompilato.</span><span class="sxs-lookup"><span data-stu-id="84d22-141">If the page was from an in-row data allocation unit, the index, if one exists, will be rebuilt.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="84d22-142">L'operazione di correzione può comportare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="84d22-142">This repair may cause data loss.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d22-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84d22-143">See Also</span></span>  
 [<span data-ttu-id="84d22-144">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="84d22-144">MSSQLSERVER_2534</span></span>](mssqlserver-2534-database-engine-error.md)  
  
  
