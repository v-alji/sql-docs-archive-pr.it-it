---
title: Attività Esegui processo di SQL Server Agent (Piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.executejob.f1
helpviewer_keywords:
- Execute SQL Server Agent Job Task dialog box
ms.assetid: 4ed75956-ebb8-4d8c-9c16-fc0eb00bd3a0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b997d5144b113102ba0ed2d9d1df59b6707acbee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635565"
---
# <a name="execute-sql-server-agent-job-task-maintenance-plan"></a><span data-ttu-id="2ecba-102">Attività Esegui processo di SQL Server Agent (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="2ecba-102">Execute SQL Server Agent Job Task (Maintenance Plan)</span></span>
  <span data-ttu-id="2ecba-103">Utilizzare la finestra di dialogo **Attività Esegui processo di SQL Server Agent** per eseguire i processi di Microsoft SQL Server Agent nell'ambito di un piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="2ecba-103">Use the **Execute SQL Server Agent Job Task** dialog to execute Microsoft SQL Server Agent jobs within a maintenance plan.</span></span> <span data-ttu-id="2ecba-104">Questa opzione non sarà disponibile se la connessione selezionata non contiene alcun processo di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="2ecba-104">This option will not be available if you have no SQL Server Agent jobs on the selected connection.</span></span>  
  
 <span data-ttu-id="2ecba-105">Questa attività usa l'istruzione **.sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="2ecba-105">This task uses the **.sp_start_job** statement.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2ecba-106">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2ecba-106">UI element list</span></span>  
 <span data-ttu-id="2ecba-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="2ecba-107">**Connection**</span></span>  
 <span data-ttu-id="2ecba-108">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2ecba-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="2ecba-109">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="2ecba-109">**New**</span></span>  
 <span data-ttu-id="2ecba-110">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2ecba-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="2ecba-111">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="2ecba-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="2ecba-112">**Processi di SQL Server Agent disponibili**</span><span class="sxs-lookup"><span data-stu-id="2ecba-112">**Available SQL Agent jobs**</span></span>  
 <span data-ttu-id="2ecba-113">Consente di selezionare il processo da eseguire.</span><span class="sxs-lookup"><span data-stu-id="2ecba-113">Select the job to execute.</span></span> <span data-ttu-id="2ecba-114">Nella griglia vengono visualizzati il **Nome processo** e la **Descrizione** per identificare i processi.</span><span class="sxs-lookup"><span data-stu-id="2ecba-114">The grid provides the **Job name** and **Description** to identify the jobs.</span></span>  
  
 <span data-ttu-id="2ecba-115">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="2ecba-115">**View T-SQL**</span></span>  
 <span data-ttu-id="2ecba-116">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="2ecba-116">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ecba-117">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="2ecba-117">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="2ecba-118">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="2ecba-118">New Connection Dialog Box</span></span>  
 <span data-ttu-id="2ecba-119">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="2ecba-119">**Connection name**</span></span>  
 <span data-ttu-id="2ecba-120">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="2ecba-120">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="2ecba-121">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="2ecba-121">**Select or enter a server name**</span></span>  
 <span data-ttu-id="2ecba-122">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2ecba-122">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="2ecba-123">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="2ecba-123">**Refresh**</span></span>  
 <span data-ttu-id="2ecba-124">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="2ecba-124">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="2ecba-125">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="2ecba-125">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="2ecba-126">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="2ecba-126">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="2ecba-127">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="2ecba-127">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="2ecba-128">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="2ecba-128">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="2ecba-129">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="2ecba-129">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="2ecba-130">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ecba-130">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="2ecba-131">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="2ecba-131">This option is not available.</span></span>  
  
 <span data-ttu-id="2ecba-132">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="2ecba-132">**User name**</span></span>  
 <span data-ttu-id="2ecba-133">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="2ecba-133">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="2ecba-134">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="2ecba-134">This option is not available.</span></span>  
  
 <span data-ttu-id="2ecba-135">**Password**</span><span class="sxs-lookup"><span data-stu-id="2ecba-135">**Password**</span></span>  
 <span data-ttu-id="2ecba-136">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="2ecba-136">Provide a password to use when authenticating.</span></span> <span data-ttu-id="2ecba-137">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="2ecba-137">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ecba-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ecba-138">See Also</span></span>  
 <span data-ttu-id="2ecba-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ecba-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span></span>  
 <span data-ttu-id="2ecba-140">[Creazione di un processo](../../ssms/agent/create-a-job.md) </span><span class="sxs-lookup"><span data-stu-id="2ecba-140">[Create a Job](../../ssms/agent/create-a-job.md) </span></span>  
 [<span data-ttu-id="2ecba-141">sp_start_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2ecba-141">sp_start_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql)  
  
  
