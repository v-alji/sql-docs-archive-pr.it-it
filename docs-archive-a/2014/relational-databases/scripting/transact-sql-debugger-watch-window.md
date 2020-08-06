---
title: finestra Espressioni di controllo
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Watch Window [Transact-SQL]
ms.assetid: 23f3baa4-14c2-4262-92f7-3f43fcfa0436
author: rothja
ms.author: jroth
ms.openlocfilehash: c2a3db9b095902fcb5620af91fb86d80f773d606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635471"
---
# <a name="watch-window"></a><span data-ttu-id="28ed7-102">finestra Espressioni di controllo</span><span class="sxs-lookup"><span data-stu-id="28ed7-102">Watch Window</span></span>
  <span data-ttu-id="28ed7-103">Nella finestra **Espressione di controllo** vengono visualizzate informazioni sulle espressioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="28ed7-103">The **Watch** window displays information about the expressions that you have selected.</span></span> <span data-ttu-id="28ed7-104">Sono disponibili fino a quattro finestre di visualizzazione delle espressioni di controllo: **Espressione di controllo 1**, **Espressione di controllo 2, Espressione di controllo 3**ed **Espressione di controllo 4**.</span><span class="sxs-lookup"><span data-stu-id="28ed7-104">There can be up to four watch windows: **Watch 1**, **Watch 2, Watch 3**, and **Watch 4**.</span></span> <span data-ttu-id="28ed7-105">Le espressioni vengono valutate nell'ambito del frame dello stack di chiamate corrente selezionato nella finestra **Stack di chiamate** .</span><span class="sxs-lookup"><span data-stu-id="28ed7-105">The expressions are evaluated within the scope of the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="28ed7-106">Per controllare variabili ed espressioni, è necessario utilizzare la modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="28ed7-106">You must be in debug mode to watch variables and expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="28ed7-107">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="28ed7-107">Task List</span></span>  
 <span data-ttu-id="28ed7-108">**Per accedere alle finestre Espressione di controllo**</span><span class="sxs-lookup"><span data-stu-id="28ed7-108">**To access the Watch windows**</span></span>  
  
-   <span data-ttu-id="28ed7-109">Scegliere **Finestre** dal menu **Debug**, fare clic su **Espressione di controllo**, quindi su **Espressione di controllo 1**, **Espressione di controllo 2, Espressione di controllo 3**o **Espressione di controllo 4**.</span><span class="sxs-lookup"><span data-stu-id="28ed7-109">On the **Debug** menu, click **Windows**, click **Watch**, and then click **Watch 1**, **Watch 2, Watch 3**, or **Watch 4**.</span></span>  
  
 <span data-ttu-id="28ed7-110">**Per modificare il valore di un'espressione**</span><span class="sxs-lookup"><span data-stu-id="28ed7-110">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="28ed7-111">Fare clic con il pulsante destro del mouse sull'espressione e scegliere **Modifica valore**.</span><span class="sxs-lookup"><span data-stu-id="28ed7-111">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="28ed7-112">Colonne</span><span class="sxs-lookup"><span data-stu-id="28ed7-112">Columns</span></span>  
 <span data-ttu-id="28ed7-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="28ed7-113">**Name**</span></span>  
 <span data-ttu-id="28ed7-114">Espressioni elencate dal debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28ed7-114">Are the expressions that are listed by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="28ed7-115">Sono supportate le espressioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="28ed7-115">The following expressions are supported:</span></span>  
  
-   <span data-ttu-id="28ed7-116">Variabili.</span><span class="sxs-lookup"><span data-stu-id="28ed7-116">Variables.</span></span>  
  
-   <span data-ttu-id="28ed7-117">Parametri.</span><span class="sxs-lookup"><span data-stu-id="28ed7-117">Parameters.</span></span>  
  
-   <span data-ttu-id="28ed7-118">Funzioni di sistema il cui nome inizia con @@.</span><span class="sxs-lookup"><span data-stu-id="28ed7-118">System functions whose name starts with @@.</span></span>  
  
-   <span data-ttu-id="28ed7-119">Espressioni compilate applicando operatori a uno o più parametri, variabili o funzioni di sistema, ad esempio @@IntegerCounter + 1 o FirstName + LastName.</span><span class="sxs-lookup"><span data-stu-id="28ed7-119">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
-   <span data-ttu-id="28ed7-120">Istruzioni Transact-SQL tramite cui viene restituito un solo valore, ad esempio SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="28ed7-120">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
 <span data-ttu-id="28ed7-121">**Valore**</span><span class="sxs-lookup"><span data-stu-id="28ed7-121">**Value**</span></span>  
 <span data-ttu-id="28ed7-122">Consente di visualizzare il valore restituito dopo che il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] valuta l'espressione specificata in **Nome**.</span><span class="sxs-lookup"><span data-stu-id="28ed7-122">Displays the value that is returned after the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger evaluates the expression specified in **Name**.</span></span>  
  
 <span data-ttu-id="28ed7-123">Se la lunghezza di un'espressione è maggiore della larghezza della colonna **Valore** , il valore completo verrà visualizzato in una descrizione comandi quando si sposta il puntatore sulla cella **Valore** per l'espressione.</span><span class="sxs-lookup"><span data-stu-id="28ed7-123">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="28ed7-124">Un'icona di lente di ingrandimento in una cella **Valore** indica che è disponibile il visualizzatore del debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28ed7-124">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="28ed7-125">Nell'elenco è possibile specificare **Visualizzatore testo**, **Visualizzatore XML**o **Visualizzatore HTML**.</span><span class="sxs-lookup"><span data-stu-id="28ed7-125">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="28ed7-126">Per avviare un visualizzatore del debugger, fare clic sull'icona di lente di ingrandimento.</span><span class="sxs-lookup"><span data-stu-id="28ed7-126">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="28ed7-127">Nel debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] verrà visualizzata una finestra di dialogo contenente dati in un formato appropriato per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="28ed7-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="28ed7-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="28ed7-128">**Type**</span></span>  
 <span data-ttu-id="28ed7-129">Consente di visualizzare il tipo di dati dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="28ed7-129">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ed7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28ed7-130">See Also</span></span>  
 <span data-ttu-id="28ed7-131">[Debugger Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="28ed7-131">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="28ed7-132">[Informazioni del debugger Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="28ed7-132">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="28ed7-133">[finestra Variabili locali](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="28ed7-133">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="28ed7-134">[Finestra Stack di chiamate](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="28ed7-134">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="28ed7-135">[Finestra di dialogo Controllo immediato](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="28ed7-135">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="28ed7-136">Espressioni &#40; Transact-SQL &#41;</span><span class="sxs-lookup"><span data-stu-id="28ed7-136">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
