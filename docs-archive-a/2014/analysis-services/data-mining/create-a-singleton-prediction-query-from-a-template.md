---
title: Creare una query di stima singleton da un modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton query predictions [DMX]
ms.assetid: e0a68ab0-bece-4d25-b464-47f1719302e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80e853875cce349dd8623fab3c30f1ad09bfbf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625039"
---
# <a name="create-a-singleton-prediction-query-from-a-template"></a><span data-ttu-id="b05b2-102">Creare una query di stima singleton da un modello</span><span class="sxs-lookup"><span data-stu-id="b05b2-102">Create a Singleton Prediction Query from a Template</span></span>
  <span data-ttu-id="b05b2-103">Una query singleton è utile quando si dispone di un modello che si desidera utilizzare per la stima, ma non si desidera eseguirne il mapping a un set di dati di input esterno oppure eseguire stime bulk.</span><span class="sxs-lookup"><span data-stu-id="b05b2-103">A singleton query is useful when you have a model that you want to use for prediction, but don't want to map it to an external input data set or make bulk predictions.</span></span> <span data-ttu-id="b05b2-104">Con una query singleton, è possibile fornire uno o più valori al modello e ottenere all'istante il valore stimato.</span><span class="sxs-lookup"><span data-stu-id="b05b2-104">With a singleton query, you can provide a value or values to the model and instantly see the predicted value.</span></span>  
  
 <span data-ttu-id="b05b2-105">Ad esempio, la query DMX seguente rappresenta una query singleton sul modello di mailing diretto, TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="b05b2-105">For example, the following DMX query represents a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT * FROM [TM_Decision_tree] ;  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="b05b2-106">La procedura che segue descrive come usare Esplora modelli in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per creare rapidamente questa query.</span><span class="sxs-lookup"><span data-stu-id="b05b2-106">The procedure that follows describes how to use the Template Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to quickly create this query.</span></span>  
  
### <a name="to-open-the-analysis-services-templates-in-sql-server-management-studio"></a><span data-ttu-id="b05b2-107">Per aprire i modelli di Analysis Services in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b05b2-107">To open the Analysis Services templates in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="b05b2-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Esplora modelli** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="b05b2-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="b05b2-109">Fare clic sull'icona del cubo per aprire i modelli di **Analysis Server**.</span><span class="sxs-lookup"><span data-stu-id="b05b2-109">Click the cube icon to open the **Analysis Server**templates.</span></span>  
  
### <a name="to-open-a-prediction-query-template"></a><span data-ttu-id="b05b2-110">Per aprire un modello di query di stima</span><span class="sxs-lookup"><span data-stu-id="b05b2-110">To open a prediction query template</span></span>  
  
1.  <span data-ttu-id="b05b2-111">Nell'elenco di modelli di Analysis Server in **Esplora modelli**espandere **DMX**, quindi espandere **Query di stima**.</span><span class="sxs-lookup"><span data-stu-id="b05b2-111">In **Template Explorer**, in the list of Analysis Server templates, expand **DMX**, and thenexpand **Prediction Queries**.</span></span>  
  
2.  <span data-ttu-id="b05b2-112">Fare doppio clic su **Query di stima singleton**.</span><span class="sxs-lookup"><span data-stu-id="b05b2-112">Double-click **Singleton Prediction**.</span></span>  
  
3.  <span data-ttu-id="b05b2-113">Nella finestra di dialogo **Connetti ad Analysis Services** digitare il nome del server con l'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che contiene il modello di data mining su cui eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="b05b2-113">In the **Connect to Analysis Services** dialog box, type the name of the server that has the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining model to be queried.</span></span>  
  
4.  <span data-ttu-id="b05b2-114">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="b05b2-114">Click **Connect**.</span></span>  
  
5.  <span data-ttu-id="b05b2-115">Il modello si apre nel database specificato, insieme con un Visualizzatore oggetti del modello di data mining che contiene le funzioni del data mining e un elenco di strutture di data mining e i modelli correlati.</span><span class="sxs-lookup"><span data-stu-id="b05b2-115">The template opens in the specified database, together with a mining model Object Browser that contains data mining functions and a list of data mining structures and related models.</span></span>  
  
### <a name="to-customize-the-singleton-query-template"></a><span data-ttu-id="b05b2-116">Per personalizzare il modello della query singleton</span><span class="sxs-lookup"><span data-stu-id="b05b2-116">To customize the singleton query template</span></span>  
  
1.  <span data-ttu-id="b05b2-117">Nel modello fare clic sull'elenco a discesa **Database disponibili** e quindi selezionare un'istanza di Analysis Services dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="b05b2-117">In the template, click the **Available Databases** drop-down list, and then select an instance of Analysis Service from the list.</span></span>  
  
2.  <span data-ttu-id="b05b2-118">Nell'elenco **Modello di data mining** selezionare il modello di data mining su cui si desidera eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="b05b2-118">In the **Mining Model** list, select the mining model that you want to query.</span></span>  
  
     <span data-ttu-id="b05b2-119">L'elenco di colonne nel modello di data mining viene visualizzato nel riquadro **Metadati** del Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="b05b2-119">The list of columns in the mining model appears in the **Metadata** pane of the object browser.</span></span>  
  
3.  <span data-ttu-id="b05b2-120">Scegliere **Imposta valori per parametri modello** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="b05b2-120">On the **Query** menu, select **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="b05b2-121">Nella riga dell' **elenco di selezione** digitare \* per ottenere tutte le colonne oppure digitare un elenco delimitato da virgole di colonne ed espressioni per ottenere colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="b05b2-121">In the **select list** row, type \* to return all columns, or type a comma-delimited list of columns and expressions to return specific columns.</span></span>  
  
     <span data-ttu-id="b05b2-122">Se si digita \*, viene restituita la colonna stimabile, insieme con le colonne per le quali vengono forniti nuovi valori nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="b05b2-122">If you type \*, the predictable column is returned, together with any columns for which you provide new values for in step 6.</span></span>  
  
     <span data-ttu-id="b05b2-123">Per il codice di esempio mostrato all'inizio di questo argomento, la riga dell' **elenco di selezione** è stata impostata su \*.</span><span class="sxs-lookup"><span data-stu-id="b05b2-123">For the sample code shown at the start of this topic, the **select list** row was set to \*.</span></span>  
  
5.  <span data-ttu-id="b05b2-124">Nella riga del **modello di data mining** digitare il nome del modello di data mining tra quelli presenti nell'elenco dei modelli di data mining visualizzati in **Esplora oggetti**.</span><span class="sxs-lookup"><span data-stu-id="b05b2-124">In the **mining model** row, type the name of the mining model from among the list of mining models that appear in **Object Explorer**.</span></span>  
  
     <span data-ttu-id="b05b2-125">Per il codice di esempio mostrato all'inizio di questo argomento, la riga del **modello di data mining** è stata impostata sul nome, `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="b05b2-125">For the sample code shown at the start of this topic, the **mining model** row was set to the name, `TM_Decision_Tree`.</span></span>  
  
6.  <span data-ttu-id="b05b2-126">Nella riga del **valore** digitare il nuovo valore dei dati per il quale si desidera effettuare una stima.</span><span class="sxs-lookup"><span data-stu-id="b05b2-126">In the **value** row, type the new data value for which you want to make a prediction.</span></span>  
  
     <span data-ttu-id="b05b2-127">Per il codice di esempio mostrato all'inizio di questo argomento, la riga del **valore** è stata impostata su `2` per stimare il comportamento di acquisto della bicicletta in base al numero di figli a casa.</span><span class="sxs-lookup"><span data-stu-id="b05b2-127">For the sample code shown at the start of this topic, the **value** row was set to `2` to predict bike buying behavior based on the number of children at home.</span></span>  
  
7.  <span data-ttu-id="b05b2-128">Nella riga della **colonna** digitare il nome della colonna nel modello di data mining su cui deve essere eseguito il mapping dei nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="b05b2-128">In the **column** row, type the name of the column in the mining model to which the new data should be mapped.</span></span>  
  
     <span data-ttu-id="b05b2-129">Per il codice di esempio mostrato all'inizio di questo argomento, la riga della **colonna** è stata impostata su `Number Children at Home` .</span><span class="sxs-lookup"><span data-stu-id="b05b2-129">For the sample code shown at the start of this topic, the **column** row was set to `Number Children at Home`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b05b2-130">Quando si usa la finestra di dialogo **Specifica valori per parametri modello** , non è necessario racchiudere il nome della colonna tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="b05b2-130">When you use the **Specify Values for Template Parameters** dialog box, you do not have to add square brackets around the column name.</span></span> <span data-ttu-id="b05b2-131">Le parentesi verranno aggiunte automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b05b2-131">The brackets will automatically be added for you.</span></span>  
  
8.  <span data-ttu-id="b05b2-132">Lasciare l' **alias di input** come `t` .</span><span class="sxs-lookup"><span data-stu-id="b05b2-132">Leave the **input alias** as `t`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="b05b2-133">Nel riquadro del testo della query cercare la sottolineatura rossa sotto la virgola e i puntini di sospensione che indicano un errore di sintassi.</span><span class="sxs-lookup"><span data-stu-id="b05b2-133">In the query text pane, find the red squiggle under the comma and ellipsis that indicates a syntax error.</span></span> <span data-ttu-id="b05b2-134">Eliminare i puntini di sospensione e aggiungere le condizioni di query aggiuntive desiderate.</span><span class="sxs-lookup"><span data-stu-id="b05b2-134">Delete the ellipsis, and add any additional query condition that you want.</span></span> <span data-ttu-id="b05b2-135">Se non si aggiungono altre condizioni, eliminare la virgola.</span><span class="sxs-lookup"><span data-stu-id="b05b2-135">If you do not add any other conditions, delete the comma.</span></span>  
  
     <span data-ttu-id="b05b2-136">Per il codice di esempio mostrato all'inizio di questo argomento, la condizione di query aggiuntiva è stata impostata su `'45' as [Age]`.</span><span class="sxs-lookup"><span data-stu-id="b05b2-136">For the sample code shown at the start of this topic, the additional query condition was set to `'45' as [Age]`.</span></span>  
  
11. <span data-ttu-id="b05b2-137">Fare clic su **Execute**.</span><span class="sxs-lookup"><span data-stu-id="b05b2-137">Click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b05b2-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b05b2-138">See Also</span></span>  
 [<span data-ttu-id="b05b2-139">Creazione di stime &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b05b2-139">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
  
