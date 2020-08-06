---
title: Aggiungere un gestore eventi a un pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- event handlers [Integration Services], creating
ms.assetid: 5e56885d-8658-480a-bed9-3f2f8003fd78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 007d81a395e06ac5a97210cd3e3ed6eea91aee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627965"
---
# <a name="add-an-event-handler-to-a-package"></a><span data-ttu-id="8c3d9-102">Aggiunta di un gestore eventi a un pacchetto</span><span class="sxs-lookup"><span data-stu-id="8c3d9-102">Add an Event Handler to a Package</span></span>
  <span data-ttu-id="8c3d9-103">In fase di esecuzione contenitori e attività generano eventi.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-103">At run time, containers and tasks raise events.</span></span> <span data-ttu-id="8c3d9-104">È possibile creare gestori di eventi personalizzati che rispondono a tali eventi eseguendo un flusso di lavoro alla generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-104">You can create custom event handlers that respond to these events by running a workflow when the event is raised.</span></span> <span data-ttu-id="8c3d9-105">Ad esempio, è possibile creare un gestore di evento che invia un messaggio di posta elettronica quando un'attività non viene completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-105">For example, you can create an event handler that sends an e-mail message when a task fails.</span></span>  
  
 <span data-ttu-id="8c3d9-106">Un gestore di evento è simile a un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-106">An event handler is similar to a package.</span></span> <span data-ttu-id="8c3d9-107">Come un pacchetto, può fornire un ambito per le variabili e includere un flusso di controllo, oltre a flussi di dati facoltativi.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-107">Like a package, an event handler can provide scope for variables, and includes a control flow and optional data flows.</span></span> <span data-ttu-id="8c3d9-108">È possibile compilare gestori di eventi per i pacchetti, per il contenitore Ciclo Foreach, per il contenitore Ciclo For, per il contenitore Sequenza e per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-108">You can build event handlers for packages, the Foreach Loop container, the For Loop container, the Sequence container, and all tasks.</span></span>  
  
 <span data-ttu-id="8c3d9-109">Per creare i gestori di eventi è possibile usare l'area di progettazione della scheda **Gestori eventi** in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c3d9-109">You create event handlers by using the design surface of the **Event Handlers** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="8c3d9-110">Quando la scheda **Gestori eventi** è attiva, nei nodi **Elementi flusso di controllo** e **Attività di manutenzione** della casella degli strumenti di Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] sono disponibili le attività e i contenitori necessari per la compilazione del flusso di controllo del gestore di evento.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-110">When the **Event Handlers** tab is active, the **Control Flow Items** and **Maintenance Plan Tasks** nodes of the Toolbox in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer contain the task and containers for building the control flow in the event handler.</span></span> <span data-ttu-id="8c3d9-111">Nei nodi **Origini flusso di dati**, **Trasformazioni**e **Destinazioni flusso di dati** sono disponibili le origini dei dati, le trasformazioni e le destinazioni per la compilazione dei flussi di dati nel gestore di evento.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-111">The **Data Flow Sources**, **Transformations**, **and Data Flow Destinations** nodes contain the data sources, transformations, and destinations for building the data flows in the event handler.</span></span> <span data-ttu-id="8c3d9-112">Per altre informazioni, vedere [Flusso di controllo](control-flow/control-flow.md) e [Flusso di dati](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8c3d9-112">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="8c3d9-113">La scheda **Gestori eventi** include anche l'area **Gestioni connessioni** , in cui è possibile creare e modificare le gestioni connessioni usate dai gestori di eventi per connettersi a server e origini dei dati.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-113">The **Event Handlers** tab also includes the **Connections** Managers area where you can create and modify the connection managers that event handlers use to connect to servers and data sources.</span></span> <span data-ttu-id="8c3d9-114">Per altre informazioni, vedere [Creazione di gestioni connessioni](../../2014/integration-services/create-connection-managers.md).</span><span class="sxs-lookup"><span data-stu-id="8c3d9-114">For more information, see [Create Connection Managers](../../2014/integration-services/create-connection-managers.md).</span></span>  
  
### <a name="to-create-an-event-handler"></a><span data-ttu-id="8c3d9-115">Per creare un gestore dell'evento</span><span class="sxs-lookup"><span data-stu-id="8c3d9-115">To create an event handler</span></span>  
  
1.  <span data-ttu-id="8c3d9-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8c3d9-117">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8c3d9-118">Fare clic sulla scheda **Gestori eventi** .</span><span class="sxs-lookup"><span data-stu-id="8c3d9-118">Click the **Event Handlers** tab.</span></span>  
  
     <span data-ttu-id="8c3d9-119">![Screenshot dell'area di progettazione con gestore dell'evento](media/eventhandlers.gif "Screenshot dell'area di progettazione con gestore dell'evento")</span><span class="sxs-lookup"><span data-stu-id="8c3d9-119">![Screenshot of design surface with event handler](media/eventhandlers.gif "Screenshot of design surface with event handler")</span></span>  
  
     <span data-ttu-id="8c3d9-120">La creazione del flusso di controllo e dei flussi di dati di un gestore dell'evento è analoga alla creazione del flusso di controllo e dei flussi di dati di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-120">Creating the control flow and data flows in an event handler is similar to creating the control flow and data flows in a package.</span></span> <span data-ttu-id="8c3d9-121">Per altre informazioni, vedere [Flusso di controllo](control-flow/control-flow.md) e [Flusso di dati](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8c3d9-121">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
4.  <span data-ttu-id="8c3d9-122">Nell'elenco **File eseguibili** selezionare il file per il quale si desidera creare un gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-122">In the **Executable** list, select the executable for which you want to create an event handler.</span></span>  
  
5.  <span data-ttu-id="8c3d9-123">Nell'elenco **Gestore evento** selezionare il gestore dell'evento che si desidera compilare.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-123">In the **Event handler** list, select the event handler you want to build.</span></span>  
  
6.  <span data-ttu-id="8c3d9-124">Fare clic sul collegamento nell'area di progettazione della scheda **Gestore evento** .</span><span class="sxs-lookup"><span data-stu-id="8c3d9-124">Click the link on the design surface of the **Event Handler** tab.</span></span>  
  
7.  <span data-ttu-id="8c3d9-125">Aggiungere le voci del flusso di controllo nel gestore dell'evento, quindi connetterle tra di loro tramite un vincolo di precedenza trascinando il vincolo da una voce del flusso di controllo a un'altra.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-125">Add control flow items to the event handler, and connect items using a precedence constraint by dragging the constraint from one control flow item to another.</span></span> <span data-ttu-id="8c3d9-126">Per altre informazioni, vedere [Flusso di controllo](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8c3d9-126">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
8.  <span data-ttu-id="8c3d9-127">Facoltativamente, aggiungere un'attività Flusso di dati e nell'area di progettazione della scheda **Flusso di dati** creare un flusso di dati per il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-127">Optionally, add a Data Flow task, and on the design surface of the **Data Flow** tab, create a data flow for the event handler.</span></span> <span data-ttu-id="8c3d9-128">Per altre informazioni, vedere [Flusso di dati](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8c3d9-128">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
9. <span data-ttu-id="8c3d9-129">Scegliere **Salva elementi selezionati** dal menu **File** per salvare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8c3d9-129">On the **File** menu, click **Save Selected Items** to save the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c3d9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c3d9-130">See Also</span></span>  
 <span data-ttu-id="8c3d9-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="8c3d9-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span></span>  
 [<span data-ttu-id="8c3d9-132">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8c3d9-132">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
