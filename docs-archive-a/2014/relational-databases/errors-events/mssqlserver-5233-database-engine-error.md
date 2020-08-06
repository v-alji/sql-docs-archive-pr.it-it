---
title: MSSQLSERVER_5233 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5233 (Database Engine error)
ms.assetid: 7a855afa-2d3b-49b7-adef-197b99fc98b1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0a5e2c603652534a6d3093a01da0a926a7195954
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636099"
---
# <a name="mssqlserver_5233"></a><span data-ttu-id="ff5cf-102">MSSQLSERVER_5233</span><span class="sxs-lookup"><span data-stu-id="ff5cf-102">MSSQLSERVER_5233</span></span>
    
## <a name="details"></a><span data-ttu-id="ff5cf-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ff5cf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff5cf-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ff5cf-104">Product Name</span></span>|<span data-ttu-id="ff5cf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff5cf-105">SQL Server</span></span>|  
|<span data-ttu-id="ff5cf-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="ff5cf-106">Event ID</span></span>|<span data-ttu-id="ff5cf-107">5233</span><span class="sxs-lookup"><span data-stu-id="ff5cf-107">5233</span></span>|  
|<span data-ttu-id="ff5cf-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="ff5cf-108">Event Source</span></span>|<span data-ttu-id="ff5cf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ff5cf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ff5cf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ff5cf-110">Component</span></span>|<span data-ttu-id="ff5cf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ff5cf-111">SQLEngine</span></span>|  
|<span data-ttu-id="ff5cf-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="ff5cf-112">Symbolic Name</span></span>|<span data-ttu-id="ff5cf-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="ff5cf-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="ff5cf-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ff5cf-114">Message Text</span></span>|<span data-ttu-id="ff5cf-115">Errore di tabella: ID di unità di allocazione A_ID, pagina P_ID.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-115">Table error: alloc unit ID A_ID, page P_ID.</span></span> <span data-ttu-id="ff5cf-116">Test (TEST) non riuscito.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-116">The test (TEST) failed.</span></span> <span data-ttu-id="ff5cf-117">Valori: VAL1 e VAL2.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-117">The values are VAL1 and VAL2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ff5cf-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ff5cf-118">Explanation</span></span>  
 <span data-ttu-id="ff5cf-119">Il controllo sulla pagina *P_ID* non è riuscito poiché l'intestazione della pagina è danneggiata.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-119">Page *P_ID* has failed auditing due to a corruption in its page header.</span></span> <span data-ttu-id="ff5cf-120">La stringa presente in TEST indica il test effettivo che non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-120">The string in TEST gives the actual test that failed.</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="ff5cf-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="ff5cf-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="ff5cf-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="ff5cf-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="ff5cf-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="ff5cf-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="ff5cf-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="ff5cf-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="ff5cf-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="ff5cf-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="ff5cf-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="ff5cf-130">Restore from Backup</span></span>  
 <span data-ttu-id="ff5cf-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="ff5cf-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="ff5cf-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="ff5cf-133">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-133">Not applicable.</span></span> <span data-ttu-id="ff5cf-134">Impossibile correggere questo errore.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-134">This error cannot be repaired.</span></span> <span data-ttu-id="ff5cf-135">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ff5cf-135">If you cannot restore the database from a backup, contact Microsoft Customer Service and Support (CSS).</span></span>  
  
  
