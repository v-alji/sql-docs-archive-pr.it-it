---
title: MSSQLSERVER_7984 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7984 (Database Engine error)
ms.assetid: e3192f56-e4e2-41da-b132-65f1e7540b1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7f92fe4f3751621e0cc636ffcd2d4de73b348d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635635"
---
# <a name="mssqlserver_7984"></a><span data-ttu-id="21972-102">MSSQLSERVER_7984</span><span class="sxs-lookup"><span data-stu-id="21972-102">MSSQLSERVER_7984</span></span>
    
## <a name="details"></a><span data-ttu-id="21972-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="21972-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21972-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="21972-104">Product Name</span></span>|<span data-ttu-id="21972-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="21972-105">SQL Server</span></span>|  
|<span data-ttu-id="21972-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="21972-106">Event ID</span></span>|<span data-ttu-id="21972-107">7984</span><span class="sxs-lookup"><span data-stu-id="21972-107">7984</span></span>|  
|<span data-ttu-id="21972-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="21972-108">Event Source</span></span>|<span data-ttu-id="21972-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="21972-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="21972-110">Componente</span><span class="sxs-lookup"><span data-stu-id="21972-110">Component</span></span>|<span data-ttu-id="21972-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="21972-111">SQLEngine</span></span>|  
|<span data-ttu-id="21972-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="21972-112">Symbolic Name</span></span>|<span data-ttu-id="21972-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span><span class="sxs-lookup"><span data-stu-id="21972-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span></span>|  
|<span data-ttu-id="21972-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="21972-114">Message Text</span></span>|<span data-ttu-id="21972-115">Controlli preliminari su tabella di sistema: ID oggetto O_ID.</span><span class="sxs-lookup"><span data-stu-id="21972-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="21972-116">Pagina P_ID con tipo imprevisto PAGETYPE.</span><span class="sxs-lookup"><span data-stu-id="21972-116">Page P_ID has unexpected page type PAGETYPE.</span></span> <span data-ttu-id="21972-117">Istruzione di controllo interrotta a causa di un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="21972-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="21972-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="21972-118">Explanation</span></span>  
 <span data-ttu-id="21972-119">Nel livello dati dell'oggetto specificato è stata trovata una pagina con un tipo diverso da DATA_PAGE.</span><span class="sxs-lookup"><span data-stu-id="21972-119">A page with a type other than DATA_PAGE was found in the data level of the specified object.</span></span> <span data-ttu-id="21972-120">L'errore viene generato durante la prima fase dei controlli del comando DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="21972-120">This error is raised during the first phase of the DBCC CHECKDB command checks.</span></span> <span data-ttu-id="21972-121">Durante tale fase, DBCC CHECKDB esegue controlli primitivi nelle pagine dei dati delle tabelle di base di sistema critiche.</span><span class="sxs-lookup"><span data-stu-id="21972-121">During this phase, DBCC CHECKDB performs primitive checks on the data pages of critical system base tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21972-122">Non è possibile correggere eventuali errori rilevati nelle tabelle di sistema. Il comando DBCC CHECKDB verrà pertanto terminato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="21972-122">If any errors are found in the system tables, the errors cannot be repaired; therefore, the DBCC CHECKDB command ends immediately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="21972-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="21972-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="21972-124">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="21972-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="21972-125">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="21972-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="21972-126">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="21972-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="21972-127">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="21972-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="21972-128">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="21972-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="21972-129">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="21972-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="21972-130">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="21972-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="21972-131">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="21972-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="21972-132">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="21972-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="21972-133">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="21972-133">Restore from Backup</span></span>  
 <span data-ttu-id="21972-134">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="21972-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="21972-135">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="21972-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="21972-136">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="21972-136">Not applicable.</span></span> <span data-ttu-id="21972-137">L'errore non può essere corretto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="21972-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="21972-138">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21972-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
