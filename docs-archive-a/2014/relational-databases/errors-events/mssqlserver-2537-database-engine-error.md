---
title: MSSQLSERVER_2537 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2537 (Database Engine error)
ms.assetid: 0af6ff69-d75a-4c39-8da2-9bd0695277c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c227867bac5a0ea5789ba653414444d011e5910d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636127"
---
# <a name="mssqlserver_2537"></a><span data-ttu-id="4457c-102">MSSQLSERVER_2537</span><span class="sxs-lookup"><span data-stu-id="4457c-102">MSSQLSERVER_2537</span></span>
    
## <a name="details"></a><span data-ttu-id="4457c-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4457c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4457c-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="4457c-104">Product Name</span></span>|<span data-ttu-id="4457c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4457c-105">SQL Server</span></span>|  
|<span data-ttu-id="4457c-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="4457c-106">Event ID</span></span>|<span data-ttu-id="4457c-107">2537</span><span class="sxs-lookup"><span data-stu-id="4457c-107">2537</span></span>|  
|<span data-ttu-id="4457c-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="4457c-108">Event Source</span></span>|<span data-ttu-id="4457c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4457c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4457c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4457c-110">Component</span></span>|<span data-ttu-id="4457c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4457c-111">SQLEngine</span></span>|  
|<span data-ttu-id="4457c-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="4457c-112">Symbolic Name</span></span>|<span data-ttu-id="4457c-113">DBCC_RECORD_CHECK_FAILED</span><span class="sxs-lookup"><span data-stu-id="4457c-113">DBCC_RECORD_CHECK_FAILED</span></span>|  
|<span data-ttu-id="4457c-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="4457c-114">Message Text</span></span>|<span data-ttu-id="4457c-115">Errore di tabella: ID di oggetto O_ID, ID di indice I_ID, ID di partizione PN_ID, ID di unità di allocazione A_ID (tipo TYPE), pagina P_ID, riga ROW_ID.</span><span class="sxs-lookup"><span data-stu-id="4457c-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page P_ID, row ROW_ID.</span></span> <span data-ttu-id="4457c-116">Controllo del record (CHECK_TEXT) non riuscito.</span><span class="sxs-lookup"><span data-stu-id="4457c-116">Record check (CHECK_TEXT) failed.</span></span> <span data-ttu-id="4457c-117">Valori: VALUE1 e VALUE2.</span><span class="sxs-lookup"><span data-stu-id="4457c-117">Values are VALUE1 and VALUE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4457c-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="4457c-118">Explanation</span></span>  
 <span data-ttu-id="4457c-119">La riga ROW_ID (o una colonna della riga) non ha superato il test o la condizione descritta da CHECK_TEXT.</span><span class="sxs-lookup"><span data-stu-id="4457c-119">The row ROW_ID (or a column in the row) failed the test or condition described by CHECK_TEXT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4457c-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="4457c-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4457c-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="4457c-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4457c-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="4457c-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4457c-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="4457c-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4457c-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="4457c-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4457c-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="4457c-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4457c-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="4457c-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4457c-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="4457c-127">If you suspect that write-caching is the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4457c-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="4457c-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4457c-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4457c-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4457c-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="4457c-130">Restore from Backup</span></span>  
 <span data-ttu-id="4457c-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="4457c-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4457c-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4457c-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4457c-133">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="4457c-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="4457c-134">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="4457c-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="4457c-135">Eseguire quindi DBCC CHECKDB con la clausola REPAIR consigliata.</span><span class="sxs-lookup"><span data-stu-id="4457c-135">Then, run DBCC CHECKDB with the recommended REPAIR clause.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4457c-136">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4457c-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="4457c-137">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="4457c-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="4457c-138">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="4457c-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="4457c-139">L'istruzione REPAIR ricompila l'indice se esistente.</span><span class="sxs-lookup"><span data-stu-id="4457c-139">REPAIR will rebuild the index if an index exists.</span></span>  
  
 <span data-ttu-id="4457c-140">**Attenzione**: l'operazione di correzione può comportare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="4457c-140">**Caution** This repair may cause data loss.</span></span>  
  
  
