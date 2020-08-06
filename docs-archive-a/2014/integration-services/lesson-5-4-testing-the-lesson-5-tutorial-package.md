---
title: "Passaggio 4: Test del pacchetto creato nella lezione 5 dell'esercitazione | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5215b77d-c2ec-4b25-a3de-ca49ea197d74
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 76e4692de4daa9ddd6ed0e418bed5cda74ec7650
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626140"
---
# <a name="step-4-testing-the-lesson-5-tutorial-package"></a><span data-ttu-id="7a7c9-102">Passaggio 4: Test del pacchetto creato nell'esercitazione della lezione 5</span><span class="sxs-lookup"><span data-stu-id="7a7c9-102">Step 4: Testing the Lesson 5 Tutorial Package</span></span>
  <span data-ttu-id="7a7c9-103">In fase di esecuzione, il pacchetto ottiene il valore della proprietà `Directory` da una variabile aggiornata in fase di esecuzione, anziché utilizzare il nome della directory originale specificato quando è stato creato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-103">At run time, your package will obtain the value for the `Directory` property from a variable updated at run time, rather than using the original directory name that you specified when you created the package.</span></span> <span data-ttu-id="7a7c9-104">Il valore della variabile è popolato dal file SSISTutorial.dtsConfig file.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-104">The value of the variable is populated by the SSISTutorial.dtsConfig file.</span></span>  
  
 <span data-ttu-id="7a7c9-105">Per verificare che il pacchetto esegua l'aggiornamento della proprietà Directory con il nuovo valore in fase di esecuzione, eseguire semplicemente il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-105">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="7a7c9-106">Poiché solo tre file di dati di esempio sono stati copiati nella nuova directory, il flusso di dati verrà eseguito solo tre volte anziché essere reiterato nei 14 file della cartella originale.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-106">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="7a7c9-107">Verifica del layout del pacchetto</span><span class="sxs-lookup"><span data-stu-id="7a7c9-107">Checking the Package Layout</span></span>  
 <span data-ttu-id="7a7c9-108">Prima di testare il pacchetto è consigliabile verificare che il flusso di controllo e il flusso di dati nel pacchetto della lezione 5 contengano gli oggetti visualizzati nelle figure seguenti.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-108">Before you test the package you should verify that the control and data flows in the Lesson 5 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="7a7c9-109">Il flusso di controllo deve essere identico a quello nella lezione 4.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-109">The control flow should be identical to the control flow in lesson 4.</span></span> <span data-ttu-id="7a7c9-110">Il flusso di dati deve essere identico a quello nella lezione 4.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-110">The data flow should be identical to the data flow in lessons 4.</span></span>  
  
 <span data-ttu-id="7a7c9-111">**Flusso di controllo**</span><span class="sxs-lookup"><span data-stu-id="7a7c9-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="7a7c9-112">![Flusso di controllo nel pacchetto](../../2014/tutorials/media/task4lesson2control.gif "Flusso di controllo nel pacchetto")</span><span class="sxs-lookup"><span data-stu-id="7a7c9-112">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="7a7c9-113">**Flusso di dati**</span><span class="sxs-lookup"><span data-stu-id="7a7c9-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="7a7c9-114">![Flusso di dati nel pacchetto](../../2014/tutorials/media/task9lesson1data.gif "Flusso di dati nel pacchetto")</span><span class="sxs-lookup"><span data-stu-id="7a7c9-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-5-tutorial-package"></a><span data-ttu-id="7a7c9-115">Per testare il pacchetto creato nella lezione 5 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="7a7c9-115">To test the Lesson 5 tutorial package</span></span>  
  
1.  <span data-ttu-id="7a7c9-116">Dal menu **Debug** scegliere **Avvia debug**.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="7a7c9-117">Al termine dell'esecuzione del pacchetto, scegliere **Interrompi debug**dal menu **debug** .</span><span class="sxs-lookup"><span data-stu-id="7a7c9-117">After the package has completed running, on the **Debug** menu, and then click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="7a7c9-118">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="7a7c9-118">Next Lesson</span></span>  
 [<span data-ttu-id="7a7c9-119">Lezione 6: Uso di parametri con il modello di distribuzione del progetto</span><span class="sxs-lookup"><span data-stu-id="7a7c9-119">Lesson 6: Using Parameters with the Project Deployment Model</span></span>](../integration-services/lesson-6-using-parameters-with-the-project-deployment-model-in-ssis.md)  
  
  
