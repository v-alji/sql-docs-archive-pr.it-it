---
title: Aggiungere un'espressione (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a60ee091-b4ed-41e1-9b6a-032c316cd03f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 16f414bfad47ae92681de50eb576a6ac2cb3f5fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712735"
---
# <a name="add-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="03c02-102">Aggiungere un'espressione (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="03c02-102">Add an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="03c02-103">Le espressioni vengono usate in un report per definire proprietà, filtri, gruppi, criteri di ordinamento, stringhe di connessione e valori di parametri degli elementi del report.</span><span class="sxs-lookup"><span data-stu-id="03c02-103">Expressions are used throughout a report for defining report item properties, filters, groups, sort order, connection strings, and parameter values.</span></span> <span data-ttu-id="03c02-104">Le espressioni iniziano con il segno di uguale (=) e sono scritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03c02-104">Expressions begin with an equal sign (=) and are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="03c02-105">Vengono valutate in fase di esecuzione dal componente Elaborazione report che combina i risultati della valutazione e gli elementi di layout del report.</span><span class="sxs-lookup"><span data-stu-id="03c02-105">They are evaluated at run time by the report processor, which combines the evaluation result with report layout elements.</span></span>  
  
 <span data-ttu-id="03c02-106">Le espressioni possono essere semplici o complesse.</span><span class="sxs-lookup"><span data-stu-id="03c02-106">Expressions can be simple or complex.</span></span> <span data-ttu-id="03c02-107">Le espressioni semplici fanno riferimento a un solo elemento in una raccolta predefinita.</span><span class="sxs-lookup"><span data-stu-id="03c02-107">Simple expression refer to a single item in a built-in collection.</span></span> <span data-ttu-id="03c02-108">Le espressioni complesse possono contenere costanti, operatori, elementi di raccolta globali e chiamate di funzioni.</span><span class="sxs-lookup"><span data-stu-id="03c02-108">Complex expressions can contain constants, operators, global collection items, and function calls.</span></span> <span data-ttu-id="03c02-109">Per altre informazioni, vedere [Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="03c02-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-expression-to-a-text-box"></a><span data-ttu-id="03c02-110">Per aggiungere un'espressione a una casella di testo</span><span class="sxs-lookup"><span data-stu-id="03c02-110">To add an expression to a text box</span></span>  
  
-   <span data-ttu-id="03c02-111">In visualizzazione **Progettazione** fare clic sulla casella di testo nell'area di progettazione in cui si desidera aggiungere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="03c02-111">In **Design** view, click the text box on the design surface to which you want to add an expression.</span></span>  
  
    -   <span data-ttu-id="03c02-112">In caso di un'espressione semplice, digitare il testo visualizzato per l'espressione nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="03c02-112">For a simple expression, type the display text for the expression in the text box.</span></span> <span data-ttu-id="03c02-113">Per il campo del set di dati Sales, ad esempio, digitare `[Sales]`.</span><span class="sxs-lookup"><span data-stu-id="03c02-113">For example, for the dataset field Sales, type `[Sales]`.</span></span>  
  
    -   <span data-ttu-id="03c02-114">In caso di un'espressione complessa, fare clic con il pulsante destro del mouse sulla casella di testo e selezionare **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="03c02-114">For a complex expression, right-click the text box, and select **Expression**.</span></span> <span data-ttu-id="03c02-115">Verrà visualizzata la finestra di dialogo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="03c02-115">The **Expression** dialog box opens.</span></span> <span data-ttu-id="03c02-116">Digitare o creare in modo interattivo l'espressione dopo il segno '=' nel riquadro dell'espressione, quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="03c02-116">Type or interactively create your expression after the '=' in the expression pane, and then click OK.</span></span>  
  
         <span data-ttu-id="03c02-117">L'espressione verrà visualizzata nell'area di progettazione come `<<Expr>>`.</span><span class="sxs-lookup"><span data-stu-id="03c02-117">The expression appears on the design surface as `<<Expr>>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03c02-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03c02-118">See Also</span></span>  
 <span data-ttu-id="03c02-119">[Formattazione di testo e segnaposto &#40;Generatore report e SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03c02-119">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="03c02-120">[Caselle di testo &#40;Generatore report e SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03c02-120">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="03c02-121">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03c02-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="03c02-122">[Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03c02-122">[Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="03c02-123">[Esempi di espressioni di raggruppamento &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03c02-123">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="03c02-124">[Finestra di dialogo Espressione &#40;Generatore report&#41;](../expression-dialog-box-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="03c02-124">[Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md) </span></span>  
 <span data-ttu-id="03c02-125">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03c02-125">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="03c02-126">Aggiungere codice a un report &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="03c02-126">Add Code to a Report &#40;SSRS&#41;</span></span>](add-code-to-a-report-ssrs.md)  
  
  
