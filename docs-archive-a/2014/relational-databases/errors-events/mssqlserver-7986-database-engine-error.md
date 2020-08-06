---
title: MSSQLSERVER_7986 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7986 (Database Engine error)
ms.assetid: ae64276c-4e1e-4ef3-9ee9-ebeb2f61e565
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4f7d312987a2692c95f2cf6dbe0c86a4b2acbe6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718150"
---
# <a name="mssqlserver_7986"></a><span data-ttu-id="66754-102">MSSQLSERVER_7986</span><span class="sxs-lookup"><span data-stu-id="66754-102">MSSQLSERVER_7986</span></span>
    
## <a name="details"></a><span data-ttu-id="66754-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="66754-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66754-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="66754-104">Product Name</span></span>|<span data-ttu-id="66754-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="66754-105">SQL Server</span></span>|  
|<span data-ttu-id="66754-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="66754-106">Event ID</span></span>|<span data-ttu-id="66754-107">7986</span><span class="sxs-lookup"><span data-stu-id="66754-107">7986</span></span>|  
|<span data-ttu-id="66754-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="66754-108">Event Source</span></span>|<span data-ttu-id="66754-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="66754-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="66754-110">Componente</span><span class="sxs-lookup"><span data-stu-id="66754-110">Component</span></span>|<span data-ttu-id="66754-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="66754-111">SQLEngine</span></span>|  
|<span data-ttu-id="66754-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="66754-112">Symbolic Name</span></span>|<span data-ttu-id="66754-113">DBCC2_PRE_CHECKS_CROSS_OBJECT_LINKAGE</span><span class="sxs-lookup"><span data-stu-id="66754-113">DBCC2_PRE_CHECKS_CROSS_OBJECT_LINKAGE</span></span>|  
|<span data-ttu-id="66754-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="66754-114">Message Text</span></span>|<span data-ttu-id="66754-115">Controlli preliminari su tabella di sistema: per l'ID oggetto O_ID è definito un collegamento a catena tra oggetti.</span><span class="sxs-lookup"><span data-stu-id="66754-115">System table pre-checks: Object ID O_ID has cross-object chain linkage.</span></span> <span data-ttu-id="66754-116">La pagina ID1_P punta a ID2_P nell'ID di unità di allocazione ID1_A (dovrebbe essere ID2_A).</span><span class="sxs-lookup"><span data-stu-id="66754-116">Page P_ID1 points to P_ID2 in alloc unit ID A_ID1 (should be A_ID2).</span></span> <span data-ttu-id="66754-117">Istruzione di controllo interrotta a causa di un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="66754-117">Check statement terminated due to unrepairable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="66754-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="66754-118">Explanation</span></span>  
 <span data-ttu-id="66754-119">La prima fase dell'esecuzione di un comando DBCC CHECKDB consiste nell'eseguire controlli primitivi nelle pagine dei dati delle tabelle di sistema critiche.</span><span class="sxs-lookup"><span data-stu-id="66754-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="66754-120">Non è possibile correggere eventuali errori rilevati. DBCC CHECKDB verrà pertanto terminato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="66754-120">If any errors are found, they cannot be repaired; therefore, the DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="66754-121">Il puntatore di pagina successiva della pagina *P_ID1* nel livello dati dell'oggetto specificato punta alla pagina *P_ID2* di un oggetto diverso.</span><span class="sxs-lookup"><span data-stu-id="66754-121">The next page pointer of page *P_ID1* in the data level of the specified object points to a page, *P_ID2*, in a different object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66754-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="66754-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="66754-123">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="66754-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="66754-124">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="66754-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="66754-125">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="66754-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="66754-126">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="66754-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="66754-127">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="66754-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="66754-128">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="66754-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="66754-129">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="66754-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="66754-130">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="66754-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="66754-131">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="66754-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="66754-132">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="66754-132">Restore from Backup</span></span>  
 <span data-ttu-id="66754-133">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="66754-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="66754-134">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="66754-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="66754-135">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="66754-135">Not applicable.</span></span> <span data-ttu-id="66754-136">L'errore non può essere corretto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="66754-136">This error cannot be repaired automatically.</span></span> <span data-ttu-id="66754-137">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66754-137">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
