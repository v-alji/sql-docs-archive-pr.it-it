---
title: 'Lezione 11: creare partizioni | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 92eb21a8-5fc4-4999-ad37-1332ce26431d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4db5edd5d47fe424ef6e6ad2a822106110209059
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623554"
---
# <a name="lesson-11-create-partitions"></a><span data-ttu-id="c4c74-102">Lezione 11: Creare partizioni</span><span class="sxs-lookup"><span data-stu-id="c4c74-102">Lesson 11: Create Partitions</span></span>
  <span data-ttu-id="c4c74-103">In questa lezione verranno create partizioni per dividere la tabella Internet Sales in parti logiche più piccole, che possono essere elaborate (aggiornate) indipendentemente dalle altre partizioni.</span><span class="sxs-lookup"><span data-stu-id="c4c74-103">In this lesson, you will create partitions to divide the Internet Sales table into smaller logical parts that can be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="c4c74-104">Per impostazione predefinita, ogni tabella inclusa nel modello dispone di una partizione che include tutte le colonne e le righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="c4c74-104">By default, every table you include in your model has one partition which includes all of the table's columns and rows.</span></span> <span data-ttu-id="c4c74-105">Per la tabella Internet Sales, si desidera dividere i dati in base all'anno. una partizione per ognuno dei cinque anni della tabella.</span><span class="sxs-lookup"><span data-stu-id="c4c74-105">For the Internet Sales table, we want to divide the data by year; one partition for each of the table's five years.</span></span>  <span data-ttu-id="c4c74-106">Ogni partizione può quindi essere elaborata in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="c4c74-106">Each partition can then be processed independently.</span></span> <span data-ttu-id="c4c74-107">Per altre informazioni, vedere [Partizioni &#40;SSAS tabulare&#41;](tabular-models/partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c4c74-107">To learn more, see [Partitions &#40;SSAS Tabular&#41;](tabular-models/partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="c4c74-108">Tempo previsto per il completamento della lezione: **15 minuti**</span><span class="sxs-lookup"><span data-stu-id="c4c74-108">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c4c74-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c4c74-109">Prerequisites</span></span>  
 <span data-ttu-id="c4c74-110">Questo argomento fa parte di un'esercitazione sulla creazione di modelli tabulari, con lezioni che è consigliabile completare nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="c4c74-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="c4c74-111">Prima di eseguire le attività in questa lezione è necessario aver completato la lezione precedente: [Lezione 10: Creare gerarchie](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="c4c74-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
## <a name="create-partitions"></a><span data-ttu-id="c4c74-112">Creare partizioni</span><span class="sxs-lookup"><span data-stu-id="c4c74-112">Create Partitions</span></span>  
  
#### <a name="to-create-partitions-in-the-internet-sales-table"></a><span data-ttu-id="c4c74-113">Per creare partizioni nella tabella Internet Sales</span><span class="sxs-lookup"><span data-stu-id="c4c74-113">To create partitions in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="c4c74-114">In Progettazione modelli fare clic sulla tabella **Internet Sales** , quindi scegliere **Partizioni** dal menu **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-114">In the model designer, click on the **Internet Sales** table, then click on the **Table** menu, and then click **Partitions**.</span></span>  
  
     <span data-ttu-id="c4c74-115">Verrà visualizzata la finestra di dialogo **Gestione partizioni** .</span><span class="sxs-lookup"><span data-stu-id="c4c74-115">The **Partition Manager** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c4c74-116">In **partizioni**nella finestra di dialogo **Gestione partizioni** fare clic sulla partizione **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="c4c74-116">In the **Partition Manager** dialog box, in **Partitions**, click the **Internet Sales** partition.</span></span>  
  
3.  <span data-ttu-id="c4c74-117">In **nome partizione**modificare il nome in `Internet Sales 2005` .</span><span class="sxs-lookup"><span data-stu-id="c4c74-117">In **Partition Name**, change the name to `Internet Sales 2005`.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="c4c74-118">Prima di continuare con il passaggio successivo, osservare che per i nomi di colonna nella finestra Anteprima tabella vengono visualizzate le colonne incluse nella tabella del modello (selezionate) con i nomi di colonna dell'origine.</span><span class="sxs-lookup"><span data-stu-id="c4c74-118">Before continuing to the next step, notice the column names in the Table Preview window display those columns included in the model table (checked) with the column names from the source.</span></span> <span data-ttu-id="c4c74-119">Questo si verifica in quanto nella finestra Anteprima tabella vengono visualizzate le colonne della tabella di origine, non quelle della tabella del modello.</span><span class="sxs-lookup"><span data-stu-id="c4c74-119">This is because the Table Preview window displays columns from the source table, not from the model table.</span></span>  
  
4.  <span data-ttu-id="c4c74-120">Fare clic sul pulsante **Editor di query** nella parte superiore destra della finestra di anteprima.</span><span class="sxs-lookup"><span data-stu-id="c4c74-120">Select the **Query Editor** button just above the right side of the preview window.</span></span>  
  
     <span data-ttu-id="c4c74-121">Poiché si desidera che la partizione includa solo le righe comprese in un determinato periodo, è necessario includere una clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="c4c74-121">Because you want the partition to include only those rows within a certain period, you must include a WHERE clause.</span></span> <span data-ttu-id="c4c74-122">È possibile creare una clausola WHERE solo tramite un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="c4c74-122">You can only create a WHERE clause by using a SQL Statement.</span></span>  
  
5.  <span data-ttu-id="c4c74-123">Nel campo **Istruzione SQL** sostituire l'istruzione esistente incollando l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="c4c74-123">In the **SQL Statement** field, replace the existing statement by pasting in the following statement:</span></span>  
  
    ```  
    SELECT   
    [dbo].[FactInternetSales].[ProductKey],  
    [dbo].[FactInternetSales].[CustomerKey],  
    [dbo].[FactInternetSales].[PromotionKey],  
    [dbo].[FactInternetSales].[CurrencyKey],  
    [dbo].[FactInternetSales].[SalesTerritoryKey],  
    [dbo].[FactInternetSales].[SalesOrderNumber],  
    [dbo].[FactInternetSales].[SalesOrderLineNumber],  
    [dbo].[FactInternetSales].[RevisionNumber],  
    [dbo].[FactInternetSales].[OrderQuantity],  
    [dbo].[FactInternetSales].[UnitPrice],  
    [dbo].[FactInternetSales].[ExtendedAmount],  
    [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
    [dbo].[FactInternetSales].[DiscountAmount],  
    [dbo].[FactInternetSales].[ProductStandardCost],  
    [dbo].[FactInternetSales].[TotalProductCost],  
    [dbo].[FactInternetSales].[SalesAmount],  
    [dbo].[FactInternetSales].[TaxAmt],  
    [dbo].[FactInternetSales].[Freight],  
    [dbo].[FactInternetSales].[CarrierTrackingNumber],  
    [dbo].[FactInternetSales].[CustomerPONumber],  
    [dbo].[FactInternetSales].[OrderDate],  
    [dbo].[FactInternetSales].[DueDate],  
    [dbo].[FactInternetSales].[ShipDate]   
    FROM [dbo].[FactInternetSales]  
    WHERE (([OrderDate] >= N'2005-01-01 00:00:00') AND ([OrderDate] < N'2006-01-01 00:00:00'))  
    ```  
  
     <span data-ttu-id="c4c74-124">Questa istruzione specifica che la partizione deve includere tutti i dati delle righe in cui OrderDate si riferisce all'anno di calendario 2005, come specificato nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="c4c74-124">This statement specifies the partition should include all of the data in those rows where the OrderDate is for the 2005 calendar year as specified in the WHERE clause.</span></span>  
  
6.  <span data-ttu-id="c4c74-125">Fare clic su **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-125">Click **Validate**.</span></span>  
  
     <span data-ttu-id="c4c74-126">Si noti che viene visualizzato un avviso che indica che alcune colonne non sono presenti nell'origine.</span><span class="sxs-lookup"><span data-stu-id="c4c74-126">Notice a warning is displayed stating that certain columns are not present in source.</span></span> <span data-ttu-id="c4c74-127">Ciò è dovuto al fatto che nella [lezione 3: rinominare le colonne](rename-columns.md)sono state rinominate le colonne della tabella Internet Sales nel modello in modo che siano diverse dalle stesse colonne nell'origine.</span><span class="sxs-lookup"><span data-stu-id="c4c74-127">This is because in [Lesson 3: Rename Columns](rename-columns.md), you renamed those columns in the Internet Sales table in the model to be different from those same columns at the source.</span></span>  
  
#### <a name="to-create-a-partition-for-the-2006-year-in-the-internet-sales-table"></a><span data-ttu-id="c4c74-128">Per creare una partizione per l'anno 2006 nella tabella Internet Sales</span><span class="sxs-lookup"><span data-stu-id="c4c74-128">To create a partition for the 2006 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="c4c74-129">In **partizioni**nella finestra di dialogo **Gestione partizioni** fare clic sulla `Internet Sales 2005` partizione appena creata e quindi su **copia**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-129">In the **Partition Manager** dialog box, in **Partitions**, click the `Internet Sales 2005` partition you just created, and then **Copy**.</span></span>  
  
2.  <span data-ttu-id="c4c74-130">In **nome partizione**Digitare `Internet Sales 2006` .</span><span class="sxs-lookup"><span data-stu-id="c4c74-130">In **Partition Name**, type `Internet Sales 2006`.</span></span>  
  
3.  <span data-ttu-id="c4c74-131">Nell'istruzione SQL, affinché nella partizione siano incluse solo le righe per l'anno 2006, sostituire la clausola WHERE con la seguente:</span><span class="sxs-lookup"><span data-stu-id="c4c74-131">In the SQL Statement, in-order for the partition to include only those rows for the 2006 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2006-01-01 00:00:00') AND ([OrderDate] < N'2007-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2007-year-in-the-internet-sales-table"></a><span data-ttu-id="c4c74-132">Per creare una partizione per l'anno 2007 nella tabella Internet Sales</span><span class="sxs-lookup"><span data-stu-id="c4c74-132">To create a partition for the 2007 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="c4c74-133">Nella finestra di dialogo **Gestione partizioni** fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-133">In the **Partition Manager** dialog box, click **Copy**.</span></span>  
  
2.  <span data-ttu-id="c4c74-134">In **nome partizione**Digitare `Internet Sales 2007` .</span><span class="sxs-lookup"><span data-stu-id="c4c74-134">In **Partition Name**, type `Internet Sales 2007`.</span></span>  
  
3.  <span data-ttu-id="c4c74-135">In **passa a**selezionare **Editor query**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-135">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="c4c74-136">Nell'istruzione SQL, affinché nella partizione siano incluse solo le righe per l'anno 2007, sostituire la clausola WHERE con la seguente:</span><span class="sxs-lookup"><span data-stu-id="c4c74-136">In the SQL Statement, in-order for the partition to include only those rows for the 2007 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2007-01-01 00:00:00') AND ([OrderDate] < N'2008-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2008-year-in-the-internet-sales-table"></a><span data-ttu-id="c4c74-137">Per creare una partizione per l'anno 2008 nella tabella Internet Sales</span><span class="sxs-lookup"><span data-stu-id="c4c74-137">To create a partition for the 2008 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="c4c74-138">Nella finestra di dialogo **Gestione partizioni** fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-138">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="c4c74-139">In **nome partizione**Digitare `Internet Sales 2008` .</span><span class="sxs-lookup"><span data-stu-id="c4c74-139">In **Partition Name**, type `Internet Sales 2008`.</span></span>  
  
3.  <span data-ttu-id="c4c74-140">In **passa a**selezionare **Editor query**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-140">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="c4c74-141">Nell'istruzione SQL, affinché nella partizione siano incluse solo le righe per l'anno 2008, sostituire la clausola WHERE con la seguente:</span><span class="sxs-lookup"><span data-stu-id="c4c74-141">In the SQL Statement, in-order for the partition to include only those rows for the 2008 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2008-01-01 00:00:00') AND ([OrderDate] < N'2009-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2009-year-in-the-internet-sales-table"></a><span data-ttu-id="c4c74-142">Per creare una partizione per l'anno 2009 nella tabella Internet Sales</span><span class="sxs-lookup"><span data-stu-id="c4c74-142">To create a partition for the 2009 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="c4c74-143">Nella finestra di dialogo **Gestione partizioni** fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-143">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="c4c74-144">In **nome partizione**Digitare `Internet Sales 2009` .</span><span class="sxs-lookup"><span data-stu-id="c4c74-144">In **Partition Name**, type `Internet Sales 2009`.</span></span>  
  
3.  <span data-ttu-id="c4c74-145">In **passa a**selezionare **Editor query**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-145">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="c4c74-146">Nell'istruzione SQL, affinché nella partizione siano incluse solo le righe per l'anno 2009, sostituire la clausola WHERE con la seguente:</span><span class="sxs-lookup"><span data-stu-id="c4c74-146">In the SQL Statement, in-order for the partition to include only those rows for the 2009 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2009-01-01 00:00:00') AND ([OrderDate] < N'2010-01-01 00:00:00'))  
    ```  
  
## <a name="process-partitions"></a><span data-ttu-id="c4c74-147">Elaborare le partizioni</span><span class="sxs-lookup"><span data-stu-id="c4c74-147">Process Partitions</span></span>  
 <span data-ttu-id="c4c74-148">Nella finestra di dialogo **Gestione partizioni** , notare l'asterisco (**\***) accanto ai nomi di partizione per ognuna delle nuove partizioni appena create.</span><span class="sxs-lookup"><span data-stu-id="c4c74-148">In the **Partition Manager** dialog box, notice the asterisk (**\***) next to the partition names for each of the new partitions you just created.</span></span> <span data-ttu-id="c4c74-149">L'asterisco indica che la partizione non è stata elaborata (aggiornata).</span><span class="sxs-lookup"><span data-stu-id="c4c74-149">This indicates that the partition has not been processed (refreshed).</span></span> <span data-ttu-id="c4c74-150">Quando si creano nuove partizioni, è necessario eseguire un'operazione di elaborazione delle partizioni o della tabella per aggiornare i dati nelle partizioni.</span><span class="sxs-lookup"><span data-stu-id="c4c74-150">When you create new partitions, you should run a Process Partitions or Process Table operation to refresh the data in those partitions.</span></span>  
  
#### <a name="to-process-internet-sales-partitions"></a><span data-ttu-id="c4c74-151">Per elaborare le partizioni di Internet Sales</span><span class="sxs-lookup"><span data-stu-id="c4c74-151">To process Internet Sales partitions</span></span>  
  
1.  <span data-ttu-id="c4c74-152">Fare clic su **OK** per chiudere la finestra di dialogo **Gestione partizioni** .</span><span class="sxs-lookup"><span data-stu-id="c4c74-152">Click **OK** to close the **Partition Manager** dialog box.</span></span>  
  
2.  <span data-ttu-id="c4c74-153">In Progettazione modelli fare clic sulla tabella **Internet Sales** , scegliere **Elabora** (Aggiorna) nel menu **Modello** , quindi fare clic su **Elabora partizioni**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-153">In the model designer, click the **Internet Sales** table, then click the **Model** menu, then point to **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
3.  <span data-ttu-id="c4c74-154">Nella finestra di dialogo **Elabora partizioni** verificare che l'opzione **Modalità** sia impostata su **Elaborazione predefinita**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-154">In the **Process Partitions** dialog box, verify the **Mode** is set to **Process Default**.</span></span>  
  
4.  <span data-ttu-id="c4c74-155">Selezionare la casella di controllo **Elaborazione** per ognuna delle cinque partizioni create e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4c74-155">Select the checkbox in the **Process** column for each of the five partitions you created, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c4c74-156">Se vengono richieste le credenziali di rappresentazione, immettere il nome utente e la password di Windows specificati al passaggio 6 della lezione 2.</span><span class="sxs-lookup"><span data-stu-id="c4c74-156">If you are prompted for Impersonation credentials, enter the Windows user name and password you specified in Lesson 2, step 6.</span></span>  
  
     <span data-ttu-id="c4c74-157">Verrà visualizzata la finestra di dialogo **elaborazione dati** con i dettagli del processo per ogni partizione.</span><span class="sxs-lookup"><span data-stu-id="c4c74-157">The **Data Process** dialog box then appears and displays process details for each partition.</span></span> <span data-ttu-id="c4c74-158">Si noti che per ogni partizione viene trasferito un numero diverso di righe.</span><span class="sxs-lookup"><span data-stu-id="c4c74-158">Notice that a different number of rows for each partition are transferred.</span></span> <span data-ttu-id="c4c74-159">Questo avviene in quanto ogni partizione include solo le righe per l'anno specificato nella clausola WHERE dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="c4c74-159">This is because each partition includes only those rows for the year specified in the WHERE clause in the SQL Statement.</span></span> <span data-ttu-id="c4c74-160">Non vi sono dati per l'anno 2010.</span><span class="sxs-lookup"><span data-stu-id="c4c74-160">There is no data for the 2010 year.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c4c74-161">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c4c74-161">Next Steps</span></span>  
 <span data-ttu-id="c4c74-162">Per continuare questa esercitazione, passare alla lezione successiva: [Lezione 12: Creare ruoli](lesson-11-create-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c4c74-162">To continue this tutorial, go to the next lesson: Lesson: [Lesson 12: Create Roles](lesson-11-create-roles.md).</span></span>  
  
  
