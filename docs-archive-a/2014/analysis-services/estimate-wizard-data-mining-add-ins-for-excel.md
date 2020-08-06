---
title: Procedura guidata stima (componenti aggiuntivi Data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- estimation
ms.assetid: 7f2b1d5f-c9b3-4939-b35a-34ae099af15f
author: minewiskan
ms.author: owend
ms.openlocfilehash: ace9fa3a62690061677312d4f7dbb6b8a1d0ea5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718881"
---
# <a name="estimate-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="5c27d-102">Procedura guidata Stima (componenti aggiuntivi Data mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="5c27d-102">Estimate Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="5c27d-103">![Procedura guidata Stima sulla barra multifunzione Data mining](media/dmc-estimate.gif "Procedura guidata Stima sulla barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="5c27d-103">![Estimate wizard in Data Mining ribbon](media/dmc-estimate.gif "Estimate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="5c27d-104">La procedura guidata **Valutazione** consente di creare un modello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="5c27d-104">The **Estimate** wizard helps you create an estimation model.</span></span> <span data-ttu-id="5c27d-105">Un modello di valutazione consente di estrarre modelli dai dati e di utilizzarli per stimare i fattori che influiscono sui risultati.</span><span class="sxs-lookup"><span data-stu-id="5c27d-105">An estimation model extracts patterns from data and uses the patterns to predict the factors that affect outcomes.</span></span>  
  
 <span data-ttu-id="5c27d-106">La valutazione viene utilizzata per stimare i risultati numerici.</span><span class="sxs-lookup"><span data-stu-id="5c27d-106">Estimation is used for predicting numeric outcomes.</span></span> <span data-ttu-id="5c27d-107">Se, ad esempio, la colonna di destinazione contiene il numero dei diplomati nelle scuole, espresso come percentuale, è possibile analizzare i fattori che possono determinare un aumento o una riduzione di questo numero, ad esempio il numero di studenti per scuola, il rapporto numerico tra studenti e insegnanti e il numero di insegnanti.</span><span class="sxs-lookup"><span data-stu-id="5c27d-107">For example, if your target column contains graduation rates for schools, with graduation rates expressed as percentages, you could analyze factors that potentially increase or decrease graduation rates, such as the number of students per school, the student-teacher ratio, and the number of teachers.</span></span>  
  
## <a name="using-the-estimate-data-wizard"></a><span data-ttu-id="5c27d-108">Utilizzo della procedura guidata Valutazione dati</span><span class="sxs-lookup"><span data-stu-id="5c27d-108">Using the Estimate Data Wizard</span></span>  
  
1.  <span data-ttu-id="5c27d-109">Sulla barra multifunzione **data mining** fare clic su **stima**.</span><span class="sxs-lookup"><span data-stu-id="5c27d-109">On the **Data Mining** ribbon, click **Estimate**.</span></span>  
  
2.  <span data-ttu-id="5c27d-110">Nella finestra di dialogo **selezione dati di origine** selezionare i dati di origine da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5c27d-110">In the **Select Source Data** dialog box, select the source data to use.</span></span> <span data-ttu-id="5c27d-111">È possibile utilizzare i dati in una **tabella**di Excel, un **intervallo di dati**di Excel o da un' **origine dati esterna**.</span><span class="sxs-lookup"><span data-stu-id="5c27d-111">You can use data in an Excel **Table**, an Excel **Data Range**, or from an **External data source**.</span></span>  
  
     <span data-ttu-id="5c27d-112">Se si utilizza un'origine dati esterna, è possibile creare viste o query personalizzate e salvarle come origine dati di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c27d-112">If you use an external data source, you can create custom views or queries and save them as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="5c27d-113">Nella finestra di dialogo **stima** selezionare la **colonna da analizzare**.</span><span class="sxs-lookup"><span data-stu-id="5c27d-113">In the **Estimation** dialog box, select the **Column to analyze**.</span></span>  
  
     <span data-ttu-id="5c27d-114">La colonna di destinazione deve contenere dati numerici continui.</span><span class="sxs-lookup"><span data-stu-id="5c27d-114">The target column must contain continuous numeric data.</span></span>  
  
4.  <span data-ttu-id="5c27d-115">Selezionare le colonne da utilizzare come input selezionando la casella di controllo **colonne di input** .</span><span class="sxs-lookup"><span data-stu-id="5c27d-115">Select columns to use as input by checking the **Input columns** checkbox.</span></span>  
  
     <span data-ttu-id="5c27d-116">Queste colonne verranno utilizzate per creare i modelli.</span><span class="sxs-lookup"><span data-stu-id="5c27d-116">These columns will be used to create the patterns.</span></span> <span data-ttu-id="5c27d-117">Eliminare dall'analisi tutte le colonne di scarsa utilità, ad esempio i numeri di ID o le colonne che contengono dati irrilevanti.</span><span class="sxs-lookup"><span data-stu-id="5c27d-117">You should eliminate from analysis any columns that are not likely to help, such as ID numbers, or columns that contain irrelevant data.</span></span>  
  
5.  <span data-ttu-id="5c27d-118">La procedura guidata **stima** consente di selezionare l'algoritmo ottimale per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="5c27d-118">The **Estimate** wizard selects the optimum algorithm for your data set.</span></span> <span data-ttu-id="5c27d-119">Tuttavia, è possibile fare clic su **parametri** per aprire la finestra di dialogo **parametri algoritmo** e impostare le opzioni avanzate.</span><span class="sxs-lookup"><span data-stu-id="5c27d-119">However, you can click **Parameters** to open the **Algorithm Parameters** dialog box and set advanced options.</span></span>  
  
6.  <span data-ttu-id="5c27d-120">Se i dati sono numerici ed è possibile usare il metodo di regressione lineare Microsoft, è possibile selezionare la casella **regressore** per qualsiasi colonna numerica che si conosca (o sospetta) correlata al valore stimabile.</span><span class="sxs-lookup"><span data-stu-id="5c27d-120">If your data is numeric and you can use the Microsoft Linear Regression method, you can check the **Regressor** box for any numeric columns that you know (or strongly suspect) to be correlated with the predictable value.</span></span>  
  
     <span data-ttu-id="5c27d-121">L'algoritmo testerà quindi i valori in tale colonna per determinare se influiscono sui risultati.</span><span class="sxs-lookup"><span data-stu-id="5c27d-121">The algorithm will then test the values in that column to determine if they affect the outcomes.</span></span> <span data-ttu-id="5c27d-122">In caso di dubbi, fare clic su **Suggerisci** e l'algoritmo eseguirà il test di tutte le colonne e rileverà automaticamente i valori migliori da utilizzare come regressori.</span><span class="sxs-lookup"><span data-stu-id="5c27d-122">If you are unsure, click **Suggest** and the algorithm will test all column and automatically detect the best values to use as regressors.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c27d-123">Per creare una valutazione, è necessario un regressore.</span><span class="sxs-lookup"><span data-stu-id="5c27d-123">A regressor is required to create an estimate.</span></span> <span data-ttu-id="5c27d-124">Tramite la procedura guidata viene consigliato sempre il regressore migliore, in base a un passaggio iniziale di analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="5c27d-124">The wizard always recommends the best regressor, based on an initial pass over the data.</span></span> <span data-ttu-id="5c27d-125">Se pertanto non si è sicuri, è consigliabile accettare le selezioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="5c27d-125">Therefore, if you are not sure, it is best to accept the recommended selections.</span></span>  
  
7.  <span data-ttu-id="5c27d-126">Nella pagina **suddivisione dei dati in set di training e di testing** specificare se si desidera creare un piccolo subset di dati per il testing.</span><span class="sxs-lookup"><span data-stu-id="5c27d-126">On the **Split data into training and testing sets** page, specify whether you want to create a small subset of the data for testing.</span></span>  
  
8.  <span data-ttu-id="5c27d-127">Nella pagina **fine** specificare i nomi per la nuova struttura di data mining e la modalità di data mining oppure accettare i nomi predefiniti specificati.</span><span class="sxs-lookup"><span data-stu-id="5c27d-127">On the **Finish** page, provide names for the new mining structure and mining mode, or accept the default names that are provided.</span></span>  
  
9. <span data-ttu-id="5c27d-128">Impostare le opzioni per l'utilizzo del modello.</span><span class="sxs-lookup"><span data-stu-id="5c27d-128">Set options for using the model.</span></span>  
  
    -   <span data-ttu-id="5c27d-129">Selezionare **Sfoglia** per aprire immediatamente il modello in un visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="5c27d-129">Select **Browse** to immediately open the model in a viewer.</span></span>  
  
         <span data-ttu-id="5c27d-130">Il visualizzatore grafico consente di visualizzare un grafico della rete di dipendenze e l'albero delle decisioni generato dall'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="5c27d-130">This graphical viewer displays a dependency network graph and the decision tree generated by the algorithm.</span></span> <span data-ttu-id="5c27d-131">Esaminando queste informazioni, è possibile comprendere meglio i fattori che contribuiscono a generare i valori valutati.</span><span class="sxs-lookup"><span data-stu-id="5c27d-131">By exploring this information, you can better understand the factors that contribute to the estimated values.</span></span>  
  
    -   <span data-ttu-id="5c27d-132">Selezionare **Abilita drill-through** per consentire agli utenti dell'analisi di visualizzare i dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="5c27d-132">Select **Enable drillthrough** to let users of your analysis view the underlying data.</span></span>  
  
         <span data-ttu-id="5c27d-133">Questa opzione è disponibile solo se si utilizzano gli algoritmi Decision Trees o Linear Regression.</span><span class="sxs-lookup"><span data-stu-id="5c27d-133">This option is available only if you use the Decision Trees opr Linear Regression algorithms.</span></span>  
  
    -   <span data-ttu-id="5c27d-134">**Usa modello temporaneo**.</span><span class="sxs-lookup"><span data-stu-id="5c27d-134">**Use temporary model**.</span></span> <span data-ttu-id="5c27d-135">Se si seleziona questa opzione, il modello non verrà salvato nel server.</span><span class="sxs-lookup"><span data-stu-id="5c27d-135">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="5c27d-136">I modelli temporanei vengono eliminati quando si chiude Excel.</span><span class="sxs-lookup"><span data-stu-id="5c27d-136">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-estimation-models"></a><span data-ttu-id="5c27d-137">Ulteriori informazioni sui modelli di valutazione</span><span class="sxs-lookup"><span data-stu-id="5c27d-137">More About Estimation Models</span></span>  
 <span data-ttu-id="5c27d-138">La procedura guidata **stima** supporta l'utilizzo di uno degli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c27d-138">The **Estimate** wizard supports the use of any of the following algorithms:</span></span>  
  
-   <span data-ttu-id="5c27d-139">Algoritmo Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="5c27d-139">Microsoft Decision Tree algorithm</span></span>  
  
-   <span data-ttu-id="5c27d-140">Algoritmo Microsoft Linear Regression</span><span class="sxs-lookup"><span data-stu-id="5c27d-140">Microsoft Linear Regression algorithm</span></span>  
  
-   <span data-ttu-id="5c27d-141">Algoritmo Microsoft Logistic Regression</span><span class="sxs-lookup"><span data-stu-id="5c27d-141">Microsoft Logistic Regression algorithm</span></span>  
  
-   <span data-ttu-id="5c27d-142">Algoritmo Microsoft Neural Network</span><span class="sxs-lookup"><span data-stu-id="5c27d-142">Microsoft Neural network algorithm</span></span>  
  
 <span data-ttu-id="5c27d-143">Nella finestra di dialogo **parametri algoritmo** è possibile impostare opzioni avanzate aggiuntive, a seconda dell'algoritmo scelto.</span><span class="sxs-lookup"><span data-stu-id="5c27d-143">In the **Algorithm Parameters** dialog box, you can set additional advanced options, depending on which algorithm you chose.</span></span> <span data-ttu-id="5c27d-144">Per informazioni sulle opzioni per ciascun algoritmo, vedere questi argomenti nella documentazione online di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="5c27d-144">For information on the options for each algorithm see these topics in SQL Server Books Online:</span></span>  
  
 [<span data-ttu-id="5c27d-145">Guida di riferimento tecnico per l'algoritmo Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="5c27d-145">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="5c27d-146">Riferimento tecnico per l'algoritmo Microsoft Linear Regression</span><span class="sxs-lookup"><span data-stu-id="5c27d-146">Microsoft Linear Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-linear-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="5c27d-147">Riferimento tecnico per l'algoritmo Microsoft Logistic Regression</span><span class="sxs-lookup"><span data-stu-id="5c27d-147">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="5c27d-148">Microsoft Neural Network Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="5c27d-148">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="5c27d-149">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c27d-149">Requirements</span></span>  
 <span data-ttu-id="5c27d-150">Per utilizzare la procedura guidata Valutazione dati, è necessario essere connessi a un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c27d-150">To use the Estimate Data Wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="5c27d-151">Per informazioni su come creare una connessione, vedere [connettersi ai dati di origine &#40;client di data mining per&#41;Excel ](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5c27d-151">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="5c27d-152">Per utilizzare l'algoritmo di valutazione, il risultato che si sta tentando di stimare deve essere espresso come valore numerico, ad esempio valuta, importo delle vendite, data oppure ora.</span><span class="sxs-lookup"><span data-stu-id="5c27d-152">To use the estimation algorithm, the outcome that you are trying to predict must be expressed as a numeric value, such as a currency, sales amount, date, or time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c27d-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c27d-153">See Also</span></span>  
 <span data-ttu-id="5c27d-154">[Creazione di un modello di data mining](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="5c27d-154">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="5c27d-155">Diagramma dell'albero delle decisioni procedura dettagliata &#40;componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="5c27d-155">Decision Tree Diagram Walkthrough  &#40;Data Mining Add-ins&#41;</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
  
