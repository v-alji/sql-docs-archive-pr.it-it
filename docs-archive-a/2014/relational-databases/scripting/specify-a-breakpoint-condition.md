---
title: Impostare una condizione del punto di interruzione
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint conditions
ms.assetid: b43d8a2b-99a3-4fb7-8848-99c042ea7ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 659b6ca1149eb8f0412efbe2adbaf4c1ffce59d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717796"
---
# <a name="specify-a-breakpoint-condition"></a><span data-ttu-id="bc822-102">Impostare una condizione del punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="bc822-102">Specify a Breakpoint Condition</span></span>
  <span data-ttu-id="bc822-103">Una condizione per il punto di interruzione è un'espressione [!INCLUDE[tsql](../../includes/tsql-md.md)] valutata dal debugger quando viene raggiunto il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="bc822-103">A breakpoint condition is a [!INCLUDE[tsql](../../includes/tsql-md.md)] expression that is evaluated by the debugger when the breakpoint is reached.</span></span> <span data-ttu-id="bc822-104">Se la condizione viene soddisfatta e viene raggiunto un numero di passaggi specificato, il debugger interrompe o esegue l'azione specificata per il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="bc822-104">If the condition is satisfied and any specified hit count reached, the debugger either breaks or performs the action specified for the breakpoint.</span></span>  
  
## <a name="specifying-conditions"></a><span data-ttu-id="bc822-105">Definizione delle condizioni</span><span class="sxs-lookup"><span data-stu-id="bc822-105">Specifying Conditions</span></span>  
 <span data-ttu-id="bc822-106">L'espressione specificata deve essere un'espressione Transact-SQL valida che restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="bc822-106">The expression specified must be a valid Transact-SQL expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="bc822-107">Per altre informazioni, vedere [Espressioni &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bc822-107">For more information, see [Expressions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span></span>  
  
 <span data-ttu-id="bc822-108">Se si specifica una condizione per il punto di interruzione con una sintassi non valida, viene immediatamente visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="bc822-108">If you specify a breakpoint condition with invalid syntax, a warning message appears immediately.</span></span> <span data-ttu-id="bc822-109">Se si specifica una condizione con una sintassi valida ma una semantica non valida, viene visualizzato un messaggio di avviso la prima volta che viene raggiunto il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="bc822-109">If you specify a condition with valid syntax but invalid semantics, a warning message is displayed the first time the breakpoint is hit.</span></span> <span data-ttu-id="bc822-110">In entrambi i casi, il debugger interrompe l'esecuzione al raggiungimento del punto di interruzione non valido.</span><span class="sxs-lookup"><span data-stu-id="bc822-110">In either case, the debugger breaks execution when the invalid breakpoint is hit.</span></span>  
  
#### <a name="to-specify-a-condition"></a><span data-ttu-id="bc822-111">Per specificare una condizione</span><span class="sxs-lookup"><span data-stu-id="bc822-111">To Specify a Condition</span></span>  
  
1.  <span data-ttu-id="bc822-112">Nella finestra dell'editor fare clic con il pulsante destro del mouse sul glifo del punto di interruzione, quindi scegliere **Condizione** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="bc822-112">In the editor window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="bc822-113">-oppure-</span><span class="sxs-lookup"><span data-stu-id="bc822-113">-or-</span></span>  
  
     <span data-ttu-id="bc822-114">Nella finestra **Punti di interruzione** fare clic con il pulsante destro del mouse sul glifo del punto di interruzione e quindi scegliere **Condizione** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="bc822-114">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="bc822-115">Nella finestra di dialogo **Condizione punto di interruzione** immettere un'espressione booleana valida nella casella **Condizione** .</span><span class="sxs-lookup"><span data-stu-id="bc822-115">In the **Breakpoint Condition** dialog box, enter a valid Boolean expression in the **Condition** box.</span></span>  
  
3.  <span data-ttu-id="bc822-116">Scegliere **è true** se si desidera interrompere l'intervallo quando l'espressione restituisce `true` oppure scegliere **è stato modificato** se si desidera interrompere l'intervallo quando viene modificato il valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="bc822-116">Choose **Is true** if you want to break when the expression evaluates to `true`, or choose **Has changed** if you want to break when the value of the expression has changed.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc822-117">Il debugger non valuta l'espressione booleana fino a quando il primo il punto di interruzione non viene raggiunto.</span><span class="sxs-lookup"><span data-stu-id="bc822-117">The debugger does not evaluate the Boolean expression until the first time the breakpoint is reached.</span></span> <span data-ttu-id="bc822-118">Se si sceglie **È stato modificato**, il debugger non considera la prima valutazione una modifica e quindi non interrompe l'esecuzione in corrispondenza della prima valutazione.</span><span class="sxs-lookup"><span data-stu-id="bc822-118">If you choose **Has changed**, the debugger does not consider the first evaluation to be a change, so the debugger will not break on the first evaluation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc822-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc822-119">See Also</span></span>  
 <span data-ttu-id="bc822-120">[Specificare un numero di passaggi](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="bc822-120">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="bc822-121">Specificare un'azione del punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="bc822-121">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
