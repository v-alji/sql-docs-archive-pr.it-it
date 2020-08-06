---
title: Aggiunta di una vista origine dati con tabelle nidificate (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a14cd7f1-7a10-4ec6-af6a-f5f0676a0308
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: da1a9bff093e0b59e9d1166554d95bcf61aded08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720549"
---
# <a name="adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial"></a><span data-ttu-id="62cfc-102">Aggiunta di una vista origine dati con tabelle nidificate (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="62cfc-102">Adding a Data Source View with Nested Tables (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="62cfc-103">Per creare un modello di analisi degli acquisti, è necessario utilizzare una vista origine dati che supporti dati associativi.</span><span class="sxs-lookup"><span data-stu-id="62cfc-103">To create a market basket model, you must use a data source view that supports associative data.</span></span> <span data-ttu-id="62cfc-104">Questa vista origine dati verrà utilizzata anche per lo scenario di clustering delle sequenze.</span><span class="sxs-lookup"><span data-stu-id="62cfc-104">This data source view will also be used for the sequence clustering scenario.</span></span>  
  
 <span data-ttu-id="62cfc-105">Questa vista origine dati è diversa da altre che potrebbero essere state elaborate perché contiene una *tabella nidificata*.</span><span class="sxs-lookup"><span data-stu-id="62cfc-105">This data source view is different from others that you may have worked with because it contains a *nested table*.</span></span> <span data-ttu-id="62cfc-106">Una *tabella nidificata* è una tabella che contiene più righe di informazioni su una singola riga della tabella del case.</span><span class="sxs-lookup"><span data-stu-id="62cfc-106">A *nested table* is a table that contains multiple rows of information about a single row in the case table.</span></span> <span data-ttu-id="62cfc-107">Se ad esempio il modello analizza il comportamento di acquisto dei clienti, in genere si utilizza una tabella che dispone di una riga univoca per ogni cliente come tabella del case.</span><span class="sxs-lookup"><span data-stu-id="62cfc-107">For example, if your model analyzes the purchasing behavior of customers, you would typically use a table that has a unique row for each customer as the case table.</span></span> <span data-ttu-id="62cfc-108">Ogni cliente potrebbe tuttavia fare più acquisti, pertanto potrebbe essere necessario analizzare la sequenza di prodotti che vengono frequentemente acquistati insieme.</span><span class="sxs-lookup"><span data-stu-id="62cfc-108">However, each customer might make multiple purchases, and you might want to analyze the sequence of purchases, or products that are frequently purchased together.</span></span> <span data-ttu-id="62cfc-109">Per rappresentare in modo logico questi acquisti nel modello, è necessario aggiungere un'altra tabella alla vista origine dati che elenca gli acquisti per ogni cliente.</span><span class="sxs-lookup"><span data-stu-id="62cfc-109">To logically represent these purchases in your model, you add another table to the data source view that lists the purchases for each customer.</span></span>  
  
 <span data-ttu-id="62cfc-110">La tabella degli acquisti nidificata è correlata alla tabella dei clienti con una relazione molti-a-uno.</span><span class="sxs-lookup"><span data-stu-id="62cfc-110">This nested purchases table is related to the customer table by a many-to-one relationship.</span></span> <span data-ttu-id="62cfc-111">La tabella nidificata potrebbe contenere molte righe per ogni cliente, ognuna delle quali contiene un solo prodotto acquistato, con informazioni aggiuntive sull'ordine tramite il quale sono stati effettuati gli acquisti, il prezzo al momento dell'ordine o eventuali promozioni applicate.</span><span class="sxs-lookup"><span data-stu-id="62cfc-111">The nested table might contain many rows for each customer, each row containing a single product that was purchased, perhaps with additional information about the order that the purchases were made, the price at the time of the order, or any promotions that applied.</span></span> <span data-ttu-id="62cfc-112">È possibile utilizzare le informazioni nella tabella nidificata come input per il modello o come attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="62cfc-112">You can use the information in the nested table as inputs to the model, or as the predictable attribute.</span></span>  
  
 <span data-ttu-id="62cfc-113">In questa lezione verranno effettuate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62cfc-113">In this lesson, you do the following tasks:</span></span>  
  
-   <span data-ttu-id="62cfc-114">Si aggiunge una vista origine dati all' [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] origine dati.</span><span class="sxs-lookup"><span data-stu-id="62cfc-114">You add a data source view to the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source.</span></span>  
  
-   <span data-ttu-id="62cfc-115">Si aggiungeranno il case e le tabelle nidificate alla vista aggiunta.</span><span class="sxs-lookup"><span data-stu-id="62cfc-115">You add the case and nested tables to this view.</span></span>  
  
-   <span data-ttu-id="62cfc-116">Si specificherà la relazione molti-a-uno tra il case e la tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="62cfc-116">You specify the many-to-one relationship between the case and nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62cfc-117">.</span><span class="sxs-lookup"><span data-stu-id="62cfc-117">.</span></span> <span data-ttu-id="62cfc-118">È importante attenersi con scrupolo alla procedura descritta per specificare correttamente la relazione tra la tabella del case e la tabella nidificata ed evitare errori quando si elabora il modello.</span><span class="sxs-lookup"><span data-stu-id="62cfc-118">It is important that you follow the described procedure exactly, to correctly specify the relationship between the case table and the nested table and to avoid errors when you process the model.</span></span>  
  
-   <span data-ttu-id="62cfc-119">Si definirà in che modo vengono utilizzate le colonne di dati nel modello.</span><span class="sxs-lookup"><span data-stu-id="62cfc-119">You define how the columns of data are used in the model.</span></span>  
  
 <span data-ttu-id="62cfc-120">Per ulteriori informazioni sull'utilizzo delle tabelle case e nidificate e su come scegliere una chiave di tabella nidificata, vedere [tabelle nidificate &#40;Analysis Services-&#41;di data mining ](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="62cfc-120">For more information about working with case and nested tables, and how to choose a nested table key, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="62cfc-121">Per aggiungere una vista origine dati</span><span class="sxs-lookup"><span data-stu-id="62cfc-121">To add a data source view</span></span>  
  
1.  <span data-ttu-id="62cfc-122">In Esplora soluzioni fare clic con il pulsante destro del mouse su **viste origine dati**, quindi scegliere **nuova vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="62cfc-122">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
     <span data-ttu-id="62cfc-123">Verrà avviata Creazione guidata vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="62cfc-123">The Data Source View Wizard opens.</span></span>  
  
2.  <span data-ttu-id="62cfc-124">Nella pagina **Creazione guidata vista origine dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="62cfc-124">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="62cfc-125">Nella pagina **Selezione origine dati** , in **origini dati relazionali**, selezionare l' [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] origine dati creata nell'esercitazione di base sul data mining.</span><span class="sxs-lookup"><span data-stu-id="62cfc-125">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source that you created in the Basic Data Mining Tutorial.</span></span> <span data-ttu-id="62cfc-126">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="62cfc-126">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="62cfc-127">Nella pagina **Selezione tabelle e viste** selezionare le tabelle seguenti, quindi fare clic sulla freccia destra per includerle nella nuova vista origine dati:</span><span class="sxs-lookup"><span data-stu-id="62cfc-127">On the **Select Tables and Views** page, select the following tables, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   `vAssocSeqOrders`  
  
    -   `vAssocSeqLineItems`  
  
5.  <span data-ttu-id="62cfc-128">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="62cfc-128">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="62cfc-129">Per impostazione predefinita, nella pagina **Completamento procedura guidata** la vista origine dati è denominata [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62cfc-129">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="62cfc-130">Modificare il nome in `Orders` , quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="62cfc-130">Change the name to `Orders`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="62cfc-131">Verrà aperto Progettazione vista origine dati e `Orders` verrà visualizzata la vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="62cfc-131">Data Source View Designer opens and the `Orders` data source view appears.</span></span>  
  
### <a name="to-create-a-relationship-between-tables"></a><span data-ttu-id="62cfc-132">Per creare una relazione tra le tabelle</span><span class="sxs-lookup"><span data-stu-id="62cfc-132">To create a relationship between tables</span></span>  
  
1.  <span data-ttu-id="62cfc-133">In Progettazione vista origine dati posizionare le due tabelle in modo che siano allineate orizzontalmente, con la tabella vAssocSeqLineItems sulla sinistra e la tabella vAssocSeqOrders sulla destra.</span><span class="sxs-lookup"><span data-stu-id="62cfc-133">In Data Source View Designer, position the two tables so that the tables are aligned horizontally, with the vAssocSeqLineItems table on the left side and the vAssocSeqOrders table on the right side.</span></span>  
  
2.  <span data-ttu-id="62cfc-134">Selezionare la colonna **OrderNumber** nella tabella vAssocSeqLineItems.</span><span class="sxs-lookup"><span data-stu-id="62cfc-134">Select the **OrderNumber** column in the vAssocSeqLineItems table.</span></span>  
  
3.  <span data-ttu-id="62cfc-135">Trascinare la colonna nella tabella vAssocSeqOrders e inserirla nella colonna **OrderNumber** .</span><span class="sxs-lookup"><span data-stu-id="62cfc-135">Drag the column to the vAssocSeqOrders table, and put it on the **OrderNumber** column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="62cfc-136">Assicurarsi di trascinare la colonna **OrderNumber** dalla tabella nidificata vAssocSeqLineItems, che rappresenta il lato molti del join, alla tabella del case vAssocSeqOrders, che rappresenta il lato uno del join.</span><span class="sxs-lookup"><span data-stu-id="62cfc-136">Make sure to drag the **OrderNumber** column from the vAssocSeqLineItems nested table, which represents the many side of the join, to the vAssocSeqOrders case table, which represents the one side of the join.</span></span>  
  
     <span data-ttu-id="62cfc-137">Esiste ora una nuova *relazione molti-a-uno* tra le tabelle VAssocSeqLineItems e vAssocSeqOrders.</span><span class="sxs-lookup"><span data-stu-id="62cfc-137">A new *many-to-one relationship* now exists between the vAssocSeqLineItems and vAssocSeqOrders tables.</span></span> <span data-ttu-id="62cfc-138">Se le tabelle sono state unite in join correttamente, la vista origine dati visualizzata sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="62cfc-138">If you have joined the tables correctly, the data source view should appear as follows:</span></span>  
  
     <span data-ttu-id="62cfc-139">![Join molti-a-uno previsto in una tabella del case e in una tabella nidificata](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "Join molti-a-uno previsto in una tabella del case e in una tabella nidificata")</span><span class="sxs-lookup"><span data-stu-id="62cfc-139">![expected many-to-one join on nested and case table](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "expected many-to-one join on nested and case table")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="62cfc-140">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="62cfc-140">Next Task in Lesson</span></span>  
 [<span data-ttu-id="62cfc-141">Creazione di una struttura e di un modello di Market basket &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="62cfc-141">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="62cfc-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62cfc-142">See Also</span></span>  
 <span data-ttu-id="62cfc-143">[Esercitazione intermedia sul data mining &#40;Analysis Services-&#41;di data mining](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="62cfc-143">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="62cfc-144">[Strutture di data mining &#40;Analysis Services-&#41;di data mining](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="62cfc-144">[Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="62cfc-145">Modelli di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="62cfc-145">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-models-analysis-services-data-mining.md)  
  
  
