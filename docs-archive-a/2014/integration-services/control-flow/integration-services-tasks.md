---
title: Attività di Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [Integration Services], tasks
- files [Integration Services], task options
- workflow tasks [Integration Services]
- Integration Services, tasks
- adding package tasks
- tasks [Integration Services], listed
- SSIS tasks
- SSIS, tasks
- control flow [Integration Services], tasks
- tasks [Integration Services]
- grouping tasks
- tasks [Integration Services], about tasks
- SQL Server Integration Services tasks
- data preparation tasks [Integration Services]
- directory operations [Integration Services]
ms.assetid: 75c8901d-6966-4af3-abe5-10af6dd9313b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5fa58dec1e05a0333c295efc7f00a1d6df935792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627330"
---
# <a name="integration-services-tasks"></a><span data-ttu-id="3c310-102">Attività di Integration Services</span><span class="sxs-lookup"><span data-stu-id="3c310-102">Integration Services Tasks</span></span>
  <span data-ttu-id="3c310-103">Le attività sono elementi del flusso di controllo che definiscono le unità di lavoro eseguite nel flusso di controllo di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3c310-103">Tasks are control flow elements that define units of work that are performed in a package control flow.</span></span> <span data-ttu-id="3c310-104">Un pacchetto di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è costituito da una o più attività.</span><span class="sxs-lookup"><span data-stu-id="3c310-104">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package is made up of one or more tasks.</span></span> <span data-ttu-id="3c310-105">Se il pacchetto contiene più attività, queste ultime sono connesse e ordinate in sequenza nel flusso di controllo tramite vincoli di precedenza.</span><span class="sxs-lookup"><span data-stu-id="3c310-105">If the package contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span>  
  
 <span data-ttu-id="3c310-106">È inoltre possibile creare attività personalizzate utilizzando un linguaggio di programmazione che supporta COM, ad esempio Visual Basic, oppure un linguaggio di programmazione .NET, ad esempio C#.</span><span class="sxs-lookup"><span data-stu-id="3c310-106">You can also write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span>  
  
 <span data-ttu-id="3c310-107">Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)], lo strumento grafico disponibile in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per operare sui pacchetti, offre un'area di progettazione per la creazione del flusso di controllo dei pacchetti, oltre a editor personalizzati per la configurazione delle attività.</span><span class="sxs-lookup"><span data-stu-id="3c310-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the graphical tool in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] for working with packages, provides the design surface for creating package control flow, and provides custom editors for configuring tasks.</span></span> <span data-ttu-id="3c310-108">È inoltre possibile programmare il modello a oggetti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per creare pacchetti a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="3c310-108">You can also program the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model to create packages programmatically.</span></span>  
  
## <a name="types-of-tasks"></a><span data-ttu-id="3c310-109">Tipi di attività</span><span class="sxs-lookup"><span data-stu-id="3c310-109">Types of Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="3c310-110">include i tipi di attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="3c310-110">includes the following types of tasks.</span></span>  
  
 <span data-ttu-id="3c310-111">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="3c310-111">Data Flow Task</span></span>  
 <span data-ttu-id="3c310-112">Questa attività esegue flussi di dati per estrarre dati, applicare trasformazioni a livello di colonna e caricare dati.</span><span class="sxs-lookup"><span data-stu-id="3c310-112">The task that runs data flows to extract data, apply column level transformations, and load data.</span></span>  
  
 <span data-ttu-id="3c310-113">Attività di preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="3c310-113">Data Preparation Tasks</span></span>  
 <span data-ttu-id="3c310-114">Queste attività consentono di effettuare le seguenti operazioni: copiare file e directory, scaricare file e dati, eseguire metodi Web, applicare operazioni a documenti XML ed eseguire il profiling dei dati per la pulitura.</span><span class="sxs-lookup"><span data-stu-id="3c310-114">These tasks do the following processes: copy files and directories; download files and data; run Web methods; apply operations to XML documents; and profile data for cleansing.</span></span>  
  
 <span data-ttu-id="3c310-115">Attività di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3c310-115">Workflow Tasks</span></span>  
 <span data-ttu-id="3c310-116">Queste attività comunicano con altri processi per eseguire pacchetti, programmi o file batch, scambiare messaggi tra pacchetti, inviare messaggi di posta elettronica, leggere dati di Strumentazione gestione Windows (WMI) e monitorare eventi WMI.</span><span class="sxs-lookup"><span data-stu-id="3c310-116">The tasks that communicate with other processes to run packages, run programs or batch files, send and receive messages between packages, send e-mail messages, read Windows Management Instrumentation (WMI) data, and watch for WMI events.</span></span>  
  
 <span data-ttu-id="3c310-117">Attività di SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c310-117">SQL Server Tasks</span></span>  
 <span data-ttu-id="3c310-118">Queste attività consentono di copiare, inserire, eliminare, modificare e accedere a dati e oggetti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c310-118">The tasks that access, copy, insert, delete, and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects and data.</span></span>  
  
 <span data-ttu-id="3c310-119">Attività di scripting</span><span class="sxs-lookup"><span data-stu-id="3c310-119">Scripting Tasks</span></span>  
 <span data-ttu-id="3c310-120">Queste attività consentono di estendere le funzionalità dei pacchetti tramite script.</span><span class="sxs-lookup"><span data-stu-id="3c310-120">The tasks that extend package functionality by using scripts.</span></span>  
  
 <span data-ttu-id="3c310-121">Attività di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3c310-121">Analysis Services Tasks</span></span>  
 <span data-ttu-id="3c310-122">Queste attività consentono di creare, modificare, eliminare ed elaborare oggetti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c310-122">The tasks that create, modify, delete, and process [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="3c310-123">Attività di manutenzione</span><span class="sxs-lookup"><span data-stu-id="3c310-123">Maintenance Tasks</span></span>  
 <span data-ttu-id="3c310-124">Queste attività consentono di eseguire funzioni amministrative quali il backup e la compattazione dei database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la ricompilazione e la riorganizzazione degli indici e l'esecuzione dei processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3c310-124">The tasks that perform administrative functions such as backing up and shrinking [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, rebuilding and reorganizing indexes, and running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="3c310-125">Attività personalizzate</span><span class="sxs-lookup"><span data-stu-id="3c310-125">Custom Tasks</span></span>  
 <span data-ttu-id="3c310-126">È inoltre possibile creare attività personalizzate utilizzando un linguaggio di programmazione che supporta COM, ad esempio Visual Basic, oppure un linguaggio di programmazione .NET, ad esempio C#.</span><span class="sxs-lookup"><span data-stu-id="3c310-126">Additionally, you can write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span> <span data-ttu-id="3c310-127">Se si desidera accedere a un'attività personalizzata in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , è possibile creare e registrare un'interfaccia utente per l'attività.</span><span class="sxs-lookup"><span data-stu-id="3c310-127">If you want to access your custom task in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can create and register a user interface for the task.</span></span> <span data-ttu-id="3c310-128">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="3c310-128">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="configuration-of-tasks"></a><span data-ttu-id="3c310-129">Configurazione di attività</span><span class="sxs-lookup"><span data-stu-id="3c310-129">Configuration of Tasks</span></span>  
 <span data-ttu-id="3c310-130">Un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] può contenere una singola attività, ad esempio un'attività Esegui SQL che elimina record in una tabella di database durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3c310-130">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can contain a single task, such as an Execute SQL task that deletes records in a database table when the package runs.</span></span> <span data-ttu-id="3c310-131">I pacchetti, tuttavia, contengono molte attività, ognuna delle quali è impostata per essere eseguita nel contesto del flusso di controllo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3c310-131">However, packages typically contain several tasks, and each task is set to run within the context of the package control flow.</span></span> <span data-ttu-id="3c310-132">Possono includere attività anche i gestori di eventi, ovvero flussi di lavoro eseguiti in risposta a eventi di run-time.</span><span class="sxs-lookup"><span data-stu-id="3c310-132">Event handlers, which are workflows that run in response to run-time events, can also have tasks.</span></span>  
  
 <span data-ttu-id="3c310-133">Per altre informazioni sull'aggiunta di un'attività a un pacchetto tramite la finestra di progettazione di [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Aggiunta o eliminazione di un'attività o un contenitore in un flusso di controllo](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="3c310-133">For more information about adding a task to a package using [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span></span>  
  
 <span data-ttu-id="3c310-134">Per altre informazioni sull'aggiunta di un'attività a un pacchetto a livello di codice, vedere [Aggiunta di attività a livello di programmazione](../building-packages-programmatically/adding-tasks-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="3c310-134">For more information about adding a task to a package programmatically, see [Adding Tasks Programmatically](../building-packages-programmatically/adding-tasks-programmatically.md).</span></span>  
  
 <span data-ttu-id="3c310-135">Le attività possono essere configurate individualmente utilizzando le finestre di dialogo personalizzate per le singole attività disponibili in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] oppure la finestra Proprietà inclusa in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c310-135">Each task can be configured individually using the custom dialog boxes for each task that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides, or the Properties window included in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="3c310-136">Un pacchetto può includere più attività dello stesso tipo, ad esempio sei attività Esegui SQL, ognuna delle quali può essere configurata in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="3c310-136">A package can include multiple tasks of the same type-for example, six Execute SQL tasks-and each task can be configured differently.</span></span> <span data-ttu-id="3c310-137">Per altre informazioni, vedere [Impostazione delle proprietà di un'attività o di un contenitore](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="3c310-137">For more information, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="tasks-connections-and-groups"></a><span data-ttu-id="3c310-138">Gruppi e connessioni attività</span><span class="sxs-lookup"><span data-stu-id="3c310-138">Tasks Connections and Groups</span></span>  
 <span data-ttu-id="3c310-139">Se un'attività contiene più attività, queste ultime sono connesse e ordinate in sequenza nel flusso di controllo tramite vincoli di precedenza.</span><span class="sxs-lookup"><span data-stu-id="3c310-139">If the task contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span> <span data-ttu-id="3c310-140">Per altre informazioni, vedere [Vincoli di precedenza](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="3c310-140">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="3c310-141">Le attività possono essere raggruppate ed eseguite come una singola unità di lavoro oppure ripetute in un ciclo.</span><span class="sxs-lookup"><span data-stu-id="3c310-141">Tasks can be grouped together and performed as a single unit of work, or repeated in a loop.</span></span> <span data-ttu-id="3c310-142">Per altre informazioni, vedere [Contenitore Ciclo Foreach](foreach-loop-container.md), [Contenitore Ciclo For](for-loop-container.md)e [Contenitore Sequenza](sequence-container.md).</span><span class="sxs-lookup"><span data-stu-id="3c310-142">For more information, see [Foreach Loop Container](foreach-loop-container.md), [For Loop Container](for-loop-container.md), and [Sequence Container](sequence-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3c310-143">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="3c310-143">Related Tasks</span></span>  
 [<span data-ttu-id="3c310-144">Aggiungere o eliminare un'attività o un contenitore in un flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="3c310-144">Add or Delete a Task or a Container in a Control Flow</span></span>](add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
  
