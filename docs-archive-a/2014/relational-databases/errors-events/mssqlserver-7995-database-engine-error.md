---
title: MSSQLSERVER_7995 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7995 (Database Engine error)
ms.assetid: af6d6322-3cba-43d8-be97-e6ef15f8c933
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c65cf2b16c4d7a0dcf40272f8280205a111d08e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629398"
---
# <a name="mssqlserver_7995"></a><span data-ttu-id="ab812-102">MSSQLSERVER_7995</span><span class="sxs-lookup"><span data-stu-id="ab812-102">MSSQLSERVER_7995</span></span>
    
## <a name="details"></a><span data-ttu-id="ab812-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ab812-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab812-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ab812-104">Product Name</span></span>|<span data-ttu-id="ab812-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab812-105">SQL Server</span></span>|  
|<span data-ttu-id="ab812-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="ab812-106">Event ID</span></span>|<span data-ttu-id="ab812-107">7995</span><span class="sxs-lookup"><span data-stu-id="ab812-107">7995</span></span>|  
|<span data-ttu-id="ab812-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="ab812-108">Event Source</span></span>|<span data-ttu-id="ab812-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ab812-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ab812-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ab812-110">Component</span></span>|<span data-ttu-id="ab812-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ab812-111">SQLEngine</span></span>|  
|<span data-ttu-id="ab812-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="ab812-112">Symbolic Name</span></span>|<span data-ttu-id="ab812-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="ab812-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span></span>|  
|<span data-ttu-id="ab812-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ab812-114">Message Text</span></span>|<span data-ttu-id="ab812-115">Database 'NOMEDB': impossibile eseguire ulteriori elaborazioni DBCC NOMECONTROLLO a causa di errori di consistenza nei cataloghi di sistema.</span><span class="sxs-lookup"><span data-stu-id="ab812-115">Database 'DBNAME': consistency errors in system catalogs prevent further DBCC CHECKNAME processing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ab812-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ab812-116">Explanation</span></span>  
 <span data-ttu-id="ab812-117">Il processo DBCC CHECKDB è composto dalle tre fasi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab812-117">The DBCC CHECKDB process consists of the following three stages:</span></span>  
  
1.  <span data-ttu-id="ab812-118">Controlli di allocazione,</span><span class="sxs-lookup"><span data-stu-id="ab812-118">Allocation checks.</span></span> <span data-ttu-id="ab812-119">che equivalgono all'esecuzione di DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="ab812-119">This is equivalent to running DBCC CHECKALLOC.</span></span>  
  
2.  <span data-ttu-id="ab812-120">Controlli di consistenza delle tabelle di sistema,</span><span class="sxs-lookup"><span data-stu-id="ab812-120">System tables consistency checks.</span></span> <span data-ttu-id="ab812-121">che equivalgono all'esecuzione di DBCC CHECKTABLE in un elenco di piccole dimensioni di tabelle di base di sistema necessarie.</span><span class="sxs-lookup"><span data-stu-id="ab812-121">This is equivalent to running DBCC CHECKTABLE on a small list of necessary system base tables.</span></span>  
  
3.  <span data-ttu-id="ab812-122">Controllo di consistenza dei database completi.</span><span class="sxs-lookup"><span data-stu-id="ab812-122">Complete database consistency checks.</span></span>  
  
 <span data-ttu-id="ab812-123">L'errore MSSQLEngine_7995 viene generato nella fase 2 e indica che DBCC CHECKDB ha rilevato errori che il comando non è in grado di correggere oppure che l'istruzione REPAIR non è stata specificata.</span><span class="sxs-lookup"><span data-stu-id="ab812-123">MSSQLEngine_7995 is raised in stage 2 to indicate that DBCC CHECKDB has found errors that the command cannot repair or that REPAIR has not been specified.</span></span> <span data-ttu-id="ab812-124">DBCC CHECKDB non è in grado di continuare con la fase 3 poiché le tabelle di base di sistema in questione archiviano i metadati di tutti gli oggetti nel database oppure sono danneggiate.</span><span class="sxs-lookup"><span data-stu-id="ab812-124">DBCC CHECKDB cannot continue with stage 3 because either the system base tables in question store the metadata for all objects in the database or the system base tables are corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab812-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="ab812-125">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="ab812-126">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="ab812-126">Look for Hardware Failure</span></span>  
 <span data-ttu-id="ab812-127">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="ab812-127">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="ab812-128">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="ab812-128">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="ab812-129">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="ab812-129">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="ab812-130">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="ab812-130">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="ab812-131">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="ab812-131">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="ab812-132">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="ab812-132">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="ab812-133">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="ab812-133">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="ab812-134">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ab812-134">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="ab812-135">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="ab812-135">Restore from Backup</span></span>  
 <span data-ttu-id="ab812-136">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="ab812-136">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="ab812-137">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="ab812-137">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="ab812-138">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="ab812-138">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="ab812-139">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="ab812-139">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="ab812-140">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="ab812-140">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="ab812-141">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="ab812-141">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="ab812-142">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="ab812-142">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="ab812-143">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="ab812-143">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="ab812-144">Esaminare l'elenco di errori per vedere quale effetto avrà l'istruzione REPAIR su ognuno di loro.</span><span class="sxs-lookup"><span data-stu-id="ab812-144">Examine the list of errors to see what REPAIR will do for each.</span></span>  
  
  
