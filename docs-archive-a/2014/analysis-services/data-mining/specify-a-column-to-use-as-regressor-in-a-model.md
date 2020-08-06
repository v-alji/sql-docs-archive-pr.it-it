---
title: Specificare una colonna da utilizzare come regressore in un modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8e0cb8e-302a-4166-9ed0-e2d9e2919b0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 86899d3793985b5e3c07618360d7b6a540935a54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623590"
---
# <a name="specify-a-column-to-use-as-regressor-in-a-model"></a><span data-ttu-id="769b8-102">Specificare una colonna da utilizzare come regressore in un modello</span><span class="sxs-lookup"><span data-stu-id="769b8-102">Specify a Column to Use as Regressor in a Model</span></span>
  <span data-ttu-id="769b8-103">Un modello di regressione lineare rappresenta il valore dell'attributo stimabile come il risultato di una formula che consente di combinare gli input in modo che i dati si adattino il più possibile a una retta di regressione stimata.</span><span class="sxs-lookup"><span data-stu-id="769b8-103">A linear regression model represents the value of the predictable attribute as the result of a formula that combines the inputs in such a way that the data is fitted as a closely as possible to an estimated regression line.</span></span> <span data-ttu-id="769b8-104">L'algoritmo accetta come input sono valori numerici e rileva automaticamente gli input che si adattano meglio.</span><span class="sxs-lookup"><span data-stu-id="769b8-104">The algorithm accepts only numeric values as inputs, and automatically detects the inputs that provide the best fit.</span></span>  
  
 <span data-ttu-id="769b8-105">Per specificare che una colonna può essere inclusa come regressore, è possibile tuttavia aggiungere il parametro FORCE_REGRESSOR al modello e indicare i regressori da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="769b8-105">However, you can specify that a column be included as a regressor by adding the FORCE_REGRESSOR parameter to the model and specifying the regressors to use.</span></span> <span data-ttu-id="769b8-106">Questa operazione può essere eseguita nei casi in cui l'attributo è significativo anche se l'effetto è insufficiente per essere rilevato dal modello o quando si desidera garantire che l'attributo venga incluso nella formula.</span><span class="sxs-lookup"><span data-stu-id="769b8-106">You might want to do this in cases where the attribute has meaning even if the effect is too small to be detected by the model, or when you want to ensure that the attribute is included in the formula.</span></span>  
  
 <span data-ttu-id="769b8-107">Di seguito viene descritto come creare un modello di regressione lineare semplice usando gli stessi dati di esempio usati per l' [esercitazione sulle reti neurali](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="769b8-107">The following procedure describes how to create a simple linear regression model, using the same sample data that is used for the [neural networks tutorial](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="769b8-108">Sebbene non sia necessariamente affidabile, il modello dimostra i concetti di base per utilizzare Progettazione modelli di data mining per personalizzare un modello di regressione lineare.</span><span class="sxs-lookup"><span data-stu-id="769b8-108">The model is not necessarily robust, but demonstrates how to use the Data Mining Designer to customize a linear regression model.</span></span>  
  
### <a name="how-to-create-a-simple-linear-regression-model"></a><span data-ttu-id="769b8-109">Come creare un semplice modello di regressione lineare</span><span class="sxs-lookup"><span data-stu-id="769b8-109">How to create a simple linear regression model</span></span>  
  
1.  <span data-ttu-id="769b8-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Esplora soluzioni **di**espandere **Strutture di data mining**.</span><span class="sxs-lookup"><span data-stu-id="769b8-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, expand **Mining Structures**.</span></span>  
  
2.  <span data-ttu-id="769b8-111">Fare doppio clic su Call Center.dmm per aprirlo nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="769b8-111">Double-click Call Center.dmm to open it in the designer.</span></span>  
  
3.  <span data-ttu-id="769b8-112">Scegliere **Nuovo modello di data mining** dal menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="769b8-112">From the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="769b8-113">Selezionare **Microsoft Linear Regression**come algoritmo.</span><span class="sxs-lookup"><span data-stu-id="769b8-113">For the algorithm, select **Microsoft Linear Regression**.</span></span> <span data-ttu-id="769b8-114">e digitare **Regressione Call Center**come nome.</span><span class="sxs-lookup"><span data-stu-id="769b8-114">For the name, type **Call Center Regression**.</span></span>  
  
5.  <span data-ttu-id="769b8-115">Nella scheda **Modelli di data mining** modificare l'uso delle colonne come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="769b8-115">In the **Mining Models** tab, change the column usage as follows.</span></span> <span data-ttu-id="769b8-116">È necessario impostare su **Ignora**tutte le colonne non presenti nell'elenco seguente, se tale impostazione non è già specificata.</span><span class="sxs-lookup"><span data-stu-id="769b8-116">All columns not in the following list should be set to **Ignore**, if they are not already.</span></span>  
  
     <span data-ttu-id="769b8-117">FactCallCenterID**Key**</span><span class="sxs-lookup"><span data-stu-id="769b8-117">FactCallCenterID**Key**</span></span>  
  
     <span data-ttu-id="769b8-118">ServiceGrade**PredictOnly**</span><span class="sxs-lookup"><span data-stu-id="769b8-118">ServiceGrade**PredictOnly**</span></span>  
  
     <span data-ttu-id="769b8-119">Operatori totali**Input**</span><span class="sxs-lookup"><span data-stu-id="769b8-119">Total Operators**Input**</span></span>  
  
     <span data-ttu-id="769b8-120">AverageTimePerIssue**Input**</span><span class="sxs-lookup"><span data-stu-id="769b8-120">AverageTimePerIssue**Input**</span></span>  
  
6.  <span data-ttu-id="769b8-121">Scegliere l'opzione **Set Model Parameters** (Imposta parametri modello) dal menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="769b8-121">From the **Mining Model** menu, select **Set Model Parameters**.</span></span>  
  
7.  <span data-ttu-id="769b8-122">Per il parametro FORCE_REGRESSOR, nella colonna **Valore** digitare i nomi di colonna racchiusi tra parentesi quadre e separati da una virgola come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="769b8-122">For the parameter, FORCE_REGRESSOR, in the **Value** column, type the column names enclosed in brackets and separated by a comma, as follows:</span></span>  
  
    ```  
    [Average Time Per Issue],[Total Operators]  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="769b8-123">Le colonne che rappresentano i regressori migliori verranno rilevate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="769b8-123">The algorithm will automatically detect which columns are the best regressors.</span></span> <span data-ttu-id="769b8-124">È necessario applicare i regressori solo quando si desidera garantire che una colonna venga inclusa nella formula finale.</span><span class="sxs-lookup"><span data-stu-id="769b8-124">You only need to force regressors when you want to ensure that a column is included in the final formula.</span></span>  
  
8.  <span data-ttu-id="769b8-125">Scegliere **Elabora modello** nel menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="769b8-125">From the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="769b8-126">Nel visualizzatore il modello è rappresentato da un nodo singolo che contiene la formula di regressione.</span><span class="sxs-lookup"><span data-stu-id="769b8-126">In the viewer, the model is represented a single node containing the regression formula.</span></span> <span data-ttu-id="769b8-127">È possibile visualizzare la formula in **Legenda data mining**oppure è possibile usare le query per estrarre i coefficienti per la formula.</span><span class="sxs-lookup"><span data-stu-id="769b8-127">You can view the formula in the **Mining Legend**, or you can extract the coefficients for the formula by using queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769b8-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="769b8-128">See Also</span></span>  
 <span data-ttu-id="769b8-129">[Algoritmo Microsoft Linear regressione](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="769b8-129">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="769b8-130">[Query di data mining](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="769b8-130">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="769b8-131">[Riferimento tecnico per l'algoritmo Microsoft Linear regressione](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="769b8-131">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="769b8-132">Contenuto dei modelli di data mining per i modelli di regressione lineare &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="769b8-132">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
