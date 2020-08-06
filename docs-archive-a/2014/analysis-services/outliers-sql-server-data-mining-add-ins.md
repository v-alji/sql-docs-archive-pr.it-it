---
title: Outlier (SQL Server componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exceptions [data mining]
- data preparation
- outliers [data mining]
- data cleaning
ms.assetid: e6fa7c62-4005-4792-9211-3b699377a517
author: minewiskan
ms.author: owend
ms.openlocfilehash: 92dddf3338d15e700576a13476ee364696bfd274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727215"
---
# <a name="outliers-sql-server-data-mining-add-ins"></a><span data-ttu-id="08cfc-102">Outlier (componenti aggiuntivi Data mining di SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08cfc-102">Outliers (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="08cfc-103">![Procedura guidata Rimozione outlier sulla barra multifunzione Data mining](media/dmc-outliers.gif "Procedura guidata Rimozione outlier sulla barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="08cfc-103">![Outliers wizard in Data Mining ribbon](media/dmc-outliers.gif "Outliers wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="08cfc-104">Un *outlier* indica un valore di dati problematico per uno dei motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="08cfc-104">An *outlier* means a data value that is problematic for any one of the following reasons:</span></span>  
  
-   <span data-ttu-id="08cfc-105">Il valore non rientra nell'intervallo previsto.</span><span class="sxs-lookup"><span data-stu-id="08cfc-105">Value is outside the expected range.</span></span>  
  
-   <span data-ttu-id="08cfc-106">I dati potrebbero essere stati immessi in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="08cfc-106">Data might have been entered incorrectly.</span></span>  
  
-   <span data-ttu-id="08cfc-107">Il valore non è presente.</span><span class="sxs-lookup"><span data-stu-id="08cfc-107">Value is missing.</span></span>  
  
-   <span data-ttu-id="08cfc-108">I dati sono costituiti da uno spazio o da un'altra stringa Null.</span><span class="sxs-lookup"><span data-stu-id="08cfc-108">Data consists of a space or other null string.</span></span>  
  
-   <span data-ttu-id="08cfc-109">Il valore è accurato, ma è talmente al di fuori della distribuzione che può influire in modo significativo sul modello.</span><span class="sxs-lookup"><span data-stu-id="08cfc-109">Value is accurate, but is so far outside the distribution that it can significantly affect the model.</span></span>  
  
 <span data-ttu-id="08cfc-110">Il client di data mining per Excel consente di rilevare questi dati, quindi di aggiornare i valori o di eliminarli.</span><span class="sxs-lookup"><span data-stu-id="08cfc-110">The Data Mining Client for Excel helps you detect this data, and then update the values or suppress them.</span></span> <span data-ttu-id="08cfc-111">È possibile, ad esempio, sostituire gli outlier con una media aritmetica o eliminare le righe che contengono valori potenzialmente errati.</span><span class="sxs-lookup"><span data-stu-id="08cfc-111">For example, you can replace outliers with an arithmetic mean, or you can delete rows that contain potentially wrong values.</span></span>  
  
## <a name="handling-outliers"></a><span data-ttu-id="08cfc-112">Gestione degli outlier</span><span class="sxs-lookup"><span data-stu-id="08cfc-112">Handling Outliers</span></span>  
 <span data-ttu-id="08cfc-113">La procedura guidata **Rimuovi outlier** offre diversi strumenti per gestire in modo appropriato gli outlier:</span><span class="sxs-lookup"><span data-stu-id="08cfc-113">The **Remove Outliers** wizard gives you several tools to handle outliers appropriately:</span></span>  
  
-   <span data-ttu-id="08cfc-114">È innanzitutto possibile esplorare i dati per comprendere meglio la distribuzione dei valori e la relazione degli outlier con gli altri dati.</span><span class="sxs-lookup"><span data-stu-id="08cfc-114">First, you can explore the data to better understand the distribution of values and the relationship of the outliers to other data.</span></span>  
  
     <span data-ttu-id="08cfc-115">È ad esempio possibile utilizzare l'attività **Esplora dati** per rivedere e correggere i valori.</span><span class="sxs-lookup"><span data-stu-id="08cfc-115">For example, you can use the **Explore Data** task to review and fix the values.</span></span> <span data-ttu-id="08cfc-116">Nella procedura guidata **Rimuovi outlier** viene inoltre visualizzato un grafico, una linea o un grafico a barre, per facilitare la comprensione della distribuzione di tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="08cfc-116">The **Remove Outliers** wizard also displays a graph, either a line or a bar chart, to help you understand the distribution of all values.</span></span>  
  
-   <span data-ttu-id="08cfc-117">Successivamente, è possibile utilizzare la procedura guidata **outlier** per rimuovere o modificare gli outlier.</span><span class="sxs-lookup"><span data-stu-id="08cfc-117">Next, you can use the **Outliers** wizard to remove or change outliers.</span></span> <span data-ttu-id="08cfc-118">Il metodo utilizzato varia a seconda che i valori siano discreti o continui.</span><span class="sxs-lookup"><span data-stu-id="08cfc-118">The method that you use depends on whether the values are discrete or continuous.</span></span>  
  
     <span data-ttu-id="08cfc-119">I valori discreti vengono visualizzati dalla procedura guidata su un grafico a barre, dove ogni barra rappresenta un valore specifico e l'altezza della barra indica il numero di case per ogni valore.</span><span class="sxs-lookup"><span data-stu-id="08cfc-119">The wizard displays discrete values in a bar chart, where each bar represents a specific value, and the height of the bar indicates the number of cases for each value.</span></span> <span data-ttu-id="08cfc-120">Trascinando il controllo del valore di soglia sul grafico, è possibile escludere le barre che rappresentano gruppi di valori estremi o potenzialmente errati.</span><span class="sxs-lookup"><span data-stu-id="08cfc-120">By sliding the threshold control on the chart, you can cut off bars that represent groups of extreme or potentially bad values.</span></span>  
  
-   <span data-ttu-id="08cfc-121">I valori continui vengono visualizzati dalla procedura guidata su un grafico a barre o a linee.</span><span class="sxs-lookup"><span data-stu-id="08cfc-121">The wizard displays continuous values either on a bar chart or line chart.</span></span> <span data-ttu-id="08cfc-122">Sul grafico a linee, il valore è rappresentato sull'asse X e il numero dei valori sull'asse Y.</span><span class="sxs-lookup"><span data-stu-id="08cfc-122">On the line chart, the value is represented on the x-axis and the count of values on the y-axis.</span></span>  
  
     <span data-ttu-id="08cfc-123">È possibile controllare se rimuovere o impostare i valori alle estremità inferiore e superiore del grafico modificando i valori **minimo** e **massimo** oppure facendo scorrere le barre.</span><span class="sxs-lookup"><span data-stu-id="08cfc-123">You can control whether to remove or keep values at the low and high ends of the chart by changing the **Minimum** and **Maximum** values, or sliding the bars.</span></span> <span data-ttu-id="08cfc-124">Quando si modificano le impostazioni dei valori minimo e massimo, i dati che verranno eliminati vengono illustrati sul grafico con un'ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="08cfc-124">As you change the minimum and maximum value settings, the data that will be suppressed is shown by shading in the graph.</span></span>  
  
 <span data-ttu-id="08cfc-125">Dopo aver selezionato gli outlier da utilizzare, è possibile indicare come questi devono essere gestiti dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="08cfc-125">After you have selected which outliers to work with, you tell the wizard how to handle the outliers.</span></span> <span data-ttu-id="08cfc-126">È possibile eliminare le righe contenenti i valori outlier oppure specificare un valore di sostituzione, ad esempio una media, un valore Null o un altro valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="08cfc-126">You can either delete the rows that contain the outlier values, or you can specify a replacement value, such as a mean, a null, or another value of your choice.</span></span>  
  
 <span data-ttu-id="08cfc-127">Nella procedura guidata sono infine disponibili alcune opzioni per la visualizzazione dei nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="08cfc-127">Finally, the wizard gives you some options for displaying the new data.</span></span> <span data-ttu-id="08cfc-128">È possibile sostituire i dati originali con i nuovi valori, aggiungere una nuova colonna alla tabella contenente i nuovi valori o creare un nuovo foglio di lavoro contenente i dati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="08cfc-128">You can replace the original data with the new values, add a new column to the table that contains the new values, or create a new worksheet that contains the updated data.</span></span>  
  
### <a name="using-the-outlier-wizard"></a><span data-ttu-id="08cfc-129">Utilizzo della procedura guidata relativa agli outlier</span><span class="sxs-lookup"><span data-stu-id="08cfc-129">Using the Outlier Wizard</span></span>  
  
1.  <span data-ttu-id="08cfc-130">Sulla barra multifunzione **data mining** fare clic su **Pulisci dati**e selezionare **outlier**.</span><span class="sxs-lookup"><span data-stu-id="08cfc-130">In the **Data Mining** ribbon, click **Clean Data**, and select **Outliers**.</span></span>  
  
2.  <span data-ttu-id="08cfc-131">Nella finestra di dialogo **selezione dati di origine** selezionare una tabella dati di Excel o un intervallo di celle, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="08cfc-131">In the **Select Source Data** dialog box, select an Excel data table, or a range of cells, and click **Next**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="08cfc-132">Non è possibile utilizzare la procedura guidata **outlier** per i dati esterni, a meno che non venga prima copiata in Excel.</span><span class="sxs-lookup"><span data-stu-id="08cfc-132">You cannot use the **Outliers** wizard on external data, unless you copy it to Excel first.</span></span>  
  
3.  <span data-ttu-id="08cfc-133">Nella finestra di dialogo **Seleziona colonna** selezionare una **singola** colonna.</span><span class="sxs-lookup"><span data-stu-id="08cfc-133">In the **Select Column** dialog box, select a **single** column.</span></span>  
  
     <span data-ttu-id="08cfc-134">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="08cfc-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="08cfc-135">Nella finestra di dialogo **Imposta valori di soglia** esaminare la distribuzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="08cfc-135">In the **Specify Thresholds** dialog box, review the distribution of data.</span></span>  
  
    -   <span data-ttu-id="08cfc-136">Se la colonna contiene valori discreti, verrà visualizzato un istogramma contenente il conteggio per ogni valore discreto.</span><span class="sxs-lookup"><span data-stu-id="08cfc-136">If the column contains discrete values, the wizard displays a histogram containing the count for each discrete value.</span></span>  
  
         <span data-ttu-id="08cfc-137">Supponendo che gli outlier siano valori rari, è possibile filtrarli modificando il valore **minimo** .</span><span class="sxs-lookup"><span data-stu-id="08cfc-137">Assuming that outliers are rare values, you can filter them out by changing the **Minimum** value.</span></span>  
  
    -   <span data-ttu-id="08cfc-138">Se la colonna contiene dati numerici, è possibile fare clic sul pulsante **Visualizza come discreto** o sul pulsante **Visualizza come numerico** per passare dalla visualizzazione dei valori in un grafico a barre o da un grafico a linee.</span><span class="sxs-lookup"><span data-stu-id="08cfc-138">If the column contains numeric data, you can click the **View as Discrete** button or the **View as Numeric** button to toggle between viewing the values in a bar chart or line chart.</span></span>  
  
5.  <span data-ttu-id="08cfc-139">Nella finestra di dialogo **Imposta soglie** scegliere l'intervallo di dati che si desidera memorizzare digitando un valore minimo e massimo oppure trascinando le barre del dispositivo di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="08cfc-139">In the **Specify Thresholds** dialog box, choose the range of data you want to keep by typing a minimum and maximum value, or by dragging the slider bars.</span></span> <span data-ttu-id="08cfc-140">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="08cfc-140">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="08cfc-141">Nella finestra di dialogo **gestione outlier** specificare se si desidera che i valori vengano eliminati o sostituiti e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="08cfc-141">In the **Outlier Handling** dialog box, specify whether you want the values to be deleted or replaced, and click **Next**.</span></span>  
  
7.  <span data-ttu-id="08cfc-142">Nella finestra di dialogo **Seleziona destinazione** specificare il percorso in cui si desidera salvare i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="08cfc-142">In the **Select Destination** dialog box, specify where you want the new data to be saved.</span></span>  
  
### <a name="related-options"></a><span data-ttu-id="08cfc-143">Opzioni correlate</span><span class="sxs-lookup"><span data-stu-id="08cfc-143">Related Options</span></span>  
 <span data-ttu-id="08cfc-144">La procedura guidata fornisce le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="08cfc-144">The wizard provides these options:</span></span>  
  
|<span data-ttu-id="08cfc-145">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="08cfc-145">**Options**</span></span>|<span data-ttu-id="08cfc-146">**Commentoo**</span><span class="sxs-lookup"><span data-stu-id="08cfc-146">**Comment**</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="08cfc-147">**Seleziona colonna**</span><span class="sxs-lookup"><span data-stu-id="08cfc-147">**Select Column**</span></span>|<span data-ttu-id="08cfc-148">È possibile utilizzare una sola colonna alla volta.</span><span class="sxs-lookup"><span data-stu-id="08cfc-148">You can work with only one column at a time.</span></span>|  
|<span data-ttu-id="08cfc-149">**Gestione di Impostazione valori di soglia**</span><span class="sxs-lookup"><span data-stu-id="08cfc-149">**Specify Thresholds Handling**</span></span>|<span data-ttu-id="08cfc-150">Impostare una soglia usando il valore **minimo** per escludere i valori presenti in un minor numero di righe rispetto al valore soglia.</span><span class="sxs-lookup"><span data-stu-id="08cfc-150">Set a threshold using **Minimum** to exclude values that are found in fewer rows than the threshold value.</span></span><br /><br /> <span data-ttu-id="08cfc-151">Inizialmente, il valore **minimo** è uguale al valore con il minor numero di righe e non è possibile rendere il valore minimo inferiore a tale valore.</span><span class="sxs-lookup"><span data-stu-id="08cfc-151">Initially the value in **Minimum** is equal to the value with the fewest rows, and you cannot make the minimum lower than that value.</span></span>|  
|<span data-ttu-id="08cfc-152">**Gestione outlier**</span><span class="sxs-lookup"><span data-stu-id="08cfc-152">**Outlier Handling**</span></span>|<span data-ttu-id="08cfc-153">Se si decide di eliminare gli outlier, è possibile modificare i dati nel foglio di lavoro corrente oppure creare una copia dei dati in un nuovo foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="08cfc-153">If you decide to delete outliers, you can either change the data in the current worksheet, or create a copy of the data in a new worksheet.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08cfc-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08cfc-154">See Also</span></span>  
 [<span data-ttu-id="08cfc-155">Esplorare &#40;dati SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="08cfc-155">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
  
