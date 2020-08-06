---
title: Finestra di dialogo filtro set di dati o filtro modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9602174-b7e2-4e16-8ded-dfd8eb9264d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa796cd8cb23894c059deba411b3e1d6676e3b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717015"
---
# <a name="data-set-filter-or-model-filter-dialog-box"></a><span data-ttu-id="014ba-102">Finestra di dialogo Filtro dei set di dati o Filtro modello</span><span class="sxs-lookup"><span data-stu-id="014ba-102">Data Set Filter or Model Filter Dialog Box</span></span>
  <span data-ttu-id="014ba-103">Questa finestra di dialogo consente di compilare i filtri che è possibile applicare a un set di dati.</span><span class="sxs-lookup"><span data-stu-id="014ba-103">This dialog box helps you build the filters that you can apply to a data set.</span></span>  <span data-ttu-id="014ba-104">Il set di dati può essere un set esterno utilizzato per eseguire il test o un set di dati di case per un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="014ba-104">The data set can be an external data set used for testing, or the case data for a mining model.</span></span> <span data-ttu-id="014ba-105">Il nome della finestra di dialogo varia a seconda che il filtro venga utilizzato per un set di dati esterno o per un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="014ba-105">The name of the dialog box changes depending on whether the filter is for an external data set or for a mining model.</span></span>  
  
 <span data-ttu-id="014ba-106">Se si applica il filtro a un nuovo set di dati, il modello di data mining viene valutato solo con i case del set di dati che soddisfano le condizioni.</span><span class="sxs-lookup"><span data-stu-id="014ba-106">If you apply the filter to a new data set, the data mining model is evaluated by using only those cases in the data set that meet the conditions.</span></span> <span data-ttu-id="014ba-107">Se si applica il filtro al modello di data mining stesso, il training e il test del modello vengono eseguiti solo con i case del set di dati di test esistente che soddisfano i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="014ba-107">If you apply the filter to the mining model itself, the model will be trained and tested by using only the cases in the existing test data set that meet the filter criteria.</span></span>  
  
-   <span data-ttu-id="014ba-108">La finestra di dialogo **Filtro dei set di dati** è disponibile dalla scheda **Selezione input** della finestra di progettazione **Grafico accuratezza modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="014ba-108">The **Data Set Filter** dialog box is available from the **Input Selection** tab of the **Mining Accuracy Chart** designer.</span></span>  
  
-   <span data-ttu-id="014ba-109">La finestra di dialogo **Filtro modello** è disponibile dalla scheda **Modelli di data mining** della finestra di progettazione Data Mining.</span><span class="sxs-lookup"><span data-stu-id="014ba-109">The **Model Filter** dialog box is available from the **Mining Models** tab of the Data Miningdesigner.</span></span>  
  
-   <span data-ttu-id="014ba-110">Nella griglia **Condizioni** sono contenute le colonne in cui è possibile specificare un nome di colonna o tabella, un operatore e i valori di destinazione.</span><span class="sxs-lookup"><span data-stu-id="014ba-110">The **Conditions** grid contains columns where you can specify a table or column name, an operator, and target values.</span></span> <span data-ttu-id="014ba-111">Mediante questa griglia sostanzialmente si crea una clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="014ba-111">By using this grid you are essentially creating a WHERE clause.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="014ba-112">Per eseguire il test dell'accuratezza su un subset di dati di training originali, è possibile aggiungere la vista origine dati usata per definire il set di training come dati di test esterni e aggiungere quindi condizioni nella griglia **Filtro dei set di dati**.</span><span class="sxs-lookup"><span data-stu-id="014ba-112">To test accuracy on a subset of the original training data, you can add the data source view that was used to define the training set as the external testing data, and then add conditions in the **Data Set Filter** grid.</span></span>  
  
 <span data-ttu-id="014ba-113">**Per altre informazioni:** [Test e convalida &#40;Data mining&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="014ba-113">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="014ba-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="014ba-114">Options</span></span>  
 <span data-ttu-id="014ba-115">**Condizioni**</span><span class="sxs-lookup"><span data-stu-id="014ba-115">**Conditions**</span></span>  
 <span data-ttu-id="014ba-116">Consente di visualizzare nomi di tabelle seguiti da nomi di colonne con condizioni.</span><span class="sxs-lookup"><span data-stu-id="014ba-116">Displays table names, followed by column names with conditions.</span></span>  
  
|<span data-ttu-id="014ba-117">Valore</span><span class="sxs-lookup"><span data-stu-id="014ba-117">Value</span></span>|<span data-ttu-id="014ba-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="014ba-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="014ba-119">**E/o**</span><span class="sxs-lookup"><span data-stu-id="014ba-119">**And/Or**</span></span>|<span data-ttu-id="014ba-120">Scegliere un operatore per eseguire il join di più condizioni.</span><span class="sxs-lookup"><span data-stu-id="014ba-120">Choose an operator to join multiple conditions.</span></span>|  
|<span data-ttu-id="014ba-121">**Colonne struttura di data mining**</span><span class="sxs-lookup"><span data-stu-id="014ba-121">**Mining Structure Column**</span></span>|<span data-ttu-id="014ba-122">Fare clic per selezionare un'origine dati, quindi fare clic sulle righe successive della griglia per aggiungere le colonne dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="014ba-122">Click to select a data source, and then click successive lines in the grid to add columns from the data source.</span></span><br /><br /> <span data-ttu-id="014ba-123">La prima riga nella griglia specifica la vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="014ba-123">The first line in the grid specifies the data source view.</span></span> <span data-ttu-id="014ba-124">Dopo avere selezionato una vista origine dati, vengono visualizzate un'icona di tabella in **Colonna struttura di data mining** e la combinazione di tutti i criteri definiti per quell'origine dati nel campo **Valore** .</span><span class="sxs-lookup"><span data-stu-id="014ba-124">After you select a data source view, **Mining Structure Column** displays a table icon, and the **Value** field displays the combination of all criteria that you have defined for this data source.</span></span><br /><br /> <span data-ttu-id="014ba-125">Dopo avere selezionato un'origine dati, nella casella **Colonna struttura di data mining** diventa disponibile un elenco a discesa di singole colonne dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="014ba-125">After you have selected a data source, the **Mining Structure Column** box provides a dropdown list of individual columns in the data source.</span></span>|  
|<span data-ttu-id="014ba-126">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="014ba-126">**Operator**</span></span>|<span data-ttu-id="014ba-127">Selezionare un operatore dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="014ba-127">Select an operator from the list.</span></span>|  
|<span data-ttu-id="014ba-128">**Valore**</span><span class="sxs-lookup"><span data-stu-id="014ba-128">**Value**</span></span>|<span data-ttu-id="014ba-129">Per le tabelle, nel campo **Valore** viene visualizzata la combinazione di tutti i filtri applicati all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="014ba-129">For tables, the **Value** field shows the combination of all filters applied to the data source.</span></span> <span data-ttu-id="014ba-130">È anche possibile fare clic sul pulsante di compilazione **(...)** a destra della casella di testo per aprire la finestra di dialogo **filtro** e compilare una condizione.</span><span class="sxs-lookup"><span data-stu-id="014ba-130">You can also click the build **(...)** button at the right of the text box to open the **Filter** dialog box and build a condition.</span></span>|  
  
 <span data-ttu-id="014ba-131">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="014ba-131">**Expression**</span></span>  
 <span data-ttu-id="014ba-132">Consente di visualizzare il set di criteri compilato tramite la griglia.</span><span class="sxs-lookup"><span data-stu-id="014ba-132">Displays the set of criteria that you built by using the grid.</span></span>  
  
 <span data-ttu-id="014ba-133">**Modifica query**</span><span class="sxs-lookup"><span data-stu-id="014ba-133">**Edit Query**</span></span>  
 <span data-ttu-id="014ba-134">Consente di cambiare la modalità di modifica del filtro per poter specificare un'espressione di filtro direttamente nella casella di testo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="014ba-134">Changes the filter editing mode so that you can type a filter expression directly in the **Expression** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="014ba-135">Dopo aver apportato modifiche manuali all'espressione di filtro, non è possibile tornare alla modalità di modifica della griglia, anche dopo aver salvato l'espressione nella casella **espressione filtro** della scheda **Selezione input** . Se si desidera compilare un'espressione tramite la griglia, è necessario eliminare l'espressione di filtro esistente e ricominciare.</span><span class="sxs-lookup"><span data-stu-id="014ba-135">After you have made manual changes to the filter expression, you cannot return to grid edit mode, even after you have saved the expression in the **Filter Expression** box on the **Input Selection** tab. If you want to build an expression by using the grid, you must delete the existing filter expression and start over.</span></span>  
  
 <span data-ttu-id="014ba-136">**Annulla modifiche query**</span><span class="sxs-lookup"><span data-stu-id="014ba-136">**Revert Query Edits**</span></span>  
 <span data-ttu-id="014ba-137">Consente di ripristinare la griglia allo stato precedente e annullare qualsiasi modifica apportata all'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="014ba-137">Restores the grid to its previous state and cancels any changes that you made to the filter expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014ba-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="014ba-138">See Also</span></span>  
 <span data-ttu-id="014ba-139">[Attività e procedure di test e convalida &#40;di data mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="014ba-139">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="014ba-140">Progettazione Grafico accuratezza modello di data mining &#40;&#41;di data mining</span><span class="sxs-lookup"><span data-stu-id="014ba-140">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
