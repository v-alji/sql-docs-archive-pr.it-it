---
title: MSSQLSERVER_2512 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2512 (Database Engine error)
ms.assetid: 989b527f-5b02-403c-9b7f-51580f4e7688
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da121c8b49ab8290c494d33f0f2a0ba6fded9e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714392"
---
# <a name="mssqlserver_2512"></a><span data-ttu-id="b3c8b-102">MSSQLSERVER_2512</span><span class="sxs-lookup"><span data-stu-id="b3c8b-102">MSSQLSERVER_2512</span></span>
    
## <a name="details"></a><span data-ttu-id="b3c8b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b3c8b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b3c8b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b3c8b-104">Product Name</span></span>|<span data-ttu-id="b3c8b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3c8b-105">SQL Server</span></span>|  
|<span data-ttu-id="b3c8b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b3c8b-106">Event ID</span></span>|<span data-ttu-id="b3c8b-107">2512</span><span class="sxs-lookup"><span data-stu-id="b3c8b-107">2512</span></span>|  
|<span data-ttu-id="b3c8b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b3c8b-108">Event Source</span></span>|<span data-ttu-id="b3c8b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b3c8b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b3c8b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b3c8b-110">Component</span></span>|<span data-ttu-id="b3c8b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b3c8b-111">SQLEngine</span></span>|  
|<span data-ttu-id="b3c8b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b3c8b-112">Symbolic Name</span></span>|<span data-ttu-id="b3c8b-113">DBCC_DUPLICATE_KEYS</span><span class="sxs-lookup"><span data-stu-id="b3c8b-113">DBCC_DUPLICATE_KEYS</span></span>|  
|<span data-ttu-id="b3c8b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b3c8b-114">Message Text</span></span>|<span data-ttu-id="b3c8b-115">Errore di tabella: ID di oggetto O_ID, ID di indice I_ID, ID di partizione PN_ID, ID di unità di allocazione A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="b3c8b-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="b3c8b-116">Chiavi duplicate alla pagina ID1_P, slot SLOT1, e alla pagina ID2_P, slot SLOT2.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-116">Duplicate keys on page P_ID1 slot SLOT1 and page P_ID2 slot SLOT2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b3c8b-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b3c8b-117">Explanation</span></span>  
 <span data-ttu-id="b3c8b-118">I due slot specificati dispongono di chiavi identiche, inclusi gli `uniqueifiers`.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-118">The two specified slots have identical keys, including any `uniqueifiers`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b3c8b-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b3c8b-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b3c8b-120">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="b3c8b-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b3c8b-121">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b3c8b-122">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b3c8b-123">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b3c8b-124">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b3c8b-125">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b3c8b-126">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b3c8b-127">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b3c8b-128">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b3c8b-129">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="b3c8b-129">Restore from Backup</span></span>  
 <span data-ttu-id="b3c8b-130">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b3c8b-131">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b3c8b-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b3c8b-132">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="b3c8b-133">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="b3c8b-134">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b3c8b-135">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="b3c8b-136">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="b3c8b-137">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="b3c8b-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="b3c8b-138">Se il record è un record fantasma o se l'indice non è univoco, DBCC è in grado di risolvere questo problema ricompilando l'indice.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-138">If either record is a ghost or the index is nonunique, DBCC can repair this problem by rebuilding the index.</span></span> <span data-ttu-id="b3c8b-139">Altrimenti, se necessario, REPAIR eliminerà lo slot *SLOT2* nella pagina *P_ID2* o contrassegnerà lo slot come ghost.</span><span class="sxs-lookup"><span data-stu-id="b3c8b-139">Otherwise, if necessary, REPAIR will delete slot *SLOT2* on page *P_ID2* or mark the slot as a ghost.</span></span>  
  
  
