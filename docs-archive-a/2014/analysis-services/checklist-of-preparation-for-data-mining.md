---
title: Elenco di controllo della preparazione per il data mining | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e056c95-ba06-413e-8dc1-4d411a447c3b
author: minewiskan
ms.author: owend
ms.openlocfilehash: e37b1adb6aebe5d5f8fd23f5289f52425f752a6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626411"
---
# <a name="checklist-of-preparation-for-data-mining"></a><span data-ttu-id="fb528-102">Elenco di controllo per la preparazione di data mining</span><span class="sxs-lookup"><span data-stu-id="fb528-102">Checklist of Preparation for Data Mining</span></span>
  <span data-ttu-id="fb528-103">Sebbene i componenti aggiuntivi Data mining forniscano un modo piuttosto semplice e divertente per creare e provare i modelli, quando è necessario ottenere risultati ripetibili e utilizzabili, è necessario concedere il tempo appropriato per la formulazione dei requisiti aziendali di base e per il recupero e la preparazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="fb528-103">Although the Data Mining Add-ins make it fairly easy and fun to create and experiment with models, when you need to get repeatable, actionable results, you must allow adequate time for formulating basic business requirements, and for obtaining and preparing data.</span></span> <span data-ttu-id="fb528-104">In questa sezione viene fornito un elenco di controllo per pianificare la ricerca e vengono descritti i problemi comuni.</span><span class="sxs-lookup"><span data-stu-id="fb528-104">This section provides a checklist to help you plan your investigation, and describes common problems.</span></span>  
  
## <a name="checklist-of-data-preparation"></a><span data-ttu-id="fb528-105">Elenco di controllo per la preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="fb528-105">Checklist of Data Preparation</span></span>  
 <span data-ttu-id="fb528-106">**È stato identificato un output definito chiaramente.**</span><span class="sxs-lookup"><span data-stu-id="fb528-106">**I have identified a clearly defined output.**</span></span>  
 <span data-ttu-id="fb528-107">Delineare un piano per l'utilizzo dei risultati.</span><span class="sxs-lookup"><span data-stu-id="fb528-107">Have a plan for how you will use the results.</span></span> <span data-ttu-id="fb528-108">Tipi di modelli diversi producono output diversi.</span><span class="sxs-lookup"><span data-stu-id="fb528-108">Different types of models have different outputs.</span></span> <span data-ttu-id="fb528-109">Un modello Time Series genera valori per una serie in futuro, facilmente comprensibili e utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="fb528-109">A time series model generates values for a series in the future, which are easily understood and acted on.</span></span> <span data-ttu-id="fb528-110">Gli altri modelli generano set complessi che devono essere analizzati da esperti del settore per produrre il valore ottimale.</span><span class="sxs-lookup"><span data-stu-id="fb528-110">Other models generate complex sets that must be analyzed by subject matter experts to yield the most value.</span></span>  
  
-   <span data-ttu-id="fb528-111">Quale output si desidera?</span><span class="sxs-lookup"><span data-stu-id="fb528-111">What output do you want?</span></span>  
  
-   <span data-ttu-id="fb528-112">L'output può essere definito come colonna o valore singolo oppure come altro risultato utilizzabile?</span><span class="sxs-lookup"><span data-stu-id="fb528-112">Can you define the output as a single column or value, or other actionable result?</span></span>  
  
-   <span data-ttu-id="fb528-113">Quali sono i criteri per sapere se il modello è stato utile?</span><span class="sxs-lookup"><span data-stu-id="fb528-113">What are your criteria for knowing that the model was useful?</span></span>  
  
-   <span data-ttu-id="fb528-114">Come verranno utilizzati e interpretati i risultati?</span><span class="sxs-lookup"><span data-stu-id="fb528-114">How will you use and interpret those results?</span></span>  
  
-   <span data-ttu-id="fb528-115">È possibile eseguire il mapping dei nuovi dati di input ai risultati previsti?</span><span class="sxs-lookup"><span data-stu-id="fb528-115">Can you map new input data to the expected results?</span></span>  
  
 <span data-ttu-id="fb528-116">**Si conoscono il significato, i tipi di dati e la distribuzione dei dati di input.**</span><span class="sxs-lookup"><span data-stu-id="fb528-116">**I know the meaning, data types, and distribution of the input data.**</span></span>  
 <span data-ttu-id="fb528-117">Esplorare e comprendere i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="fb528-117">Take some time to explore and understand your source data.</span></span> <span data-ttu-id="fb528-118">È importante che gli utenti che esaminano il modello comprendano quale tipo di dati di input sia stato utilizzato e sappiano come interpretare i tipi di dati e la variabilità, nonché il bilanciamento e la qualità.</span><span class="sxs-lookup"><span data-stu-id="fb528-118">It is important that people who review the model understand what kind of input data was used and know how to interpret the data types and the variability, as well as the balance and the quality.</span></span>  
  
-   <span data-ttu-id="fb528-119">Di quanti dati si dispone?</span><span class="sxs-lookup"><span data-stu-id="fb528-119">How much data do you have?</span></span> <span data-ttu-id="fb528-120">Sono disponibili dati sufficienti per la modellazione?</span><span class="sxs-lookup"><span data-stu-id="fb528-120">Is there sufficient data for modeling?</span></span>  
  
     <span data-ttu-id="fb528-121">Non è necessario disporre di una quantità enorme, più piccola e bilanciata, può risultare migliore.</span><span class="sxs-lookup"><span data-stu-id="fb528-121">It need not be a huge amount - smaller and balanced can be better.</span></span>  
  
-   <span data-ttu-id="fb528-122">I dati provengono da più origini o da un'unica origine?</span><span class="sxs-lookup"><span data-stu-id="fb528-122">Is the data from multiple sources, or a single source?</span></span>  
  
-   <span data-ttu-id="fb528-123">I dati sono già stati elaborati e puliti?</span><span class="sxs-lookup"><span data-stu-id="fb528-123">Is the data already processed and clean?</span></span> <span data-ttu-id="fb528-124">Sono disponibili più dati di input?</span><span class="sxs-lookup"><span data-stu-id="fb528-124">Is more input data available?</span></span>  
  
-   <span data-ttu-id="fb528-125">Si sa come è stato modificato prima della ricezione: come è possibile che i dati siano stati troncati, riepilogati o convertiti?</span><span class="sxs-lookup"><span data-stu-id="fb528-125">Do you know how it was manipulated before you received it - how data might have been truncated, summarized, or converted?</span></span>  
  
-   <span data-ttu-id="fb528-126">I dati di input presentano alcuni risultati di esempio da poter utilizzare per il training?</span><span class="sxs-lookup"><span data-stu-id="fb528-126">Does the input data have some example results that can be used for training?</span></span>  
  
 <span data-ttu-id="fb528-127">**Si comprende il livello di integrità dei dati di cui si dispone e il livello necessario.**</span><span class="sxs-lookup"><span data-stu-id="fb528-127">**I understand the level of data integrity we have and the level we need.**</span></span>  
 <span data-ttu-id="fb528-128">Dati errati possono influire sulla qualità del modello o impedire completamente la compilazione del modello.</span><span class="sxs-lookup"><span data-stu-id="fb528-128">Bad data can affect the quality of the model, or prevent the model from being built at all.</span></span> <span data-ttu-id="fb528-129">È necessario disporre di una buona conoscenza della distribuzione e del significato dei dati e di come sono arrivati a questo stato.</span><span class="sxs-lookup"><span data-stu-id="fb528-129">You should have a good understanding of both the distribution and meaning of the data, and how it came to this state.</span></span> <span data-ttu-id="fb528-130">È necessario comprendere se è possibile o appropriato semplificare i dati mediante l'assegnazione di etichette, il troncamento dei tipi di dati numerici o il riepilogo.</span><span class="sxs-lookup"><span data-stu-id="fb528-130">You'll need to understand if it is possible or appropriate to simplify the data by labeling, truncating numeric data types, or by summarizing.</span></span>  
  
-   <span data-ttu-id="fb528-131">Etichette di dati: sono chiare e corrette?</span><span class="sxs-lookup"><span data-stu-id="fb528-131">Data labels: are they clear and correct?</span></span>  
  
-   <span data-ttu-id="fb528-132">Tipi di dati: sono appropriati e sono stati modificati?</span><span class="sxs-lookup"><span data-stu-id="fb528-132">Data types: are they appropriate, and have they been changed?</span></span>  
  
-   <span data-ttu-id="fb528-133">Sono stati ordinati, puliti o eliminati dati errati?</span><span class="sxs-lookup"><span data-stu-id="fb528-133">Have you sorted, cleaned up, or discarded wrong data?</span></span>  
  
     <span data-ttu-id="fb528-134">Si è verificato che non esistono duplicati?</span><span class="sxs-lookup"><span data-stu-id="fb528-134">Have you verified there are no duplicates?</span></span>  
  
-   <span data-ttu-id="fb528-135">Come verranno gestiti i valori mancanti?</span><span class="sxs-lookup"><span data-stu-id="fb528-135">How will you handle missing values?</span></span> <span data-ttu-id="fb528-136">I valori mancanti hanno un significato?</span><span class="sxs-lookup"><span data-stu-id="fb528-136">Do missing values have a meaning?</span></span>  
  
-   <span data-ttu-id="fb528-137">Sono state verificate le origini per vedere se è possibile che siano stati introdotti errori nel processo di importazione?</span><span class="sxs-lookup"><span data-stu-id="fb528-137">Have you verified the sources to see if any errors might have been introduced in the import process?</span></span>  
  
     <span data-ttu-id="fb528-138">Dov'è archiviato l'input?</span><span class="sxs-lookup"><span data-stu-id="fb528-138">Where is the input stored?</span></span> <span data-ttu-id="fb528-139">Per quanto tempo resta disponibile?</span><span class="sxs-lookup"><span data-stu-id="fb528-139">How long does it stay available?</span></span>  
  
     <span data-ttu-id="fb528-140">Esiste un dizionario dei dati?</span><span class="sxs-lookup"><span data-stu-id="fb528-140">Is there a data dictionary?</span></span> <span data-ttu-id="fb528-141">È possibile crearne uno?</span><span class="sxs-lookup"><span data-stu-id="fb528-141">Can you create one?</span></span>  
  
-   <span data-ttu-id="fb528-142">Se sono stati combinati set di dati, si è verificata la presenza di più colonne che rappresentano gli stessi dati?</span><span class="sxs-lookup"><span data-stu-id="fb528-142">If you combined data sets, did you check for multiple columns representing the same data?</span></span>  
  
 <span data-ttu-id="fb528-143">**So dove sono archiviati i dati di origine, da dove provengono e come vengono elaborati. Se necessario, è possibile ripetere facilmente il processo.**</span><span class="sxs-lookup"><span data-stu-id="fb528-143">**I know where source data is stored, where it came from, and how it is processed. The process can be easily repeated if needed.**</span></span>  
 <span data-ttu-id="fb528-144">I set di dati monouso sono buoni per gli esperimenti, ma se si desidera spostare il modello nell'ambiente di produzione, è opportuno pensare in anticipo in che modo è possibile applicare il processo di pulizia ai dati operativi.</span><span class="sxs-lookup"><span data-stu-id="fb528-144">One-off data sets are fine for experiments, but if you ever want to move the model into production, you'll want to think in advance about how the cleaning process can be applied to operational data.</span></span> <span data-ttu-id="fb528-145">Inoltre, se si dispone di dati operativi, è necessario conoscerne il modo in cui potrebbe essere stato modificato prima di ottenerlo. è necessario comprendere come è stato arrotondato o riepilogato, certamente.</span><span class="sxs-lookup"><span data-stu-id="fb528-145">Also, if you have operational data, you need to know how it might have been altered before you got it-you'll need to know how it was rounded, or summarized, certainly.</span></span>  
  
-   <span data-ttu-id="fb528-146">Si desidera poter ripetere il test?</span><span class="sxs-lookup"><span data-stu-id="fb528-146">Do you want to be able to repeat the experiment?</span></span>  
  
-   <span data-ttu-id="fb528-147">Quali strumenti si utilizzeranno per preparare i dati in un formato che supporta l'analisi dei dati?</span><span class="sxs-lookup"><span data-stu-id="fb528-147">What tools will you use to prepare data in a format that supports data analysis?</span></span> <span data-ttu-id="fb528-148">Possono essere automatizzati o è necessario un utente per rivederli e pulirli in Excel?</span><span class="sxs-lookup"><span data-stu-id="fb528-148">Can it be automated or do you need someone to review and clean up in Excel?</span></span>  
  
-   <span data-ttu-id="fb528-149">Se si utilizzano dati provenienti da un altro sistema, sarà possibile acquisire e tenere traccia dei filtri applicati?</span><span class="sxs-lookup"><span data-stu-id="fb528-149">If you are sourcing data from another system, will you be able to capture and track filters that were applied?</span></span>  
  
-   <span data-ttu-id="fb528-150">Anche il framework di elaborazione dati può applicare gli algoritmi di apprendimento automatico, eseguire test e visualizzare i risultati?</span><span class="sxs-lookup"><span data-stu-id="fb528-150">Can your data processing framework also apply machine learning algorithms, perform tests, and visualize results?</span></span>  
  
 <span data-ttu-id="fb528-151">**È stata decisa la granularità desiderata di stime e i dati sono stati modificati per restituire tali unità.**</span><span class="sxs-lookup"><span data-stu-id="fb528-151">**We have agreed on the desired granularity of predictions and our data has been modified to output those units.**</span></span>  
 <span data-ttu-id="fb528-152">Decidere della granularità dei risultati desiderati prima della preparazione dei dati. Ad esempio, si desidera ottenere le stime di vendita giornaliere o trimestrali?</span><span class="sxs-lookup"><span data-stu-id="fb528-152">Decide on the granularity of the results you want before preparing data, For example, do you want sales predictions by the day, or for each quarter?</span></span> <span data-ttu-id="fb528-153">Si potrebbe provare a configurare strutture dei dati diverse per gli stessi dati, per gestire diversi livelli di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="fb528-153">You might consider setting up different data structures for the same data, to handle different levels of summary.</span></span>  
  
-   <span data-ttu-id="fb528-154">Qual è l'unità di misura o l'unità di tempo corrente?</span><span class="sxs-lookup"><span data-stu-id="fb528-154">What is the current unit of measure or unit of time?</span></span>  
  
     <span data-ttu-id="fb528-155">Quale unità si desidera utilizzare nei risultati?</span><span class="sxs-lookup"><span data-stu-id="fb528-155">What unit do you want to use in the results?</span></span>  
  
-   <span data-ttu-id="fb528-156">È possibile definire un'unità di base (ad esempio, una chiamata di giorno/ora/min/istruzione) per tutti i dati di input?</span><span class="sxs-lookup"><span data-stu-id="fb528-156">Is it possible to define a basic unit (e.g. day/ hour / min / instruction call) for all input data?</span></span>  
  
     <span data-ttu-id="fb528-157">Si desidera eseguire il rollup a unità più elevate?</span><span class="sxs-lookup"><span data-stu-id="fb528-157">Do you want to rollup to higher units?</span></span>  
  
-   <span data-ttu-id="fb528-158">Le categorie sono identificate da etichette in modo coerente?</span><span class="sxs-lookup"><span data-stu-id="fb528-158">Are categories labeled consistently?</span></span> <span data-ttu-id="fb528-159">È facile aggiungere o rimuovere le categorie?</span><span class="sxs-lookup"><span data-stu-id="fb528-159">Is it easy to add or remove categories?</span></span>  
  
 <span data-ttu-id="fb528-160">**La progettazione sperimentale è ripetibile e riproducibile.**</span><span class="sxs-lookup"><span data-stu-id="fb528-160">**Our experimental design is repeatable and reproducible.**</span></span>  
 <span data-ttu-id="fb528-161">Prendere in considerazione strategie per l'analisi e la convalida dei risultati e un piano per acquisire snapshot di dati, per assicurarsi di poter far risalire gli effetti ai dati.</span><span class="sxs-lookup"><span data-stu-id="fb528-161">Consider strategies for analyzing and validating your results and plan to capture a data snapshot, to make sure you can trace back effects to data.</span></span> <span data-ttu-id="fb528-162">Se viene utilizzato un valore di inizializzazione casuale, i risultati possono variare leggermente.</span><span class="sxs-lookup"><span data-stu-id="fb528-162">If a random seed is used, the results can differ subtly.</span></span> <span data-ttu-id="fb528-163">Questa operazione può rendere difficile confrontare e convalidare i modelli.</span><span class="sxs-lookup"><span data-stu-id="fb528-163">This can make it difficult to compare and validate models.</span></span>  
  
-   <span data-ttu-id="fb528-164">Se si effettuano molte modifiche personalizzate ai dati, cosa accade la volta successiva che si desidera compilare il modello?</span><span class="sxs-lookup"><span data-stu-id="fb528-164">If you make a lot of custom changes to the data, what happens the next time you want to build the model?</span></span>  
  
-   <span data-ttu-id="fb528-165">È stata già definita una procedura manuale o un processo approvato da utilizzare per elaborare l'input e ottenere gli output desiderati?</span><span class="sxs-lookup"><span data-stu-id="fb528-165">Has a manual procedure or approved process already been defined that you should use to process input and get the desired outputs?</span></span>  
  
-   <span data-ttu-id="fb528-166">Si è deciso di utilizzare un valore di inizializzazione per il modello?</span><span class="sxs-lookup"><span data-stu-id="fb528-166">Have you decided to use a seed for the model?</span></span>  
  
 <span data-ttu-id="fb528-167">**Si dispone delle informazioni del dominio per convalidare i risultati o dell'accesso agli esperti del settore che possono fornire consigli.**</span><span class="sxs-lookup"><span data-stu-id="fb528-167">**We have the domain knowledge to validate the results, or have access to subject matter experts who can advise.**</span></span>  
 <span data-ttu-id="fb528-168">Convalidare le variabili, il modello e i risultati.</span><span class="sxs-lookup"><span data-stu-id="fb528-168">Take time to validate the variables, the model, and the results.</span></span> <span data-ttu-id="fb528-169">Richiedere l'aiuto di esperti per valutare interazioni e risultati.</span><span class="sxs-lookup"><span data-stu-id="fb528-169">Get the help of experts to assess interactions and results.</span></span> <span data-ttu-id="fb528-170">Tuttavia, non consentire ai presupposti di sovraregolare l'evidenza.</span><span class="sxs-lookup"><span data-stu-id="fb528-170">However, don't let assumptions overrule evidence.</span></span> <span data-ttu-id="fb528-171">Mostrare piena apertura verso risultati nuovi e imprevisti.</span><span class="sxs-lookup"><span data-stu-id="fb528-171">Be open to new and unexpected findings.</span></span>  
  
-   <span data-ttu-id="fb528-172">Sono disponibili informazioni di dominio che consentono di filtrare i dati e ridurre segnalazioni non significative di input?</span><span class="sxs-lookup"><span data-stu-id="fb528-172">Is domain knowledge available to help in filtering data and reducing input noise?</span></span>  
  
-   <span data-ttu-id="fb528-173">Gli esperti di dominio possono aiutare a interpretare i risultati e suggerire miglioramenti?</span><span class="sxs-lookup"><span data-stu-id="fb528-173">Can domain experts help understand interpret the results and suggest improvements?</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb528-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb528-174">See Also</span></span>  
 [<span data-ttu-id="fb528-175">Scelta di dati per il data mining</span><span class="sxs-lookup"><span data-stu-id="fb528-175">Choosing Data for Data Mining</span></span>](choosing-data-for-data-mining.md)  
  
  
