---
title: Costanti nelle espressioni (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b8ae650b-0f46-4848-b62b-15f8a40751b8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d95005a04482cb03d3bb3860aea695c7e7969255
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627151"
---
# <a name="constants-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="28e1e-102">Costanti nelle espressioni (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="28e1e-102">Constants in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="28e1e-103">Una costante è costituita da testo letterale o da testo predefinito.</span><span class="sxs-lookup"><span data-stu-id="28e1e-103">A constant consists of literal text or predefined text.</span></span> <span data-ttu-id="28e1e-104">Il componente di elaborazione del report ha accesso alle costanti predefinite in modo che quando queste vengono incluse in un'espressione, i valori che rappresentano vengono sostituiti prima di essere valutati.</span><span class="sxs-lookup"><span data-stu-id="28e1e-104">The report processor has access to predefined constants so that when you include them in an expression, the values they represent are substituted in the expression before it is evaluated.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="literal-text"></a><span data-ttu-id="28e1e-105">Testo letterale</span><span class="sxs-lookup"><span data-stu-id="28e1e-105">Literal Text</span></span>  
 <span data-ttu-id="28e1e-106">In un'espressione il testo letterale corrisponde a testo racchiuso tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="28e1e-106">In an expression, literal text is text that is in double quotation marks.</span></span> <span data-ttu-id="28e1e-107">È anche possibile digitare il testo direttamente in una casella di testo senza virgolette doppie, se non fa parte di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="28e1e-107">You can also type text directly into a text box without double quotation marks if it is not part of an expression.</span></span> <span data-ttu-id="28e1e-108">Se il valore della casella di testo non inizia con un segno di uguale (=), il testo viene trattato come testo letterale.</span><span class="sxs-lookup"><span data-stu-id="28e1e-108">If the text box value does not begin with an equal sign (=), the text is treated as literal text.</span></span> <span data-ttu-id="28e1e-109">Nella tabella seguente sono illustrati diversi esempi di testo letterale in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="28e1e-109">The following table shows several examples of literal text in an expression.</span></span>  
  
|<span data-ttu-id="28e1e-110">Costante</span><span class="sxs-lookup"><span data-stu-id="28e1e-110">Constant</span></span>|<span data-ttu-id="28e1e-111">Testo visualizzato</span><span class="sxs-lookup"><span data-stu-id="28e1e-111">Display text</span></span>|<span data-ttu-id="28e1e-112">Testo dell'espressione</span><span class="sxs-lookup"><span data-stu-id="28e1e-112">Expression text</span></span>|  
|--------------|------------------|---------------------|  
|<span data-ttu-id="28e1e-113">Report eseguito alle:</span><span class="sxs-lookup"><span data-stu-id="28e1e-113">Report run at:</span></span>|<\<Expr>>|`="Report run at: " & Globals!ExecutionTime`|  
|<span data-ttu-id="28e1e-114">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="28e1e-114">Adventure Works Cycles</span></span>|<span data-ttu-id="28e1e-115">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="28e1e-115">Adventure Works Cycles</span></span>|<span data-ttu-id="28e1e-116">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="28e1e-116">Adventure Works Cycles</span></span>|  
|<span data-ttu-id="28e1e-117">[Testo visualizzato tra parentesi quadre]</span><span class="sxs-lookup"><span data-stu-id="28e1e-117">[Bracketed display text]</span></span>|<span data-ttu-id="28e1e-118">\\[Testo visualizzato tra parentesi quadre\\]</span><span class="sxs-lookup"><span data-stu-id="28e1e-118">\\[Bracketed display text\\]</span></span>|<span data-ttu-id="28e1e-119">[Testo visualizzato tra parentesi quadre]</span><span class="sxs-lookup"><span data-stu-id="28e1e-119">[Bracketed display text]</span></span>|  
  
## <a name="rdl-constants"></a><span data-ttu-id="28e1e-120">Costanti RDL</span><span class="sxs-lookup"><span data-stu-id="28e1e-120">RDL Constants</span></span>  
 <span data-ttu-id="28e1e-121">È possibile utilizzare le costanti definite in Report Definition Language (RDL) in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="28e1e-121">You can use constants defined in Report Definition Language (RDL) in an expression.</span></span> <span data-ttu-id="28e1e-122">Nella finestra di dialogo **Espressione** le costanti vengono visualizzate quando si crea un'espressione per una proprietà del report che accetta solo determinati valori validi, noti anche come tipi enumerati.</span><span class="sxs-lookup"><span data-stu-id="28e1e-122">In the **Expression** dialog box, constants appear when you create an expression for a report property that only accepts certain valid values, also known as enumerated types.</span></span> <span data-ttu-id="28e1e-123">Nella tabella seguente sono illustrati due esempi.</span><span class="sxs-lookup"><span data-stu-id="28e1e-123">The following table shows two examples.</span></span>  
  
|<span data-ttu-id="28e1e-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="28e1e-124">Property</span></span>|<span data-ttu-id="28e1e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28e1e-125">Description</span></span>|<span data-ttu-id="28e1e-126">Valori</span><span class="sxs-lookup"><span data-stu-id="28e1e-126">Values</span></span>|  
|--------------|-----------------|------------|  
|<span data-ttu-id="28e1e-127">TextAlign</span><span class="sxs-lookup"><span data-stu-id="28e1e-127">TextAlign</span></span>|<span data-ttu-id="28e1e-128">Valori validi per l'allineamento del testo in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="28e1e-128">Valid values for aligning text in a text box.</span></span>|<span data-ttu-id="28e1e-129">Standard, A sinistra, Al centro, A destra</span><span class="sxs-lookup"><span data-stu-id="28e1e-129">General, Left, Center, Right</span></span>|  
|<span data-ttu-id="28e1e-130">BorderStyle</span><span class="sxs-lookup"><span data-stu-id="28e1e-130">BorderStyle</span></span>|<span data-ttu-id="28e1e-131">Valori validi per una linea aggiunta a un report.</span><span class="sxs-lookup"><span data-stu-id="28e1e-131">Valid values for a line added to a report.</span></span>|<span data-ttu-id="28e1e-132">Predefinito, Nessuno, Punteggiato, Tratteggiato, Continuo, Doppio, TrattoPunto, TrattoPuntoPunto</span><span class="sxs-lookup"><span data-stu-id="28e1e-132">Default, None, Dotted, Dashed, Solid, Double, DashDot, DashDotdot</span></span>|  
  
## <a name="visual-basic-constants"></a><span data-ttu-id="28e1e-133">Costanti di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="28e1e-133">Visual Basic Constants</span></span>  
 <span data-ttu-id="28e1e-134">In un'espressione è possibile usare costanti definite nella libreria run-time di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28e1e-134">You can use constants defined in the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library in an expression.</span></span> <span data-ttu-id="28e1e-135">È possibile, ad esempio, utilizzare la costante `DateInterval.Day`.</span><span class="sxs-lookup"><span data-stu-id="28e1e-135">For example, you can use the constant `DateInterval.Day`.</span></span> <span data-ttu-id="28e1e-136">L'espressione seguente per la data 10 gennaio 2008 restituisce il numero 10:</span><span class="sxs-lookup"><span data-stu-id="28e1e-136">The following expression for the date January 10, 2008 returns the number 10:</span></span>  
  
 `=DatePart("d",Globals!ExecutionTime)`  
  
## <a name="clr-constants"></a><span data-ttu-id="28e1e-137">Costanti CLR</span><span class="sxs-lookup"><span data-stu-id="28e1e-137">CLR Constants</span></span>  
 <span data-ttu-id="28e1e-138">È possibile utilizzare le costanti definite nelle classi CLR (Common Language Run-time) di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="28e1e-138">You can use constants defined in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language run-time (CLR) classes in an expression.</span></span> <span data-ttu-id="28e1e-139">Nella tabella seguente è illustrato un esempio di un colore definito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="28e1e-139">The following table shows an example of a system-defined color.</span></span>  
  
|<span data-ttu-id="28e1e-140">Costante</span><span class="sxs-lookup"><span data-stu-id="28e1e-140">Constant</span></span>|<span data-ttu-id="28e1e-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28e1e-141">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="28e1e-142">MistyRose</span><span class="sxs-lookup"><span data-stu-id="28e1e-142">MistyRose</span></span>|<span data-ttu-id="28e1e-143">Quando si crea un'espressione per una proprietà del report basata su un colore di sfondo, è possibile specificare un colore per nome.</span><span class="sxs-lookup"><span data-stu-id="28e1e-143">When you create an expression for a report property that is based on background color, you can specify a color by name.</span></span> <span data-ttu-id="28e1e-144">I nomi validi sono elencati nella finestra di dialogo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="28e1e-144">Valid names are listed in the **Expression** dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28e1e-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28e1e-145">See Also</span></span>  
 <span data-ttu-id="28e1e-146">[Finestra di dialogo espressione](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="28e1e-146">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="28e1e-147">[Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28e1e-147">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="28e1e-148">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28e1e-148">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="28e1e-149">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28e1e-149">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="28e1e-150">Finestra di dialogo dell'espressione &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="28e1e-150">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
