---
title: MSSQLSERVER_2522 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2522 (Database Engine error)
ms.assetid: 19b9b00c-330f-4dd3-9052-9d88bce83849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60446c21599c02ee9c4bc96789b106b49b71582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624233"
---
# <a name="mssqlserver_2522"></a><span data-ttu-id="13a58-102">MSSQLSERVER_2522</span><span class="sxs-lookup"><span data-stu-id="13a58-102">MSSQLSERVER_2522</span></span>
    
## <a name="details"></a><span data-ttu-id="13a58-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="13a58-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13a58-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="13a58-104">Product Name</span></span>|<span data-ttu-id="13a58-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="13a58-105">SQL Server</span></span>|  
|<span data-ttu-id="13a58-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="13a58-106">Event ID</span></span>|<span data-ttu-id="13a58-107">2522</span><span class="sxs-lookup"><span data-stu-id="13a58-107">2522</span></span>|  
|<span data-ttu-id="13a58-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="13a58-108">Event Source</span></span>|<span data-ttu-id="13a58-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="13a58-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="13a58-110">Componente</span><span class="sxs-lookup"><span data-stu-id="13a58-110">Component</span></span>|<span data-ttu-id="13a58-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="13a58-111">SQLEngine</span></span>|  
|<span data-ttu-id="13a58-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="13a58-112">Symbolic Name</span></span>|<span data-ttu-id="13a58-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="13a58-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span></span>|  
|<span data-ttu-id="13a58-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="13a58-114">Message Text</span></span>|<span data-ttu-id="13a58-115">Impossibile elaborare l'indice I_NAME della tabella O_NAME. Filegroup F_NAME non valido.</span><span class="sxs-lookup"><span data-stu-id="13a58-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is invalid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="13a58-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="13a58-116">Explanation</span></span>  
 <span data-ttu-id="13a58-117">Questo messaggio informativo indica che non è possibile verificare l'indice perché uno degli ID di filegroup archiviato nei metadati dell'indice non esiste.</span><span class="sxs-lookup"><span data-stu-id="13a58-117">This informational message indicates that the index cannot be checked because one of the filegroup IDs that is stored in the metadata of the index does not exist.</span></span> <span data-ttu-id="13a58-118">L'ID di filegroup non valido potrebbe essere relativo agli stessi dati oppure ai dati LOB (Large Object) o ai dati di overflow della riga.</span><span class="sxs-lookup"><span data-stu-id="13a58-118">The filegroup ID that is not valid might pertain to the data itself, or to the large object (LOB) data, or to the row-overflow data.</span></span>  
  
 <span data-ttu-id="13a58-119">Se non vi sono problemi, tutti gli altri indici dello stesso oggetto verranno verificati.</span><span class="sxs-lookup"><span data-stu-id="13a58-119">If there are no problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="13a58-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="13a58-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="13a58-121">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="13a58-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="13a58-122">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="13a58-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="13a58-123">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="13a58-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="13a58-124">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="13a58-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="13a58-125">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="13a58-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="13a58-126">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="13a58-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="13a58-127">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="13a58-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="13a58-128">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="13a58-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="13a58-129">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="13a58-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="13a58-130">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="13a58-130">Restore from Backup</span></span>  
 <span data-ttu-id="13a58-131">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="13a58-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="13a58-132">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="13a58-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="13a58-133">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="13a58-133">Not applicable.</span></span> <span data-ttu-id="13a58-134">L'errore non può essere corretto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="13a58-134">This error cannot be repaired automatically.</span></span>  
  
  
