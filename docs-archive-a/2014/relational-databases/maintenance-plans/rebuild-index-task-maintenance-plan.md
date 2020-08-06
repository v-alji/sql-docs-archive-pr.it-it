---
title: Attività Ricompila indice (piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reindex.f1
- reindex
helpviewer_keywords:
- Rebuild Index Task dialog box
ms.assetid: 33e2940b-139f-4563-b0cb-5683f08bd879
author: rothja
ms.author: jroth
ms.openlocfilehash: bc9d7c85a72c34cee1ef7af8cb4b4f25f918a3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627224"
---
# <a name="rebuild-index-task-maintenance-plan"></a><span data-ttu-id="b0384-102">Attività Ricompila indice (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="b0384-102">Rebuild Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="b0384-103">Usare la finestra di dialogo **Attività Ricompila indice** per ricreare gli indici nelle tabelle del database con un nuovo fattore di riempimento.</span><span class="sxs-lookup"><span data-stu-id="b0384-103">Use the **Rebuild Index Task** dialog to re-create the indexes on the tables in the database with a new fill factor.</span></span> <span data-ttu-id="b0384-104">Il fattore di riempimento determina la quantità di spazio vuoto in ogni pagina dell'indice che potrà essere utilizzato per contenere espansioni future.</span><span class="sxs-lookup"><span data-stu-id="b0384-104">The fill factor determines the amount of empty space on each page in the index, to accommodate future expansion.</span></span> <span data-ttu-id="b0384-105">Poiché il fattore di riempimento non viene gestito, a mano a mano che si aggiungono dati alla tabella lo spazio libero disponibile si riduce.</span><span class="sxs-lookup"><span data-stu-id="b0384-105">As data is added to the table, the free space fills because the fill factor is not maintained.</span></span> <span data-ttu-id="b0384-106">La riorganizzazione delle pagine di dati e di indici consente di ristabilire lo spazio libero.</span><span class="sxs-lookup"><span data-stu-id="b0384-106">Reorganizing data and index pages can re-establish the free space.</span></span>  
  
 <span data-ttu-id="b0384-107">In **Attività Ricompila indice** viene utilizzata l'istruzione ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="b0384-107">The **Rebuild Index Task** uses the ALTER INDEX statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b0384-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b0384-108">Options</span></span>  
 <span data-ttu-id="b0384-109">**Connection**</span><span class="sxs-lookup"><span data-stu-id="b0384-109">**Connection**</span></span>  
 <span data-ttu-id="b0384-110">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b0384-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="b0384-111">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="b0384-111">**New**</span></span>  
 <span data-ttu-id="b0384-112">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b0384-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="b0384-113">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="b0384-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="b0384-114">**Database**</span><span class="sxs-lookup"><span data-stu-id="b0384-114">**Databases**</span></span>  
 <span data-ttu-id="b0384-115">Consente di specificare i database su cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="b0384-115">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="b0384-116">**Tutti i database**</span><span class="sxs-lookup"><span data-stu-id="b0384-116">**All databases**</span></span>  
  
     <span data-ttu-id="b0384-117">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di tempdb.</span><span class="sxs-lookup"><span data-stu-id="b0384-117">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="b0384-118">**Tutti i database di sistema**</span><span class="sxs-lookup"><span data-stu-id="b0384-118">**All system databases**</span></span>  
  
     <span data-ttu-id="b0384-119">Consente di generare un piano di manutenzione per l'esecuzione di attività di manutenzione su ogni database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di tempdb.</span><span class="sxs-lookup"><span data-stu-id="b0384-119">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="b0384-120">Non vengono eseguite attività di manutenzione sui database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b0384-120">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="b0384-121">**Tutti i database utente**</span><span class="sxs-lookup"><span data-stu-id="b0384-121">**All user databases**</span></span>  
  
     <span data-ttu-id="b0384-122">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b0384-122">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="b0384-123">Nessuna attività di manutenzione viene eseguita sui database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0384-123">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="b0384-124">**Database specifici**</span><span class="sxs-lookup"><span data-stu-id="b0384-124">**These specific databases**</span></span>  
  
     <span data-ttu-id="b0384-125">Consente di generare un piano per l'esecuzione di attività di manutenzione solo sui database selezionati.</span><span class="sxs-lookup"><span data-stu-id="b0384-125">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="b0384-126">Se si sceglie questa opzione, è necessario selezionare almeno un database nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b0384-126">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b0384-127">I piani di manutenzione vengono eseguiti solo nei database per i quali è impostato un livello di compatibilità 80 o superiore.</span><span class="sxs-lookup"><span data-stu-id="b0384-127">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="b0384-128">I database per cui è impostato un livello di compatibilità 70 o inferiore non vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="b0384-128">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="b0384-129">**Object**</span><span class="sxs-lookup"><span data-stu-id="b0384-129">**Object**</span></span>  
 <span data-ttu-id="b0384-130">Consente di limitare la griglia **Selezione** per visualizzare tabelle, viste o entrambe.</span><span class="sxs-lookup"><span data-stu-id="b0384-130">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="b0384-131">**Selezione**</span><span class="sxs-lookup"><span data-stu-id="b0384-131">**Selection**</span></span>  
 <span data-ttu-id="b0384-132">Specificare le tabelle o gli indici su cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="b0384-132">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="b0384-133">Questa opzione non è disponibile quando si seleziona **Tabelle e viste** nella casella Oggetto.</span><span class="sxs-lookup"><span data-stu-id="b0384-133">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="b0384-134">**Riorganizza le pagine mantenendo la quantità predefinita di spazio disponibile**</span><span class="sxs-lookup"><span data-stu-id="b0384-134">**Reorganize pages with the default amount of free space**</span></span>  
 <span data-ttu-id="b0384-135">Se si seleziona questa opzione, gli indici delle tabelle del database vengono eliminati e quindi ricreati utilizzando il fattore di riempimento specificato al momento della creazione degli indici.</span><span class="sxs-lookup"><span data-stu-id="b0384-135">Drop the indexes on the tables in the database and re-create them with the fill factor that was specified when the indexes were created.</span></span>  
  
 <span data-ttu-id="b0384-136">**Modifica percentuale di spazio disponibile per pagina in**</span><span class="sxs-lookup"><span data-stu-id="b0384-136">**Change free space per page percentage to**</span></span>  
 <span data-ttu-id="b0384-137">Elimina gli indici delle tabelle del database e li ricrea utilizzando un nuovo fattore di riempimento calcolato automaticamente, riservando in tal modo la quantità di spazio disponibile specificata nelle pagine dell'indice.</span><span class="sxs-lookup"><span data-stu-id="b0384-137">Drop the indexes on the tables in the database and re-create them with a new, automatically calculated fill factor, thereby reserving the specified amount of free space on the index pages.</span></span> <span data-ttu-id="b0384-138">Maggiore è la percentuale, maggiore sarà la quantità di spazio disponibile riservata nelle pagine dell'indice e maggiori saranno le dimensioni dell'indice.</span><span class="sxs-lookup"><span data-stu-id="b0384-138">The higher the percentage, the more free space is reserved on the index pages, and the larger the index grows.</span></span> <span data-ttu-id="b0384-139">I valori validi sono compresi tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="b0384-139">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="b0384-140">**Ordina risultati in tempdb**</span><span class="sxs-lookup"><span data-stu-id="b0384-140">**Sort results in tempdb**</span></span>  
 <span data-ttu-id="b0384-141">Utilizzare l' `SORT_IN_TEMPDB` opzione, che determina la posizione in cui i risultati intermedi dell'ordinamento, generati durante la creazione dell'indice, vengono archiviati temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b0384-141">Use the `SORT_IN_TEMPDB`option, which determines where the intermediate sort results, generated during index creation, are temporarily stored.</span></span> <span data-ttu-id="b0384-142">Se non è necessario eseguire un'operazione di ordinamento o se l'ordinamento può essere eseguito in memoria, l'opzione `SORT_IN_TEMPDB`viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="b0384-142">If a sort operation is not required, or if the sort can be performed in memory, the `SORT_IN_TEMPDB`option is ignored.</span></span>  
  
 <span data-ttu-id="b0384-143">**Mantieni indici online durante la reindicizzazione**</span><span class="sxs-lookup"><span data-stu-id="b0384-143">**Keep index online while reindexing**</span></span>  
 <span data-ttu-id="b0384-144">Utilizzare l'opzione `ONLINE` per consentire agli utenti di accedere alla tabella o ai dati dell'indice cluster sottostanti, nonché agli eventuali indici non cluster associati durante le operazioni sugli indici.</span><span class="sxs-lookup"><span data-stu-id="b0384-144">Use the `ONLINE` option which allows users to access the underlying table or clustered index data and any associated nonclustered indexes during index operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0384-145">Le operazioni sugli indici online sono disponibili solo in alcune edizioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0384-145">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b0384-146">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="b0384-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="b0384-147">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="b0384-147">**View T-SQL**</span></span>  
 <span data-ttu-id="b0384-148">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="b0384-148">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0384-149">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="b0384-149">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="b0384-150">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="b0384-150">New Connection Dialog Box</span></span>  
 <span data-ttu-id="b0384-151">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="b0384-151">**Connection name**</span></span>  
 <span data-ttu-id="b0384-152">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="b0384-152">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="b0384-153">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="b0384-153">**Select or enter a server name**</span></span>  
 <span data-ttu-id="b0384-154">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b0384-154">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="b0384-155">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="b0384-155">**Refresh**</span></span>  
 <span data-ttu-id="b0384-156">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="b0384-156">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="b0384-157">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="b0384-157">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="b0384-158">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="b0384-158">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="b0384-159">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="b0384-159">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="b0384-160">Consente di connettersi a un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilizzando l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="b0384-160">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="b0384-161">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="b0384-161">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="b0384-162">Consente di connettersi a un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilizzando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0384-162">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="b0384-163">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b0384-163">This option is not available.</span></span>  
  
 <span data-ttu-id="b0384-164">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="b0384-164">**User name**</span></span>  
 <span data-ttu-id="b0384-165">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b0384-165">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="b0384-166">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b0384-166">This option is not available.</span></span>  
  
 <span data-ttu-id="b0384-167">**Password**</span><span class="sxs-lookup"><span data-stu-id="b0384-167">**Password**</span></span>  
 <span data-ttu-id="b0384-168">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b0384-168">Provide a password to use when authenticating.</span></span> <span data-ttu-id="b0384-169">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b0384-169">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0384-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0384-170">See Also</span></span>  
 <span data-ttu-id="b0384-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b0384-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="b0384-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b0384-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span></span>  
 <span data-ttu-id="b0384-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b0384-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="b0384-174">[Opzione SORT_IN_TEMPDB per gli indici](../indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="b0384-174">[SORT_IN_TEMPDB Option For Indexes](../indexes/indexes.md) </span></span>  
 <span data-ttu-id="b0384-175">[Linee guida per operazioni di indice online](../indexes/guidelines-for-online-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="b0384-175">[Guidelines for Online Index Operations](../indexes/guidelines-for-online-index-operations.md) </span></span>  
 <span data-ttu-id="b0384-176">[Funzionamento delle operazioni sugli indici online](../indexes/how-online-index-operations-work.md) </span><span class="sxs-lookup"><span data-stu-id="b0384-176">[How Online Index Operations Work](../indexes/how-online-index-operations-work.md) </span></span>  
 [<span data-ttu-id="b0384-177">Eseguire operazioni online sugli indici</span><span class="sxs-lookup"><span data-stu-id="b0384-177">Perform Index Operations Online</span></span>](../indexes/perform-index-operations-online.md)  
  
  
