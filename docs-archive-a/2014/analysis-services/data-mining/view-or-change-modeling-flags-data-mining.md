---
title: Visualizzare o modificare i flag di modellazione (data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d1169735-fb18-417b-b8d6-9a161e444020
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf0edd827321685a2d6a9041759328a7ac6e7cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717022"
---
# <a name="view-or-change-modeling-flags-data-mining"></a><span data-ttu-id="41e8f-102">Visualizzare o modificare flag di modellazione (Data mining)</span><span class="sxs-lookup"><span data-stu-id="41e8f-102">View or Change Modeling Flags (Data Mining)</span></span>
  <span data-ttu-id="41e8f-103">I flag di modellazione sono proprietà impostate in una colonna della struttura di data mining o in colonne del modello di data mining per controllare la modalità di elaborazione dei dati durante l'analisi da parte dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="41e8f-103">Modeling flags are properties that you set on a mining structure column or mining model columns to control how the algorithm processes the data during analysis.</span></span>  
  
 <span data-ttu-id="41e8f-104">In Progettazione modelli di data mining è possibile visualizzare e modificare i flag di modellazione associati a una struttura di data mining o a una colonna di data mining visualizzando le proprietà della struttura o del modello.</span><span class="sxs-lookup"><span data-stu-id="41e8f-104">In Data Mining Designer, you can view and modify the modeling flags associated with a mining structure or mining column by viewing the properties of the structure or model.</span></span> <span data-ttu-id="41e8f-105">Inoltre, è possibile impostare i flag di modellazione tramite DMX, AMO o XMLA.</span><span class="sxs-lookup"><span data-stu-id="41e8f-105">You can also set modeling flags by using DMX, AMO, or XMLA.</span></span>  
  
 <span data-ttu-id="41e8f-106">In questa procedura viene descritto come modificare i flag di modellazione nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="41e8f-106">This procedure describes how to change the modeling flags in the designer.</span></span>  
  
### <a name="view-or-change-the-modeling-flag-for-a-structure-column-or-model-column"></a><span data-ttu-id="41e8f-107">Visualizzare o modificare il flag di modellazione per una colonna della struttura o una colonna del modello</span><span class="sxs-lookup"><span data-stu-id="41e8f-107">View or change the modeling flag for a structure column or model column</span></span>  
  
1.  <span data-ttu-id="41e8f-108">In SQL Server Design Studio aprire Esplora soluzioni, quindi fare doppio clic sulla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="41e8f-108">In SQL Server Design Studio, open Solution Explorer, and then double-click the mining structure.</span></span>  
  
2.  <span data-ttu-id="41e8f-109">Per impostare il flag di modellazione NOT NULL, fare clic sulla scheda **struttura di data mining** . Per impostare il REGRESSOre o i flag di MODEL_EXISTENCE_ONLY, fare clic sulla scheda **modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="41e8f-109">To set the NOT NULL modeling flag, click the **Mining Structure** tab. To set the REGRESSOR or MODEL_EXISTENCE_ONLY flags, click the **Mining Model** tab.</span></span>  
  
3.  <span data-ttu-id="41e8f-110">Fare clic con il pulsante destro del mouse sulla colonna da visualizzare o modificare, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="41e8f-110">Right-click the column you want to view or change, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="41e8f-111">Per aggiungere un nuovo flag di modellazione, fare clic sulla casella di testo accanto alla proprietà **ModelingFlags** e selezionare le casella o le caselle di controllo relative ai flag di modellazione che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="41e8f-111">To add a new modeling flag, click the text box next to the **ModelingFlags** property, and select the check box or check boxes for the modeling flags you want to use.</span></span>  
  
     <span data-ttu-id="41e8f-112">I flag di modellazione vengono visualizzati solo se sono appropriati per il tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="41e8f-112">Modeling flags are displayed only if they are appropriate for the column data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="41e8f-113">Dopo avere modificato un flag di modellazione, è necessario rielaborare il modello.</span><span class="sxs-lookup"><span data-stu-id="41e8f-113">After you change a modeling flag, you must reprocess the model.</span></span>  
  
### <a name="get-the-modeling-flags-used-in-the-model"></a><span data-ttu-id="41e8f-114">Recuperare i flag di modellazione utilizzati nel modello</span><span class="sxs-lookup"><span data-stu-id="41e8f-114">Get the modeling flags used in the model</span></span>  
  
-   <span data-ttu-id="41e8f-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire una finestra Query DMX e digitare una query simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="41e8f-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window, and type a query like the following:</span></span>  
  
    ```  
    SELECT COLUMN_NAME, CONTENT_TYPE, MODELING_FLAG  
    FROM $system.DMSCHEMA_MINING_COLUMNS  
    WHERE MODEL_NAME = 'Forecasting'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="41e8f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41e8f-116">See Also</span></span>  
 <span data-ttu-id="41e8f-117">[Attività e procedure relative al modello di data mining](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="41e8f-117">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="41e8f-118">Flag di modellazione &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="41e8f-118">Modeling Flags &#40;Data Mining&#41;</span></span>](modeling-flags-data-mining.md)  
  
  
