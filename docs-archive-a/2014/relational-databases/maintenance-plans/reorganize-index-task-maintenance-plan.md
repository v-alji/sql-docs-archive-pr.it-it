---
title: Attività Riorganizza indice (Piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.defrag.f1
helpviewer_keywords:
- Reorganize Index Task dialog box
ms.assetid: e9cbebbd-f36f-4176-9832-382a46ac946c
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bbb154045b781f8a92dfce9c9d2f6ee2d819c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627222"
---
# <a name="reorganize-index-task-maintenance-plan"></a><span data-ttu-id="afd8d-102">Attività Riorganizza indice (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="afd8d-102">Reorganize Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="afd8d-103">Usare la finestra di dialogo **Attività Riorganizza indice** per razionalizzare l'ordine di ricerca delle pagine dell'indice.</span><span class="sxs-lookup"><span data-stu-id="afd8d-103">Use the **ReorganizeIndex Task** dialog to move index pages into a more efficient search order.</span></span> <span data-ttu-id="afd8d-104">In questa attività viene utilizzata l'istruzione `ALTER INDEX REORGANIZE` con i database di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="afd8d-104">This task uses the `ALTER INDEX REORGANIZE` statement with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] databases.</span></span>  
  
## <a name="options"></a><span data-ttu-id="afd8d-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="afd8d-105">Options</span></span>  
 <span data-ttu-id="afd8d-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="afd8d-106">**Connection**</span></span>  
 <span data-ttu-id="afd8d-107">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="afd8d-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="afd8d-108">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="afd8d-108">**New**</span></span>  
 <span data-ttu-id="afd8d-109">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="afd8d-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="afd8d-110">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="afd8d-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="afd8d-111">**Database**</span><span class="sxs-lookup"><span data-stu-id="afd8d-111">**Databases**</span></span>  
 <span data-ttu-id="afd8d-112">Consente di specificare i database su cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="afd8d-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="afd8d-113">**Tutti i database**</span><span class="sxs-lookup"><span data-stu-id="afd8d-113">**All databases**</span></span>  
  
     <span data-ttu-id="afd8d-114">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di tempdb.</span><span class="sxs-lookup"><span data-stu-id="afd8d-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="afd8d-115">**Tutti i database di sistema**</span><span class="sxs-lookup"><span data-stu-id="afd8d-115">**All system databases**</span></span>  
  
     <span data-ttu-id="afd8d-116">Consente di generare un piano per l'esecuzione delle attività di manutenzione in ogni database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="afd8d-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="afd8d-117">Non vengono eseguite attività di manutenzione sui database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="afd8d-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="afd8d-118">**Tutti i database utente**</span><span class="sxs-lookup"><span data-stu-id="afd8d-118">**All user databases**</span></span>  
  
     <span data-ttu-id="afd8d-119">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="afd8d-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="afd8d-120">Nessuna attività di manutenzione viene eseguita sui database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="afd8d-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="afd8d-121">**Database specifici**</span><span class="sxs-lookup"><span data-stu-id="afd8d-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="afd8d-122">Consente di generare un piano per l'esecuzione di attività di manutenzione solo sui database selezionati.</span><span class="sxs-lookup"><span data-stu-id="afd8d-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="afd8d-123">Se si sceglie questa opzione, è necessario selezionare almeno un database nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="afd8d-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="afd8d-124">**Object**</span><span class="sxs-lookup"><span data-stu-id="afd8d-124">**Object**</span></span>  
 <span data-ttu-id="afd8d-125">Consente di limitare la griglia **Selezione** per visualizzare tabelle, viste o entrambe.</span><span class="sxs-lookup"><span data-stu-id="afd8d-125">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="afd8d-126">**Selezione**</span><span class="sxs-lookup"><span data-stu-id="afd8d-126">**Selection**</span></span>  
 <span data-ttu-id="afd8d-127">Specificare le tabelle o gli indici su cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="afd8d-127">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="afd8d-128">Questa opzione non è disponibile quando si seleziona **Tabelle e viste** nella casella **Oggetto** .</span><span class="sxs-lookup"><span data-stu-id="afd8d-128">Not available when **Tables and Views** is selected in the **Object** box.</span></span>  
  
 <span data-ttu-id="afd8d-129">**Compatta oggetti di grandi dimensioni**</span><span class="sxs-lookup"><span data-stu-id="afd8d-129">**Compact large objects**</span></span>  
 <span data-ttu-id="afd8d-130">Dealloca spazio per tabelle e viste, se possibile.</span><span class="sxs-lookup"><span data-stu-id="afd8d-130">Deallocate space for tables and views when possible.</span></span> <span data-ttu-id="afd8d-131">Questa opzione utilizza l'istruzione `ALTER INDEX LOB_COMPACTION = ON`</span><span class="sxs-lookup"><span data-stu-id="afd8d-131">This option uses `ALTER INDEX LOB_COMPACTION = ON`.</span></span>  
  
 <span data-ttu-id="afd8d-132">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="afd8d-132">**View T-SQL**</span></span>  
 <span data-ttu-id="afd8d-133">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="afd8d-133">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afd8d-134">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="afd8d-134">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="afd8d-135">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="afd8d-135">New Connection Dialog Box</span></span>  
 <span data-ttu-id="afd8d-136">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="afd8d-136">**Connection name**</span></span>  
 <span data-ttu-id="afd8d-137">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="afd8d-137">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="afd8d-138">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="afd8d-138">**Select or enter a server name**</span></span>  
 <span data-ttu-id="afd8d-139">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="afd8d-139">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="afd8d-140">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="afd8d-140">**Refresh**</span></span>  
 <span data-ttu-id="afd8d-141">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="afd8d-141">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="afd8d-142">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="afd8d-142">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="afd8d-143">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="afd8d-143">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="afd8d-144">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="afd8d-144">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="afd8d-145">Consente di connettersi a un'istanza del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="afd8d-145">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="afd8d-146">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="afd8d-146">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="afd8d-147">Consente di connettersi a un'istanza del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afd8d-147">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="afd8d-148">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="afd8d-148">This option is not available.</span></span>  
  
 <span data-ttu-id="afd8d-149">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="afd8d-149">**User name**</span></span>  
 <span data-ttu-id="afd8d-150">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="afd8d-150">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="afd8d-151">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="afd8d-151">This option is not available.</span></span>  
  
 <span data-ttu-id="afd8d-152">**Password**</span><span class="sxs-lookup"><span data-stu-id="afd8d-152">**Password**</span></span>  
 <span data-ttu-id="afd8d-153">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="afd8d-153">Provide a password to use when authenticating.</span></span> <span data-ttu-id="afd8d-154">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="afd8d-154">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afd8d-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afd8d-155">See Also</span></span>  
 <span data-ttu-id="afd8d-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd8d-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="afd8d-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="afd8d-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql)  
  
  
