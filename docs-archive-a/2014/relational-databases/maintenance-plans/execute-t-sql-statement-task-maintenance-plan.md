---
title: Attività Esegui istruzione T-SQL (Piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.tsql.f1
helpviewer_keywords:
- Execute T-SQL Statement Task dialog box
ms.assetid: fef3e259-0c47-4f6e-ade0-aee95e3d6c1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63738758ce228a51ab6c75eb11a681eec3b27352
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635566"
---
# <a name="execute-t-sql-statement-task-maintenance-plan"></a><span data-ttu-id="48cd4-102">Attività Esegui istruzione T-SQL (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="48cd4-102">Execute T-SQL Statement Task (Maintenance Plan)</span></span>
  <span data-ttu-id="48cd4-103">Utilizzare la finestra di dialogo **Attività Esegui istruzione T-SQL** per personalizzare il piano di manutenzione con l'aggiunta delle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] desiderate.</span><span class="sxs-lookup"><span data-stu-id="48cd4-103">Use the **Execute T-SQL Statement Task** dialog to customize your maintenance plan by adding [!INCLUDE[tsql](../../includes/tsql-md.md)] statements of your choice to this maintenance plan.</span></span>  
  
## <a name="options"></a><span data-ttu-id="48cd4-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="48cd4-104">Options</span></span>  
 <span data-ttu-id="48cd4-105">**Connection**</span><span class="sxs-lookup"><span data-stu-id="48cd4-105">**Connection**</span></span>  
 <span data-ttu-id="48cd4-106">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="48cd4-106">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="48cd4-107">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="48cd4-107">**New**</span></span>  
 <span data-ttu-id="48cd4-108">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="48cd4-108">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="48cd4-109">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="48cd4-109">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="48cd4-110">**Timeout esecuzione**</span><span class="sxs-lookup"><span data-stu-id="48cd4-110">**Execution time out**</span></span>  
 <span data-ttu-id="48cd4-111">Numero di secondi di attesa del completamento dell'attività trascorsi i quali si verifica il timeout, ovvero l'attività viene terminata.</span><span class="sxs-lookup"><span data-stu-id="48cd4-111">Time (seconds) to wait for task completion before timing out (terminating task).</span></span>  
  
 <span data-ttu-id="48cd4-112">**Istruzione T-SQL**</span><span class="sxs-lookup"><span data-stu-id="48cd4-112">**T-SQL statement**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="48cd4-113">istruzioni da eseguire.</span><span class="sxs-lookup"><span data-stu-id="48cd4-113">statements to execute.</span></span>  
  
 <span data-ttu-id="48cd4-114">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="48cd4-114">**View T-SQL**</span></span>  
 <span data-ttu-id="48cd4-115">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="48cd4-115">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48cd4-116">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="48cd4-116">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="48cd4-117">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="48cd4-117">New Connection Dialog Box</span></span>  
 <span data-ttu-id="48cd4-118">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="48cd4-118">**Connection name**</span></span>  
 <span data-ttu-id="48cd4-119">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="48cd4-119">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="48cd4-120">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="48cd4-120">**Select or enter a server name**</span></span>  
 <span data-ttu-id="48cd4-121">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="48cd4-121">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="48cd4-122">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="48cd4-122">**Refresh**</span></span>  
 <span data-ttu-id="48cd4-123">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="48cd4-123">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="48cd4-124">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="48cd4-124">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="48cd4-125">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="48cd4-125">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="48cd4-126">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="48cd4-126">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="48cd4-127">Consente di connettersi a un'istanza del [!INCLUDE[msCoName](../../includes/msconame-md.md)] di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usando l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="48cd4-127">Connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="48cd4-128">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="48cd4-128">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="48cd4-129">Consente di connettersi a un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilizzando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48cd4-129">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="48cd4-130">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="48cd4-130">This option is not available.</span></span>  
  
 <span data-ttu-id="48cd4-131">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="48cd4-131">**User name**</span></span>  
 <span data-ttu-id="48cd4-132">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="48cd4-132">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="48cd4-133">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="48cd4-133">This option is not available.</span></span>  
  
 <span data-ttu-id="48cd4-134">**Password**</span><span class="sxs-lookup"><span data-stu-id="48cd4-134">**Password**</span></span>  
 <span data-ttu-id="48cd4-135">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="48cd4-135">Provide a password to use when authenticating.</span></span> <span data-ttu-id="48cd4-136">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="48cd4-136">This option is not available.</span></span>  
  
  
