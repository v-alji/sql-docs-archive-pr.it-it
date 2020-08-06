---
title: MSSQLSERVER_7988 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7988 (Database Engine error)
ms.assetid: 29b967b8-de30-4618-99a8-8b1155e69026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 984cb03aeb5feaa230762e200304f16cd8c5df08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715299"
---
# <a name="mssqlserver_7988"></a><span data-ttu-id="06a17-102">MSSQLSERVER_7988</span><span class="sxs-lookup"><span data-stu-id="06a17-102">MSSQLSERVER_7988</span></span>
    
## <a name="details"></a><span data-ttu-id="06a17-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="06a17-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06a17-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="06a17-104">Product Name</span></span>|<span data-ttu-id="06a17-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="06a17-105">SQL Server</span></span>|  
|<span data-ttu-id="06a17-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="06a17-106">Event ID</span></span>|<span data-ttu-id="06a17-107">7988</span><span class="sxs-lookup"><span data-stu-id="06a17-107">7988</span></span>|  
|<span data-ttu-id="06a17-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="06a17-108">Event Source</span></span>|<span data-ttu-id="06a17-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="06a17-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="06a17-110">Componente</span><span class="sxs-lookup"><span data-stu-id="06a17-110">Component</span></span>|<span data-ttu-id="06a17-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="06a17-111">SQLEngine</span></span>|  
|<span data-ttu-id="06a17-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="06a17-112">Symbolic Name</span></span>|<span data-ttu-id="06a17-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span><span class="sxs-lookup"><span data-stu-id="06a17-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span></span>|  
|<span data-ttu-id="06a17-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="06a17-114">Message Text</span></span>|<span data-ttu-id="06a17-115">Controlli preliminari su tabella di sistema: ID oggetto O_ID.</span><span class="sxs-lookup"><span data-stu-id="06a17-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="06a17-116">Rilevato ciclo nella catena di dati in P_ID.</span><span class="sxs-lookup"><span data-stu-id="06a17-116">Loop in data chain detected at P_ID.</span></span> <span data-ttu-id="06a17-117">Istruzione di controllo interrotta a causa di un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="06a17-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="06a17-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="06a17-118">Explanation</span></span>  
 <span data-ttu-id="06a17-119">La prima fase dell'esecuzione di un comando DBCC CHECKDB consiste nell'eseguire controlli primitivi nelle pagine dei dati delle tabelle di sistema critiche.</span><span class="sxs-lookup"><span data-stu-id="06a17-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="06a17-120">Non è possibile correggere eventuali errori rilevati. DBCC CHECKDB verrà pertanto terminato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="06a17-120">If any errors are found, they cannot be repaired; therefore, DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="06a17-121">Viene rilevato un ciclo di collegamento delle pagine nella pagina *P_ID*.</span><span class="sxs-lookup"><span data-stu-id="06a17-121">A page linkage loop has been detected on page *P_ID*.</span></span> <span data-ttu-id="06a17-122">Tale ciclo si verifica quando i puntatori di pagina successiva di una pagina tornano infine alla pagina specificata.</span><span class="sxs-lookup"><span data-stu-id="06a17-122">A page linkage loop occurs when the next page pointers from a page eventually return to the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06a17-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="06a17-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="06a17-124">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="06a17-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="06a17-125">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="06a17-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="06a17-126">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="06a17-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="06a17-127">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="06a17-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="06a17-128">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="06a17-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="06a17-129">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="06a17-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="06a17-130">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="06a17-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="06a17-131">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="06a17-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="06a17-132">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="06a17-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="06a17-133">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="06a17-133">Restore from Backup</span></span>  
 <span data-ttu-id="06a17-134">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="06a17-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="06a17-135">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="06a17-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="06a17-136">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="06a17-136">Not applicable.</span></span> <span data-ttu-id="06a17-137">L'errore non può essere corretto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="06a17-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="06a17-138">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06a17-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
