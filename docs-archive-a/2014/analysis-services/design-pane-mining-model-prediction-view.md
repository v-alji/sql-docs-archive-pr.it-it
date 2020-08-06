---
title: Riquadro di progettazione (visualizzazione Stima modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.design.f1
ms.assetid: 17f24c8d-43cd-4f4d-83b3-a41ee8fbe8e8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 32ac73a2d6fde38d15d1f45a8439293695749ea4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716956"
---
# <a name="design-pane-mining-model-prediction-view"></a><span data-ttu-id="250b7-102">Riquadro Progettazione (visualizzazione Stima modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="250b7-102">Design Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="250b7-103">Il riquadro **Progettazione** contiene il generatore delle query di stima che consente di compilare le stime di data mining.</span><span class="sxs-lookup"><span data-stu-id="250b7-103">The **Design** pane contains the Prediction Query Builder, which you can use to build data mining predictions.</span></span> <span data-ttu-id="250b7-104">È possibile progettare query di stima che utilizzano tabelle di dati di input da una vista origine dati per generare stime bulk oppure creare query di stima singleton per fornire valori singoli.</span><span class="sxs-lookup"><span data-stu-id="250b7-104">You can design prediction queries that use tables of input data from a data source view, to generate bulk predictions, or you can create singleton prediction queries, which let you provide individual values.</span></span>  
  
 <span data-ttu-id="250b7-105">Per eseguire la query e visualizzare i risultati, passare alla visualizzazione dei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="250b7-105">To run the query and view the results, switch to query result view.</span></span>  
  
 <span data-ttu-id="250b7-106">Nella visualizzazione **Query** viene visualizzata la query DMX (Data Mining Extensions) creata dal generatore delle query di stima.</span><span class="sxs-lookup"><span data-stu-id="250b7-106">The **Query** view displays the Data Mining Extensions (DMX) query that Prediction Query Builder creates.</span></span> <span data-ttu-id="250b7-107">Se si ha dimestichezza con DMX, è possibile personalizzare questa query.</span><span class="sxs-lookup"><span data-stu-id="250b7-107">If you are familiar with DMX, you can customize this query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="250b7-108">Qualsiasi modifica manuale eventualmente apportata alla query andrà perduta quando si torna alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="250b7-108">If you make any manual changes to the query, your changes will be lost when you switch back to Design view.</span></span> <span data-ttu-id="250b7-109">Per salvare la query DMX, è possibile copiarla negli Appunti di Windows e incollarla quindi in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="250b7-109">If you want to save the DMX query, you can copy the query to the Windows Clipboard and then paste it to a text file.</span></span>  
  
 <span data-ttu-id="250b7-110">**Per altre informazioni, vedere** [Query di data mining](data-mining/data-mining-queries.md)</span><span class="sxs-lookup"><span data-stu-id="250b7-110">**For More Information:** [Data Mining Queries](data-mining/data-mining-queries.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="250b7-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="250b7-111">Options</span></span>  
 <span data-ttu-id="250b7-112">**Passa alla visualizzazione dei risultati della query**</span><span class="sxs-lookup"><span data-stu-id="250b7-112">**Switch to query result view**</span></span>  
 <span data-ttu-id="250b7-113">Fare clic su questo pulsante per spostarsi tra i riquadri **Progettazione**, **Query**e **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="250b7-113">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="250b7-114">Se si passa al riquadro **Risultato** , verrà eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="250b7-114">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="250b7-115">**Salva risultati query**</span><span class="sxs-lookup"><span data-stu-id="250b7-115">**Save the query result**</span></span>  
 <span data-ttu-id="250b7-116">Consente di aprire la finestra di dialogo **Salva risultati query di data mining** .</span><span class="sxs-lookup"><span data-stu-id="250b7-116">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="250b7-117">**Query singleton**</span><span class="sxs-lookup"><span data-stu-id="250b7-117">**Singleton query**</span></span>  
 <span data-ttu-id="250b7-118">Consente di attivare la creazione di un query singleton nella quale è possibile fornire direttamente i valori per la query anziché specificare una tabella come origine dei dati noti.</span><span class="sxs-lookup"><span data-stu-id="250b7-118">Enables creating a singleton query, in which you can provide values directly for the query instead of providing a table as the source of the known data.</span></span> <span data-ttu-id="250b7-119">La tabella **Seleziona tabelle di input** viene sostituita dalla tabella **Input query singleton** .</span><span class="sxs-lookup"><span data-stu-id="250b7-119">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span>  
  
 <span data-ttu-id="250b7-120">**Aggiorna risultati query**</span><span class="sxs-lookup"><span data-stu-id="250b7-120">**Refresh query results**</span></span>  
 <span data-ttu-id="250b7-121">Consente di rielaborare la query di stima.</span><span class="sxs-lookup"><span data-stu-id="250b7-121">Reprocesses the prediction query.</span></span> <span data-ttu-id="250b7-122">Questa opzione è attivata solo nel riquadro **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="250b7-122">This is enabled only in the **Result** pane.</span></span>  
  
 <span data-ttu-id="250b7-123">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="250b7-123">**Mining Model**</span></span>  
 <span data-ttu-id="250b7-124">Consente di visualizzare il modello di data mining selezionato sul quale si desidera basare le stime.</span><span class="sxs-lookup"><span data-stu-id="250b7-124">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="250b7-125">**Seleziona modello**</span><span class="sxs-lookup"><span data-stu-id="250b7-125">**Select Model**</span></span>  
 <span data-ttu-id="250b7-126">Consente di aprire la finestra di dialogo **Seleziona modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="250b7-126">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="250b7-127">**Seleziona tabella/e di input**</span><span class="sxs-lookup"><span data-stu-id="250b7-127">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="250b7-128">Consente di visualizzare le tabelle di input selezionate contenenti dati noti su cui basare le stime.</span><span class="sxs-lookup"><span data-stu-id="250b7-128">Displays the selected input tables that contain known data on which to base the predictions.</span></span>  
  
 <span data-ttu-id="250b7-129">**Elimina tabella**</span><span class="sxs-lookup"><span data-stu-id="250b7-129">**Delete Table**</span></span>  
 <span data-ttu-id="250b7-130">Consente di eliminare la tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="250b7-130">Deletes the selected table.</span></span> <span data-ttu-id="250b7-131">Questo pulsante è disabilitato se non è stata selezionata una tabella o non esiste.</span><span class="sxs-lookup"><span data-stu-id="250b7-131">This button is disabled if a table has not been selected or does not exist.</span></span>  
  
 <span data-ttu-id="250b7-132">**Seleziona tabella del case**</span><span class="sxs-lookup"><span data-stu-id="250b7-132">**Select Case Table**</span></span>  
 <span data-ttu-id="250b7-133">Consente di aprire la finestra di dialogo **Seleziona tabella** .</span><span class="sxs-lookup"><span data-stu-id="250b7-133">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="250b7-134">Questo pulsante è disponibile solo se non è stata selezionata una tabella.</span><span class="sxs-lookup"><span data-stu-id="250b7-134">This button appears only if a case table has not been selected.</span></span>  
  
 <span data-ttu-id="250b7-135">**Seleziona tabella nidificata**</span><span class="sxs-lookup"><span data-stu-id="250b7-135">**Select Nested Table**</span></span>  
 <span data-ttu-id="250b7-136">Consente di aprire la finestra di dialogo **Seleziona tabella** .</span><span class="sxs-lookup"><span data-stu-id="250b7-136">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="250b7-137">Questo pulsante viene visualizzato solo se è stata selezionata una tabella del case.</span><span class="sxs-lookup"><span data-stu-id="250b7-137">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="250b7-138">Se nella struttura di data mining associata non è inclusa una tabella nidificata, il pulsante è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="250b7-138">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="250b7-139">**Modifica join**</span><span class="sxs-lookup"><span data-stu-id="250b7-139">**Modify Join**</span></span>  
 <span data-ttu-id="250b7-140">Consente di aprire la finestra di dialogo **Specifica join nidificato** .</span><span class="sxs-lookup"><span data-stu-id="250b7-140">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="250b7-141">Questo pulsante è attivo solo se si seleziona una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="250b7-141">This button is active only if the nested table is selected.</span></span>  
  
 <span data-ttu-id="250b7-142">**Input query singleton**</span><span class="sxs-lookup"><span data-stu-id="250b7-142">**Singleton Query input**</span></span>  
 <span data-ttu-id="250b7-143">Questa opzione viene attivata quando si sceglie il pulsante **Query singleton**</span><span class="sxs-lookup"><span data-stu-id="250b7-143">Enabled when you select the **Singleton query** button.</span></span> <span data-ttu-id="250b7-144">e presenta le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="250b7-144">Contains the following columns:</span></span>  
  
|<span data-ttu-id="250b7-145">Valore</span><span class="sxs-lookup"><span data-stu-id="250b7-145">Value</span></span>|<span data-ttu-id="250b7-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="250b7-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="250b7-147">**Colonna modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="250b7-147">**Mining Model Column**</span></span>|<span data-ttu-id="250b7-148">Elenca le colonne del modello di data mining contenute nel modello di data mining selezionato nella tabella **Modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="250b7-148">Lists the mining model columns contained within the mining model that is selected in the **Mining Model** table.</span></span>|  
|<span data-ttu-id="250b7-149">**Valore**</span><span class="sxs-lookup"><span data-stu-id="250b7-149">**Value**</span></span>|<span data-ttu-id="250b7-150">Consente di selezionare un valore nell'elenco che contiene ogni possibile stato della colonna del modello di data mining selezionata.</span><span class="sxs-lookup"><span data-stu-id="250b7-150">Select a value from the list that contains each possible state of the selected mining model column.</span></span><br /><br /> <span data-ttu-id="250b7-151">Se la colonna è la colonna di una tabella nidificata, fare clic sulla cella del valore per aprire la finestra di dialogo **Input tabella nidificata** .</span><span class="sxs-lookup"><span data-stu-id="250b7-151">If the column is a nested table column, clicking the value cell opens the **Nested Table Input** dialog box.</span></span>|  
  
 <span data-ttu-id="250b7-152">**Origine**</span><span class="sxs-lookup"><span data-stu-id="250b7-152">**Source**</span></span>  
 <span data-ttu-id="250b7-153">Consente di selezionare l'origine contenente il campo che verrà utilizzato per la colonna.</span><span class="sxs-lookup"><span data-stu-id="250b7-153">Select the source that contains the field that you will use for the column.</span></span> <span data-ttu-id="250b7-154">È possibile usare il modello di data mining selezionato nella tabella **Modello di data mining** , la tabella o le tabelle di input selezionate nella tabella **Seleziona tabella/e di input** , una funzione di stima o un'espressione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="250b7-154">You can either use the mining model that is selected in the **Mining Model** table, the input table or tables that are selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="250b7-155">È possibile trascinare le colonne dalle tabelle contenenti il modello di data mining e dalle tabelle di input sulla cella.</span><span class="sxs-lookup"><span data-stu-id="250b7-155">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
 <span data-ttu-id="250b7-156">**Campo**</span><span class="sxs-lookup"><span data-stu-id="250b7-156">**Field**</span></span>  
 <span data-ttu-id="250b7-157">Consente di selezionare una colonna nell'elenco di colonne derivato dalla tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="250b7-157">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="250b7-158">Se è stata selezionata l'opzione **Funzione di stima** in **Origine**, l'elenco conterrà la funzione di stima disponibile per il modello di data mining specificato.</span><span class="sxs-lookup"><span data-stu-id="250b7-158">If you selected **Prediction Function** in **Source**, this contains the prediction function available for the selected mining model.</span></span>  
  
 <span data-ttu-id="250b7-159">**Gruppo**</span><span class="sxs-lookup"><span data-stu-id="250b7-159">**Group**</span></span>  
 <span data-ttu-id="250b7-160">Usare questa opzione con la colonna **And/Or** per raggruppare le espressioni.</span><span class="sxs-lookup"><span data-stu-id="250b7-160">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="250b7-161">Ad esempio: `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="250b7-161">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="250b7-162">**E/o**</span><span class="sxs-lookup"><span data-stu-id="250b7-162">**And/Or**</span></span>  
 <span data-ttu-id="250b7-163">Utilizzare questa opzione per creare una query logica.</span><span class="sxs-lookup"><span data-stu-id="250b7-163">Use to create a logical query.</span></span> <span data-ttu-id="250b7-164">Ad esempio: `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="250b7-164">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="250b7-165">**Criteri/Argomento**</span><span class="sxs-lookup"><span data-stu-id="250b7-165">**Criteria/Argument**</span></span>  
 <span data-ttu-id="250b7-166">Consente di specificare una condizione o un'espressione utente da applicare a una colonna.</span><span class="sxs-lookup"><span data-stu-id="250b7-166">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="250b7-167">È possibile trascinare le colonne dalle tabelle contenenti il modello di data mining e dalle tabelle di input sulla cella.</span><span class="sxs-lookup"><span data-stu-id="250b7-167">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="250b7-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="250b7-168">See Also</span></span>  
 <span data-ttu-id="250b7-169">[Guida di riferimento alle istruzioni DMX&#41; &#40;di Data Mining Extensions](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="250b7-169">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 <span data-ttu-id="250b7-170">[Interfacce di query di data mining](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="250b7-170">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="250b7-171">Generatore delle query di stima &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="250b7-171">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
