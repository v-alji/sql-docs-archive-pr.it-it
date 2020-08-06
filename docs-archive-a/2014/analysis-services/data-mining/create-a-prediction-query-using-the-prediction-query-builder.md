---
title: Creare una query di stima utilizzando il Generatore di query di stima | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- Mining Model Prediction [Analysis Services], prediction queries
ms.assetid: e02836e5-dd8c-4c97-a078-840ae79d3660
author: minewiskan
ms.author: owend
ms.openlocfilehash: 13f39de4085cb74949e9540570d574c09e72ee27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625040"
---
# <a name="create-a-prediction-query-using-the-prediction-query-builder"></a><span data-ttu-id="0f8a3-102">Creare una query di stima utilizzando Generatore query di stima</span><span class="sxs-lookup"><span data-stu-id="0f8a3-102">Create a Prediction Query Using the Prediction Query Builder</span></span>
  <span data-ttu-id="0f8a3-103">È possibile creare query di stima mentre si compila una soluzione di data mining in BI Development Studio, o facendo clic con il pulsante destro del mouse su un modello di data mining esistente in SQL Server Management Studio e scegliendo quindi l'opzione **Compila query di stima**.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-103">You can create prediction queries either while you are building a data mining solution in BI Development Studio, or by right-clicking an existing mining model in SQL Server Management Studio, and then choosing the option, **Build Prediction Query**.</span></span>  
  
 <span data-ttu-id="0f8a3-104">Nel **generatore delle query di stima** sono disponibili tre modalità di progettazione che è possibile alternare facendo clic sulle icone nell'angolo in alto a sinistra.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-104">The **Prediction Query Builder** has the following three design modes, which you can switch among by clicking the icons in the upper-left corner.</span></span>  
  
-   <span data-ttu-id="0f8a3-105">**Progetta**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-105">**Design**</span></span>  
  
-   <span data-ttu-id="0f8a3-106">**Query**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-106">**Query**</span></span>  
  
-   <span data-ttu-id="0f8a3-107">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-107">**Result**</span></span>  
  
 <span data-ttu-id="0f8a3-108">La modalità**Progettazione** consente di compilare una query di stima scegliendo dati di input, eseguendo il mapping dei dati al modello e aggiungendo quindi funzioni di stima in istruzioni compilate tramite la griglia.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-108">**Design** mode lets you build a prediction query by choosing input data, mapping the data to the model, and then adding prediction functions into statements you build by using the grid.</span></span> <span data-ttu-id="0f8a3-109">Nella griglia di progettazione sono presenti questi blocchi predefiniti:</span><span class="sxs-lookup"><span data-stu-id="0f8a3-109">The design grid contains these building blocks:</span></span>  
  
 <span data-ttu-id="0f8a3-110">**Origine**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-110">**Source**</span></span>  
 <span data-ttu-id="0f8a3-111">Scegliere l'origine della nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-111">Choose the source of the new column.</span></span> <span data-ttu-id="0f8a3-112">È possibile utilizzare le colonne del modello di data mining, le tabelle di input incluse nella vista origine dati, una funzione di stima o un'espressione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-112">You can use columns from the mining model, input tables included in the data source view, a prediction function, or a customized expression.</span></span>  
  
 <span data-ttu-id="0f8a3-113">**Campo**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-113">**Field**</span></span>  
 <span data-ttu-id="0f8a3-114">Determina la colonna o funzione specifica associata alla selezione nella colonna **Origine** .</span><span class="sxs-lookup"><span data-stu-id="0f8a3-114">Determines the specific column or function that is associated with the selection in the **Source** column.</span></span>  
  
 <span data-ttu-id="0f8a3-115">**Alias**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-115">**Alias**</span></span>  
 <span data-ttu-id="0f8a3-116">Determina il nome della colonna nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-116">Determines how the column is to be named in the result set.</span></span>  
  
 <span data-ttu-id="0f8a3-117">**Mostra**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-117">**Show**</span></span>  
 <span data-ttu-id="0f8a3-118">Determina se la selezione nella colonna **Origine** viene visualizzata o meno nei risultati.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-118">Determines whether the selection in the **Source** column is displayed in the results.</span></span>  
  
 <span data-ttu-id="0f8a3-119">**Gruppo**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-119">**Group**</span></span>  
 <span data-ttu-id="0f8a3-120">Insieme alla colonna **And/Or** consente di raggruppare espressioni racchiudendole tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-120">Works with the **And/Or** column to group expressions together by using parentheses.</span></span> <span data-ttu-id="0f8a3-121">Ad esempio (espr1 Or espr2) And espr3.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-121">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="0f8a3-122">**E/o**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-122">**And/Or**</span></span>  
 <span data-ttu-id="0f8a3-123">Crea la logica della query.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-123">Creates logic in the query.</span></span> <span data-ttu-id="0f8a3-124">Ad esempio (espr1 Or espr2) And espr3.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-124">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="0f8a3-125">**Criteri/Argomento**</span><span class="sxs-lookup"><span data-stu-id="0f8a3-125">**Criteria/Argument**</span></span>  
 <span data-ttu-id="0f8a3-126">Specifica una condizione o espressione dell'utente per la colonna.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-126">Specifies a condition or user expression that applies to the column.</span></span> <span data-ttu-id="0f8a3-127">È possibile trascinare colonne dalle tabelle alla cella.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-127">You can drag columns from the tables to the cell.</span></span>  
  
 <span data-ttu-id="0f8a3-128">La modalità**Query** fornisce un editor di testo che offre accesso diretto al linguaggio DMX (Data Mining Extensions), oltre a una vista dei dati di input e delle colonne del modello.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-128">**Query** mode provides a text editor that gives you direct access to the Data Mining Extensions (DMX) language, along with a view of the input data and model columns.</span></span> <span data-ttu-id="0f8a3-129">Quando si seleziona la modalità **Query** la griglia utilizzata per definire la query viene sostituita da un editor di testo di base.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-129">When you select **Query** mode, the grid that you used to define the query is replaced by a basic text editor.</span></span> <span data-ttu-id="0f8a3-130">È possibile utilizzare tale editor per copiare e salvare le query composte o per incollare le query DMX esistenti e presenti negli Appunti ed eseguirle.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-130">You can use this editor to copy and save queries you have composed, or to paste in existing DMX queries and from the Clipboard and run them.</span></span>  
  
 <span data-ttu-id="0f8a3-131">Nella vista**Risultato** viene eseguita la query corrente e vengono visualizzati i risultati in una griglia.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-131">**Result** view runs the current query and displays the results in a grid.</span></span> <span data-ttu-id="0f8a3-132">Se i dati sottostanti sono stati modificati e si desidera eseguire nuovamente la query, fare clic sul pulsante Esegui sulla barra di stato.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-132">If the underlying data has changed and you want to rerun the query, click the Play button in the status bar</span></span>  
  
 <span data-ttu-id="0f8a3-133">È possibile progettare una query di data mining utilizzando una combinazione degli strumenti visivi e dell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-133">You can design a data mining query by using a combination of the visual tools and the text editor.</span></span> <span data-ttu-id="0f8a3-134">Se si modifica la query tramite l'editor di testo e si torna quindi alla vista **Progettazione** , le modifiche apportate andranno perse e verrà ripristinata la query originale creata dal generatore di query di stima. In questo argomento viene illustrato l'utilizzo del generatore di query grafico.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-134">If you type changes to the query in the text editor and switch back to the **Design** view, all the changes are lost, and the query reverts to the original query created by Prediction Query Builder This topic walks you through use of the graphical query builder.</span></span>  
  
### <a name="to-create-a-prediction-query"></a><span data-ttu-id="0f8a3-135">Per creare una query di stima</span><span class="sxs-lookup"><span data-stu-id="0f8a3-135">To create a prediction query</span></span>  
  
1.  <span data-ttu-id="0f8a3-136">Fare clic sulla scheda **Stima modello di data mining** in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-136">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="0f8a3-137">Fare clic su **Seleziona modello** nella tabella **Modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="0f8a3-137">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="0f8a3-138">Verrà visualizzata la finestra di dialogo **Seleziona modello di data mining** , in cui sono indicate tutte le strutture di data mining presenti nel progetto.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-138">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
3.  <span data-ttu-id="0f8a3-139">Selezionare il modello in base al quale si desidera creare una stima e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-139">Select the model on which you want to create a prediction, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="0f8a3-140">Nella casella **Seleziona tabelle di input** fare clic su **Seleziona tabella del case**.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-140">On the **Select Input Table(s)** table, click **Select Case Table**.</span></span>  
  
     <span data-ttu-id="0f8a3-141">Verrà visualizzata la finestra di dialogo **Seleziona tabella** .</span><span class="sxs-lookup"><span data-stu-id="0f8a3-141">The **Select Table** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="0f8a3-142">Nell'elenco **Origine dati** selezionare l'origine dei dati contenente i dati su cui si desidera creare una stima.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-142">In the **Data Source** list, select the data source that contains the data on which to create a prediction.</span></span>  
  
6.  <span data-ttu-id="0f8a3-143">Nella casella **Nome tabella/vista** selezionare la tabella contenente i dati sui cui si desidera creare una stima e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-143">In the **Table/View Name** box, select the table that contains the data on which to create a prediction, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0f8a3-144">Dopo aver selezionato la tabella di input, il generatore delle query di stima crea un mapping predefinito tra il modello di data mining e la tabella di input in base ai nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-144">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="0f8a3-145">Per eliminare un mapping, fare clic per selezionare la linea che collega la colonna contenuta nella tabella **Modello di data mining** alla colonna contenuta nella tabella **Seleziona tabelle di input** e quindi premere CANC.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-145">To delete a mapping, click to select the line that links the column in the **Mining Model** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span> <span data-ttu-id="0f8a3-146">È inoltre possibile creare mapping manualmente facendo clic su una colonna nella tabella **Seleziona tabelle di input** e trascinandola sulla colonna corrispondente nella tabella **Modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="0f8a3-146">You can also manually create mappings by clicking a column in the **Select Input Table(s)** table and dragging it onto the corresponding column in the **Mining Model** table.</span></span>  
  
7.  <span data-ttu-id="0f8a3-147">Aggiungere qualsiasi combinazione dei tre tipi di informazioni seguenti alla griglia del generatore delle query di stima:</span><span class="sxs-lookup"><span data-stu-id="0f8a3-147">Add any combination of the following three types of information to the Prediction Query Builder grid:</span></span>  
  
    -   <span data-ttu-id="0f8a3-148">Colonne stimabili dalla casella **Modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="0f8a3-148">Predictable columns from the **Mining Model** box.</span></span>  
  
    -   <span data-ttu-id="0f8a3-149">Qualsiasi combinazione di colonne di input dalla casella **Seleziona tabelle di input** .</span><span class="sxs-lookup"><span data-stu-id="0f8a3-149">Any combination of input columns from the **Select Input Table(s)** box.</span></span>  
  
    -   <span data-ttu-id="0f8a3-150">Funzioni di stima</span><span class="sxs-lookup"><span data-stu-id="0f8a3-150">Prediction functions</span></span>  
  
8.  <span data-ttu-id="0f8a3-151">Eseguire la query facendo clic sul primo pulsante della barra degli strumenti della scheda **Stima modello di data mining** e quindi selezionando **Risultato**.</span><span class="sxs-lookup"><span data-stu-id="0f8a3-151">Run the query by clicking the first button on the toolbar of the **Mining Model Prediction** tab, and then selecting **Result**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f8a3-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f8a3-152">See Also</span></span>  
 <span data-ttu-id="0f8a3-153">[Creazione di una query singleton in Progettazione modelli di data mining](create-a-singleton-query-in-the-data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="0f8a3-153">[Create a Singleton Query in the Data Mining Designer](create-a-singleton-query-in-the-data-mining-designer.md) </span></span>  
 [<span data-ttu-id="0f8a3-154">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="0f8a3-154">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
