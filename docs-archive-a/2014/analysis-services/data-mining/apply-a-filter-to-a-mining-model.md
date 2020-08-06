---
title: Applicare un filtro a un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filters [data mining]
- filtering input rows [Analysis Services]
- filtering data [Analysis Services]
ms.assetid: 4d0abeb5-e939-46d3-9097-6e0358244300
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9f3147c36e69d9c2249d5bf6d1ba201799c6e27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635271"
---
# <a name="apply-a-filter-to-a-mining-model"></a><span data-ttu-id="58e7a-102">Applicare un filtro a un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="58e7a-102">Apply a Filter to a Mining Model</span></span>
  <span data-ttu-id="58e7a-103">Se la struttura di data mining contiene una tabella nidificata, è possibile applicare un filtro alla tabella del case, alla tabella nidificata o a entrambe.</span><span class="sxs-lookup"><span data-stu-id="58e7a-103">If your mining structure contains a nested table, you can apply a filter to the case table, the nested table, or both.</span></span>  
  
 <span data-ttu-id="58e7a-104">Nella procedura seguente viene illustrato come creare entrambi i tipi di filtro: filtri di case e filtri sulle righe della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="58e7a-104">The following procedure demonstrates how to create both kinds of filters: case filters, and filters on the nested table rows.</span></span>  
  
 <span data-ttu-id="58e7a-105">La condizione sulla tabella del case restringe i clienti a quelli con il reddito compreso tra 30000 e 40000.</span><span class="sxs-lookup"><span data-stu-id="58e7a-105">The condition on the case table restricts customers to those with income between 30000 and 40000.</span></span> <span data-ttu-id="58e7a-106">La condizione sulla tabella nidificata restringe i clienti a quelli che non hanno acquistato un determinato articolo.</span><span class="sxs-lookup"><span data-stu-id="58e7a-106">The condition on the nested table restricts the customers to those who did not purchase a particular item.</span></span>  
  
 <span data-ttu-id="58e7a-107">La condizione di filtro completa creata in questo esempio è la seguente:</span><span class="sxs-lookup"><span data-stu-id="58e7a-107">The complete filter condition created in this example is as follows:</span></span>  
  
```  
[Income] > '30000'   
AND  [Income] < '40000'   
AND EXISTS (SELECT * FROM [<nested table name>]   
WHERE [Model] <> 'Water Bottle' )   
```  
  
### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="58e7a-108">Per creare un filtro di case su un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="58e7a-108">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="58e7a-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Esplora soluzioni, fare clic sulla struttura di data mining che contiene il modello di data mining da filtrare.</span><span class="sxs-lookup"><span data-stu-id="58e7a-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="58e7a-110">Fare clic sulla scheda **Modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="58e7a-110">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="58e7a-111">Selezionare il modello, quindi fare clic con il pulsante destro del mouse per aprire il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="58e7a-111">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="58e7a-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="58e7a-112">-or-</span></span>  
  
     <span data-ttu-id="58e7a-113">Selezionare il modello.</span><span class="sxs-lookup"><span data-stu-id="58e7a-113">Select the model.</span></span> <span data-ttu-id="58e7a-114">quindi scegliere **Imposta filtro modello** dal menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-114">Then, on the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="58e7a-115">Nella finestra di dialogo **Filtro modello** fare clic sulla riga superiore nella griglia della casella di testo **Colonna struttura di data mining** .</span><span class="sxs-lookup"><span data-stu-id="58e7a-115">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
5.  <span data-ttu-id="58e7a-116">Se l'origine dati contiene una singola tabella flat, l'elenco a discesa visualizza solo i nomi delle colonne di tale tabella.</span><span class="sxs-lookup"><span data-stu-id="58e7a-116">If the data source contains a single flat table, the drop-down list displays only the names of the columns in that table.</span></span>  
  
     <span data-ttu-id="58e7a-117">Se la struttura di data mining contiene più tabelle, l'elenco mostra i nomi delle tabelle di origine.</span><span class="sxs-lookup"><span data-stu-id="58e7a-117">If the mining structure contains multiple tables, the list shows the names of the source tables.</span></span> <span data-ttu-id="58e7a-118">I nomi delle colonne vengono visualizzati solo dopo la selezione di una tabella.</span><span class="sxs-lookup"><span data-stu-id="58e7a-118">The column names do not display until a table has been selected.</span></span>  
  
     <span data-ttu-id="58e7a-119">Se la struttura di data mining contiene una tabella del case e una tabella nidificata, l'elenco a discesa mostra le colonne dalla tabella del case e il nome della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="58e7a-119">If the mining structure contains a case table and a nested table, the drop-down list shows columns from the case table, and the name of the nested table.</span></span>  
  
6.  <span data-ttu-id="58e7a-120">Selezionare una colonna dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="58e7a-120">Select a column from the drop-down list.</span></span>  
  
     <span data-ttu-id="58e7a-121">L'icona a sinistra della casella di testo cambierà per indicare che l'elemento selezionato è una tabella o una colonna.</span><span class="sxs-lookup"><span data-stu-id="58e7a-121">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
7.  <span data-ttu-id="58e7a-122">Fare clic sulla casella di testo **Operatore** e selezionare un operatore dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="58e7a-122">Click the **Operator** text box and select an operator from the list.</span></span> <span data-ttu-id="58e7a-123">Gli operatori validi variano a seconda del tipo di dati della colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="58e7a-123">The valid operators change depending on the data type of the column you selected.</span></span>  
  
8.  <span data-ttu-id="58e7a-124">Fare clic nella casella di testo **Valore** e digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="58e7a-124">Click the **Value** text box, and type a value in the box.</span></span>  
  
     <span data-ttu-id="58e7a-125">Ad esempio, selezionare `Income` come colonna, selezionare l'operatore maggiore di (>), quindi digitare `30000` .</span><span class="sxs-lookup"><span data-stu-id="58e7a-125">For example, select `Income` as the column, select the greater than operator (>), and then type `30000`.</span></span>  
  
9. <span data-ttu-id="58e7a-126">Fare clic sulla riga successiva nella griglia.</span><span class="sxs-lookup"><span data-stu-id="58e7a-126">Click the next row in the grid.</span></span>  
  
     <span data-ttu-id="58e7a-127">La condizione di filtro creata viene aggiunta automaticamente nella casella di testo Espressione.</span><span class="sxs-lookup"><span data-stu-id="58e7a-127">The filter condition that you created is automatically added to the Expression text box.</span></span> <span data-ttu-id="58e7a-128">Ad esempio: `[Income] > '30000'`</span><span class="sxs-lookup"><span data-stu-id="58e7a-128">For example, `[Income] > '30000'`</span></span>  
  
10. <span data-ttu-id="58e7a-129">Fare clic nella casella di testo **AND/OR** nella riga successiva della griglia per aggiungere una condizione.</span><span class="sxs-lookup"><span data-stu-id="58e7a-129">Click the **AND/OR** text box in the next row of the grid to add a condition.</span></span>  
  
     <span data-ttu-id="58e7a-130">Ad esempio, per creare una condizione BETWEEN, selezionare `AND` nell'elenco a discesa di operandi logici.</span><span class="sxs-lookup"><span data-stu-id="58e7a-130">For example, to create a BETWEEN condition, select `AND` from the drop-down list of logical operands.</span></span>  
  
11. <span data-ttu-id="58e7a-131">Selezionare un operatore e digitare un valore come descritto nei passaggi 7 e 8.</span><span class="sxs-lookup"><span data-stu-id="58e7a-131">Select an operator and type a value as described in Steps 7 and 8.</span></span>  
  
     <span data-ttu-id="58e7a-132">Ad esempio, selezionare di `Income` nuovo come colonna, selezionare l'operatore minore di (<), quindi digitare `40000` .</span><span class="sxs-lookup"><span data-stu-id="58e7a-132">For example, select `Income` as the column again, select the less than operator (<), and then type `40000`.</span></span>  
  
12. <span data-ttu-id="58e7a-133">Fare clic sulla riga successiva nella griglia.</span><span class="sxs-lookup"><span data-stu-id="58e7a-133">Click the next row in the grid.</span></span>  
  
13. <span data-ttu-id="58e7a-134">La condizione di filtro nella casella di testo Espressione viene aggiornata automaticamente per includere la nuova condizione.</span><span class="sxs-lookup"><span data-stu-id="58e7a-134">The filter condition in the Expression text box is automatically updated to include the new condition.</span></span> <span data-ttu-id="58e7a-135">L'espressione completa è la seguente: `[Income] > '30000'AND [Income] < '40000'`</span><span class="sxs-lookup"><span data-stu-id="58e7a-135">The completed expression is as follows: `[Income] > '30000'AND [Income] < '40000'`</span></span>  
  
### <a name="to-add-a-filter-on-the-nested-table-in-a-mining-model"></a><span data-ttu-id="58e7a-136">Per aggiungere un filtro nella tabella nidificata in un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="58e7a-136">To add a filter on the nested table in a mining model</span></span>  
  
1.  <span data-ttu-id="58e7a-137">Nella finestra di dialogo \*\* \<name> filtro modello\*\* fare clic su una riga vuota della griglia sotto **colonna struttura di data mining**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-137">In the **\<name>Model Filter** Dialog box, click an empty row in the grid under **Mining Structure Column**.</span></span>  
  
2.  <span data-ttu-id="58e7a-138">Selezionare il nome della tabella nidificata dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="58e7a-138">Select the name of the nested table from the drop-down list.</span></span>  
  
     <span data-ttu-id="58e7a-139">L'icona a sinistra della casella di testo cambia per indicare che l'elemento selezionato è il nome di una tabella.</span><span class="sxs-lookup"><span data-stu-id="58e7a-139">The icon at the left side of the text box changes to indicate that the selected item is the name of a table.</span></span>  
  
3.  <span data-ttu-id="58e7a-140">Fare clic nella casella di testo **Operatore** e selezionare **Contiene** o **Non contiene**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-140">Click the **Operator** text box and select **Contains** or **Not Contain**.</span></span>  
  
     <span data-ttu-id="58e7a-141">Queste sono le uniche condizioni disponibili per la tabella nidificata nella finestra di dialogo **Filtro modello** , perché la tabella del case è stata limitata solo ai case che contengono un determinato valore nella tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="58e7a-141">These are the only conditions available for the nested table in the **Model Filter** dialog box, because you are restricting the case table to only those cases that contain a certain value in the nested table.</span></span> <span data-ttu-id="58e7a-142">Il valore per la condizione nella tabella nidificata verrà impostato nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="58e7a-142">You will set the value for the condition on the nested table in the next step.</span></span>  
  
4.  <span data-ttu-id="58e7a-143">Fare clic sulla casella **valore** e quindi sul pulsante **(...)** per compilare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="58e7a-143">Click the **Value** box, and then click the **(...)** button to build an expression.</span></span>  
  
     <span data-ttu-id="58e7a-144">Verrà visualizzata la finestra di dialogo \*\* \<name> filtro\*\* .</span><span class="sxs-lookup"><span data-stu-id="58e7a-144">The **\<name>Filter** dialog box opens.</span></span> <span data-ttu-id="58e7a-145">Questa finestra di dialogo consente di impostare condizioni solo nella tabella corrente, che in questo caso è la tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="58e7a-145">This dialog box can set conditions only on the current table, which in this case is the nested table.</span></span>  
  
5.  <span data-ttu-id="58e7a-146">Fare clic sulla casella **Colonna struttura di data mining** e selezionare un nome di colonna dagli elenchi a discesa di colonne della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="58e7a-146">Click the **Mining Structure Column** box and select a column name from the dropdown lists of nested table columns.</span></span>  
  
6.  <span data-ttu-id="58e7a-147">Fare clic su **Operatore** e selezionare un operatore dall'elenco di operatori validi per la colonna.</span><span class="sxs-lookup"><span data-stu-id="58e7a-147">Click **Operator** and select an operator from the list of valid operators for the column.</span></span>  
  
7.  <span data-ttu-id="58e7a-148">Fare clic su **Valore** e digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="58e7a-148">Click **Value** and type a value.</span></span>  
  
     <span data-ttu-id="58e7a-149">Ad esempio, per **colonna struttura di data mining** selezionare `Model` .</span><span class="sxs-lookup"><span data-stu-id="58e7a-149">For example, for **Mining Structure Column,** select `Model`.</span></span> <span data-ttu-id="58e7a-150">Per **operator**selezionare `<>` e digitare il valore `Water Bottle` .</span><span class="sxs-lookup"><span data-stu-id="58e7a-150">For **Operator**, select `<>`, and type the value `Water Bottle`.</span></span> <span data-ttu-id="58e7a-151">Questa condizione crea l'espressione di filtro seguente:</span><span class="sxs-lookup"><span data-stu-id="58e7a-151">This condition creates the following filter expression:</span></span>  
  
```  
EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] <> 'Water Bottle' )   
```  
  
> [!NOTE]  
>  <span data-ttu-id="58e7a-152">Poiché il numero di attributi della tabella nidificata è potenzialmente illimitato, in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non viene fornito un elenco di valori possibili da cui effettuare una selezione.</span><span class="sxs-lookup"><span data-stu-id="58e7a-152">Because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="58e7a-153">È necessario digitare il valore esatto.</span><span class="sxs-lookup"><span data-stu-id="58e7a-153">You must type the exact value.</span></span> <span data-ttu-id="58e7a-154">Inoltre, non è possibile utilizzare un operatore LIKE in una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="58e7a-154">Also, you cannot use a LIKE operator in a nested table.</span></span>  
  
1.  <span data-ttu-id="58e7a-155">Aggiungere altre condizioni in base alle esigenze, combinando le condizioni selezionando `AND` o `OR` nella casella **e/o** sul lato sinistro della griglia **condizioni** .</span><span class="sxs-lookup"><span data-stu-id="58e7a-155">Add more conditions as necessary, combining the conditions by selecting `AND` or `OR` in the **AND/OR** box at the left side of the **Conditions** grid.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="58e7a-156">Nella finestra di dialogo **Filtro modello** esaminare le condizioni create utilizzando la finestra di dialogo **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="58e7a-156">In the **Model Filter** dialog box, review the conditions that you created by using the **Filter** dialog box.</span></span> <span data-ttu-id="58e7a-157">Le condizioni per la tabella nidificata vengono aggiunte alle condizioni per la tabella del case e il set completo di condizioni di filtro viene visualizzato nella casella di testo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="58e7a-157">The conditions for the nested table are appended to the conditions for the case table, and the complete set of filter conditions is displayed in the **Expression** text box.</span></span>  
  
3.  <span data-ttu-id="58e7a-158">È possibile fare clic su **Modifica query** per modificare manualmente l'espressione di filtro (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="58e7a-158">Optionally, click **Edit Query** to manually change the filter expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="58e7a-159">Se si modifica manualmente una parte di un'espressione di filtro, la griglia verrà disabilitata e da quel momento sarà necessario utilizzare l'espressione di filtro solo in modalità di modifica di testo.</span><span class="sxs-lookup"><span data-stu-id="58e7a-159">If you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="58e7a-160">Per ripristinare la modalità di modifica della griglia, è necessario cancellare l'espressione di filtro e ricominciare.</span><span class="sxs-lookup"><span data-stu-id="58e7a-160">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="58e7a-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58e7a-161">See Also</span></span>  
 <span data-ttu-id="58e7a-162">[Filtri per i modelli di data mining &#40;Analysis Services-&#41;di data mining](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="58e7a-162">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="58e7a-163">[Attività e procedure relative al modello di data mining](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="58e7a-163">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="58e7a-164">Eliminare un filtro da un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="58e7a-164">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
