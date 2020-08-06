---
title: MSSQLSERVER_5228 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5228 (Database Engine error)
ms.assetid: 5e83c617-4aa2-4755-bcc5-a798c46b97e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eef59e62f00a44aad7bfefb1719a6d8d2b3d0290
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624226"
---
# <a name="mssqlserver_5228"></a><span data-ttu-id="dc9c2-102">MSSQLSERVER_5228</span><span class="sxs-lookup"><span data-stu-id="dc9c2-102">MSSQLSERVER_5228</span></span>
    
## <a name="details"></a><span data-ttu-id="dc9c2-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dc9c2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc9c2-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="dc9c2-104">Product Name</span></span>|<span data-ttu-id="dc9c2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc9c2-105">SQL Server</span></span>|  
|<span data-ttu-id="dc9c2-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="dc9c2-106">Event ID</span></span>|<span data-ttu-id="dc9c2-107">5228</span><span class="sxs-lookup"><span data-stu-id="dc9c2-107">5228</span></span>|  
|<span data-ttu-id="dc9c2-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="dc9c2-108">Event Source</span></span>|<span data-ttu-id="dc9c2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dc9c2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dc9c2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dc9c2-110">Component</span></span>|<span data-ttu-id="dc9c2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dc9c2-111">SQLEngine</span></span>|  
|<span data-ttu-id="dc9c2-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="dc9c2-112">Symbolic Name</span></span>|<span data-ttu-id="dc9c2-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span><span class="sxs-lookup"><span data-stu-id="dc9c2-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span></span>|  
|<span data-ttu-id="dc9c2-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="dc9c2-114">Message Text</span></span>|<span data-ttu-id="dc9c2-115">Errore di tabella: ID oggetto O_ID, ID indice I_ID, ID partizione PN_ID, ID unità di allocazione A_ID (tipo TYPE), pagina PG_ID, riga R_ID.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page PG_ID, row R_ID.</span></span> <span data-ttu-id="dc9c2-116">DBCC ha rilevato una pulizia incompleta causata da un'operazione di compilazione di un indice online.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-116">DBCC detected incomplete cleanup from an online index build operation.</span></span> <span data-ttu-id="dc9c2-117">Valore della colonna di elenco degli elementi da eliminare VALUE.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-117">(Antimatter column value is VALUE.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dc9c2-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="dc9c2-118">Explanation</span></span>  
 <span data-ttu-id="dc9c2-119">È stata rilevata una build di un indice online incompleta per l'oggetto *O_ID*, indice *I_ID* e partizione *PN_ID*.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-119">An unfinished online index build was detected for object *O_ID*, index *I_ID*, and partition *PN_ID*.</span></span> <span data-ttu-id="dc9c2-120">Tale evento è dimostrato dalla presenza di una colonna di elenco degli elementi da eliminare nella riga *R_ID*.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-120">This is manifested by the presence of an antimatter column on the row *R_ID*.</span></span> <span data-ttu-id="dc9c2-121">Questa colonna viene utilizzata durante la riconciliazione di record di più origini per la compilazione di un indice online.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-121">An antimatter column is used when reconciling records from multiple sources during an online index build.</span></span> <span data-ttu-id="dc9c2-122">Nel messaggio di errore viene inoltre indicato il valore della colonna di elenco degli elementi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-122">The error message also indicates the value of the antimatter column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc9c2-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="dc9c2-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="dc9c2-124">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="dc9c2-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="dc9c2-125">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="dc9c2-126">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="dc9c2-127">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="dc9c2-128">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="dc9c2-129">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="dc9c2-130">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="dc9c2-131">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="dc9c2-132">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="dc9c2-133">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="dc9c2-133">Restore from Backup</span></span>  
 <span data-ttu-id="dc9c2-134">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="dc9c2-135">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="dc9c2-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="dc9c2-136">Se non è disponibile un backup valido, eseguire DBCC CHECKDB senza la clausola REPAIR per determinare l'entità del danno.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-136">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="dc9c2-137">Verrà automaticamente suggerita la clausola REPAIR da usare.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-137">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="dc9c2-138">Eseguire quindi DBCC CHECKDB con la clausola REPAIR appropriata per correggere il database.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-138">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="dc9c2-139">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-139">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="dc9c2-140">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-140">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="dc9c2-141">Risultati dell'esecuzione delle opzioni REPAIR</span><span class="sxs-lookup"><span data-stu-id="dc9c2-141">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="dc9c2-142">L'esecuzione di REPAIR comporta la ricompilazione dell'indice specificato e di tutti gli indici dipendenti.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-142">Running REPAIR will cause the specified index and all its dependent indexes to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc9c2-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc9c2-143">See Also</span></span>  
 [<span data-ttu-id="dc9c2-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dc9c2-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
