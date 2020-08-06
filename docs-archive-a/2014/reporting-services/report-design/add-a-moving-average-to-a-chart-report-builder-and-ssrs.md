---
title: Aggiungere una media mobile a un grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166cf9c1-0750-4866-8381-542e4fbfe65a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bc16d0cb45a3240148f931009a836c231b442b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623802"
---
# <a name="add-a-moving-average-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="ff3a5-102">Aggiungere una media mobile a un grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ff3a5-102">Add a Moving Average to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ff3a5-103">Una media mobile è una media dei dati della serie, calcolata in un periodo di tempo definito.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-103">A moving average is an average of the data in your series, calculated over a defined period of time.</span></span> <span data-ttu-id="ff3a5-104">È possibile indicare la media mobile sul grafico per identificare tendenze significative.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-104">The moving average can be shown on the chart to identify significant trends.</span></span>  
  
 <span data-ttu-id="ff3a5-105">La formula della media mobile è l'indicatore di prezzo più diffuso utilizzato nelle analisi tecniche.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-105">The Moving Average formula is the most popular price indicator used in technical analyses.</span></span> <span data-ttu-id="ff3a5-106">Da una serie del grafico è anche possibile derivare molte altre formule, ad esempio media, mediana e deviazione standard.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-106">Many other formulas, including mean, median and standard deviation, can also be derived from a series on the chart.</span></span> <span data-ttu-id="ff3a5-107">Quando si specifica una media mobile, ogni formula può includere uno o più parametri che devono essere specificati.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-107">When specifying a moving average, each formula may have one or more parameters that must be specified.</span></span>  
  
 <span data-ttu-id="ff3a5-108">Quando si aggiunge una media mobile in modalità progettazione, la serie di linee aggiunta è solo un segnaposto visivo.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-108">When a moving average formula is added in Design mode, the line series that is added is only a visual placeholder.</span></span> <span data-ttu-id="ff3a5-109">I punti dati di ogni formula verranno calcolati durante l'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-109">The chart will calculate the data points of each formula during report processing.</span></span>  
  
 <span data-ttu-id="ff3a5-110">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]non è disponibile il supporto incorporato per le linee di tendenza.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-110">Built-in support for trend lines is not available in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-calculated-moving-average-to-a-series-on-the-chart"></a><span data-ttu-id="ff3a5-111">Per aggiungere una media mobile calcolata in una serie del grafico</span><span class="sxs-lookup"><span data-stu-id="ff3a5-111">To add a calculated moving average to a series on the chart</span></span>  
  
1.  <span data-ttu-id="ff3a5-112">Fare clic con il pulsante destro del mouse in un campo dell'area **Valori** e scegliere **Aggiungi serie calcolata**.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-112">Right-click on a field in the **Values** area and click **Add Calculated Series**.</span></span> <span data-ttu-id="ff3a5-113">Verrà visualizzata la finestra di dialogo **Proprietà serie calcolata** .</span><span class="sxs-lookup"><span data-stu-id="ff3a5-113">The **Calculated Series Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="ff3a5-114">Selezionare l'opzione **Media mobile** dall'elenco a discesa **Formula** .</span><span class="sxs-lookup"><span data-stu-id="ff3a5-114">Select the **Moving average** option from the **Formula** drop-down list.</span></span>  
  
3.  <span data-ttu-id="ff3a5-115">Specificare un valore intero per **Periodo** , che rappresenta il periodo della media mobile.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-115">Specify an integer value for the **Period** that represents the period of the moving average.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff3a5-116">Il periodo è il numero di giorni utilizzato per calcolare una media mobile.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-116">The period is the number of days used to calculate a moving average.</span></span> <span data-ttu-id="ff3a5-117">Se sull'asse X non sono rappresentati valori di data/ora, il periodo è rappresentato dal numero di punti dati utilizzati per calcolare una media mobile.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-117">If date/time values are not specified on the x-axis, the period is represented by the number of data points used to calculate a moving average.</span></span> <span data-ttu-id="ff3a5-118">Se è disponibile un unico punto dati, la formula della media mobile non viene calcolata.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-118">If there is only one data point, the moving average formula does not calculate.</span></span> <span data-ttu-id="ff3a5-119">La media mobile viene calcolata a partire dal secondo punto.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-119">The moving average is calculated starting at the second point.</span></span> <span data-ttu-id="ff3a5-120">Se si specifica l'opzione **Inizia dal primo punto** , la media mobile verrà iniziata dal primo punto.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-120">If you specify the **Start from first point** option, the chart will start the moving average at the first point.</span></span> <span data-ttu-id="ff3a5-121">Se è disponibile un unico punto dati, il punto nella media mobile calcolata sarà identico al primo punto della serie originale.</span><span class="sxs-lookup"><span data-stu-id="ff3a5-121">If there is only one data point, the point in the calculated moving average will be identical to the first point in your original series.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3a5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff3a5-122">See Also</span></span>  
 <span data-ttu-id="ff3a5-123">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff3a5-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ff3a5-124">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff3a5-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ff3a5-125">Aggiungere punti vuoti al grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ff3a5-125">Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;</span></span>](add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
  
