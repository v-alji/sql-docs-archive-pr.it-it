---
title: Aggiungere una cornice del bordo a un grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ca0c5040-40bb-4cb7-bc2b-5bcbe73858bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c91d3de00caa4eab6ed1894042b2214b7dcf4b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723487"
---
# <a name="add-a-border-frame-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="591a6-102">Aggiungere un bordo o un frame a un grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="591a6-102">Add a Border Frame to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="591a6-103">Per aumentare l'impatto visivo di un grafico è possibile utilizzare un bordo/frame intorno alla parte esterna del grafico.</span><span class="sxs-lookup"><span data-stu-id="591a6-103">To give a chart more visual impact, consider using a border frame around the outside of the chart.</span></span> <span data-ttu-id="591a6-104">È possibile selezionare un bordo o un frame utilizzando la finestra di dialogo **Proprietà grafico** o il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="591a6-104">You can select a border frame by using the **Chart Properties** dialog box or by using the Properties pane.</span></span> <span data-ttu-id="591a6-105">Non è possibile applicare i bordi del grafico ad altre aree dati.</span><span class="sxs-lookup"><span data-stu-id="591a6-105">The chart border frames cannot be applied to any other data region.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-a-border-to-a-chart"></a><span data-ttu-id="591a6-106">Per applicare un bordo a un grafico</span><span class="sxs-lookup"><span data-stu-id="591a6-106">To apply a border to a chart</span></span>  
  
1.  <span data-ttu-id="591a6-107">Fare clic con il pulsante destro del mouse in un punto qualsiasi del grafico e scegliere **Proprietà grafico**.</span><span class="sxs-lookup"><span data-stu-id="591a6-107">Right-click anywhere on the chart and select **Chart Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="591a6-108">Se l'opzione **Proprietà grafico**non è visualizzata, scegliere **Grafico** nel menu di scelta rapida e selezionare **Proprietà grafico**.</span><span class="sxs-lookup"><span data-stu-id="591a6-108">If you do not see the **Chart Properties**, point to **Chart** on the shortcut menu and select **Chart Properties**.</span></span>  
  
2.  <span data-ttu-id="591a6-109">Selezionare **Bordo**e fare clic sul tipo di bordo da applicare al grafico.</span><span class="sxs-lookup"><span data-stu-id="591a6-109">Select **Border**, and click the type of border to apply to the chart.</span></span>  
  
3.  <span data-ttu-id="591a6-110">(Facoltativo) Selezionare un valore o digitare un'espressione che rappresenta lo stile del bordo.</span><span class="sxs-lookup"><span data-stu-id="591a6-110">(Optional) Select a value or type an expression that represents the style of the border.</span></span>  
  
4.  <span data-ttu-id="591a6-111">(Facoltativo) Specificare il colore della linea che verrà disegnata come bordo intorno al grafico.</span><span class="sxs-lookup"><span data-stu-id="591a6-111">(Optional) Specify the color of the line that will be drawn around the chart as the border.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="591a6-112">Nell'elenco **Colore linea** sono disponibili i colore più comuni.</span><span class="sxs-lookup"><span data-stu-id="591a6-112">The **Line color** list contains common colors.</span></span> <span data-ttu-id="591a6-113">Per disporre di una scelta di colori più vasta, fare clic sull'opzione **Altri colori** nell'elenco o fare clic sul pulsante Espressione (**fx**) accanto all'elenco per visualizzare l'editor **espressioni** .</span><span class="sxs-lookup"><span data-stu-id="591a6-113">If you want to select from a list of more colors, click **More colors** in the list or click the expression (**fx**) button next to the list to bring up the **Expression** editor.</span></span>  
  
5.  <span data-ttu-id="591a6-114">(Facoltativo) Specificare lo spessore del bordo.</span><span class="sxs-lookup"><span data-stu-id="591a6-114">(Optional) Specify the width of the border.</span></span> <span data-ttu-id="591a6-115">Sono validi i valori compresi tra 0,25 e 20 punti.</span><span class="sxs-lookup"><span data-stu-id="591a6-115">Valid values are between 0.25pt and 20pt.</span></span> <span data-ttu-id="591a6-116">Per un effetto visivo ottimale, specificare uno spessore del bordo tra 1 e 3 punti.</span><span class="sxs-lookup"><span data-stu-id="591a6-116">Consider keeping the size of your border to between 1 and 3pt for the best visual effect.</span></span>  
  
6.  <span data-ttu-id="591a6-117">(Facoltativo) Se il report contiene un colore di sfondo diverso dal bianco, è preferibile definire lo stesso colore per la pagina.</span><span class="sxs-lookup"><span data-stu-id="591a6-117">(Optional) If your report contains a background color other than white, consider defining a page color that is the same color.</span></span> <span data-ttu-id="591a6-118">Il colore della pagina è il colore di sfondo esterno al bordo.</span><span class="sxs-lookup"><span data-stu-id="591a6-118">The page color is the background color outside of the border line.</span></span>  
  
7.  <span data-ttu-id="591a6-119">(Facoltativo) Se si sceglie un tipo di frame, specificare lo stile e il colore per il frame.</span><span class="sxs-lookup"><span data-stu-id="591a6-119">(Optional) If you choose a Frame type, specify a style and color for the frame.</span></span> <span data-ttu-id="591a6-120">Nell'elenco **Colore riempimento frame** sono disponibili i colori più comuni.</span><span class="sxs-lookup"><span data-stu-id="591a6-120">The **Frame fill color** list contains common colors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="591a6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="591a6-121">See Also</span></span>  
 <span data-ttu-id="591a6-122">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="591a6-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="591a6-123">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="591a6-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="591a6-124">Aggiungere stili smussato, rilievo e trama a un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="591a6-124">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
