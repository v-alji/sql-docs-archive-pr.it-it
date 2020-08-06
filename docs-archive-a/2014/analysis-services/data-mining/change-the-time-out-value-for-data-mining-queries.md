---
title: Modificare il valore di timeout per le query di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time-out
ms.assetid: f1add4bc-e882-440a-a98b-333cfa274c3e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dcdcdcbb6e2aef48dd8725f10f38180c73f5f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630167"
---
# <a name="change-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="091b4-102">Modificare il valore di timeout per le query di data mining</span><span class="sxs-lookup"><span data-stu-id="091b4-102">Change the Time-out Value for Data Mining Queries</span></span>
  <span data-ttu-id="091b4-103">Quando si compila un grafico di accuratezza o si esegue una query di stima, talvolta la generazione di tutti i dati necessari per la stima può richiedere una notevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="091b4-103">When you build a lift chart or execute a prediction query, sometimes it can take a long time to generate all the data required for the prediction.</span></span> <span data-ttu-id="091b4-104">Per impedire il timeout della query, è possibile modificare il valore che controlla l'intervallo di tempo durante il quale il server [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] attende il completamento di una query.</span><span class="sxs-lookup"><span data-stu-id="091b4-104">To prevent the query from timing out, you can change the value that controls how long the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server waits to complete a query.</span></span>  
  
 <span data-ttu-id="091b4-105">Il valore predefinito è 15; tuttavia, se i modelli sono complessi o l'origine dati è di grandi dimensioni, questo tempo potrebbe non essere sufficiente.</span><span class="sxs-lookup"><span data-stu-id="091b4-105">The default value is 15; however, if your models are complex or the data source is large, this might not be enough.</span></span> <span data-ttu-id="091b4-106">Se necessario, è possibile aumentare notevolmente il valore in modo da assegnare una quantità di tempo sufficiente per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="091b4-106">If necessary, you can increase the value significantly, to enable enough time for processing.</span></span> <span data-ttu-id="091b4-107">Se ad esempio l'opzione **Timeout query** viene impostata su 600, l'esecuzione della query può continuare per un totale di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="091b4-107">For example, if you set **Query Timeout** to 600, the query could continue to run for up to 10 minutes.</span></span>  
  
 <span data-ttu-id="091b4-108">Per altre informazioni sulle query di stima, vedere [Attività e procedure relative alle query di data mining](data-mining-query-tasks-and-how-tos.md).</span><span class="sxs-lookup"><span data-stu-id="091b4-108">For more information about prediction queries, see [Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md).</span></span>  
  
### <a name="configure-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="091b4-109">Configurare il valore di timeout per le query di data mining</span><span class="sxs-lookup"><span data-stu-id="091b4-109">Configure the time-out value for data mining queries</span></span>  
  
1.  <span data-ttu-id="091b4-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="091b4-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from the **Tools** menu, selection **Options**.</span></span>  
  
2.  <span data-ttu-id="091b4-111">Nel riquadro **Opzioni** espandere **Finestre di progettazione Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="091b4-111">In the **Options** pane, expand **Business Intelligence Designers**.</span></span>  
  
3.  <span data-ttu-id="091b4-112">Fare clic sulla casella di testo **Timeout query** e digitare un valore per il numero di secondi.</span><span class="sxs-lookup"><span data-stu-id="091b4-112">Click the **Query Timeout** text box, and type a value for the number of seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091b4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="091b4-113">See Also</span></span>  
 <span data-ttu-id="091b4-114">[Attività e procedure relative alle query di data mining](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="091b4-114">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="091b4-115">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="091b4-115">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
