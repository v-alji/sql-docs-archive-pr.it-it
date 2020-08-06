---
title: Esplorazione e pulizia dei dati | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7c888c95-8986-461e-9f11-2395044b9d97
author: minewiskan
ms.author: owend
ms.openlocfilehash: 154c711f735bcbb472e49654139fd16a036a0dd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623569"
---
# <a name="exploring-and-cleaning-data"></a><span data-ttu-id="99225-102">Esplorazione e pulizia dei dati</span><span class="sxs-lookup"><span data-stu-id="99225-102">Exploring and Cleaning Data</span></span>
  <span data-ttu-id="99225-103">La preparazione dei dati non è una semplice pulizia dei dati.</span><span class="sxs-lookup"><span data-stu-id="99225-103">Data preparation is much more than data cleansing.</span></span> <span data-ttu-id="99225-104">Si tenga presente che la modalità con cui i dati vengono preparati influisce anche su come i risultati alla fine vengono interpretati.</span><span class="sxs-lookup"><span data-stu-id="99225-104">Remember that how data is prepared also affects how results are interpreted in the end.</span></span> <span data-ttu-id="99225-105">La preparazione dei dati include le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="99225-105">Data preparation involves these tasks:</span></span>  
  
-   <span data-ttu-id="99225-106">Esplorazione e controllo della distribuzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="99225-106">Exploring and checking the distribution of data.</span></span>  
  
-   <span data-ttu-id="99225-107">Pulizia dei record errati e scelta delle colonne per il data mining.</span><span class="sxs-lookup"><span data-stu-id="99225-107">Cleaning bad records, and choosing columns for data mining.</span></span>  
  
-   <span data-ttu-id="99225-108">Gestione corretta dei valori Null.</span><span class="sxs-lookup"><span data-stu-id="99225-108">Handling nulls appropriately.</span></span>  
  
-   <span data-ttu-id="99225-109">Creazione di contenitori per i valori o aggregazione di valori in blocchi diversi di tempo.</span><span class="sxs-lookup"><span data-stu-id="99225-109">Binning values, or aggregating values by different chunks of time.</span></span>  
  
-   <span data-ttu-id="99225-110">Aggiunta di etichette per migliorare l'utilizzabilità dei risultati.</span><span class="sxs-lookup"><span data-stu-id="99225-110">Adding labels to improve the usability of the results.</span></span>  
  
-   <span data-ttu-id="99225-111">Conversione dei tipi di dati o categorizzazione dei valori se necessario per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="99225-111">Converting data types or categorizing values where necessary for analysis.</span></span>  
  
 <span data-ttu-id="99225-112">Se non si ha familiarità con la modellazione dei dati, è consigliabile leggere l'argomento correlato [elenco di controllo della preparazione per il data mining](checklist-of-preparation-for-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="99225-112">If you are new to data modeling, we recommend that you read the related topic, [Checklist of Preparation for Data Mining](checklist-of-preparation-for-data-mining.md).</span></span>  
  
## <a name="data-preparation-tools"></a><span data-ttu-id="99225-113">Strumenti di preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="99225-113">Data Preparation Tools</span></span>  
 <span data-ttu-id="99225-114">I componenti aggiuntivi Data mining per Office includono i seguenti strumenti per la pulizia e la preparazione dei dati:</span><span class="sxs-lookup"><span data-stu-id="99225-114">The Data Mining Add-ins for Office includes the following tools for data cleansing and preparation:</span></span>  
  
### <a name="explore-data"></a><span data-ttu-id="99225-115">Esplorazione dati</span><span class="sxs-lookup"><span data-stu-id="99225-115">Explore Data</span></span>  
 <span data-ttu-id="99225-116">Utilizzare la procedura guidata **Esplora dati** per le attività di preparazione dei dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="99225-116">Use the **Explore Data** wizard for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="99225-117">Visualizzare un'anteprima dei dati per identificare gli errori che devono essere corretti prima dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="99225-117">Preview your data and identify errors that must be fixed prior to analysis.</span></span>  
  
-   <span data-ttu-id="99225-118">Raccogliere informazioni statistiche utili per comprendere il bilanciamento dei dati e delle attività di pulizia necessarie.</span><span class="sxs-lookup"><span data-stu-id="99225-118">Gather statistical information that is useful for understanding the balance of data and the required clean-up tasks.</span></span>  
  
-   <span data-ttu-id="99225-119">Identificare le colonne utili per l'analisi e pianificare la fase di modellazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="99225-119">Identify columns that are useful for analysis, and plan the data modeling phase.</span></span>  
  
 <span data-ttu-id="99225-120">[Esplorare i dati &#40;SQL Server componenti aggiuntivi Data Mining&#41;](explore-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="99225-120">[Explore Data &#40;SQL Server Data Mining Add-ins&#41;](explore-data-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="detect-and-handle-outliers"></a><span data-ttu-id="99225-121">Rilevamento e gestione degli outlier</span><span class="sxs-lookup"><span data-stu-id="99225-121">Detect and Handle Outliers</span></span>  
 <span data-ttu-id="99225-122">La procedura guidata **outlier** esegue il grafico della distribuzione dei valori nei dati e consente di rimuovere i valori estremi.</span><span class="sxs-lookup"><span data-stu-id="99225-122">The **Outliers** wizard graphs the distribution of values in your data and helps you remove extreme values.</span></span> <span data-ttu-id="99225-123">Utilizzare lo strumento **outlier** per le seguenti attività di preparazione dei dati:</span><span class="sxs-lookup"><span data-stu-id="99225-123">Use the **Outliers** tool for the following data preparation tasks:</span></span>  
  
-   <span data-ttu-id="99225-124">Determinare se i singoli valori siano affidabili, in base ai modelli individuati nei dati.</span><span class="sxs-lookup"><span data-stu-id="99225-124">Determine whether individual values are reliable, based on patterns found in the data.</span></span>  
  
-   <span data-ttu-id="99225-125">Esaminare valori anomali ed eseguire le azioni appropriate per eliminarli o sostituirli.</span><span class="sxs-lookup"><span data-stu-id="99225-125">Review unusual values and take action by deleting or replacing them.</span></span>  
  
-   <span data-ttu-id="99225-126">Definire l'ambito di un modello in un intervallo di valori specifico.</span><span class="sxs-lookup"><span data-stu-id="99225-126">Scope a model to a specific range of values.</span></span> <span data-ttu-id="99225-127">Se, ad esempio, si hanno outlier per un negozio specifico, è possibile eliminare tale valore e ottenere un modello in grado di eseguire una migliore stima degli altri negozi.</span><span class="sxs-lookup"><span data-stu-id="99225-127">For example, if you know that you have outliers at a particular store, you can eliminate that value and get a model that better predicts other stores.</span></span>  
  
 <span data-ttu-id="99225-128">[Outlier &#40;SQL Server i componenti aggiuntivi Data Mining&#41;](outliers-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="99225-128">[Outliers &#40;SQL Server Data Mining Add-ins&#41;](outliers-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="relabel-and-bin-data"></a><span data-ttu-id="99225-129">Modifica etichette e categorizzazione dati</span><span class="sxs-lookup"><span data-stu-id="99225-129">Relabel and Bin Data</span></span>  
 <span data-ttu-id="99225-130">La procedura guidata modifica **etichette** consente di raggruppare i dati in base ai valori in modo che sia possibile modificare le etichette nei dati.</span><span class="sxs-lookup"><span data-stu-id="99225-130">The **Relabel** wizard groups data by values so that you can change the labels on the data.</span></span> <span data-ttu-id="99225-131">Utilizzare lo strumento Modifica etichette per le attività di preparazione dei dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="99225-131">Use the Relabel tool for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="99225-132">Modificare i codici numerici utilizzati nei risultati di un sondaggio con una descrizione del significato dei codici.</span><span class="sxs-lookup"><span data-stu-id="99225-132">Change numeric codes used in survey results to a text description of what the numeric code means.</span></span>  
  
     <span data-ttu-id="99225-133">È ad esempio possibile sostituire Gender = 1 (Genere = 1) con Gender = Female (Genere = Femmina).</span><span class="sxs-lookup"><span data-stu-id="99225-133">For example, you might replace data entries such as Gender = 1 with Gender = Female.</span></span>  
  
-   <span data-ttu-id="99225-134">Suddividere i dati creando gruppi per rappresentare intervalli di numeri.</span><span class="sxs-lookup"><span data-stu-id="99225-134">Bin data, by creating groups to represents number ranges.</span></span>  
  
     <span data-ttu-id="99225-135">È possibile, ad esempio, sostituire una colonna Income dei numeri con etichette quali **reddito-moderato** e **reddito-alto**.</span><span class="sxs-lookup"><span data-stu-id="99225-135">For example, you might want to replace an Income column of numbers with labels such as **Income - Moderate** and **Income - High**.</span></span>  
  
-   <span data-ttu-id="99225-136">Comprimere i valori discreti in categorie.</span><span class="sxs-lookup"><span data-stu-id="99225-136">Collapse discrete values into categories.</span></span>  
  
     <span data-ttu-id="99225-137">Se ad esempio si possiedono troppi prodotti singoli per poter individuare un modello di acquisto, è possibile provare ad assegnare i prodotti a categorie più ampie.</span><span class="sxs-lookup"><span data-stu-id="99225-137">For example, if you have too many individual products to detect a pattern among purchases, you could try assigning products into broader categories.</span></span>  
  
 [<span data-ttu-id="99225-138">Modifica etichette &#40;SQL Server i componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="99225-138">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
### <a name="cleanse-data"></a><span data-ttu-id="99225-139">Pulizia dei dati</span><span class="sxs-lookup"><span data-stu-id="99225-139">Cleanse Data</span></span>  
 <span data-ttu-id="99225-140">La pulizia dei dati include un'ampia gamma di attività, la maggior parte delle quali sono supportate da componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="99225-140">Data cleansing encompasses a wide range of activities, most of which are supported by the add-ins</span></span>  
  
-   <span data-ttu-id="99225-141">Identificare i valori NULL e determinare se devono essere modificati in valori reali o essere gestiti come valori `Missing`.</span><span class="sxs-lookup"><span data-stu-id="99225-141">Identify nulls and determine whether they should be changed to a real value or handled as `Missing` values.</span></span>  
  
-   <span data-ttu-id="99225-142">Individuare i valori mancanti, quindi rimuoverli o assegnare loro un valore appropriato come medio, Null o un altro valore.</span><span class="sxs-lookup"><span data-stu-id="99225-142">Detect missing values, and then remove them, or impute an appropriate value, such as a mean, null, or other value.</span></span>  
  
 [<span data-ttu-id="99225-143">Esplorare &#40;dati SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="99225-143">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="99225-144">Modifica etichette &#40;SQL Server i componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="99225-144">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="99225-145">Estendi da esempio</span><span class="sxs-lookup"><span data-stu-id="99225-145">Fill From Example</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
### <a name="sample-data"></a><span data-ttu-id="99225-146">Dati di esempio</span><span class="sxs-lookup"><span data-stu-id="99225-146">Sample Data</span></span>  
 <span data-ttu-id="99225-147">La procedura guidata Dati di esempio consente di creare set di dati equilibrati per il training e il testing dei modelli in due modi.</span><span class="sxs-lookup"><span data-stu-id="99225-147">The Sample Data wizard provides two methods for creating balanced data sets for training and testing models.</span></span>  
  
-   <span data-ttu-id="99225-148">**Campionamento casuale.**</span><span class="sxs-lookup"><span data-stu-id="99225-148">**Random sampling.**</span></span> <span data-ttu-id="99225-149">Utilizzare questa opzione per estrarre un set di dati rappresentativo da un più ampio set di dati, da utilizzare come training o test.</span><span class="sxs-lookup"><span data-stu-id="99225-149">Use this option to extract a representative set of data from a larger data set, for use in either training or testing.</span></span> <span data-ttu-id="99225-150">I componenti aggiuntivi Data mining utilizzano il *campionamento stratificato* per assicurare che venga ottenuto un set di valori bilanciato per ogni variabile campionata.</span><span class="sxs-lookup"><span data-stu-id="99225-150">The Data Mining Add-ins use *stratified sampling* to ensure that a balanced set of values is obtained for each variable sampled.</span></span>  
  
-   <span data-ttu-id="99225-151">**Sovracampionamento.**</span><span class="sxs-lookup"><span data-stu-id="99225-151">**Oversampling.**</span></span> <span data-ttu-id="99225-152">Utilizzare questa opzione quando la quantità di dati a disposizione è inferiore a quella che si vorrebbe per un risultato di destinazione e occorre ponderare i dati con più precisione.</span><span class="sxs-lookup"><span data-stu-id="99225-152">Use this option when you have less data than you would like for a target outcome, and need to weight that data more heavily.</span></span> <span data-ttu-id="99225-153">Le frodi possono essere relativamente rare, ma è possibile sovracampionare i casi di frode per ottenere dati adeguati per la creazione di un modello.</span><span class="sxs-lookup"><span data-stu-id="99225-153">For example, fraud might be relatively rare, but you can oversample cases involving fraud to get adequate data for modeling.</span></span>  
  
 <span data-ttu-id="99225-154">[&#40;di dati di esempio SQL Server&#41;componenti aggiuntivi Data mining ](sample-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="99225-154">[Sample Data &#40;SQL Server Data Mining Add-ins&#41;](sample-data-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99225-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99225-155">See Also</span></span>  
 <span data-ttu-id="99225-156">[Creazione di un modello di data mining](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="99225-156">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="99225-157">[Convalida di modelli e utilizzo di modelli per la stima &#40;componenti aggiuntivi Data mining per Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="99225-157">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="99225-158">Distribuzione e scalabilità di modelli di data mining &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="99225-158">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
