---
title: Attività Profiling dati e visualizzatore | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], about data profiling
- data profiling
- profiling data
ms.assetid: 756840e3-aa09-45cd-9951-1a17af4b5925
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ae15d1cc75f8db04c36a830e44d07800c5aecf75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627336"
---
# <a name="data-profiling-task-and-viewer"></a><span data-ttu-id="0f521-102">Attività Profiling dati e visualizzatore</span><span class="sxs-lookup"><span data-stu-id="0f521-102">Data Profiling Task and Viewer</span></span>
  <span data-ttu-id="0f521-103">L'attività Profiling dati offre funzionalità di profiling dei dati all'interno del processo di estrazione, trasformazione e caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="0f521-103">The Data Profiling task provides data profiling functionality inside the process of extracting, transforming, and loading data.</span></span> <span data-ttu-id="0f521-104">L'attività Profiling dati offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f521-104">By using the Data Profiling task, you can achieve the following benefits:</span></span>  
  
-   <span data-ttu-id="0f521-105">Analisi più efficace dei dati di origine</span><span class="sxs-lookup"><span data-stu-id="0f521-105">Analyze the source data more effectively</span></span>  
  
-   <span data-ttu-id="0f521-106">Migliore comprensione dei dati di origine</span><span class="sxs-lookup"><span data-stu-id="0f521-106">Understand the source data better</span></span>  
  
-   <span data-ttu-id="0f521-107">Assenza di problemi di qualità dei dati prima che vengano inseriti nel data warehouse</span><span class="sxs-lookup"><span data-stu-id="0f521-107">Prevent data quality problems before they are introduced into the data warehouse.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0f521-108">L'attività Profiling dati funziona solo con i dati archiviati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f521-108">The Data Profiling task works only with data that is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0f521-109">L'attività non può essere utilizzata con origini dati di terze parti o basate su file.</span><span class="sxs-lookup"><span data-stu-id="0f521-109">It does not work with third-party or file-based data sources.</span></span>  
  
## <a name="data-profiling-overview"></a><span data-ttu-id="0f521-110">Panoramica del profiling dei dati</span><span class="sxs-lookup"><span data-stu-id="0f521-110">Data Profiling Overview</span></span>  
 <span data-ttu-id="0f521-111">La qualità dei dati è importante per ogni azienda.</span><span class="sxs-lookup"><span data-stu-id="0f521-111">Data quality is important to every business.</span></span> <span data-ttu-id="0f521-112">La compilazione da parte delle organizzazione di sistemi analitici e di Business Intelligence da integrare nei sistemi transazionali in uso fa sì che l'affidabilità degli indicatori di prestazioni chiave e delle stime basate sul modello di data mining dipenda completamente dalla validità dei dati su cui tali elementi si basano.</span><span class="sxs-lookup"><span data-stu-id="0f521-112">As enterprises build analytical and business intelligence systems on top of their transactional systems, the reliability of key performance indicators and of data mining predictions depends completely on the validity of the data on which they are based.</span></span> <span data-ttu-id="0f521-113">Benché l'importanza di dati validi per il processo decisionale delle aziende stia aumentando, aumenta anche la sfida posta dalla necessità di garantire la validità di tali dati.</span><span class="sxs-lookup"><span data-stu-id="0f521-113">But although the importance of valid data for business decision-making is increasing, the challenge of making sure of this data's validity is also increasing.</span></span> <span data-ttu-id="0f521-114">I dati affluiscono costantemente a un'organizzazione da origini e sistemi diversi e da un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="0f521-114">Data is streaming into the enterprise constantly from diverse systems and sources, and a large numbers of users.</span></span>  
  
 <span data-ttu-id="0f521-115">Le metriche della qualità dei dati possono essere difficili da definire in quanto specifici per il dominio o l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f521-115">Metrics for data quality can be difficult to define because they are specific to the domain or the application.</span></span> <span data-ttu-id="0f521-116">Un approccio comune alla definizione della qualità dei dati consiste nel profiling dei dati.</span><span class="sxs-lookup"><span data-stu-id="0f521-116">One common approach to defining data quality is data profiling.</span></span>  
  
 <span data-ttu-id="0f521-117">Un profilo dati è una raccolta di statistiche aggregate sui dati che possono includere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f521-117">A data profile is a collection of aggregate statistics about data that might include the following:</span></span>  
  
-   <span data-ttu-id="0f521-118">Numero di righe della tabella Customer.</span><span class="sxs-lookup"><span data-stu-id="0f521-118">The number of rows in the Customer table.</span></span>  
  
-   <span data-ttu-id="0f521-119">Numero di valori distinct nella colonna State.</span><span class="sxs-lookup"><span data-stu-id="0f521-119">The number of distinct values in the State column.</span></span>  
  
-   <span data-ttu-id="0f521-120">Numero di valori Null o mancanti nella colonna Zip.</span><span class="sxs-lookup"><span data-stu-id="0f521-120">The number of null or missing values in the Zip column.</span></span>  
  
-   <span data-ttu-id="0f521-121">Distribuzione di valori nella colonna City.</span><span class="sxs-lookup"><span data-stu-id="0f521-121">The distribution of values in the City column.</span></span>  
  
-   <span data-ttu-id="0f521-122">Livello di attendibilità della dipendenza funzionale della colonna State nella colonna Zip, ovvero lo stato deve essere sempre lo stesso per un determinato valore Zip.</span><span class="sxs-lookup"><span data-stu-id="0f521-122">The strength of the functional dependency of the State column on the Zip column-that is, the state should always be the same for a given zip value.</span></span>  
  
 <span data-ttu-id="0f521-123">Le statistiche fornite dal profilo dati consentono di ottenere le informazioni necessarie per ridurre al minimo in modo efficace i possibili problemi di qualità correlati all'utilizzo di dati di origine.</span><span class="sxs-lookup"><span data-stu-id="0f521-123">The statistics that a data profile provides gives you the information that you need in order to effectively minimize the quality issues that might occur from using the source data.</span></span>  
  
## <a name="integration-services-and-data-profiling"></a><span data-ttu-id="0f521-124">Integration Services e profiling dati</span><span class="sxs-lookup"><span data-stu-id="0f521-124">Integration Services and Data Profiling</span></span>  
 <span data-ttu-id="0f521-125">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]il processo di profiling dei dati è costituito dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f521-125">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the data profiling process consist of the following steps:</span></span>  
  
 <span data-ttu-id="0f521-126">**Passaggio 1: Configurazione dell'attività Profiling dati**</span><span class="sxs-lookup"><span data-stu-id="0f521-126">**Step 1: Setting up the Data Profiling Task**</span></span>  
 <span data-ttu-id="0f521-127">L'attività Profiling dati è un'attività che consente di configurare i profili che si desidera calcolare.</span><span class="sxs-lookup"><span data-stu-id="0f521-127">The Data Profiling task is a task that you use to configure the profiles that you want to compute.</span></span> <span data-ttu-id="0f521-128">Viene quindi eseguito il pacchetto contenente l'attività Profiling dati per calcolare i profili.</span><span class="sxs-lookup"><span data-stu-id="0f521-128">You then run the package that contains the Data Profiling task to compute the profiles.</span></span> <span data-ttu-id="0f521-129">L'attività salva l'output del profilo in formato XML in un file o una variabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0f521-129">The task saves the profile output in XML format to a file or a package variable.</span></span>  
  
 <span data-ttu-id="0f521-130">**Per altre informazioni:** [Impostazione dell'attività Profiling dati](data-profiling-task.md)</span><span class="sxs-lookup"><span data-stu-id="0f521-130">**For more information:** [Setup of the Data Profiling Task](data-profiling-task.md)</span></span>  
  
 <span data-ttu-id="0f521-131">**Passaggio 2: Controllo dei profili calcolati dall'attività Profiling dati**</span><span class="sxs-lookup"><span data-stu-id="0f521-131">**Step 2: Reviewing the Profiles that the Data Profiling Task Computes**</span></span>  
 <span data-ttu-id="0f521-132">Per visualizzare i profili dati calcolati dall'attività Profiling dati, è necessario inviare l'output a un file e quindi utilizzare il visualizzatore del profilo dati.</span><span class="sxs-lookup"><span data-stu-id="0f521-132">To view the data profiles that the Data Profiling task computes, you send the output to a file, and then you use the Data Profile Viewer.</span></span> <span data-ttu-id="0f521-133">Questo visualizzatore è un'utilità autonoma che consente di visualizzare l'output del profilo in forma di riepilogo e in formato dettagliato con funzionalità di drill-down facoltative.</span><span class="sxs-lookup"><span data-stu-id="0f521-133">This viewer is a stand-alone utility that displays the profile output in both summary and detail format with optional drilldown capability.</span></span>  
  
 <span data-ttu-id="0f521-134">**Per altre informazioni:** [Visualizzatore profilo dati](data-profile-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="0f521-134">**For more information:** [Data Profile Viewer](data-profile-viewer.md)</span></span>  
  
### <a name="addition-of-conditional-logic-to-the-data-profiling-workflow"></a><span data-ttu-id="0f521-135">Aggiunta di logica condizionale al flusso di lavoro del profiling dei dati</span><span class="sxs-lookup"><span data-stu-id="0f521-135">Addition of Conditional Logic to the Data Profiling Workflow</span></span>  
 <span data-ttu-id="0f521-136">L'attività Profiling dati non dispone di caratteristiche incorporate che consentono di utilizzare la logica condizionale per connettere questa attività alle attività a valle basate sull'output del profilo.</span><span class="sxs-lookup"><span data-stu-id="0f521-136">The Data Profiling task does not have built-in features that allow you to use conditional logic to connect this task to downstream tasks based on the profile output.</span></span> <span data-ttu-id="0f521-137">È possibile, tuttavia, aggiungere tale logica in modo semplice, con operazioni di programmazione ridotte, in un'attività Script.</span><span class="sxs-lookup"><span data-stu-id="0f521-137">However, you can easily add this logic, with a small amount of programming, in a Script task.</span></span> <span data-ttu-id="0f521-138">L'attività Script, ad esempio, può eseguire una query XPath sul file di output dell'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="0f521-138">For example, the Script task could perform an XPath query against the output file of the Data Profiling task.</span></span> <span data-ttu-id="0f521-139">La query può determinare se la percentuale di valori Null in una colonna specifica supera una determinata soglia.</span><span class="sxs-lookup"><span data-stu-id="0f521-139">The query could determine whether the percentage of null values in a particular column exceeds a certain threshold.</span></span> <span data-ttu-id="0f521-140">Se la percentuale supera la soglia, è possibile interrompere il pacchetto e risolvere il problema nei dati di origine prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0f521-140">If the percentage exceeds the threshold, you could interrupt the package and resolve the problem in the source data before continuing.</span></span> <span data-ttu-id="0f521-141">Per altre informazioni, vedere [Incorporamento di un'attività Profiling dati nel flusso di lavoro del pacchetto](incorporate-a-data-profiling-task-in-package-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="0f521-141">For more information, see [Incorporate a Data Profiling Task in Package Workflow](incorporate-a-data-profiling-task-in-package-workflow.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="0f521-142">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="0f521-142">Related Content</span></span>  
 [<span data-ttu-id="0f521-143">Pagina relativa allo schema del profiler dati</span><span class="sxs-lookup"><span data-stu-id="0f521-143">Data Profiler Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=251524)  
  
  
