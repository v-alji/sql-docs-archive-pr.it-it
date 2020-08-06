---
title: MSSQLSERVER_2577 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2577 (Database Engine error)
ms.assetid: f53256a2-2fb0-47fd-9ed9-c45389104145
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9e4b7b85f59ba721eae6b4a0ac8db1b2d288422d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636119"
---
# <a name="mssqlserver_2577"></a><span data-ttu-id="a0704-102">MSSQLSERVER_2577</span><span class="sxs-lookup"><span data-stu-id="a0704-102">MSSQLSERVER_2577</span></span>
    
## <a name="details"></a><span data-ttu-id="a0704-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a0704-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0704-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a0704-104">Product Name</span></span>|<span data-ttu-id="a0704-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a0704-105">SQL Server</span></span>|  
|<span data-ttu-id="a0704-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a0704-106">Event ID</span></span>|<span data-ttu-id="a0704-107">2577</span><span class="sxs-lookup"><span data-stu-id="a0704-107">2577</span></span>|  
|<span data-ttu-id="a0704-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a0704-108">Event Source</span></span>|<span data-ttu-id="a0704-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a0704-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a0704-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a0704-110">Component</span></span>|<span data-ttu-id="a0704-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a0704-111">SQLEngine</span></span>|  
|<span data-ttu-id="a0704-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a0704-112">Symbolic Name</span></span>|<span data-ttu-id="a0704-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="a0704-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="a0704-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a0704-114">Message Text</span></span>|<span data-ttu-id="a0704-115">Numeri di sequenza della catena non ordinati nella catena IAM (Index Allocation Map) per l'ID di oggetto O_ID, ID di indice I_ID, ID di partizione PN_ID, ID di unità di allocazione A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="a0704-115">Chain sequence numbers out of order in the Index Allocation Map (IAM) chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="a0704-116">La pagina P_ID1, con numero di sequenza SEQUENCE1 punta alla pagina P_ID2, con numero di sequenza SEQUENCE2.</span><span class="sxs-lookup"><span data-stu-id="a0704-116">Page P_ID1 with sequence number SEQUENCE1 points to page P_ID2 with sequence number SEQUENCE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a0704-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a0704-117">Explanation</span></span>  
 <span data-ttu-id="a0704-118">Ogni pagina IAM (Index Allocation Map) ha un numero di sequenza.</span><span class="sxs-lookup"><span data-stu-id="a0704-118">Every Index Allocation Map (IAM) page has a sequence number.</span></span> <span data-ttu-id="a0704-119">Il numero di sequenza indica la posizione della pagina IAM all'interno della catena IAM.</span><span class="sxs-lookup"><span data-stu-id="a0704-119">The sequence number is the position of the IAM page within the IAM chain.</span></span> <span data-ttu-id="a0704-120">Di norma i numeri di sequenza vengono aumentati di un'unità per ogni pagina IAM.</span><span class="sxs-lookup"><span data-stu-id="a0704-120">The rule is that sequence numbers increase by one for each IAM page.</span></span> <span data-ttu-id="a0704-121">La pagina IAM *P_ID2* ha un numero di sequenza che non segue questa regola.</span><span class="sxs-lookup"><span data-stu-id="a0704-121">IAM page, *P_ID2*, has a sequence number that does not follow this rule.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a0704-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a0704-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a0704-123">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="a0704-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a0704-124">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="a0704-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a0704-125">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="a0704-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a0704-126">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="a0704-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a0704-127">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="a0704-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a0704-128">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="a0704-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a0704-129">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="a0704-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a0704-130">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="a0704-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a0704-131">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a0704-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a0704-132">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="a0704-132">Restore from Backup</span></span>  
 <span data-ttu-id="a0704-133">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="a0704-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a0704-134">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a0704-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a0704-135">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="a0704-135">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="a0704-136">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="a0704-136">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="a0704-137">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="a0704-137">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a0704-138">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="a0704-138">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="a0704-139">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="a0704-139">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="a0704-140">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="a0704-140">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="a0704-141">L'esecuzione dell'istruzione REPAIR ricompila la catena IAM.</span><span class="sxs-lookup"><span data-stu-id="a0704-141">Running REPAIR will rebuild the IAM chain.</span></span> <span data-ttu-id="a0704-142">REPAIR divide innanzitutto la catena IAM esistente in due metà.</span><span class="sxs-lookup"><span data-stu-id="a0704-142">REPAIR first splits the existing IAM chain in two halves.</span></span> <span data-ttu-id="a0704-143">La prima metà della catena termina con una pagina IAM, *P_ID1*.</span><span class="sxs-lookup"><span data-stu-id="a0704-143">The first half of the chain will end with IAM page, *P_ID1*.</span></span> <span data-ttu-id="a0704-144">Il puntatore di pagina successiva della pagina *P_ID1* viene impostato su (0:0).</span><span class="sxs-lookup"><span data-stu-id="a0704-144">The next page pointer of the *P_ID1* page will be set to (0:0).</span></span> <span data-ttu-id="a0704-145">La seconda metà della catena inizia con una pagina IAM, *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="a0704-145">The second half of the chain will start with IAM page, *P_ID2*.</span></span> <span data-ttu-id="a0704-146">Il puntatore di pagina precedente della pagina *P_ID2* viene impostato su (0:0).</span><span class="sxs-lookup"><span data-stu-id="a0704-146">The previous page pointer of the *P_ID2* page will be set to (0:0).</span></span>  
  
 <span data-ttu-id="a0704-147">REPAIR collega quindi le due metà e rigenera i numeri di sequenza della catena IAM.</span><span class="sxs-lookup"><span data-stu-id="a0704-147">REPAIR will then connect the two haves of the chain together and regenerate the sequence numbers for the IAM chain.</span></span> <span data-ttu-id="a0704-148">Le pagine IAM che non possono essere corrette verranno deallocate.</span><span class="sxs-lookup"><span data-stu-id="a0704-148">Any IAM pages that cannot be repaired will be deallocated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a0704-149">L'operazione di correzione può comportare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="a0704-149">This repair may cause data loss.</span></span>  
  
  
