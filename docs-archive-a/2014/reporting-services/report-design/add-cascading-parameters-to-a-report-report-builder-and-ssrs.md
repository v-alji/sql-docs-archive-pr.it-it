---
title: Aggiunta di parametri di propagazione a un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a22eec3-57a7-478e-b6fc-102a9dbe0591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5419d448b2fa9526224e1bccd80d5c195e2763d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712728"
---
# <a name="add-cascading-parameters-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="15957-102">Aggiunta di parametri di propagazione a un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="15957-102">Add Cascading Parameters to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="15957-103">I parametri di propagazione consentono di gestire quantità elevate di dati del report.</span><span class="sxs-lookup"><span data-stu-id="15957-103">Cascading parameters provide a way of managing large amounts of report data.</span></span> <span data-ttu-id="15957-104">È possibile definire un set di parametri correlati in modo che l'elenco dei valori di un parametro dipenda dal valore scelto per un altro parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-104">You can define a set of related parameters so that the list of values for one parameter depends on the value chosen in another parameter.</span></span> <span data-ttu-id="15957-105">Il primo parametro può essere ad esempio indipendente e presentare un elenco di categorie di prodotti.</span><span class="sxs-lookup"><span data-stu-id="15957-105">For example, the first parameter is independent and might present a list of product categories.</span></span> <span data-ttu-id="15957-106">Quando l'utente seleziona una categoria, il secondo parametro dipende dal valore del primo parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-106">When the user selects a category, the second parameter is dependent on the value of the first parameter.</span></span> <span data-ttu-id="15957-107">I relativi valori vengono aggiornati con un elenco di sottocategorie all'interno della categoria scelta.</span><span class="sxs-lookup"><span data-stu-id="15957-107">Its values are updated with a list of subcategories within the chosen category.</span></span> <span data-ttu-id="15957-108">Quando l'utente visualizza il report, per filtrarne i dati vengono utilizzati sia i valori dei parametri di categoria che di sottocategoria.</span><span class="sxs-lookup"><span data-stu-id="15957-108">When the user views the report, the values for both the category and subcategory parameters are used to filter report data.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="15957-109">Per creare parametri di propagazione, è innanzitutto necessario definire la query del set di dati e includere un parametro di query per ogni parametro di propagazione necessario.</span><span class="sxs-lookup"><span data-stu-id="15957-109">To create cascading parameters, you define the dataset query first and include a query parameter for each cascading parameter that you need.</span></span> <span data-ttu-id="15957-110">È inoltre necessario creare un set di dati distinto per ogni parametro di propagazione allo scopo di fornire i valori disponibili.</span><span class="sxs-lookup"><span data-stu-id="15957-110">You must also create a separate dataset for each cascading parameter to provide available values.</span></span> <span data-ttu-id="15957-111">Per altre informazioni, vedere [Aggiungere, modificare o eliminare valori disponibili per un parametro di report &#40;Generatore report e SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="15957-111">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
 <span data-ttu-id="15957-112">Per i parametri di propagazione l'ordine è importante in quanto la query del set di dati relativa a un parametro riportato più avanti nell'elenco include un riferimento a ciascun parametro riportato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="15957-112">Order is important for cascading parameters because the dataset query for a parameter later in the list includes a reference to each parameter that is earlier in the list.</span></span> <span data-ttu-id="15957-113">In fase di esecuzione l'ordine dei parametri nel riquadro dei dati del report determina l'ordine in cui le query del parametro vengono visualizzate nel report e quindi l'ordine in cui un utente sceglie ogni valore del parametro successivo.</span><span class="sxs-lookup"><span data-stu-id="15957-113">At run time, the order of the parameters in the Report Data pane determines the order in which the parameter queries appear in the report, and therefore, the order in which a user chooses each successive parameter value.</span></span>  
  
 <span data-ttu-id="15957-114">Per informazioni sulla creazione di parametri a cascata con più valori includendo la caratteristica Seleziona tutto, vedere [How to have a Select All Multi-Value Cascading Parameter](https://go.microsoft.com/fwlink/?LinkId=184757)(Come creare un parametro a cascata multivalore Seleziona tutto).</span><span class="sxs-lookup"><span data-stu-id="15957-114">For information about creating cascading parameters with multiple values and including the Select All feature, see [How to have a Select All Multivalue Cascading Parameter](https://go.microsoft.com/fwlink/?LinkId=184757).</span></span>  
  
### <a name="to-create-the-main-dataset-with-a-query-that-includes-multiple-related-parameters"></a><span data-ttu-id="15957-115">Per creare il set di dati principale con una query che include più parametri correlati</span><span class="sxs-lookup"><span data-stu-id="15957-115">To create the main dataset with a query that includes multiple related parameters</span></span>  
  
1.  <span data-ttu-id="15957-116">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse su un'origine dati e quindi scegliere **Aggiungi set di dati**.</span><span class="sxs-lookup"><span data-stu-id="15957-116">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="15957-117">Nella casella **Nome**digitare il nome del set di dati.</span><span class="sxs-lookup"><span data-stu-id="15957-117">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="15957-118">In **Origine dati**scegliere il nome dell'origine dati o fare clic su **Nuova** per crearne una.</span><span class="sxs-lookup"><span data-stu-id="15957-118">In **Data source**, choose the name of the data source or click **New** to create one.</span></span>  
  
4.  <span data-ttu-id="15957-119">In **Tipo di query**scegliere il tipo di query per l'origine dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="15957-119">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="15957-120">In questo argomento si presuppone che venga usato il tipo di query **Testo** .</span><span class="sxs-lookup"><span data-stu-id="15957-120">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="15957-121">In **Query**digitare la query da usare per recuperare i dati per questo report.</span><span class="sxs-lookup"><span data-stu-id="15957-121">In **Query**, type the query to use to retrieve data for this report.</span></span> <span data-ttu-id="15957-122">La query deve includere le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="15957-122">The query must include the following parts:</span></span>  
  
    1.  <span data-ttu-id="15957-123">Un elenco di campi dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="15957-123">A list of data source fields.</span></span> <span data-ttu-id="15957-124">In un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] , ad esempio, l'istruzione SELECT specifica un elenco di nomi di colonne del database di una determinata tabella o vista.</span><span class="sxs-lookup"><span data-stu-id="15957-124">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, the SELECT statement specifies a list of database column names from a given table or view.</span></span>  
  
    2.  <span data-ttu-id="15957-125">Un parametro della query per ogni parametro di propagazione.</span><span class="sxs-lookup"><span data-stu-id="15957-125">One query parameter for each cascading parameter.</span></span> <span data-ttu-id="15957-126">Un parametro della query limita i dati recuperati dall'origine dati specificando determinati valori da includere o escludere dalla query.</span><span class="sxs-lookup"><span data-stu-id="15957-126">A query parameter limits the data retrieved from the data source by specifying certain values to include or exclude from the query.</span></span> <span data-ttu-id="15957-127">In genere, i parametri della query si trovano in una clausola di restrizione nella query.</span><span class="sxs-lookup"><span data-stu-id="15957-127">Typically, query parameters occur in a restriction clause in the query.</span></span> <span data-ttu-id="15957-128">In un'istruzione SELECT [!INCLUDE[tsql](../../includes/tsql-md.md)] , ad esempio, i parametri della query si trovano nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="15957-128">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement, query parameters occur in the WHERE clause.</span></span> <span data-ttu-id="15957-129">Per altre informazioni, vedere "Filtraggio delle righe usando WHERE e HAVING" nella documentazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] inclusa nella [documentazione online di SQL Server](https://go.microsoft.com/fwlink/?linkid=120955)</span><span class="sxs-lookup"><span data-stu-id="15957-129">For more information, see "Filtering Rows by Using WHERE and HAVING" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
6.  <span data-ttu-id="15957-130">Fare clic su **Esegui** (**!**).</span><span class="sxs-lookup"><span data-stu-id="15957-130">Click **Run** (**!**).</span></span> <span data-ttu-id="15957-131">Dopo aver incluso i parametri della query e aver eseguito la query, verranno creati automaticamente i parametri del report corrispondenti ai parametri della query.</span><span class="sxs-lookup"><span data-stu-id="15957-131">After you include query parameters and then run the query, report parameters that correspond to the query parameters are automatically created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15957-132">L'ordine in cui si presentano i parametri della query quando si esegue per la prima volta una query determina anche l'ordine in cui vengono creati nel report.</span><span class="sxs-lookup"><span data-stu-id="15957-132">The order of query parameters the first time you run a query determines the order that they are created in the report.</span></span> <span data-ttu-id="15957-133">Per modificare l'ordine, vedere [Modificare l'ordine di un parametro del report &#40;Generatore report e SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="15957-133">To change the order, see [Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="15957-134">Procedere quindi alla creazione di un set di dati che specifichi i valori del parametro indipendente.</span><span class="sxs-lookup"><span data-stu-id="15957-134">Next, you will create a dataset that provides the values for the independent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-an-independent-parameter"></a><span data-ttu-id="15957-135">Per creare un set di dati in modo da specificare i valori di un parametro indipendente</span><span class="sxs-lookup"><span data-stu-id="15957-135">To create a dataset to provide values for an independent parameter</span></span>  
  
1.  <span data-ttu-id="15957-136">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse su un'origine dati e quindi scegliere **Aggiungi set di dati**.</span><span class="sxs-lookup"><span data-stu-id="15957-136">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="15957-137">Nella casella **Nome**digitare il nome del set di dati.</span><span class="sxs-lookup"><span data-stu-id="15957-137">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="15957-138">In **Origine dati**verificare che il nome sia quello dell'origine dati selezionata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="15957-138">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="15957-139">In **Tipo di query**scegliere il tipo di query per l'origine dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="15957-139">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="15957-140">In questo argomento si presuppone che venga usato il tipo di query **Testo** .</span><span class="sxs-lookup"><span data-stu-id="15957-140">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="15957-141">In **Query**digitare la query da usare per recuperare i valori per questo parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-141">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="15957-142">In genere le query per i parametri indipendenti non contengono parametri di query.</span><span class="sxs-lookup"><span data-stu-id="15957-142">Queries for independent parameters typically do not contain query parameters.</span></span> <span data-ttu-id="15957-143">Per creare, ad esempio, una query per un parametro che specifichi tutti i valori di categoria, è possibile usare un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="15957-143">For example, to create a query for a parameter that provides all category values, you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT <column name> FROM <table>  
    ```  
  
     <span data-ttu-id="15957-144">Il comando SELECT DISTINCT rimuove i valori duplicati dal set di risultati in modo che sia possibile ottenere tutti i valori univoci dalla colonna specificata nella tabella indicata.</span><span class="sxs-lookup"><span data-stu-id="15957-144">The SELECT DISTINCT command removes duplicate values from the result set so that you get each unique value from the specified column in the specified table.</span></span>  
  
     <span data-ttu-id="15957-145">Fare clic su **Esegui** (**!**).</span><span class="sxs-lookup"><span data-stu-id="15957-145">Click **Run** (**!**).</span></span> <span data-ttu-id="15957-146">Nel set di risultati sono riportati i valori disponibili per il primo parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-146">The result set shows the values that are available for this first parameter.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="15957-147">Impostare quindi le proprietà del primo parametro in modo da utilizzare questo set di dati per popolarne i valori disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="15957-147">Next, you will set the properties of the first parameter to use this dataset to populate its available values at run-time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="15957-148">Per impostare i valori disponibili per un parametro di report</span><span class="sxs-lookup"><span data-stu-id="15957-148">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="15957-149">Nella cartella Parametri del riquadro dei dati del report fare clic con il pulsante destro del mouse sul primo parametro e quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="15957-149">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="15957-150">Nella casella **Nome**verificare che il nome del parametro sia corretto.</span><span class="sxs-lookup"><span data-stu-id="15957-150">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="15957-151">Fare clic su **Valori disponibili**.</span><span class="sxs-lookup"><span data-stu-id="15957-151">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="15957-152">Fare clic su **Ottieni valori da una query**.</span><span class="sxs-lookup"><span data-stu-id="15957-152">Click **Get values from a query**.</span></span> <span data-ttu-id="15957-153">Verranno visualizzati tre campi.</span><span class="sxs-lookup"><span data-stu-id="15957-153">Three fields appear.</span></span>  
  
5.  <span data-ttu-id="15957-154">Nell'elenco a discesa di **Set di dati**fare clic sul nome del set di dati creato nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="15957-154">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="15957-155">Nel campo **Valore** fare clic sul nome del campo contenente il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-155">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="15957-156">Nel campo **Etichetta** fare clic sul nome del campo che fornisce l'etichetta del parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-156">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="15957-157">Procedere quindi alla creazione di un set di dati che specifichi i valori di un parametro dipendente.</span><span class="sxs-lookup"><span data-stu-id="15957-157">Next, you will create a dataset that provides the values for a dependent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-a-dependent-parameter"></a><span data-ttu-id="15957-158">Per creare un set di dati in modo da specificare i valori di un parametro dipendente</span><span class="sxs-lookup"><span data-stu-id="15957-158">To create a dataset to provide values for a dependent parameter</span></span>  
  
1.  <span data-ttu-id="15957-159">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse su un'origine dati e quindi scegliere **Aggiungi set di dati**.</span><span class="sxs-lookup"><span data-stu-id="15957-159">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="15957-160">Nella casella **Nome**digitare il nome del set di dati.</span><span class="sxs-lookup"><span data-stu-id="15957-160">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="15957-161">In **Origine dati**verificare che il nome sia quello dell'origine dati selezionata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="15957-161">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="15957-162">In **Tipo di query**scegliere il tipo di query per l'origine dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="15957-162">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="15957-163">In questo argomento si presuppone che venga usato il tipo di query **Testo** .</span><span class="sxs-lookup"><span data-stu-id="15957-163">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="15957-164">In **Query**digitare la query da usare per recuperare i valori per questo parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-164">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="15957-165">In genere le query per i parametri dipendenti includono parametri di query per ogni parametro dal quale dipende questo parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-165">Queries for dependent parameters typically include query parameters for each parameter that this parameter is dependent on.</span></span> <span data-ttu-id="15957-166">Per creare, ad esempio, una query per un parametro che specifichi tutti i valori di sottocategoria (parametro dipendente) per una categoria (parametro indipendente), è possibile usare un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="15957-166">For example, to create a query for a parameter that provides all subcategory (dependent parameter) values for a category (independent parameter), you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT Subcategory FROM <table>   
    WHERE (Category = @Category)  
    ```  
  
     <span data-ttu-id="15957-167">Nella clausola WHERE, Category è il nome di un campo di \<table> e @Category è un parametro di query.</span><span class="sxs-lookup"><span data-stu-id="15957-167">In the WHERE clause, Category is the name of a field from \<table> and @Category is a query parameter.</span></span> <span data-ttu-id="15957-168">Questa istruzione produce un elenco di sottocategorie per la categoria specificata in @Category.</span><span class="sxs-lookup"><span data-stu-id="15957-168">This statement produces a list of subcategories for the category specified in @Category.</span></span> <span data-ttu-id="15957-169">In fase di esecuzione tale valore verrà compilato con il valore selezionato dall'utente per il parametro del report con nome identico.</span><span class="sxs-lookup"><span data-stu-id="15957-169">At run time, this value will be filled in with the value that the user chooses for the report parameter that has the same name.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="15957-170">Impostare quindi le proprietà del secondo parametro in modo da utilizzare questo set di dati per popolarne i valori disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="15957-170">Next, you will set the properties of the second parameter to use this dataset to populate its available values at run time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="15957-171">Per impostare i valori disponibili per un parametro di report</span><span class="sxs-lookup"><span data-stu-id="15957-171">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="15957-172">Nella cartella Parametri del riquadro dei dati del report fare clic con il pulsante destro del mouse sul primo parametro e quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="15957-172">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="15957-173">Nella casella **Nome**verificare che il nome del parametro sia corretto.</span><span class="sxs-lookup"><span data-stu-id="15957-173">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="15957-174">Fare clic su **Valori disponibili**.</span><span class="sxs-lookup"><span data-stu-id="15957-174">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="15957-175">Fare clic su **Ottieni valori da una query**.</span><span class="sxs-lookup"><span data-stu-id="15957-175">Click **Get values from a query**.</span></span>  
  
5.  <span data-ttu-id="15957-176">Nell'elenco a discesa di **Set di dati**fare clic sul nome del set di dati creato nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="15957-176">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="15957-177">Nel campo **Valore** fare clic sul nome del campo contenente il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-177">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="15957-178">Nel campo **Etichetta** fare clic sul nome del campo che fornisce l'etichetta del parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-178">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-cascading-parameters"></a><span data-ttu-id="15957-179">Per verificare i parametri di propagazione</span><span class="sxs-lookup"><span data-stu-id="15957-179">To test the cascading parameters</span></span>  
  
1.  <span data-ttu-id="15957-180">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="15957-180">Click **Run**.</span></span>  
  
2.  <span data-ttu-id="15957-181">Scegliere un valore nell'elenco a discesa del primo parametro indipendente.</span><span class="sxs-lookup"><span data-stu-id="15957-181">From the drop-down list for the first, independent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="15957-182">Il componente Elaborazione report esegue la query del set di dati per il parametro successivo e passa il valore scelto per il primo parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-182">The report processor runs the dataset query for the next parameter and passes it the value you chose for the first parameter.</span></span> <span data-ttu-id="15957-183">L'elenco a discesa per il secondo parametro viene popolato con i valori disponibili basati sul valore del primo parametro.</span><span class="sxs-lookup"><span data-stu-id="15957-183">The drop-down list for the second parameter is populated with the available values based on the first parameter value.</span></span>  
  
3.  <span data-ttu-id="15957-184">Nell'elenco a discesa del secondo parametro dipendente scegliere un valore.</span><span class="sxs-lookup"><span data-stu-id="15957-184">From the drop-down list for the second, dependent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="15957-185">In seguito alla selezione dell'ultimo parametro il report non viene eseguito automaticamente in modo da consentire all'utente di modificare la scelta effettuata.</span><span class="sxs-lookup"><span data-stu-id="15957-185">The report does not run automatically after you choose the last parameter so that you can change your choice.</span></span>  
  
4.  <span data-ttu-id="15957-186">Fare clic su **Visualizza rapporto**.</span><span class="sxs-lookup"><span data-stu-id="15957-186">Click **View Report**.</span></span> <span data-ttu-id="15957-187">La visualizzazione del report verrà aggiornata in base ai parametri scelti.</span><span class="sxs-lookup"><span data-stu-id="15957-187">The report updates the display based on the parameters you have chosen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15957-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15957-188">See Also</span></span>  
 <span data-ttu-id="15957-189">[Aggiunta, modifica o eliminazione di un parametro di report &#40;Generatore report e SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="15957-189">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="15957-190">[Parametri del report &#40;Generatore report e Progettazione report&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="15957-190">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="15957-191">[Esercitazione: aggiungere un parametro al report &#40;Generatore report&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="15957-191">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="15957-192">[Esercitazioni &#40;Generatore report&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="15957-192">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="15957-193">[Aggiungere filtri del set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="15957-193">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="15957-194">Set di dati condivisi e incorporati del report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="15957-194">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
