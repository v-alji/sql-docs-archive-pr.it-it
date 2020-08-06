---
title: MSSQLSERVER_2515 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2515 (Database Engine error)
ms.assetid: af93aa29-70c9-4923-90af-aafadb20c1c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73b2d8b8ff01b97428ba6149f537d96044c6ae3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713199"
---
# <a name="mssqlserver_2515"></a><span data-ttu-id="c3bef-102">MSSQLSERVER_2515</span><span class="sxs-lookup"><span data-stu-id="c3bef-102">MSSQLSERVER_2515</span></span>
    
## <a name="details"></a><span data-ttu-id="c3bef-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c3bef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3bef-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="c3bef-104">Product Name</span></span>|<span data-ttu-id="c3bef-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c3bef-105">SQL Server</span></span>|  
|<span data-ttu-id="c3bef-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="c3bef-106">Event ID</span></span>|<span data-ttu-id="c3bef-107">2515</span><span class="sxs-lookup"><span data-stu-id="c3bef-107">2515</span></span>|  
|<span data-ttu-id="c3bef-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="c3bef-108">Event Source</span></span>|<span data-ttu-id="c3bef-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c3bef-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c3bef-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c3bef-110">Component</span></span>|<span data-ttu-id="c3bef-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c3bef-111">SQLEngine</span></span>|  
|<span data-ttu-id="c3bef-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="c3bef-112">Symbolic Name</span></span>|<span data-ttu-id="c3bef-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span><span class="sxs-lookup"><span data-stu-id="c3bef-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span></span>|  
|<span data-ttu-id="c3bef-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="c3bef-114">Message Text</span></span>|<span data-ttu-id="c3bef-115">La pagina ID_P, con ID di oggetto ID_O, ID di indice ID_I, ID di partizione ID_PN e ID di unità di allocazione ID_A (tipo TIPO) è stata modificata ma non è contrassegnata come modificata nella mappa di bit del backup differenziale.</span><span class="sxs-lookup"><span data-stu-id="c3bef-115">Page P_ID, object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID type TYPE has been modified but is not marked modified in the differential backup bitmap.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c3bef-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="c3bef-116">Explanation</span></span>  
 <span data-ttu-id="c3bef-117">La pagina specificata ha un numero di sequenza del file di log (LSN) superiore all'LSN di riferimento del backup differenziale nella gestione dei backup del database oppure all'LSN di base differenziale nel blocco di controllo file, a seconda di quello più recente.</span><span class="sxs-lookup"><span data-stu-id="c3bef-117">The page specified has a log sequence number (LSN) that is higher than the differential reference LSN in the BackupManager of the database, or the differential base LSN in the file control block of the file, whichever is more recent.</span></span> <span data-ttu-id="c3bef-118">La pagina non viene tuttavia contrassegnata come modificata nella mappa di bit del backup differenziale.</span><span class="sxs-lookup"><span data-stu-id="c3bef-118">However, the page is not marked as changed in the differential backup bitmap.</span></span>  
  
 <span data-ttu-id="c3bef-119">Dato che questo controllo viene eseguito solo quando è noto che la mappa di bit differenziale è priva di errori, verrà segnalata solo una pagina per database.</span><span class="sxs-lookup"><span data-stu-id="c3bef-119">Only one page per database will be reported, because this check is only performed when the differential bitmap is known to be error free.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c3bef-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="c3bef-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="c3bef-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="c3bef-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="c3bef-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="c3bef-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="c3bef-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="c3bef-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="c3bef-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="c3bef-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="c3bef-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="c3bef-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="c3bef-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="c3bef-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="c3bef-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="c3bef-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="c3bef-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="c3bef-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="c3bef-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c3bef-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="c3bef-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="c3bef-130">Restore from Backup</span></span>  
 <span data-ttu-id="c3bef-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="c3bef-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="c3bef-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="c3bef-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="c3bef-133">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="c3bef-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="c3bef-134">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="c3bef-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="c3bef-135">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="c3bef-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="c3bef-136">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c3bef-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="c3bef-137">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="c3bef-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="c3bef-138">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="c3bef-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="c3bef-139">L'esecuzione di REPAIR invalida la mappa di bit differenziale.</span><span class="sxs-lookup"><span data-stu-id="c3bef-139">Running REPAIR will invalidate the differential bitmap.</span></span> <span data-ttu-id="c3bef-140">Non è possibile eseguire un backup differenziale fino a che viene eseguito un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="c3bef-140">You cannot perform a differential backup until a full database backup is taken.</span></span> <span data-ttu-id="c3bef-141">Il backup completo del database offre un riferimento per la ricompilazione della mappa di bit differenziale.</span><span class="sxs-lookup"><span data-stu-id="c3bef-141">The full database backup provides a baseline for the differential bitmap to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3bef-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3bef-142">See Also</span></span>  
 <span data-ttu-id="c3bef-143">[Creare un backup completo del database &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c3bef-143">[Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="c3bef-144">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="c3bef-144">MSSQLSERVER_2516</span></span>](mssqlserver-2516-database-engine-error.md)  
  
  
