---
title: Selezione dimensione cubo di origine (creazione guidata modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.selectsourcecube.f1
ms.assetid: 556e216b-5e21-4160-967d-4c57591fbab4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6295a5312b4501236e0ce8f5776fc43c0d014581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625593"
---
# <a name="select-the-source-cube-dimension-data-mining-wizard"></a><span data-ttu-id="e218e-102">Selezione dimensione cubo di origine (Creazione guidata modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="e218e-102">Select the Source Cube Dimension (Data Mining Wizard)</span></span>
  <span data-ttu-id="e218e-103">Usare la pagina **Selezione dimensione cubo di origine** per selezionare la dimensione del cubo contenente i case da analizzare.</span><span class="sxs-lookup"><span data-stu-id="e218e-103">Use the **Select the Source Cube Dimension** page to select the dimension from the cube that contains the cases you want to analyze.</span></span> <span data-ttu-id="e218e-104">Se, ad esempio, si compila un modello che analizza il comportamento di acquisto dei clienti in base ai dati demografici, è necessario selezionare la dimensione Customer che in genere contiene un record univoco per ogni cliente e vari attributi che rappresentano i dati demografici, ad esempio sesso, ubicazione o reddito.</span><span class="sxs-lookup"><span data-stu-id="e218e-104">For example, if you are building a model that analyzes the purchasing behavior of customers based on demographics, you would select the Customer dimension, which typically contains a unique record for each customer and various attributes that represent demographics, such as gender, location, or income.</span></span> <span data-ttu-id="e218e-105">Più avanti nella procedura guidata si potrà aggiungere una tabella correlata a questa tabella del case, ad esempio una tabella nidificata in cui sono elencati i prodotti acquistati dal cliente.</span><span class="sxs-lookup"><span data-stu-id="e218e-105">Later in the wizard you will have the opportunity to add a table that is related to this case table: for example, you might add a nested table that shows which products the customer has purchased.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e218e-106">Questa pagina viene visualizzata solo se è stata selezionata l'opzione **Da cubo esistente** nella pagina **Selezione metodo di definizione** della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e218e-106">This page will appear only if you have selected **From existing cube** on the **Select the Definition Method** page of the wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e218e-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e218e-107">Options</span></span>  
 <span data-ttu-id="e218e-108">**Selezionare una dimensione del cubo di origine**</span><span class="sxs-lookup"><span data-stu-id="e218e-108">**Select a Source Cube Dimension**</span></span>  
 <span data-ttu-id="e218e-109">Consente di selezionare la dimensione del cubo da cui verranno recuperati i dati dell'origine per la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="e218e-109">Select the dimension of the cube that will provide the source data for your mining structure.</span></span>  
  
## <a name="choosing-a-dimension"></a><span data-ttu-id="e218e-110">Scelta di una dimensione</span><span class="sxs-lookup"><span data-stu-id="e218e-110">Choosing a Dimension</span></span>  
 <span data-ttu-id="e218e-111">Poiché è possibile selezionare una sola dimensione da utilizzare nel modello, è importante comprendere la struttura del cubo e selezionare la dimensione che fornisce le informazioni più appropriate per il modello.</span><span class="sxs-lookup"><span data-stu-id="e218e-111">Because you can select only one dimension for use in your model, it is important that you understand the cube structure and select the dimension that provides the best information for your model.</span></span> <span data-ttu-id="e218e-112">In caso di dubbi sulla dimensione da utilizzare, potrebbe essere utile esplorare il cubo ed esaminare i campi e i dati delle dimensioni utilizzando Progettazione dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e218e-112">If you are not sure which dimension to use, it might be helpful to browse the cube and review the fields and the data in them by using Dimension Designer.</span></span> <span data-ttu-id="e218e-113">Per altre informazioni, vedere [Esplorare i dati di una dimensione in Progettazione dimensioni](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span><span class="sxs-lookup"><span data-stu-id="e218e-113">For more information, see [Browse Dimension Data in Dimension Designer](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span></span>  
  
 <span data-ttu-id="e218e-114">Se non si ha familiarità con le dimensioni in generale, vedere [Introduzione alle dimensioni &#40;Analysis Services - Dati multidimensionali&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e218e-114">If you are unfamiliar with dimensions in general, see [Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e218e-115">Per altre informazioni sul tipo di informazioni generalmente contenute in una singola dimensione, inclusi gli attributi e le misure che potrebbero essere utili per il data mining, vedere [Relazioni tra dimensioni](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="e218e-115">For more information about the type of information that is typically contained in a single dimension, including attributes and measures that might be useful for data mining, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
 <span data-ttu-id="e218e-116">Se la dimensione scelta non contiene tutti gli attributi correlati richiesti per la compilazione del modello di data mining, potrebbe essere necessario modificarla.</span><span class="sxs-lookup"><span data-stu-id="e218e-116">If the dimension that you choose does not contain all of the related attributes that you need to build the data mining model, you might need to modify the dimension.</span></span> <span data-ttu-id="e218e-117">Per altre informazioni, vedere [Definire le dimensioni del database](multidimensional-models/define-database-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="e218e-117">For more information, see [Define Database Dimensions](multidimensional-models/define-database-dimensions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e218e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e218e-118">See Also</span></span>  
 <span data-ttu-id="e218e-119">[Guida sensibile al contesto della creazione guidata modello di data mining &#40;Analysis Services-&#41;di data mining](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e218e-119">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="e218e-120">[Creazione della struttura di data mining &#40;creazione guidata modello di data mining&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e218e-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="e218e-121">Selezionare la chiave del case &#40;creazione guidata modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="e218e-121">Select the Case Key &#40;Data Mining Wizard&#41;</span></span>](select-the-case-key-data-mining-wizard.md)  
  
  
