---
title: Creazione di una struttura del modello di data mining Sequence Clustering (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9339227-6c2e-4c4b-8be2-8c1960bc4a8d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 37d0a1738a758a9d8c4fd6b80310037937a9803f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626998"
---
# <a name="creating-a-sequence-clustering-mining-model-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="7e352-102">Creazione di una struttura del modello di data mining Sequence Clustering (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="7e352-102">Creating a Sequence Clustering Mining Model Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="7e352-103">Il primo passaggio nella creazione di un modello di data mining Sequence Clustering consiste nell'utilizzo della Creazione guidata modello di data mining per la creazione di una nuova struttura di data mining e di un modello di data mining sulla base dell'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering.</span><span class="sxs-lookup"><span data-stu-id="7e352-103">The first step in creating a sequence clustering mining model is to use the Data Mining Wizard to create a new mining structure and a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span>  
  
 <span data-ttu-id="7e352-104">Verrà utilizzata la stessa vista origine dati impiegata per l'analisi degli acquisti, ma si aggiungerà una colonna che contiene l'identificatore `sequence`.</span><span class="sxs-lookup"><span data-stu-id="7e352-104">You will use the same data source view that you used for the market basket analysis, but you will add a column that contains the `sequence` identifier.</span></span> <span data-ttu-id="7e352-105">In questo scenario la sequenza indica l'ordine in cui il cliente ha incluso gli articoli tra gli acquisti.</span><span class="sxs-lookup"><span data-stu-id="7e352-105">In this scenario, the sequence means the order in which the customer added items to the shopping basket.</span></span>  
  
 <span data-ttu-id="7e352-106">Verranno anche aggiunte alcune colonne utilizzate in uno dei modelli per raggruppare i clienti in base ai dati demografici.</span><span class="sxs-lookup"><span data-stu-id="7e352-106">You will also add some columns that are used in one of the models to group customers by demographics.</span></span>  
  
### <a name="to-create-a-sequence-clustering-structure-and-model"></a><span data-ttu-id="7e352-107">Per creare una struttura e un modello di data mining Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="7e352-107">To create a sequence clustering structure and model</span></span>  
  
1.  <span data-ttu-id="7e352-108">In Esplora soluzioni in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] fare clic con il pulsante destro del mouse su **strutture di data mining** e scegliere **nuova struttura di data mining**</span><span class="sxs-lookup"><span data-stu-id="7e352-108">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="7e352-109">Nella pagina iniziale **Creazione guidata modello di data mining** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e352-109">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="7e352-110">Nella pagina **Selezione metodo di definizione** verificare che sia selezionato **da database relazionale o data warehouse esistente** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e352-110">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="7e352-111">Nella pagina **Crea la struttura di data mining** verificare che sia selezionata l'opzione **crea struttura di data mining con un modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="7e352-111">On the **Create the Data Mining Structure** page, verify that the option **Create mining structure with a mining model** is selected.</span></span> <span data-ttu-id="7e352-112">Quindi, fare clic sull'elenco a discesa dell'opzione **che data mining tecnica si desidera utilizzare**e selezionare **Microsoft Sequence Clustering**.</span><span class="sxs-lookup"><span data-stu-id="7e352-112">Next, click the dropdown list for the option, **Which data mining technique do you want to use?**, and select **Microsoft Sequence Clustering**.</span></span> <span data-ttu-id="7e352-113">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e352-113">Click **Next**.</span></span>  
  
     <span data-ttu-id="7e352-114">Verrà visualizzata la pagina **Selezione vista origine dati** .</span><span class="sxs-lookup"><span data-stu-id="7e352-114">The **Select Data Source View** page appears.</span></span> <span data-ttu-id="7e352-115">In **viste origine dati disponibili**selezionare `Orders` .</span><span class="sxs-lookup"><span data-stu-id="7e352-115">Under **Available data source views**, select `Orders`.</span></span>  
  
     <span data-ttu-id="7e352-116">Orders è la stessa vista origine dati utilizzata per lo scenario di analisi degli acquisti.</span><span class="sxs-lookup"><span data-stu-id="7e352-116">Orders is the same data source view that you used for the market basket scenario.</span></span> <span data-ttu-id="7e352-117">Se questa vista origine dati non è stata creata, vedere [aggiunta di una vista origine dati con tabelle nidificate &#40;esercitazione intermedia sul Data Mining&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="7e352-117">If you have not created this data source view, see [Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="7e352-118">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e352-118">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7e352-119">Nella pagina **impostazione tipi di tabelle** selezionare la casella di controllo **case** accanto alla tabella **vAssocSeqOrders** , quindi selezionare la casella di controllo **nidificata** accanto alla tabella **vAssocSeqLineItems** .</span><span class="sxs-lookup"><span data-stu-id="7e352-119">On the **Specify Table Types** page, select the **Case** check box next to the **vAssocSeqOrders** table, and select the **Nested** check box next to the **vAssocSeqLineItems** table.</span></span> <span data-ttu-id="7e352-120">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e352-120">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e352-121">Se si verifica un errore quando si selezionano le caselle di controllo **case** o **nidificate** , è possibile che il join nella vista origine dati non sia corretto.</span><span class="sxs-lookup"><span data-stu-id="7e352-121">If an error occurs when you select the **Case** or **Nested** check boxes, it may be that the join in the data source view is not correct.</span></span> <span data-ttu-id="7e352-122">La tabella nidificata, **vAssocSeqLineItems**, deve essere connessa alla tabella del case, **vAssocSeqOrders,** da un join molti-a-uno.</span><span class="sxs-lookup"><span data-stu-id="7e352-122">The nested table, **vAssocSeqLineItems**, must be connected to the case table, **vAssocSeqOrders,** by a many-to-one join.</span></span> <span data-ttu-id="7e352-123">È possibile modificare la relazione facendo clic con il pulsante destro del mouse sulla linea di join e invertendo la direzione del join.</span><span class="sxs-lookup"><span data-stu-id="7e352-123">You can edit the relationship by right-clicking on the join line and then reversing the direction of the join.</span></span> <span data-ttu-id="7e352-124">Per ulteriori informazioni, vedere finestra di [dialogo Crea relazione o modifica relazione &#40;Analysis Services-&#41;dati multidimensionali ](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="7e352-124">For more information, see [Create or Edit Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
7.  <span data-ttu-id="7e352-125">Nella pagina **impostazione dati di training** scegliere le colonne da utilizzare nel modello selezionando una casella di controllo come segue:</span><span class="sxs-lookup"><span data-stu-id="7e352-125">On the **Specify the Training Data** page, choose the columns for use in the model by selecting a check box as follows:</span></span>  
  
    -   <span data-ttu-id="7e352-126">**IncomeGroup** Selezionare la casella di controllo **input** .</span><span class="sxs-lookup"><span data-stu-id="7e352-126">**IncomeGroup** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="7e352-127">Questa colonna contiene interessanti informazioni sui clienti che è possibile utilizzare per il clustering.</span><span class="sxs-lookup"><span data-stu-id="7e352-127">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="7e352-128">Verranno utilizzate nel primo modello e ignorate nel secondo modello.</span><span class="sxs-lookup"><span data-stu-id="7e352-128">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="7e352-129">**OrderNumber** Selezionare la `Key` casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="7e352-129">**OrderNumber** Select the `Key` check box.</span></span>  
  
         <span data-ttu-id="7e352-130">Questo campo sarà utilizzato come identificatore per la tabella del case o `Key`.</span><span class="sxs-lookup"><span data-stu-id="7e352-130">This field will be used as the identifier for the case table, or `Key`.</span></span> <span data-ttu-id="7e352-131">In generale, è consigliabile non utilizzare mai il campo chiave della tabella del case come input, perché la chiave contiene valori univoci che non sono utili per il clustering.</span><span class="sxs-lookup"><span data-stu-id="7e352-131">In general, you should never use the key field of the case table as an input, because the key contains unique values that are not useful for clustering.</span></span>  
  
    -   <span data-ttu-id="7e352-132">**Area geografica** Selezionare la casella di controllo **input** .</span><span class="sxs-lookup"><span data-stu-id="7e352-132">**Region** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="7e352-133">Questa colonna contiene interessanti informazioni sui clienti che è possibile utilizzare per il clustering.</span><span class="sxs-lookup"><span data-stu-id="7e352-133">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="7e352-134">Verranno utilizzate nel primo modello e ignorate nel secondo modello.</span><span class="sxs-lookup"><span data-stu-id="7e352-134">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="7e352-135">**LineNumber** Selezionare le `Key` caselle di controllo e **input** .</span><span class="sxs-lookup"><span data-stu-id="7e352-135">**LineNumber** Select the `Key` and **Input** check boxes.</span></span>  
  
         <span data-ttu-id="7e352-136">Il campo **lineNumber** verrà utilizzato come identificatore per la tabella nidificata o `Sequence Key` .</span><span class="sxs-lookup"><span data-stu-id="7e352-136">The **LineNumber** field will be used as the identifier for the nested table, or `Sequence Key`.</span></span> <span data-ttu-id="7e352-137">La chiave di una tabella nidificata deve essere sempre utilizzata per l'input.</span><span class="sxs-lookup"><span data-stu-id="7e352-137">The key for a nested table must always be used for input.</span></span>  
  
    -   <span data-ttu-id="7e352-138">**Modello** di Selezionare le caselle di controllo **input** e **stimabile** .</span><span class="sxs-lookup"><span data-stu-id="7e352-138">**Model** Select the **Input** and **Predictable** check boxes.</span></span>  
  
     <span data-ttu-id="7e352-139">Verificare che le selezioni siano corrette, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e352-139">Verify that the selections are correct, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="7e352-140">Nella pagina **impostazione tipo di contenuto e dati delle colonne** verificare che la griglia contenga le colonne, i tipi di contenuto e i tipi di dati indicati nella tabella seguente, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e352-140">On the **Specify Columns' Content and Data Type** page, verify that the grid contains the columns, content types, and data types shown in the following table, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="7e352-141">Tabelle/Colonne</span><span class="sxs-lookup"><span data-stu-id="7e352-141">Tables/Columns</span></span>|<span data-ttu-id="7e352-142">Tipo di contenuto</span><span class="sxs-lookup"><span data-stu-id="7e352-142">Content Type</span></span>|<span data-ttu-id="7e352-143">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7e352-143">Data Type</span></span>|  
    |---------------------|------------------|---------------|  
    |<span data-ttu-id="7e352-144">IncomeGroup</span><span class="sxs-lookup"><span data-stu-id="7e352-144">IncomeGroup</span></span>|<span data-ttu-id="7e352-145">Discrete</span><span class="sxs-lookup"><span data-stu-id="7e352-145">Discrete</span></span>|<span data-ttu-id="7e352-146">Testo</span><span class="sxs-lookup"><span data-stu-id="7e352-146">Text</span></span>|  
    |<span data-ttu-id="7e352-147">OrderNumber</span><span class="sxs-lookup"><span data-stu-id="7e352-147">OrderNumber</span></span>|<span data-ttu-id="7e352-148">Chiave</span><span class="sxs-lookup"><span data-stu-id="7e352-148">Key</span></span>|<span data-ttu-id="7e352-149">Testo</span><span class="sxs-lookup"><span data-stu-id="7e352-149">Text</span></span>|  
    |<span data-ttu-id="7e352-150">Region</span><span class="sxs-lookup"><span data-stu-id="7e352-150">Region</span></span>|<span data-ttu-id="7e352-151">Discrete</span><span class="sxs-lookup"><span data-stu-id="7e352-151">Discrete</span></span>|<span data-ttu-id="7e352-152">Testo</span><span class="sxs-lookup"><span data-stu-id="7e352-152">Text</span></span>|  
    |<span data-ttu-id="7e352-153">vAssocSeqLineItems</span><span class="sxs-lookup"><span data-stu-id="7e352-153">vAssocSeqLineItems</span></span>|||  
    |<span data-ttu-id="7e352-154">Line Number</span><span class="sxs-lookup"><span data-stu-id="7e352-154">Line Number</span></span>|<span data-ttu-id="7e352-155">Key Sequence</span><span class="sxs-lookup"><span data-stu-id="7e352-155">Key Sequence</span></span>|<span data-ttu-id="7e352-156">long</span><span class="sxs-lookup"><span data-stu-id="7e352-156">Long</span></span>|  
    |<span data-ttu-id="7e352-157">Modello</span><span class="sxs-lookup"><span data-stu-id="7e352-157">Model</span></span>|<span data-ttu-id="7e352-158">Discrete</span><span class="sxs-lookup"><span data-stu-id="7e352-158">Discrete</span></span>|<span data-ttu-id="7e352-159">Testo</span><span class="sxs-lookup"><span data-stu-id="7e352-159">Text</span></span>|  
  
9. <span data-ttu-id="7e352-160">Nella pagina **Crea set di testing** modificare la **percentuale di dati per il testing** su 20, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e352-160">On the **Create Testing Set** page, change the **Percentage of data for testing** to 20, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="7e352-161">Nella pagina **Completamento procedura guidata** Digitare per il **nome della struttura di data mining** `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="7e352-161">On the **Completing the Wizard** page, for the **Mining structure name**, type `Sequence Clustering with Region`.</span></span>  
  
11. <span data-ttu-id="7e352-162">Per il **nome del modello di data mining**, digitare `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="7e352-162">For the **Mining model name**, type `Sequence Clustering with Region`.</span></span>  
  
12. <span data-ttu-id="7e352-163">Selezionare la casella **Consenti drill-through** , quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="7e352-163">Check the **Allow drill through** box, and then click **Finish**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7e352-164">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="7e352-164">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7e352-165">Elaborazione del modello Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="7e352-165">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="7e352-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e352-166">See Also</span></span>  
 <span data-ttu-id="7e352-167">[Progettazione modelli di data mining](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7e352-167">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="7e352-168">Algoritmo Microsoft Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="7e352-168">Microsoft Sequence Clustering Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)  
  
  
