---
title: "Lesson 2: Modifying the Report Data Source Properties (Lezione 2: Modifica delle proprietà dell'origine dati del report) | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c962b0ff-ce8a-4742-8262-dc730901afcf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05e56a58ce28ee1e1e450d3af012cbd1ffe668ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625231"
---
# <a name="lesson-2-modifying-the-report-data-source-properties"></a><span data-ttu-id="d3e04-102">Lesson 2: Modifying the Report Data Source Properties</span><span class="sxs-lookup"><span data-stu-id="d3e04-102">Lesson 2: Modifying the Report Data Source Properties</span></span>
  <span data-ttu-id="d3e04-103">In questa lezione verrà utilizzato Gestione report per seleziona un report da recapitare ai destinatari.</span><span class="sxs-lookup"><span data-stu-id="d3e04-103">In this lesson, you will use Report Manager to select a report that will be delivered to recipients.</span></span> <span data-ttu-id="d3e04-104">Con la sottoscrizione guidata dai dati che verrà definita verrà distribuito il report **Ordine vendita** creato nell'esercitazione [Creare un report tabella semplice &#40;esercitazione su SSRS&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d3e04-104">The data-driven subscription that you will define will distribute the **Sales Order** report created in the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span></span> <span data-ttu-id="d3e04-105">Nei passaggi seguenti verranno modificate le informazioni di connessione all'origine dei dati utilizzate dal report per acquisire i dati.</span><span class="sxs-lookup"><span data-stu-id="d3e04-105">In the steps that follow, you will modify the data source connection information used by the report to get data.</span></span> <span data-ttu-id="d3e04-106">Solo i report in cui vengono usate **credenziali archiviate** per accedere a un'origine dati del report possono essere distribuiti attraverso una sottoscrizione guidata dai dati.</span><span class="sxs-lookup"><span data-stu-id="d3e04-106">Only reports that use **stored credentials** to access a report data source can be distributed through a data-driven subscription.</span></span> <span data-ttu-id="d3e04-107">Le credenziali archiviate sono necessarie per l'esecuzione automatica dei report.</span><span class="sxs-lookup"><span data-stu-id="d3e04-107">Stored credentials are necessary for unattended report processing.</span></span>

 <span data-ttu-id="d3e04-108">Inoltre, verrà modificato il set di dati e il report per utilizzare un parametro al fine di filtrare il report in `[Order]` in modo che tramite la sottoscrizione sia possibile restituire istanze differenti del report per formati di rendering e ordini specifici.</span><span class="sxs-lookup"><span data-stu-id="d3e04-108">You will also modify the dataset and report to use a parameter to filter the report on the `[Order]` so the subscription can output different instances of the report for specific orders and rendering formats.</span></span>

 <span data-ttu-id="d3e04-109">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="d3e04-109">**In this topic:**</span></span>

-   [<span data-ttu-id="d3e04-110">Per modificare le proprietà dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="d3e04-110">To Modify the Data Source Properties</span></span>](#bkmk_modify_datasource)

-   [<span data-ttu-id="d3e04-111">Per modificare AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="d3e04-111">To Modify the AdventureWorksDataset</span></span>](#bkmk_modify_dataset)

-   [<span data-ttu-id="d3e04-112">Per aggiungere un parametro del report e ripubblicare il report</span><span class="sxs-lookup"><span data-stu-id="d3e04-112">To Add a Report Parameter and Republish the Report</span></span>](#bkmk_add_reportparameter)

-   [<span data-ttu-id="d3e04-113">Per ridistribuire il report</span><span class="sxs-lookup"><span data-stu-id="d3e04-113">To Re-deploy the Report</span></span>](#bkmk_redeploy)

##  <a name="to-modify-the-data-source-properties"></a><a name="bkmk_modify_datasource"></a><span data-ttu-id="d3e04-114">Per modificare le proprietà dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="d3e04-114">To Modify the Data Source Properties</span></span>

1.  <span data-ttu-id="d3e04-115">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) con privilegi di amministratore, ad esempio, fare clic con il pulsante destro del mouse sull'icona di Internet Explorer e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>

2.  <span data-ttu-id="d3e04-116">Selezionare la cartella contenente il report **Ordini vendita** e nel menu di scelta rapida del report fare clic su **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-116">Browse to the folder containing the **Sales Orders** report and in the context menu of the report, click **Manage**.</span></span>

     <span data-ttu-id="d3e04-117">![Aprire il menu di scelta rapida del report e selezionare Gestisci](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Aprire il menu di scelta rapida del report e selezionare Gestisci")</span><span class="sxs-lookup"><span data-stu-id="d3e04-117">![Open the report context menu and select manage](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Open the report context menu and select manage")</span></span>

3.  <span data-ttu-id="d3e04-118">Fare clic sulla scheda **Origini dati** .</span><span class="sxs-lookup"><span data-stu-id="d3e04-118">Click the **Data Sources** tab.</span></span>

4.  <span data-ttu-id="d3e04-119">In **Tipo di connessione**selezionare **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-119">For **Connection Type**, select **Microsoft SQL Server**.</span></span>

5.  <span data-ttu-id="d3e04-120">La stringa di connessione dell'origine dati personalizzata sarà come riportata di seguito; inoltre, si presuppone che il database di esempio si trovi in un server di database locale:</span><span class="sxs-lookup"><span data-stu-id="d3e04-120">The custom data source connection string will be the following and it assumes that the sample database is on a local database server:</span></span>

    ```
    Data source=localhost; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="d3e04-121">Fare clic su **Credenziali archiviate in modo protetto nel server di report**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-121">Click **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="d3e04-122">Digitare il nome utente nel formato *dominio\utente*e la password.</span><span class="sxs-lookup"><span data-stu-id="d3e04-122">Type your user name (use the format *domain\user*) and password.</span></span> <span data-ttu-id="d3e04-123">Se non si dispone delle autorizzazioni per l'accesso al database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , specificare un account di accesso autorizzato.</span><span class="sxs-lookup"><span data-stu-id="d3e04-123">If you do not have permission to access the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database, specify a login that does.</span></span>

8.  <span data-ttu-id="d3e04-124">Fare clic su **Usa come credenziali di Windows per la connessione all'origine dei dati**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-124">Click **Use as windows credentials when connecting to the data source**, and then click **OK**.</span></span> <span data-ttu-id="d3e04-125">Se non viene utilizzato un account di dominio, ad esempio se si utilizza un account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], non selezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="d3e04-125">If you are not using a domain account (for example, if you are using a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login), do not click this checkbox.</span></span>

9. <span data-ttu-id="d3e04-126">Fare clic su **Test connessione** per verificare che sia possibile connettersi all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d3e04-126">Click **Test Connection** to verify you can connect to the data source.</span></span>

10. <span data-ttu-id="d3e04-127">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-127">Click **Apply**.</span></span>

11. <span data-ttu-id="d3e04-128">Visualizzare il report per verificare che venga eseguito con le credenziali specificate.</span><span class="sxs-lookup"><span data-stu-id="d3e04-128">View the report to verify that the report runs with the credentials you specified.</span></span> <span data-ttu-id="d3e04-129">Per visualizzare il report, fare clic sulla scheda **Visualizza** . si noti che, una volta aperto il report, è necessario selezionare un nome di dipendente e quindi fare clic sul pulsante **Visualizza report** per visualizzare il report.</span><span class="sxs-lookup"><span data-stu-id="d3e04-129">To view the report, click the **View** tab. Note that once the report is open, you must select an Employee name and then click the **View Report** button to view the report.</span></span>

##  <a name="to-modify-the-adventureworksdataset"></a><a name="bkmk_modify_dataset"></a><span data-ttu-id="d3e04-130">Per modificare il AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="d3e04-130">To Modify the AdventureWorksDataset</span></span>

1.  <span data-ttu-id="d3e04-131">Aprire il report Ordini vendita in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3e04-131">Open the Sales Orders report in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span></span>

2.  <span data-ttu-id="d3e04-132">Fare clic con il pulsante destro del mouse sul set di dati `AdventureWorksDataset` e scegliere **Proprietà set di dati**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-132">Right-click the dataset `AdventureWorksDataset` and click **Dataset Properties**.</span></span>

3.  <span data-ttu-id="d3e04-133">Aggiungere l'istruzione `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` prima dell'istruzione `Group By` .</span><span class="sxs-lookup"><span data-stu-id="d3e04-133">Add the statement `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` before the `Group By` statement.</span></span> <span data-ttu-id="d3e04-134">La sintassi della query completa è la seguente:</span><span class="sxs-lookup"><span data-stu-id="d3e04-134">The full query syntax is the following:</span></span>

    ```
    SELECT soh.OrderDate AS Date, soh.SalesOrderNumber AS [Order], pps.Name AS Subcat, pp.Name AS Product, SUM(sd.OrderQty) AS Qty, SUM(sd.LineTotal)  AS LineTotal
    FROM Sales.SalesPerson AS sp INNER JOIN
      Sales.SalesOrderHeader AS soh ON sp.BusinessEntityID = soh.SalesPersonID INNER JOIN
       Sales.SalesOrderDetail AS sd ON sd.SalesOrderID = soh.SalesOrderID INNER JOIN
       Production.Product AS pp ON sd.ProductID = pp.ProductID
    INNER JOIN
       Production.ProductSubcategory AS pps ON pp.ProductSubcategoryID = pps.ProductSubcategoryID 
    INNER JOIN
        Production.ProductCategory AS ppc ON ppc.ProductCategoryID = pps.ProductCategoryID

    WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)

    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name, soh.SalesPersonID
    HAVING (ppc.Name = 'Clothing')
    ```

4.  <span data-ttu-id="d3e04-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-135">Click **OK**</span></span>

##  <a name="to-add-a-report-parameter-and-republish-the-report"></a><a name="bkmk_add_reportparameter"></a><span data-ttu-id="d3e04-136">Per aggiungere un parametro del report e ripubblicare il report</span><span class="sxs-lookup"><span data-stu-id="d3e04-136">To Add a Report Parameter and Republish the Report</span></span>

1.  <span data-ttu-id="d3e04-137">Nel riquadro dei dati del \*\*\*\* report fare clic su **Nuovo** , quindi scegliere **Parametro**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-137">In the **Report Data** pane click **New** and then click **Parameter...**</span></span>

2.  <span data-ttu-id="d3e04-138">In **Nome**digitare `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="d3e04-138">In **Name**, type `OrderNumber`.</span></span>

3.  <span data-ttu-id="d3e04-139">In **Messaggio di richiesta**digitare `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="d3e04-139">In **Prompt**, type `OrderNumber`.</span></span>

4.  <span data-ttu-id="d3e04-140">Selezionare **Consenti nessun valore ("")**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-140">Select **Allow blank value ("")**.</span></span>

5.  <span data-ttu-id="d3e04-141">Selezionare **Consenti valore Null**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-141">Select **Allow null value**.</span></span>

6.  <span data-ttu-id="d3e04-142">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-142">Click **OK**.</span></span> <span data-ttu-id="d3e04-143">Il parametro verrà aggiunto al riquadro dei dati del \*\*\*\* report e l'immagine sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="d3e04-143">The parameter will be added to the **Report Data pane** and it will look like the following image:</span></span>

     <span data-ttu-id="d3e04-144">![Il nuovo parametro viene aggiunto al riquadro dei dati del report](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "Il nuovo parametro viene aggiunto al riquadro dei dati del report")</span><span class="sxs-lookup"><span data-stu-id="d3e04-144">![The new parameter is added to the Report Data pane](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "The new parameter is added to the Report Data pane")</span></span>

7.  <span data-ttu-id="d3e04-145">Fare clic sulla scheda **Anteprima** per eseguire il report. Si noti la casella di input del parametro nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="d3e04-145">Click the **Preview** tab to run the report.Note the parameter input box at the top of the report.</span></span> <span data-ttu-id="d3e04-146">È possibile:</span><span class="sxs-lookup"><span data-stu-id="d3e04-146">You can either:</span></span>

    -   <span data-ttu-id="d3e04-147">Fare clic su Visualizza report per visualizzare il report completo senza l'utilizzo di parametri.</span><span class="sxs-lookup"><span data-stu-id="d3e04-147">Click View Report to see the full report without using a parameter.</span></span>

    -   <span data-ttu-id="d3e04-148">Deselezionare l'opzione Null e digitare un numero di ordine, ad esempio so71949, per visualizzare solo quell'ordine nel report.</span><span class="sxs-lookup"><span data-stu-id="d3e04-148">Unselect the Null option and type an order number, for example so71949 to view only the one order in the report.</span></span>

         <span data-ttu-id="d3e04-149">![Visualizzatore report con l'area dei parametri visibile](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Visualizzatore report con l'area dei parametri visibile")</span><span class="sxs-lookup"><span data-stu-id="d3e04-149">![Report viewer with parameter area visible](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Report viewer with parameter area visible")</span></span>

8.  <span data-ttu-id="d3e04-150">Distribuire di nuovo il report in modo che con la configurazione della sottoscrizione nella prossima lezione sia possibile utilizzare le modifiche apportate in questa lezione.</span><span class="sxs-lookup"><span data-stu-id="d3e04-150">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="d3e04-151">Per ulteriori informazioni sulle proprietà del progetto utilizzate nell'esercitazione relativa alla tabella, vedere la sezione "per pubblicare il report nel server di report (facoltativo)" della [lezione 6: aggiunta di gruppi e totali &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="d3e04-151">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

##  <a name="to-re-deploy-the-report"></a><a name="bkmk_redeploy"></a><span data-ttu-id="d3e04-152">Per ridistribuire il report</span><span class="sxs-lookup"><span data-stu-id="d3e04-152">To Re-deploy the Report</span></span>

1.  <span data-ttu-id="d3e04-153">Distribuire di nuovo il report in modo che con la configurazione della sottoscrizione nella prossima lezione sia possibile utilizzare le modifiche apportate in questa lezione.</span><span class="sxs-lookup"><span data-stu-id="d3e04-153">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="d3e04-154">Per ulteriori informazioni sulle proprietà del progetto utilizzate nell'esercitazione relativa alla tabella, vedere la sezione "per pubblicare il report nel server di report (facoltativo)" della [lezione 6: aggiunta di gruppi e totali &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="d3e04-154">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

2.  <span data-ttu-id="d3e04-155">Sulla barra degli strumenti fare clic su **Compila** , quindi scegliere **Distribuisci Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="d3e04-155">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3e04-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d3e04-156">Next Steps</span></span>
 <span data-ttu-id="d3e04-157">In questo modo il report è stato configurato per l'acquisizione di dati utilizzando credenziali archiviate.</span><span class="sxs-lookup"><span data-stu-id="d3e04-157">You successfully configured the report to get data using stored credentials.</span></span> <span data-ttu-id="d3e04-158">Il passaggio successivo consiste nell'impostazione della sottoscrizione tramite le pagine relative disponibili in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="d3e04-158">Next, you specify the subscription using the Data-Driven Subscription pages in Report Manager.</span></span> <span data-ttu-id="d3e04-159">Vedere [Lezione 3: Definizione di una sottoscrizione guidata dai dati](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="d3e04-159">See [Lesson 3: Defining a Data-Driven Subscription](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3e04-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3e04-160">See Also</span></span>
 <span data-ttu-id="d3e04-161">[Gestione delle origini dati del report](report-data/manage-report-data-sources.md) [specificare le credenziali e le informazioni di connessione per le origini dati del report](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [creare una sottoscrizione guidata dai dati &#40;esercitazione su SSRS&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [creare un Report tabella semplice &#40;Esercitazione su SSRS&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="d3e04-161">[Manage Report Data Sources](report-data/manage-report-data-sources.md) [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span></span>


