---
title: Specificare le dimensioni di un indicatore tramite un'espressione (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab0b86f1-4882-4258-a2b6-c612faecfa4b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b450abb957329b8dbaa4f7f0e4c963c5f63f06b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623768"
---
# <a name="specify-the-size-of-an-indicator-using-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="e0e17-102">Specificare le dimensioni di un indicatore tramite un'espressione (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e0e17-102">Specify the Size of an Indicator Using an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e0e17-103">Per migliorare l'impatto visivo degli indicatori, oltre al colore, alla direzione e alla forma è possibile usare anche le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e0e17-103">In addition to color, direction, and shape, you can use size to maximize the visual impact of indicators.</span></span>  
  
 <span data-ttu-id="e0e17-104">Un indicatore dispone di una raccolta di stati dell'indicatore denominata IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="e0e17-104">An indicator has a collection of indicator states named IndicatorStates.</span></span> <span data-ttu-id="e0e17-105">La raccolta IndicatorStates dispone in genere di più stati.</span><span class="sxs-lookup"><span data-stu-id="e0e17-105">The IndicatorStates collection typically have multiple states.</span></span> <span data-ttu-id="e0e17-106">Ogni stato è un membro della raccolta e viene rappresentato da un'icona.</span><span class="sxs-lookup"><span data-stu-id="e0e17-106">Each state is a member of the collection and is represented by an icon.</span></span> <span data-ttu-id="e0e17-107">Gli stati, insieme, formano la raccolta IndicatorsStates.</span><span class="sxs-lookup"><span data-stu-id="e0e17-107">Together the states constitute the IndicatorsStates collection.</span></span>  
  
 <span data-ttu-id="e0e17-108">Per configurare dinamicamente le dimensioni delle icone, è possibile impostare le proprietà dei membri della raccolta IndicatorsStates nel riquadro Proprietà di Generatore report.</span><span class="sxs-lookup"><span data-stu-id="e0e17-108">To dynamically configure the sizes of icons, you set properties of members of the IndicatorsStates collection in the Properties pane of Report Builder.</span></span> <span data-ttu-id="e0e17-109">Se il riquadro **Proprietà** non è visibile, selezionare **Proprietà** nella scheda **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="e0e17-109">If the **Properties** pane is not visible, click the **View** tab and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0e17-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]usare la finestra **Proprietà** per impostare le proprietà dei membri.</span><span class="sxs-lookup"><span data-stu-id="e0e17-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you use the **Properties** window to set the member properties.</span></span> <span data-ttu-id="e0e17-111">Se la finestra **Proprietà** non è aperta, premere il tasto F4.</span><span class="sxs-lookup"><span data-stu-id="e0e17-111">If the **Properties** window is not open, press the F4 key.</span></span>  
  
 <span data-ttu-id="e0e17-112">Il riquadro **Proprietà** consente l'accesso alle proprietà della raccolta IndicatorStates di un indicatore.</span><span class="sxs-lookup"><span data-stu-id="e0e17-112">The **Properties** pane provides access to the properties of the IndicatorStates collection of an indicator.</span></span> <span data-ttu-id="e0e17-113">Le diverse dimensioni delle icone vengono configurate impostando la proprietà ScaleFactor dei membri raccolta IndicatorStates tramite un'espressione.</span><span class="sxs-lookup"><span data-stu-id="e0e17-113">You configure the icons to be different sizes by setting the ScaleFactor property of the IndicatorStates collection members using an expression.</span></span> <span data-ttu-id="e0e17-114">Per altre informazioni, vedere [Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e0e17-114">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="e0e17-115">L'espressione utilizzata in questa procedura è stata usata anche per generare il report con diverse dimensioni di indicatori, mostrato in [Indicatori &#40;Generatore report e SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e0e17-115">The expression used in this procedure was also used to generate the report with different sizes of indicators, shown in [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-the-indicator-icon-size-using-an-expression"></a><span data-ttu-id="e0e17-116">Per specificare le dimensioni dell'icona dell'indicatore tramite un'espressione</span><span class="sxs-lookup"><span data-stu-id="e0e17-116">To specify the indicator icon size using an expression</span></span>  
  
1.  <span data-ttu-id="e0e17-117">Scegliere l'indicatore che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="e0e17-117">Click the indicator you want to change.</span></span>  
  
2.  <span data-ttu-id="e0e17-118">Nel riquadro Proprietà individuare la proprietà IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="e0e17-118">In the Properties pane, locate the IndicatorStates property.</span></span>  
  
     <span data-ttu-id="e0e17-119">Se il riquadro Proprietà è organizzato per categorie, IndicatorStates si trova nella categoria **Stati** .</span><span class="sxs-lookup"><span data-stu-id="e0e17-119">If the Properties pane is organized by category, you will find IndicatorStates in the **States** category.</span></span>  
  
3.  <span data-ttu-id="e0e17-120">Fare clic sul pulsante con i puntini di sospensione **(...)** accanto a IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="e0e17-120">Click the ellipsis **(...)** button next to IndicatorStates.</span></span> <span data-ttu-id="e0e17-121">Verrà visualizzata la finestra di dialogo **Editor raccolte IndicatorState** .</span><span class="sxs-lookup"><span data-stu-id="e0e17-121">The **IndicatorState Collection Editor** dialog box opens.</span></span>  
  
     <span data-ttu-id="e0e17-122">Selezionare tutti i membri della raccolta.</span><span class="sxs-lookup"><span data-stu-id="e0e17-122">Select all members of the collection.</span></span>  
  
4.  <span data-ttu-id="e0e17-123">Nell'elenco **Proprietà a selezione multipla** fare clic sulla freccia in giù accanto a ScaleFactor, quindi su **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="e0e17-123">In the **Multi-Select Properties** list, click the down arrow next to ScaleFactor and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="e0e17-124">Nella finestra di dialogo **Espressione** scrivere l'espressione.</span><span class="sxs-lookup"><span data-stu-id="e0e17-124">In the **Expression** dialog box write the expression.</span></span>  
  
     <span data-ttu-id="e0e17-125">L'espressione di esempio seguente consente di modificare le dimensioni dell'icona in base al valore del campo **SalesYTD** .</span><span class="sxs-lookup"><span data-stu-id="e0e17-125">The following sample expression makes the icon a different size based on the value of the **SalesYTD** field.</span></span>  
  
     `=IIF(Fields!SalesYTD.value = 0,0,Fields!SalesYTD.value/Max(Fields!SalesYTD.value,"Indicator"))`  
  
     <span data-ttu-id="e0e17-126">Per altre informazioni, vedere [Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e0e17-126">For more information, see [Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0e17-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0e17-127">See Also</span></span>  
 [<span data-ttu-id="e0e17-128">Indicatori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e0e17-128">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
