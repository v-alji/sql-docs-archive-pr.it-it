---
title: Aggiungere un'enumerazione a un flusso di controllo | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding enumerations
- Foreach Loop containers
- control flow [Integration Services], enumerations
- repeating workflows
- enumerations [Integration Services]
ms.assetid: f212b5fb-3cc4-422e-9b7c-89eb769a812a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59b8569880fdf1a49f5f2ca1f6841841f9790af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627953"
---
# <a name="add-enumeration-to-a-control-flow"></a><span data-ttu-id="09f52-102">Aggiunta di un'enumerazione a un flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="09f52-102">Add Enumeration to a Control Flow</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="09f52-103">include il contenitore Ciclo Foreach, un elemento del flusso di controllo che semplifica l'integrazione di un costrutto di ciclo per l'enumerazione di file e oggetti nel flusso di controllo di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="09f52-103">includes the Foreach Loop container, a control flow element that makes it simple to include a looping construct that enumerates files and objects in the control flow of a package.</span></span> <span data-ttu-id="09f52-104">Per altre informazioni, vedere [Contenitore Ciclo Foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="09f52-104">For more information, see [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="09f52-105">Il contenitore Ciclo Foreach non offre funzionalità, ma solo una struttura in cui è possibile compilare un flusso di controllo ripetibile, nonché specificare e configurare un tipo di enumeratore.</span><span class="sxs-lookup"><span data-stu-id="09f52-105">The Foreach Loop container provides no functionality; it provides only the structure in which you build the repeatable control flow, specify an enumerator type, and configure the enumerator.</span></span> <span data-ttu-id="09f52-106">Per aggiungere funzionalità al contenitore Ciclo Foreach è necessario includervi almeno un'attività.</span><span class="sxs-lookup"><span data-stu-id="09f52-106">To provide container functionality, you must include at least one task in the Foreach Loop container.</span></span> <span data-ttu-id="09f52-107">Per altre informazioni, vedere [Attività di Integration Services](control-flow/integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="09f52-107">For more information, see [Integration Services Tasks](control-flow/integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="09f52-108">Il contenitore Ciclo Foreach può includere un flusso di controllo con più attività e può includere altri contenitori.</span><span class="sxs-lookup"><span data-stu-id="09f52-108">The Foreach Loop container can include a control flow with multiple tasks and other containers.</span></span> <span data-ttu-id="09f52-109">L'aggiunta di attività e contenitori a un contenitore Ciclo Foreach è analoga all'aggiunta di tali elementi a un pacchetto, con la differenza che è necessario trascinare attività e contenitori nel contenitore Ciclo Foreach anziché nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="09f52-109">Adding tasks and containers to a Foreach Loop container is similar to adding them to a package, except you drag the tasks and containers to the Foreach Loop container instead of to the package.</span></span> <span data-ttu-id="09f52-110">Se il contenitore Ciclo Foreach include più di un contenitore o attività, sarà possibile connettere tali elementi utilizzando vincoli di precedenza, come avviene nei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="09f52-110">If the Foreach Loop container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="09f52-111">Per altre informazioni, vedere [Vincoli di precedenza](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="09f52-111">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
### <a name="to-implement-a-foreach-loop-container-in-a-control-flow"></a><span data-ttu-id="09f52-112">Per implementare un contenitore Ciclo Foreach in un flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="09f52-112">To implement a Foreach Loop container in a control flow</span></span>  
  
1.  <span data-ttu-id="09f52-113">Aggiungere il contenitore Ciclo Foreach al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="09f52-113">Add the Foreach Loop container to the package.</span></span> <span data-ttu-id="09f52-114">Per altre informazioni, vedere [aggiungere o eliminare un'attività o un contenitore in un flusso di controllo](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span><span class="sxs-lookup"><span data-stu-id="09f52-114">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="09f52-115">.</span><span class="sxs-lookup"><span data-stu-id="09f52-115">.</span></span>  
  
2.  <span data-ttu-id="09f52-116">Aggiungere attività e contenitori al contenitore Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="09f52-116">Add tasks and containers to the Foreach Loop container.</span></span> <span data-ttu-id="09f52-117">Per altre informazioni, vedere [aggiungere o eliminare un'attività o un contenitore in un flusso di controllo](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span><span class="sxs-lookup"><span data-stu-id="09f52-117">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="09f52-118">.</span><span class="sxs-lookup"><span data-stu-id="09f52-118">.</span></span>  
  
3.  <span data-ttu-id="09f52-119">Connettere le attività e i contenitori inclusi nel contenitore Ciclo Foreach tramite vincoli di precedenza.</span><span class="sxs-lookup"><span data-stu-id="09f52-119">Connect tasks and containers in the Foreach Loop container using precedence constraints.</span></span> <span data-ttu-id="09f52-120">Per altre informazioni, vedere [Connessione di attività e contenitori tramite un vincolo di precedenza predefinito](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="09f52-120">For more information, see [Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span></span>  
  
4.  <span data-ttu-id="09f52-121">Configurare il contenitore Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="09f52-121">Configure the Foreach Loop container.</span></span> <span data-ttu-id="09f52-122">Per altre informazioni, vedere [Configurazione di un contenitore Ciclo Foreach](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="09f52-122">For more information, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f52-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09f52-123">See Also</span></span>  
 <span data-ttu-id="09f52-124">[Aggiungere o eliminare un'attività o un contenitore in un flusso di controllo](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="09f52-124">[Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="09f52-125">[Raggruppare o disraggruppare componenti](group-or-ungroup-components.md) </span><span class="sxs-lookup"><span data-stu-id="09f52-125">[Group or Ungroup Components](group-or-ungroup-components.md) </span></span>  
 <span data-ttu-id="09f52-126">[Vincoli di precedenza](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="09f52-126">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="09f52-127">[Aggiungere un'iterazione a un flusso di controllo](add-iteration-to-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="09f52-127">[Add Iteration to a Control Flow](add-iteration-to-a-control-flow.md) </span></span>  
 [<span data-ttu-id="09f52-128">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="09f52-128">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
