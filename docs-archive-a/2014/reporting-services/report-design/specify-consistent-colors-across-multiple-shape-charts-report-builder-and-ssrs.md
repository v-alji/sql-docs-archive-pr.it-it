---
title: Specificare colori coerenti in più grafici con forme (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d52f68e9-2ba7-4bff-9053-4089e5164ab4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c2c89f0f8cda3b7d6ef6b2acbd0de66c87170357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623773"
---
# <a name="specify-consistent-colors-across-multiple-shape-charts-report-builder-and-ssrs"></a><span data-ttu-id="47114-102">Specificare i colori coerenti in più grafici con forme (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="47114-102">Specify Consistent Colors across Multiple Shape Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="47114-103">Nei grafici diversi dai grafici con forme viene selezionato un nuovo colore dalla tavolozza in base all'indice di serie del grafico.</span><span class="sxs-lookup"><span data-stu-id="47114-103">On non-shape charts, a new color is selected from the palette based on the index of series in the chart.</span></span> <span data-ttu-id="47114-104">Verrà eseguito il mapping delle prime serie sul grafico al primo colore della tavolozza.</span><span class="sxs-lookup"><span data-stu-id="47114-104">For example, the first series on your chart will be mapped to the first color in the palette.</span></span> <span data-ttu-id="47114-105">Questo comportamento non si verifica nei grafici con forme,</span><span class="sxs-lookup"><span data-stu-id="47114-105">However, this behavior differs for shape charts.</span></span> <span data-ttu-id="47114-106">nei quali di ogni colore nella tavolozza viene eseguito il mapping a un punto dati nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="47114-106">On shape charts, each color in the palette is mapped to a data point in the dataset.</span></span> <span data-ttu-id="47114-107">Ad esempio viene eseguito il mapping del punto dati 1 al primo colore nella tavolozza e del punto dati 2 alla seconda tavolozza di colori e così via.</span><span class="sxs-lookup"><span data-stu-id="47114-107">For example, data point 1 is mapped to the first color in the palette, data point 2 is mapped to the second color palette and so on.</span></span>  
  
 <span data-ttu-id="47114-108">Un punto dati che non presenta valori non viene visualizzato in un grafico con forme.</span><span class="sxs-lookup"><span data-stu-id="47114-108">If a data point has no value, it is omitted from display on a shape chart.</span></span> <span data-ttu-id="47114-109">Ciò significa che il punto dati non viene colorato.</span><span class="sxs-lookup"><span data-stu-id="47114-109">This means that the data point is skipped from being colored.</span></span> <span data-ttu-id="47114-110">Se ad esempio il valore del punto 2 è zero, verrà eseguito il mapping del punto 1 al primo colore della tavolozza e verrà eseguito il mapping del punto 3 al secondo colore della tavolozza.</span><span class="sxs-lookup"><span data-stu-id="47114-110">For example, if point 2 has a value of zero, point 1 will be mapped to the first color in the palette, and point 3 will be mapped to the second color in the palette.</span></span> <span data-ttu-id="47114-111">Questo metodo risulta utile nel caso di punti vuoti nel set di dati di un grafico a torta in quanto impedisce che venga utilizzato inutilmente un colore della tavolozza se non è necessario disegnare il punto vuoto.</span><span class="sxs-lookup"><span data-stu-id="47114-111">This approach is useful because the empty points in the dataset of a pie chart do not unnecessarily use a palette color when the empty point does not need to be drawn.</span></span>  
  
 <span data-ttu-id="47114-112">Come effetto collaterale, quando in un report vengono visualizzati più grafici a torta, potrebbero essere visualizzati colori diversi per i punti dati con lo stesso raggruppamento di categoria.</span><span class="sxs-lookup"><span data-stu-id="47114-112">As a side effect, when multiple pie charts are displayed in a report, the pie charts may display different colors for data points that have the same category grouping.</span></span> <span data-ttu-id="47114-113">Per risolvere questo inconveniente, è necessario definire colori singoli su cui viene eseguito il mapping a un gruppo di categorie anziché valori di dati singoli.</span><span class="sxs-lookup"><span data-stu-id="47114-113">To resolve this, you need to define individual colors that map to a category group instead of individual data values.</span></span> <span data-ttu-id="47114-114">La modalità di esecuzione di questa operazione varia a seconda che si tratti di grafici sparkline in una tabella o in una matrice o di grafici con forme nel report stesso.</span><span class="sxs-lookup"><span data-stu-id="47114-114">How you do this depends on if the shape charts are sparklines in a table or matrix, or if they are shape charts in the report itself.</span></span>  
  
 <span data-ttu-id="47114-115">La legenda è collegata alla serie, pertanto qualsiasi colore si specifica per la serie verrà mostrato automaticamente sulla legenda.</span><span class="sxs-lookup"><span data-stu-id="47114-115">The legend is connected to the series, so any color you specify for the series will automatically be shown on the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-consistent-colors-across-multiple-sparkline-shape-charts-in-a-table-or-matrix"></a><span data-ttu-id="47114-116">Per specificare colori coerenti in più grafici con forme di tipo sparkline in una tabella o in una matrice</span><span class="sxs-lookup"><span data-stu-id="47114-116">To specify consistent colors across multiple sparkline shape charts in a table or matrix</span></span>  
  
1.  <span data-ttu-id="47114-117">Fare clic nel grafico per visualizzare il riquadro Dati grafico.</span><span class="sxs-lookup"><span data-stu-id="47114-117">Click the chart to display the Chart Data pane.</span></span>  
  
2.  <span data-ttu-id="47114-118">Nell'area **Gruppi di categorie** fare clic con il pulsante destro del mouse su una categoria e scegliere **Proprietà gruppo categorie**.</span><span class="sxs-lookup"><span data-stu-id="47114-118">In the **Category Groups** area, right-click a category and click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="47114-119">Nella casella **Sincronizza gruppi in** della scheda Generale fare clic sul nome della categoria per la quale si desidera sincronizzare i colori, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="47114-119">On the General tab, in the **Synchronize groups in** box, click the name of the category for which you would like to synchronize colors, and then click **OK**.</span></span>  
  
### <a name="to-specify-consistent-colors-across-multiple-shape-charts"></a><span data-ttu-id="47114-120">Per specificare colori coerenti in più grafici con forme</span><span class="sxs-lookup"><span data-stu-id="47114-120">To specify consistent colors across multiple shape charts</span></span>  
  
1.  <span data-ttu-id="47114-121">Fare clic con il pulsante destro del mouse al di fuori del corpo del report, quindi selezionare **Proprietà report**.</span><span class="sxs-lookup"><span data-stu-id="47114-121">Right-click outside the body of the report, and select **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="47114-122">In **Codice**digitare il codice seguente nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="47114-122">In **Code**, type the following code into the textbox.</span></span>  
  
    ```  
    Private colorPalette As String() = {"Color1", "Color2", "Color3"}  
    Private count As Integer = 0  
    Private mapping As New System.Collections.Hashtable()  
    Public Function GetColor(ByVal groupingValue As String) As String  
        If mapping.ContainsKey(groupingValue) Then  
            Return mapping(groupingValue)  
        End If  
        Dim c As String = colorPalette(count Mod colorPalette.Length)  
        count = count + 1  
        mapping.Add(groupingValue, c)  
        Return c  
    End Function  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="47114-123">Sarà necessario sostituire le stringhe "Color1" con colori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="47114-123">You will need to replace the "Color1" strings with your own colors.</span></span> <span data-ttu-id="47114-124">È possibile utilizzare colori denominati, ad esempio "Rosso" oppure il valore esadecimale a sei cifre che rappresenta il colore, ad esempio "#FFFFFF" che indica il nero.</span><span class="sxs-lookup"><span data-stu-id="47114-124">You can use named colors, for example "Red", or you can use six-digit hexadecimal value that represent the color, such as "#FFFFFF" for black.</span></span> <span data-ttu-id="47114-125">Se sono stati definiti più di tre colori, sarà necessario estendere la matrice di colori in modo che il numero di colori della matrice corrisponda al numero di punti nel grafico con forme.</span><span class="sxs-lookup"><span data-stu-id="47114-125">If you have more than three colors defined, you will need to extend the array of colors so that the number of colors in the array matches the number of points in your shape chart.</span></span> <span data-ttu-id="47114-126">È possibile aggiungere nuovi colori alla matrice specificando un elenco delimitato da virgole di valori stringa che contengono colori denominati o rappresentazioni esadecimali dei colori.</span><span class="sxs-lookup"><span data-stu-id="47114-126">You can add new colors to the array by specifying a comma-separated list of string values that contain named colors or hexadecimal representations of colors.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="47114-127">Fare clic con il pulsante destro del mouse sul grafico con forme e scegliere **Proprietà serie**.</span><span class="sxs-lookup"><span data-stu-id="47114-127">Right-click on the shape chart and select **Series Properties**.</span></span>  
  
5.  <span data-ttu-id="47114-128">In **Riempimento**fare clic sul pulsante **Espressione** (*fx*) per modificare l'espressione per la proprietà **Colore** .</span><span class="sxs-lookup"><span data-stu-id="47114-128">In **Fill**, click the **Expression** (*fx*) button to edit the expression for the **Color** property.</span></span>  
  
6.  <span data-ttu-id="47114-129">Digitare l'espressione seguente, in cui "MyCategoryField" è il campo visualizzato nell'area **Gruppi di categorie** :</span><span class="sxs-lookup"><span data-stu-id="47114-129">Type the following expression, where "MyCategoryField" is the field that is displayed in the **Category Groups** area:</span></span>  
  
    ```  
    =Code.GetColor(Fields!MyCategoryField)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="47114-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47114-130">See Also</span></span>  
 <span data-ttu-id="47114-131">[Formattazione dei colori delle serie in un grafico &#40;Generatore report e SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47114-131">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47114-132">[Aggiungere stili smussato, rilievo e trama a un grafico &#40;Generatore report e SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="47114-132">[Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span></span>  
 <span data-ttu-id="47114-133">[Definire i colori in un grafico mediante la tavolozza &#40;Generatore report e SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47114-133">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47114-134">[Aggiungere punti vuoti al grafico &#40;Generatore report e SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47114-134">[Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47114-135">[Grafici con forme &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47114-135">[Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47114-136">[Collegamento di più aree dati allo stesso set di dati &#40;Generatore report e SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47114-136">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47114-137">[Aree dati annidate &#40;Generatore report e SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47114-137">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="47114-138">Grafici sparkline e barre dei dati &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="47114-138">Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
