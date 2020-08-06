---
title: Utilizzare un'espressione in un componente flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], data flow
- expressions [Integration Services], data flow components
ms.assetid: 9181b998-d24a-41fb-bb3c-14eee34f910d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 653bf468d0af6d44c5abe7344fcc13f93f86b430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718426"
---
# <a name="use-an-expression-in-a-data-flow-component"></a><span data-ttu-id="a76c9-102">Utilizzo di un'espressione in un componente flusso di dati</span><span class="sxs-lookup"><span data-stu-id="a76c9-102">Use an Expression in a Data Flow Component</span></span>
  <span data-ttu-id="a76c9-103">In questo argomento viene descritta la procedura per l'aggiunta di un'espressione nella trasformazione Suddivisione condizionale o Colonna derivata.</span><span class="sxs-lookup"><span data-stu-id="a76c9-103">This procedure describes how to add an expression to the Conditional Split transformation or to the Derived Column transformation.</span></span> <span data-ttu-id="a76c9-104">La trasformazione Suddivisione condizionale utilizza espressioni per definire le condizioni che dirigono le righe di dati all'output della trasformazione, mentre la trasformazione Colonna derivata utilizza espressioni per definire i valori assegnati alle colonne.</span><span class="sxs-lookup"><span data-stu-id="a76c9-104">The Conditional Split transformation uses expressions to define the conditions that direct data rows to a transformation output, and the Derived Column transformation uses expressions to define values assigned to columns.</span></span>  
  
 <span data-ttu-id="a76c9-105">Per implementare un'espressione in una trasformazione, è necessario che il pacchetto includa almeno un'attività Flusso di dati e un'origine.</span><span class="sxs-lookup"><span data-stu-id="a76c9-105">To implement an expression in a transformation, the package must already include at least one Data Flow task and a source.</span></span> <span data-ttu-id="a76c9-106">Per informazioni sull'aggiunta di questi elementi ai pacchetti, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a76c9-106">For information about adding items to packages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a76c9-107">Aggiunta o eliminazione di un'attività o un contenitore in un flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="a76c9-107">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
    
  
-   [<span data-ttu-id="a76c9-108">Aggiunta o eliminazione di un componente in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="a76c9-108">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
-   [<span data-ttu-id="a76c9-109">Connessione di componenti in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="a76c9-109">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)  
  
### <a name="to-create-an-expression"></a><span data-ttu-id="a76c9-110">Per creare un'espressione</span><span class="sxs-lookup"><span data-stu-id="a76c9-110">To create an expression</span></span>  
  
1.  <span data-ttu-id="a76c9-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="a76c9-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a76c9-112">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="a76c9-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a76c9-113">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] fare clic sulla scheda **Flusso di controllo** e quindi sull'attività Flusso di dati contenente il flusso di dati in cui si vuole implementare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="a76c9-113">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow** tab, and then click the Data Flow task that contains the data flow in which you want to implement an expression.</span></span>  
  
4.  <span data-ttu-id="a76c9-114">Fare clic sulla scheda **Flusso di dati** e trascinare una trasformazione Suddivisione condizionale o Colonna derivata dalla **casella degli strumenti** all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a76c9-114">Click the **Data Flow** tab, and drag either a Conditional Split or Derived Column transformation from the **Toolbox** to the design surface.</span></span>  
  
5.  <span data-ttu-id="a76c9-115">Trascinare il connettore verde dall'origine o trasformazione alla trasformazione Suddivisione condizionale o Colonna derivata.</span><span class="sxs-lookup"><span data-stu-id="a76c9-115">Drag the green connector from the source or a transformation to the Conditional Split or Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="a76c9-116">Fare doppio clic sulla trasformazione. Verrà visualizzata la finestra di dialogo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a76c9-116">Double-click the transformation to open its dialog box.</span></span>  
  
7.  <span data-ttu-id="a76c9-117">Nel riquadro di sinistra espandere il nodo **Variabili** in modo da visualizzare le variabili definite dall'utente e di sistema. Espandere anche il nodo **Colonne** in modo da visualizzare le colonne di input della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="a76c9-117">In the left pane, expand **Variables** to display system and user-defined variables, and expand **Columns** to display the transformation input columns.</span></span>  
  
8.  <span data-ttu-id="a76c9-118">Nel riquadro di destra espandere i nodi **Funzioni matematiche**, **Funzioni per i valori stringa**, **Funzioni di data/ora**, **Funzioni NULL**, **Cast di tipo**e **Operatori** per accedere alle funzioni, ai cast e agli operatori del linguaggio delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="a76c9-118">In the right pane, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators** to access the functions, the casts, and the operators that the expression grammar provides.</span></span>  
  
9. <span data-ttu-id="a76c9-119">A seconda della trasformazione, compilare un'espressione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a76c9-119">Depending on the transformation, do one of the following to build an expression:</span></span>  
  
    -   <span data-ttu-id="a76c9-120">Nella finestra di dialogo **Editor trasformazione Suddivisione condizionale** trascinare variabili, colonne, funzioni, operatori e cast nella colonna **Condizione** .</span><span class="sxs-lookup"><span data-stu-id="a76c9-120">In the **Conditional Split Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Condition** column.</span></span> <span data-ttu-id="a76c9-121">In alternativa, è possibile digitare l'espressione direttamente nella colonna **Condizione** .</span><span class="sxs-lookup"><span data-stu-id="a76c9-121">Alternatively, you can type an expression directly in the **Condition** column.</span></span>  
  
    -   <span data-ttu-id="a76c9-122">Nella finestra di dialogo **Editor trasformazione Colonna derivata** trascinare variabili, colonne, funzioni, operatori e cast nella colonna **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="a76c9-122">In the **Derived Column Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Expression** column.</span></span> <span data-ttu-id="a76c9-123">In alternativa, è possibile digitare l'espressione direttamente nella colonna **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="a76c9-123">Alternatively, you can type an expression directly in the **Expression** column.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a76c9-124">Quando lo stato attivo viene rimosso dalla colonna **Condizione** o **Espressione** , il testo dell'espressione potrebbe essere evidenziato per indicare che la sintassi dell'espressione non è corretta.</span><span class="sxs-lookup"><span data-stu-id="a76c9-124">When you remove the focus from the **Condition** column or the **Expression** column, the expression text might be highlighted to indicate that the expression syntax is incorrect.</span></span>  
  
10. <span data-ttu-id="a76c9-125">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a76c9-125">Click **OK** to exit the dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a76c9-126">Se l'espressione non è valida, viene visualizzato un avviso che evidenzia gli errori di sintassi.</span><span class="sxs-lookup"><span data-stu-id="a76c9-126">If the expression is not valid, an alert appears describing the syntax errors in the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76c9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a76c9-127">See Also</span></span>  
 <span data-ttu-id="a76c9-128">[Integration Services &#40;espressioni di&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="a76c9-128">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="a76c9-129">[Trasformazione Suddivisione condizionale](data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a76c9-129">[Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="a76c9-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a76c9-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span></span>  
 <span data-ttu-id="a76c9-131">[Attività Flusso di dati](control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="a76c9-131">[Data Flow Task](control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="a76c9-132">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="a76c9-132">Data Flow</span></span>](data-flow/data-flow.md)  
  
  
