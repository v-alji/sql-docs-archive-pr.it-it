---
title: Modificare il testo di un elemento legenda (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9e82fa34-17ed-494f-b25d-03dcc353a21f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d0bb721aa0ff03a5211065111c98605cd86e971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636576"
---
# <a name="change-the-text-of-a-legend-item-report-builder-and-ssrs"></a><span data-ttu-id="29e94-102">Modificare il testo di un elemento legenda (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="29e94-102">Change the Text of a Legend Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="29e94-103">Quando un campo viene posizionato nell'area Valori del grafico, viene generato automaticamente un elemento della legenda contenente il nome di tale campo.</span><span class="sxs-lookup"><span data-stu-id="29e94-103">When a field is placed in the Values area of the chart, a legend item is automatically generated that contains the name of this field.</span></span> <span data-ttu-id="29e94-104">Ogni elemento della legenda è collegato a una singola serie nel grafico, ad eccezione dei grafici con forme in cui la legenda è collegata a singoli punti dati anziché a singole serie.</span><span class="sxs-lookup"><span data-stu-id="29e94-104">Every legend item is connected to an individual series on the chart, with the exception of shape charts, where the legend is connected to individual data points instead of individual series.</span></span>  
  
 <span data-ttu-id="29e94-105">Nei grafici con forme è possibile modificare il testo di un elemento della legenda in modo da visualizzare ulteriori informazioni sui singoli punti dati.</span><span class="sxs-lookup"><span data-stu-id="29e94-105">On shape charts, you can change the text of a legend item to show more information about the individual data points.</span></span> <span data-ttu-id="29e94-106">Se, ad esempio, si desidera visualizzare i valori dei punti dati come percentuali nella legenda, è possibile utilizzare una parola chiave quale `#PERCENT`.</span><span class="sxs-lookup"><span data-stu-id="29e94-106">For example, if you want to show the values of the data points as percentages in the legend, you can use a keyword such as `#PERCENT`.</span></span> <span data-ttu-id="29e94-107">Per applicare formati numerici e di data, è possibile aggiungere codici di formato .NET Framework con determinate parole chiave.</span><span class="sxs-lookup"><span data-stu-id="29e94-107">You can append .NET Framework format codes in conjunction with keywords to apply numeric and date formats.</span></span> <span data-ttu-id="29e94-108">Per altre informazioni sulle parole chiave, vedere [Formattazione dei punti dati di un grafico &#40;Generatore report e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="29e94-108">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="29e94-109">![Grafico ottimizzato](../media/sharpchart.png "Grafico ottimizzato")</span><span class="sxs-lookup"><span data-stu-id="29e94-109">![Sharp Chart](../media/sharpchart.png "Sharp Chart")</span></span>  
  
 <span data-ttu-id="29e94-110">Nei grafici senza forme è possibile modificare il testo di un elemento della legenda.</span><span class="sxs-lookup"><span data-stu-id="29e94-110">On non-shape charts, you can change the text of a legend item.</span></span> <span data-ttu-id="29e94-111">Se, ad esempio, il nome della serie è "Serie 1", è possibile modificare il testo per renderlo più descrittivo, ad esempio "Vendite anno 2008".</span><span class="sxs-lookup"><span data-stu-id="29e94-111">For example, if your series name is "Series1", you may want to change the text to something more descriptive like "Sales for 2008".</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-shape-chart"></a><span data-ttu-id="29e94-112">Per modificare il testo visualizzato nella legenda in un grafico con forme</span><span class="sxs-lookup"><span data-stu-id="29e94-112">To modify the text that appears in the legend on a Shape chart</span></span>  
  
1.  <span data-ttu-id="29e94-113">Fare clic con il pulsante destro del mouse su una serie o su un campo contenuto nell'area **Valori** e quindi selezionare **Proprietà serie**.</span><span class="sxs-lookup"><span data-stu-id="29e94-113">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="29e94-114">Fare clic su **Legenda** e digitare una parola chiave nella casella **Testo legenda personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="29e94-114">Click **Legend** and in the **Custom legend text** box, type a keyword.</span></span>  
  
 <span data-ttu-id="29e94-115">La tabella seguente include esempi di parole chiave specifiche del grafico da usare per la proprietà **Testo legenda personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="29e94-115">The following table provides examples of chart-specific keywords to use for the **Custom Legend Text** property.</span></span> <span data-ttu-id="29e94-116">Per altre informazioni sulle parole chiave, vedere [Formattazione dei punti dati di un grafico &#40;Generatore report e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="29e94-116">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
|<span data-ttu-id="29e94-117">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="29e94-117">Keyword</span></span>|<span data-ttu-id="29e94-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29e94-118">Description</span></span>|<span data-ttu-id="29e94-119">Esempio di testo visualizzato nella legenda</span><span class="sxs-lookup"><span data-stu-id="29e94-119">Example of what appears as text in the legend</span></span>|  
|-------------|-----------------|---------------------------------------------------|  
|`#PERCENT{P1}`|<span data-ttu-id="29e94-120">Visualizza la percentuale del valore totale con una posizione decimale.</span><span class="sxs-lookup"><span data-stu-id="29e94-120">Displays the percentage of the total value to one decimal place.</span></span>|<span data-ttu-id="29e94-121">85.0%</span><span class="sxs-lookup"><span data-stu-id="29e94-121">85.0%</span></span>|  
|`#VALY`|<span data-ttu-id="29e94-122">Visualizza il valore numerico effettivo del campo dati.</span><span class="sxs-lookup"><span data-stu-id="29e94-122">Displays the actual numeric value of the data field.</span></span>|<span data-ttu-id="29e94-123">17000</span><span class="sxs-lookup"><span data-stu-id="29e94-123">17000</span></span>|  
|`#VALY{C2}`|<span data-ttu-id="29e94-124">Visualizza il valore numerico effettivo del campo dati come valuta con due posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="29e94-124">Displays the actual numeric value of the data field as a currency to two decimal places.</span></span>|<span data-ttu-id="29e94-125">$17000.00</span><span class="sxs-lookup"><span data-stu-id="29e94-125">$17000.00</span></span>|  
|`#AXISLABEL (#PERCENT{P0})`|<span data-ttu-id="29e94-126">Visualizza la rappresentazione testuale del campo categoria, seguita dalla percentuale visualizzata da ogni categoria nel grafico.</span><span class="sxs-lookup"><span data-stu-id="29e94-126">Displays the text representation of the category field, followed by the percentage that each category displays on the chart.</span></span>|<span data-ttu-id="29e94-127">Michael Blythe (85%)</span><span class="sxs-lookup"><span data-stu-id="29e94-127">Michael Blythe (85%)</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="29e94-128">La parola chiave #AXISLABEL può essere valutata solo in fase di esecuzione quando non è specificato alcun campo nell'area **Gruppi di serie** .</span><span class="sxs-lookup"><span data-stu-id="29e94-128">The #AXISLABEL keyword can only be evaluated at run time when there is not a field specified in the **Series Groups** area.</span></span>  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-non-shape-chart"></a><span data-ttu-id="29e94-129">Per modificare il testo visualizzato nella legenda in un grafico senza forme</span><span class="sxs-lookup"><span data-stu-id="29e94-129">To modify the text that appears in the legend on a non-Shape chart</span></span>  
  
1.  <span data-ttu-id="29e94-130">Fare clic con il pulsante destro del mouse su una serie o su un campo contenuto nell'area **Valori** e quindi selezionare **Proprietà serie**.</span><span class="sxs-lookup"><span data-stu-id="29e94-130">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="29e94-131">Fare clic su **Legenda** e digitare un'etichetta di legenda nella casella **Testo legenda personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="29e94-131">Click **Legend** and in the **Custom legend text** box, type a legend label.</span></span> <span data-ttu-id="29e94-132">La serie verrà aggiornata con il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="29e94-132">The series is updated with your text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e94-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29e94-133">See Also</span></span>  
 <span data-ttu-id="29e94-134">[Formattazione della legenda in un grafico &#40;Generatore report e SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="29e94-134">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="29e94-135">[Formattazione dei colori delle serie in un grafico &#40;Generatore report e SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="29e94-135">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="29e94-136">Nascondere elementi legenda nel grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="29e94-136">Hide Legend Items on the Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-hide-items-report-builder.md)  
  
  
