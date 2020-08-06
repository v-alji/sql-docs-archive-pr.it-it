---
title: Grafici azionari (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f75ca11e-b7f5-4ac0-ba17-fe6f82742dad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0f8c9c7dbc750bdb477f2ea1d96aa03f7ad022f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623766"
---
# <a name="stock-charts-report-builder-and-ssrs"></a><span data-ttu-id="f177e-102">Grafici azionari (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f177e-102">Stock Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f177e-103">I grafici azionari sono progettati appositamente per i dati finanziari o scientifici in cui si usano fino a quattro valori per ogni punto dati.</span><span class="sxs-lookup"><span data-stu-id="f177e-103">A stock chart is specifically designed for financial or scientific data that uses up to four values per data point.</span></span> <span data-ttu-id="f177e-104">Questi valori si allineano ai valori massimo, minimo, di apertura e di chiusura usati per tracciare dati azionari finanziari.</span><span class="sxs-lookup"><span data-stu-id="f177e-104">These values align with the high, low, open and close values that are used to plot financial stock data.</span></span> <span data-ttu-id="f177e-105">In questo tipo di grafico i valori di apertura o di chiusura vengono visualizzati tramite i marcatori, solitamente linee o triangoli.</span><span class="sxs-lookup"><span data-stu-id="f177e-105">This chart type displays opening and closing values by using markers, which are typically lines or triangles.</span></span> <span data-ttu-id="f177e-106">Nell'esempio seguente i valori di apertura sono rappresentati dai marcatori a sinistra, mentre quelli di chiusura dai marcatori a destra.</span><span class="sxs-lookup"><span data-stu-id="f177e-106">In the following example, the opening values are shown by the markers on the left, and the closing values are shown by the markers on the right.</span></span>  
  
 <span data-ttu-id="f177e-107">![Grafico azionario](../media/rs-stockchart.gif "Grafico azionario")</span><span class="sxs-lookup"><span data-stu-id="f177e-107">![Stock chart](../media/rs-stockchart.gif "Stock chart")</span></span>  
  
 <span data-ttu-id="f177e-108">Un esempio di questo grafico azionario è disponibile come report di Generatore report di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] di esempio.</span><span class="sxs-lookup"><span data-stu-id="f177e-108">An example of a stock chart is available as a sample [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="f177e-109">Per altre informazioni sul download di questo e di altri report di esempio, vedere la pagina relativa ai [report di esempio per Generatore report e Progettazione report](https://go.microsoft.com/fwlink/?LinkId=198283) di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f177e-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="f177e-110">Variazioni</span><span class="sxs-lookup"><span data-stu-id="f177e-110">Variations</span></span>  
  
-   <span data-ttu-id="f177e-111">**Candela**.</span><span class="sxs-lookup"><span data-stu-id="f177e-111">**Candlestick**.</span></span> <span data-ttu-id="f177e-112">Il grafico a candela è un tipo speciale di grafico azionario in cui si usano caselle per indicare l'intervallo tra i valori di apertura e di chiusura.</span><span class="sxs-lookup"><span data-stu-id="f177e-112">The candlestick chart is a specialized form of the stock chart, wherein boxes are used to show the range between the open and close values.</span></span> <span data-ttu-id="f177e-113">Analogamente al grafico azionario, il grafico a candela consente di visualizzare fino a quattro valori per ogni punto dati.</span><span class="sxs-lookup"><span data-stu-id="f177e-113">Like the stock chart, the candlestick chart can display up to four values per data point.</span></span>  
  
## <a name="data-considerations-for-stock-charts"></a><span data-ttu-id="f177e-114">Considerazioni sui dati per i grafici azionari</span><span class="sxs-lookup"><span data-stu-id="f177e-114">Data Considerations for Stock Charts</span></span>  
  
-   <span data-ttu-id="f177e-115">Quando si presentano molti punti dati azionari, ad esempio la tendenza annua dei prezzi azionari, risulta difficile distinguere ogni valore di apertura, di chiusura, massimo e minimo di ogni punto dati.</span><span class="sxs-lookup"><span data-stu-id="f177e-115">When presenting many stock data points, such as annual stock price trend, it is difficult to distinguish each open, close, high and low value of each data point.</span></span> <span data-ttu-id="f177e-116">In questo scenario è consigliabile usare un grafico a linee anziché un grafico azionario.</span><span class="sxs-lookup"><span data-stu-id="f177e-116">In this scenario, consider using a line chart instead of a stock chart.</span></span>  
  
-   <span data-ttu-id="f177e-117">Quando vengono generate le etichette degli assi, la numerazione inizia solitamente da zero.</span><span class="sxs-lookup"><span data-stu-id="f177e-117">When axis labels are generated, labeling usually begins at zero.</span></span>  <span data-ttu-id="f177e-118">In generale, i prezzi azionari non presentano lo stesso grado di fluttuazione di altri set di dati.</span><span class="sxs-lookup"><span data-stu-id="f177e-118">In general, stock prices do not fluctuate to the same degree as other data sets.</span></span> <span data-ttu-id="f177e-119">Per questo motivo, è possibile evitare che le etichette dell'asse inizino da zero, in modo da ottenere una visuale migliore dei dati.</span><span class="sxs-lookup"><span data-stu-id="f177e-119">For this reason, you may want to disable the axis labels from starting at zero, in order to get a better view of your data.</span></span> <span data-ttu-id="f177e-120">A tale scopo, impostare **IncludeZero** su **false** nella finestra di dialogo **Proprietà asse** o nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="f177e-120">To do this, set **IncludeZero** to **false** in the **Axis Properties** dialog box or the Properties window.</span></span> <span data-ttu-id="f177e-121">Per altre informazioni sulla generazione delle etichette dell'asse da parte del grafico, vedere [Formattazione delle etichette degli assi in un grafico &#40;Generatore report e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f177e-121">For more information about how the chart generates axis labels, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="f177e-122">sono disponibili molte formule calcolate da usare con i grafici azionari, tra cui Indicatori prezzo, Indice di forza relativa, MACD e così via.</span><span class="sxs-lookup"><span data-stu-id="f177e-122">provides many calculated formulas for use with stock charts, including Price Indicator, Relative Strength Index, MACD and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f177e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f177e-123">See Also</span></span>  
 <span data-ttu-id="f177e-124">[Grafici a intervalli &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f177e-124">[Range Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f177e-125">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f177e-125">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f177e-126">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f177e-126">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f177e-127">Finestra di dialogo Proprietà asse, Opzioni asse &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f177e-127">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
