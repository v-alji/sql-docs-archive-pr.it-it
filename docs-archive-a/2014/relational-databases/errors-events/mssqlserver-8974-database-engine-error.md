---
title: MSSQLSERVER_8974 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8974 (Database Engine error)
ms.assetid: 52098678-0858-4a14-ad07-37ebbafca5fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3107f5b62caf04e232532c2d2b93d5da19fb53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638409"
---
# <a name="mssqlserver_8974"></a><span data-ttu-id="1804d-102">MSSQLSERVER_8974</span><span class="sxs-lookup"><span data-stu-id="1804d-102">MSSQLSERVER_8974</span></span>
    
## <a name="details"></a><span data-ttu-id="1804d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1804d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1804d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="1804d-104">Product Name</span></span>|<span data-ttu-id="1804d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1804d-105">SQL Server</span></span>|  
|<span data-ttu-id="1804d-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="1804d-106">Event ID</span></span>|<span data-ttu-id="1804d-107">8974</span><span class="sxs-lookup"><span data-stu-id="1804d-107">8974</span></span>|  
|<span data-ttu-id="1804d-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="1804d-108">Event Source</span></span>|<span data-ttu-id="1804d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1804d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1804d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1804d-110">Component</span></span>|<span data-ttu-id="1804d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1804d-111">SQLEngine</span></span>|  
|<span data-ttu-id="1804d-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="1804d-112">Symbolic Name</span></span>|<span data-ttu-id="1804d-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span><span class="sxs-lookup"><span data-stu-id="1804d-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span></span>|  
|<span data-ttu-id="1804d-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="1804d-114">Message Text</span></span>|<span data-ttu-id="1804d-115">Errore di tabella: ID di oggetto O_ID, ID di indice I_ID, ID di partizione PN_ID, ID di unità di allocazione A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="1804d-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="1804d-116">La pagina P_ID2, slot S_ID2 e la pagina P_ID3, slot P_ID3 puntano al nodo di dati all'esterno di righe alla pagina P_ID1, slot S_ID1, ID di testo TEXT_ID.</span><span class="sxs-lookup"><span data-stu-id="1804d-116">The off-row data node at page P_ID1, slot S_ID1, text ID TEXT_ID is pointed to by page P_ID2, slot S_ID2 and by page P_ID3, slot P_ID3.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1804d-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="1804d-117">Explanation</span></span>  
 <span data-ttu-id="1804d-118">Un nodo di dati all'esterno di righe viene elencato come nodo figlio da due record di dati o di indice.</span><span class="sxs-lookup"><span data-stu-id="1804d-118">An off-row data node has two data or index records that list it as a child node.</span></span> <span data-ttu-id="1804d-119">Un nodo può disporre di un solo nodo padre.</span><span class="sxs-lookup"><span data-stu-id="1804d-119">A node can have only one parent node.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1804d-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="1804d-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="1804d-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="1804d-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="1804d-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="1804d-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="1804d-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="1804d-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="1804d-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="1804d-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="1804d-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="1804d-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="1804d-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="1804d-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="1804d-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="1804d-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="1804d-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="1804d-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="1804d-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1804d-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="1804d-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="1804d-130">Restore from Backup</span></span>  
 <span data-ttu-id="1804d-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="1804d-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="1804d-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="1804d-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="1804d-133">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="1804d-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="1804d-134">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="1804d-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="1804d-135">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="1804d-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1804d-136">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="1804d-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="1804d-137">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="1804d-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="1804d-138">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="1804d-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="1804d-139">Il nodo di dati all'esterno di righe della pagina *P_ID1* verrà eliminato così come entrambi i riferimenti nelle pagine *P_ID2* e *P_ID3*.</span><span class="sxs-lookup"><span data-stu-id="1804d-139">The off-row data node on page *P_ID1* will be deleted and both references on pages *P_ID2* and *P_ID3* will be deleted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1804d-140">L'operazione di correzione potrebbe comportare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="1804d-140">This repair might cause data loss.</span></span>  
  
  
