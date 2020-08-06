---
title: MSSQLSERVER_8996 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8996 (Database Engine error)
ms.assetid: 4e655cdc-945a-4a18-95dd-75f050563d26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d0cb5f0294ea471a6e300adbabc0f7b55632994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636088"
---
# <a name="mssqlserver_8996"></a><span data-ttu-id="35279-102">MSSQLSERVER_8996</span><span class="sxs-lookup"><span data-stu-id="35279-102">MSSQLSERVER_8996</span></span>
    
## <a name="details"></a><span data-ttu-id="35279-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="35279-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35279-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="35279-104">Product Name</span></span>|<span data-ttu-id="35279-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="35279-105">SQL Server</span></span>|  
|<span data-ttu-id="35279-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="35279-106">Event ID</span></span>|<span data-ttu-id="35279-107">8996</span><span class="sxs-lookup"><span data-stu-id="35279-107">8996</span></span>|  
|<span data-ttu-id="35279-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="35279-108">Event Source</span></span>|<span data-ttu-id="35279-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="35279-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="35279-110">Componente</span><span class="sxs-lookup"><span data-stu-id="35279-110">Component</span></span>|<span data-ttu-id="35279-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="35279-111">SQLEngine</span></span>|  
|<span data-ttu-id="35279-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="35279-112">Symbolic Name</span></span>|<span data-ttu-id="35279-113">DBCC3_IAM_PAGE_RANGE_IN_WRONG_FILEGROUP</span><span class="sxs-lookup"><span data-stu-id="35279-113">DBCC3_IAM_PAGE_RANGE_IN_WRONG_FILEGROUP</span></span>|  
|<span data-ttu-id="35279-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="35279-114">Message Text</span></span>|<span data-ttu-id="35279-115">La pagina IAM P_ID per l'ID di oggetto O_ID, ID di indice I_ID, ID di partizione PN_ID, ID di unità di allocazione A_ID (tipo TYPE) controlla alcune pagine nel filegroup FG_ID1, che dovrebbero trovarsi nel filegroup FG_ID2.</span><span class="sxs-lookup"><span data-stu-id="35279-115">IAM page P_ID for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) controls pages in filegroup FG_ID1, that should be in filegroup FG_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="35279-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="35279-116">Explanation</span></span>  
 <span data-ttu-id="35279-117">La pagina della mappa di allocazione degli indici (IAM, Index Allocation Map) *P_ID* del filegroup *FG_ID1* include erroneamente extent del filegroup *FG_ID2*.</span><span class="sxs-lookup"><span data-stu-id="35279-117">The index allocation map (IAM) page *P_ID* in filegroup *FG_ID1* incorrectly includes extents from filegroup *FG_ID2*.</span></span> <span data-ttu-id="35279-118">Tutti gli extent di una pagina IAM dovrebbero trovarsi nello stesso filegroup della pagina IAM.</span><span class="sxs-lookup"><span data-stu-id="35279-118">All extents for an IAM page should be in the same filegroup as the IAM page itself.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35279-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="35279-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="35279-120">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="35279-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="35279-121">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="35279-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="35279-122">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="35279-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="35279-123">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="35279-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="35279-124">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="35279-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="35279-125">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="35279-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="35279-126">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="35279-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="35279-127">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="35279-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="35279-128">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="35279-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="35279-129">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="35279-129">Restore from Backup</span></span>  
 <span data-ttu-id="35279-130">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="35279-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="35279-131">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="35279-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="35279-132">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="35279-132">Not applicable.</span></span> <span data-ttu-id="35279-133">Impossibile correggere questo errore.</span><span class="sxs-lookup"><span data-stu-id="35279-133">This error cannot be repaired.</span></span> <span data-ttu-id="35279-134">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35279-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
