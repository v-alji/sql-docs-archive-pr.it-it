---
title: "Passaggio 4: Test del pacchetto creato nella lezione 2 dell'esercitazione | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0e8c0a25-8f79-41df-8ed2-f82a74b129cd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c055f80cbe9e6748b82569204e3a2d82e2f437e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624815"
---
# <a name="step-4-testing-the-lesson-2-tutorial-package"></a><span data-ttu-id="ade73-102">Passaggio 4: Test del pacchetto creato nella lezione 2 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="ade73-102">Step 4: Testing the Lesson 2 Tutorial Package</span></span>
  <span data-ttu-id="ade73-103">Dopo aver configurato il contenitore Ciclo Foreach e la gestione connessione file flat, il pacchetto creato nella lezione 2 consente di eseguire un'iterazione dell'insieme di 14 file flat contenuti nella cartella Sample Data.</span><span class="sxs-lookup"><span data-stu-id="ade73-103">With the Foreach Loop container and the Flat File connection manager now configured, the Lesson 2 package can iterate through the collection of 14 flat files in the Sample Data folder.</span></span> <span data-ttu-id="ade73-104">Ogni volta che viene trovato un nome di file corrispondente ai criteri specificati, il contenitore Ciclo Foreach popola la variabile definita dall'utente con il nome del file.</span><span class="sxs-lookup"><span data-stu-id="ade73-104">Each time a file name is found that matches the specified file name criteria, the Foreach Loop container populates the user-defined variable with the file name.</span></span> <span data-ttu-id="ade73-105">Tale variabile aggiorna di conseguenza la proprietà ConnectionString della gestione connessione file flat e viene stabilita una connessione al nuovo file flat.</span><span class="sxs-lookup"><span data-stu-id="ade73-105">This variable, in turn, updates the ConnectionString property of the Flat File connection manager, and a connection to the new flat file is made.</span></span> <span data-ttu-id="ade73-106">Il contenitore Ciclo Foreach quindi esegue l'attività del flusso di dati non modificati sui dati del nuovo file flat prima di connettersi al file successivo contenuto nella cartella.</span><span class="sxs-lookup"><span data-stu-id="ade73-106">The Foreach Loop container then runs the unmodified data flow task against the data in the new flat file before connecting to the next file in the folder.</span></span>  
  
 <span data-ttu-id="ade73-107">Utilizzare la procedura seguente per verificare la funzionalità relativa ai cicli aggiunta al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ade73-107">Use the following procedure to test the new looping functionality that you have added to your package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ade73-108">Se si esegue il pacchetto della lezione 1, sarà necessario eliminare i record da dbo.FactCurrency in AdventureWorksDW2012 prima di eseguire il pacchetto da questa lezione. In caso contrario, il pacchetto non verrà eseguito correttamente e verranno generati errori indicanti una violazione del vincolo di chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ade73-108">If you ran the package from Lesson 1, you will need to delete the records from dbo.FactCurrency in AdventureWorksDW2012 before you run the package from this lesson or the package will fail with errors indicating a Violation of Primary Key constraint.</span></span> <span data-ttu-id="ade73-109">Verranno restituiti gli stessi errori se si esegue il pacchetto selezionando Debug/Avvia debug (o premendo F5) perché verranno eseguite entrambe le lezioni 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="ade73-109">You will receive the same errors if you run the package by selecting Debug/Start Debugging (or press F5) because both Lesson 1 and Lesson 2 will run.</span></span> <span data-ttu-id="ade73-110">Tramite la lezione 2 si tenterà di inserire record già inseriti nella lezione 1.</span><span class="sxs-lookup"><span data-stu-id="ade73-110">Lesson 2 will attempt to insert records already inserted in Lesson 1.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="ade73-111">Verifica del layout del pacchetto</span><span class="sxs-lookup"><span data-stu-id="ade73-111">Checking the Package Layout</span></span>  
 <span data-ttu-id="ade73-112">Prima di testare il pacchetto, è consigliabile verificare che il flusso di controllo e il flusso di dati nel pacchetto della lezione 2 contengano gli oggetti visualizzati nei diagrammi seguenti.</span><span class="sxs-lookup"><span data-stu-id="ade73-112">Before you test the package you should verify that the control and data flows in the Lesson 2 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="ade73-113">Il flusso di dati deve essere identico a quello nella lezione 1.</span><span class="sxs-lookup"><span data-stu-id="ade73-113">The data flow should be identical to the data flow in lesson 1.</span></span>  
  
 <span data-ttu-id="ade73-114">**Flusso di controllo**</span><span class="sxs-lookup"><span data-stu-id="ade73-114">**Control Flow**</span></span>  
  
 <span data-ttu-id="ade73-115">![Flusso di controllo nel pacchetto](../../2014/tutorials/media/task4lesson2control.gif "Flusso di controllo nel pacchetto")</span><span class="sxs-lookup"><span data-stu-id="ade73-115">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="ade73-116">**Flusso di dati**</span><span class="sxs-lookup"><span data-stu-id="ade73-116">**Data Flow**</span></span>  
  
 <span data-ttu-id="ade73-117">![Flusso di dati nel pacchetto](../../2014/tutorials/media/task9lesson1data.gif "Flusso di dati nel pacchetto")</span><span class="sxs-lookup"><span data-stu-id="ade73-117">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-2-tutorial-package"></a><span data-ttu-id="ade73-118">Per testare il pacchetto creato nella lezione 2 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="ade73-118">To test the Lesson 2 tutorial package</span></span>  
  
1.  <span data-ttu-id="ade73-119">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Lesson 2.dtsx** e scegliere **Esegui pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="ade73-119">In **Solution Explorer**, right-click **Lesson 2.dtsx** and click **Execute Package**.</span></span>  
  
     <span data-ttu-id="ade73-120">Il pacchetto verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="ade73-120">The package will run.</span></span> <span data-ttu-id="ade73-121">È possibile verificare lo stato di ogni ciclo nella finestra output o facendo clic sulla scheda **stato** . Si noterà, ad esempio, che 1097 righe sono state aggiunte alla tabella di destinazione dal file Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="ade73-121">You can verify the status of each loop in the Output window, or by clicking on the **Progress** tab. For example, you can see that 1097 lines were added to the destination table from the file Currency_VEB.txt.</span></span>  
  
2.  <span data-ttu-id="ade73-122">Al termine dell'esecuzione del pacchetto, scegliere **Arresta debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="ade73-122">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="ade73-123">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="ade73-123">Next Lesson</span></span>  
 [<span data-ttu-id="ade73-124">Lezione 5: Aggiunta di configurazioni del pacchetto per il modello di distribuzione del pacchetto</span><span class="sxs-lookup"><span data-stu-id="ade73-124">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>](../integration-services/lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="ade73-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ade73-125">See Also</span></span>  
 [<span data-ttu-id="ade73-126">Esecuzione di progetti e pacchetti</span><span class="sxs-lookup"><span data-stu-id="ade73-126">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
