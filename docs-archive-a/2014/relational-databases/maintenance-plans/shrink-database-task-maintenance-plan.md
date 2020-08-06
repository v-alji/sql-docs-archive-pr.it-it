---
title: Attività Compatta database (Piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.shrink.f1
- Shrink Database Task
- Shrink Database(s) Task
helpviewer_keywords:
- Shrink Database Task dialog box
ms.assetid: a9874cac-cded-4145-9c38-8aafd267dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8ee6060a4ee6ca3272434cf3d9115638a675e62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715244"
---
# <a name="shrink-database-task-maintenance-plan"></a><span data-ttu-id="d9319-102">Attività Compatta database (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="d9319-102">Shrink Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="d9319-103">Usare la finestra di dialogo **Attività Compatta database** per creare un'attività che cerchi di ridurre le dimensioni dei database selezionati.</span><span class="sxs-lookup"><span data-stu-id="d9319-103">Use the **Shrink Database Task** dialog to create a task that attempts to reduce the size of the selected databases.</span></span> <span data-ttu-id="d9319-104">Le opzioni illustrate di seguito consentono di definire la quantità di spazio non utilizzato che deve rimanere nel database dopo la compattazione. Maggiore è la percentuale specificata, minore sarà il livello di compattazione del database.</span><span class="sxs-lookup"><span data-stu-id="d9319-104">Use the options below to determine the amount of unused space to remain in the database after the database is shrunk (the larger the percentage, the less the database can shrink).</span></span> <span data-ttu-id="d9319-105">Il valore è basato sulla percentuale dei dati effettivi presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="d9319-105">The value is based on the percentage of the actual data in the database.</span></span> <span data-ttu-id="d9319-106">Compattando ad esempio un database da 100 MB contenente 60 MB di dati e 40 MB di spazio disponibile con una percentuale di spazio disponibile del 50%, si ottiene un database con 60 MB di dati e 30 MB di spazio disponibile, perché il 50% di 60 MB è pari a 30 MB.</span><span class="sxs-lookup"><span data-stu-id="d9319-106">For example, a 100-MB database containing 60 MB of data and 40 MB of free space, with a free space percentage of 50 percent, would result in 60 MB of data and 30 MB of free space (because 50 percent of 60 MB is 30 MB).</span></span> <span data-ttu-id="d9319-107">Viene eliminato dal database solo lo spazio in eccesso.</span><span class="sxs-lookup"><span data-stu-id="d9319-107">Only excess space in the database is eliminated.</span></span> <span data-ttu-id="d9319-108">I valori validi sono compresi tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="d9319-108">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="d9319-109">Compattando i file di dati si recupera spazio spostando le pagine di dati dalla fine del file allo spazio non occupato più vicino all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="d9319-109">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="d9319-110">Quando alla fine del file viene creato sufficiente spazio libero, le pagine di dati possono essere deallocate e restituite al file system.</span><span class="sxs-lookup"><span data-stu-id="d9319-110">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d9319-111">I dati spostati per ridurre un file possono essere dispersi in qualsiasi percorso disponibile nel file,</span><span class="sxs-lookup"><span data-stu-id="d9319-111">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="d9319-112">provocando la frammentazione dell'indice e rallentando le prestazioni di query che eseguono ricerche in un intervallo dell'indice</span><span class="sxs-lookup"><span data-stu-id="d9319-112">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="d9319-113">Per eliminare la frammentazione, valutare la possibilità di ricompilare gli indici sul file dopo la compattazione.</span><span class="sxs-lookup"><span data-stu-id="d9319-113">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
 <span data-ttu-id="d9319-114">Questa attività esegue l'istruzione DBCC SHRINKDATABASE.</span><span class="sxs-lookup"><span data-stu-id="d9319-114">This task executes the DBCC SHRINKDATABASE statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d9319-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d9319-115">Options</span></span>  
 <span data-ttu-id="d9319-116">**Connection**</span><span class="sxs-lookup"><span data-stu-id="d9319-116">**Connection**</span></span>  
 <span data-ttu-id="d9319-117">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d9319-117">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="d9319-118">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="d9319-118">**New**</span></span>  
 <span data-ttu-id="d9319-119">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d9319-119">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="d9319-120">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="d9319-120">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="d9319-121">**Database**</span><span class="sxs-lookup"><span data-stu-id="d9319-121">**Databases**</span></span>  
 <span data-ttu-id="d9319-122">Consente di specificare i database su cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="d9319-122">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="d9319-123">**Tutti i database**</span><span class="sxs-lookup"><span data-stu-id="d9319-123">**All databases**</span></span>  
  
     <span data-ttu-id="d9319-124">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ad eccezione di tempdb.</span><span class="sxs-lookup"><span data-stu-id="d9319-124">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="d9319-125">**Tutti i database di sistema**</span><span class="sxs-lookup"><span data-stu-id="d9319-125">**All system databases**</span></span>  
  
     <span data-ttu-id="d9319-126">Consente di generare un piano di manutenzione per l'esecuzione di attività di manutenzione su ogni database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di tempdb.</span><span class="sxs-lookup"><span data-stu-id="d9319-126">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="d9319-127">Non vengono eseguite attività di manutenzione sui database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d9319-127">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="d9319-128">**Tutti i database utente**</span><span class="sxs-lookup"><span data-stu-id="d9319-128">**All user databases**</span></span>  
  
     <span data-ttu-id="d9319-129">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d9319-129">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="d9319-130">Nessuna attività di manutenzione viene eseguita sui database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9319-130">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="d9319-131">**I database seguenti**</span><span class="sxs-lookup"><span data-stu-id="d9319-131">**These databases**</span></span>  
  
     <span data-ttu-id="d9319-132">Consente di generare un piano per l'esecuzione di attività di manutenzione solo sui database selezionati.</span><span class="sxs-lookup"><span data-stu-id="d9319-132">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="d9319-133">Se si sceglie questa opzione, è necessario selezionare almeno un database nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d9319-133">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9319-134">I piani di manutenzione vengono eseguiti solo nei database per i quali è impostato un livello di compatibilità 80 o superiore.</span><span class="sxs-lookup"><span data-stu-id="d9319-134">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="d9319-135">I database per cui è impostato un livello di compatibilità 70 o inferiore non vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="d9319-135">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="d9319-136">**Compatta database quando le dimensioni superano**</span><span class="sxs-lookup"><span data-stu-id="d9319-136">**Shrink database when it grows beyond**</span></span>  
 <span data-ttu-id="d9319-137">Specificare le dimensioni in megabyte che causano l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d9319-137">Specify the size in megabytes that causes the task to execute.</span></span>  
  
 <span data-ttu-id="d9319-138">**Spazio che deve rimanere disponibile dopo la compattazione**</span><span class="sxs-lookup"><span data-stu-id="d9319-138">**Amount of free space to remain after shrink**</span></span>  
 <span data-ttu-id="d9319-139">Consente di arrestare l'operazione di compattazione quando lo spazio disponibile nei file di database raggiunge le dimensioni specificate.</span><span class="sxs-lookup"><span data-stu-id="d9319-139">Stop shrinking when free space in database files reaches this size.</span></span>  
  
 <span data-ttu-id="d9319-140">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="d9319-140">**View T-SQL**</span></span>  
 <span data-ttu-id="d9319-141">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="d9319-141">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9319-142">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="d9319-142">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="d9319-143">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="d9319-143">New Connection Dialog Box</span></span>  
 <span data-ttu-id="d9319-144">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="d9319-144">**Connection name**</span></span>  
 <span data-ttu-id="d9319-145">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="d9319-145">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="d9319-146">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="d9319-146">**Select or enter a server name**</span></span>  
 <span data-ttu-id="d9319-147">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d9319-147">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="d9319-148">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="d9319-148">**Refresh**</span></span>  
 <span data-ttu-id="d9319-149">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="d9319-149">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="d9319-150">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="d9319-150">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="d9319-151">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="d9319-151">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="d9319-152">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="d9319-152">**Use Windows NT Integrated security**</span></span>  
 <span data-ttu-id="d9319-153">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="d9319-153">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="d9319-154">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="d9319-154">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="d9319-155">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9319-155">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="d9319-156">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d9319-156">This option is not available.</span></span>  
  
 <span data-ttu-id="d9319-157">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="d9319-157">**User name**</span></span>  
 <span data-ttu-id="d9319-158">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d9319-158">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="d9319-159">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d9319-159">This option is not available.</span></span>  
  
 <span data-ttu-id="d9319-160">**Password**</span><span class="sxs-lookup"><span data-stu-id="d9319-160">**Password**</span></span>  
 <span data-ttu-id="d9319-161">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d9319-161">Provide a password to use when authenticating.</span></span> <span data-ttu-id="d9319-162">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d9319-162">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9319-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9319-163">See Also</span></span>  
 [<span data-ttu-id="d9319-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d9319-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql)  
  
  
