---
title: Specifica di un numero di passaggi
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.breakpt.hitcount
helpviewer_keywords:
- Transact-SQL debugger, breakpoint hit count
ms.assetid: 24836939-94ed-4e57-aa85-5d6938d859e4
author: rothja
ms.author: jroth
ms.openlocfilehash: 34c75e990bce1ea5e64c0b45f7acbcaa52fc3c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635478"
---
# <a name="specify-a-hit-count"></a><span data-ttu-id="85e8d-102">Specifica di un numero di passaggi</span><span class="sxs-lookup"><span data-stu-id="85e8d-102">Specify a Hit Count</span></span>
  <span data-ttu-id="85e8d-103">Un numero di passaggi di un punto di interruzione è un contatore incrementato dal debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] ogni volta che viene raggiunto il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="85e8d-103">A breakpoint hit count is a counter that is incremented by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger each time the breakpoint is reached.</span></span> <span data-ttu-id="85e8d-104">Se viene raggiunto il numero di passaggi specificato e viene soddisfatta qualsiasi condizione per il punto di interruzione, il debugger esegue l'azione specificata per il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="85e8d-104">If the specified hit count is reached and any specified breakpoint condition is satisfied, the debugger performs the action specified for the breakpoint.</span></span>  
  
## <a name="hit-count-considerations"></a><span data-ttu-id="85e8d-105">Considerazioni relative al numero di passaggi</span><span class="sxs-lookup"><span data-stu-id="85e8d-105">Hit Count Considerations</span></span>  
 <span data-ttu-id="85e8d-106">Per impostazione predefinita, l'esecuzione viene interrotta ogni volta che viene rilevato un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="85e8d-106">By default, execution breaks every time a breakpoint is hit.</span></span> <span data-ttu-id="85e8d-107">È possibile scegliere tra una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85e8d-107">You can choose between the following options:</span></span>  
  
-   <span data-ttu-id="85e8d-108">Interrompi sempre (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="85e8d-108">Break always (the default).</span></span>  
  
-   <span data-ttu-id="85e8d-109">interrompi quando il numero di passaggi è uguale a [valore specificato]</span><span class="sxs-lookup"><span data-stu-id="85e8d-109">Break when the hit count equals a specified value.</span></span>  
  
-   <span data-ttu-id="85e8d-110">interrompi quando il numero di passaggi è un multiplo di [valore specificato]</span><span class="sxs-lookup"><span data-stu-id="85e8d-110">Break when the hit count equals a multiple of a specified value.</span></span>  
  
-   <span data-ttu-id="85e8d-111">Interrompi quando il numero di passaggi è maggiore o uguale a [valore specificato]</span><span class="sxs-lookup"><span data-stu-id="85e8d-111">Break when the hit count is greater than or equal to a specified value.</span></span>  
  
 <span data-ttu-id="85e8d-112">I numeri di passaggi dei punti di interruzione vengono incrementati nell'ambito di una sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="85e8d-112">Breakpoint hit counts are incremented within the scope of a debugging session.</span></span> <span data-ttu-id="85e8d-113">Tutti i numeri di passaggi vengono impostati su zero all'inizio di ogni sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="85e8d-113">All hit counts are set to zero at the start of each debugging session.</span></span>  
  
 <span data-ttu-id="85e8d-114">Se si desidera tenere traccia del numero di volte in cui viene rilevato un punto di interruzione senza che il punto di interruzione interrompa l'esecuzione, specificare un numero di passaggi con un valore molto elevato in modo che il punto di interruzione non effettui mai l'interruzione.</span><span class="sxs-lookup"><span data-stu-id="85e8d-114">If you want to track how many times a breakpoint is hit without having the breakpoint break execution, specify a hit count with a very high value so the breakpoint never breaks.</span></span>  
  
 <span data-ttu-id="85e8d-115">L'azione predefinita per un punto di interruzione consiste nell'interrompere l'esecuzione una volta raggiunto il numero di passaggi e soddisfatta la condizione per il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="85e8d-115">The default action for a breakpoint is to break execution when both the hit count and breakpoint condition have been satisfied.</span></span> <span data-ttu-id="85e8d-116">Per informazioni su come specificare altre azioni, vedere [Specificare un'azione del punto di interruzione](specify-a-breakpoint-action.md).</span><span class="sxs-lookup"><span data-stu-id="85e8d-116">For information about specifying other actions, see [Specify a Breakpoint Action](specify-a-breakpoint-action.md).</span></span>  
  
#### <a name="to-specify-a-hit-count"></a><span data-ttu-id="85e8d-117">Per specificare un numero di passaggi</span><span class="sxs-lookup"><span data-stu-id="85e8d-117">To Specify a Hit Count</span></span>  
  
1.  <span data-ttu-id="85e8d-118">Nella finestra dell'editor fare clic con il pulsante destro del mouse sul glifo del punto di interruzione e scegliere **Passaggi** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="85e8d-118">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="85e8d-119">-oppure-</span><span class="sxs-lookup"><span data-stu-id="85e8d-119">-or-</span></span>  
  
     <span data-ttu-id="85e8d-120">Nella finestra **Punti di interruzione** fare clic con il pulsante destro del mouse sul glifo del punto di interruzione e scegliere **Passaggi** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="85e8d-120">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="85e8d-121">Nella finestra di dialogo **Passaggi punto di interruzione** selezionare il comportamento desiderato nella casella **Quando il punto di interruzione viene raggiunto** .</span><span class="sxs-lookup"><span data-stu-id="85e8d-121">In the **Breakpoint Hit Count** dialog box, select the behavior you want from the **When the breakpoint is hit** box.</span></span>  
  
     <span data-ttu-id="85e8d-122">Se si sceglie un'impostazione diversa da **Interrompi sempre**, a destra dell'elenco verrà visualizzata una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="85e8d-122">If you choose any setting other than **Break Always**, a text box appears to the right of the list.</span></span> <span data-ttu-id="85e8d-123">Immettere un numero intero nella casella di testo per specificare il numero di passaggi desiderato.</span><span class="sxs-lookup"><span data-stu-id="85e8d-123">Enter an integer in the text box to specify the hit count you want.</span></span>  
  
3.  <span data-ttu-id="85e8d-124">Fare clic su **OK** per implementare le modifiche o su **Annulla** per uscire senza applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="85e8d-124">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
#### <a name="to-view-or-reset-the-current-hit-count"></a><span data-ttu-id="85e8d-125">Per visualizzare o reimpostare il numero di passaggi corrente</span><span class="sxs-lookup"><span data-stu-id="85e8d-125">To View or Reset the Current Hit Count</span></span>  
  
1.  <span data-ttu-id="85e8d-126">Nella finestra dell'editor fare clic con il pulsante destro del mouse sul glifo del punto di interruzione e scegliere **Passaggi** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="85e8d-126">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="85e8d-127">-oppure-</span><span class="sxs-lookup"><span data-stu-id="85e8d-127">-or-</span></span>  
  
     <span data-ttu-id="85e8d-128">Nella finestra **Punti di interruzione** fare clic con il pulsante destro del mouse sul glifo del punto di interruzione e scegliere **Passaggi** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="85e8d-128">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="85e8d-129">Nella finestra di dialogo **Passaggi punto di interruzione** verrà visualizzata l'opzione **Passaggi correnti:** al di sopra del pulsante **Reimposta** .</span><span class="sxs-lookup"><span data-stu-id="85e8d-129">In the **Breakpoint Hit Count** dialog box, the **Current hit count:** is displayed just above the **Reset** button.</span></span>  
  
3.  <span data-ttu-id="85e8d-130">Fare clic su **Reimposta** se si vuole impostare il numero di passaggi corrente su zero.</span><span class="sxs-lookup"><span data-stu-id="85e8d-130">Click **Reset** if you want to set the current hit count to zero.</span></span>  
  
4.  <span data-ttu-id="85e8d-131">Fare clic su **OK** o su **Annulla** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="85e8d-131">Click **OK** or **Cancel** to exit the dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e8d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85e8d-132">See Also</span></span>  
 [<span data-ttu-id="85e8d-133">Impostare una condizione del punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="85e8d-133">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)  
  
  
