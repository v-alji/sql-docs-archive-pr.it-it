---
title: MSSQLSERVER_7933 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7933 (Database Engine error)
ms.assetid: 722bd2c6-0fb9-4838-954a-439744c6ac4b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ff25201d56b1bf55a0ecafbba7fbc787dc2fb64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629405"
---
# <a name="mssqlserver_7933"></a><span data-ttu-id="32cca-102">MSSQLSERVER_7933</span><span class="sxs-lookup"><span data-stu-id="32cca-102">MSSQLSERVER_7933</span></span>
    
## <a name="details"></a><span data-ttu-id="32cca-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="32cca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32cca-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="32cca-104">Product Name</span></span>|<span data-ttu-id="32cca-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="32cca-105">SQL Server</span></span>|  
|<span data-ttu-id="32cca-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="32cca-106">Event ID</span></span>|<span data-ttu-id="32cca-107">7933</span><span class="sxs-lookup"><span data-stu-id="32cca-107">7933</span></span>|  
|<span data-ttu-id="32cca-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="32cca-108">Event Source</span></span>|<span data-ttu-id="32cca-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="32cca-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="32cca-110">Componente</span><span class="sxs-lookup"><span data-stu-id="32cca-110">Component</span></span>|<span data-ttu-id="32cca-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="32cca-111">SQLEngine</span></span>|  
|<span data-ttu-id="32cca-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="32cca-112">Symbolic Name</span></span>|<span data-ttu-id="32cca-113">DBCC2_FS_ORPHANED_ROWSET_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="32cca-113">DBCC2_FS_ORPHANED_ROWSET_DIRECTORY</span></span>|  
|<span data-ttu-id="32cca-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="32cca-114">Message Text</span></span>|<span data-ttu-id="32cca-115">Errore di tabella: l'ID di directory FILESTREAM F_ID esiste per una partizione, ma la partizione corrispondente non esiste nel database.</span><span class="sxs-lookup"><span data-stu-id="32cca-115">Table error: A Filestream directory ID F_ID exists for a partition, but the corresponding partition does not exist in the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="32cca-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="32cca-116">Explanation</span></span>  
 <span data-ttu-id="32cca-117">Durante DBCC CHECKDB, nello spazio dati FILESTREAM è stata individuata la directory di un set di righe la cui partizione corrispondente non è tuttavia presente nel database.</span><span class="sxs-lookup"><span data-stu-id="32cca-117">During DBCC CHECKDB, a rowset directory was found in the FILESTREAM dataspace; however, its corresponding partition is missing in the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32cca-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="32cca-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="32cca-119">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="32cca-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="32cca-120">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="32cca-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="32cca-121">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="32cca-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="32cca-122">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="32cca-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="32cca-123">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="32cca-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="32cca-124">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="32cca-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="32cca-125">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="32cca-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="32cca-126">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="32cca-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="32cca-127">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="32cca-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="32cca-128">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="32cca-128">Restore from Backup</span></span>  
 <span data-ttu-id="32cca-129">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="32cca-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="32cca-130">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="32cca-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="32cca-131">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="32cca-131">Not applicable.</span></span> <span data-ttu-id="32cca-132">L'errore non può essere corretto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="32cca-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="32cca-133">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32cca-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
