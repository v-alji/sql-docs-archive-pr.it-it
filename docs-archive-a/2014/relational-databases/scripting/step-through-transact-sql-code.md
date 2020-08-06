---
title: Esecuzione istruzione per istruzione del codice Transact-SQL
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, debugging code
- Transact-SQL debugger, step over
- Transact-SQL debugger, step out
- Transact-SQL debugger, step into
ms.assetid: e09079b8-c4c9-42b4-821b-4ce81a98a086
author: rothja
ms.author: jroth
ms.openlocfilehash: 48cb307130c65729640864a26bdf1dfaf344b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636013"
---
# <a name="step-through-transact-sql-code"></a><span data-ttu-id="2581c-102">Esecuzione istruzione per istruzione del codice Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2581c-102">Step Through Transact-SQL Code</span></span>
  <span data-ttu-id="2581c-103">Il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] consente di controllare quali istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] vengono eseguite in una finestra dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2581c-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger enables you to control which [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are run in a [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span> <span data-ttu-id="2581c-104">È possibile sospendere l'esecuzione del debugger in corrispondenza di singole istruzioni e successivamente visualizzare lo stato degli elementi di codice in quei punti.</span><span class="sxs-lookup"><span data-stu-id="2581c-104">You can pause the debugger on individual statements and then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="2581c-105">Punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="2581c-105">Breakpoints</span></span>  
 <span data-ttu-id="2581c-106">Un punto di interruzione indica al debugger di sospendere temporaneamente l'esecuzione in corrispondenza di un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] specifica.</span><span class="sxs-lookup"><span data-stu-id="2581c-106">A breakpoint signals the debugger to pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="2581c-107">Per ulteriori informazioni sui punti di interruzione, vedere Utilizzo di punti di interruzione Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="2581c-107">For more information about breakpoints, see Using Transact-SQL Breakpoints.</span></span>  
  
## <a name="controlling-statement-execution"></a><span data-ttu-id="2581c-108">Controllo dell'esecuzione di istruzioni</span><span class="sxs-lookup"><span data-stu-id="2581c-108">Controlling Statement Execution</span></span>  
 <span data-ttu-id="2581c-109">Nel debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] è possibile specificare le opzioni seguenti per eseguire il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] dall'istruzione corrente:</span><span class="sxs-lookup"><span data-stu-id="2581c-109">In the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can specify the following options for executing from the current statement in [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
-   <span data-ttu-id="2581c-110">Eseguire il codice fino al successivo punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2581c-110">Run to the next breakpoint.</span></span>  
  
-   <span data-ttu-id="2581c-111">Eseguire la successiva istruzione.</span><span class="sxs-lookup"><span data-stu-id="2581c-111">Step into the next statement.</span></span>  
  
     <span data-ttu-id="2581c-112">Se l'istruzione successiva richiama una stored procedure, una funzione o un trigger [!INCLUDE[tsql](../../includes/tsql-md.md)] , verrà visualizzata dal debugger una nuova finestra dell'editor di query contenente il codice del modulo.</span><span class="sxs-lookup"><span data-stu-id="2581c-112">If the next statement invokes a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, function, or trigger, the debugger displays a new Query Editor window that contains the code of the module.</span></span> <span data-ttu-id="2581c-113">La finestra sarà in modalità di debug e l'esecuzione verrà sospesa in corrispondenza della prima istruzione nel modulo.</span><span class="sxs-lookup"><span data-stu-id="2581c-113">The window is in debug mode, and execution pauses on the first statement in the module.</span></span> <span data-ttu-id="2581c-114">È possibile spostarsi quindi nel codice del modulo, ad esempio, impostando dei punti di interruzione o avanzando istruzione per istruzione nel codice.</span><span class="sxs-lookup"><span data-stu-id="2581c-114">You can then move through the module code, for example, by setting breakpoints or stepping through the code.</span></span>  
  
-   <span data-ttu-id="2581c-115">Passare all'istruzione successiva.</span><span class="sxs-lookup"><span data-stu-id="2581c-115">Step over the next statement.</span></span>  
  
     <span data-ttu-id="2581c-116">Viene eseguita l'istruzione successiva.</span><span class="sxs-lookup"><span data-stu-id="2581c-116">The next statement is executed.</span></span> <span data-ttu-id="2581c-117">Tuttavia, se l'istruzione richiama una stored procedure, una funzione o un trigger, il codice del modulo viene eseguito fino alla fine e i risultati vengono restituiti al codice che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2581c-117">However, if the statement invokes a stored procedure, function, or trigger, the module code runs until it finishes, and the results are returned to the calling code.</span></span> <span data-ttu-id="2581c-118">Se si è sicuri che in una stored procedure non vi siano errori, è possibile superarla.</span><span class="sxs-lookup"><span data-stu-id="2581c-118">If you are sure there are no errors in a stored procedure, you can step over it.</span></span> <span data-ttu-id="2581c-119">L'esecuzione viene sospesa in corrispondenza dell'istruzione che segue la chiamata alla stored procedure, la funzione o il trigger.</span><span class="sxs-lookup"><span data-stu-id="2581c-119">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="2581c-120">Uscire da una stored procedure, una funzione o un trigger.</span><span class="sxs-lookup"><span data-stu-id="2581c-120">Step out of a stored procedure, function, or trigger.</span></span>  
  
     <span data-ttu-id="2581c-121">L'esecuzione viene sospesa in corrispondenza dell'istruzione che segue la chiamata alla stored procedure, la funzione o il trigger.</span><span class="sxs-lookup"><span data-stu-id="2581c-121">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="2581c-122">Eseguire il codice dalla posizione corrente alla posizione corrente del puntatore e ignorare tutti i punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2581c-122">Run from the current location to the current location of the pointer, and ignore all breakpoints.</span></span>  
  
 <span data-ttu-id="2581c-123">Nella tabella seguente sono elencate le varie procedure che consentono di controllare il modo in cui le istruzioni sono eseguite nel debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2581c-123">The following table lists the various ways in which you can control how statements execute in the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span>  
  
|<span data-ttu-id="2581c-124">Azione</span><span class="sxs-lookup"><span data-stu-id="2581c-124">Action</span></span>|<span data-ttu-id="2581c-125">Procedura</span><span class="sxs-lookup"><span data-stu-id="2581c-125">Procedure</span></span>|  
|------------|---------------|  
|<span data-ttu-id="2581c-126">Eseguire tutte le istruzioni dall'istruzione corrente al successivo punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="2581c-126">Run all statements from the current statement to the next breakpoint</span></span>|<span data-ttu-id="2581c-127">Scegliere **Continua** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="2581c-127">On the **Debug** menu, click **Continue**.</span></span><br /><br /> <span data-ttu-id="2581c-128">Sulla barra degli strumenti **debug** fare clic sul pulsante **continue (continua** ).</span><span class="sxs-lookup"><span data-stu-id="2581c-128">On the **Debug** toolbar, click the **Continue** button.</span></span>|  
|<span data-ttu-id="2581c-129">Eseguire la successiva istruzione o il successivo modulo.</span><span class="sxs-lookup"><span data-stu-id="2581c-129">Step into the next statement or module</span></span>|<span data-ttu-id="2581c-130">Scegliere **Esegui istruzione**dal menu **debug** .</span><span class="sxs-lookup"><span data-stu-id="2581c-130">On the **Debug** menu, click **Step Into**.</span></span><br /><br /> <span data-ttu-id="2581c-131">Sulla barra degli strumenti **debug** fare clic sul pulsante **Esegui istruzione** .</span><span class="sxs-lookup"><span data-stu-id="2581c-131">On the **Debug** toolbar, click the **Step Into** button.</span></span><br /><br /> <span data-ttu-id="2581c-132">Premere F11.</span><span class="sxs-lookup"><span data-stu-id="2581c-132">Press F11.</span></span>|  
|<span data-ttu-id="2581c-133">Passare alla successiva istruzione o al successivo modulo.</span><span class="sxs-lookup"><span data-stu-id="2581c-133">Step over the next statement or module</span></span>|<span data-ttu-id="2581c-134">Scegliere **Esegui istruzione/routine** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="2581c-134">On the **Debug** menu, click **Step Over**.</span></span><br /><br /> <span data-ttu-id="2581c-135">Sulla barra degli strumenti **debug** fare clic sul pulsante **Esegui istruzione/** routine.</span><span class="sxs-lookup"><span data-stu-id="2581c-135">On the **Debug** toolbar, click the **Step Over** button.</span></span><br /><br /> <span data-ttu-id="2581c-136">Premere F10.</span><span class="sxs-lookup"><span data-stu-id="2581c-136">Press F10.</span></span>|  
|<span data-ttu-id="2581c-137">Uscire da un modulo</span><span class="sxs-lookup"><span data-stu-id="2581c-137">Step out of a module</span></span>|<span data-ttu-id="2581c-138">Dal menu **debug** scegliere **Esci da istruzione/uscita**.</span><span class="sxs-lookup"><span data-stu-id="2581c-138">On the **Debug** menu, click **Step Out**.</span></span><br /><br /> <span data-ttu-id="2581c-139">Sulla barra degli strumenti **debug** fare clic sul pulsante Esci **da istruzione/uscita** .</span><span class="sxs-lookup"><span data-stu-id="2581c-139">On the **Debug** toolbar, click the **Step Out** button.</span></span><br /><br /> <span data-ttu-id="2581c-140">Premere MAIUSC+F11.</span><span class="sxs-lookup"><span data-stu-id="2581c-140">Press SHIFT+F11.</span></span>|  
|<span data-ttu-id="2581c-141">Eseguire il codice fino alla posizione corrente del cursore</span><span class="sxs-lookup"><span data-stu-id="2581c-141">Run to the current cursor location</span></span>|<span data-ttu-id="2581c-142">Fare clic con il pulsante destro del mouse nella finestra dell'editor di query, quindi fare clic su **Esegui fino al cursore**.</span><span class="sxs-lookup"><span data-stu-id="2581c-142">Right-click in the Query Editor window, and then click **Run To Cursor**.</span></span><br /><br /> <span data-ttu-id="2581c-143">Premere CTRL+F10.</span><span class="sxs-lookup"><span data-stu-id="2581c-143">Press CTRL+F10.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2581c-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2581c-144">See Also</span></span>  
 [<span data-ttu-id="2581c-145">Informazioni del debugger Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2581c-145">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
