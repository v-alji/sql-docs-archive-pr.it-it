---
title: MSSQLSERVER_2534 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2534 (Database Engine error)
ms.assetid: 121cf99d-0722-494c-be24-3369c1a0badc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 409c429f961cd8357bfa2e40663c33f3c1f2e36d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636132"
---
# <a name="mssqlserver_2534"></a><span data-ttu-id="75b61-102">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="75b61-102">MSSQLSERVER_2534</span></span>
    
## <a name="details"></a><span data-ttu-id="75b61-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="75b61-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75b61-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="75b61-104">Product Name</span></span>|<span data-ttu-id="75b61-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="75b61-105">SQL Server</span></span>|  
|<span data-ttu-id="75b61-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="75b61-106">Event ID</span></span>|<span data-ttu-id="75b61-107">2534</span><span class="sxs-lookup"><span data-stu-id="75b61-107">2534</span></span>|  
|<span data-ttu-id="75b61-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="75b61-108">Event Source</span></span>|<span data-ttu-id="75b61-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="75b61-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="75b61-110">Componente</span><span class="sxs-lookup"><span data-stu-id="75b61-110">Component</span></span>|<span data-ttu-id="75b61-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="75b61-111">SQLEngine</span></span>|  
|<span data-ttu-id="75b61-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="75b61-112">Symbolic Name</span></span>|<span data-ttu-id="75b61-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span><span class="sxs-lookup"><span data-stu-id="75b61-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span></span>|  
|<span data-ttu-id="75b61-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="75b61-114">Message Text</span></span>|<span data-ttu-id="75b61-115">Errore di tabella: la pagina P_ID, la cui intestazione indica che è allocata all'ID di oggetto ID O_ID, con ID di indice I_ID, ID di partizione PN_ID e ID di unità di allocazione ID A_ID (tipo TYPE), è allocata da un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="75b61-115">Table error: Page P_ID, whose header indicates it as being allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), is allocated by another object.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="75b61-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="75b61-116">Explanation</span></span>  
 <span data-ttu-id="75b61-117">L'intestazione della pagina contiene l'ID di unità di allocazione *A_ID*, ma nessuna delle pagine della mappa di allocazione degli indici (IAM, Index Allocation Map) relativa a tale unità di allocazione alloca la pagina.</span><span class="sxs-lookup"><span data-stu-id="75b61-117">The header of the page contains the allocation unit ID, *A_ID*, but none of the Index Allocation Map (IAM) pages of that allocation unit allocates the page.</span></span> <span data-ttu-id="75b61-118">L'intestazione della pagina contiene pertanto l'ID di unità di allocazione errato e la pagina restituirà un corrispondente errore MSSQLServer_2533 in cui viene indicato l'ID di unità di allocazione a cui la pagina è effettivamente allocata.</span><span class="sxs-lookup"><span data-stu-id="75b61-118">Therefore, the header of the page contains the wrong allocation unit ID, and the page will have a matching MSSQLServer_2533 error that corresponds to the allocation unit ID to which the page is actually allocated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="75b61-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="75b61-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="75b61-120">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="75b61-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="75b61-121">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="75b61-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="75b61-122">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="75b61-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="75b61-123">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="75b61-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="75b61-124">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="75b61-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="75b61-125">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="75b61-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="75b61-126">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="75b61-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="75b61-127">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="75b61-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="75b61-128">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="75b61-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="75b61-129">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="75b61-129">Restore from Backup</span></span>  
 <span data-ttu-id="75b61-130">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="75b61-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="75b61-131">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="75b61-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="75b61-132">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="75b61-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="75b61-133">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="75b61-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="75b61-134">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="75b61-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="75b61-135">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="75b61-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="75b61-136">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="75b61-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="75b61-137">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="75b61-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="75b61-138">L'istruzione REPAIR ricompila l'indice se esistente.</span><span class="sxs-lookup"><span data-stu-id="75b61-138">REPAIR will rebuild the index if an index exists.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="75b61-139">L'esecuzione di REPAIR per l'errore [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) corrispondente dealloca la pagina prima della ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="75b61-139">Running REPAIR for the matching [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) error deallocates the page before the rebuild.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="75b61-140">L'operazione di correzione può comportare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="75b61-140">This repair may cause data loss.</span></span>  
  
  
