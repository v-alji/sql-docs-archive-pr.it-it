---
title: 'Lesson 3: Defining a Dataset for the Table Report (Reporting Services) (Lezione 3: Definizione di un set di dati per il report tabella (Reporting Services)) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ee93dfcb-8f52-4d63-b4f6-0d38e00fd350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 33fe48a60db2e7d15d205a4bff6205347f95c61c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626562"
---
# <a name="lesson-3-defining-a-dataset-for-the-table-report-reporting-services"></a><span data-ttu-id="3df6f-102">Lezione 3: Definizione di un set di dati per il report tabella (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="3df6f-102">Lesson 3: Defining a Dataset for the Table Report (Reporting Services)</span></span>
  <span data-ttu-id="3df6f-103">Dopo aver definito l'origine dati, è necessario definire un set di dati.</span><span class="sxs-lookup"><span data-stu-id="3df6f-103">After you define the data source, you need to define a dataset.</span></span> <span data-ttu-id="3df6f-104">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]i dati utilizzati nei report sono contenuti in un *set di dati*.</span><span class="sxs-lookup"><span data-stu-id="3df6f-104">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], data that you use in reports is contained in a *dataset*.</span></span> <span data-ttu-id="3df6f-105">Un set di dati contiene un puntatore a un'origine dati e la query utilizzata dal report, nonché le variabili e i campi calcolati.</span><span class="sxs-lookup"><span data-stu-id="3df6f-105">A dataset includes a pointer to a data source and a query to be used by the report, as well as calculated fields and variables.</span></span>  
  
 <span data-ttu-id="3df6f-106">Per progettare la query è possibile utilizzare la finestra Progettazione query in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="3df6f-106">You can use the query designer in Report Designer to design the query.</span></span> <span data-ttu-id="3df6f-107">Per questa esercitazione verrà creata una query che recupera le informazioni sugli ordini di vendita dal [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database **2008** .</span><span class="sxs-lookup"><span data-stu-id="3df6f-107">For this tutorial, you will create a query that retrieves sales order information from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]**2008** database.</span></span>  
  
### <a name="to-define-a-transact-sql-query-for-report-data"></a><span data-ttu-id="3df6f-108">Per definire una query Transact-SQL per i dati del report</span><span class="sxs-lookup"><span data-stu-id="3df6f-108">To define a Transact-SQL query for report data</span></span>  
  
1.  <span data-ttu-id="3df6f-109">Nel riquadro **dei dati del report** fare clic su **nuovo**e quindi su **set**di dati. Verrà visualizzata la finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="3df6f-109">In the **Report Data** pane, click **New**, and then click **Dataset...**. The **Dataset Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="3df6f-110">Nella casella **Nome** digitare **AdventureWorksDataset**.</span><span class="sxs-lookup"><span data-stu-id="3df6f-110">In the **Name** box, type **AdventureWorksDataset**.</span></span>  
  
3.  <span data-ttu-id="3df6f-111">Fare clic su **Usare un set di dati incorporato nel report**.</span><span class="sxs-lookup"><span data-stu-id="3df6f-111">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="3df6f-112">Verificare che il nome dell'origine dati, AdventureWorks2012, sia presente nella casella di testo **origine dati** e che il **tipo di query** sia **testo**.</span><span class="sxs-lookup"><span data-stu-id="3df6f-112">Make sure the name of your data source, AdventureWorks2012, is in the **Data source** text box, and that the **Query type** is **Text**.</span></span>  
  
5.  <span data-ttu-id="3df6f-113">Digitare oppure copiare e incollare la query Transact-SQL seguente nella casella **Query** .</span><span class="sxs-lookup"><span data-stu-id="3df6f-113">Type, or copy and paste, the following Transact-SQL query into the **Query** box.</span></span>  
  
    ```  
    SELECT   
       soh.OrderDate AS [Date],   
       soh.SalesOrderNumber AS [Order],   
       pps.Name AS Subcat, pp.Name as Product,    
       SUM(sd.OrderQty) AS Qty,  
       SUM(sd.LineTotal) AS LineTotal  
    FROM Sales.SalesPerson sp   
       INNER JOIN Sales.SalesOrderHeader AS soh   
          ON sp.BusinessEntityID = soh.SalesPersonID  
       INNER JOIN Sales.SalesOrderDetail AS sd   
          ON sd.SalesOrderID = soh.SalesOrderID  
       INNER JOIN Production.Product AS pp   
          ON sd.ProductID = pp.ProductID  
       INNER JOIN Production.ProductSubcategory AS pps   
          ON pp.ProductSubcategoryID = pps.ProductSubcategoryID  
       INNER JOIN Production.ProductCategory AS ppc   
          ON ppc.ProductCategoryID = pps.ProductCategoryID  
    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name,   
       soh.SalesPersonID  
    HAVING ppc.Name = 'Clothing'  
    ```  
  
6.  <span data-ttu-id="3df6f-114">(Facoltativo) Fare clic sul pulsante **Progettazione query** .</span><span class="sxs-lookup"><span data-stu-id="3df6f-114">(Optional) Click the **Query Designer** button.</span></span> <span data-ttu-id="3df6f-115">La query verrà visualizzata nella finestra Progettazione query basata su testo.</span><span class="sxs-lookup"><span data-stu-id="3df6f-115">The query is displayed in the text-based query designer.</span></span> <span data-ttu-id="3df6f-116">È possibile passare alla finestra Progettazione query con interfaccia grafica facendo clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="3df6f-116">You can toggle to the graphical query designer by clicking **Edit As Text**.</span></span> <span data-ttu-id="3df6f-117">Per visualizzare i risultati della query, fare clic sul pulsante Esegui **(!)** sulla barra degli strumenti Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="3df6f-117">View the results of the query by clicking the run **(!)** button on the query designer toolbar.</span></span>  
  
     <span data-ttu-id="3df6f-118">Verranno visualizzati i dati contenuti in sei campi di quattro tabelle differenti del database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3df6f-118">You see the data from six fields from four different tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="3df6f-119">Nella query vengono utilizzate funzionalità di Transact-SQL come gli alias.</span><span class="sxs-lookup"><span data-stu-id="3df6f-119">The query makes use of Transact-SQL functionality such as aliases.</span></span> <span data-ttu-id="3df6f-120">La tabella SalesOrderHeader viene ad esempio denominata soh.</span><span class="sxs-lookup"><span data-stu-id="3df6f-120">For example, the SalesOrderHeader table is called soh.</span></span>  
  
     <span data-ttu-id="3df6f-121">Fare clic su **OK** per chiudere la finestra Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="3df6f-121">Click **OK** to exit the query designer.</span></span>  
  
7.  <span data-ttu-id="3df6f-122">Fare clic su **OK** per chiudere la finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="3df6f-122">Click **OK** to exit the **Dataset Properties** dialog box.</span></span>  
  
     <span data-ttu-id="3df6f-123">I campi e il set di dati di **AdventureWorksDataset** vengono visualizzati nel riquadro Dati report.</span><span class="sxs-lookup"><span data-stu-id="3df6f-123">Your **AdventureWorksDataset** dataset and fields appear in the Report Data pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="3df6f-124">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="3df6f-124">Next Task</span></span>  
 <span data-ttu-id="3df6f-125">In questo modo si è specificata una query che recupera i dati per il report.</span><span class="sxs-lookup"><span data-stu-id="3df6f-125">You have successfully specified a query that retrieves data for your report.</span></span> <span data-ttu-id="3df6f-126">Il passaggio successivo consiste nella creazione del layout del report.</span><span class="sxs-lookup"><span data-stu-id="3df6f-126">Next, you will create the report layout.</span></span> <span data-ttu-id="3df6f-127">Vedere [Lezione 4: Aggiunta di una tabella al report &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3df6f-127">See [Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df6f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3df6f-128">See Also</span></span>  
 <span data-ttu-id="3df6f-129">[Strumenti di progettazione query in Progettazione report SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3df6f-129">[Query Design Tools in Report Designer SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span></span>  
 <span data-ttu-id="3df6f-130">[Tipo di connessione SQL Server &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3df6f-130">[SQL Server Connection Type &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="3df6f-131">Esercitazione: Scrittura di istruzioni Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3df6f-131">Tutorial: Writing Transact-SQL Statements</span></span>](../t-sql/tutorial-writing-transact-sql-statements.md)  
  
  
