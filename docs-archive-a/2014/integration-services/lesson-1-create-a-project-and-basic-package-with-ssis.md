---
title: 'Lezione 1: creazione del progetto e del pacchetto di base | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 84d0b877-603f-4f8e-bb6b-671558ade5c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a9ddc36ef242cc4e4b146e90dfa9de470e68d83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628827"
---
# <a name="lesson-1-creating-the-project-and-basic-package"></a><span data-ttu-id="7f42e-102">Lezione 1: Creazione del progetto e del pacchetto di base</span><span class="sxs-lookup"><span data-stu-id="7f42e-102">Lesson 1: Creating the Project and Basic Package</span></span>
  <span data-ttu-id="7f42e-103">In questa lezione verrà creato un pacchetto ETL semplice tramite cui vengono estratti i dati da un'unica origine file flat, trasformati i dati usando due componenti di trasformazione Ricerca e scritti i dati in questione nella tabella dei fatti **FactCurrency** di **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="7f42e-103">In this lesson, you will create a simple ETL package that extracts data from a single flat file source, transforms the data using two lookup transformation components, and writes that data to the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span> <span data-ttu-id="7f42e-104">In questa lezione si imparerà a creare nuovi pacchetti, aggiungere e configurare connessioni origine e destinazione dati e usare nuovi componenti flusso di controllo e flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="7f42e-104">As part of this lesson, you will learn how to create new packages, add and configure data source and destination connections, and work with new control flow and data flow components.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7f42e-105">Per eseguire questa esercitazione, è necessario il database di esempio **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="7f42e-105">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="7f42e-106">Per ulteriori informazioni sull'installazione e sulla distribuzione di **AdventureWorksDW2012**, vedere [Microsoft SQL Server Product samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span><span class="sxs-lookup"><span data-stu-id="7f42e-106">For more information on installing and deploying **AdventureWorksDW2012**, see [Microsoft SQL Server Product Samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span></span>  
  
## <a name="understanding-the-package-requirements"></a><span data-ttu-id="7f42e-107">Informazioni sui requisiti del pacchetto</span><span class="sxs-lookup"><span data-stu-id="7f42e-107">Understanding the Package Requirements</span></span>  
 <span data-ttu-id="7f42e-108">Per questa esercitazione è richiesto Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="7f42e-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
  
 <span data-ttu-id="7f42e-109">Per altre informazioni sull'installazione di SQL Server Data Tools, vedere [Scaricare SQL Server Data Tools](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span><span class="sxs-lookup"><span data-stu-id="7f42e-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span></span>  
  
 <span data-ttu-id="7f42e-110">Prima di creare un pacchetto è necessario conoscere bene la formattazione usata nei dati di origine e nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f42e-110">Before creating a package, you need a good understanding of the formatting used in both the source data and the destination.</span></span> <span data-ttu-id="7f42e-111">Dopo avere acquisito familiarità con questi due formati di dati sarà possibile definire le trasformazioni necessarie per eseguire il mapping tra i dati di origine e la destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f42e-111">Once you understand both of these data formats, you will be ready to define the transformations necessary to map the source data to the destination.</span></span>  
  
### <a name="looking-at-the-source"></a><span data-ttu-id="7f42e-112">Esame dell'origine</span><span class="sxs-lookup"><span data-stu-id="7f42e-112">Looking at the Source</span></span>  
 <span data-ttu-id="7f42e-113">In questa esercitazione vengono usati i dati valutari contenuti nel file flat SampleCurrencyData.txt.</span><span class="sxs-lookup"><span data-stu-id="7f42e-113">For this tutorial, the source data is a set of historical currency data contained in the flat file, SampleCurrencyData.txt.</span></span> <span data-ttu-id="7f42e-114">I dati di origine sono contenuti nelle quattro colonne seguenti: il tasso medio della valuta, un codice valuta, un codice data e il tasso di fine giornata.</span><span class="sxs-lookup"><span data-stu-id="7f42e-114">The source data has the following four columns: the average rate of the currency, a currency key, a date key, and the end-of-day rate.</span></span>  
  
 <span data-ttu-id="7f42e-115">Di seguito viene riportato un esempio dei dati di origine contenuti nel file SampleCurrencyData.txt:</span><span class="sxs-lookup"><span data-stu-id="7f42e-115">Here is an example of the source data contained in the SampleCurrencyData.txt file:</span></span>  
  
 `1.00070049USD9/3/05 0:001.001201442`  
  
 `1.00020004USD9/4/05 0:001`  
  
 `1.00020004USD9/5/05 0:001.001201442`  
  
 `1.00020004USD9/6/05 0:001`  
  
 `1.00020004USD9/7/05 0:001.00070049`  
  
 `1.00070049USD9/8/05 0:000.99980004`  
  
 `1.00070049USD9/9/05 0:001.001502253`  
  
 `1.00070049USD9/10/05 0:000.99990001`  
  
 `1.00020004USD9/11/05 0:001.001101211`  
  
 `1.00020004USD9/12/05 0:000.99970009`  
  
 <span data-ttu-id="7f42e-116">Quando si usano dati di origine di file flat, è importante capire in che modo Gestione connessione file flat interpreta i relativi dati.</span><span class="sxs-lookup"><span data-stu-id="7f42e-116">When working with flat file source data, it is important to understand how the Flat File connection manager interprets the flat file data.</span></span> <span data-ttu-id="7f42e-117">Se l'origine del file flat è Unicode, tutte le colonne vengono definite nella gestione connessione file flat come [DT_WSTR] con una larghezza predefinita di 50.</span><span class="sxs-lookup"><span data-stu-id="7f42e-117">If the flat file source is Unicode, the Flat File connection manager defines all columns as [DT_WSTR] with a default column width of 50.</span></span> <span data-ttu-id="7f42e-118">Se l'origine del file flat è con codifica ANSI, le colonne sono definite come [DT_STR] con una larghezza di 50.</span><span class="sxs-lookup"><span data-stu-id="7f42e-118">If the flat file source is ANSI-encoded, the columns are defined as [DT_STR] with a column width of 50.</span></span> <span data-ttu-id="7f42e-119">Le impostazioni predefinite sono liberamente modificabili per adattare al meglio i tipi di colonna ai dati.</span><span class="sxs-lookup"><span data-stu-id="7f42e-119">You will probably have to change these defaults to make the string column types more appropriate for your data.</span></span> <span data-ttu-id="7f42e-120">Per farlo, è necessario esaminare il tipi di dati della destinazione di scrittura dei dati e scegliere il tipo corretto all'interno di Gestione connessione file flat.</span><span class="sxs-lookup"><span data-stu-id="7f42e-120">To do this, you will need to look at the data type of the destination where the data will be written to and then choose the correct type within the Flat File connection manager.</span></span>  
  
### <a name="looking-at-the-destination"></a><span data-ttu-id="7f42e-121">Esame della destinazione</span><span class="sxs-lookup"><span data-stu-id="7f42e-121">Looking at the Destination</span></span>  
 <span data-ttu-id="7f42e-122">La destinazione finale dei dati di origine è la tabella dei fatti **FactCurrency** di **AdventureWorksDW**.</span><span class="sxs-lookup"><span data-stu-id="7f42e-122">The ultimate destination for the source data is the **FactCurrency** fact table in **AdventureWorksDW**.</span></span> <span data-ttu-id="7f42e-123">La tabella dei fatti **FactCurrency** presenta quattro colonne e ha relazioni con due tabelle delle dimensioni, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7f42e-123">The **FactCurrency** fact table has four columns, and has relationships to two dimension tables, as shown in the following table.</span></span>  
  
|<span data-ttu-id="7f42e-124">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7f42e-124">Column Name</span></span>|<span data-ttu-id="7f42e-125">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7f42e-125">Data Type</span></span>|<span data-ttu-id="7f42e-126">Tabella di ricerca</span><span class="sxs-lookup"><span data-stu-id="7f42e-126">Lookup Table</span></span>|<span data-ttu-id="7f42e-127">colonna di ricerca</span><span class="sxs-lookup"><span data-stu-id="7f42e-127">Lookup Column</span></span>|  
|-----------------|---------------|------------------|-------------------|  
|<span data-ttu-id="7f42e-128">AverageRate</span><span class="sxs-lookup"><span data-stu-id="7f42e-128">AverageRate</span></span>|<span data-ttu-id="7f42e-129">float</span><span class="sxs-lookup"><span data-stu-id="7f42e-129">float</span></span>|<span data-ttu-id="7f42e-130">nessuno</span><span class="sxs-lookup"><span data-stu-id="7f42e-130">None</span></span>|<span data-ttu-id="7f42e-131">nessuno</span><span class="sxs-lookup"><span data-stu-id="7f42e-131">None</span></span>|  
|<span data-ttu-id="7f42e-132">CurrencyKey</span><span class="sxs-lookup"><span data-stu-id="7f42e-132">CurrencyKey</span></span>|<span data-ttu-id="7f42e-133">int (FK)</span><span class="sxs-lookup"><span data-stu-id="7f42e-133">int (FK)</span></span>|<span data-ttu-id="7f42e-134">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="7f42e-134">DimCurrency</span></span>|<span data-ttu-id="7f42e-135">CurrencyKey (PK)</span><span class="sxs-lookup"><span data-stu-id="7f42e-135">CurrencyKey (PK)</span></span>|  
|<span data-ttu-id="7f42e-136">DateKey</span><span class="sxs-lookup"><span data-stu-id="7f42e-136">DateKey</span></span>|<span data-ttu-id="7f42e-137">int (FK)</span><span class="sxs-lookup"><span data-stu-id="7f42e-137">Int (FK)</span></span>|<span data-ttu-id="7f42e-138">DimDate</span><span class="sxs-lookup"><span data-stu-id="7f42e-138">DimDate</span></span>|<span data-ttu-id="7f42e-139">DateKey (PK)</span><span class="sxs-lookup"><span data-stu-id="7f42e-139">DateKey (PK)</span></span>|  
|<span data-ttu-id="7f42e-140">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="7f42e-140">EndOfDayRate</span></span>|<span data-ttu-id="7f42e-141">float</span><span class="sxs-lookup"><span data-stu-id="7f42e-141">float</span></span>|<span data-ttu-id="7f42e-142">nessuno</span><span class="sxs-lookup"><span data-stu-id="7f42e-142">None</span></span>|<span data-ttu-id="7f42e-143">nessuno</span><span class="sxs-lookup"><span data-stu-id="7f42e-143">None</span></span>|  
  
### <a name="mapping-source-data-to-be-compatible-with-the-destination"></a><span data-ttu-id="7f42e-144">Mapping dei dati di origine per la compatibilità con la destinazione</span><span class="sxs-lookup"><span data-stu-id="7f42e-144">Mapping Source Data to be Compatible with the Destination</span></span>  
 <span data-ttu-id="7f42e-145">L'analisi dei formati dei dati di origine e di destinazione indica che per i valori **CurrencyKey** e **DateKey** saranno necessarie le ricerche.</span><span class="sxs-lookup"><span data-stu-id="7f42e-145">Analysis of the source and destination data formats indicates that lookups will be necessary for the **CurrencyKey** and **DateKey** values.</span></span> <span data-ttu-id="7f42e-146">Tramite le trasformazioni mediante le quali verranno svolte queste ricerche si otterranno i valori **CurrencyKey** e **DateKey** usando le chiavi alternative ottenute dalle tabelle delle dimensioni **DimCurrency** e **DimDate** .</span><span class="sxs-lookup"><span data-stu-id="7f42e-146">The transformations that will perform these lookups will obtain the **CurrencyKey** and **DateKey** values by using the alternate keys from **DimCurrency** and **DimDate** dimension tables.</span></span>  
  
|<span data-ttu-id="7f42e-147">Colonna file flat</span><span class="sxs-lookup"><span data-stu-id="7f42e-147">Flat File Column</span></span>|<span data-ttu-id="7f42e-148">Nome tabella</span><span class="sxs-lookup"><span data-stu-id="7f42e-148">Table Name</span></span>|<span data-ttu-id="7f42e-149">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7f42e-149">Column Name</span></span>|<span data-ttu-id="7f42e-150">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7f42e-150">Data Type</span></span>|  
|----------------------|----------------|-----------------|---------------|  
|<span data-ttu-id="7f42e-151">0</span><span class="sxs-lookup"><span data-stu-id="7f42e-151">0</span></span>|<span data-ttu-id="7f42e-152">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="7f42e-152">FactCurrency</span></span>|<span data-ttu-id="7f42e-153">AverageRate</span><span class="sxs-lookup"><span data-stu-id="7f42e-153">AverageRate</span></span>|<span data-ttu-id="7f42e-154">float</span><span class="sxs-lookup"><span data-stu-id="7f42e-154">float</span></span>|  
|<span data-ttu-id="7f42e-155">1</span><span class="sxs-lookup"><span data-stu-id="7f42e-155">1</span></span>|<span data-ttu-id="7f42e-156">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="7f42e-156">DimCurrency</span></span>|<span data-ttu-id="7f42e-157">CurrencyAlternateKey</span><span class="sxs-lookup"><span data-stu-id="7f42e-157">CurrencyAlternateKey</span></span>|<span data-ttu-id="7f42e-158">nchar (3)</span><span class="sxs-lookup"><span data-stu-id="7f42e-158">nchar (3)</span></span>|  
|<span data-ttu-id="7f42e-159">2</span><span class="sxs-lookup"><span data-stu-id="7f42e-159">2</span></span>|<span data-ttu-id="7f42e-160">DimDate</span><span class="sxs-lookup"><span data-stu-id="7f42e-160">DimDate</span></span>|<span data-ttu-id="7f42e-161">FullDateAlternateKey</span><span class="sxs-lookup"><span data-stu-id="7f42e-161">FullDateAlternateKey</span></span>|<span data-ttu-id="7f42e-162">date</span><span class="sxs-lookup"><span data-stu-id="7f42e-162">date</span></span>|  
|<span data-ttu-id="7f42e-163">3</span><span class="sxs-lookup"><span data-stu-id="7f42e-163">3</span></span>|<span data-ttu-id="7f42e-164">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="7f42e-164">FactCurrency</span></span>|<span data-ttu-id="7f42e-165">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="7f42e-165">EndOfDayRate</span></span>|<span data-ttu-id="7f42e-166">float</span><span class="sxs-lookup"><span data-stu-id="7f42e-166">float</span></span>|  
  
## <a name="lesson-tasks"></a><span data-ttu-id="7f42e-167">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="7f42e-167">Lesson Tasks</span></span>  
 <span data-ttu-id="7f42e-168">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f42e-168">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="7f42e-169">Passaggio 1: Creazione di un nuovo progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="7f42e-169">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="7f42e-170">Passaggio 2: Aggiunta e configurazione di una gestione connessione file flat</span><span class="sxs-lookup"><span data-stu-id="7f42e-170">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="7f42e-171">Passaggio 3: Aggiunta e configurazione di una gestione connessione OLE DB</span><span class="sxs-lookup"><span data-stu-id="7f42e-171">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>](lesson-1-3-adding-and-configuring-an-ole-db-connection-manager.md)  
  
-   [<span data-ttu-id="7f42e-172">Passaggio 4: Aggiunta di un'attività Flusso di dati al pacchetto</span><span class="sxs-lookup"><span data-stu-id="7f42e-172">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
-   [<span data-ttu-id="7f42e-173">Passaggio 5: Aggiunta e configurazione dell'origine file flat</span><span class="sxs-lookup"><span data-stu-id="7f42e-173">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
-   [<span data-ttu-id="7f42e-174">Passaggio 6: Aggiunta e configurazione delle trasformazioni Ricerca</span><span class="sxs-lookup"><span data-stu-id="7f42e-174">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
-   [<span data-ttu-id="7f42e-175">Passaggio 7: Aggiunta e configurazione della destinazione OLE DB</span><span class="sxs-lookup"><span data-stu-id="7f42e-175">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
-   [<span data-ttu-id="7f42e-176">Passaggio 8: Semplificazione del pacchetto della lezione 1</span><span class="sxs-lookup"><span data-stu-id="7f42e-176">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
-   [<span data-ttu-id="7f42e-177">Passaggio 9: Test del pacchetto creato nella lezione 1 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="7f42e-177">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="7f42e-178">Inizio della lezione</span><span class="sxs-lookup"><span data-stu-id="7f42e-178">Start the Lesson</span></span>  
 [<span data-ttu-id="7f42e-179">Passaggio 1: Creazione di un nuovo progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="7f42e-179">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
  
