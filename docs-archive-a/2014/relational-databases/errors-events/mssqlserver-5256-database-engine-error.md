---
title: MSSQLSERVER_5256 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5256 (Database Engine error)
ms.assetid: 6fe254b4-2926-446f-8b20-0f1d921a4615
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9146b7744e78550463cbec4c05df5fd75a049898
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718162"
---
# <a name="mssqlserver_5256"></a><span data-ttu-id="b2959-102">MSSQLSERVER_5256</span><span class="sxs-lookup"><span data-stu-id="b2959-102">MSSQLSERVER_5256</span></span>
    
## <a name="details"></a><span data-ttu-id="b2959-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b2959-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2959-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b2959-104">Product Name</span></span>|<span data-ttu-id="b2959-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2959-105">SQL Server</span></span>|  
|<span data-ttu-id="b2959-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b2959-106">Event ID</span></span>|<span data-ttu-id="b2959-107">5256</span><span class="sxs-lookup"><span data-stu-id="b2959-107">5256</span></span>|  
|<span data-ttu-id="b2959-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b2959-108">Event Source</span></span>|<span data-ttu-id="b2959-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b2959-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b2959-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b2959-110">Component</span></span>|<span data-ttu-id="b2959-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b2959-111">SQLEngine</span></span>|  
|<span data-ttu-id="b2959-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b2959-112">Symbolic Name</span></span>|<span data-ttu-id="b2959-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="b2959-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="b2959-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b2959-114">Message Text</span></span>|<span data-ttu-id="b2959-115">Errore di tabella: ID di pagina non corretto nell'intestazione di pagina dell'ID di unità di allocazione A_ID, pagina P_ID1.</span><span class="sxs-lookup"><span data-stu-id="b2959-115">Table error: alloc unit ID A_ID, page P_ID1 contains an incorrect page ID in its page header.</span></span> <span data-ttu-id="b2959-116">PageId nell'intestazione di pagina = P_ID2.</span><span class="sxs-lookup"><span data-stu-id="b2959-116">The PageId in the page header = P_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b2959-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b2959-117">Explanation</span></span>  
 <span data-ttu-id="b2959-118">L'intestazione della pagina *P_ID1* contiene un ID di pagina non corretto, *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="b2959-118">The page header of page *P_ID1* contains an incorrect page ID, *P_ID2*.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2959-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b2959-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b2959-120">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="b2959-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b2959-121">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="b2959-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b2959-122">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="b2959-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b2959-123">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="b2959-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b2959-124">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="b2959-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b2959-125">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="b2959-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b2959-126">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="b2959-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b2959-127">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="b2959-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b2959-128">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b2959-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b2959-129">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="b2959-129">Restore from Backup</span></span>  
 <span data-ttu-id="b2959-130">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="b2959-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b2959-131">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b2959-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b2959-132">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="b2959-132">Not applicable.</span></span> <span data-ttu-id="b2959-133">Impossibile correggere questo errore.</span><span class="sxs-lookup"><span data-stu-id="b2959-133">This error cannot be repaired.</span></span> <span data-ttu-id="b2959-134">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2959-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
