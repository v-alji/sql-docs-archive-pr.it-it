---
title: 'Lezione 10: creare gerarchie | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e2561d3-4890-4495-a9cd-84eb88508938
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d0982a05c37c28167e44e3f9f082ea5113b59bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715855"
---
# <a name="lesson-10-create-hierarchies"></a><span data-ttu-id="fb2d5-102">Lezione 10: Creare gerarchie</span><span class="sxs-lookup"><span data-stu-id="fb2d5-102">Lesson 10: Create Hierarchies</span></span>
  <span data-ttu-id="fb2d5-103">In questa lezione si procederà alla creazione di gerarchie.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-103">In this lesson, you will create hierarchies.</span></span> <span data-ttu-id="fb2d5-104">Le gerarchie sono gruppi di colonne disposti in livelli. Una gerarchia Geografia potrebbe ad esempio includere i sottolivelli Paese, Stato, Regione e Città.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-104">Hierarchies are groups of columns arranged in levels; for example, a Geography hierarchy might have sub-levels for Country, State, County, and City.</span></span> <span data-ttu-id="fb2d5-105">Le gerarchie possono essere visualizzate separatamente da altre colonne in un elenco di campi dell'applicazione client per la creazione di report, in modo che sia più semplice per gli utenti del client individuare i campi appropriati da includere in un report.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-105">Hierarchies can appear separate from other columns in a reporting client application field list, making them easier for client users to navigate and include in a report.</span></span> <span data-ttu-id="fb2d5-106">Per altre informazioni, vedere [Gerarchie &#40;SSAS tabulare&#41;](tabular-models/hierarchies-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="fb2d5-106">To learn more, see [Hierarchies &#40;SSAS Tabular&#41;](tabular-models/hierarchies-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="fb2d5-107">Per creare le gerarchi viene usata la funzionalità Progettazione modelli in *Vista diagramma*.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-107">To create hierarchies, you will use the model designer in *Diagram View*.</span></span> <span data-ttu-id="fb2d5-108">La creazione e la gestione di gerarchie non sono supportate in Progettazione modelli in Vista dati.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-108">Creating and managing hierarchies is not supported in the model designer in Data View.</span></span>  
  
 <span data-ttu-id="fb2d5-109">Tempo previsto per il completamento della lezione: **20 minuti**</span><span class="sxs-lookup"><span data-stu-id="fb2d5-109">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fb2d5-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fb2d5-110">Prerequisites</span></span>  
 <span data-ttu-id="fb2d5-111">Questo argomento fa parte di un'esercitazione sulla creazione di modelli tabulari, con lezioni che è consigliabile completare nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="fb2d5-112">Prima di eseguire le attività in questa lezione è necessario aver completato la lezione precedente: [Lezione 9: Creare prospettive](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="fb2d5-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
## <a name="create-hierarchies"></a><span data-ttu-id="fb2d5-113">Creare gerarchie</span><span class="sxs-lookup"><span data-stu-id="fb2d5-113">Create Hierarchies</span></span>  
  
#### <a name="to-create-a-category-hierarchy-in-the-product-table"></a><span data-ttu-id="fb2d5-114">Per creare una gerarchia Category nella tabella Product</span><span class="sxs-lookup"><span data-stu-id="fb2d5-114">To create a Category hierarchy in the Product table</span></span>  
  
1.  <span data-ttu-id="fb2d5-115">In Progettazione modelli fare clic sul `Model` menu, scegliere **vista modelli**, quindi fare clic su **vista diagramma**.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-115">In the model designer, click on the `Model` menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="fb2d5-116">Utilizzare i controlli della mini mappa in alto a destra in Progettazione modelli per modificare la modalità di visualizzazione degli oggetti nella vista diagramma.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-116">Use the Minimap controls at the top-right of the model designer to change how you can view objects in Diagram View.</span></span> <span data-ttu-id="fb2d5-117">Se si riposizionano gli oggetti nella vista diagramma, la vista verrà mantenuta quando si salva il progetto.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-117">If you reposition objects in Diagram View, that view will be retained when you save the project.</span></span>  
  
2.  <span data-ttu-id="fb2d5-118">In Progettazione modelli fare clic con il pulsante destro del mouse sulla `Product` tabella, quindi scegliere **Crea gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-118">In the model designer, right-click the `Product` table, and then click **Create Hierarchy**.</span></span> <span data-ttu-id="fb2d5-119">Verrà visualizzata una nuova gerarchia nella parte inferiore della finestra della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-119">A new hierarchy appears at the bottom of the table window.</span></span>  
  
3.  <span data-ttu-id="fb2d5-120">Nel nome della gerarchia rinominare la gerarchia digitando `Category` e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-120">In the hierarchy name, rename the hierarchy by typing `Category`, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="fb2d5-121">Nella `Product` tabella fare clic sulla colonna **Product Category Name** , quindi trascinarla nella `Category` gerarchia e quindi rilasciare il pulsante sopra il `Category` nome.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-121">In the `Product` table, click the **Product Category Name** column, then drag it to the `Category` hierarchy, and then release on top of the `Category` name.</span></span>  
  
5.  <span data-ttu-id="fb2d5-122">Nella `Category` gerarchia, fare clic con il pulsante destro del mouse sulla colonna **Product Category Name** , scegliere **Rinomina**, quindi digitare `Category` .</span><span class="sxs-lookup"><span data-stu-id="fb2d5-122">In the `Category` hierarchy, right-click the **Product Category Name** column, then click **Rename**, and then type `Category`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb2d5-123">La ridenominazione di una colonna in una gerarchia non comporta la ridenominazione della colonna nella tabella.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-123">Renaming a column in a hierarchy does not rename that column in the table.</span></span> <span data-ttu-id="fb2d5-124">Una colonna in una gerarchia è solo una rappresentazione della colonna nella tabella.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-124">A column in a hierarchy is just a representation of the column in the table.</span></span>  
  
6.  <span data-ttu-id="fb2d5-125">Nella `Product` tabella fare clic con il pulsante destro del mouse sulla colonna **Product Subcategory Name** , scegliere **Aggiungi a gerarchia**dal menu di scelta rapida e quindi fare clic su `Category` .</span><span class="sxs-lookup"><span data-stu-id="fb2d5-125">In the `Product` table, right-click the **Product Subcategory Name** column, then in the context menu, point to **Add to Hierarchy**, and then click `Category`.</span></span>  
  
7.  <span data-ttu-id="fb2d5-126">Rinominare **Product Subcategory Name** in `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="fb2d5-126">Rename **Product Subcategory Name** to `Subcategory`.</span></span>  
  
8.  <span data-ttu-id="fb2d5-127">Utilizzando clic e trascina o utilizzando il comando **Aggiungi a gerarchia** nel menu di scelta rapida, aggiungere le colonne **nome modello** e **nome prodotto** (in ordine) e posizionarle sotto la colonna **Product Subcategory Name** .</span><span class="sxs-lookup"><span data-stu-id="fb2d5-127">By using click and drag, or by using the **Add to Hierarchy** command in the context menu, add the **Model Name** and **Product Name** columns (in order) and place them beneath the **Product Subcategory Name** column.</span></span> <span data-ttu-id="fb2d5-128">Rinominare queste colonne `Model` e `Product` , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-128">Rename these columns `Model` and `Product`, respectively.</span></span>  
  
#### <a name="to-create-hierarchies-in-the-date-table"></a><span data-ttu-id="fb2d5-129">Per creare gerarchie nella tabella Date</span><span class="sxs-lookup"><span data-stu-id="fb2d5-129">To create hierarchies in the Date table</span></span>  
  
1.  <span data-ttu-id="fb2d5-130">In Progettazione modelli fare clic con il pulsante destro del mouse sulla tabella **Date** e scegliere **Crea gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-130">In the model designer, right-click the **Date** table, and then click **Create Hierarchy**.</span></span>  
  
2.  <span data-ttu-id="fb2d5-131">Rinominare la gerarchia in **Calendar**.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-131">Rename the hierarchy to **Calendar**.</span></span>  
  
3.  <span data-ttu-id="fb2d5-132">Aggiungere le colonne seguenti, in ordine, quindi rinominarle:</span><span class="sxs-lookup"><span data-stu-id="fb2d5-132">Add the following columns, in-order, and then rename them:</span></span>  
  
    |<span data-ttu-id="fb2d5-133">Colonna</span><span class="sxs-lookup"><span data-stu-id="fb2d5-133">Column</span></span>|<span data-ttu-id="fb2d5-134">Rinominare in:</span><span class="sxs-lookup"><span data-stu-id="fb2d5-134">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="fb2d5-135">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="fb2d5-135">Calendar Year</span></span>|<span data-ttu-id="fb2d5-136">Year</span><span class="sxs-lookup"><span data-stu-id="fb2d5-136">Year</span></span>|  
    |<span data-ttu-id="fb2d5-137">Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="fb2d5-137">Calendar Semester</span></span>|<span data-ttu-id="fb2d5-138">Semester</span><span class="sxs-lookup"><span data-stu-id="fb2d5-138">Semester</span></span>|  
    |<span data-ttu-id="fb2d5-139">Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="fb2d5-139">Calendar Quarter</span></span>|<span data-ttu-id="fb2d5-140">Quarter</span><span class="sxs-lookup"><span data-stu-id="fb2d5-140">Quarter</span></span>|  
    |<span data-ttu-id="fb2d5-141">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="fb2d5-141">Month Calendar</span></span>|<span data-ttu-id="fb2d5-142">Month</span><span class="sxs-lookup"><span data-stu-id="fb2d5-142">Month</span></span>|  
    |<span data-ttu-id="fb2d5-143">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="fb2d5-143">Day Of Month</span></span>|<span data-ttu-id="fb2d5-144">Giorno</span><span class="sxs-lookup"><span data-stu-id="fb2d5-144">Day</span></span>|  
  
4.  <span data-ttu-id="fb2d5-145">Nella tabella **Date** ripetere i passaggi precedenti, creando una gerarchia **Fiscal** e includendo le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb2d5-145">In the **Date** table, repeat the above steps, creating a **Fiscal** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="fb2d5-146">Colonna</span><span class="sxs-lookup"><span data-stu-id="fb2d5-146">Column</span></span>|<span data-ttu-id="fb2d5-147">Rinominare in:</span><span class="sxs-lookup"><span data-stu-id="fb2d5-147">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="fb2d5-148">Fiscal Year</span><span class="sxs-lookup"><span data-stu-id="fb2d5-148">Fiscal Year</span></span>|<span data-ttu-id="fb2d5-149">Year</span><span class="sxs-lookup"><span data-stu-id="fb2d5-149">Year</span></span>|  
    |<span data-ttu-id="fb2d5-150">Fiscal Semester</span><span class="sxs-lookup"><span data-stu-id="fb2d5-150">Fiscal Semester</span></span>|<span data-ttu-id="fb2d5-151">Semester</span><span class="sxs-lookup"><span data-stu-id="fb2d5-151">Semester</span></span>|  
    |<span data-ttu-id="fb2d5-152">Fiscal Quarter</span><span class="sxs-lookup"><span data-stu-id="fb2d5-152">Fiscal Quarter</span></span>|<span data-ttu-id="fb2d5-153">Quarter</span><span class="sxs-lookup"><span data-stu-id="fb2d5-153">Quarter</span></span>|  
    |<span data-ttu-id="fb2d5-154">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="fb2d5-154">Month Calendar</span></span>|<span data-ttu-id="fb2d5-155">Month</span><span class="sxs-lookup"><span data-stu-id="fb2d5-155">Month</span></span>|  
    |<span data-ttu-id="fb2d5-156">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="fb2d5-156">Day Of Month</span></span>|<span data-ttu-id="fb2d5-157">Giorno</span><span class="sxs-lookup"><span data-stu-id="fb2d5-157">Day</span></span>|  
  
5.  <span data-ttu-id="fb2d5-158">Infine, nella tabella **Date** ripetere i passaggi precedenti, creando una gerarchia **Production Calendar** e includendo le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb2d5-158">Finally, in the **Date** table, repeat the above steps, creating a **Production Calendar** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="fb2d5-159">Colonna</span><span class="sxs-lookup"><span data-stu-id="fb2d5-159">Column</span></span>|<span data-ttu-id="fb2d5-160">Rinominare in:</span><span class="sxs-lookup"><span data-stu-id="fb2d5-160">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="fb2d5-161">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="fb2d5-161">Calendar Year</span></span>|<span data-ttu-id="fb2d5-162">Year</span><span class="sxs-lookup"><span data-stu-id="fb2d5-162">Year</span></span>|  
    |<span data-ttu-id="fb2d5-163">Week Number Of Year</span><span class="sxs-lookup"><span data-stu-id="fb2d5-163">Week Number Of Year</span></span>|<span data-ttu-id="fb2d5-164">Settimana</span><span class="sxs-lookup"><span data-stu-id="fb2d5-164">Week</span></span>|  
    |<span data-ttu-id="fb2d5-165">Day Of Week</span><span class="sxs-lookup"><span data-stu-id="fb2d5-165">Day Of Week</span></span>|<span data-ttu-id="fb2d5-166">Giorno</span><span class="sxs-lookup"><span data-stu-id="fb2d5-166">Day</span></span>|  
  
## <a name="next-steps"></a><span data-ttu-id="fb2d5-167">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fb2d5-167">Next Steps</span></span>  
 <span data-ttu-id="fb2d5-168">Per continuare questa esercitazione, passare alla lezione successiva: [Lezione 11: Creare partizioni](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="fb2d5-168">To continue this tutorial, go to the next lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
  
