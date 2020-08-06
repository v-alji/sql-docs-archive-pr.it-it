---
title: Impostare le proprietà di un'attività o di un contenitore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], properties
ms.assetid: 52d47ca4-fb8c-493d-8b2b-48bb269f859b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0a4c556b94af02c2f874f2740a70b1294c35e653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726052"
---
# <a name="set-the-properties-of-a-task-or-container"></a><span data-ttu-id="0d7b8-102">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="0d7b8-102">Set the Properties of a Task or Container</span></span>
  <span data-ttu-id="0d7b8-103">È possibile impostare la maggior parte delle proprietà delle attività e dei contenitori usando la finestra **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-103">You can set most properties of tasks and containers by using the **Properties** window.</span></span> <span data-ttu-id="0d7b8-104">Fanno eccezione le proprietà delle raccolte di attività e quelle troppo complesse per essere impostate nella finestra **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-104">The exceptions are properties of task collections and properties that are too complex to set by using the **Properties** window.</span></span> <span data-ttu-id="0d7b8-105">L'enumeratore usato dal contenitore Ciclo Foreach, ad esempio, non può essere configurato nella finestra **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-105">For example, you cannot configure the enumerator that the Foreach Loop container uses in the **Properties** window.</span></span> <span data-ttu-id="0d7b8-106">Per impostare tali proprietà complesse, è necessario utilizzare un editor attività o contenitori.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-106">You must use a task or container editor to set these complex properties.</span></span> <span data-ttu-id="0d7b8-107">La maggior parte degli editor attività e contenitori include più nodi, ognuno dei quali contiene proprietà correlate.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-107">Most task and container editors have multiple nodes and each node contains related properties.</span></span> <span data-ttu-id="0d7b8-108">Il nome del nodo indica l'oggetto delle proprietà contenute.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-108">The name of the node indicates the subject of the properties that the node contains.</span></span>  
  
 <span data-ttu-id="0d7b8-109">Le procedure seguenti descrivono come impostare le proprietà di un'attività o di un contenitore usando la finestra **Proprietà** o l'editor attività o contenitori corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-109">The following procedures describe how to set the properties of a task or container by using either the **Properties** windows, or the corresponding task or container editor.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-the-properties-window"></a><span data-ttu-id="0d7b8-110">Per impostare le proprietà di un'attività o di un contenitore utilizzando la finestra Proprietà</span><span class="sxs-lookup"><span data-stu-id="0d7b8-110">To set the properties of a task or container by using the Properties window</span></span>  
  
1.  <span data-ttu-id="0d7b8-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0d7b8-112">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0d7b8-113">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="0d7b8-113">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="0d7b8-114">Nell'area di progettazione della scheda **Flusso di controllo** fare clic con il pulsante destro del mouse sull'attività o sul contenitore, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-114">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="0d7b8-115">Nella finestra **Proprietà** aggiornare i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-115">In the **Properties** window, update the property value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d7b8-116">È possibile impostare la maggior parte delle proprietà digitando un valore direttamente nella casella di testo o selezionandone uno in un elenco.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-116">Most properties can be set by typing a value directly in the text box, or by selecting a value from a list.</span></span> <span data-ttu-id="0d7b8-117">Alcune proprietà sono tuttavia più complesse e dispongono di un editor proprietà personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-117">However, some properties are more complex and have a custom property editor.</span></span> <span data-ttu-id="0d7b8-118">Per impostare la proprietà, fare clic nella casella di testo, quindi sul pulsante di compilazione **(...)** per aprire l'editor personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-118">To set the property, click in the text box, and then click the build **(...)** button to open the custom editor.</span></span>  
  
6.  <span data-ttu-id="0d7b8-119">Facoltativamente, creare espressioni di proprietà per aggiornare dinamicamente le proprietà dell'attività o del contenitore.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-119">Optionally, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="0d7b8-120">Per altre informazioni, vedere [Aggiunta o modifica di un'espressione di proprietà](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0d7b8-120">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="0d7b8-121">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="0d7b8-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-a-task-or-container-editor"></a><span data-ttu-id="0d7b8-122">Per impostare le proprietà di un'attività o di un contenitore utilizzando un editor attività o contenitori</span><span class="sxs-lookup"><span data-stu-id="0d7b8-122">To set the properties of a task or container by using a task or container editor</span></span>  
  
1.  <span data-ttu-id="0d7b8-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0d7b8-124">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-124">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0d7b8-125">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="0d7b8-125">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="0d7b8-126">Nell'area di progettazione della scheda **Flusso di controllo** fare clic con il pulsante destro del mouse sull'attività o sul contenitore, quindi scegliere **Modifica** per aprire l'editor attività o contenitori corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-126">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Edit** to open the corresponding task or container editor.</span></span>  
  
     <span data-ttu-id="0d7b8-127">Per informazioni sulla configurazione di un contenitore Ciclo For, vedere [Configurazione di un contenitore Ciclo For](control-flow/for-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="0d7b8-127">For information about how to configure the For Loop container, see [Configure a For Loop Container](control-flow/for-loop-container.md).</span></span>  
  
     <span data-ttu-id="0d7b8-128">Per informazioni su come configurare il contenitore Ciclo Foreach, vedere [Configurare un contenitore Ciclo Foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="0d7b8-128">For information about how to configure the Foreach Loop container, see [Configure a Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d7b8-129">Il contenitore Sequenza non dispone di un editor personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-129">The Sequence container has no custom editor.</span></span>  
  
5.  <span data-ttu-id="0d7b8-130">Se l'editor attività o contenitori include più nodi, fare clic su quello che contiene la proprietà da impostare.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-130">If the task or container editor has multiple nodes, click the node that contains the property that you want to set.</span></span>  
  
6.  <span data-ttu-id="0d7b8-131">Facoltativamente, fare clic su **Espressioni** e, nella pagina **Espressioni** , creare espressioni di proprietà per aggiornare in modo dinamico le proprietà dell'attività o del contenitore.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-131">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="0d7b8-132">Per altre informazioni, vedere [Aggiunta o modifica di un'espressione di proprietà](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0d7b8-132">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="0d7b8-133">Aggiornare il valore delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="0d7b8-133">Update the property value.</span></span>  
  
8.  <span data-ttu-id="0d7b8-134">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="0d7b8-134">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7b8-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d7b8-135">See Also</span></span>  
 <span data-ttu-id="0d7b8-136">[Attività di Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="0d7b8-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="0d7b8-137">Contenitori in Integration Services</span><span class="sxs-lookup"><span data-stu-id="0d7b8-137">Integration Services Containers</span></span>](control-flow/integration-services-containers.md)  
  
  
