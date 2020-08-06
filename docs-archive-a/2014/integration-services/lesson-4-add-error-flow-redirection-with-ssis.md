---
title: 'Lezione 4: aggiunta del reindirizzamento del flusso degli errori | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c8dbda2-75e3-4278-9b4e-dcd220c92522
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5b1d1ff9abf59a6288d1b693fce5a6fb707a129b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724803"
---
# <a name="lesson-4-adding-error-flow-redirection"></a><span data-ttu-id="dcd18-102">Lezione 4: Aggiunta del reindirizzamento del flusso degli errori</span><span class="sxs-lookup"><span data-stu-id="dcd18-102">Lesson 4: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="dcd18-103">Per gestire gli errori che possono verificarsi durante il processo di trasformazione, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] consente di decidere in base a ogni componente e a ogni colonna come gestire i dati che non possono essere trasformati.</span><span class="sxs-lookup"><span data-stu-id="dcd18-103">To handle errors that may occur in the transformation process, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gives you the ability to decide on a per component and per column basis how to handle data that cannot be transformed.</span></span> <span data-ttu-id="dcd18-104">È possibile scegliere di ignorare un errore in alcune colonne, reindirizzare l'intera riga con esito negativo o interrompere l'esecuzione del componente.</span><span class="sxs-lookup"><span data-stu-id="dcd18-104">You can choose to ignore a failure in certain columns, redirect the entire failed row, or just fail the component.</span></span> <span data-ttu-id="dcd18-105">Per impostazione predefinita, tutti i componenti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sono configurati in modo da interrompersi quando si verificano errori.</span><span class="sxs-lookup"><span data-stu-id="dcd18-105">By default, all components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are configured to fail when errors occur.</span></span> <span data-ttu-id="dcd18-106">L'arresto di un componente determina l'arresto del pacchetto e di conseguenza di tutte le elaborazioni successive.</span><span class="sxs-lookup"><span data-stu-id="dcd18-106">Failing a component, in turn, causes the package to fail and all subsequent processing to stop.</span></span>  
  
 <span data-ttu-id="dcd18-107">Anziché arrestare l'esecuzione del pacchetto a causa degli errori, è consigliabile configurare e gestire potenziali errori di elaborazione nel momento stesso in cui si verificano durante la trasformazione.</span><span class="sxs-lookup"><span data-stu-id="dcd18-107">Instead of letting failures stop package execution, it is good practice to configure and handle potential processing errors as they occur within the transformation.</span></span> <span data-ttu-id="dcd18-108">Sebbene sia possibile decidere di ignorare gli errori in modo da garantire l'esecuzione dei pacchetti, è talvolta opportuno reindirizzare la riga con esito negativo a un altro percorso di elaborazione in cui i dati e gli errori possono essere mantenuti e quindi essere esaminati e rielaborati in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="dcd18-108">While you might choose to ignore failures to ensure your package runs successfully, it is often better to redirect the failed row to another processing path where the data and the error can be persisted, examined and reprocessed at a later time.</span></span>  
  
 <span data-ttu-id="dcd18-109">In questa lezione verranno illustrate le procedure per la creazione di una copia del pacchetto sviluppato in [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="dcd18-109">In this lesson, you will create a copy of the package that you developed in [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span></span> <span data-ttu-id="dcd18-110">L'utilizzo di questo nuovo pacchetto consentirà di creare una versione danneggiata di uno dei file di dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="dcd18-110">Working with this new package, you will create a corrupted version of one of the sample data files.</span></span> <span data-ttu-id="dcd18-111">Durante l'esecuzione del pacchetto, il file danneggiato forzerà la generazione di un errore di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="dcd18-111">The corrupted file will force a processing error to occur when you run the package.</span></span>  
  
 <span data-ttu-id="dcd18-112">Per gestire i dati dell'errore verrà aggiunta e configurata una destinazione file flat che consente di scrivere in un file tutte le righe che non riescono a individuare un valore di ricerca nella trasformazione Lookup Currency Key.</span><span class="sxs-lookup"><span data-stu-id="dcd18-112">To handle the error data, you will add and configure a Flat File destination that will write any rows that fail to locate a lookup value in the Lookup Currency Key transformation to a file.</span></span>  
  
 <span data-ttu-id="dcd18-113">Prima che i dati dell'errore vengano scritti nel file, si includerà un componente script che usa uno script per ottenere le descrizioni degli errori.</span><span class="sxs-lookup"><span data-stu-id="dcd18-113">Before the error data is written to the file, you will include a Script component that uses script to get error descriptions.</span></span> <span data-ttu-id="dcd18-114">La trasformazione Lookup Currency Key verrà quindi riconfigurata in modo che i dati che non possono essere elaborati vengano reindirizzati alla trasformazione Script.</span><span class="sxs-lookup"><span data-stu-id="dcd18-114">You will then reconfigure the Lookup Currency Key transformation to redirect any data that could not be processed to the Script transformation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dcd18-115">Per eseguire questa esercitazione, è necessario il database di esempio **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="dcd18-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="dcd18-116">Per altre informazioni sull'installazione e sulla distribuzione di **AdventureWorksDW2012**, vedere [Esempi di Reporting Services su CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span><span class="sxs-lookup"><span data-stu-id="dcd18-116">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples Project on CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span></span>  
  
## <a name="tasks-in-lesson"></a><span data-ttu-id="dcd18-117">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="dcd18-117">Tasks in Lesson</span></span>  
 <span data-ttu-id="dcd18-118">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="dcd18-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="dcd18-119">Passaggio 1: Copia del pacchetto della lezione 3</span><span class="sxs-lookup"><span data-stu-id="dcd18-119">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
-   [<span data-ttu-id="dcd18-120">Passaggio 2: Creazione di un file danneggiato</span><span class="sxs-lookup"><span data-stu-id="dcd18-120">Step 2: Creating a Corrupted File</span></span>](lesson-4-2-creating-a-corrupted-file.md)  
  
-   [<span data-ttu-id="dcd18-121">Passaggio 3: Aggiunta del reindirizzamento del flusso degli errori</span><span class="sxs-lookup"><span data-stu-id="dcd18-121">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
-   [<span data-ttu-id="dcd18-122">Passaggio 4: Aggiunta di una destinazione file flat</span><span class="sxs-lookup"><span data-stu-id="dcd18-122">Step 4: Adding a Flat File Destination</span></span>](lesson-4-4-adding-a-flat-file-destination.md)  
  
-   [<span data-ttu-id="dcd18-123">Passaggio 5: Test del pacchetto creato nella lezione 4 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="dcd18-123">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="dcd18-124">Inizio della lezione</span><span class="sxs-lookup"><span data-stu-id="dcd18-124">Start the Lesson</span></span>  
 [<span data-ttu-id="dcd18-125">Passaggio 1: Copia del pacchetto della lezione 3</span><span class="sxs-lookup"><span data-stu-id="dcd18-125">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
  
