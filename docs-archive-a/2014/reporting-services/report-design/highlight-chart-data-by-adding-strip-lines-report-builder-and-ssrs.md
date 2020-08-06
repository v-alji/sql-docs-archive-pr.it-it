---
title: Evidenziare i dati del grafico mediante l'aggiunta di strisce (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: addd6137-4b6e-4e88-a7e8-9600fcd1ccce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01b0bb41a71daf9ac558ce8d8bb84480426870c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625145"
---
# <a name="highlight-chart-data-by-adding-strip-lines-report-builder-and-ssrs"></a><span data-ttu-id="288a2-102">Evidenziare i dati del grafico mediante l'aggiunta di strisce (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="288a2-102">Highlight Chart Data by Adding Strip Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="288a2-103">Le strisce o bande sono intervalli orizzontali o verticali che applicano un'ombreggiatura allo sfondo del grafico a intervalli regolari o personalizzati.</span><span class="sxs-lookup"><span data-stu-id="288a2-103">Strip lines, or strips, are horizontal or vertical ranges that shade the background of the chart in regular or custom intervals.</span></span> <span data-ttu-id="288a2-104">È possibile utilizzare le strisce per:</span><span class="sxs-lookup"><span data-stu-id="288a2-104">You can use strip lines to:</span></span>  
  
-   <span data-ttu-id="288a2-105">Migliorare la leggibilità per la ricerca di singoli valori nel grafico.</span><span class="sxs-lookup"><span data-stu-id="288a2-105">Improve readability for looking up individual values on the chart.</span></span> <span data-ttu-id="288a2-106">Specificare strisce a intervalli regolari per consentire di separare i punti dati durante la lettura del grafico.</span><span class="sxs-lookup"><span data-stu-id="288a2-106">Specify strip lines at regular intervals to help separate data points when reading the chart.</span></span>  
  
-   <span data-ttu-id="288a2-107">Evidenziare date che ricorrono a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="288a2-107">Highlight dates that occur at regular intervals.</span></span> <span data-ttu-id="288a2-108">Ad esempio, in un report sulle vendite è possibile utilizzare le strisce per identificare i punti dati relativi ai fine settimana.</span><span class="sxs-lookup"><span data-stu-id="288a2-108">For example, in a sales report you might use strip lines to identify weekend data points.</span></span>  
  
-   <span data-ttu-id="288a2-109">Evidenziare un intervallo chiave specifico.</span><span class="sxs-lookup"><span data-stu-id="288a2-109">Highlight a specific key range.</span></span> <span data-ttu-id="288a2-110">Nell'ambito dell'esempio precedente, è possibile utilizzare una striscia per evidenziare l'intervallo di vendite più elevato compreso tra 80 e 100 dollari.</span><span class="sxs-lookup"><span data-stu-id="288a2-110">Using the previous example, you can use one strip line to highlight the highest range of sales that is between $80-100.</span></span>  
  
 <span data-ttu-id="288a2-111">Le strisce non sono applicabili ai tipi di grafico polari o con forme.</span><span class="sxs-lookup"><span data-stu-id="288a2-111">Strip lines are not applicable to Shape or Polar chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-interlaced-strip-lines-at-regular-intervals-on-a-chart"></a><span data-ttu-id="288a2-112">Per visualizzare strisce interlacciate a intervalli regolari in un grafico</span><span class="sxs-lookup"><span data-stu-id="288a2-112">To display interlaced strip lines at regular intervals on a chart</span></span>  
  
1.  <span data-ttu-id="288a2-113">Per mostrare strisce orizzontali, fare clic con il pulsante destro del mouse sull'asse del grafico verticale e scegliere **Proprietà asse verticale**.</span><span class="sxs-lookup"><span data-stu-id="288a2-113">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="288a2-114">Per mostrare strisce verticali, fare clic con il pulsante destro del mouse sull'asse del grafico orizzontale e scegliere **Proprietà asse orizzontale**.</span><span class="sxs-lookup"><span data-stu-id="288a2-114">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="288a2-115">Selezionare l'opzione **Usa interlacciamento** .</span><span class="sxs-lookup"><span data-stu-id="288a2-115">Select the **Use interlacing** option.</span></span> <span data-ttu-id="288a2-116">Sul grafico verranno visualizzate delle strisce di colore grigio.</span><span class="sxs-lookup"><span data-stu-id="288a2-116">Grey strip lines will appear on your chart.</span></span>  
  
3.  <span data-ttu-id="288a2-117">(Facoltativo) Specificare un colore per le strisce usando l'elenco a discesa **Colore** adiacente.</span><span class="sxs-lookup"><span data-stu-id="288a2-117">(Optional) Specify a color for the strip lines using the adjacent **Color** drop-down list.</span></span>  
  
### <a name="to-display-interlaced-strip-lines-at-custom-intervals-on-a-chart"></a><span data-ttu-id="288a2-118">Per visualizzare strisce interlacciate a intervalli personalizzati in un grafico</span><span class="sxs-lookup"><span data-stu-id="288a2-118">To display interlaced strip lines at custom intervals on a chart</span></span>  
  
1.  <span data-ttu-id="288a2-119">Per mostrare strisce orizzontali, fare clic con il pulsante destro del mouse sull'asse del grafico verticale e scegliere **Proprietà asse verticale**.</span><span class="sxs-lookup"><span data-stu-id="288a2-119">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="288a2-120">Per mostrare strisce verticali, fare clic con il pulsante destro del mouse sull'asse del grafico orizzontale e scegliere **Proprietà asse orizzontale**.</span><span class="sxs-lookup"><span data-stu-id="288a2-120">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
     <span data-ttu-id="288a2-121">Nella finestra Proprietà verranno visualizzate le proprietà dell'asse.</span><span class="sxs-lookup"><span data-stu-id="288a2-121">The axis properties are displayed in the Properties window.</span></span>  
  
2.  <span data-ttu-id="288a2-122">Nella sezione **Aspetto** del riquadro Proprietà fare clic sul pulsante di modifica della raccolta (...) per la proprietà StripLines per aprire **Editor raccolte ChartStripLine**.</span><span class="sxs-lookup"><span data-stu-id="288a2-122">In the **Appearance** section of the Properties pane, for the StripLines property, click the Edit Collection (...) button to open the **ChartStripLine Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="288a2-123">Fare clic su **Aggiungi** per aggiungere una nuova striscia alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="288a2-123">Click **Add** to add a new strip line to the collection.</span></span>  
  
4.  <span data-ttu-id="288a2-124">Fare clic su StripWidth per specificare la larghezza della striscia, misurata in pollici sul report.</span><span class="sxs-lookup"><span data-stu-id="288a2-124">Click StripWidth to specify the width of the strip line, measured in inches on the report.</span></span> <span data-ttu-id="288a2-125">Se si vogliono evidenziare date oppure ore, fare clic su StripWidthType e selezionare un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="288a2-125">If you are highlighting dates or times, click StripWidthType and select a time interval.</span></span>  
  
5.  <span data-ttu-id="288a2-126">Digitare un valore o un'espressione per l'intervallo in modo da specificare la frequenza con cui si ripeterà la striscia.</span><span class="sxs-lookup"><span data-stu-id="288a2-126">Type a value or expression for the Interval to specify how often the strip line will repeat.</span></span>  <span data-ttu-id="288a2-127">Ad esempio, se si specifica un intervallo 10, e la lunghezza riga è 5, le strisce verranno visualizzate in corrispondenza dei valori 0 - 5, 15 - 20, 30 - 35 e così via.</span><span class="sxs-lookup"><span data-stu-id="288a2-127">For example, if you specify an interval of 10, and your strip line width is 5, strip lines will display at values of 0 to 5, 15 to 20, 30 to 35, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="288a2-128">Per impostazione predefinita, l'intervallo è impostato su Automatico. Per questo motivo, non verrà calcolato un intervallo per le strisce personalizzato.</span><span class="sxs-lookup"><span data-stu-id="288a2-128">By default, Interval is set to Auto, which means the chart will not calculate an interval for custom strip lines.</span></span> <span data-ttu-id="288a2-129">Gli intervalli per le strisce verranno calcolati solo se è impostato un valore di intervallo.</span><span class="sxs-lookup"><span data-stu-id="288a2-129">The chart only calculates intervals for strip lines if an interval value is set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="288a2-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="288a2-130">See Also</span></span>  
 <span data-ttu-id="288a2-131">[Formattazione delle etichette degli assi in un grafico &#40;Generatore report e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="288a2-131">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="288a2-132">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="288a2-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="288a2-133">Aggiungere una media mobile a un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="288a2-133">Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md)  
  
  
