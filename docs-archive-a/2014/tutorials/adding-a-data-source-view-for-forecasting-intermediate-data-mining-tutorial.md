---
title: Aggiunta di una vista origine dati per la previsione (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2665040a-1291-4064-ba01-f458637dda57
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9424988efa6a9856f4ef0d558992fc90ac303861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720544"
---
# <a name="adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial"></a><span data-ttu-id="2cb7a-102">Aggiunta di una vista origine dati per la previsione (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="2cb7a-102">Adding a Data Source View for Forecasting (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="2cb7a-103">In questa attività verrà aggiunta una vista origine dati da utilizzare per lo scenario di previsione.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-103">In this task, you add a data source view that will be used for the forecasting scenario.</span></span> <span data-ttu-id="2cb7a-104">I modelli di previsione richiedono che i dati contengano una colonna che può essere utilizzata per identificare gli intervalli di una serie temporale.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-104">A forecasting model requires that the data contains a column that can be used to identify steps in a time series.</span></span> <span data-ttu-id="2cb7a-105">Se si prevede di analizzare più serie di dati, è necessario che tutte le serie terminino alla stessa data o intervallo temporale.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-105">If you plan to analyze multiple series of data, all series must end on the same date or time step.</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="2cb7a-106">Per aggiungere una vista origine dati</span><span class="sxs-lookup"><span data-stu-id="2cb7a-106">To add a data source view</span></span>  
  
1.  <span data-ttu-id="2cb7a-107">In Esplora soluzioni fare clic con il pulsante destro del mouse su **viste origine dati**, quindi scegliere **nuova vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-107">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="2cb7a-108">Nella pagina **Creazione guidata vista origine dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-108">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="2cb7a-109">Nella pagina **Selezione origine dati** , in **origini dati relazionali**, selezionare l' [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] origine dati.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-109">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source.</span></span> <span data-ttu-id="2cb7a-110">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-110">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2cb7a-111">Se questa origine dati non è presente, è possibile trovare i passaggi per creare l'origine dati nell'esercitazione di [base sul data mining](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="2cb7a-111">If you do not have this data source, you can find the steps to create the data source in the [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
4.  <span data-ttu-id="2cb7a-112">Nella pagina **Selezione tabelle e viste** selezionare la tabella vTimeSeries (dbo), quindi fare clic sulla freccia destra per aggiungerla alla vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-112">On the **Select Tables and Views** page, select the table, vTimeSeries (dbo), and then click the right arrow to add it to the data source view.</span></span>  
  
5.  <span data-ttu-id="2cb7a-113">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="2cb7a-114">Per impostazione predefinita, nella pagina **Completamento procedura guidata** la vista origine dati è denominata [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb7a-114">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="2cb7a-115">Modificare il nome in **SalesByRegion**, quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-115">Change the name to **SalesByRegion**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="2cb7a-116">Verrà aperto Progettazione vista origine dati e verrà visualizzata la vista origine dati **SalesByRegion** .</span><span class="sxs-lookup"><span data-stu-id="2cb7a-116">Data Source View Designer opens and the **SalesByRegion** data source view appears.</span></span>  
  
## <a name="working-with-the-data-source-view"></a><span data-ttu-id="2cb7a-117">Utilizzo della vista origine dati</span><span class="sxs-lookup"><span data-stu-id="2cb7a-117">Working with the Data Source View</span></span>  
 <span data-ttu-id="2cb7a-118">Dopo aver creato la vista origine dati, è possibile esplorarne i dati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cb7a-118">After you have created the data source view, you can explore the data in the following ways:</span></span>  
  
-   <span data-ttu-id="2cb7a-119">Fare clic con il pulsante destro del mouse sulla tabella vTimeSeries nella finestra di progettazione e selezionare **Esplora dati** per aprire la tabella selezionata in una griglia.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-119">Right-click the table vTimeSeries in the designer, and select **Explore Data** to open the selected table in a grid.</span></span>  
  
-   <span data-ttu-id="2cb7a-120">Fare clic su **Opzioni di campionamento** , quindi utilizzare la finestra di dialogo **Opzioni di esplorazione dati** per modificare il metodo di campionamento.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-120">Click **Sampling options** and then use the **Data Exploration Options** dialog box to change the sampling method.</span></span> <span data-ttu-id="2cb7a-121">Fare clic su **Aggiorna** per caricare i dati nella tabella utilizzando le nuove impostazioni delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-121">Click **Refresh** to load data in the table using the new option settings.</span></span> <span data-ttu-id="2cb7a-122">Ad esempio, è possibile specificare il numero di righe da restituire nell'esempio o scegliere le prime n righe.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-122">For example, you could specify the number of rows to output in the sample, or choose the top n rows.</span></span>  
  
-   <span data-ttu-id="2cb7a-123">Fare clic con il pulsante destro del mouse sulla tabella vTimeSeries e selezionare **Proprietà** per assegnare un nuovo nome alla tabella.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-123">Right-click the table vTimeSeries and select **Properties** to assign a new name to the table.</span></span> <span data-ttu-id="2cb7a-124">È anche possibile selezionare singole colonne dalla vista origine dati e, successivamente, modificare le proprietà delle colonne.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-124">You can also select individual columns from the data source view, and the modify the column properties.</span></span>  
  
-   <span data-ttu-id="2cb7a-125">Fare clic in un punto qualsiasi dell'area di progettazione della vista origine dati per creare una nuova query e assegnarvi un nome, per creare relazioni tra tabelle o per modificare il layout dell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-125">Click anywhere in the data source view design area to create a new query and assign a name to it, to create relationships between tables, or to change the layout of the design area.</span></span>  
  
-   <span data-ttu-id="2cb7a-126">Fare clic con il pulsante destro del mouse su una tabella e scegliere **nuovo calcolo denominato** per creare colonne derivate, incluse le aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-126">Right-click a table and select **New Named Calculation** to create derived columns, including aggregations.</span></span> <span data-ttu-id="2cb7a-127">È inoltre possibile aggiungere nuove tabelle e viste dall'origine dati della vista corrente.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-127">You can also add new tables and views from the data source in this view.</span></span>  
  
 <span data-ttu-id="2cb7a-128">Nell'attività successiva verranno esplorati i dati della serie temporale e verrà determinata la colonna migliore da utilizzare come identificatore della serie temporale.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-128">In the next task, you will explore the time series data and determine the best column to use as the time series identifier.</span></span> <span data-ttu-id="2cb7a-129">Verrà anche descritto come gestire i gap nei dati della serie temporale.</span><span class="sxs-lookup"><span data-stu-id="2cb7a-129">You will also learn how to handle gaps in time series data.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2cb7a-130">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="2cb7a-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2cb7a-131">Informazioni sui requisiti per un modello Time Series &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="2cb7a-131">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2cb7a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cb7a-132">See Also</span></span>  
 [<span data-ttu-id="2cb7a-133">Algoritmo Microsoft Time Series</span><span class="sxs-lookup"><span data-stu-id="2cb7a-133">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
