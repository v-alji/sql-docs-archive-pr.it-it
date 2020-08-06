---
title: MSSQLSERVER_2579 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2579 (Database Engine error)
ms.assetid: 8f929d69-8eb4-4fe9-be52-b9680a7820db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e68cd090ff9d20b14b3456dcda66496fc2bc02d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636115"
---
# <a name="mssqlserver_2579"></a><span data-ttu-id="2ed2e-102">MSSQLSERVER_2579</span><span class="sxs-lookup"><span data-stu-id="2ed2e-102">MSSQLSERVER_2579</span></span>
    
## <a name="details"></a><span data-ttu-id="2ed2e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2ed2e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ed2e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="2ed2e-104">Product Name</span></span>|<span data-ttu-id="2ed2e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ed2e-105">SQL Server</span></span>|  
|<span data-ttu-id="2ed2e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="2ed2e-106">Event ID</span></span>|<span data-ttu-id="2ed2e-107">2579</span><span class="sxs-lookup"><span data-stu-id="2ed2e-107">2579</span></span>|  
|<span data-ttu-id="2ed2e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="2ed2e-108">Event Source</span></span>|<span data-ttu-id="2ed2e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2ed2e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2ed2e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2ed2e-110">Component</span></span>|<span data-ttu-id="2ed2e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2ed2e-111">SQLEngine</span></span>|  
|<span data-ttu-id="2ed2e-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="2ed2e-112">Symbolic Name</span></span>|<span data-ttu-id="2ed2e-113">DBCC_EXTENT_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="2ed2e-113">DBCC_EXTENT_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="2ed2e-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="2ed2e-114">Message Text</span></span>|<span data-ttu-id="2ed2e-115">Errore di tabella: l'extent ID_P nell'oggetto con ID ID_O, ID di indice ID_I, ID di partizione ID_PN, ID di unità di allocazione ID_A (tipo TYPE) è oltre l'intervallo consentito per questo database.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-115">Table error: Extent P_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) is beyond the range of this database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2ed2e-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="2ed2e-116">Explanation</span></span>  
 <span data-ttu-id="2ed2e-117">*P_ID* è l'ID di pagina del form *(filenum:pageinfile)* .</span><span class="sxs-lookup"><span data-stu-id="2ed2e-117">*P_ID* is a PageID of the form *(filenum:pageinfile)*.</span></span> <span data-ttu-id="2ed2e-118">Il valore *pageinfile* di questo extent è maggiore della dimensione fisica del file (*filenum)* del database.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-118">The *pageinfile* of this extent is greater than the physical size of the file (*filenum)* of the database.</span></span> <span data-ttu-id="2ed2e-119">L'extent è contrassegnato per l'allocazione in una pagina IAM con l'ID di unità di allocazione indicato.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-119">The extent is marked as being allocated in an IAM page for the indicated allocation unit ID.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ed2e-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="2ed2e-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="2ed2e-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="2ed2e-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="2ed2e-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="2ed2e-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="2ed2e-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="2ed2e-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="2ed2e-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="2ed2e-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="2ed2e-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="2ed2e-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="2ed2e-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="2ed2e-130">Restore from Backup</span></span>  
 <span data-ttu-id="2ed2e-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="2ed2e-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="2ed2e-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="2ed2e-133">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="2ed2e-134">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="2ed2e-135">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2ed2e-136">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="2ed2e-137">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="2ed2e-138">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="2ed2e-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="2ed2e-139">L'esecuzione dell'istruzione REPAIR determina la deallocazione dell'extent dalla pagina IAM.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-139">Running REPAIR will cause the extent to be deallocated from the IAM page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2ed2e-140">L'operazione di correzione può comportare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="2ed2e-140">This repair may cause data loss.</span></span>  
  
  
