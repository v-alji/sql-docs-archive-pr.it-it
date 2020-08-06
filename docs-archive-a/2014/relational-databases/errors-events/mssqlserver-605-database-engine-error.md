---
title: MSSQLSERVER_605 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 605 (Database Engine error)
ms.assetid: d8d3a22e-1ff8-48a4-891f-4c8619437e24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e196fba84af492b25e798629d3e808b1bf22857e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636093"
---
# <a name="mssqlserver_605"></a><span data-ttu-id="dac51-102">MSSQLSERVER_605</span><span class="sxs-lookup"><span data-stu-id="dac51-102">MSSQLSERVER_605</span></span>
    
## <a name="details"></a><span data-ttu-id="dac51-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dac51-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dac51-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="dac51-104">Product Name</span></span>|<span data-ttu-id="dac51-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dac51-105">SQL Server</span></span>|  
|<span data-ttu-id="dac51-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="dac51-106">Event ID</span></span>|<span data-ttu-id="dac51-107">605</span><span class="sxs-lookup"><span data-stu-id="dac51-107">605</span></span>|  
|<span data-ttu-id="dac51-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="dac51-108">Event Source</span></span>|<span data-ttu-id="dac51-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dac51-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dac51-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dac51-110">Component</span></span>|<span data-ttu-id="dac51-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dac51-111">SQLEngine</span></span>|  
|<span data-ttu-id="dac51-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="dac51-112">Symbolic Name</span></span>|<span data-ttu-id="dac51-113">WRONGPAGE</span><span class="sxs-lookup"><span data-stu-id="dac51-113">WRONGPAGE</span></span>|  
|<span data-ttu-id="dac51-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="dac51-114">Message Text</span></span>|<span data-ttu-id="dac51-115">Impossibile recuperare la pagina logica %S_PGID nel database %d,</span><span class="sxs-lookup"><span data-stu-id="dac51-115">Attempt to fetch logical page %S_PGID in database %d failed.</span></span> <span data-ttu-id="dac51-116">poiché appartiene all'unità di allocazione %I64d, non a %I64d.</span><span class="sxs-lookup"><span data-stu-id="dac51-116">It belongs to allocation unit %I64d not to %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dac51-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="dac51-117">Explanation</span></span>  
 <span data-ttu-id="dac51-118">Questo errore in genere indica il danneggiamento di una pagina o un'allocazione nel database specificato.</span><span class="sxs-lookup"><span data-stu-id="dac51-118">This error generally signifies page or allocation corruption in the specified database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dac51-119">rileva il danneggiamento durante la lettura di pagine appartenenti a una tabella seguendo i collegamenti delle pagine o usando la mappa di allocazione degli indici (IAM, Index Allocation Map).</span><span class="sxs-lookup"><span data-stu-id="dac51-119">detects corruption when reading pages belonging to a table either by following the page linkages or by using the Index Allocation Map (IAM).</span></span> <span data-ttu-id="dac51-120">Tutte le pagine allocate a una tabella devono appartenere a una delle unità di allocazione associate alla tabella.</span><span class="sxs-lookup"><span data-stu-id="dac51-120">All pages allocated to a table must belong to one of the allocation units associated with the table.</span></span> <span data-ttu-id="dac51-121">Se l'ID dell'unità di allocazione incluso nell'intestazione della pagina non corrisponde a uno degli ID di unità di allocazione associati alla tabella, viene generata questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="dac51-121">If the allocation unit ID contained in the page header does not match an allocation unit ID associated with the table, this exception is raised.</span></span> <span data-ttu-id="dac51-122">Il primo ID di unità di allocazione elencato nel messaggio di errore è l'ID presente nell'intestazione di pagina, mentre il secondo è quello associato alla tabella.</span><span class="sxs-lookup"><span data-stu-id="dac51-122">The first allocation unit ID listed in the error message is the ID present in the page header, and the second allocation unit value is the ID associated with the table.</span></span>  
  
 <span data-ttu-id="dac51-123">**Errori di danneggiamento dei dati**</span><span class="sxs-lookup"><span data-stu-id="dac51-123">**Data Corruption Errors**</span></span>  
  
 <span data-ttu-id="dac51-124">Un livello di gravità pari a 21 indica un potenziale danneggiamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="dac51-124">A severity level of 21 indicates potential data corruption.</span></span> <span data-ttu-id="dac51-125">Le possibili cause sono una catena di pagine o una mappa di allocazione degli indici danneggiata oppure una voce non valida nella vista del catalogo [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="dac51-125">Possible causes are a damaged page chain, a corrupt IAM, or an invalid entry in the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view for that object.</span></span> <span data-ttu-id="dac51-126">Questi errori spesso sono causati da errori hardware o dei driver di dispositivi disco.</span><span class="sxs-lookup"><span data-stu-id="dac51-126">These errors are often caused by hardware or disk device driver failure.</span></span>  
  
 <span data-ttu-id="dac51-127">**Errori transitori**</span><span class="sxs-lookup"><span data-stu-id="dac51-127">**Transient Errors**</span></span>  
  
 <span data-ttu-id="dac51-128">Un livello di gravità pari a 12 indica un potenziale errore transitorio, ovvero un errore che si verifica nella cache e non implica danneggiamento di dati sul disco.</span><span class="sxs-lookup"><span data-stu-id="dac51-128">A severity level of 12 indicates a potential transient error; that is, it occurs in the cache and does not indicate damage to data on disk.</span></span> <span data-ttu-id="dac51-129">Gli errori 605 di tipo transitorio possono essere causati dalle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dac51-129">Transient 605 errors can be caused by the following conditions:</span></span>  
  
-   <span data-ttu-id="dac51-130">Invio di una notifica anomala a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da parte del sistema operativo per informare che è stata completata un'operazione di I/O. Il messaggio di errore viene visualizzato anche se non si è effettivamente verificato alcun danneggiamento di dati.</span><span class="sxs-lookup"><span data-stu-id="dac51-130">The operating system prematurely notifies [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that an I/O operation has completed; the error message is displayed even though no actual data corruption exists.</span></span>  
  
 <span data-ttu-id="dac51-131">Esecuzione di una query con l'hint di Query Optimizer NOLOCK o impostazione del livello di isolamento della transazione su READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="dac51-131">Running a query with the Optimizer hint NOLOCK or setting the transaction isolation level to READ UNCOMMITTED.</span></span> <span data-ttu-id="dac51-132">Quando una query che utilizza NOLOCK o READ UNCOMMITTED tenta di leggere dati spostati o modificati da un altro utente, si verifica un errore 605.</span><span class="sxs-lookup"><span data-stu-id="dac51-132">When a query that is using NOLOCK or READ UNCOMMITTED tries to read data that is being moved or changed by another user, a 605 error occurs.</span></span> <span data-ttu-id="dac51-133">Per verificare che si tratti di un errore 605 transitorio, eseguire di nuovo la query in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="dac51-133">To verify that it is a transient 605 error, rerun the query later.</span></span> <span data-ttu-id="dac51-134">Per altre informazioni, vedere l'articolo [235880](https://support.microsoft.com/kb/235880/en-us) della Knowledge Base: "Viene visualizzato un messaggio di errore "Errore 605" quando si esegue una query con l'hint di ottimizzazione NOLOCK o si imposta il livello di isolamento della transazione su READ UNCOMMITTED in SQL Server".</span><span class="sxs-lookup"><span data-stu-id="dac51-134">For more information, see this KB article [235880](https://support.microsoft.com/kb/235880/en-us): "You receive an "Error 605" error message when you run a query with the optimizer hint NOLOCK or you set the transaction isolation level to READ UNCOMMITTED in SQL Server."</span></span>  
  
 <span data-ttu-id="dac51-135">In generale, se l'errore si verifica durante l'accesso ai dati ma le successive operazioni DBCC CHECKDB vengono completate senza errori, l'errore 605 era probabilmente transitorio.</span><span class="sxs-lookup"><span data-stu-id="dac51-135">In general, if the error occurs during data access but subsequent DBCC CHECKDB operations complete without error, the 605 error was probably transient.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dac51-136">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="dac51-136">User Action</span></span>  
 <span data-ttu-id="dac51-137">Se l'errore 605 non è temporaneo, il problema è grave e deve essere corretto eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dac51-137">If the 605 error is not transient, the problem is severe and must be corrected by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="dac51-138">Identificare le tabelle associate alle unità di allocazione specificate nel messaggio eseguendo la query seguente.</span><span class="sxs-lookup"><span data-stu-id="dac51-138">Identify the tables associated with the allocation units specified in the message by running the following query.</span></span> <span data-ttu-id="dac51-139">Sostituire `allocation_unit_id` con le unità di allocazione specificate nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="dac51-139">Replace `allocation_unit_id` with the allocation units specified in the error message.</span></span>  
  
     <span data-ttu-id="dac51-140">USE`database_name`;</span><span class="sxs-lookup"><span data-stu-id="dac51-140">USE`database_name`;</span></span>  
  
     <span data-ttu-id="dac51-141">GO</span><span class="sxs-lookup"><span data-stu-id="dac51-141">GO</span></span>  
  
     <span data-ttu-id="dac51-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span><span class="sxs-lookup"><span data-stu-id="dac51-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span></span>  
  
     <span data-ttu-id="dac51-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span><span class="sxs-lookup"><span data-stu-id="dac51-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span></span>  
  
     <span data-ttu-id="dac51-144">FROM sys.allocation_units AS au</span><span class="sxs-lookup"><span data-stu-id="dac51-144">FROM sys.allocation_units AS au</span></span>  
  
     <span data-ttu-id="dac51-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span><span class="sxs-lookup"><span data-stu-id="dac51-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span></span>  
  
     <span data-ttu-id="dac51-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span><span class="sxs-lookup"><span data-stu-id="dac51-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span></span>  
  
     <span data-ttu-id="dac51-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span><span class="sxs-lookup"><span data-stu-id="dac51-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span></span>  
  
     <span data-ttu-id="dac51-148">ORDER BY au.allocation_unit_id;</span><span class="sxs-lookup"><span data-stu-id="dac51-148">ORDER BY au.allocation_unit_id;</span></span>  
  
     <span data-ttu-id="dac51-149">GO</span><span class="sxs-lookup"><span data-stu-id="dac51-149">GO</span></span>  
  
2.  <span data-ttu-id="dac51-150">Eseguire DBCC CHECKTABLE senza una clausola REPAIR nella tabella associata al secondo ID di unità di allocazione specificato nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="dac51-150">Execute DBCC CHECKTABLE without a REPAIR clause on the table associated with the second allocation unit ID specified in the error message.</span></span>  
  
3.  <span data-ttu-id="dac51-151">Eseguire DBCC CHECKDB senza una clausola REPAIR il prima possibile, per determinare l'entità del danno all'intero database.</span><span class="sxs-lookup"><span data-stu-id="dac51-151">Execute DBCC CHECKDB without a REPAIR clause as soon as possible to determine the full extent of the corruption in the entire database.</span></span>  
  
4.  <span data-ttu-id="dac51-152">Verificare se nel log degli errori sono presenti altri errori spesso associati all'errore 605 e verificare se nel registro eventi di Windows sono presenti segnalazioni di eventuali problemi relativi al sistema o all'hardware.</span><span class="sxs-lookup"><span data-stu-id="dac51-152">Check the error log for other errors that often accompany a 605 error and examine the Windows Event Log for any system or hardware related issues.</span></span> <span data-ttu-id="dac51-153">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="dac51-153">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="dac51-154">Se il problema non è hardware, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dac51-154">If the problem is not hardware related, perform one of the following tasks:</span></span>  
  
1.  <span data-ttu-id="dac51-155">Ripristinare il database da un backup valido noto.</span><span class="sxs-lookup"><span data-stu-id="dac51-155">Restore the database from a known clean backup.</span></span> <span data-ttu-id="dac51-156">Per ripristinare solo le pagine danneggiate, è possibile utilizzare la caratteristica di backup per il ripristino di pagina.</span><span class="sxs-lookup"><span data-stu-id="dac51-156">You can leverage the page restore backup feature to restore just the damaged pages.</span></span>  
  
2.  <span data-ttu-id="dac51-157">Per correggere il danneggiamento, eseguire DBCC CHECKDB con la clausola REPAIR consigliata dall'operazione DBCC CHECKDB eseguita nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="dac51-157">Run DBCC CHECKDB with the REPAIR clause recommended by the DBCC CHECKDB operation performed in step 3 to repair the corruption.</span></span> <span data-ttu-id="dac51-158">Se l'esecuzione di DBCC CHECKDB con una clausola REPAIR non consente di risolvere il problema, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="dac51-158">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span> <span data-ttu-id="dac51-159">Accertarsi di avere l'output di DBCC CHECKDB disponibile per la consultazione.</span><span class="sxs-lookup"><span data-stu-id="dac51-159">Have the output from DBCC CHECKDB available for review.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="dac51-160">Se non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con la clausola REPAIR, contattare il personale del supporto tecnico prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="dac51-160">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac51-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dac51-161">See Also</span></span>  
 [<span data-ttu-id="dac51-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dac51-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql)  
  
  
