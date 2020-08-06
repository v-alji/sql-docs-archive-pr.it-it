---
title: 'Lesson 8: Create a Data Filter (Lezione 8: Creare un filtro di dati) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19ccbdba-e3da-40a4-b652-32c628cf32e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c11d4cf83619e53cd7e8f00091c66cc8e50ad76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625210"
---
# <a name="lesson-8-create-a-data-filter"></a><span data-ttu-id="9a597-102">Lezione 8: Creare un filtro di dati</span><span class="sxs-lookup"><span data-stu-id="9a597-102">Lesson 8: Create a Data Filter</span></span>
  <span data-ttu-id="9a597-103">Dopo aver aggiunto un'azione drill-through nel report padre, il passaggio successivo consiste nel creare un filtro di dati per la tabella di dati definita per il report figlio.</span><span class="sxs-lookup"><span data-stu-id="9a597-103">After you add a drillthrough action on the parent report, your next step is to create a data filter for the data table that you defined for the child report.</span></span>  
  
 <span data-ttu-id="9a597-104">È possibile creare un filtro basato su tabella **o** un filtro query per il report drill-through.</span><span class="sxs-lookup"><span data-stu-id="9a597-104">You can create a table-based filter **or** a query filter for the drillthrough report.</span></span> <span data-ttu-id="9a597-105">In questa lezione vengono fornite le istruzioni per entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="9a597-105">This lesson provides instructions for both options.</span></span>  
  
## <a name="table-based-filter"></a><span data-ttu-id="9a597-106">Filtro basato su tabella</span><span class="sxs-lookup"><span data-stu-id="9a597-106">Table-Based Filter</span></span>  
 <span data-ttu-id="9a597-107">È necessario completare le attività seguenti per implementare un filtro basato su tabella.</span><span class="sxs-lookup"><span data-stu-id="9a597-107">You need to complete the following tasks to implement a table-based filter.</span></span>  
  
-   <span data-ttu-id="9a597-108">Aggiungere un'espressione di filtro alla Tablix nel report figlio.</span><span class="sxs-lookup"><span data-stu-id="9a597-108">Add a filter expression to the tablix in the child report.</span></span>  
  
-   <span data-ttu-id="9a597-109">Creare una funzione mediante la quale vengono selezionati i dati non filtrati dalla tabella `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="9a597-109">Create a function that selects unfiltered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="9a597-110">Aggiungere un gestore eventi mediante il quale viene associato l'oggetto DataTable di `PurchaseOrderDetail` al report figlio.</span><span class="sxs-lookup"><span data-stu-id="9a597-110">Add an event handler that binds the `PurchaseOrderDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-add-a-filter-expression-to-the-tablix-in-the-child-report"></a><span data-ttu-id="9a597-111">Per aggiungere un'espressione di filtro alla Tablix nel report figlio</span><span class="sxs-lookup"><span data-stu-id="9a597-111">To add a filter expression to the tablix in the child report</span></span>  
  
1.  <span data-ttu-id="9a597-112">Aprire il report figlio.</span><span class="sxs-lookup"><span data-stu-id="9a597-112">Open the child report.</span></span>  
  
2.  <span data-ttu-id="9a597-113">Selezionare un'intestazione di colonna nella Tablix, fare clic con il pulsante destro del mouse sulla cella grigia visualizzata sopra l'intestazione di colonna e quindi scegliere **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="9a597-113">Select a column heading in the tablix, right-click the gray cell that appears above the column heading, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="9a597-114">Fare clic sulla pagina **filtri** , quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9a597-114">Click on the **Filters** page, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="9a597-115">Nell' **espressione** archiviato fare clic sull' `ProductID` elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9a597-115">In the **Expression** filed, click `ProductID` from the drop-down list.</span></span> <span data-ttu-id="9a597-116">Si tratta della colonna a cui applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="9a597-116">This is the column to which you apply the filter.</span></span>  
  
5.  <span data-ttu-id="9a597-117">Fare clic sull'operatore EQUAL ( **=** ) nell'elenco a discesa **operatore** .</span><span class="sxs-lookup"><span data-stu-id="9a597-117">Click the equal (**=**) operator in the **Operator** drop-down list.</span></span>  
  
6.  <span data-ttu-id="9a597-118">Fare clic sul pulsante espressione accanto al campo **valore** , fare clic su **parametri** nell'area **categoria** , quindi fare doppio clic `productid` nell'area **valori** .</span><span class="sxs-lookup"><span data-stu-id="9a597-118">Click the expression button next to the **Value** field, click **Parameters** in the **Category** area, and then double-click `productid` in the **Values** area.</span></span> <span data-ttu-id="9a597-119">Il campo **Imposta espressione per: Valore** dovrebbe contenere ora un'espressione simile a **=Parameters!productid.Value**.</span><span class="sxs-lookup"><span data-stu-id="9a597-119">The **Set expression for: Value** field should now contain expression similar to **=Parameters!productid.Value**.</span></span>  
  
7.  <span data-ttu-id="9a597-120">Fare clic su **OK** e di nuovo su **OK** nella finestra di dialogo **Proprietà Tablix** .</span><span class="sxs-lookup"><span data-stu-id="9a597-120">Click **OK,** and **OK** again in the **Tablix Properties** dialog box.</span></span>  
  
8.  <span data-ttu-id="9a597-121">Salvare il file con estensione rdlc.</span><span class="sxs-lookup"><span data-stu-id="9a597-121">Save the .rdlc file.</span></span>  
  
#### <a name="to-create-a-function-that-selects-unfiltered-data-from-the-purchaseordedetail-table"></a><span data-ttu-id="9a597-122">Per creare una funzione mediante la quale vengono selezionati i dati non filtrati dalla tabella PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="9a597-122">To create a function that selects unfiltered data from the PurchaseOrdeDetail table</span></span>  
  
1.  <span data-ttu-id="9a597-123">In Esplora soluzioni espandere Default.aspx, quindi fare doppio clic su Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="9a597-123">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="9a597-124">Creare una nuova funzione che accetta un parametro, `productid`, di tipo Integer, restituisce un oggetto `datatable` e consente di eseguire le operazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a597-124">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object, and does the following.</span></span>  
  
    1.  <span data-ttu-id="9a597-125">Crea un'istanza del DataSet, `DataSet2` , creata nel passaggio 2 della [lezione 4: definire una connessione dati e una tabella di dati per il report figlio](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="9a597-125">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="9a597-126">Creare una connessione al database di SQL Server per eseguire la query definita nella **Lezione 4: Definire una connessione dati e una tabella di dati per il report figlio**.</span><span class="sxs-lookup"><span data-stu-id="9a597-126">Create a connection to the SqlServer database to execute the query defined in **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="9a597-127">Tramite la query verranno restituiti i dati non filtrati.</span><span class="sxs-lookup"><span data-stu-id="9a597-127">The query will return unfiltered data.</span></span>  
  
    4.  <span data-ttu-id="9a597-128">Inserire i dati non filtrati nell'istanza di DataSet eseguendo la query.</span><span class="sxs-lookup"><span data-stu-id="9a597-128">Fill the DataSet instance with the unfiltered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="9a597-129">Restituire l'oggetto DataTable di `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="9a597-129">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="9a597-130">La funzione sarà simile alla seguente e dovrà essere utilizzata solo come riferimento.</span><span class="sxs-lookup"><span data-stu-id="9a597-130">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="9a597-131">È infatti possibile utilizzare qualsiasi modello desiderato per recuperare i dati necessari per il report figlio.</span><span class="sxs-lookup"><span data-stu-id="9a597-131">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table, fetch the  
            /// unfiltered data and bind it with the Child report  
            /// </summary>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail()  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail ", sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-binds-the-purchaseorderdetail-datatable-to-the-child-report"></a><span data-ttu-id="9a597-132">Per aggiungere un gestore eventi mediante il quale viene associato l'oggetto DataTable di PurchaseOrderDetail al report figlio</span><span class="sxs-lookup"><span data-stu-id="9a597-132">To add an event handler that binds the PurchaseOrderDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="9a597-133">Aprire Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="9a597-133">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="9a597-134">Fare clic con il pulsante destro del mouse sul controllo ReportViewer, quindi scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="9a597-134">Right click the ReportViewer control, and then click **Properties.**</span></span>  
  
3.  <span data-ttu-id="9a597-135">Nella pagina **Proprietà** fare clic sull'icona **eventi** .</span><span class="sxs-lookup"><span data-stu-id="9a597-135">On the **Properties** page, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="9a597-136">Fare doppio clic sull'evento **drill-through** .</span><span class="sxs-lookup"><span data-stu-id="9a597-136">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="9a597-137">Verrà aggiunta una sezione del gestore eventi nel codice, che sarà simile al blocco riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a597-137">This will add an event handler section in the code, which will look similar to the below block.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="9a597-138">Completare il gestore eventi</span><span class="sxs-lookup"><span data-stu-id="9a597-138">Complete the event handler.</span></span> <span data-ttu-id="9a597-139">nel quale dovrebbe essere inclusa la funzionalità riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a597-139">It should include the following functionalty.</span></span>  
  
    1.  <span data-ttu-id="9a597-140">Recuperare il riferimento all'oggetto del report figlio dal parametro *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="9a597-140">Fetch the child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="9a597-141">Chiamare la funzione,`GetPurchaseOrderDetail`</span><span class="sxs-lookup"><span data-stu-id="9a597-141">Call the function, `GetPurchaseOrderDetail`</span></span>  
  
    3.  <span data-ttu-id="9a597-142">Associare l'oggetto DataTable di `PurchaseOrderDetail` all'origine dati corrispondente del report.</span><span class="sxs-lookup"><span data-stu-id="9a597-142">Bind the `PurchaseOrderDetail` DataTable with the report's corresponding data source.</span></span>  
  
         <span data-ttu-id="9a597-143">Il codice del gestore eventi completato sarà simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="9a597-143">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                     //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                     //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail()));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="9a597-144">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="9a597-144">Save the file.</span></span>  
  
## <a name="query-filter"></a><span data-ttu-id="9a597-145">Filtro query</span><span class="sxs-lookup"><span data-stu-id="9a597-145">Query Filter</span></span>  
 <span data-ttu-id="9a597-146">È necessario completare le attività seguenti per implementare un filtro query.</span><span class="sxs-lookup"><span data-stu-id="9a597-146">You need to complete the following tasks to implement a query filter.</span></span>  
  
-   <span data-ttu-id="9a597-147">Creare una funzione mediante la quale sono stati selezionati i dati filtrati dalla tabella `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="9a597-147">Create a function that selected filtered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="9a597-148">Aggiungere un gestore eventi mediante il quale vengono recuperati i valori dei parametri e viene associato l'oggetto DataTable di `PurchaseOrdeDetail` al report figlio.</span><span class="sxs-lookup"><span data-stu-id="9a597-148">Add an event handler that retrieves parameter values and binds the `PurchaseOrdeDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-create-a-function-that-selects-filtered-data-from-the-purchaseorderdetail-table"></a><span data-ttu-id="9a597-149">Per creare una funzione mediante la quale vengono selezionati i dati filtrati dalla tabella PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="9a597-149">To create a function that selects filtered data from the PurchaseOrderDetail table</span></span>  
  
1.  <span data-ttu-id="9a597-150">In Esplora soluzioni espandere Default.aspx, quindi fare doppio clic su Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="9a597-150">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="9a597-151">Creare una nuova funzione che accetta un parametro, `productid`, di tipo Integer, restituisce un oggetto `datatable` e consente di eseguire le operazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a597-151">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object and does the following.</span></span>  
  
    1.  <span data-ttu-id="9a597-152">Crea un'istanza del DataSet, `DataSet2` , creata nel passaggio 2 della [lezione 4: definire una connessione dati e una tabella di dati per il report figlio](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="9a597-152">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="9a597-153">Creare una connessione al database di SQL Server per eseguire la query definita in **Lezione 4: Definire una connessione dati e una tabella di dati per il report figlio**.</span><span class="sxs-lookup"><span data-stu-id="9a597-153">Create a connection to the SqlServer database to execute the query defined **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="9a597-154">Nella query sarà incluso un parametro, `productid`, per garantire che i dati restituiti vengano filtrati in base a `ProductID` selezionato nel report padre.</span><span class="sxs-lookup"><span data-stu-id="9a597-154">The query will include a parameter, `productid`, to make sure the data returned is filtered based on the `ProductID` selected in the parent report.</span></span>  
  
    4.  <span data-ttu-id="9a597-155">Inserire i dati filtrati nell'istanza di DataSet eseguendo la query.</span><span class="sxs-lookup"><span data-stu-id="9a597-155">Fill the DataSet instance with the filtered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="9a597-156">Restituire l'oggetto DataTable di `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="9a597-156">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="9a597-157">La funzione sarà simile alla seguente e dovrà essere utilizzata solo come riferimento.</span><span class="sxs-lookup"><span data-stu-id="9a597-157">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="9a597-158">È infatti possibile utilizzare qualsiasi modello desiderato per recuperare i dati necessari per il report figlio.</span><span class="sxs-lookup"><span data-stu-id="9a597-158">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table and filter the  
            /// data for a specific ProductID selected in the Parent report.  
            /// </summary>  
            /// <param name="productid">Parameter passed from the Parent report to filter data.</param>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail(int productid)  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail where ProductID = " + productid, sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-retrieves-parameter-values-and-binds-the-purchaseordedetail-datatable-to-the-child-report"></a><span data-ttu-id="9a597-159">Per aggiungere un gestore eventi mediante il quale vengono recuperati i valori dei parametri e viene associato l'oggetto DataTable di PurchaseOrderDetail al report figlio</span><span class="sxs-lookup"><span data-stu-id="9a597-159">To add an event handler that retrieves parameter values and binds the PurchaseOrdeDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="9a597-160">Aprire Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="9a597-160">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="9a597-161">Fare clic con il pulsante destro del mouse sul controllo ReportViewer, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9a597-161">Right-click the ReportViewer control, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9a597-162">Nel riquadro **Proprietà** fare clic sull'icona **eventi** .</span><span class="sxs-lookup"><span data-stu-id="9a597-162">On the **Properties** pane, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="9a597-163">Fare doppio clic sull'evento **drill-through** .</span><span class="sxs-lookup"><span data-stu-id="9a597-163">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="9a597-164">Verrà aggiunta una sezione del gestore eventi nel codice, che sarà simile a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a597-164">This will add an event handler section in the code that will look similar to the following.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="9a597-165">Completare il gestore eventi</span><span class="sxs-lookup"><span data-stu-id="9a597-165">Complete the event handler.</span></span> <span data-ttu-id="9a597-166">nel quale dovrebbe essere inclusa la funzionalità riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a597-166">It should include the following functionality.</span></span>  
  
    1.  <span data-ttu-id="9a597-167">Recuperare il riferimento all'oggetto del report figlio dal parametro *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="9a597-167">Fetch the Child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="9a597-168">Ottenere l'elenco dei parametri del report figlio dall'oggetto del report figlio recuperato.</span><span class="sxs-lookup"><span data-stu-id="9a597-168">Get the child report parameter list from the child report object fetched.</span></span>  
  
    3.  <span data-ttu-id="9a597-169">Scorrere la raccolta dei parametri e recuperare il valore per il parametro, `ProductID`, passato dal report padre.</span><span class="sxs-lookup"><span data-stu-id="9a597-169">Iterate through the parameter's collection and retrieve the value for the parameter, `ProductID`, passed from the parent report.</span></span>  
  
    4.  <span data-ttu-id="9a597-170">Chiamare la funzione, `GetPurchaseOrderDetail`, e passare il valore per il parametro `ProductID`.</span><span class="sxs-lookup"><span data-stu-id="9a597-170">Call the function, `GetPurchaseOrderDetail`, and pass the value for parameter `ProductID`.</span></span>  
  
    5.  <span data-ttu-id="9a597-171">Associare l'oggetto DataTable di `PurchaseOrderDetail` all'origine dati corrispondente del report.</span><span class="sxs-lookup"><span data-stu-id="9a597-171">Bind the `PurchaseOrderDetail` DataTable with the Report's corresponding data source.</span></span>  
  
         <span data-ttu-id="9a597-172">Il codice del gestore eventi completato sarà simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="9a597-172">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                    //Variable to store the parameter value passed from the MainReport.  
                    int productid = 0;  
  
                    //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                    //Get all the parameters passed from the main report to the target report.  
                    //OriginalParametersToDrillthrough actually returns a Generic list of   
                    //type ReportParameter.  
                    IList<ReportParameter> list = report.OriginalParametersToDrillthrough;  
  
                    //Parse through each parameters to fetch the values passed along with them.  
                    foreach (ReportParameter param in list)  
                    {  
                        //Since we know the report has only one parameter and it is not a multivalued,   
                        //we can directly fetch the first value from the Values array.  
                        productid = Convert.ToInt32(param.Values[0].ToString());  
                    }  
  
                    //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail(productid)));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="9a597-173">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="9a597-173">Save the file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="9a597-174">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="9a597-174">Next Task</span></span>  
 <span data-ttu-id="9a597-175">È stato creato correttamente un filtro di dati per la tabella di dati definita per il report figlio.</span><span class="sxs-lookup"><span data-stu-id="9a597-175">You have successfully created a data filter for the data table that you defined for the child report.</span></span> <span data-ttu-id="9a597-176">Successivamente, verrà compilata ed eseguita l'applicazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="9a597-176">Next, you will build and run the website application.</span></span>  
  
  
