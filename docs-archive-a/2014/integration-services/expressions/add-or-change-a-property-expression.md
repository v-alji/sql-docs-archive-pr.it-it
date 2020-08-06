---
title: Aggiungere o modificare un'espressione di proprietà | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- expressions [Integration Services], creating
- expressions [Integration Services], property expressions
ms.assetid: cb5da499-065f-4fa6-9f6d-5bc5f385241e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d6d12fbe46930818af2b47b59620963d39616e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635188"
---
# <a name="add-or-change-a-property-expression"></a><span data-ttu-id="d6109-102">Aggiunta o modifica di un'espressione di proprietà</span><span class="sxs-lookup"><span data-stu-id="d6109-102">Add or Change a Property Expression</span></span>
  <span data-ttu-id="d6109-103">È possibile creare espressioni di proprietà per pacchetti, attività, contenitori Ciclo Foreach, contenitori Ciclo For, contenitori Sequenza, gestori di eventi, gestioni connessioni a livello di pacchetto e progetto e provider di log.</span><span class="sxs-lookup"><span data-stu-id="d6109-103">You can create property expressions for packages, tasks, Foreach Loop containers, For Loop containers, Sequence containers, event handlers, package and project level connection managers, and log providers.</span></span>  
  
 <span data-ttu-id="d6109-104">Per creare o modificare espressioni di proprietà, è possibile usare l' **Editor espressioni di proprietà** o il **Generatore di espressioni**.</span><span class="sxs-lookup"><span data-stu-id="d6109-104">To create or change property expressions, you can use either the **Property Expressions Editor** or **Expression Builder**.</span></span> <span data-ttu-id="d6109-105">È possibile accedere all' **Editor espressioni di proprietà** dagli editor personalizzati disponibili per attività e contenitori o dalla finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="d6109-105">The **Property Expressions Editor** can be accessed from either the custom editors that are available for tasks and containers, or from the **Properties** window.</span></span> <span data-ttu-id="d6109-106">È possibile accedere al**Generatore di espressioni** dall' **Editor espressioni di proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d6109-106">**Expression Builder** can be accessed from inside the **Property Expressions Editor**.</span></span> <span data-ttu-id="d6109-107">È possibile scrivere espressioni sia nell'**Editor espressioni di proprietà** che nel **Generatore di espressioni**, tuttavia **Generatore di espressioni** offre un set di strumenti dell'interfaccia grafica che semplificano la compilazione di espressioni complesse.</span><span class="sxs-lookup"><span data-stu-id="d6109-107">While you can write expressions in either the **Property Expressions Editor** or **Expression Builder**, **Expression Builder** provides a graphical set of tools that makes it simple to build complex expressions.</span></span>  
  
 <span data-ttu-id="d6109-108">Per sapere di più sulla sintassi, gli operatori e le funzioni offerti da [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vedere [Operatori &#40;espressione SSIS&#41;](operators-ssis-expression.md) e [Funzioni &#40;espressione SSIS&#41;](functions-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="d6109-108">To learn more about the syntax, operators, and functions that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides, see [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) and [Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md).</span></span> <span data-ttu-id="d6109-109">Gli argomenti relativi a ogni operatore e funzione includono esempi di utilizzo dell'operatore o della funzione in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="d6109-109">The topic for each operator or function includes examples of using that operator or function in an expression.</span></span> <span data-ttu-id="d6109-110">Per esempi di espressioni più complesse, vedere [Utilizzo delle espressioni di proprietà nei pacchetti](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="d6109-110">For examples of more complex expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
### <a name="to-create-or-change-a-property-expression"></a><span data-ttu-id="d6109-111">Per creare o modificare un'espressione di proprietà</span><span class="sxs-lookup"><span data-stu-id="d6109-111">To create or change a property expression</span></span>  
  
1.  <span data-ttu-id="d6109-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto che contiene il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] desiderato.</span><span class="sxs-lookup"><span data-stu-id="d6109-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="d6109-113">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo e quindi eseguire una delle operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d6109-113">In Solution Explorer, double-click the package to open it, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="d6109-114">Nel caso di un'attività o di un contenitore, fare doppio clic sull'elemento e quindi su **Espressioni** nell'editor.</span><span class="sxs-lookup"><span data-stu-id="d6109-114">If the item is a task or a container, double-click the item, and then click **Expressions** in the editor.</span></span>  
  
    -   <span data-ttu-id="d6109-115">Fare clic con il pulsante destro del mouse sull'elemento e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d6109-115">Right-click the item and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d6109-116">Fare clic nella casella **Espressioni** e quindi sui puntini di sospensione (...).</span><span class="sxs-lookup"><span data-stu-id="d6109-116">Click in the **Expressions** box and then click the ellipsis (...).</span></span>  
  
4.  <span data-ttu-id="d6109-117">Nell' **Editor espressioni di proprietà**selezionare una proprietà nell'elenco **Proprietà** ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6109-117">In the **Property Expressions Editor**, select a property in the **Property** list, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="d6109-118">Digitare o modificare direttamente l'espressione di proprietà nella colonna **Espressione** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6109-118">Type or change the property expression directly in the **Expression** column, and then click **OK**.</span></span>  
  
         <span data-ttu-id="d6109-119">-oppure-</span><span class="sxs-lookup"><span data-stu-id="d6109-119">-or-</span></span>  
  
    -   <span data-ttu-id="d6109-120">Fare clic sui puntini di sospensione (...) nella riga dell'espressione della proprietà per aprire il **Generatore di espressioni**.</span><span class="sxs-lookup"><span data-stu-id="d6109-120">Click the ellipsis (...) in the expression row of the property to open the **Expression Builder**.</span></span>  
  
5.  <span data-ttu-id="d6109-121">(Facoltativo) Nel **Generatore di espressioni**, eseguire una delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6109-121">(Optional) In the **Expression Builder**, do any of the following tasks:</span></span>  
  
    -   <span data-ttu-id="d6109-122">Per accedere a variabili definite dal sistema e dall'utente, espandere **Variabili**.</span><span class="sxs-lookup"><span data-stu-id="d6109-122">To access system and user-defined variables, expand **Variables**.</span></span>  
  
    -   <span data-ttu-id="d6109-123">Per accedere alle funzioni, ai cast e agli operatori del linguaggio delle espressioni di [!INCLUDE[ssIS](../../includes/ssis-md.md)] , espandere i nodi **Funzioni matematiche**, **Funzioni per i valori stringa**, **Funzioni di data/ora**, **Funzioni NULL**, **Cast di tipo**e **Operatori**.</span><span class="sxs-lookup"><span data-stu-id="d6109-123">To access the functions, the casts, and the operators that the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression language provides, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators**.</span></span>  
  
    -   <span data-ttu-id="d6109-124">Per compilare o modificare un'espressione nel **Generatore di espressioni**, trascinare le variabili, le colonne, le funzioni, gli operatori e i cast nella casella **Espressione** oppure digitare direttamente l'espressione nella casella.</span><span class="sxs-lookup"><span data-stu-id="d6109-124">To build or change an expression in the **Expression Builder**, drag variables, columns, functions, operators, and casts to the **Expression** box, or type the expression in the box.</span></span>  
  
    -   <span data-ttu-id="d6109-125">Per visualizzare il risultato della valutazione dell'espressione, fare clic su **Valuta espressione** nel **Generatore di espressioni**.</span><span class="sxs-lookup"><span data-stu-id="d6109-125">To view the evaluation result of the expression, click **Evaluate Expression** in the **Expression Builder**.</span></span>  
  
         <span data-ttu-id="d6109-126">Se l'espressione non è valida, viene visualizzato un avviso che evidenzia gli errori di sintassi.</span><span class="sxs-lookup"><span data-stu-id="d6109-126">If the expression is not valid, an alert appears that describes the syntax errors in the expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d6109-127">Quando si valuta un'espressione, il risultato della valutazione non viene assegnato alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d6109-127">Evaluating an expression does not assign the evaluation result to the property.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d6109-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6109-128">See Also</span></span>  
 <span data-ttu-id="d6109-129">[Espressioni di Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="d6109-129">[Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="d6109-130">[Utilizzo delle espressioni di proprietà nei pacchetti](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="d6109-130">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="d6109-131">[Pacchetti di Integration Services &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="d6109-131">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="d6109-132">[Contenitori in Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="d6109-132">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="d6109-133">[Attività di Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="d6109-133">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="d6109-134">[Gestori eventi di Integration Services &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="d6109-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="d6109-135">[Connessioni in Integration Services &#40;SSIS&#41;](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="d6109-135">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="d6109-136">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6109-136">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)  
  
  
