---
title: Scheda grafico di accuratezza (vista Grafico accuratezza modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.liftchart.f1
ms.assetid: f1674e2e-d38e-40c7-b8d1-5585ce9a0168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7cdad01ff3549140bf4fed606b1e8f9eaed10dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727256"
---
# <a name="lift-chart-tab-mining-accuracy-chart-view"></a><span data-ttu-id="37bc9-102">Scheda Grafico di accuratezza (vista Grafico di accuratezza modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="37bc9-102">Lift Chart Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="37bc9-103">Usare il riquadro **Grafico di accuratezza** per visualizzare un grafico di confronto di tutti i modelli di data mining selezionati nella struttura di data mining specificata.</span><span class="sxs-lookup"><span data-stu-id="37bc9-103">Use the **Lift Chart** pane to view a chart that compares all the selected mining models in the selected mining structure.</span></span>  
  
 <span data-ttu-id="37bc9-104">Se nel modello viene stimato un attributo discreto, è possibile che nel riquadro venga visualizzato un grafico di accuratezza o un grafico dei profitti.</span><span class="sxs-lookup"><span data-stu-id="37bc9-104">If the model predicts a discrete attribute, the pane can display either a lift chart or a profit chart.</span></span> <span data-ttu-id="37bc9-105">Per informazioni sui grafici di accuratezza, vedere [Grafico di accuratezza &#40;Analysis Services - Data mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="37bc9-105">For information about lift charts, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="37bc9-106">Per creare un grafico dei profitti è necessario fornire informazioni aggiuntive sul costo dell'implementazione dei requisiti del modello di data mining nonché del risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="37bc9-106">To create a profit chart, you must provide additional information about the cost of implementing the recommendations of the mining model, as well as the expected return.</span></span> <span data-ttu-id="37bc9-107">Per altre informazioni, vedere [Grafico profitt &#40;Analysis Services - Data mining&#41;](data-mining/profit-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="37bc9-107">For more information, see [Profit Chart &#40;Analysis Services - Data Mining&#41;](data-mining/profit-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="37bc9-108">Se nel modello viene stimato un attributo continuo, nel riquadro viene visualizzato un grafico a dispersione.</span><span class="sxs-lookup"><span data-stu-id="37bc9-108">If the model predicts a continuous attribute, the pane will display a scatter plot graph.</span></span>  
  
 <span data-ttu-id="37bc9-109">Per informazioni generali sui metodi di misurazione dell'accuratezza di un modello di data mining, vedere [Grafico di accuratezza &#40;Analysis Services - Data mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="37bc9-109">For general information about methods of measuring the accuracy of a mining model, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="37bc9-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="37bc9-110">Options</span></span>  
 <span data-ttu-id="37bc9-111">**Tipo di grafico**</span><span class="sxs-lookup"><span data-stu-id="37bc9-111">**Chart Type**</span></span>  
 <span data-ttu-id="37bc9-112">Consente di impostare il tipo di grafico da visualizzare nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="37bc9-112">Sets the type of chart to display in the viewer.</span></span> <span data-ttu-id="37bc9-113">È possibile selezionare **Grafico di accuratezza** o **Grafico profitti**.</span><span class="sxs-lookup"><span data-stu-id="37bc9-113">You can select either **Lift Chart** or **Profit Chart**.</span></span>  
  
 <span data-ttu-id="37bc9-114">**Impostazioni**</span><span class="sxs-lookup"><span data-stu-id="37bc9-114">**Settings**</span></span>  
 <span data-ttu-id="37bc9-115">Consente di aprire la finestra di dialogo **Impostazioni grafico profitti** , utilizzabile per configurare un grafico dei profitti.</span><span class="sxs-lookup"><span data-stu-id="37bc9-115">Opens the **Profit Chart Settings** dialog box, which you can use to configure a profit chart.</span></span>  
  
 <span data-ttu-id="37bc9-116">Il grafico dei profitti non è disponibile se si seleziona una colonna stimabile continua nella scheda **Mapping colonne** .</span><span class="sxs-lookup"><span data-stu-id="37bc9-116">The profit chart is not available if a continuous predictable column was selected in the **Column Mapping** tab.</span></span>  
  
 <span data-ttu-id="37bc9-117">**Copia**</span><span class="sxs-lookup"><span data-stu-id="37bc9-117">**Copy**</span></span>  
 <span data-ttu-id="37bc9-118">Consente di copiare il grafico negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="37bc9-118">Copies the chart to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37bc9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37bc9-119">See Also</span></span>  
 <span data-ttu-id="37bc9-120">[Progettazione Grafico accuratezza modello di data mining &#40;&#41;di data mining](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="37bc9-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="37bc9-121">[Attività e procedure di test e convalida &#40;di data mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="37bc9-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="37bc9-122">Test e convalida &#40;Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="37bc9-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
