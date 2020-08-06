---
title: Attività Pulizia contenuto cronologia (Piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.historycleanup.f1
helpviewer_keywords:
- History Cleanup Task dialog box
ms.assetid: 66bb6c39-958c-4053-a27f-b1118d2567f5
ms.reviewer: ''
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 03ff35b14fc13d2b4446b15501114489b52c421e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635564"
---
# <a name="history-cleanup-task-maintenance-plan"></a><span data-ttu-id="b93e3-102">Attività Pulizia contenuto cronologia (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="b93e3-102">History Cleanup Task (Maintenance Plan)</span></span>

  <span data-ttu-id="b93e3-103">Utilizzare la finestra di dialogo **Attività Pulizia contenuto cronologia** per eliminare le informazioni cronologiche meno recenti dalle tabelle del database msdb.</span><span class="sxs-lookup"><span data-stu-id="b93e3-103">Use the **History Cleanup Task** dialog to discard old historical information from tables in the msdb database.</span></span> <span data-ttu-id="b93e3-104">Questa attività supporta l'eliminazione della cronologia delle operazioni di backup e ripristino, della cronologia processo agente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e della cronologia del piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="b93e3-104">This task supports deleting backup and restore history, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job history, and maintenance plan history.</span></span>  
  
 <span data-ttu-id="b93e3-105">Questa istruzione usa le istruzioni **sp_purge_jobhistory** e **sp_delete_backuphistory** .</span><span class="sxs-lookup"><span data-stu-id="b93e3-105">This statement uses the **sp_purge_jobhistory** and **sp_delete_backuphistory** statements.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b93e3-106">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b93e3-106">UI element list</span></span>  
 <span data-ttu-id="b93e3-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="b93e3-107">**Connection**</span></span>  
 <span data-ttu-id="b93e3-108">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b93e3-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="b93e3-109">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="b93e3-109">**New**</span></span>  
 <span data-ttu-id="b93e3-110">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b93e3-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="b93e3-111">La finestra di dialogo **Nuova connessione** viene descritta più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b93e3-111">The **New Connection** dialog box is described later in this topic.</span></span>  
  
 <span data-ttu-id="b93e3-112">**Cronologia operazioni di backup e ripristino**</span><span class="sxs-lookup"><span data-stu-id="b93e3-112">**Backup and restore history**</span></span>  
 <span data-ttu-id="b93e3-113">Se si mantengono i record relativi alla data di creazione di backup recenti, è possibile semplificare la creazione di un piano di recupero da parte di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in caso si desideri ripristinare un database.</span><span class="sxs-lookup"><span data-stu-id="b93e3-113">Retaining records of when recent backups were created can help [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] create a recovery plan when you want to restore a database.</span></span> <span data-ttu-id="b93e3-114">Il periodo di memorizzazione deve essere almeno pari alla frequenza dei backup completi del database.</span><span class="sxs-lookup"><span data-stu-id="b93e3-114">The retention period should be at least the frequency of full database back ups.</span></span>  
  
 <span data-ttu-id="b93e3-115">**Cronologia processo di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="b93e3-115">**SQL Server Agent Job history**</span></span>  
 <span data-ttu-id="b93e3-116">Questa cronologia si rivela utile per risolvere problemi relativi a processi non riusciti o per individuare le cause di determinate azioni sul database.</span><span class="sxs-lookup"><span data-stu-id="b93e3-116">This history can help you troubleshoot failed jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="b93e3-117">**Cronologia piano di manutenzione**</span><span class="sxs-lookup"><span data-stu-id="b93e3-117">**Maintenance plan history**</span></span>  
 <span data-ttu-id="b93e3-118">Questa cronologia si rivela utile per risolvere problemi relativi a processi del piano di manutenzione non riusciti o per individuare le cause di determinate azioni sul database.</span><span class="sxs-lookup"><span data-stu-id="b93e3-118">This history can help you troubleshoot failed maintenance plan jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="b93e3-119">**Rimuovi dati presenti nella cronologia da più di**</span><span class="sxs-lookup"><span data-stu-id="b93e3-119">**Remove historical data older than**</span></span>  
 <span data-ttu-id="b93e3-120">Specifica il periodo di permanenza nella cronologia oltre il quale gli elementi devono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="b93e3-120">Specify age of items that you want to delete.</span></span>  
  
 <span data-ttu-id="b93e3-121">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="b93e3-121">**View T-SQL**</span></span>  
 <span data-ttu-id="b93e3-122">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="b93e3-122">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b93e3-123">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="b93e3-123">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="b93e3-124">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="b93e3-124">New Connection Dialog Box</span></span>  
 <span data-ttu-id="b93e3-125">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="b93e3-125">**Connection name**</span></span>  
 <span data-ttu-id="b93e3-126">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="b93e3-126">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="b93e3-127">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="b93e3-127">**Select or enter a server name**</span></span>  
 <span data-ttu-id="b93e3-128">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b93e3-128">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="b93e3-129">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="b93e3-129">**Refresh**</span></span>  
 <span data-ttu-id="b93e3-130">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="b93e3-130">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="b93e3-131">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="b93e3-131">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="b93e3-132">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="b93e3-132">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="b93e3-133">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="b93e3-133">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="b93e3-134">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di SQL Server utilizzando l'autenticazione di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="b93e3-134">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="b93e3-135">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="b93e3-135">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="b93e3-136">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di SQL Server utilizzando l'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b93e3-136">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="b93e3-137">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b93e3-137">This option is not available.</span></span>  
  
 <span data-ttu-id="b93e3-138">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="b93e3-138">**User name**</span></span>  
 <span data-ttu-id="b93e3-139">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b93e3-139">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="b93e3-140">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b93e3-140">This option is not available.</span></span>  
  
 <span data-ttu-id="b93e3-141">**Password**</span><span class="sxs-lookup"><span data-stu-id="b93e3-141">**Password**</span></span>  
 <span data-ttu-id="b93e3-142">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b93e3-142">Provide a password to use when authenticating.</span></span> <span data-ttu-id="b93e3-143">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b93e3-143">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b93e3-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b93e3-144">See Also</span></span>  
 <span data-ttu-id="b93e3-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b93e3-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span></span>  
 [<span data-ttu-id="b93e3-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b93e3-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
  
