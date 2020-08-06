---
title: Contenitore Ciclo For | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.forloopcontainerdetails.f1
helpviewer_keywords:
- repeating control flow
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: 44cf7355-992b-4bbf-a28c-bfb012de06f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a6c864779237fdbf4dd249f87b7c06655293c047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623451"
---
# <a name="for-loop-container"></a><span data-ttu-id="f8459-102">Contenitore Ciclo For</span><span class="sxs-lookup"><span data-stu-id="f8459-102">For Loop Container</span></span>
  <span data-ttu-id="f8459-103">Il contenitore Ciclo For definisce un flusso di controllo ripetuto all'interno di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f8459-103">The For Loop container defines a repeating control flow in a package.</span></span> <span data-ttu-id="f8459-104">L'implementazione del ciclo è simile alla struttura del ciclo **For** nei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="f8459-104">The loop implementation is similar to the **For** looping structure in programming languages.</span></span> <span data-ttu-id="f8459-105">A ogni ripetizione del ciclo il contenitore Ciclo For valuta un'espressione e ne ripete il flusso di lavoro finché tale espressione non restituisce `False`.</span><span class="sxs-lookup"><span data-stu-id="f8459-105">In each repeat of the loop, the For Loop container evaluates an expression and repeats its workflow until the expression evaluates to `False`.</span></span>  
  
 <span data-ttu-id="f8459-106">Per definire il ciclo, il contenitore Ciclo For usa gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8459-106">The For Loop container usesthe following elements to define the loop:</span></span>  
  
-   <span data-ttu-id="f8459-107">Un'espressione di inizializzazione facoltativa che assegna valori ai contatori del ciclo.</span><span class="sxs-lookup"><span data-stu-id="f8459-107">An optional initialization expression that assigns values to the loop counters.</span></span>  
  
-   <span data-ttu-id="f8459-108">Un'espressione di valutazione che contiene l'espressione utilizzata per stabilire se il ciclo deve essere arrestato o continuare.</span><span class="sxs-lookup"><span data-stu-id="f8459-108">An evaluation expression that contains the expression used to test whether the loop should stop or continue.</span></span>  
  
-   <span data-ttu-id="f8459-109">Un'espressione di iterazione facoltativa che incrementa o decrementa il contatore del ciclo.</span><span class="sxs-lookup"><span data-stu-id="f8459-109">An optional iteration expression that increments or decrements the loop counter.</span></span>  
  
 <span data-ttu-id="f8459-110">Nella figura seguente viene illustrato un contenitore Ciclo For con un'attività Invia messaggi.</span><span class="sxs-lookup"><span data-stu-id="f8459-110">The following diagram shows a For Loop container with a Send Mail task.</span></span> <span data-ttu-id="f8459-111">Se l'espressione di inizializzazione è `@Counter = 0`, l'espressione di valutazione è `@Counter < 4`e l'espressione di iterazione è `@Counter = @Counter + 1`, il ciclo si ripeterà quattro volte e verranno inviati quattro messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f8459-111">If the initialization expression is `@Counter = 0`, the evaluation expression is `@Counter < 4`, and the iteration expression is `@Counter = @Counter + 1`, the loop repeats four times and sends four e-mail messages.</span></span>  
  
 <span data-ttu-id="f8459-112">![Un contenitore Ciclo For ripete un'attività quattro volte](../media/ssis-forloop.gif "Un contenitore Ciclo For ripete un'attività quattro volte")</span><span class="sxs-lookup"><span data-stu-id="f8459-112">![A For Loop container repeats a task four times](../media/ssis-forloop.gif "A For Loop container repeats a task four times")</span></span>  
  
 <span data-ttu-id="f8459-113">Le espressioni devono essere espressioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] valide.</span><span class="sxs-lookup"><span data-stu-id="f8459-113">The expressions must be valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions.</span></span>  
  
 <span data-ttu-id="f8459-114">Per creare le espressioni di inizializzazione e assegnazione, è possibile utilizzare l'operatore di assegnazione (=).</span><span class="sxs-lookup"><span data-stu-id="f8459-114">To create the initialization and assignment expressions, you can use the assignment operator (=).</span></span> <span data-ttu-id="f8459-115">In altre circostanze questo operatore non è supportato dalla grammatica delle espressioni di Integration Services, ma può essere utilizzato solo dai tipi di espressione di inizializzazione e assegnazione nel contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="f8459-115">This operator is not otherwise supported by the Integration Services expression grammar and can only be used by the initialization and assignment expression types in the For Loop container.</span></span> <span data-ttu-id="f8459-116">Tutte le espressioni che usano l'operatore di assegnazione devono avere la sintassi `@Var = <expression>`, dove **Var** è una variabile di runtime ed \<expression> è un'espressione che segue le regole della sintassi delle espressioni di [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8459-116">Any expression that uses the assignment operator must have the syntax `@Var = <expression>`, where **Var** is a run-time variable and \<expression> is an expression that follows the rules of the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="f8459-117">L'espressione può includere le variabili, i valori letterali e tutti gli operatori e le funzioni supportati dalla grammatica delle espressioni di SSIS.</span><span class="sxs-lookup"><span data-stu-id="f8459-117">The expression can include the variables, literals, and any operators and functions that the SSIS expression grammar supports.</span></span> <span data-ttu-id="f8459-118">L'espressione deve restituire un tipo di dati di cui è possibile eseguire il cast al tipo di dati della variabile.</span><span class="sxs-lookup"><span data-stu-id="f8459-118">The expression must evaluate to a data type that can be cast to the data type of the variable.</span></span>  
  
 <span data-ttu-id="f8459-119">Un contenitore Ciclo For può includere una sola espressione di valutazione,</span><span class="sxs-lookup"><span data-stu-id="f8459-119">A For Loop container can have only one evaluation expression.</span></span> <span data-ttu-id="f8459-120">pertanto esegue tutti gli elementi del flusso di controllo per lo stesso numero di volte.</span><span class="sxs-lookup"><span data-stu-id="f8459-120">This means that the For Loop container runs all its control flow elements the same number of times.</span></span> <span data-ttu-id="f8459-121">Poiché un contenitore Ciclo For può includere altri contenitori Ciclo For, nei pacchetti è possibile compilare cicli nidificati e implementare loop complessi.</span><span class="sxs-lookup"><span data-stu-id="f8459-121">Because the For Loop container can include other For Loop containers, you can build nested loops and implement complex looping in packages.</span></span>  
  
 <span data-ttu-id="f8459-122">È possibile impostare una proprietà di transazione sul contenitore Ciclo For per definire una transazione per un subset del flusso di controllo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f8459-122">You can set a transaction property on the For Loop container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="f8459-123">In questo modo è possibile gestire le transazioni con un livello di granularità superiore.</span><span class="sxs-lookup"><span data-stu-id="f8459-123">In this way, you can manage transactions at a more granular level.</span></span> <span data-ttu-id="f8459-124">Se ad esempio un contenitore Ciclo For ripete un flusso di controllo che aggiorna più volte i dati di una tabella, sarà possibile configurare il ciclo For e il relativo flusso di controllo per l'utilizzo di una transazione, in modo da assicurare che se non è possibile aggiornare correttamente tutti i dati, non ne verrà aggiornato alcuno.</span><span class="sxs-lookup"><span data-stu-id="f8459-124">For example, if a For Loop container repeats a control flow that updates data in a table multiple times, you can configure the For Loop and its control flow to use a transaction to ensure that if not all data is updated successfully, no data is updated.</span></span> <span data-ttu-id="f8459-125">Per altre informazioni, vedere [Transazioni di Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="f8459-125">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-for-loop-container"></a><span data-ttu-id="f8459-126">Configurazione del contenitore Ciclo For</span><span class="sxs-lookup"><span data-stu-id="f8459-126">Configuration of the For Loop Container</span></span>  
 <span data-ttu-id="f8459-127">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="f8459-127">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f8459-128">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8459-128">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f8459-129">Editor ciclo For</span><span class="sxs-lookup"><span data-stu-id="f8459-129">For Loop Editor</span></span>](../for-loop-editor.md)  
  
-   [<span data-ttu-id="f8459-130">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="f8459-130">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="f8459-131">Per altre informazioni sull'impostazione a livello di codice di queste proprietà, vedere la documentazione per la classe **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** nella Guida per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="f8459-131">For more information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f8459-132">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="f8459-132">Related Tasks</span></span>  
 <span data-ttu-id="f8459-133">Per informazioni sulla configurazione di un contenitore Ciclo For, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="f8459-133">For information about how to configure a For Loop Container, see the following topics.</span></span>  
  
-   [<span data-ttu-id="f8459-134">Configurazione di un contenitore Ciclo For</span><span class="sxs-lookup"><span data-stu-id="f8459-134">Configure a For Loop Container</span></span>](for-loop-container.md)  
  
-   [<span data-ttu-id="f8459-135">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="f8459-135">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="f8459-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8459-136">See Also</span></span>  
 <span data-ttu-id="f8459-137">[Flusso di controllo](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="f8459-137">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="f8459-138">Espressioni di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f8459-138">Integration Services &#40;SSIS&#41; Expressions</span></span>](../expressions/integration-services-ssis-expressions.md)  
  
  
