---
title: Finestra Punti di interruzione
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Breakpoints Window [Transact-SQL]
ms.assetid: bad88d10-fdd5-4d3d-b5ea-a4f063847485
author: rothja
ms.author: jroth
ms.openlocfilehash: 077d501e581ed5baaac45cc6bbbb34e0040730e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636004"
---
# <a name="breakpoints-window"></a><span data-ttu-id="2c372-102">Finestra Punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="2c372-102">Breakpoints Window</span></span>
  <span data-ttu-id="2c372-103">Nella finestra **Punti di interruzione** sono elencati tutti i punti di interruzione impostati nell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] corrente.</span><span class="sxs-lookup"><span data-stu-id="2c372-103">The **Breakpoints** window lists all the breakpoints that are set in the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="2c372-104">Per gestire i punti di interruzione, usare la barra degli strumenti nella finestra **Punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="2c372-104">To manage the breakpoints, use the toolbar in the **Breakpoints** window.</span></span> <span data-ttu-id="2c372-105">I punti di interruzione sono posizioni nel codice in cui viene sospesa l'esecuzione in modalità di debug per consentire la visualizzazione dei dati di debug.</span><span class="sxs-lookup"><span data-stu-id="2c372-105">Breakpoints are locations in the code where execution pauses in debug mode so that you can view debugging data.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="2c372-106">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="2c372-106">Task List</span></span>  
 <span data-ttu-id="2c372-107">**Per accedere alla finestra Punti di interruzione**</span><span class="sxs-lookup"><span data-stu-id="2c372-107">**To access the Breakpoints window**</span></span>  
  
-   <span data-ttu-id="2c372-108">Scegliere **Finestre** dal menu **Debug**, quindi fare clic su **Punti di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="2c372-108">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
## <a name="breakpoints-window-columns"></a><span data-ttu-id="2c372-109">Colonne della finestra Punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="2c372-109">Breakpoints Window Columns</span></span>  
 <span data-ttu-id="2c372-110">Per impostazione predefinita, la finestra **Punti di interruzione** include le colonne seguenti.</span><span class="sxs-lookup"><span data-stu-id="2c372-110">By default, the **Breakpoints** window lists the following columns.</span></span>  
  
 <span data-ttu-id="2c372-111">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2c372-111">**Name**</span></span>  
 <span data-ttu-id="2c372-112">Consente di visualizzare il nome del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2c372-112">Displays the name of the breakpoint.</span></span> <span data-ttu-id="2c372-113">I nomi dei punti di interruzione vengono forniti dal debugger.</span><span class="sxs-lookup"><span data-stu-id="2c372-113">Breakpoint names are provided by the debugger.</span></span> <span data-ttu-id="2c372-114">Questo nome include il nome della finestra dell'editor di query del Motore di database che contiene il punto di interruzione e il numero di riga nell'editor di query in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2c372-114">This name includes the name of Database Engine Query Editor window that contains the breakpoint, and the line number in the Query Editor on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="2c372-115">**Condition**</span><span class="sxs-lookup"><span data-stu-id="2c372-115">**Condition**</span></span>  
 <span data-ttu-id="2c372-116">Viene visualizzato **(nessuna condizione)** .</span><span class="sxs-lookup"><span data-stu-id="2c372-116">Displays **(no condition)**.</span></span> <span data-ttu-id="2c372-117">Il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] non supporta l'impostazione di condizioni per i punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2c372-117">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint conditions.</span></span>  
  
 <span data-ttu-id="2c372-118">**Passaggi**</span><span class="sxs-lookup"><span data-stu-id="2c372-118">**Hit Count**</span></span>  
 <span data-ttu-id="2c372-119">Viene visualizzato**interrompi sempre**.</span><span class="sxs-lookup"><span data-stu-id="2c372-119">Displays**breaks always**.</span></span>  
  
 <span data-ttu-id="2c372-120">È possibile aggiungere e rimuovere le colonne seguenti selezionandole nell'elenco **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="2c372-120">You can add and remove the following columns by selecting them on the **Columns** list.</span></span>  
  
 <span data-ttu-id="2c372-121">**Filter**</span><span class="sxs-lookup"><span data-stu-id="2c372-121">**Filter**</span></span>  
 <span data-ttu-id="2c372-122">Viene visualizzato **(nessuno)** .</span><span class="sxs-lookup"><span data-stu-id="2c372-122">Displays **(none)**.</span></span> <span data-ttu-id="2c372-123">Il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] non supporta l'impostazione di filtri per i punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2c372-123">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint filters.</span></span>  
  
 <span data-ttu-id="2c372-124">**Quando raggiunto**</span><span class="sxs-lookup"><span data-stu-id="2c372-124">**When Hit**</span></span>  
 <span data-ttu-id="2c372-125">Viene visualizzato **Interrompi**.</span><span class="sxs-lookup"><span data-stu-id="2c372-125">Displays **Break**.</span></span>  
  
 <span data-ttu-id="2c372-126">**Lingua**</span><span class="sxs-lookup"><span data-stu-id="2c372-126">**Language**</span></span>  
 <span data-ttu-id="2c372-127">Viene visualizzato **Transact-SQL** per [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c372-127">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2c372-128">**Funzione**</span><span class="sxs-lookup"><span data-stu-id="2c372-128">**Function**</span></span>  
 <span data-ttu-id="2c372-129">Consente di visualizzare il numero della riga in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2c372-129">Displays the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="2c372-130">**File**</span><span class="sxs-lookup"><span data-stu-id="2c372-130">**File**</span></span>  
 <span data-ttu-id="2c372-131">Consente di visualizzare il nome del file di origine che contiene il punto di interruzione e il numero della riga in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2c372-131">Displays the name of the source file that contains the breakpoint, and the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="2c372-132">**Indirizzo**</span><span class="sxs-lookup"><span data-stu-id="2c372-132">**Address**</span></span>  
 <span data-ttu-id="2c372-133">Il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] non supporta questa caratteristica.</span><span class="sxs-lookup"><span data-stu-id="2c372-133">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="2c372-134">**Processo**</span><span class="sxs-lookup"><span data-stu-id="2c372-134">**Process**</span></span>  
 <span data-ttu-id="2c372-135">Viene visualizzato **[SQL]** , a indicare che si tratta di un processo del [!INCLUDE[ssDE](../../includes/ssde-md.md)] ,</span><span class="sxs-lookup"><span data-stu-id="2c372-135">Displays **[SQL]** to indicate that this is a [!INCLUDE[ssDE](../../includes/ssde-md.md)] process.</span></span> <span data-ttu-id="2c372-136">seguito dal nome dell'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] in cui viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="2c372-136">This is followed by the name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the code executes.</span></span>  
  
## <a name="breakpoints-window-toolbar"></a><span data-ttu-id="2c372-137">Barra degli strumenti della finestra Punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="2c372-137">Breakpoints Window Toolbar</span></span>  
 <span data-ttu-id="2c372-138">Quando la finestra dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] corrente include punti di interruzione attivi, nella finestra **Punti di interruzione** viene visualizzata una barra degli strumenti che può essere usata per gestire i punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2c372-138">When the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window has active breakpoints, the **Breakpoints** window displays a toolbar that can be used to manage the breakpoints.</span></span>  
  
 <span data-ttu-id="2c372-139">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="2c372-139">**Delete**</span></span>  
 <span data-ttu-id="2c372-140">Consente di eliminare il punto di interruzione selezionato.</span><span class="sxs-lookup"><span data-stu-id="2c372-140">Deletes the selected breakpoint.</span></span>  
  
 <span data-ttu-id="2c372-141">**Elimina tutti i punti di interruzione**</span><span class="sxs-lookup"><span data-stu-id="2c372-141">**Delete All Breakpoints**</span></span>  
 <span data-ttu-id="2c372-142">Consente di eliminare tutti i punti di interruzione visualizzati nella finestra **Punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="2c372-142">Deletes all breakpoints that are displayed in the **Breakpoints** window.</span></span>  
  
 <span data-ttu-id="2c372-143">**Disabilita tutti i punti di interruzione**</span><span class="sxs-lookup"><span data-stu-id="2c372-143">**Disable All Breakpoints**</span></span>  
 <span data-ttu-id="2c372-144">Consente di disabilitare tutti i punti di interruzione perché non arrestino più l'esecuzione del codice. I punti di interruzione, tuttavia, non vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="2c372-144">Disables all breakpoints so that they no longer stop code execution; however, the breakpoints remain.</span></span> <span data-ttu-id="2c372-145">Quando tutti i punti di interruzione sono disabilitati, il nome di questo pulsante diventa **Abilita tutti i punti di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="2c372-145">When all the breakpoints are disabled, this button becomes **Enable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="2c372-146">**Abilita tutti i punti di interruzione**</span><span class="sxs-lookup"><span data-stu-id="2c372-146">**Enable All Breakpoints**</span></span>  
 <span data-ttu-id="2c372-147">Consente di abilitare tutti i punti di interruzione in modo che arrestino l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="2c372-147">Enables all breakpoints so that they stop code execution.</span></span> <span data-ttu-id="2c372-148">Quando tutti i punti di interruzione sono abilitati, il nome di questo pulsante diventa **Disabilita tutti i punti di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="2c372-148">When all breakpoints are enabled, this button becomes **Disable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="2c372-149">**Vai a codice sorgente**</span><span class="sxs-lookup"><span data-stu-id="2c372-149">**Go To Source Code**</span></span>  
 <span data-ttu-id="2c372-150">Consente di posizionare il cursore sulla riga dell'editor di query che contiene il punto di interruzione selezionato.</span><span class="sxs-lookup"><span data-stu-id="2c372-150">Positions the cursor on the line in the Query Editor that contains the selected breakpoint.</span></span>  
  
 <span data-ttu-id="2c372-151">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2c372-151">**Columns**</span></span>  
 <span data-ttu-id="2c372-152">Vengono elencate tutte le colonne che è possibile visualizzare nella finestra **Punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="2c372-152">Lists all the columns that can be displayed in the **Breakpoints** window.</span></span> <span data-ttu-id="2c372-153">Una casella di controllo indica le colonne visualizzate.</span><span class="sxs-lookup"><span data-stu-id="2c372-153">A check box indicates the columns that are displayed.</span></span> <span data-ttu-id="2c372-154">Per aggiungere o rimuovere una colonna nella finestra **Punti di interruzione** , selezionarla nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2c372-154">To add or remove a column in the **Breakpoints** window, select the column on the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c372-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c372-155">See Also</span></span>  
 [<span data-ttu-id="2c372-156">Debugger Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2c372-156">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
