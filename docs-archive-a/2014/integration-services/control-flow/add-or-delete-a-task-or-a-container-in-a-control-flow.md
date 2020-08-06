---
title: Aggiungere o eliminare un'attività o un contenitore in un flusso di controllo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], adding
- adding tasks
- adding containers
- tasks [Integration Services], adding
ms.assetid: 653084c6-87a3-45d5-b458-914ecf24d56a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8338a4143358d732a974287e587f482dc5c36a22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629564"
---
# <a name="add-or-delete-a-task-or-a-container-in-a-control-flow"></a><span data-ttu-id="b0fc9-102">Aggiunta o eliminazione di un'attività o un contenitore in un flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="b0fc9-102">Add or Delete a Task or a Container in a Control Flow</span></span>
  <span data-ttu-id="b0fc9-103">Quando si usa la progettazione dei flussi di controllo, nella casella degli strumenti di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] sono elencate le attività disponibili in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per la compilazione del flusso di controllo in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-103">When you are working in the control flow designer, the Toolbox in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer lists the tasks that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides for building control flow in a package.</span></span> <span data-ttu-id="b0fc9-104">Per altre informazioni sulla casella degli strumenti, vedere [Casella degli strumenti SSIS](../ssis-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="b0fc9-104">For more information about the Toolbox, see [SSIS Toolbox](../ssis-toolbox.md).</span></span>  
  
 <span data-ttu-id="b0fc9-105">Un pacchetto può includere più istanze della stessa attività.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-105">A package can include multiple instances of the same task.</span></span> <span data-ttu-id="b0fc9-106">Ogni istanza di un'attività è univocamente identificata nel pacchetto e può avere una propria configurazione.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-106">Each instance of a task is uniquely identified in the package, and you can configure each instance differently.</span></span>  
  
 <span data-ttu-id="b0fc9-107">Se si elimina un'attività, verranno eliminati anche i vincoli di precedenza che la connettono ad altre attività e contenitori nel flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-107">If you delete a task, the precedence constraints that connect the task to other tasks and containers in the control flow are also deleted.</span></span>  
  
 <span data-ttu-id="b0fc9-108">Nelle procedure seguenti viene descritto come aggiungere o eliminare un'attività o un contenitore nel flusso di controllo di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-108">The following procedures describe how to add or delete a task or container in the control flow of a package.</span></span>  
  
### <a name="to-add-a-task-or-a-container-to-a-control-flow"></a><span data-ttu-id="b0fc9-109">Per aggiungere un'attività o un contenitore a un flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="b0fc9-109">To add a task or a container to a control flow</span></span>  
  
1.  <span data-ttu-id="b0fc9-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b0fc9-111">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b0fc9-112">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="b0fc9-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="b0fc9-113">Per aprire la **casella degli strumenti**, scegliere **Casella degli strumenti** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="b0fc9-113">To open the **Toolbox**, click **Toolbox** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="b0fc9-114">Espandere **Elementi flusso di controllo** e **Attività di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-114">Expand **Control Flow Items** and **Maintenance Tasks**.</span></span>  
  
6.  <span data-ttu-id="b0fc9-115">Trascinare attività e contenitori dalla **casella degli strumenti** all'area di progettazione della scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="b0fc9-115">Drag tasks and containers from the **Toolbox** to the design surface of the **Control Flow** tab.</span></span>  
  
7.  <span data-ttu-id="b0fc9-116">Connettere un'attività o un contenitore nel flusso di controllo del pacchetto trascinandone il connettore fino a un altro componente nel flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-116">Connect a task or container within the package control flow by dragging its connector to another component in the control flow.</span></span>  
  
8.  <span data-ttu-id="b0fc9-117">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="b0fc9-117">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-task-or-a-container-from-a-control-flow"></a><span data-ttu-id="b0fc9-118">Per eliminare un'attività o un contenitore da un flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="b0fc9-118">To delete a task or a container from a control flow</span></span>  
  
1.  <span data-ttu-id="b0fc9-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b0fc9-120">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-120">In Solution Explorer, double-click the package to open it.</span></span> <span data-ttu-id="b0fc9-121">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0fc9-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="b0fc9-122">Fare clic sulla scheda **Flusso di controllo** , fare clic con il pulsante destro del mouse sull'attività o il contenitore da rimuovere e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-122">Click the **Control Flow** tab, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
    -   <span data-ttu-id="b0fc9-123">Aprire **Esplora pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-123">Open **Package Explorer**.</span></span> <span data-ttu-id="b0fc9-124">Nella cartella **File eseguibili** fare clic con il pulsante destro del mouse sull'attività o il contenitore da rimuovere e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b0fc9-124">From the **Executables** folder, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="b0fc9-125">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="b0fc9-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0fc9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0fc9-126">See Also</span></span>  
 <span data-ttu-id="b0fc9-127">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b0fc9-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="b0fc9-128">[Contenitori di Integration Services](integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="b0fc9-128">[Integration Services Containers](integration-services-containers.md) </span></span>  
 [<span data-ttu-id="b0fc9-129">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="b0fc9-129">Control Flow</span></span>](control-flow.md)  
  
  
