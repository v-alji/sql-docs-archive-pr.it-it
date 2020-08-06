---
title: Contenitore Sequenza | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sequencecontainer.f1
helpviewer_keywords:
- Sequence container
- grouping control flows
- containers [Integration Services], Sequence
- subset control flow [Integration Services]
ms.assetid: 7731f91e-b8b3-4d96-a0d9-73f568547cb3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b972f923e2134363ba1b378beebebbeb1e5d6bb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629957"
---
# <a name="sequence-container"></a><span data-ttu-id="62fa2-102">Sequenza - contenitore</span><span class="sxs-lookup"><span data-stu-id="62fa2-102">Sequence Container</span></span>
  <span data-ttu-id="62fa2-103">Il contenitore Sequenza definisce un flusso di controllo costituito da un subset del flusso di controllo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="62fa2-103">The Sequence container defines a control flow that is a subset of the package control flow.</span></span> <span data-ttu-id="62fa2-104">I contenitori Sequenza suddividono il pacchetto in più flussi di controllo separati, ognuno dei quali include una o più attività e contenitori che vengono eseguiti nel flusso di controllo globale del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="62fa2-104">Sequence containers group the package into multiple separate control flows, each containing one or more tasks and containers that run within the overall package control flow.</span></span>  
  
 <span data-ttu-id="62fa2-105">Il contenitore Sequenza può includere più attività, oltre ad altri contenitori.</span><span class="sxs-lookup"><span data-stu-id="62fa2-105">The Sequence container can include multiple tasks in addition to other containers.</span></span> <span data-ttu-id="62fa2-106">L'aggiunta di attività e contenitori a un contenitore Sequenza è analoga all'aggiunta di tali elementi a un pacchetto, con la differenza che è necessario trascinare attività e contenitori nel contenitore Sequenza anziché nel contenitore del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="62fa2-106">Adding tasks and containers to a Sequence container is similar to adding them to a package, except you drag the tasks and containers to the Sequence container instead of to the package container.</span></span> <span data-ttu-id="62fa2-107">Se il contenitore Sequenza include più di un contenitore o attività, è possibile connettere tali elementi utilizzando vincoli di precedenza, come avviene nei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="62fa2-107">If the Sequence container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="62fa2-108">Per altre informazioni, vedere [Vincoli di precedenza](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="62fa2-108">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="62fa2-109">L'utilizzo del contenitore Sequenza offre molti vantaggi:</span><span class="sxs-lookup"><span data-stu-id="62fa2-109">There are many benefits of using a Sequence container:</span></span>  
  
-   <span data-ttu-id="62fa2-110">Consente di disabilitare gruppi di attività per indirizzare il debug su un subset del flusso di controllo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="62fa2-110">Disabling groups of tasks to focus package debugging on one subset of the package control flow.</span></span>  
  
-   <span data-ttu-id="62fa2-111">Consente di gestire le proprietà di più attività da un'unica posizione, tramite l'impostazione di proprietà su un contenitore Sequenza anziché sulle singole attività.</span><span class="sxs-lookup"><span data-stu-id="62fa2-111">Managing properties on multiple tasks in one location by setting properties on a Sequence container instead of on the individual tasks.</span></span>  
  
     <span data-ttu-id="62fa2-112">È ad esempio possibile impostare su `Disable` la proprietà `True` del contenitore Sequenza per disabilitare tutte le attività e i contenitori in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="62fa2-112">For example, you can set the `Disable` property of the Sequence container to `True` to disable all the tasks and containers in the Sequence container.</span></span>  
  
-   <span data-ttu-id="62fa2-113">Fornisce l'ambito per le variabili utilizzate da un gruppo di attività e contenitori correlati.</span><span class="sxs-lookup"><span data-stu-id="62fa2-113">Providing scope for variables that a group of related tasks and containers use.</span></span>  
  
-   <span data-ttu-id="62fa2-114">Consente di raggruppare più attività in modo da poterle gestire più facilmente comprimendo ed espandendo il contenitore Sequenza.</span><span class="sxs-lookup"><span data-stu-id="62fa2-114">Grouping many tasks so you can more easily managed them by collapsing and expanding the Sequence container.</span></span>  
  
     <span data-ttu-id="62fa2-115">È inoltre possibile creare gruppi di attività che possono essere compressi ed espansi usando la casella **Gruppo** .</span><span class="sxs-lookup"><span data-stu-id="62fa2-115">You can also create task groups, which expand and collapse using the **Group** box.</span></span> <span data-ttu-id="62fa2-116">La casella **Gruppo** è tuttavia una caratteristica della fase di progettazione che non dispone di proprietà o comportamento in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="62fa2-116">However, the **Group** box is a design-time feature that has no properties or run-time behavior.</span></span> <span data-ttu-id="62fa2-117">Per altre informazioni, vedere [Raggruppare o separare componenti](../group-or-ungroup-components.md)</span><span class="sxs-lookup"><span data-stu-id="62fa2-117">For more information, see [Group or Ungroup Components](../group-or-ungroup-components.md)</span></span>  
  
-   <span data-ttu-id="62fa2-118">Impostare un attributo di transazione sul contenitore Sequenza per definire una transazione per un subset del flusso di controllo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="62fa2-118">Set a transaction attribute on the Sequence container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="62fa2-119">In questo modo è possibile gestire le transazioni con un livello di granularità superiore.</span><span class="sxs-lookup"><span data-stu-id="62fa2-119">In this way, you can manage transactions at a more granular level.</span></span>  
  
     <span data-ttu-id="62fa2-120">Se ad esempio un contenitore Sequenza include due attività correlate, una che elimina dati da una tabella e un'altra che inserisce dati in una tabella, è possibile configurare una transazione per garantire che se non dovesse riuscire l'azione di inserimento, verrà eseguito il rollback dell'azione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="62fa2-120">For example, if a Sequence container includes two related tasks, one task that deletes data in a table and another task that inserts data into a table, you can configure a transaction to ensure that the delete action is rolled back if the insert action fails.</span></span> <span data-ttu-id="62fa2-121">Per altre informazioni, vedere [Transazioni di Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="62fa2-121">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-sequence-container"></a><span data-ttu-id="62fa2-122">Configurazione del contenitore Sequenza</span><span class="sxs-lookup"><span data-stu-id="62fa2-122">Configuration of the Sequence Container</span></span>  
 <span data-ttu-id="62fa2-123">Il contenitore Sequenza non dispone di un'interfaccia utente personalizzata e può essere configurato solo tramite la finestra **Proprietà** di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="62fa2-123">The Sequence container has no custom user interface and you can configure it only in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="62fa2-124">Per informazioni sull'impostazione a livello di codice di queste proprietà, vedere la documentazione relativa alla classe **T:Microsoft.SqlServer.Dts.Runtime.Sequence** nella Guida per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="62fa2-124">For information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.Sequence** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="62fa2-125">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="62fa2-125">Related Tasks</span></span>  
 <span data-ttu-id="62fa2-126">Per informazioni su come impostare le proprietà del componente, vedere nel [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vedere [Impostazione delle proprietà di un'attività o di un contenitore](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="62fa2-126">For information about how to set properties of the component in the [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62fa2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62fa2-127">See Also</span></span>  
 <span data-ttu-id="62fa2-128">[Aggiunta o eliminazione di un'attività o un contenitore in un flusso di controllo](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="62fa2-128">[Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="62fa2-129">[Connessione di attività e contenitori tramite un vincolo di precedenza predefinito](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="62fa2-129">[Connect Tasks and Containers by Using a Default Precedence Constraint](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="62fa2-130">Contenitori in Integration Services</span><span class="sxs-lookup"><span data-stu-id="62fa2-130">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
