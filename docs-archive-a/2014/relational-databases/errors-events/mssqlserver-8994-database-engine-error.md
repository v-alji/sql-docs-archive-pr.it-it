---
title: MSSQLSERVER_8994 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8994 (Database Engine error)
ms.assetid: 8f4b0e2f-04c0-46e4-9208-20a7085d7a1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0bcc0b1db100b70390c09e9c825dbfd068d968af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624221"
---
# <a name="mssqlserver_8994"></a><span data-ttu-id="94bc9-102">MSSQLSERVER_8994</span><span class="sxs-lookup"><span data-stu-id="94bc9-102">MSSQLSERVER_8994</span></span>
    
## <a name="details"></a><span data-ttu-id="94bc9-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="94bc9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="94bc9-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="94bc9-104">Product Name</span></span>|<span data-ttu-id="94bc9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="94bc9-105">SQL Server</span></span>|  
|<span data-ttu-id="94bc9-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="94bc9-106">Event ID</span></span>|<span data-ttu-id="94bc9-107">8994</span><span class="sxs-lookup"><span data-stu-id="94bc9-107">8994</span></span>|  
|<span data-ttu-id="94bc9-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="94bc9-108">Event Source</span></span>|<span data-ttu-id="94bc9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="94bc9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="94bc9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="94bc9-110">Component</span></span>|<span data-ttu-id="94bc9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="94bc9-111">SQLEngine</span></span>|  
|<span data-ttu-id="94bc9-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="94bc9-112">Symbolic Name</span></span>|<span data-ttu-id="94bc9-113">DBCC3_MISSING_FORWARDING_ROW</span><span class="sxs-lookup"><span data-stu-id="94bc9-113">DBCC3_MISSING_FORWARDING_ROW</span></span>|  
|<span data-ttu-id="94bc9-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="94bc9-114">Message Text</span></span>|<span data-ttu-id="94bc9-115">La pagina della riga da inoltrare P_ID2, slot S_ID2 deve puntare all'ID di oggetto O_ID, nella pagina della riga inoltrata P_ID1, slot S_ID1.</span><span class="sxs-lookup"><span data-stu-id="94bc9-115">Object ID O_ID, forwarded row page P_ID1, slot S_ID1 should be pointed to by forwarding row page P_ID2, slot S_ID2.</span></span> <span data-ttu-id="94bc9-116">Impossibile trovare la riga da inoltrare.</span><span class="sxs-lookup"><span data-stu-id="94bc9-116">Did not encounter forwarding row.</span></span> <span data-ttu-id="94bc9-117">Possibile errore di allocazione.</span><span class="sxs-lookup"><span data-stu-id="94bc9-117">Possible allocation error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="94bc9-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="94bc9-118">Explanation</span></span>  
 <span data-ttu-id="94bc9-119">Manca la riga da inoltrare che dovrebbe puntare a una riga inoltrata in un heap.</span><span class="sxs-lookup"><span data-stu-id="94bc9-119">A forwarded row in a heap is missing the forwarding row that should point to it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="94bc9-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="94bc9-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="94bc9-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="94bc9-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="94bc9-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="94bc9-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="94bc9-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="94bc9-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="94bc9-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="94bc9-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="94bc9-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="94bc9-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="94bc9-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="94bc9-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="94bc9-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="94bc9-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="94bc9-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="94bc9-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="94bc9-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="94bc9-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="94bc9-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="94bc9-130">Restore from Backup</span></span>  
 <span data-ttu-id="94bc9-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="94bc9-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="94bc9-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="94bc9-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="94bc9-133">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="94bc9-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="94bc9-134">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="94bc9-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="94bc9-135">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="94bc9-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="94bc9-136">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="94bc9-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="94bc9-137">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="94bc9-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="94bc9-138">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="94bc9-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="94bc9-139">La riga inoltrata verrà convertita in una riga di dati regolare.</span><span class="sxs-lookup"><span data-stu-id="94bc9-139">The forwarded row will be converted to a regular data row.</span></span>  
  
  
