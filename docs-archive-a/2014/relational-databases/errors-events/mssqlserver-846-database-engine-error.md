---
title: MSSQLSERVER_846 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 846 (Database Engine error)
ms.assetid: ccf367eb-06b0-42b8-b4d6-2b88f4a502d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b7cb6461d467090b03c246db5074ad203ce0ac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635079"
---
# <a name="mssqlserver_846"></a><span data-ttu-id="84b70-102">MSSQLSERVER_846</span><span class="sxs-lookup"><span data-stu-id="84b70-102">MSSQLSERVER_846</span></span>
    
## <a name="details"></a><span data-ttu-id="84b70-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="84b70-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84b70-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="84b70-104">Product Name</span></span>|<span data-ttu-id="84b70-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="84b70-105">SQL Server</span></span>|  
|<span data-ttu-id="84b70-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="84b70-106">Event ID</span></span>|<span data-ttu-id="84b70-107">846</span><span class="sxs-lookup"><span data-stu-id="84b70-107">846</span></span>|  
|<span data-ttu-id="84b70-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="84b70-108">Event Source</span></span>|<span data-ttu-id="84b70-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="84b70-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="84b70-110">Componente</span><span class="sxs-lookup"><span data-stu-id="84b70-110">Component</span></span>|<span data-ttu-id="84b70-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="84b70-111">SQLEngine</span></span>|  
|<span data-ttu-id="84b70-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="84b70-112">Symbolic Name</span></span>|<span data-ttu-id="84b70-113">N/D</span><span class="sxs-lookup"><span data-stu-id="84b70-113">N/A</span></span>|  
|<span data-ttu-id="84b70-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="84b70-114">Message Text</span></span>|<span data-ttu-id="84b70-115">Timeout durante l'attesa del latch del buffer: tipo %d, bp %p, pagina %d:%d, stat %#x, ID database: %d, ID unità di allocazione:%I64d%ls, attività 0x%p : %d, attesa %d, flag 0x%I64x, attività proprietaria 0x%p.</span><span class="sxs-lookup"><span data-stu-id="84b70-115">A time-out occurred while waiting for buffer latch -- type %d, bp %p, page %d:%d, stat %#x, database id: %d, allocation unit Id: %I64d%ls, task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span> <span data-ttu-id="84b70-116">L'attesa verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="84b70-116">Not continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="84b70-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="84b70-117">Explanation</span></span>  
 <span data-ttu-id="84b70-118">È possibile che un computer si arresti oppure che si verifichi un timeout o altre interruzioni delle operazioni regolari nel momento in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] scrive errori di latch del buffer nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84b70-118">A computer might stop responding, or a time-out or some other disruption of regular operations might occur at the same time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] writes buffer latch errors to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="84b70-119">Se nel messaggio il campo stat ha il valore di 0x04 attivato, significa che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in attesa di un'operazione di I/O.</span><span class="sxs-lookup"><span data-stu-id="84b70-119">If the stat field in the message has the value of 0x04 on, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for an I/O operation.</span></span> <span data-ttu-id="84b70-120">Nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] potrebbe inoltre essere presente il messaggio [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="84b70-120">You may also receive message [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="84b70-121">Se nel messaggio il campo stat ha il valore 0x04 disattivato, significa che si sta verificando un'intensa contesa per una pagina.</span><span class="sxs-lookup"><span data-stu-id="84b70-121">If the stat field in the message has the value 0x04 off, there is heavy contention for a page.</span></span> <span data-ttu-id="84b70-122">Se l'oggetto è costituito da una pagina di dati, è possibile che il problema sia causato da una progettazione di codice non efficiente.</span><span class="sxs-lookup"><span data-stu-id="84b70-122">If the object is a data page, this can be caused by inefficient code design.</span></span> <span data-ttu-id="84b70-123">Se la pagina non contiene dati, è possibile che l'errore si verifichi a causa di colli di bottiglia del server, ad esempio risorse hardware insufficienti.</span><span class="sxs-lookup"><span data-stu-id="84b70-123">If the page is nondata, the error might be caused by server bottlenecks, such as insufficient hardware resources.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="84b70-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="84b70-124">User Action</span></span>  
 <span data-ttu-id="84b70-125">Per risolvere il problema, eseguire uno o più dei passaggi seguenti che, a seconda dell'ambiente in uso, potrebbero consentire di ridurre o eliminare i messaggi di errore:</span><span class="sxs-lookup"><span data-stu-id="84b70-125">To work around this problem, depending on your environment, one or more of the following steps might reduce or eliminate the error messages:</span></span>  
  
-   <span data-ttu-id="84b70-126">Determinare se è presente un collo di bottiglia dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="84b70-126">Determine whether you have any hardware bottlenecks.</span></span> <span data-ttu-id="84b70-127">Se necessario, aggiornare l'hardware in modo che supporti i requisiti di configurazione, query e carico dell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="84b70-127">If it is necessary, upgrade your hardware so that it can support the configuration, query, and load requirements of your environment.</span></span> <span data-ttu-id="84b70-128">Per altre informazioni sui colli di bottiglia, vedere [Individuare i colli di bottiglia](../performance/identify-bottlenecks.md).</span><span class="sxs-lookup"><span data-stu-id="84b70-128">For more information about bottlenecks, see [Identify Bottlenecks](../performance/identify-bottlenecks.md).</span></span>  
  
-   <span data-ttu-id="84b70-129">Controllare gli errori registrati ed eseguire tutti gli strumenti di diagnostica offerti dal fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="84b70-129">Check for any logged errors and run any diagnostics provided by your hardware vendor.</span></span>  
  
-   <span data-ttu-id="84b70-130">Verificare che le unità disco non siano compresse.</span><span class="sxs-lookup"><span data-stu-id="84b70-130">Make sure that your disk drives are not compressed.</span></span> <span data-ttu-id="84b70-131">L'archiviazione di dati o file di log nelle unità compresse non è supportata.</span><span class="sxs-lookup"><span data-stu-id="84b70-131">Storing data or log files on compressed drives is not supported.</span></span> <span data-ttu-id="84b70-132">Per altre informazioni sui file fisici, vedere [Filegroup e file di database](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="84b70-132">For more information about physical files, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
-   <span data-ttu-id="84b70-133">Verificare se i messaggi di errore non vengono più visualizzati quando si disattivano le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84b70-133">See whether the error messages disappear when you set the following options to off:</span></span>  
  
    -   <span data-ttu-id="84b70-134">Opzione di configurazione priority boost di SQL Server</span><span class="sxs-lookup"><span data-stu-id="84b70-134">SQL Server priority boost configuration option</span></span>  
  
    -   <span data-ttu-id="84b70-135">Opzione lightweight pooling (modalità fiber)</span><span class="sxs-lookup"><span data-stu-id="84b70-135">Lightweight pooling (fiber mode) option</span></span>  
  
    -   <span data-ttu-id="84b70-136">Opzione set working set size</span><span class="sxs-lookup"><span data-stu-id="84b70-136">Set working set size option</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="84b70-137">La modifica dell'impostazione predefinita OFF delle opzioni precedenti può di frequente risultare controproducente.</span><span class="sxs-lookup"><span data-stu-id="84b70-137">The previous settings can frequently be counter-productive if you change them from their default setting of OFF.</span></span> <span data-ttu-id="84b70-138">Per altre informazioni sulle impostazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="84b70-138">For more information about the settings, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
-   <span data-ttu-id="84b70-139">Ottimizzare le query per ridurre le risorse utilizzate nel sistema.</span><span class="sxs-lookup"><span data-stu-id="84b70-139">Tune queries to reduce resources used on the system.</span></span> <span data-ttu-id="84b70-140">L'ottimizzazione delle prestazioni consente di ridurre il sovraccarico del sistema e migliorare il tempo di risposta per le query individuali.</span><span class="sxs-lookup"><span data-stu-id="84b70-140">Performance tuning will help reduce the stress on a system and improve response time for individual queries.</span></span>  
  
-   <span data-ttu-id="84b70-141">Impostare l'opzione AUTO_SHRINK su OFF per ridurre l'overhead delle modifiche alle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="84b70-141">Set the AUTO_SHRINK option to OFF to reduce the overhead of changes to the database size.</span></span>  
  
-   <span data-ttu-id="84b70-142">Verificare di aver impostato l'opzione FILEGROWTH su incrementi di dimensioni tali da risultare poco frequenti.</span><span class="sxs-lookup"><span data-stu-id="84b70-142">Make sure that you set the FILEGROWTH option to increments that are large enough to be infrequent.</span></span> <span data-ttu-id="84b70-143">Pianificare un processo che consenta di controllare lo spazio disponibile nei database e quindi aumentare le dimensioni dei database durante i periodi di attività ridotta.</span><span class="sxs-lookup"><span data-stu-id="84b70-143">Schedule a job to check the available space in the databases, and then increase the database size during nonpeak hours.</span></span>  
  
  
