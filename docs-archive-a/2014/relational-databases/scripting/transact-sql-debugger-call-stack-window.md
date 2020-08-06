---
title: Finestra Stack di chiamate
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Call Stack Window [Transact-SQL]
ms.assetid: ddb0b19c-87cd-4883-bcb8-ec09ffb30369
author: rothja
ms.author: jroth
ms.openlocfilehash: b4b72e484ade696be81ebac8ea4eed9be295edf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636665"
---
# <a name="call-stack-window"></a><span data-ttu-id="99d4d-102">Finestra Stack di chiamate</span><span class="sxs-lookup"><span data-stu-id="99d4d-102">Call Stack Window</span></span>
  <span data-ttu-id="99d4d-103">Nella finestra **Stack di chiamate** vengono visualizzati i moduli nello stack di chiamate e i tipi di dati e i valori di qualsiasi parametro passati ai moduli.</span><span class="sxs-lookup"><span data-stu-id="99d4d-103">The **Call Stack** window displays the modules on the call stack, and the data types and values of any parameters that are passed to the modules.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="99d4d-104">i moduli includono stored procedure, funzioni e trigger.</span><span class="sxs-lookup"><span data-stu-id="99d4d-104">modules include stored procedures, functions, and triggers.</span></span> <span data-ttu-id="99d4d-105">Per visualizzare lo stack di chiamate, è necessario utilizzare la modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="99d4d-105">To display the call stack, you must be in debug mode.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="99d4d-106">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="99d4d-106">Task List</span></span>  
 <span data-ttu-id="99d4d-107">**Per accedere alla finestra Stack di chiamate**</span><span class="sxs-lookup"><span data-stu-id="99d4d-107">**To access the Call Stack window**</span></span>  
  
-   <span data-ttu-id="99d4d-108">Scegliere **Finestre** dal menu **Debug**, quindi fare clic su **Stack di chiamate**.</span><span class="sxs-lookup"><span data-stu-id="99d4d-108">On the **Debug** menu, click **Windows**, and then click **Call Stack**.</span></span>  
  
 <span data-ttu-id="99d4d-109">**Per modificare il frame dello stack di chiamate corrente**</span><span class="sxs-lookup"><span data-stu-id="99d4d-109">**To change the current Call Stack frame**</span></span>  
  
 <span data-ttu-id="99d4d-110">Per impostare il frame dello stack come frame corrente, è possibile utilizzare una delle procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="99d4d-110">You can use either of the following procedures to make a stack frame the current frame:</span></span>  
  
-   <span data-ttu-id="99d4d-111">Fare clic con il pulsante destro del mouse sul frame dello stack, quindi scegliere **Passa al frame**.</span><span class="sxs-lookup"><span data-stu-id="99d4d-111">Right-click the stack frame, and then click **Switch To Frame**.</span></span>  
  
-   <span data-ttu-id="99d4d-112">Fare doppio clic sul frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="99d4d-112">Double-click the stack frame.</span></span>  
  
 <span data-ttu-id="99d4d-113">**Per visualizzare l'origine di un frame diversa dal frame corrente**</span><span class="sxs-lookup"><span data-stu-id="99d4d-113">**To view the source of a frame other than the current frame**</span></span>  
  
-   <span data-ttu-id="99d4d-114">Fare clic con il pulsante destro del mouse sul frame dello stack, quindi scegliere **Vai a codice sorgente**.</span><span class="sxs-lookup"><span data-stu-id="99d4d-114">Right-click the stack frame, and then click **Go To Source Code**.</span></span>  
  
## <a name="stack-frames"></a><span data-ttu-id="99d4d-115">Frame dello stack</span><span class="sxs-lookup"><span data-stu-id="99d4d-115">Stack Frames</span></span>  
 <span data-ttu-id="99d4d-116">Ogni riga nella finestra **Stack di chiamate** è denominata frame dello stack e rappresenta una chiamata da un file script [!INCLUDE[tsql](../../includes/tsql-md.md)] a un modulo o una chiamata da un modulo a un altro modulo.</span><span class="sxs-lookup"><span data-stu-id="99d4d-116">Each row in the **Call Stack** window is called a stack frame and represents either a call from a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file to a module or a call from one module to another.</span></span> <span data-ttu-id="99d4d-117">Il frame dello stack inferiore nella visualizzazione indica la riga nella finestra dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] che ha eseguito la prima chiamata nello stack.</span><span class="sxs-lookup"><span data-stu-id="99d4d-117">The bottom stack frame in the display indicates the line in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window that made the first call into the stack.</span></span> <span data-ttu-id="99d4d-118">La riga superiore indica la riga in cui il debugger ha sospeso l'esecuzione ed è identificata da una freccia gialla nel margine sinistro della finestra.</span><span class="sxs-lookup"><span data-stu-id="99d4d-118">The top row indicates the line on which the debugger paused execution, and is identified by a yellow arrow in the left margin of the window.</span></span> <span data-ttu-id="99d4d-119">Ogni riga intermedia indica il modulo e il numero di riga del codice sorgente che ha chiamato il frame dello stack superiore successivo.</span><span class="sxs-lookup"><span data-stu-id="99d4d-119">Each intermediate row indicates the module and the line number of the source code that called the next higher stack frame.</span></span>  
  
 <span data-ttu-id="99d4d-120">Tutte le espressioni incluse nelle finestre **Variabili locali**, **Espressione di controllo**e **Controllo immediato** vengono valutate in base al frame dello stack corrente.</span><span class="sxs-lookup"><span data-stu-id="99d4d-120">All expressions in the **Locals**, **Watch**, and **QuickWatch** windows are evaluated based on the current stack frame.</span></span> <span data-ttu-id="99d4d-121">Nella finestra dell'editor di query viene visualizzato il codice per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="99d4d-121">The Query Editor window displays the code for the current frame.</span></span> <span data-ttu-id="99d4d-122">Per impostazione predefinita, il frame dello stack corrente è il frame in cui il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] ha sospeso l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="99d4d-122">By default, the current stack frame is the frame in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger paused execution.</span></span> <span data-ttu-id="99d4d-123">Quando si imposta il frame dello stack corrente su un altro frame, le espressioni incluse nelle finestre **Variabili locali**, **Espressione di controllo**e **Controllo immediato** vengono nuovamente valutate nel contesto del nuovo frame e il codice sorgente del nuovo frame viene visualizzato nella finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="99d4d-123">When you change the current stack frame to another frame, the expressions in the **Locals**, **Watch**, and **QuickWatch** windows are reevaluated in the context of the new frame, and the source code of the new frame is displayed in the Query Editor window.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="99d4d-124">Colonne</span><span class="sxs-lookup"><span data-stu-id="99d4d-124">Columns</span></span>  
 <span data-ttu-id="99d4d-125">**Nome**</span><span class="sxs-lookup"><span data-stu-id="99d4d-125">**Name**</span></span>  
 <span data-ttu-id="99d4d-126">Vengono visualizzate informazioni su un modulo nello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="99d4d-126">Displays information about a module on the call stack.</span></span>  
  
 <span data-ttu-id="99d4d-127">Per la riga inferiore nello stack di chiamate, in **Nome** vengono indicati la finestra di origine dell'editor di query e il numero di riga della prima chiamata nello stack.</span><span class="sxs-lookup"><span data-stu-id="99d4d-127">For the bottom row in the call stack, **Name** lists the Query Editor source window and line number of the first call into the stack.</span></span> <span data-ttu-id="99d4d-128">Per le altre righe, **Nome** usa il formato **Module(Instance.Database)(ParmList) LineNumber**.</span><span class="sxs-lookup"><span data-stu-id="99d4d-128">For the other rows, **Name** has the format **Module(Instance.Database)(ParmList) LineNumber**.</span></span>  
  
 <span data-ttu-id="99d4d-129">**Modulo**</span><span class="sxs-lookup"><span data-stu-id="99d4d-129">**Module**</span></span>  
 <span data-ttu-id="99d4d-130">Nome della stored procedure o della funzione che ha eseguito la chiamata al frame successivo.</span><span class="sxs-lookup"><span data-stu-id="99d4d-130">Is the name of the stored procedure, function, or stored procedure that called to the next frame.</span></span>  
  
 <span data-ttu-id="99d4d-131">**Instance.Database**</span><span class="sxs-lookup"><span data-stu-id="99d4d-131">**Instance.Database**</span></span>  
 <span data-ttu-id="99d4d-132">Istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] e database che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="99d4d-132">Is the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the database that is holding the module.</span></span>  
  
 <span data-ttu-id="99d4d-133">**ParmList**</span><span class="sxs-lookup"><span data-stu-id="99d4d-133">**ParmList**</span></span>  
 <span data-ttu-id="99d4d-134">Indica il tipo di dati, il nome e il valore per ogni parametro passato durante la chiamata al modulo.</span><span class="sxs-lookup"><span data-stu-id="99d4d-134">Indicates the data type, name, and value for each parameter that is passed in during the call to the module.</span></span>  
  
 <span data-ttu-id="99d4d-135">**LineNumber**</span><span class="sxs-lookup"><span data-stu-id="99d4d-135">**LineNumber**</span></span>  
 <span data-ttu-id="99d4d-136">Per tutte le righe ad eccezione di quella superiore, **LineNumber** indica la riga nel modulo che ha eseguito la chiamata al frame.</span><span class="sxs-lookup"><span data-stu-id="99d4d-136">For all rows except the top row, **LineNumber** indicates which line in the module called to the frame.</span></span> <span data-ttu-id="99d4d-137">Per la riga superiore, **LineNumber** indica la riga in cui è attualmente attivo il debugger.</span><span class="sxs-lookup"><span data-stu-id="99d4d-137">For the top row, **LineNumber** indicates the line on which the debugger is currently focused.</span></span>  
  
 <span data-ttu-id="99d4d-138">**Lingua**</span><span class="sxs-lookup"><span data-stu-id="99d4d-138">**Language**</span></span>  
 <span data-ttu-id="99d4d-139">Viene visualizzato **Transact-SQL** per [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99d4d-139">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d4d-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99d4d-140">See Also</span></span>  
 <span data-ttu-id="99d4d-141">[Debugger Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="99d4d-141">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="99d4d-142">[Informazioni del debugger Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="99d4d-142">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 [<span data-ttu-id="99d4d-143">Eseguire istruzione per istruzione il codice Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99d4d-143">Step Through Transact-SQL Code</span></span>](step-through-transact-sql-code.md)  
