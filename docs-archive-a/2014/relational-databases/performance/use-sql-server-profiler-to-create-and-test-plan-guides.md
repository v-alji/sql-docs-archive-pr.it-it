---
title: Usare SQL Server Profiler per creare e testare guide di piano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- checking plan guides
- plan guides [SQL Server], testing
- plan guides [SQL Server], SQL Server Profiler
- matching queries to plan guides [SQL Server]
- testing plan guides
- SQL Server Profiler, plan guides
- plan guides [SQL Server], creating
- capturing query text [SQL Server]
- verifying plan guides
- Profiler [SQL Server Profiler], plan guides
- query-to-plan guide matching [SQL Server]
ms.assetid: 7018dbf0-1a1a-411a-88af-327bedf9cfbd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 543905343d74c9fbabe5f671d9021657ea5f76b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716272"
---
# <a name="use-sql-server-profiler-to-create-and-test-plan-guides"></a><span data-ttu-id="386bb-102">Usare SQL Server Profiler per creare e testare guide di piano</span><span class="sxs-lookup"><span data-stu-id="386bb-102">Use SQL Server Profiler to Create and Test Plan Guides</span></span>
  <span data-ttu-id="386bb-103">Quando si crea una guida di piano è possibile usare [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per acquisire il testo esatto della query da usare nell'argomento *statement_text* della stored procedure **sp_create_plan_guide** .</span><span class="sxs-lookup"><span data-stu-id="386bb-103">When you are creating a plan guide, you can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to capture the exact query text for use in the *statement_text* argument of the **sp_create_plan_guide** stored procedure.</span></span> <span data-ttu-id="386bb-104">Questo garantisce che in fase di compilazione la guida di piano corrisponderà alla query.</span><span class="sxs-lookup"><span data-stu-id="386bb-104">This helps make sure that the plan guide will be matched to the query at compile time.</span></span> <span data-ttu-id="386bb-105">Dopo la creazione della guida di piano è possibile utilizzare ancora [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per verificare che la guida di piano corrisponda effettivamente alla query.</span><span class="sxs-lookup"><span data-stu-id="386bb-105">After the plan guide is created, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can also be used to test that the plan guide is, in fact, being matched to the query.</span></span> <span data-ttu-id="386bb-106">È in genere consigliabile testare le guide di piano tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per verificarne la corrispondenza con la query.</span><span class="sxs-lookup"><span data-stu-id="386bb-106">Generally, you should test plan guides by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to verify that your query is being matched to your plan guide.</span></span>  
  
## <a name="capturing-query-text-by-using-sql-server-profiler"></a><span data-ttu-id="386bb-107">Acquisizione del testo di una query tramite SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="386bb-107">Capturing Query Text by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="386bb-108">Se si esegue una query e se ne acquisisce il testo esattamente come è stato inviato a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], sarà possibile creare una guida di piano di tipo SQL o TEMPLATE che corrisponderà esattamente al testo della query.</span><span class="sxs-lookup"><span data-stu-id="386bb-108">If you run a query and capture the text exactly as it was submitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can create a plan guide of type SQL or TEMPLATE that will match the query text exactly.</span></span> <span data-ttu-id="386bb-109">Questo garantisce che la guida di piano verrà utilizzata da Query Optimizer.</span><span class="sxs-lookup"><span data-stu-id="386bb-109">This makes sure that the plan guide is used by the query optimizer.</span></span>  
  
 <span data-ttu-id="386bb-110">Si consideri la query seguente, inviata da un'applicazione come batch autonomo:</span><span class="sxs-lookup"><span data-stu-id="386bb-110">Consider the following query that is submitted by an application as a stand-alone batch:</span></span>  
  
```  
SELECT COUNT(*) AS c  
FROM Sales.SalesOrderHeader AS h  
INNER JOIN Sales.SalesOrderDetail AS d  
  ON h.SalesOrderID = d.SalesOrderID  
WHERE h.OrderDate BETWEEN '20000101' and '20050101';  
```  
  
 <span data-ttu-id="386bb-111">Si supponga di voler eseguire la query tramite un'operazione di merge join, ma che SHOWPLAN indichi che la query non sta utilizzando un merge join.</span><span class="sxs-lookup"><span data-stu-id="386bb-111">Suppose you want this query to execute using a merge join operation, but SHOWPLAN indicates that the query is not using a merge join.</span></span> <span data-ttu-id="386bb-112">Non è possibile modificare la query direttamente nell'applicazione, pertanto è necessario creare una guida di piano per specificare che l'hint per la query MERGE JOIN venga accodato alla query in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="386bb-112">You cannot change the query directly in the application, so instead you create a plan guide to specify that the MERGE JOIN query hint be appended to the query at compile time.</span></span>  
  
 <span data-ttu-id="386bb-113">Per acquisire il testo della query esattamente come viene ricevuto da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="386bb-113">To capture the text of the query exactly as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] receives it, follow these steps:</span></span>  
  
1.  <span data-ttu-id="386bb-114">Avviare una traccia di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] verificando che sia selezionato il tipo di evento **SQL:BatchStarting** .</span><span class="sxs-lookup"><span data-stu-id="386bb-114">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making sure that the **SQL:BatchStarting** event type is selected.</span></span>  
  
2.  <span data-ttu-id="386bb-115">Eseguire la query dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="386bb-115">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="386bb-116">Sospendere la traccia di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="386bb-116">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="386bb-117">Fare clic sull'evento **SQL:BatchStarting** corrispondente alla query.</span><span class="sxs-lookup"><span data-stu-id="386bb-117">Click the **SQL:BatchStarting** event that corresponds to the query.</span></span>  
  
5.  <span data-ttu-id="386bb-118">Fare clic con il pulsante destro del mouse e scegliere **Estrai dati eventi**.</span><span class="sxs-lookup"><span data-stu-id="386bb-118">Right-click and select **Extract Event Data**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="386bb-119">Non tentare di copiare il testo del batch selezionandolo dal riquadro inferiore della finestra di traccia di SQL Profiler.</span><span class="sxs-lookup"><span data-stu-id="386bb-119">Do not try to copy the batch text by selecting it from the lower pane of the Profiler trace window.</span></span> <span data-ttu-id="386bb-120">In caso contrario, la guida di piano creata potrebbe non corrispondere al batch originale.</span><span class="sxs-lookup"><span data-stu-id="386bb-120">This might cause the plan guide that you create to not match the original batch.</span></span>  
  
6.  <span data-ttu-id="386bb-121">Salvare i dati degli eventi in un file.</span><span class="sxs-lookup"><span data-stu-id="386bb-121">Save the event data to a file.</span></span> <span data-ttu-id="386bb-122">Si ottiene in tal modo il testo del batch.</span><span class="sxs-lookup"><span data-stu-id="386bb-122">This is the batch text.</span></span>  
  
7.  <span data-ttu-id="386bb-123">Aprire il file del testo del batch nel Blocco note e copiare il testo.</span><span class="sxs-lookup"><span data-stu-id="386bb-123">Open the batch text file in Notepad and copy the text to the copy and paste buffer.</span></span>  
  
8.  <span data-ttu-id="386bb-124">Creare la guida di piano e incollare il testo copiato tra le virgolette (**"**) specificate per l'argomento **@stmt** .</span><span class="sxs-lookup"><span data-stu-id="386bb-124">Create the plan guide and paste the copied text inside the quotation marks (**''**) specified for the **@stmt** argument.</span></span> <span data-ttu-id="386bb-125">È necessario usare caratteri di escape per ogni virgoletta singola nell' **@stmt** argomento facendola precedere da un'altra virgoletta singola.</span><span class="sxs-lookup"><span data-stu-id="386bb-125">You must escape any single quotation marks in the **@stmt** argument by preceding them with another single quotation mark.</span></span> <span data-ttu-id="386bb-126">Fare attenzione a non aggiungere o rimuovere altri caratteri quando si inseriscono queste virgolette.</span><span class="sxs-lookup"><span data-stu-id="386bb-126">Be careful not to add or remove any other characters when you insert these single quotation marks.</span></span> <span data-ttu-id="386bb-127">Ad esempio, il valore letterale di data **'** 20000101 **'** deve essere delimitato come **''** 20000101 **''** .</span><span class="sxs-lookup"><span data-stu-id="386bb-127">For example, the date literal **'** 20000101 **'** must be delimited as **''** 20000101 **''**.</span></span>  
  
 <span data-ttu-id="386bb-128">La guida di piano ottenuta è la seguente:</span><span class="sxs-lookup"><span data-stu-id="386bb-128">Here is the plan guide:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'MyGuide1',  
    @stmt = N'<paste the text copied from the batch text file here>',  
    @type = N'SQL',  
    @module_or_batch = NULL,  
    @params = NULL,  
    @hints = N'OPTION (MERGE JOIN)';  
```  
  
## <a name="testing-plan-guides-by-using-sql-server-profiler"></a><span data-ttu-id="386bb-129">Test della guida di piano tramite SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="386bb-129">Testing Plan Guides by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="386bb-130">Per verificare la corrispondenza tra una guida di piano e una query, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="386bb-130">To verify that a plan guide is being matched to a query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="386bb-131">Avviare una traccia di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] verificando che sia selezionato il tipo di evento **Showplan XML** , disponibile nel nodo **Performance** .</span><span class="sxs-lookup"><span data-stu-id="386bb-131">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making certain that the **Showplan XML** event type is selected (located under the **Performance** node).</span></span>  
  
2.  <span data-ttu-id="386bb-132">Eseguire la query dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="386bb-132">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="386bb-133">Sospendere la traccia di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="386bb-133">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="386bb-134">Trovare l'evento **Showplan XML** relativo alla query interessata.</span><span class="sxs-lookup"><span data-stu-id="386bb-134">Find the **Showplan XML** event for the affected query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="386bb-135">L'evento **Showplan XML for Query Compile** non può essere usato.</span><span class="sxs-lookup"><span data-stu-id="386bb-135">The **Showplan XML for Query Compile** event cannot be used.</span></span> <span data-ttu-id="386bb-136">**PlanGuideDB** non esiste nell'evento in questione.</span><span class="sxs-lookup"><span data-stu-id="386bb-136">**PlanGuideDB** does not exist in that event.</span></span>  
  
5.  <span data-ttu-id="386bb-137">Se la guida di piano è di tipo OBJECT o SQL, verificare che nell'evento **Showplan XML** siano contenuti gli attributi **PlanGuideDB** e **PlanGuideName** per la guida di piano che si prevedeva corrispondesse alla query.</span><span class="sxs-lookup"><span data-stu-id="386bb-137">If the plan guide is of type OBJECT or SQL, verify that the **Showplan XML** event contains the **PlanGuideDB** and **PlanGuideName** attributes for the plan guide that you expected to match the query.</span></span> <span data-ttu-id="386bb-138">In alternativa, se la guida di piano è di tipo TEMPLATE, verificare che l'evento **Showplan XML** contenga gli attributi **TemplatePlanGuideDB** e **TemplatePlanGuideName** per la guida di piano prevista.</span><span class="sxs-lookup"><span data-stu-id="386bb-138">Or, in the case of a TEMPLATE plan guide, verify that the **Showplan XML** event contains the **TemplatePlanGuideDB** and **TemplatePlanGuideName** attributes for the expected plan guide.</span></span> <span data-ttu-id="386bb-139">Se tali attributi sono presenti, la guida di piano funziona regolarmente.</span><span class="sxs-lookup"><span data-stu-id="386bb-139">This verifies that the plan guide is working.</span></span> <span data-ttu-id="386bb-140">Questi attributi sono contenuti nell'elemento **\<StmtSimple>** del piano.</span><span class="sxs-lookup"><span data-stu-id="386bb-140">These attributes are contained under the **\<StmtSimple>** element of the plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="386bb-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="386bb-141">See Also</span></span>  
 [<span data-ttu-id="386bb-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="386bb-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)  
  
  
