---
title: "Passaggio 9: Test del pacchetto creato nella lezione 1 dell'esercitazione | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9aee7acf-797b-46f2-830d-80ab64a9f0b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dff1132489c1683430b1003e88f5037664b11983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628825"
---
# <a name="step-9-testing-the-lesson-1-tutorial-package"></a><span data-ttu-id="42919-102">Passaggio 9: Test del pacchetto creato nella lezione 1 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="42919-102">Step 9: Testing the Lesson 1 Tutorial Package</span></span>
  <span data-ttu-id="42919-103">In questa lezione sono state eseguite le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42919-103">In this lesson, you have done the following tasks:</span></span>  
  
-   <span data-ttu-id="42919-104">Creazione di un nuovo progetto [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42919-104">Created a new [!INCLUDE[ssIS](../includes/ssis-md.md)] project.</span></span>  
  
-   <span data-ttu-id="42919-105">Configurazione delle gestioni connessioni necessarie al pacchetto per connettersi ai dati di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42919-105">Configured the connection managers that the package needs to connect to the source and destination data.</span></span>  
  
-   <span data-ttu-id="42919-106">Aggiunta di un flusso di dati che preleva i dati da un'origine file flat, esegue le necessarie trasformazioni Ricerca sui dati e configura i dati per la destinazione.</span><span class="sxs-lookup"><span data-stu-id="42919-106">Added a data flow that takes the data from a flat file source, performs the necessary Lookup transformations on the data, and configures the data for the destination.</span></span>  
  
 <span data-ttu-id="42919-107">Il pacchetto è ora completo.</span><span class="sxs-lookup"><span data-stu-id="42919-107">Your package is now complete!</span></span> <span data-ttu-id="42919-108">A questo punto, è necessario testarlo.</span><span class="sxs-lookup"><span data-stu-id="42919-108">It is time to test your package.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="42919-109">Verifica del layout del pacchetto</span><span class="sxs-lookup"><span data-stu-id="42919-109">Checking the Package Layout</span></span>  
 <span data-ttu-id="42919-110">Prima di testare il pacchetto è consigliabile verificare che il flusso di controllo e il flusso di dati nel pacchetto della lezione 1 contengano gli oggetti visualizzati nelle figure seguenti.</span><span class="sxs-lookup"><span data-stu-id="42919-110">Before you test the package you should verify that the control and data flows in the Lesson 1 package contain the objects shown in the following diagrams.</span></span>  
  
 <span data-ttu-id="42919-111">**Flusso di controllo**</span><span class="sxs-lookup"><span data-stu-id="42919-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="42919-112">![Flusso di controllo nel pacchetto](../../2014/tutorials/media/task9lesson1control.gif "Flusso di controllo nel pacchetto")</span><span class="sxs-lookup"><span data-stu-id="42919-112">![Control flow in package](../../2014/tutorials/media/task9lesson1control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="42919-113">**Flusso di dati**</span><span class="sxs-lookup"><span data-stu-id="42919-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="42919-114">![Flusso di dati nel pacchetto](../../2014/tutorials/media/task9lesson1data.gif "Flusso di dati nel pacchetto")</span><span class="sxs-lookup"><span data-stu-id="42919-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-1-tutorial-package"></a><span data-ttu-id="42919-115">Per eseguire il pacchetto creato nella lezione 1 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="42919-115">To run the Lesson 1 tutorial package</span></span>  
  
1.  <span data-ttu-id="42919-116">Dal menu **Debug** scegliere **Avvia debug**.</span><span class="sxs-lookup"><span data-stu-id="42919-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="42919-117">Il pacchetto verrà eseguito e verranno aggiunte 1097 righe alla tabella dei fatti **FactCurrency** in **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="42919-117">The package will run, resulting in 1097 rows successfully added into the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span>  
  
2.  <span data-ttu-id="42919-118">Al termine dell'esecuzione del pacchetto, scegliere **Arresta debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="42919-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="42919-119">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="42919-119">Next Lesson</span></span>  
 [<span data-ttu-id="42919-120">Lezione 2: Aggiunta di cicli</span><span class="sxs-lookup"><span data-stu-id="42919-120">Lesson 2: Adding Looping</span></span>](../integration-services/lesson-2-adding-looping-with-ssis.md)  
  
## <a name="see-also"></a><span data-ttu-id="42919-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42919-121">See Also</span></span>  
 [<span data-ttu-id="42919-122">Esecuzione di progetti e pacchetti</span><span class="sxs-lookup"><span data-stu-id="42919-122">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
