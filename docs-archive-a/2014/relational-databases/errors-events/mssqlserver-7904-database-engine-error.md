---
title: MSSQLSERVER_7904 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7904 (Database Engine error)
ms.assetid: d047920c-f864-4338-b15f-49820886fbc5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5e7be2e8413bc0267a642360da66a6a9ec0de8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628710"
---
# <a name="mssqlserver_7904"></a><span data-ttu-id="bb1b5-102">MSSQLSERVER_7904</span><span class="sxs-lookup"><span data-stu-id="bb1b5-102">MSSQLSERVER_7904</span></span>
    
## <a name="details"></a><span data-ttu-id="bb1b5-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bb1b5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb1b5-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="bb1b5-104">Product Name</span></span>|<span data-ttu-id="bb1b5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bb1b5-105">SQL Server</span></span>|  
|<span data-ttu-id="bb1b5-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="bb1b5-106">Event ID</span></span>|<span data-ttu-id="bb1b5-107">7904</span><span class="sxs-lookup"><span data-stu-id="bb1b5-107">7904</span></span>|  
|<span data-ttu-id="bb1b5-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="bb1b5-108">Event Source</span></span>|<span data-ttu-id="bb1b5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bb1b5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bb1b5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bb1b5-110">Component</span></span>|<span data-ttu-id="bb1b5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bb1b5-111">SQLEngine</span></span>|  
|<span data-ttu-id="bb1b5-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="bb1b5-112">Symbolic Name</span></span>|<span data-ttu-id="bb1b5-113">DBCC2_FS_MISSING_FILE</span><span class="sxs-lookup"><span data-stu-id="bb1b5-113">DBCC2_FS_MISSING_FILE</span></span>|  
|<span data-ttu-id="bb1b5-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="bb1b5-114">Message Text</span></span>|<span data-ttu-id="bb1b5-115">Errore di tabella: impossibile trovare il file FileStream per l'ID di colonna C_ID, ROWGUID RG_ID, nell'oggetto con ID O_ID, ID di indice I_ID, ID di partizione PN_ID.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-115">Table error: The filestream file for column ID C_ID, ROWGUID RG_ID in object ID O_ID, index ID I_ID, partition ID PN_ID was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bb1b5-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bb1b5-116">Explanation</span></span>  
 <span data-ttu-id="bb1b5-117">Un valore di colonna in una partizione è privo di un file FILESTREAM corrispondente nella relativa directory di colonne FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-117">A column value of a partition does not have a matching FILESTREAM file in the corresponding FILESTREAM column directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bb1b5-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="bb1b5-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="bb1b5-119">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="bb1b5-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="bb1b5-120">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="bb1b5-121">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="bb1b5-122">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="bb1b5-123">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="bb1b5-124">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="bb1b5-125">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="bb1b5-126">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="bb1b5-127">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="bb1b5-128">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="bb1b5-128">Restore from Backup</span></span>  
 <span data-ttu-id="bb1b5-129">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="bb1b5-130">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="bb1b5-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="bb1b5-131">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-131">Not applicable.</span></span> <span data-ttu-id="bb1b5-132">Impossibile correggere questo errore.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-132">This error cannot be repaired.</span></span> <span data-ttu-id="bb1b5-133">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb1b5-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
