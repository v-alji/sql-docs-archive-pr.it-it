---
title: Attività Controlla integrità database (piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.integrity.f1
- sql12.swb.maint.integrity.f1
helpviewer_keywords:
- Check Database Integrity Task dialog box
ms.assetid: 3534494a-5dfe-4738-b49a-e7fabd731c47
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f786755a3b7ed5d991b4cf0e32c067e355c111ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635572"
---
# <a name="check-database-integrity-task-maintenance-plan"></a><span data-ttu-id="26fed-102">Attività Controlla integrità database (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="26fed-102">Check Database Integrity Task (Maintenance Plan)</span></span>
  <span data-ttu-id="26fed-103">Usare la finestra di dialogo **Attività Controlla integrità database** per controllare l'allocazione e l'integrità strutturale delle tabelle utente e di sistema e degli indici del database eseguendo l'istruzione `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26fed-103">Use the **Check Database Integrity Task** dialog to check the allocation and structural integrity of user and system tables, and indexes in the database, by running the `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="26fed-104">L'esecuzione di `DBCC` consente di individuare gli eventuali problemi di integrità nel database, in modo che l'amministratore di sistema o il proprietario del database possa analizzarli e correggerli in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="26fed-104">Running `DBCC` ensures that any integrity problems with the database are reported, thereby allowing them to be addressed later by a system administrator or database owner.</span></span>  
  
## <a name="options"></a><span data-ttu-id="26fed-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="26fed-105">Options</span></span>  
 <span data-ttu-id="26fed-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="26fed-106">**Connection**</span></span>  
 <span data-ttu-id="26fed-107">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="26fed-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="26fed-108">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="26fed-108">**New**</span></span>  
 <span data-ttu-id="26fed-109">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="26fed-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="26fed-110">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="26fed-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="26fed-111">**Database**</span><span class="sxs-lookup"><span data-stu-id="26fed-111">**Databases**</span></span>  
 <span data-ttu-id="26fed-112">Consente di specificare i database su cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="26fed-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="26fed-113">**Tutti i database**</span><span class="sxs-lookup"><span data-stu-id="26fed-113">**All databases**</span></span>  
  
     <span data-ttu-id="26fed-114">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ad eccezione di **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="26fed-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except **tempdb**.</span></span>  
  
-   <span data-ttu-id="26fed-115">**Tutti i database di sistema**</span><span class="sxs-lookup"><span data-stu-id="26fed-115">**All system databases**</span></span>  
  
     <span data-ttu-id="26fed-116">Consente di generare un piano per l'esecuzione delle attività di manutenzione in ogni database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="26fed-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="26fed-117">Non vengono eseguite attività di manutenzione sui database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="26fed-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="26fed-118">**Tutti i database utente**</span><span class="sxs-lookup"><span data-stu-id="26fed-118">**All user databases**</span></span>  
  
     <span data-ttu-id="26fed-119">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="26fed-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="26fed-120">Nessuna attività di manutenzione viene eseguita sui database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26fed-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="26fed-121">**Database specifici**</span><span class="sxs-lookup"><span data-stu-id="26fed-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="26fed-122">Consente di generare un piano per l'esecuzione di attività di manutenzione solo sui database selezionati.</span><span class="sxs-lookup"><span data-stu-id="26fed-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="26fed-123">Se si sceglie questa opzione, è necessario selezionare almeno un database nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="26fed-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26fed-124">I piani di manutenzione vengono eseguiti solo nei database per i quali è impostato un livello di compatibilità 80 o superiore.</span><span class="sxs-lookup"><span data-stu-id="26fed-124">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="26fed-125">I database per cui è impostato un livello di compatibilità 70 o inferiore non vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="26fed-125">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="26fed-126">**Includi indici**</span><span class="sxs-lookup"><span data-stu-id="26fed-126">**Include indexes**</span></span>  
 <span data-ttu-id="26fed-127">Viene controllata l'integrità di tutte le pagine di indice, nonché delle pagine dei dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="26fed-127">Check the integrity of all the index pages as well as the table data pages.</span></span>  
  
 <span data-ttu-id="26fed-128">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="26fed-128">**View T-SQL**</span></span>  
 <span data-ttu-id="26fed-129">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="26fed-129">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26fed-130">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="26fed-130">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="26fed-131">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="26fed-131">New Connection Dialog Box</span></span>  
 <span data-ttu-id="26fed-132">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="26fed-132">**Connection name**</span></span>  
 <span data-ttu-id="26fed-133">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="26fed-133">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="26fed-134">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="26fed-134">**Select or enter a server name**</span></span>  
 <span data-ttu-id="26fed-135">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="26fed-135">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="26fed-136">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="26fed-136">**Refresh**</span></span>  
 <span data-ttu-id="26fed-137">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="26fed-137">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="26fed-138">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="26fed-138">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="26fed-139">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="26fed-139">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="26fed-140">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="26fed-140">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="26fed-141">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="26fed-141">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="26fed-142">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="26fed-142">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="26fed-143">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26fed-143">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="26fed-144">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="26fed-144">This option is not available.</span></span>  
  
 <span data-ttu-id="26fed-145">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="26fed-145">**User name**</span></span>  
 <span data-ttu-id="26fed-146">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="26fed-146">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="26fed-147">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="26fed-147">This option is not available.</span></span>  
  
 <span data-ttu-id="26fed-148">**Password**</span><span class="sxs-lookup"><span data-stu-id="26fed-148">**Password**</span></span>  
 <span data-ttu-id="26fed-149">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="26fed-149">Provide a password to use when authenticating.</span></span> <span data-ttu-id="26fed-150">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="26fed-150">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26fed-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26fed-151">See Also</span></span>  
 [<span data-ttu-id="26fed-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="26fed-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
