---
title: Definire i colori in un grafico mediante la tavolozza (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d95efc22-5a32-43d4-9bd2-12753e7fd395
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7db137ed87b0c84e43577dcf2936a6287abd8e36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628448"
---
# <a name="define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs"></a><span data-ttu-id="556c9-102">Definire i colori in un grafico mediante la tavolozza (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="556c9-102">Define Colors on a Chart Using a Palette (Report Builder and SSRS)</span></span>
  <span data-ttu-id="556c9-103">È possibile modificare la tavolozza colori per un grafico selezionando una tavolozza predefinita o definendo una tavolozza personalizzata.</span><span class="sxs-lookup"><span data-stu-id="556c9-103">You can change the color palette for a chart by selecting a pre-defined palette or defining a custom palette.</span></span> <span data-ttu-id="556c9-104">Le tavolozze personalizzate sono specifiche dei report.</span><span class="sxs-lookup"><span data-stu-id="556c9-104">Custom palettes are report-specific.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-colors-on-the-chart-using-a-built-in-color-palette"></a><span data-ttu-id="556c9-105">Per modificare i colori nel grafico utilizzando una tavolozza colori predefinita</span><span class="sxs-lookup"><span data-stu-id="556c9-105">To change the colors on the chart using a built-in color palette</span></span>  
  
1.  <span data-ttu-id="556c9-106">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="556c9-106">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="556c9-107">Nell'area di progettazione fare clic sul grafico.</span><span class="sxs-lookup"><span data-stu-id="556c9-107">On the design surface, click the chart.</span></span> <span data-ttu-id="556c9-108">Le proprietà dell'oggetto grafico verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="556c9-108">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
     <span data-ttu-id="556c9-109">Il nome dell'oggetto (**Chart1** per impostazione predefinita) viene visualizzato nell'elenco a discesa nella parte superiore del riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="556c9-109">The object name (**Chart1** by default) appears in the drop-down list at the top of the Properties pane.</span></span>  
  
3.  <span data-ttu-id="556c9-110">Nella sezione **Grafico** selezionare nell'elenco a discesa una nuova tavolozza per la proprietà Palette.</span><span class="sxs-lookup"><span data-stu-id="556c9-110">In the **Chart** section, for the Palette property, select a new palette from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="556c9-111">Una tavolozza predefinita non consente di modificare o di ordinare i colori.</span><span class="sxs-lookup"><span data-stu-id="556c9-111">You cannot change the colors or order in a pre-defined palette.</span></span>  
  
### <a name="to-define-your-own-colors-on-the-chart-using-a-custom-color-palette"></a><span data-ttu-id="556c9-112">Per definire colori personalizzati nel grafico utilizzando una tavolozza colori personalizzata</span><span class="sxs-lookup"><span data-stu-id="556c9-112">To define your own colors on the chart using a custom color palette</span></span>  
  
1.  <span data-ttu-id="556c9-113">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="556c9-113">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="556c9-114">Nell'area di progettazione fare clic sul grafico.</span><span class="sxs-lookup"><span data-stu-id="556c9-114">On the design surface, click the chart.</span></span> <span data-ttu-id="556c9-115">Le proprietà dell'oggetto grafico verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="556c9-115">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="556c9-116">Nella sezione **grafico** `Palette` selezionare **personalizzata**per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="556c9-116">In the **Chart** section, for the `Palette` property, select **Custom**.</span></span>  
  
4.  <span data-ttu-id="556c9-117">Nella proprietà CustomPaletteColors fare clic sul pulsante di modifica della raccolta ( **…** ).</span><span class="sxs-lookup"><span data-stu-id="556c9-117">In the CustomPaletteColors property, click the Edit Collection (**...**) button.</span></span> <span data-ttu-id="556c9-118">Verrà visualizzata la finestra di dialogo **Editor raccolte ReportColorExpression** .</span><span class="sxs-lookup"><span data-stu-id="556c9-118">The **ReportColorExpression Collection Editor** opens.</span></span>  
  
5.  <span data-ttu-id="556c9-119">Fare clic su **Aggiungi** per aggiungere un colore.</span><span class="sxs-lookup"><span data-stu-id="556c9-119">Click **Add** to add a color.</span></span> <span data-ttu-id="556c9-120">Selezionare un colore dall'elenco a discesa oppure selezionare Espressione e specificare un valore esadecimale per un colore specifico, ad esempio ff6600 per l'arancione.</span><span class="sxs-lookup"><span data-stu-id="556c9-120">Select a color from the drop-down list or select Expression and specify a hex value for a specific color, such as ff6600 for "Orange".</span></span>  
  
     <span data-ttu-id="556c9-121">Per ulteriori informazioni sui valori esadecimali, vedere la [tabella dei colori](https://go.microsoft.com/fwlink/?linkid=9258) su MSDN.</span><span class="sxs-lookup"><span data-stu-id="556c9-121">For more information about hex values, see [Color Table](https://go.microsoft.com/fwlink/?linkid=9258) on MSDN.</span></span>  
  
6.  <span data-ttu-id="556c9-122">Fare clic su **Aggiungi** per aggiungere altri colori alla tavolozza.</span><span class="sxs-lookup"><span data-stu-id="556c9-122">Click **Add** to add more colors to the palette.</span></span>  
  
7.  <span data-ttu-id="556c9-123">Al termine dell'operazione scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="556c9-123">When you are done, click **OK**.</span></span>  
  
 <span data-ttu-id="556c9-124">Se si utilizza una tavolozza personalizzata, è possibile modificare l'ordine dei colori per modificare il colore di diverse serie nel grafico.</span><span class="sxs-lookup"><span data-stu-id="556c9-124">If you are using a custom palette, you can change the order of the colors to change the color of different series in the chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="556c9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="556c9-125">See Also</span></span>  
 <span data-ttu-id="556c9-126">[Formattazione dei colori delle serie in un grafico &#40;Generatore report e SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="556c9-126">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="556c9-127">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="556c9-127">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="556c9-128">Specificare i colori coerenti in più grafici con forme &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="556c9-128">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
