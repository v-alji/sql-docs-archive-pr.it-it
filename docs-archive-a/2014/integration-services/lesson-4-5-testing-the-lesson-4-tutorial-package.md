---
title: "Passaggio 5: Test del pacchetto creato nella lezione 4 dell'esercitazione | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5f18df92-0248-4858-836b-c8b02f0e0439
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a897f99bf68805e4e66c3b6bbe818b312077fb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720232"
---
# <a name="step-5-testing-the-lesson-4-tutorial-package"></a><span data-ttu-id="935d9-102">Passaggio 5: Test del pacchetto creato nella lezione 4 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="935d9-102">Step 5: Testing the Lesson 4 Tutorial Package</span></span>
  <span data-ttu-id="935d9-103">In fase di esecuzione, il file danneggiato Currency_BAD.txt non sarà in grado di generare una corrispondenza all'interno della trasformazione Lookup Currency Key.</span><span class="sxs-lookup"><span data-stu-id="935d9-103">At run time, the corrupted file, Currency_BAD.txt, will fail to generate a match within the Currency Key Lookup transformation.</span></span> <span data-ttu-id="935d9-104">Dato che l'output degli errori di Lookup Currency Key è stato configurato per il reindirizzamento delle righe con esito negativo alla nuova destinazione Failed Rows, il componente non presenta errori e il pacchetto viene eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="935d9-104">Because the error output of Currency Key Lookup has now been configured to redirect failed rows to the new Failed Rows destination, the component does not fail, and the package runs successfully.</span></span> <span data-ttu-id="935d9-105">Tutte le righe di errore sono riportate nel file ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="935d9-105">All failed error rows are written to ErrorOutput.txt.</span></span>  
  
 <span data-ttu-id="935d9-106">In questa attività verrà eseguito il test della configurazione dell'output degli errori modificata tramite l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="935d9-106">In this task, you will test the revised error output configuration by running the package.</span></span> <span data-ttu-id="935d9-107">Al termine dell'esecuzione corretta del pacchetto sarà possibile visualizzare il contenuto del file ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="935d9-107">Upon successful package execution, you will then view the contents of the ErrorOutput.txt file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="935d9-108">Per evitare l'accumulo di righe di errore nel file ErrorOutput.txt, è consigliabile eliminare manualmente il contenuto del file dopo l'esecuzione di ogni pacchetto.</span><span class="sxs-lookup"><span data-stu-id="935d9-108">If you do not want to accumulate error rows in the ErrorOutput.txt file, you should manually delete the file content between package runs.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="935d9-109">Verifica del layout del pacchetto</span><span class="sxs-lookup"><span data-stu-id="935d9-109">Checking the Package layout</span></span>  
 <span data-ttu-id="935d9-110">Prima di testare il pacchetto è consigliabile verificare che il flusso di controllo e il flusso di dati nel pacchetto della lezione 4 contengano gli oggetti visualizzati nelle figure seguenti.</span><span class="sxs-lookup"><span data-stu-id="935d9-110">Before you test the package you should verify that the control flow and the data flow in the Lesson 4 package contain the objects shown in the following diagrams.</span></span> <span data-ttu-id="935d9-111">Il flusso di controllo deve essere identico a quello nelle lezioni 2 - 4.</span><span class="sxs-lookup"><span data-stu-id="935d9-111">The control flow should be identical to the control flow in lessons 2 - 4.</span></span>  
  
 <span data-ttu-id="935d9-112">**Flusso di controllo**</span><span class="sxs-lookup"><span data-stu-id="935d9-112">**Control Flow**</span></span>  
  
 <span data-ttu-id="935d9-113">![Flusso di controllo nel pacchetto](../../2014/tutorials/media/task4lesson2control.gif "Flusso di controllo nel pacchetto")</span><span class="sxs-lookup"><span data-stu-id="935d9-113">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="935d9-114">**Flusso di dati**</span><span class="sxs-lookup"><span data-stu-id="935d9-114">**Data Flow**</span></span>  
  
 <span data-ttu-id="935d9-115">![Flusso di dati nel pacchetto](../../2014/tutorials/media/task5lesson5data.gif "Flusso di dati nel pacchetto")</span><span class="sxs-lookup"><span data-stu-id="935d9-115">![Data flow in package](../../2014/tutorials/media/task5lesson5data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-4-tutorial-package"></a><span data-ttu-id="935d9-116">Per eseguire il pacchetto creato nella lezione 4 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="935d9-116">To run the Lesson 4 tutorial package</span></span>  
  
1.  <span data-ttu-id="935d9-117">Dal menu **Debug** scegliere **Avvia debug**.</span><span class="sxs-lookup"><span data-stu-id="935d9-117">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="935d9-118">Al termine dell'esecuzione del pacchetto, scegliere **Arresta debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="935d9-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-verify-the-contents-of-the-erroroutputtxt-file"></a><span data-ttu-id="935d9-119">Per verificare il contenuto del file ErrorOutput.txt</span><span class="sxs-lookup"><span data-stu-id="935d9-119">To verify the contents of the ErrorOutput.txt file</span></span>  
  
-   <span data-ttu-id="935d9-120">Aprire il file ErrorOutput.txt in Blocco note o qualsiasi altro editor di testo.</span><span class="sxs-lookup"><span data-stu-id="935d9-120">In Notepad or any other text editor, open the ErrorOutput.txt file.</span></span> <span data-ttu-id="935d9-121">L'ordine predefinito delle colonne è: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="935d9-121">The default column order is: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span></span>  
  
     <span data-ttu-id="935d9-122">Si noti che tutte le righe nel file contengono il valore BAD per il CurrencyID privo di corrispondenza, il valore -1071607778 per ErrorCode, il valore 0 per ErrorColumn e il valore "Nessuna corrispondenza per la riga durante le ricerca" per ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="935d9-122">Notice that all the rows in the file contain the unmatched CurrencyID value of BAD, the ErrorCode value of -1071607778, the ErrorColumn value of 0, and the ErrorDescription value "Row yielded no match during lookup".</span></span> <span data-ttu-id="935d9-123">Il valore di ErrorColumn è impostato su 0 perché l'errore non è specifico della colonna.</span><span class="sxs-lookup"><span data-stu-id="935d9-123">The value of the ErrorColumn is set to 0 because the error is not column specific.</span></span> <span data-ttu-id="935d9-124">È l'operazione di ricerca che ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="935d9-124">It is the lookup operation that failed.</span></span> <span data-ttu-id="935d9-125">.</span><span class="sxs-lookup"><span data-stu-id="935d9-125">.</span></span>  
  
  
