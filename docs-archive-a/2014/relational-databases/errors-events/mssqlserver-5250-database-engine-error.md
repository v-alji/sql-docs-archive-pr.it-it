---
title: MSSQLSERVER_5250 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5250 (Database Engine error)
ms.assetid: f4a1d0e8-f27f-4cb8-a25d-040b40555dcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace26b88aca5b00c23aff3fe48f7c1d04ef35245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718168"
---
# <a name="mssqlserver_5250"></a><span data-ttu-id="0bfe5-102">MSSQLSERVER_5250</span><span class="sxs-lookup"><span data-stu-id="0bfe5-102">MSSQLSERVER_5250</span></span>
    
## <a name="details"></a><span data-ttu-id="0bfe5-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0bfe5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0bfe5-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0bfe5-104">Product Name</span></span>|<span data-ttu-id="0bfe5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0bfe5-105">SQL Server</span></span>|  
|<span data-ttu-id="0bfe5-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0bfe5-106">Event ID</span></span>|<span data-ttu-id="0bfe5-107">5250</span><span class="sxs-lookup"><span data-stu-id="0bfe5-107">5250</span></span>|  
|<span data-ttu-id="0bfe5-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0bfe5-108">Event Source</span></span>|<span data-ttu-id="0bfe5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0bfe5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0bfe5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0bfe5-110">Component</span></span>|<span data-ttu-id="0bfe5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0bfe5-111">SQLEngine</span></span>|  
|<span data-ttu-id="0bfe5-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0bfe5-112">Symbolic Name</span></span>|<span data-ttu-id="0bfe5-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="0bfe5-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span></span>|  
|<span data-ttu-id="0bfe5-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0bfe5-114">Message Text</span></span>|<span data-ttu-id="0bfe5-115">Errore di database: la pagina PAGE_TYPE P_ID per il database 'NAME' (ID database DB_ID) non è valida.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-115">Database error: PAGE_TYPE page P_ID for database 'NAME' (database ID DB_ID) is invalid.</span></span> <span data-ttu-id="0bfe5-116">Impossibile correggere questo errore.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-116">This error cannot be repaired.</span></span> <span data-ttu-id="0bfe5-117">È necessario eseguire un ripristino dal backup.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-117">You must restore from backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0bfe5-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0bfe5-118">Explanation</span></span>  
 <span data-ttu-id="0bfe5-119">Una pagina di intestazione o una pagina di avvio del file nel database specificato è danneggiata.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-119">A file header page or boot page in the specified database is corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0bfe5-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0bfe5-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="0bfe5-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="0bfe5-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="0bfe5-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="0bfe5-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="0bfe5-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="0bfe5-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="0bfe5-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="0bfe5-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="0bfe5-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="0bfe5-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="0bfe5-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="0bfe5-130">Restore from Backup</span></span>  
 <span data-ttu-id="0bfe5-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="0bfe5-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="0bfe5-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="0bfe5-133">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-133">Not applicable.</span></span> <span data-ttu-id="0bfe5-134">Impossibile correggere questo errore.</span><span class="sxs-lookup"><span data-stu-id="0bfe5-134">This error cannot be repaired.</span></span> <span data-ttu-id="0bfe5-135">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bfe5-135">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
