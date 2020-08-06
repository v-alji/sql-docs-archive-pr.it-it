---
title: Compilare una query in Progettazione query relazionale (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 28b25861-f3b4-4c3e-a9b0-03d6e4cfea26
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 555d72c4d3bca8677d04fdc4160639f004d6bbe9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723512"
---
# <a name="build-a-query-in-the-relational-query-designer-report-builder-and-ssrs"></a><span data-ttu-id="95c53-102">Compilare una query in Progettazione query relazionale (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="95c53-102">Build a Query in the Relational Query Designer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="95c53-103">Una finestra Progettazione query consente di specificare i dati da recuperare da un'origine dati esterna per un set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="95c53-103">A query designer helps you specify which data to retrieve from an external data source for a report dataset.</span></span> <span data-ttu-id="95c53-104">Si utilizza la finestra Progettazione query quando si compila una query in una procedura guidata o si crea una query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="95c53-104">You use a query designer when you build a query in a wizard or create a dataset query.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="95c53-105">Un set di dati è basato su un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="95c53-105">A dataset is based on a data source.</span></span> <span data-ttu-id="95c53-106">Il tipo di origine dati e l'ambiente di creazione determinano la finestra Progettazione query da visualizzare quando si definisce la query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="95c53-106">The type of data source and the authoring environment determines which query designer opens when you define the dataset query.</span></span> <span data-ttu-id="95c53-107">Le funzionalità di Progettazione query variano in base all'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="95c53-107">Query designer features vary based on the underlying data source.</span></span> <span data-ttu-id="95c53-108">Per ulteriori informazioni sui livelli di dati, vedere [connessioni dati, origini dati e stringhe di connessione in Generatore report](../data-connections-data-sources-and-connection-strings-in-report-builder.md) o [connessioni dati, origini dati e stringhe di connessione in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="95c53-108">For more information about data layers, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) or [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span></span>  
  
 <span data-ttu-id="95c53-109">È possibile utilizzare una finestra Progettazione query per le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="95c53-109">You can use a query designer for the following tasks:</span></span>  
  
-   <span data-ttu-id="95c53-110">Esplorare i metadati per più schemi nell'origine dati esterna</span><span class="sxs-lookup"><span data-stu-id="95c53-110">Explore the metadata for multiple schemas on the external data source</span></span>  
  
-   <span data-ttu-id="95c53-111">Specificare i campi da recuperare per il set di dati</span><span class="sxs-lookup"><span data-stu-id="95c53-111">Specify fields to retrieve for the dataset</span></span>  
  
-   <span data-ttu-id="95c53-112">Specificare le relazioni tra due oggetti quali tabelle</span><span class="sxs-lookup"><span data-stu-id="95c53-112">Specify relationships between two objects such as tables</span></span>  
  
-   <span data-ttu-id="95c53-113">Specificare i filtri per limitare i dati prima che vengono recuperati come dati del report</span><span class="sxs-lookup"><span data-stu-id="95c53-113">Specify filters to restrict the data before it is retrieved as report data</span></span>  
  
-   <span data-ttu-id="95c53-114">Indicare se creare parametri</span><span class="sxs-lookup"><span data-stu-id="95c53-114">Indicate whether to create parameters</span></span>  
  
-   <span data-ttu-id="95c53-115">Specificare le aggregazioni per eseguire i calcoli nell'origine dati esterna</span><span class="sxs-lookup"><span data-stu-id="95c53-115">Specify aggregates to perform calculations on the external data source</span></span>  
  
 <span data-ttu-id="95c53-116">Dopo avere visualizzato una finestra Progettazione query, è possibile compilare una query nello stesso modo per un set di dati incorporato o un set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="95c53-116">After you open a query designer, you build a query in the same way for either an embedded dataset or a shared dataset.</span></span> <span data-ttu-id="95c53-117">Nelle procedure riportate di seguito viene utilizzata una query del set di dati incorporato.</span><span class="sxs-lookup"><span data-stu-id="95c53-117">The following procedures use an embedded dataset query.</span></span>  
  
 <span data-ttu-id="95c53-118">Per altre informazioni, vedere [Interfaccia utente di Progettazione query relazionale &#40;Generatore report&#41;](relational-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="95c53-118">For more information, see [Relational Query Designer User Interface &#40;Report Builder&#41;](relational-query-designer-user-interface-report-builder.md).</span></span>  
  
### <a name="to-build-a-query-for-an-embedded-dataset-in-report-design-view"></a><span data-ttu-id="95c53-119">Per compilare una query per un set di dati incorporato nella visualizzazione Struttura report</span><span class="sxs-lookup"><span data-stu-id="95c53-119">To build a query for an embedded dataset in Report Design View</span></span>  
  
1.  <span data-ttu-id="95c53-120">Aprire la finestra Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="95c53-120">Open the query designer.</span></span> <span data-ttu-id="95c53-121">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sul set di dati e quindi scegliere **Query**.</span><span class="sxs-lookup"><span data-stu-id="95c53-121">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
     <span data-ttu-id="95c53-122">Verrà visualizzata la finestra Progettazione query associata all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="95c53-122">The query designer that is associated with the data source opens.</span></span>  
  
2.  <span data-ttu-id="95c53-123">Nel riquadro Vista di database espandere le cartelle in cui viene visualizzata una vista gerarchica di oggetti dello schema di database quali tabelle, viste e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="95c53-123">In the Database view pane, expand the folders that display a hierarchical view of database schema objects such as tables, views, and stored procedures.</span></span> <span data-ttu-id="95c53-124">Fare clic sulla casella scelta per selezionare tutti i campi per un oggetto o espandere il nodo per selezionare i singoli campi.</span><span class="sxs-lookup"><span data-stu-id="95c53-124">Click the select box to select all fields for an object or expand the node to select individual fields.</span></span>  
  
     <span data-ttu-id="95c53-125">Quando si selezionano i campi dal riquadro Vista di database, le scelte vengono visualizzate nel riquadro **Seleziona campi** .</span><span class="sxs-lookup"><span data-stu-id="95c53-125">As you select fields from the Database view pane, the **Select fields** pane displays your selections.</span></span>  
  
     <span data-ttu-id="95c53-126">Se si selezionano campi da più tabelle di database correlate, utilizzare il riquadro Relazioni per visualizzare le relazioni tra tabelle rilevate dallo schema del database.</span><span class="sxs-lookup"><span data-stu-id="95c53-126">If you select fields from more than one related database table, use the Relationships pane to view the table relationships that were detected from the database schema.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="95c53-127">L'elenco di campi del set di dati viene visualizzato nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="95c53-127">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-specify-limits-for-a-query"></a><span data-ttu-id="95c53-128">Per specificare i limiti per una query</span><span class="sxs-lookup"><span data-stu-id="95c53-128">To specify limits for a query</span></span>  
  
1.  <span data-ttu-id="95c53-129">In Progettazione query relazionale verificare di aver selezionato i campi e che questi vengano visualizzati nel riquadro **Campi selezionati** .</span><span class="sxs-lookup"><span data-stu-id="95c53-129">In the relational query designer, verify that you have fields selected and that the fields appear in the **Selected fields** pane.</span></span>  
  
2.  <span data-ttu-id="95c53-130">Nella barra degli strumenti del riquadro Filtri applicati fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="95c53-130">In the Applied filters pane toolbar, click **Add Filter**.</span></span> <span data-ttu-id="95c53-131">Verrà visualizzata una nuova riga del filtro.</span><span class="sxs-lookup"><span data-stu-id="95c53-131">A new filter row appears.</span></span>  
  
3.  <span data-ttu-id="95c53-132">In **Nome campo**fare clic per visualizzare l'elenco a discesa dei campi e quindi fare clic sul nome del campo in base al quale si vuole filtrare.</span><span class="sxs-lookup"><span data-stu-id="95c53-132">In **Field name**, click to display the drop-down list of fields, and then click the name of the field that you want to filter by.</span></span> <span data-ttu-id="95c53-133">Per filtrare ad esempio in base alla quantità, fare clic sul campo che contiene il numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="95c53-133">For example, to filter by quantity, click the field that contains the number of items.</span></span>  
  
4.  <span data-ttu-id="95c53-134">In **Operatore**fare clic per visualizzare l'elenco a discesa degli operatori e quindi selezionare l'operatore di confronto da usare nel filtro.</span><span class="sxs-lookup"><span data-stu-id="95c53-134">In **Operator**, click to display the drop-down list of operators, and then select the comparison operator to use in the filter.</span></span>  
  
5.  <span data-ttu-id="95c53-135">In **Valore**digitare il valore in base al quale si vuole filtrare.</span><span class="sxs-lookup"><span data-stu-id="95c53-135">In **Value**, type the value that you want to filter by.</span></span> <span data-ttu-id="95c53-136">Per filtrare ad esempio in base a una quantità maggiore di 100, digitare 100.</span><span class="sxs-lookup"><span data-stu-id="95c53-136">For example, to filter on quantity greater than 100, type 100.</span></span>  
  
6.  <span data-ttu-id="95c53-137">Selezionare l'opzione di parametro in questa riga per creare un parametro del set di dati per consentire a un utente di specificare un valore di filtro.</span><span class="sxs-lookup"><span data-stu-id="95c53-137">Select the parameter option in this row to create a dataset parameter to enable a user to specify a filter value.</span></span> <span data-ttu-id="95c53-138">Un parametro del report che corrisponde al parametro del set di dati viene creato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="95c53-138">A report parameter that matches the dataset parameter is automatically created.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="95c53-139">L'elenco di campi del set di dati viene visualizzato nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="95c53-139">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-view-a-query-result-set"></a><span data-ttu-id="95c53-140">Per visualizzare un set di risultati della query</span><span class="sxs-lookup"><span data-stu-id="95c53-140">To view a query result set</span></span>  
  
1.  <span data-ttu-id="95c53-141">Sulla barra degli strumenti di Progettazione query fare clic su **Esegui query (!)** .</span><span class="sxs-lookup"><span data-stu-id="95c53-141">On the query designer toolbar, click **Run Query (!)**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95c53-142">Nella finestra Progettazione query vengono utilizzate le credenziali della fase di progettazione per eseguire la query e recuperare il set di risultati.</span><span class="sxs-lookup"><span data-stu-id="95c53-142">The query designer uses design time credentials to run the query and retrieve the result set.</span></span> <span data-ttu-id="95c53-143">Per altre informazioni, vedere [Specifica di credenziali in Generatore report](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="95c53-143">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="95c53-144">La query viene eseguita sull'origine dati e i dati di esempio vengono restituiti nel riquadro Risultati query.</span><span class="sxs-lookup"><span data-stu-id="95c53-144">The query runs on the data source and returns example data in the Query results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c53-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95c53-145">See Also</span></span>  
 <span data-ttu-id="95c53-146">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95c53-146">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="95c53-147">[Aggiungere dati da origini dati esterne &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95c53-147">[Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="95c53-148">[Progettazione query &#40;Generatore report&#41;](../query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="95c53-148">[Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="95c53-149">[Creare un set di dati condiviso o un set di dati incorporato &#40;Generatore report e SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95c53-149">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95c53-150">[Visualizzazione di progettazione report &#40;Generatore report&#41;](../report-builder/report-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="95c53-150">[Report Design View &#40;Report Builder&#41;](../report-builder/report-design-view-report-builder.md) </span></span>  
 <span data-ttu-id="95c53-151">[Visualizzazione di progettazione set di dati condivisi &#40;Generatore report&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="95c53-151">[Shared Dataset Design View &#40;Report Builder&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span></span>  
 [<span data-ttu-id="95c53-152">Strumenti di progettazione query in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="95c53-152">Reporting Services Query Designers</span></span>](../reporting-services-query-designers.md)  
  
  
