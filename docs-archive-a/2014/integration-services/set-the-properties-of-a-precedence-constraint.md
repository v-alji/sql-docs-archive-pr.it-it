---
title: Impostare le proprietà di un vincolo di precedenza | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Precedence Constraint Editor dialog box
- precedence constraints [Integration Services], properties
ms.assetid: d990f600-5c09-4cd5-8528-0a58d79dc9f2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 55b95bdb79d801156bef6198bc0f57accb5d9517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636783"
---
# <a name="set-the-properties-of-a-precedence-constraint"></a><span data-ttu-id="4303e-102">Impostazione delle proprietà di un vincolo di precedenza</span><span class="sxs-lookup"><span data-stu-id="4303e-102">Set the Properties of a Precedence Constraint</span></span>
  <span data-ttu-id="4303e-103">Per impostare le proprietà dei vincoli di precedenza, è possibile utilizzare uno dei seguenti strumenti:</span><span class="sxs-lookup"><span data-stu-id="4303e-103">To set properties on precedence constraints, you can use one of these tools:</span></span>  
  
-   <span data-ttu-id="4303e-104">La finestra di dialogo **Editor vincoli di precedenza** .</span><span class="sxs-lookup"><span data-stu-id="4303e-104">You can use the **Precedence Constraint Editor** dialog box.</span></span>  
  
-   <span data-ttu-id="4303e-105">La finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="4303e-105">You can use the Properties window.</span></span> <span data-ttu-id="4303e-106">Nella finestra Proprietà sono elencate le proprietà per la configurazione dei vincoli di precedenza non disponibili nella finestra di dialogo **Editor vincoli di precedenza** .</span><span class="sxs-lookup"><span data-stu-id="4303e-106">The Properties window lists properties for configuring precedence constraints that are not available in the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="4303e-107">ed è possibile specificare una descrizione e un nome del vincolo di precedenza, nonché configurare l'annotazione da visualizzare per il vincolo di precedenza nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4303e-107">In the Properties window, you can provide a description and name of the precedence constraint, and configure the annotation to display for the precedence constraint on the design surface.</span></span>  
  
 <span data-ttu-id="4303e-108">Nelle procedure seguenti viene descritta l'impostazione delle proprietà dei vincoli di precedenza tramite ognuno di questi strumenti.</span><span class="sxs-lookup"><span data-stu-id="4303e-108">The following procedures describe how to set properties on precedence constraints by using each of these tools.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-precedence-constraint-editor"></a><span data-ttu-id="4303e-109">Per impostare le proprietà di un vincolo di precedenza tramite Editor vincoli di precedenza</span><span class="sxs-lookup"><span data-stu-id="4303e-109">To set the properties of a precedence constraint by using the Precedence Constraint Editor</span></span>  
  
1.  <span data-ttu-id="4303e-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="4303e-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="4303e-111">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="4303e-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4303e-112">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="4303e-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="4303e-113">Fare doppio clic sul vincolo di precedenza.</span><span class="sxs-lookup"><span data-stu-id="4303e-113">Double-click the precedence constraint.</span></span>  
  
     <span data-ttu-id="4303e-114">Verrà aperta la finestra di dialogo **Editor vincoli di precedenza** .</span><span class="sxs-lookup"><span data-stu-id="4303e-114">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="4303e-115">Nell'elenco a discesa **Operazione valutazione** selezionare un'operazione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="4303e-115">In the **Evaluation operation** drop-down list, select an evaluation operation.</span></span>  
  
6.  <span data-ttu-id="4303e-116">Nell' `Value` elenco a discesa selezionare il risultato dell'esecuzione dell'eseguibile con precedenza.</span><span class="sxs-lookup"><span data-stu-id="4303e-116">In the `Value` drop-down list, select the execution result of the precedence executable.</span></span>  
  
7.  <span data-ttu-id="4303e-117">Se l'operazione di valutazione utilizza un'espressione, `Expression` digitare un'espressione nella casella e fare clic su **test** per valutare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="4303e-117">If the evaluation operation uses an expression, in the `Expression` box, type an expression, and click **Test** to evaluate the expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4303e-118">Per i nomi delle variabili viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4303e-118">Variable names are case-sensitive.</span></span>  
  
8.  <span data-ttu-id="4303e-119">Se all'eseguibile soggetto al vincolo sono connessi più contenitori o attività, selezionare **and logico** per specificare che i risultati dell'esecuzione di tutti i file eseguibili precedenti devono restituire `true` .</span><span class="sxs-lookup"><span data-stu-id="4303e-119">If multiple tasks or containers are connected to the constrained executable, select **Logical AND** to specify that the execution results of all preceding executables must evaluate to `true`.</span></span> <span data-ttu-id="4303e-120">Selezionare **OR logico** per specificare che un solo risultato di esecuzione deve restituire `true` .</span><span class="sxs-lookup"><span data-stu-id="4303e-120">Select **Logical OR** to specify that only one execution result must evaluate to `true`.</span></span>  
  
9. <span data-ttu-id="4303e-121">Scegliere **OK** per chiudere la finestra **Editor vincoli di precedenza**.</span><span class="sxs-lookup"><span data-stu-id="4303e-121">Click **OK** to close the **Precedence Constraint Editor**.</span></span>  
  
10. <span data-ttu-id="4303e-122">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="4303e-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-properties-window"></a><span data-ttu-id="4303e-123">Per impostare le proprietà di un vincolo di precedenza tramite la finestra Proprietà</span><span class="sxs-lookup"><span data-stu-id="4303e-123">To set the properties of a precedence constraint by using the Properties window</span></span>  
  
1.  <span data-ttu-id="4303e-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto da modificare.</span><span class="sxs-lookup"><span data-stu-id="4303e-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to modify.</span></span>  
  
2.  <span data-ttu-id="4303e-125">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="4303e-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4303e-126">Fare clic sulla scheda **flusso di controllo** . Nell'area di progettazione della scheda **flusso di controllo** fare clic con il pulsante destro del mouse sul vincolo di precedenza, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4303e-126">Click the **Control Flow** tab. On the design surface of the **Control Flow** tab, right-click the precedence constraint, and then click **Properties**.</span></span> <span data-ttu-id="4303e-127">Nella finestra Proprietà modificare i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4303e-127">In the Properties window, modify the property values.</span></span>  
  
4.  <span data-ttu-id="4303e-128">Nella finestra **Proprietà** impostare le proprietà di lettura/scrittura seguenti dei vincoli di precedenza:</span><span class="sxs-lookup"><span data-stu-id="4303e-128">In the **Properties** window, set the following read/write properties of precedence constraints:</span></span>  
  
    |<span data-ttu-id="4303e-129">Proprietà di lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="4303e-129">Read/write property</span></span>|<span data-ttu-id="4303e-130">Azione di configurazione</span><span class="sxs-lookup"><span data-stu-id="4303e-130">Configuration action</span></span>|  
    |--------------------------|--------------------------|  
    |<span data-ttu-id="4303e-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4303e-131">Description</span></span>|<span data-ttu-id="4303e-132">Specificare una descrizione.</span><span class="sxs-lookup"><span data-stu-id="4303e-132">Provide a description.</span></span>|  
    |<span data-ttu-id="4303e-133">EvalOp</span><span class="sxs-lookup"><span data-stu-id="4303e-133">EvalOp</span></span>|<span data-ttu-id="4303e-134">Selezionare un'operazione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="4303e-134">Select an evaluation operation.</span></span> <span data-ttu-id="4303e-135">Se `Expression` è selezionata l'operazione, **ExpressionAndConstant**o **ExpressionOrConstant** , è possibile specificare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="4303e-135">If the `Expression`, **ExpressionAndConstant**, or **ExpressionOrConstant** operation is selected, you can specify an expression.</span></span>|  
    |<span data-ttu-id="4303e-136">Expression</span><span class="sxs-lookup"><span data-stu-id="4303e-136">Expression</span></span>|<span data-ttu-id="4303e-137">Se l'operazione di valutazione include un'espressione, specificare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="4303e-137">If the evaluation operation includes and expression, provide an expression.</span></span> <span data-ttu-id="4303e-138">L'espressione deve restituire un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="4303e-138">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="4303e-139">Per altre informazioni sul linguaggio delle espressioni, vedere [Espressioni di Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4303e-139">For more information about the expression language, see [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>|  
    |<span data-ttu-id="4303e-140">LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="4303e-140">LogicalAnd</span></span>|<span data-ttu-id="4303e-141">Impostare `LogicalAnd` per specificare se il vincolo di precedenza viene valutato insieme ad altri vincoli di precedenza, quando più eseguibili precedono e sono collegati all'eseguibile soggetto al vincolo</span><span class="sxs-lookup"><span data-stu-id="4303e-141">Set `LogicalAnd` to specify whether the precedence constraint is evaluated in concert with other precedence constraints, when multiple executables precede and are linked to the constrained executable</span></span>|  
    |<span data-ttu-id="4303e-142">Nome</span><span class="sxs-lookup"><span data-stu-id="4303e-142">Name</span></span>|<span data-ttu-id="4303e-143">Aggiornare il nome del vincolo di precedenza.</span><span class="sxs-lookup"><span data-stu-id="4303e-143">Update the name of the precedence constraint.</span></span>|  
    |<span data-ttu-id="4303e-144">ShowAnnotation</span><span class="sxs-lookup"><span data-stu-id="4303e-144">ShowAnnotation</span></span>|<span data-ttu-id="4303e-145">Specificare il tipo di annotazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4303e-145">Specify the type of annotation to use.</span></span> <span data-ttu-id="4303e-146">Selezionare **Never** per disabilitare le annotazioni, **AsNeeded** per attivare le annotazioni su richiesta, **ConstraintName** per aggiungere automaticamente annotazioni usando il valore della proprietà Name, **ConstraintDescription** per aggiungere automaticamente annotazioni usando il valore della proprietà Description e **ConstraintOptions** per aggiungere automaticamente annotazioni usando i valori delle proprietà Value ed Expression.</span><span class="sxs-lookup"><span data-stu-id="4303e-146">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **ConstraintName** to automatically annotate using the value of the Name property, **ConstraintDescription** to automatically annotate using the value of the Description property, and **ConstraintOptions** to automatically annotate using the values of the Value and Expression properties.</span></span>|  
    |<span data-ttu-id="4303e-147">Valore</span><span class="sxs-lookup"><span data-stu-id="4303e-147">Value</span></span>|<span data-ttu-id="4303e-148">Se l'operazione di valutazione specificata nella proprietà EvalOP include un vincolo, selezionare il risultato dell'esecuzione dell'eseguibile vincolante.</span><span class="sxs-lookup"><span data-stu-id="4303e-148">If the evaluation operation specified in the EvalOP property includes a constraint, select the execution result of the constraining executable.</span></span>|  
  
5.  <span data-ttu-id="4303e-149">Chiudere la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="4303e-149">Close the Properties window.</span></span>  
  
6.  <span data-ttu-id="4303e-150">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="4303e-150">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4303e-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4303e-151">See Also</span></span>  
 <span data-ttu-id="4303e-152">[Vincoli di precedenza](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="4303e-152">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="4303e-153">[Connessione di attività e contenitori tramite un vincolo di precedenza predefinito](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="4303e-153">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="4303e-154">[Impostare il valore di un vincolo di precedenza tramite il menu di scelta rapida](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="4303e-154">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 [<span data-ttu-id="4303e-155">Uso di un'espressione in un vincolo di precedenza</span><span class="sxs-lookup"><span data-stu-id="4303e-155">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
