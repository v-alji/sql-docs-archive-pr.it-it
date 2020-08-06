---
title: 'Lezione 2: aggiunta di cicli | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 01f2ed61-1e5a-4ec6-b6a6-2bd070c64077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65efb84b4e50b470470e396bbe5681ce4b5dfac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626143"
---
# <a name="lesson-2-adding-looping"></a><span data-ttu-id="5b797-102">Lezione 2: Aggiunta di cicli</span><span class="sxs-lookup"><span data-stu-id="5b797-102">Lesson 2: Adding Looping</span></span>
  <span data-ttu-id="5b797-103">Nella [lezione 1: creazione del progetto e del pacchetto di base](lesson-1-create-a-project-and-basic-package-with-ssis.md)è stato creato un pacchetto che estrae i dati da un'unica origine file flat, trasforma i dati usando le trasformazioni Ricerca e infine carica i dati nella tabella dei fatti **FactCurrency** del database di esempio **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="5b797-103">In [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md), you created a package that extracted data from a single flat file source, transformed the data using Lookup transformations, and finally loaded the data into the **FactCurrency** fact table of the **AdventureWorksDW2012** sample database.</span></span>  
  
 <span data-ttu-id="5b797-104">Tuttavia, per un processo di estrazione, trasformazione e caricamento (ETL, Extract, Transform and Loading) raramente viene usato un unico file flat.</span><span class="sxs-lookup"><span data-stu-id="5b797-104">However, it is rare for an extract, transform, and load (ETL) process to use a single flat file.</span></span> <span data-ttu-id="5b797-105">In genere durante un processo ETL i dati vengono estratti da più origini file flat.</span><span class="sxs-lookup"><span data-stu-id="5b797-105">A typical ETL process would extract data from multiple flat file sources.</span></span> <span data-ttu-id="5b797-106">L'estrazione dei dati da più origini richiede un flusso di controllo iterativo.</span><span class="sxs-lookup"><span data-stu-id="5b797-106">Extracting data from multiple sources requires an iterative control flow.</span></span> <span data-ttu-id="5b797-107">Una delle funzionalità più attese di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] è la possibilità di aggiungere facilmente iterazioni o cicli ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5b797-107">One of the most anticipated features of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is the ability to easily add iteration or looping to packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="5b797-108">offre due tipi di contenitori per eseguire i cicli di pacchetti: il contenitore Ciclo Foreach e il contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="5b797-108">provides two types of containers for looping through packages: the Foreach Loop container and the For Loop container.</span></span> <span data-ttu-id="5b797-109">Nel contenitore Ciclo Foreach viene usato un enumeratore per eseguire il ciclo mentre nel contenitore Ciclo For viene usata in genere un'espressione di variabili.</span><span class="sxs-lookup"><span data-stu-id="5b797-109">The Foreach Loop container uses an enumerator to perform the looping, whereas the For Loop container typically uses a variable expression.</span></span> <span data-ttu-id="5b797-110">Questa lezione prevede l'uso del contenitore Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="5b797-110">This lesson uses the Foreach Loop container.</span></span>  
  
 <span data-ttu-id="5b797-111">Il contenitore Ciclo Foreach consente a un pacchetto di ripetere il flusso di controllo per ogni membro di un enumeratore specificato.</span><span class="sxs-lookup"><span data-stu-id="5b797-111">The Foreach Loop container enables a package to repeat the control flow for each member of a specified enumerator.</span></span> <span data-ttu-id="5b797-112">Il contenitore Ciclo Foreach consente di enumerare:</span><span class="sxs-lookup"><span data-stu-id="5b797-112">With the Foreach Loop container, you can enumerate:</span></span>  
  
-   <span data-ttu-id="5b797-113">Righe di un recordset ADO</span><span class="sxs-lookup"><span data-stu-id="5b797-113">ADO recordset rows</span></span>  
  
-   <span data-ttu-id="5b797-114">Informazioni sullo schema ADO .NET</span><span class="sxs-lookup"><span data-stu-id="5b797-114">ADO .Net schema information</span></span>  
  
-   <span data-ttu-id="5b797-115">Strutture di file e directory</span><span class="sxs-lookup"><span data-stu-id="5b797-115">File and directory structures</span></span>  
  
-   <span data-ttu-id="5b797-116">Variabili utente, di sistema e del pacchetto</span><span class="sxs-lookup"><span data-stu-id="5b797-116">System, package and user variables</span></span>  
  
-   <span data-ttu-id="5b797-117">Oggetti enumerabili contenuti in una variabile</span><span class="sxs-lookup"><span data-stu-id="5b797-117">Enumerable objects contained in a variable</span></span>  
  
-   <span data-ttu-id="5b797-118">Elementi di una raccolta</span><span class="sxs-lookup"><span data-stu-id="5b797-118">Items in a collection</span></span>  
  
-   <span data-ttu-id="5b797-119">Nodi in un'espressione XPATH</span><span class="sxs-lookup"><span data-stu-id="5b797-119">Nodes in an XML Path Language (XPath) expression</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="5b797-120">Oggetti SMO (Management Objects)</span><span class="sxs-lookup"><span data-stu-id="5b797-120">Management Objects (SMO)</span></span>  
  
 <span data-ttu-id="5b797-121">In questa lezione verranno illustrate le procedure per modificare il pacchetto ETL semplice creato nella lezione 1 usando il contenitore Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="5b797-121">In this lesson, you will modify the simple ETL package created in Lesson 1 to take advantage of the Foreach Loop container.</span></span> <span data-ttu-id="5b797-122">Verranno inoltre impostate le variabili del pacchetto definite dall'utente in modo che nel pacchetto creato nell'esercitazione sia possibile scorrere tutti i file flat contenuti nella cartella.</span><span class="sxs-lookup"><span data-stu-id="5b797-122">You will also set user-defined package variables to enable the tutorial package to iterate through all the flat files in the folder.</span></span> <span data-ttu-id="5b797-123">Se non è stata completata la lezione precedente, è possibile copiare il pacchetto della lezione 1 completato incluso nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="5b797-123">If you have not completed the previous lesson, you can also copy the completed Lesson 1 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="5b797-124">In questa lezione verrà modificato solo il flusso di controllo, non il flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="5b797-124">In this lesson, you will not modify the data flow, only the control flow.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5b797-125">Per eseguire questa esercitazione, è necessario il database di esempio **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="5b797-125">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="5b797-126">Per altre informazioni sull'installazione e sulla distribuzione di **AdventureWorksDW2012**, vedere la pagina relativa agli [esempi del prodotto Reporting Services su CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="5b797-126">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="5b797-127">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="5b797-127">Lesson Tasks</span></span>  
 <span data-ttu-id="5b797-128">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b797-128">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="5b797-129">Passaggio 1: Copia del pacchetto della lezione 1</span><span class="sxs-lookup"><span data-stu-id="5b797-129">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
-   [<span data-ttu-id="5b797-130">Passaggio 2: Aggiunta e configurazione del contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="5b797-130">Step 2: Adding and Configuring the Foreach Loop Container</span></span>](lesson-2-2-adding-and-configuring-the-foreach-loop-container.md)  
  
-   [<span data-ttu-id="5b797-131">Passaggio 3: Modifica della gestione connessione file flat</span><span class="sxs-lookup"><span data-stu-id="5b797-131">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="5b797-132">Passaggio 4: Test del pacchetto creato nella lezione 2 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="5b797-132">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="5b797-133">Inizio della lezione</span><span class="sxs-lookup"><span data-stu-id="5b797-133">Start the Lesson</span></span>  
 [<span data-ttu-id="5b797-134">Passaggio 1: Copia del pacchetto della lezione 1</span><span class="sxs-lookup"><span data-stu-id="5b797-134">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="5b797-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b797-135">See Also</span></span>  
 [<span data-ttu-id="5b797-136">Contenitore Ciclo For</span><span class="sxs-lookup"><span data-stu-id="5b797-136">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
