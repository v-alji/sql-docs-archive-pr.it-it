---
title: 'Lezione 6: creare colonne calcolate | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d126766a-5699-4e9f-8213-8c7eea0fc14e
author: minewiskan
ms.author: owend
ms.openlocfilehash: dcebf61955e230c9e61c955683b897026553cb52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627500"
---
# <a name="lesson-6-create-calculated-columns"></a><span data-ttu-id="e9dd5-102">Lezione 6: Creare colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="e9dd5-102">Lesson 6: Create Calculated Columns</span></span>
  <span data-ttu-id="e9dd5-103">In questa lezione verranno creati nuovi dati nel modello aggiungendo colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-103">In this lesson, you will create new data in your model by adding calculated columns.</span></span> <span data-ttu-id="e9dd5-104">Una colonna calcolata è basata sui dati già presenti nel modello.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-104">A calculated column is based on data that already exists in the model.</span></span> <span data-ttu-id="e9dd5-105">Per altre informazioni, vedere [Colonne calcolate &#40;SSAS tabulare&#41;](tabular-models/ssas-calculated-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e9dd5-105">To learn more, see [Calculated Columns &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns.md).</span></span>  
  
 <span data-ttu-id="e9dd5-106">Verranno create cinque nuove colonne calcolate in tre tabelle diverse.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-106">You will create five new calculated columns in three different tables.</span></span> <span data-ttu-id="e9dd5-107">I passaggi sono leggermente diversi per ogni attività.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-107">The steps are slightly different for each task.</span></span> <span data-ttu-id="e9dd5-108">L'obiettivo è quello di mostrare che vi sono diversi metodi per creare nuove colonne, rinominarle e collocarle in diverse posizioni in una tabella.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-108">This is to show you there are several ways to create new columns, rename them, and place them in various locations in a table.</span></span>  
  
 <span data-ttu-id="e9dd5-109">Tempo previsto per il completamento della lezione: **15 minuti**</span><span class="sxs-lookup"><span data-stu-id="e9dd5-109">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e9dd5-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e9dd5-110">Prerequisites</span></span>  
 <span data-ttu-id="e9dd5-111">Questo argomento fa parte di un'esercitazione sulla creazione di modelli tabulari, con lezioni che è consigliabile completare nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="e9dd5-112">Prima di eseguire le attività in questa lezione è necessario aver completato la lezione precedente: [Lezione 5: Creare relazioni](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="e9dd5-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
## <a name="create-calculated-columns"></a><span data-ttu-id="e9dd5-113">Creare colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="e9dd5-113">Create Calculated Columns</span></span>  
  
#### <a name="create-a-month-calendar-calculated-column-in-the-date-table"></a><span data-ttu-id="e9dd5-114">Creare una colonna calcolata Month Calendar nella tabella Date</span><span class="sxs-lookup"><span data-stu-id="e9dd5-114">Create a Month Calendar calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="e9dd5-115">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]scegliere **Vista modelli** nel menu **Modello**, quindi fare clic su **Vista dati**.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-115">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Model View**, and then click **Data View**.</span></span>  
  
     <span data-ttu-id="e9dd5-116">Le colonne calcolate possono essere create solo tramite Progettazione modelli in Vista dati.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-116">Calculated columns can only be created by using the model designer in Data View.</span></span>  
  
2.  <span data-ttu-id="e9dd5-117">In Progettazione modelli fare clic sulla tabella (scheda) **Data** .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-117">In the model designer, click the **Date** table (tab).</span></span>  
  
3.  <span data-ttu-id="e9dd5-118">Fare clic con il pulsante destro del mouse sulla colonna **Calendar Quarter** , quindi scegliere **Inserisci colonna**.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-118">Right-click the **Calendar Quarter** column, and then click **Insert Column**.</span></span>  
  
     <span data-ttu-id="e9dd5-119">Una nuova colonna denominata **CalculatedColumn1** verrà inserita a sinistra della colonna **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-119">A new column named **CalculatedColumn1** is inserted to the left of the **Calendar Quarter** column.</span></span>  
  
4.  <span data-ttu-id="e9dd5-120">Sulla barra della formula sopra la tabella digitare la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-120">In the formula bar above the table, type the following formula.</span></span> <span data-ttu-id="e9dd5-121">La funzionalità Completamento automatico è utile per digitare correttamente i nomi completi di colonne e tabelle ed elenca le funzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-121">AutoComplete helps you type the fully qualified names of columns and tables, and lists the functions that are available.</span></span>  
  
     `=RIGHT(" " & FORMAT([Month],"#0"), 2) & " - " & [Month Name]`  
  
     <span data-ttu-id="e9dd5-122">Dopo avere completato la compilazione della formula, premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-122">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="e9dd5-123">I valori vengono quindi popolati per tutte le righe nella colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-123">Values are then populated for all the rows in the calculated column.</span></span> <span data-ttu-id="e9dd5-124">Se si scorre verso il basso nella tabella, si noterà che le righe possono avere valori diversi per questa colonna, in base ai dati in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-124">If you scroll down through the table, you will see that rows can have different values for this column, based on the data that is in each row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e9dd5-125">Se viene visualizzato un errore, verificare che i nomi di colonna nella formula corrispondano ai nomi di colonna modificati in [Lezione 3: Rinominare colonne](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e9dd5-125">If you receive an error, verify the column names in the formula match the column names you changed in [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
5.  <span data-ttu-id="e9dd5-126">Rinominare la colonna in `Month Calendar` .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-126">Rename this column to `Month Calendar`.</span></span>  
  
 <span data-ttu-id="e9dd5-127">La colonna calcolata Month Calendar fornisce un nome ordinabile per il mese.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-127">The Month Calendar calculated column provides a sortable name for Month.</span></span>  
  
#### <a name="create-a-day-of-week-calculated-column-in-the-date-table"></a><span data-ttu-id="e9dd5-128">Creare una colonna calcolata Day of Week nella tabella Date</span><span class="sxs-lookup"><span data-stu-id="e9dd5-128">Create a Day of Week calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="e9dd5-129">Con la tabella **Date** ancora attiva, fare clic sul menu **Colonna** , quindi scegliere **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-129">With the **Date** table still active, click on the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="e9dd5-130">Una nuova colonna verrà aggiunta all'estremità destra della tabella.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-130">A new column is added to the far right of the table</span></span>  
  
2.  <span data-ttu-id="e9dd5-131">Nella barra della formula digitare la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="e9dd5-131">In the formula bar, type the following formula:</span></span>  
  
     `=RIGHT(" " & FORMAT([Day Number Of Week],"#0"), 2) & " - " & [Day Name]`  
  
     <span data-ttu-id="e9dd5-132">Dopo avere completato la compilazione della formula, premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="e9dd5-133">Rinominare la colonna in `Day of Week` .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-133">Rename the column to `Day of Week`.</span></span>  
  
4.  <span data-ttu-id="e9dd5-134">Fare clic sull'intestazione di colonna, quindi trascinare la colonna tra le colonne **Day Name** e **Day of Month** .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-134">Click on the column heading, and then drag the column between the **Day Name** column and the **Day of Month** column.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="e9dd5-135">Lo spostamento delle colonne nella tabella semplifica l'esplorazione.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-135">Moving columns in your table makes it easier to navigate.</span></span>  
  
 <span data-ttu-id="e9dd5-136">La colonna calcolata Day of Week fornisce un nome ordinabile per il giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-136">The Day of Week calculated column provides a sortable name for the day of week.</span></span>  
  
#### <a name="create-a-product-subcategory-name-calculated-column-in-the-product-table"></a><span data-ttu-id="e9dd5-137">Creare una colonna calcolata Product Subcategory Name nella tabella Product</span><span class="sxs-lookup"><span data-stu-id="e9dd5-137">Create a Product Subcategory Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="e9dd5-138">In Progettazione modelli selezionare la tabella **Product** .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-138">In the model designer, select the **Product** table.</span></span>  
  
2.  <span data-ttu-id="e9dd5-139">Scorrere fino all'estremità destra della tabella.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-139">Scroll to the far right of the table.</span></span> <span data-ttu-id="e9dd5-140">Si noti che la colonna all'estrema destra è denominata **Aggiungi colonna** (in corsivo). Fare clic sull'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-140">Notice the right-most column is named **Add Column** (italicized), click the column heading.</span></span>  
  
3.  <span data-ttu-id="e9dd5-141">Nella barra della formula digitare la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-141">In the formula bar, type the following formula.</span></span>  
  
     `=RELATED('Product Subcategory'[Product Subcategory Name])`  
  
     <span data-ttu-id="e9dd5-142">Dopo avere completato la compilazione della formula, premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-142">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="e9dd5-143">Rinominare la colonna in `Product Subcategory Name` .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-143">Rename the column to `Product Subcategory Name`.</span></span>  
  
 <span data-ttu-id="e9dd5-144">La colonna calcolata Product Subcategory Name viene utilizzata per creare una gerarchia nella tabella Product, che include dati della colonna Product Subcategory Name della tabella Product Subcategory.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-144">The Product Subcategory Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Subcategory Name column in the Product Subcategory table.</span></span> <span data-ttu-id="e9dd5-145">Le gerarchie non possono essere estese a più di una tabella.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-145">Hierarchies cannot span more than one table.</span></span> <span data-ttu-id="e9dd5-146">La creazione di gerarchie verrà eseguita più avanti, nella lezione 7.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-146">You will create hierarchies later in Lesson 7.</span></span>  
  
#### <a name="create-a-product-category-name-calculated-column-in-the-product-table"></a><span data-ttu-id="e9dd5-147">Creare una colonna calcolata Product Category Name nella tabella Product</span><span class="sxs-lookup"><span data-stu-id="e9dd5-147">Create a Product Category Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="e9dd5-148">Con la tabella **Product** ancora attiva, fare clic sul menu **Colonna** , quindi scegliere **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-148">With the **Product** table still active, click the **Column** menu, and then click **Add Column**.</span></span>  
  
2.  <span data-ttu-id="e9dd5-149">Nella barra della formula digitare la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="e9dd5-149">In the formula bar, type the following formula:</span></span>  
  
     `=RELATED('Product Category'[Product Category Name])`  
  
     <span data-ttu-id="e9dd5-150">Dopo avere completato la compilazione della formula, premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-150">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="e9dd5-151">Rinominare la colonna in `Product Category Name` .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-151">Rename the column to `Product Category Name`.</span></span>  
  
 <span data-ttu-id="e9dd5-152">La colonna calcolata Product Category Name viene utilizzata per creare una gerarchia nella tabella Product, che include dati della colonna Product Category Name della tabella Product Category.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-152">The Product Category Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Category Name column in the Product Category table.</span></span> <span data-ttu-id="e9dd5-153">Le gerarchie non possono essere estese a più di una tabella.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-153">Hierarchies cannot span more than one table.</span></span>  
  
#### <a name="create-a-margin-calculated-column-in-the-internet-sales-table"></a><span data-ttu-id="e9dd5-154">Creare una colonna calcolata Margin nella tabella Internet Sales</span><span class="sxs-lookup"><span data-stu-id="e9dd5-154">Create a Margin calculated column in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="e9dd5-155">In Progettazione modelli selezionare la tabella **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-155">In the model designer, select the **Internet Sales** table.</span></span>  
  
2.  <span data-ttu-id="e9dd5-156">Aggiungere una nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-156">Add a new column.</span></span>  
  
3.  <span data-ttu-id="e9dd5-157">Nella barra della formula digitare la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="e9dd5-157">In the formula bar, type the following formula:</span></span>  
  
     `=[Sales Amount]-[Total Product Cost]`  
  
     <span data-ttu-id="e9dd5-158">Dopo avere completato la compilazione della formula, premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-158">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="e9dd5-159">Rinominare la colonna in `Margin` .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-159">Rename the column to `Margin`.</span></span>  
  
5.  <span data-ttu-id="e9dd5-160">Trascinare la colonna tra le colonne **Sales Amount** e **Tax Amt** .</span><span class="sxs-lookup"><span data-stu-id="e9dd5-160">Drag the column between the **Sales Amount** column and the **Tax Amt** column.</span></span>  
  
 <span data-ttu-id="e9dd5-161">La colonna calcolata Margin viene utilizzata per analizzare i margini di profitto per ogni riga (prodotto).</span><span class="sxs-lookup"><span data-stu-id="e9dd5-161">The Margin calculated column is used to analyze profit margins for each (product) row.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e9dd5-162">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e9dd5-162">Next Step</span></span>  
 <span data-ttu-id="e9dd5-163">Per continuare questa esercitazione, passare alla lezione successiva: [Lezione 7: Creare misure](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="e9dd5-163">To continue this lesson, go to the next lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
  
