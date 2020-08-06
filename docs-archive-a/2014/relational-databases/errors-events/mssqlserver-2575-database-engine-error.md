---
title: MSSQLSERVER_2575 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2575 (Database Engine error)
ms.assetid: 92dfe449-a122-4730-942b-e1d319862d20
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 461d2b57b5ace98ca624f8dc3717c98f3e9e4d67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624230"
---
# <a name="mssqlserver_2575"></a><span data-ttu-id="f38b1-102">MSSQLSERVER_2575</span><span class="sxs-lookup"><span data-stu-id="f38b1-102">MSSQLSERVER_2575</span></span>
    
## <a name="details"></a><span data-ttu-id="f38b1-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f38b1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f38b1-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f38b1-104">Product Name</span></span>|<span data-ttu-id="f38b1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f38b1-105">SQL Server</span></span>|  
|<span data-ttu-id="f38b1-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f38b1-106">Event ID</span></span>|<span data-ttu-id="f38b1-107">2575</span><span class="sxs-lookup"><span data-stu-id="f38b1-107">2575</span></span>|  
|<span data-ttu-id="f38b1-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f38b1-108">Event Source</span></span>|<span data-ttu-id="f38b1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f38b1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f38b1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f38b1-110">Component</span></span>|<span data-ttu-id="f38b1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f38b1-111">SQLEngine</span></span>|  
|<span data-ttu-id="f38b1-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f38b1-112">Symbolic Name</span></span>|<span data-ttu-id="f38b1-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="f38b1-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="f38b1-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f38b1-114">Message Text</span></span>|<span data-ttu-id="f38b1-115">Il puntatore di pagina successiva della pagina IAM (Index Allocation Map) P_ID2 nell'oggetto con ID O_ID, ID di indice I_ID, ID di partizione PN_ID, ID di unità di allocazione A_ID (tipo TYPE) punta alla pagina IAM P_ID1, che non è stata rilevata durante l'analisi.</span><span class="sxs-lookup"><span data-stu-id="f38b1-115">IAM page P_ID1 is pointed to by the next pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f38b1-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f38b1-116">Explanation</span></span>  
 <span data-ttu-id="f38b1-117">Per l'indice specificato è stata individuata una pagina IAM (Index Allocation Map). Il puntatore di pagina successiva di tale pagina punta tuttavia a una pagina IAM che non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="f38b1-117">An Index Allocation Map (IAM) page was found for the specified index; however, the IAM page for its next-page pointer was not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f38b1-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f38b1-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="f38b1-119">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="f38b1-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="f38b1-120">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="f38b1-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="f38b1-121">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="f38b1-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="f38b1-122">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="f38b1-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="f38b1-123">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="f38b1-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="f38b1-124">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="f38b1-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="f38b1-125">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="f38b1-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="f38b1-126">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="f38b1-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="f38b1-127">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f38b1-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="f38b1-128">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="f38b1-128">Restore from Backup</span></span>  
 <span data-ttu-id="f38b1-129">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="f38b1-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="f38b1-130">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="f38b1-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="f38b1-131">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="f38b1-131">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="f38b1-132">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="f38b1-132">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="f38b1-133">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="f38b1-133">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f38b1-134">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="f38b1-134">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="f38b1-135">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="f38b1-135">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="f38b1-136">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="f38b1-136">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="f38b1-137">L'istruzione DBCC ricompila l'indice.</span><span class="sxs-lookup"><span data-stu-id="f38b1-137">DBCC will rebuild the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f38b1-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f38b1-138">See Also</span></span>  
 [<span data-ttu-id="f38b1-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f38b1-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
