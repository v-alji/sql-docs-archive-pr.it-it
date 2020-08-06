---
title: Finestra di dialogo Controllo immediato
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.quickwatch
helpviewer_keywords:
- QuickWatch Dialog [Transact-SQL]
ms.assetid: d6bbb373-1452-41f2-bdc5-86ae689c3dc0
author: rothja
ms.author: jroth
ms.openlocfilehash: 48e4bda558b75bec0c81815c90feff9d6500a803
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637211"
---
# <a name="quickwatch-dialog-box"></a><span data-ttu-id="b75eb-102">Finestra di dialogo Controllo immediato</span><span class="sxs-lookup"><span data-stu-id="b75eb-102">QuickWatch Dialog Box</span></span>
  <span data-ttu-id="b75eb-103">Utilizzare la finestra di dialogo **Controllo immediato** per visualizzare rapidamente il tipo di dati e il valore di un'espressione [!INCLUDE[tsql](../../includes/tsql-md.md)] , ad esempio una variabile o un parametro, quando si esegue il debug di codice [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b75eb-103">Use the **QuickWatch** dialog box to quickly view the data type and value of one [!INCLUDE[tsql](../../includes/tsql-md.md)] expression, such as a variable or parameter, when you are debugging [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="b75eb-104">Per controllare più espressioni, è anche possibile aggiungere l'espressione a una finestra **Espressione di controllo** .</span><span class="sxs-lookup"><span data-stu-id="b75eb-104">To watch multiple expressions, you can also add the expression to a **Watch** window.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="b75eb-105">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="b75eb-105">Task List</span></span>  
 <span data-ttu-id="b75eb-106">**Per accedere alla finestra di dialogo Controllo immediato**</span><span class="sxs-lookup"><span data-stu-id="b75eb-106">**To access the QuickWatch dialog box**</span></span>  
  
-   <span data-ttu-id="b75eb-107">Scegliere **Controllo immediato** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="b75eb-107">On the **Debug** menu, click **QuickWatch**.</span></span>  
  
 <span data-ttu-id="b75eb-108">**Per visualizzare le informazioni relative a un'espressione**</span><span class="sxs-lookup"><span data-stu-id="b75eb-108">**To view the information about an expression**</span></span>  
  
1.  <span data-ttu-id="b75eb-109">Nella casella di riepilogo **Espressione** digitare o selezionare l'espressione desiderata.</span><span class="sxs-lookup"><span data-stu-id="b75eb-109">In the **Expression** list box, type or select the expression that you want.</span></span> <span data-ttu-id="b75eb-110">Sono supportate le espressioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="b75eb-110">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] expressions are supported:</span></span>  
  
    -   <span data-ttu-id="b75eb-111">Variabili.</span><span class="sxs-lookup"><span data-stu-id="b75eb-111">Variables.</span></span>  
  
    -   <span data-ttu-id="b75eb-112">Parametri.</span><span class="sxs-lookup"><span data-stu-id="b75eb-112">Parameters.</span></span>  
  
    -   <span data-ttu-id="b75eb-113">Funzioni di sistema il cui nome inizia con @@.</span><span class="sxs-lookup"><span data-stu-id="b75eb-113">System functions whose name starts with @@.</span></span>  
  
    -   <span data-ttu-id="b75eb-114">Espressioni compilate applicando operatori a uno o più parametri, variabili o funzioni di sistema, ad esempio @@IntegerCounter + 1 o FirstName + LastName.</span><span class="sxs-lookup"><span data-stu-id="b75eb-114">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
    -   <span data-ttu-id="b75eb-115">Istruzioni Transact-SQL tramite cui viene restituito un solo valore, ad esempio SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="b75eb-115">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
2.  <span data-ttu-id="b75eb-116">Fare clic su **Rivaluta**.</span><span class="sxs-lookup"><span data-stu-id="b75eb-116">Click **Reevaluate**.</span></span>  
  
 <span data-ttu-id="b75eb-117">**Per aggiungere un'espressione di controllo immediato a una finestra Espressione di controllo**</span><span class="sxs-lookup"><span data-stu-id="b75eb-117">**To add the QuickWatch expression to a Watch window**</span></span>  
  
-   <span data-ttu-id="b75eb-118">Fare clic su **Aggiungi espressione di controllo**.</span><span class="sxs-lookup"><span data-stu-id="b75eb-118">Click **Add Watch**.</span></span>  
  
 <span data-ttu-id="b75eb-119">**Per modificare il valore di un'espressione di controllo immediato**</span><span class="sxs-lookup"><span data-stu-id="b75eb-119">**To change the value of the QuickWatch expression**</span></span>  
  
-   <span data-ttu-id="b75eb-120">Fare clic con il pulsante destro del mouse sull'espressione e scegliere **Modifica valore**.</span><span class="sxs-lookup"><span data-stu-id="b75eb-120">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b75eb-121">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b75eb-121">Options</span></span>  
 <span data-ttu-id="b75eb-122">**Elenco di espressioni**</span><span class="sxs-lookup"><span data-stu-id="b75eb-122">**Expression list**</span></span>  
 <span data-ttu-id="b75eb-123">Consente di visualizzare l'espressione selezionata.</span><span class="sxs-lookup"><span data-stu-id="b75eb-123">Displays the currently selected expression.</span></span> <span data-ttu-id="b75eb-124">L'elenco a discesa contiene un set di espressioni che è possibile selezionare per visualizzarle.</span><span class="sxs-lookup"><span data-stu-id="b75eb-124">The drop-down list contains a set of expressions that you can select to display.</span></span> <span data-ttu-id="b75eb-125">Le espressioni incluse nell'elenco sono quelle disponibili nell'ambito del frame dello stack corrente selezionato nella finestra **Stack di chiamate** .</span><span class="sxs-lookup"><span data-stu-id="b75eb-125">The expressions in the list are those available in the scope of the stack frame that is currently selected in the **Call Stack** window.</span></span> <span data-ttu-id="b75eb-126">Per visualizzare un'espressione diversa, immettere l'espressione o selezionarla nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b75eb-126">To display a different expression, either enter the expression or select it from list.</span></span> <span data-ttu-id="b75eb-127">Il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] supporta le espressioni seguenti: variabili, parametri e le funzioni di sistema i cui nomi iniziano con @@.</span><span class="sxs-lookup"><span data-stu-id="b75eb-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports the following expressions: variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="b75eb-128">**Griglia Valore**</span><span class="sxs-lookup"><span data-stu-id="b75eb-128">**Value grid**</span></span>  
 <span data-ttu-id="b75eb-129">Consente di visualizzare le proprietà dell'espressione attualmente controllata.</span><span class="sxs-lookup"><span data-stu-id="b75eb-129">Displays the properties of the expression that is currently being watched.</span></span>  
  
 <span data-ttu-id="b75eb-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b75eb-130">**Name**</span></span>  
 <span data-ttu-id="b75eb-131">Espressione [!INCLUDE[tsql](../../includes/tsql-md.md)] controllata.</span><span class="sxs-lookup"><span data-stu-id="b75eb-131">Is the [!INCLUDE[tsql](../../includes/tsql-md.md)] expression being watched.</span></span>  
  
 <span data-ttu-id="b75eb-132">**Valore**</span><span class="sxs-lookup"><span data-stu-id="b75eb-132">**Value**</span></span>  
 <span data-ttu-id="b75eb-133">Consente di visualizzare il valore assegnato all'espressione.</span><span class="sxs-lookup"><span data-stu-id="b75eb-133">Displays the value that is currently assigned to the expression.</span></span> <span data-ttu-id="b75eb-134">Quando l'espressione non è associata ad alcun valore, viene visualizzato uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="b75eb-134">A blank is displayed when the expression currently has no value.</span></span>  
  
 <span data-ttu-id="b75eb-135">Se la lunghezza di un'espressione è maggiore della larghezza della colonna **Valore** , il valore completo verrà visualizzato in una descrizione comandi quando si sposta il puntatore sulla cella **Valore** per l'espressione.</span><span class="sxs-lookup"><span data-stu-id="b75eb-135">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="b75eb-136">Un'icona di lente di ingrandimento in una cella **Valore** indica che è disponibile il visualizzatore del debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b75eb-136">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="b75eb-137">Nell'elenco è possibile specificare **Visualizzatore testo**, **Visualizzatore XML**o **Visualizzatore HTML**.</span><span class="sxs-lookup"><span data-stu-id="b75eb-137">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="b75eb-138">Per avviare un visualizzatore del debugger, fare clic sull'icona di lente di ingrandimento.</span><span class="sxs-lookup"><span data-stu-id="b75eb-138">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="b75eb-139">Tramite il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] viene visualizzata una finestra di dialogo contenente dati in un formato appropriato per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="b75eb-139">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="b75eb-140">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b75eb-140">**Type**</span></span>  
 <span data-ttu-id="b75eb-141">Consente di visualizzare il tipo di dati dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="b75eb-141">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b75eb-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b75eb-142">See Also</span></span>  
 <span data-ttu-id="b75eb-143">[Debugger Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="b75eb-143">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="b75eb-144">[Informazioni del debugger Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="b75eb-144">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="b75eb-145">[finestra Espressioni di controllo](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="b75eb-145">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="b75eb-146">[finestra Variabili locali](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="b75eb-146">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="b75eb-147">[Finestra Stack di chiamate](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="b75eb-147">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 [<span data-ttu-id="b75eb-148">Espressioni &#40; Transact-SQL &#41;</span><span class="sxs-lookup"><span data-stu-id="b75eb-148">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
  
  
