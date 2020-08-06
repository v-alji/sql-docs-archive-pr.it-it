---
title: MSSQLSERVER_833 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 833 (Database Engine error)
ms.assetid: 14129cc4-be80-4772-9e3f-0e5da4d0696b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e20018c0fe1cd0748f4930e0022622adcbfad10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628692"
---
# <a name="mssqlserver_833"></a><span data-ttu-id="0d95e-102">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="0d95e-102">MSSQLSERVER_833</span></span>
    
## <a name="details"></a><span data-ttu-id="0d95e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0d95e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d95e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0d95e-104">Product Name</span></span>|<span data-ttu-id="0d95e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0d95e-105">SQL Server</span></span>|  
|<span data-ttu-id="0d95e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0d95e-106">Event ID</span></span>|<span data-ttu-id="0d95e-107">833</span><span class="sxs-lookup"><span data-stu-id="0d95e-107">833</span></span>|  
|<span data-ttu-id="0d95e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0d95e-108">Event Source</span></span>|<span data-ttu-id="0d95e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0d95e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0d95e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0d95e-110">Component</span></span>|<span data-ttu-id="0d95e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0d95e-111">SQLEngine</span></span>|  
|<span data-ttu-id="0d95e-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0d95e-112">Symbolic Name</span></span>|<span data-ttu-id="0d95e-113">BUF_LONG_IO</span><span class="sxs-lookup"><span data-stu-id="0d95e-113">BUF_LONG_IO</span></span>|  
|<span data-ttu-id="0d95e-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0d95e-114">Message Text</span></span>|<span data-ttu-id="0d95e-115">In SQL Server sono state rilevate% d occorrenze di richieste di I/O che impiegano più di% d secondi per essere completate nel file [% ls] nel database `[%ls] (%d)` .</span><span class="sxs-lookup"><span data-stu-id="0d95e-115">SQL Server has encountered %d occurrence(s) of I/O requests taking longer than %d seconds to complete on file [%ls] in database`[%ls] (%d)`.</span></span>  <span data-ttu-id="0d95e-116">L'handle di file del sistema operativo è 0x%p.</span><span class="sxs-lookup"><span data-stu-id="0d95e-116">The OS file handle is 0x%p.</span></span>  <span data-ttu-id="0d95e-117">Offset dell'ultimo I/O lungo: %#016I64x.</span><span class="sxs-lookup"><span data-stu-id="0d95e-117">The offset of the latest long I/O is: %#016I64x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0d95e-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0d95e-118">Explanation</span></span>  
 <span data-ttu-id="0d95e-119">Questo messaggio indica che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha eseguito una richiesta di lettura o scrittura dal disco e che la durata dell'operazione è stata superiore a 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="0d95e-119">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="0d95e-120">Questo errore viene segnalato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e indica un problema relativo al sottosistema di IO.</span><span class="sxs-lookup"><span data-stu-id="0d95e-120">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the IO subsystem.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="0d95e-121">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="0d95e-121">Possible Causes</span></span>  
 <span data-ttu-id="0d95e-122">Il problema può essere causato da problemi di prestazioni del sistema, errori hardware, errori del firmware, problemi del driver del dispositivo o dall'intervento del driver di filtro nel processo di I/O.</span><span class="sxs-lookup"><span data-stu-id="0d95e-122">This problem can be caused system performance issues, hardware errors, firmware errors, device driver problems, or filter driver intervention in the IO process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0d95e-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0d95e-123">User Action</span></span>  
 <span data-ttu-id="0d95e-124">Per risolvere il problema che ha causato questo errore, individuare nel registro eventi di sistema i messaggi di errore correlati all'hardware.</span><span class="sxs-lookup"><span data-stu-id="0d95e-124">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="0d95e-125">Esaminare inoltre eventuali log specifici dei componenti hardware se disponibili.</span><span class="sxs-lookup"><span data-stu-id="0d95e-125">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="0d95e-126">Utilizzare Performance Monitor per esaminare i contatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d95e-126">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="0d95e-127">**Media secondi/trasf. disco**</span><span class="sxs-lookup"><span data-stu-id="0d95e-127">**Average Disk Sec/Transfer**</span></span>  
  
-   <span data-ttu-id="0d95e-128">**Lunghezza media coda del disco**</span><span class="sxs-lookup"><span data-stu-id="0d95e-128">**Average Disk Queue Length**</span></span>  
  
-   <span data-ttu-id="0d95e-129">**Lunghezza corrente coda del disco**</span><span class="sxs-lookup"><span data-stu-id="0d95e-129">**Current Disk Queue Length**</span></span>  
  
 <span data-ttu-id="0d95e-130">Il valore della durata media, ad esempio, di **Disco sec/trasferimento** in un computer che esegue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in genere inferiore a 15 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="0d95e-130">For example, the **Average Disk Sec/Transfer** time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="0d95e-131">L'aumento del valore di **Media secondi/trasf. disco** indica che il sottosistema di I/O non è in grado di soddisfare in modo ottimale le richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="0d95e-131">If the **Average Disk Sec/Transfer** value increases, this indicates that the I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d95e-132">L'accesso al disco può essere rallentato da un programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="0d95e-132">Disk access can be slowed by an antivirus program.</span></span> <span data-ttu-id="0d95e-133">Per aumentare la velocità di accesso, escludere dalle analisi virus attive i file di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specificati nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="0d95e-133">To increase access speed, exclude the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files that are specified in the error message from active virus scans.</span></span>  
  
 <span data-ttu-id="0d95e-134">Per altre informazioni sugli errori di I/O, vedere [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) (Nozioni di base sull'I/O in Microsoft SQL Server, capitolo 2) e l'articolo della Knowledge Base all'indirizzo [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span><span class="sxs-lookup"><span data-stu-id="0d95e-134">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) and the Knowledge Base article at [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span></span>  
  
  
