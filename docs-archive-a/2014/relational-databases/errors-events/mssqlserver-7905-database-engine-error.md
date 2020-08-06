---
title: MSSQLSERVER_7905 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7905 (Database Engine error)
ms.assetid: cf19fbbb-7158-45f2-8778-8f3cad7f574a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 253bf03c1bfacccfd809cd417163eb9d54644f28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628711"
---
# <a name="mssqlserver_7905"></a><span data-ttu-id="98063-102">MSSQLSERVER_7905</span><span class="sxs-lookup"><span data-stu-id="98063-102">MSSQLSERVER_7905</span></span>
    
## <a name="details"></a><span data-ttu-id="98063-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="98063-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98063-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="98063-104">Product Name</span></span>|<span data-ttu-id="98063-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="98063-105">SQL Server</span></span>|  
|<span data-ttu-id="98063-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="98063-106">Event ID</span></span>|<span data-ttu-id="98063-107">7905</span><span class="sxs-lookup"><span data-stu-id="98063-107">7905</span></span>|  
|<span data-ttu-id="98063-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="98063-108">Event Source</span></span>|<span data-ttu-id="98063-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="98063-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="98063-110">Componente</span><span class="sxs-lookup"><span data-stu-id="98063-110">Component</span></span>|<span data-ttu-id="98063-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="98063-111">SQLEngine</span></span>|  
|<span data-ttu-id="98063-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="98063-112">Symbolic Name</span></span>|<span data-ttu-id="98063-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="98063-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span></span>|  
|<span data-ttu-id="98063-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="98063-114">Message Text</span></span>|<span data-ttu-id="98063-115">Errore di database: la directory 'DIRECTORY' non è una directory FILESTREAM valida.</span><span class="sxs-lookup"><span data-stu-id="98063-115">Database error: The directory 'DIRECTORY' is not a valid Filestream directory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="98063-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="98063-116">Explanation</span></span>  
 <span data-ttu-id="98063-117">Il nome di una directory di set di righe è l'ID di partizione della partizione, ad eccezione dei nomi di directory di set di righe speciali, ad esempio 'ghost'.</span><span class="sxs-lookup"><span data-stu-id="98063-117">The name of a rowset directory is the partition ID of the partition, except for the special rowset directory names such as 'ghost'.</span></span> <span data-ttu-id="98063-118">Se non è possibile convertire tale nome in un ID di partizione, la directory non verrà considerata una directory di set di righe valida.</span><span class="sxs-lookup"><span data-stu-id="98063-118">If a rowset directory name cannot be converted to a partition ID, the directory is not a valid rowset directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98063-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="98063-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="98063-120">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="98063-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="98063-121">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="98063-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="98063-122">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="98063-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="98063-123">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="98063-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="98063-124">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="98063-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="98063-125">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="98063-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="98063-126">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="98063-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="98063-127">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="98063-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="98063-128">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="98063-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="98063-129">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="98063-129">Restore from Backup</span></span>  
 <span data-ttu-id="98063-130">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="98063-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="98063-131">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="98063-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="98063-132">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="98063-132">Not applicable.</span></span> <span data-ttu-id="98063-133">Impossibile correggere questo errore.</span><span class="sxs-lookup"><span data-stu-id="98063-133">This error cannot be repaired.</span></span> <span data-ttu-id="98063-134">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98063-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
