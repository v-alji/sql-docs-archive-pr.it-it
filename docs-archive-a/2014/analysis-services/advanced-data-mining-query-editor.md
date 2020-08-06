---
title: Editor avanzato query di data mining | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 27e7fc46-689d-43a4-9647-1c27d182bdd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2aadf4df75b1ccf6001ad8e97d589ce5666f56ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625945"
---
# <a name="advanced-data-mining-query-editor"></a><span data-ttu-id="ced54-102">Editor avanzato query di data mining</span><span class="sxs-lookup"><span data-stu-id="ced54-102">Advanced Data Mining Query Editor</span></span>
  <span data-ttu-id="ced54-103">Il **Editor avanzato di query di data mining** è uno strumento che consente di compilare modelli e query personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ced54-103">The **Data Mining Query Advanced Editor** is a tool to help you build custom models and queries.</span></span>  
  
 <span data-ttu-id="ced54-104">L'editor fornisce un set di modelli con collegamenti selezionabili.</span><span class="sxs-lookup"><span data-stu-id="ced54-104">The editor provides a set of templates with clickable links.</span></span> <span data-ttu-id="ced54-105">È sufficiente fare clic su ogni collegamento e utilizzare le finestre di dialogo per selezionare oggetti o valori e compilare istruzioni DMX complesse.</span><span class="sxs-lookup"><span data-stu-id="ced54-105">Just click each link, and use the dialog boxes to select objects or values and build complex Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="ced54-106">È possibile passare dalla vista al modello di modifica del testo per modificare manualmente l'istruzione DMX.</span><span class="sxs-lookup"><span data-stu-id="ced54-106">You can switch the view to text editing model to modify the DMX statement manually.</span></span>  
  
 <span data-ttu-id="ced54-107">Per ottenere la **Editor avanzato di query di data mining**, fare clic su **query** e quindi su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="ced54-107">To get to the **Data Mining Query Advanced Editor**, click **Query** and then click **Advanced**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ced54-108">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="ced54-108">UI element list</span></span>  
 <span data-ttu-id="ced54-109">**Riquadro Query DMX**</span><span class="sxs-lookup"><span data-stu-id="ced54-109">**DMX Query pane**</span></span>  
 <span data-ttu-id="ced54-110">In questo riquadro è possibile visualizzare l'istruzione DMX corrente.</span><span class="sxs-lookup"><span data-stu-id="ced54-110">Here you can see the current DMX statement.</span></span>  
  
 <span data-ttu-id="ced54-111">Fare clic con il pulsante destro del mouse nel riquadro per copiare l'istruzione DMX corrente.</span><span class="sxs-lookup"><span data-stu-id="ced54-111">Right-click in the pane to copy the current DMX statement.</span></span>  
  
 <span data-ttu-id="ced54-112">È possibile fare clic su una parte evidenziata dell'istruzione per visualizzare le opzioni specifiche della clausola.</span><span class="sxs-lookup"><span data-stu-id="ced54-112">You can click any highlighted part of the statement to get options specific to that clause.</span></span> <span data-ttu-id="ced54-113">Per eliminare, aggiungere o modificare un output, ad esempio, fare clic con il pulsante destro del mouse sul **\<Output>** collegamento.</span><span class="sxs-lookup"><span data-stu-id="ced54-113">For example, to delete, add, or edit an output, right-click the **\<Output>** link.</span></span>  
  
 <span data-ttu-id="ced54-114">**Modifica query/Generatore query**</span><span class="sxs-lookup"><span data-stu-id="ced54-114">**Edit Query/Query Builder**</span></span>  
 <span data-ttu-id="ced54-115">Utilizzare questo pulsante per cambiare l'Editor tra un editor di testo, in cui è possibile scrivere direttamente istruzioni DMX; e la **Generatore di query**, che consente di compilare un'istruzione DMX.</span><span class="sxs-lookup"><span data-stu-id="ced54-115">Use this button to switch the editor between a text editor, where you can write DMX statements directly; and the **Query Builder**, which helps you build a DMX statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ced54-116">**Avviso:** Se si cambiano le visualizzazioni prima dell'esecuzione della query, viene visualizzato un messaggio che informa che è possibile che si perdano alcune modifiche.</span><span class="sxs-lookup"><span data-stu-id="ced54-116">**Warning:** If you switch views before the query has been run, a message appears stating that you might lose some changes.</span></span> <span data-ttu-id="ced54-117">Se l'istruzione DMX è valida, in molti casi l' **Generatore di query** potrebbe convertire correttamente le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ced54-117">If the DMX statement is valid, in many cases the **Query Builder** might successfully convert these changes.</span></span> <span data-ttu-id="ced54-118">Tuttavia, se è stata compilata un'istruzione DMX particolarmente complessa, è consigliabile salvare in modo definitivo il lavoro prima di passare alle viste.</span><span class="sxs-lookup"><span data-stu-id="ced54-118">However, if you have built a particularly complex DMX statement, you should definitely save your work before switching views.</span></span>  
  
 <span data-ttu-id="ced54-119">**Modelli DMX**</span><span class="sxs-lookup"><span data-stu-id="ced54-119">**DMX Templates**</span></span>  
 <span data-ttu-id="ced54-120">Fare clic e selezionare in un elenco di modelli che contengono esempi DMX.</span><span class="sxs-lookup"><span data-stu-id="ced54-120">Click and select from a list of templates that contain DMX examples.</span></span> <span data-ttu-id="ced54-121">I modelli forniscono quasi tutti i tipi di query di stima o del modello che potrebbero essere necessari, tra cui query con tabelle annidate, e istruzioni DMX per gestire i modelli.</span><span class="sxs-lookup"><span data-stu-id="ced54-121">The templates provide just about every type of model or prediction query that you might need, including queries that use nested tables, and DMX statements to manage models.</span></span> <span data-ttu-id="ced54-122">Anche se si ha familiarità con alcune istruzioni DMX, i modelli possono far risparmiare del tempo grazie alla sintassi appropriata.</span><span class="sxs-lookup"><span data-stu-id="ced54-122">Even if you know some DMX, the templates can save you time by getting the syntax right.</span></span>  
  
 <span data-ttu-id="ced54-123">**Scegli modello**</span><span class="sxs-lookup"><span data-stu-id="ced54-123">**Choose Model**</span></span>  
 <span data-ttu-id="ced54-124">Fare clic per visualizzare un elenco di modelli di data mining disponibili nella connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="ced54-124">Click to view a list of data mining models available on the current connection.</span></span>  
  
 <span data-ttu-id="ced54-125">È inoltre possibile visualizzare un elenco dei modelli disponibili facendo clic sul nome del modello nell'istruzione DMX nel riquadro **query DMX** .</span><span class="sxs-lookup"><span data-stu-id="ced54-125">You can also display a list of available models by clicking on the model name in the DMX statement in the **DMX Query** pane.</span></span> <span data-ttu-id="ced54-126">Il nome del modello è in genere evidenziato in rosso.</span><span class="sxs-lookup"><span data-stu-id="ced54-126">The model name is typically highlighted in red.</span></span>  
  
 <span data-ttu-id="ced54-127">**Selezionare l'input**</span><span class="sxs-lookup"><span data-stu-id="ced54-127">**Select Input**</span></span>  
 <span data-ttu-id="ced54-128">Fare clic per scegliere i dati da utilizzare come input per il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ced54-128">Click to choose the data to use as input to the mining model.</span></span> <span data-ttu-id="ced54-129">Se non è stata specificata alcuna origine dati, è anche possibile fare clic sul **\<Input>** collegamento, evidenziato in rosso nel riquadro **query DMX** .</span><span class="sxs-lookup"><span data-stu-id="ced54-129">If no data source has been specified, you can also click the **\<Input>** link, which is highlighted in red in the **DMX Query** pane.</span></span>  
  
 <span data-ttu-id="ced54-130">Selezionare \*\* \@ InputRowset\*\* nell'elenco a discesa per aprire la finestra di dialogo **Sostituisci InputRowset** e modificare un input esistente.</span><span class="sxs-lookup"><span data-stu-id="ced54-130">Select **\@InputRowset** from the dropdown list to open the **Replace InputRowset** dialog box and modify an existing input.</span></span>  
  
 <span data-ttu-id="ced54-131">Selezionare **Aggiungi input** per aprire la finestra di dialogo **Aggiungi input** e specificare una nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="ced54-131">Select **Add Input** to open the **Add Input** dialog box and specify a new data source.</span></span>  
  
 <span data-ttu-id="ced54-132">È anche possibile modificare un input esistente facendo clic sul collegamento \*\* \@ InputRowset\*\* , evidenziato in rosso nel riquadro query DMX.</span><span class="sxs-lookup"><span data-stu-id="ced54-132">You can also modify an existing input by clicking the **\@InputRowset** link, which is highlighted in red in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="ced54-133">**Colonne mappa**</span><span class="sxs-lookup"><span data-stu-id="ced54-133">**Map Columns**</span></span>  
 <span data-ttu-id="ced54-134">Selezionare le colonne del modello di data mining, quindi eseguirne il mapping alle colonne nell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ced54-134">Select columns from the mining model and then map them to columns in the external data source.</span></span>  
  
 <span data-ttu-id="ced54-135">È inoltre possibile fare clic sul **\<Mapping>** collegamento evidenziato nel riquadro query DMX.</span><span class="sxs-lookup"><span data-stu-id="ced54-135">You can also click the highlighted **\<Mapping>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="ced54-136">**Aggiungi output**</span><span class="sxs-lookup"><span data-stu-id="ced54-136">**Add Output**</span></span>  
 <span data-ttu-id="ced54-137">Fare clic per scegliere le colonne che devono essere restituite come output come parte di una query di stima.</span><span class="sxs-lookup"><span data-stu-id="ced54-137">Click to choose the columns that should be output as part of a prediction query.</span></span>  
  
 <span data-ttu-id="ced54-138">È inoltre possibile fare clic sul **\<Add Output>** collegamento evidenziato nel riquadro query DMX.</span><span class="sxs-lookup"><span data-stu-id="ced54-138">You can also click the highlighted **\<Add Output>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="ced54-139">**Colonne modello**</span><span class="sxs-lookup"><span data-stu-id="ced54-139">**Model Columns**</span></span>  
 <span data-ttu-id="ced54-140">Consente di visualizzare l'elenco delle colonne contenute nel modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="ced54-140">Lists the columns in the selected mining model.</span></span> <span data-ttu-id="ced54-141">Un rombo accanto al nome della colonna indica che si tratta di una colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="ced54-141">A diamond mark next to the column name indicates that the column is a predictable column.</span></span>  
  
 <span data-ttu-id="ced54-142">**Colonne di input**</span><span class="sxs-lookup"><span data-stu-id="ced54-142">**Input Columns**</span></span>  
 <span data-ttu-id="ced54-143">Consente di visualizzare l'elenco delle colonne dell'origine dati esterna aggiunte come input.</span><span class="sxs-lookup"><span data-stu-id="ced54-143">Lists the columns from the external data source that have been added as inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced54-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ced54-144">See Also</span></span>  
 [<span data-ttu-id="ced54-145">&#40;di query SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ced54-145">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
  
