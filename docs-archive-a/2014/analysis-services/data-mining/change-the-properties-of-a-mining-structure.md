---
title: Modificare le proprietà di una struttura di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], properties
ms.assetid: 03b16897-2e36-42b8-9f7d-db1b9b898401
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c1e63ad5fada770394e2fc283e0e592319281b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711163"
---
# <a name="change-the-properties-of-a-mining-structure"></a><span data-ttu-id="f7c94-102">Modificare le proprietà di una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="f7c94-102">Change the Properties of a Mining Structure</span></span>
  <span data-ttu-id="f7c94-103">Sono disponibili due tipi di proprietà su una struttura di data mining, entrambi modificabili:</span><span class="sxs-lookup"><span data-stu-id="f7c94-103">There are two kinds of properties on a mining structure, both of which can be modified:</span></span>  
  
-   <span data-ttu-id="f7c94-104">Proprietà della struttura di data mining che influiscono sull'intera struttura</span><span class="sxs-lookup"><span data-stu-id="f7c94-104">Properties of the mining structure that affect the entire structure</span></span>  
  
-   <span data-ttu-id="f7c94-105">Proprietà su singole colonne della struttura</span><span class="sxs-lookup"><span data-stu-id="f7c94-105">Properties on individual columns in the structure</span></span>  
  
 <span data-ttu-id="f7c94-106">Si noti che alcune proprietà dipendono da altre impostazioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7c94-106">Note that some properties are dependent on other property settings.</span></span> <span data-ttu-id="f7c94-107">Non è ad esempio possibile impostare le proprietà che controllano la creazione di contenitori, ad esempio <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> o <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> finché non viene impostato il tipo di dati della colonna su `Discretized`.</span><span class="sxs-lookup"><span data-stu-id="f7c94-107">For example, you cannot set properties that control binning behavior (such as <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> or <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) until you have set the data type of the column to `Discretized`.</span></span>  
  
 <span data-ttu-id="f7c94-108">Per altre informazioni sulle proprietà di data mining, vedere [Colonne della struttura di data mining](mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="f7c94-108">For more information about mining structure properties, see [Mining Structure Columns](mining-structure-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-structure"></a><span data-ttu-id="f7c94-109">Per modificare le proprietà di una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="f7c94-109">To change the properties of a mining structure</span></span>  
  
1.  <span data-ttu-id="f7c94-110">Nella scheda **Struttura di data mining** di Progettazione modelli di data mining fare clic con il pulsante destro del mouse sulla struttura di data mining o su una colonna della struttura e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f7c94-110">On the **Mining Structure** tab in Data Mining Designer, right-click either the mining structure or a column in the mining structure, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="f7c94-111">A destra dello schermo verrà visualizzata la finestra **Proprietà** , se non è già visualizzata.</span><span class="sxs-lookup"><span data-stu-id="f7c94-111">The **Properties** window opens on the right side of the screen, if it was not already visible.</span></span>  
  
2.  <span data-ttu-id="f7c94-112">Nella finestra **Proprietà** selezionare il valore corrispondente alla proprietà che si vuole modificare e quindi immettere il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f7c94-112">In the **Properties** window, select the value that corresponds to the property that you want to change, and then enter the new value.</span></span>  
  
     <span data-ttu-id="f7c94-113">Il nuovo valore diventerà effettivo quando si seleziona un elemento diverso nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f7c94-113">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c94-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7c94-114">See Also</span></span>  
 [<span data-ttu-id="f7c94-115">Attività e procedure relative alla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="f7c94-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
