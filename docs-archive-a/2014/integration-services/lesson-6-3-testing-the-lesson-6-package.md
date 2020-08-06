---
title: 'Passaggio 3: Test del pacchetto della lezione 6 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c184c92d-948f-4037-a502-5fabd909c84c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3c7ab82e9b04fe0752252102374f745e311d830d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721603"
---
# <a name="step-3-testing-the-lesson-6-package"></a><span data-ttu-id="613c7-102">Passaggio 3: Test del pacchetto della lezione 6</span><span class="sxs-lookup"><span data-stu-id="613c7-102">Step 3: Testing the Lesson 6 Package</span></span>
  <span data-ttu-id="613c7-103">In fase di esecuzione, il pacchetto ottiene il valore della proprietà Directory dal parametro VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="613c7-103">At run time, your package will obtain the value for the Directory property from the VarFolderName parameter.</span></span>  
  
 <span data-ttu-id="613c7-104">Per verificare che il pacchetto esegua l'aggiornamento della proprietà Directory con il nuovo valore in fase di esecuzione, eseguire semplicemente il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="613c7-104">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="613c7-105">Poiché solo tre file di dati di esempio sono stati copiati nella nuova directory, il flusso di dati verrà eseguito solo tre volte anziché essere reiterato nei 14 file della cartella originale.</span><span class="sxs-lookup"><span data-stu-id="613c7-105">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="613c7-106">Verifica del layout del pacchetto</span><span class="sxs-lookup"><span data-stu-id="613c7-106">Checking the Package Layout</span></span>  
 <span data-ttu-id="613c7-107">Prima di testare il pacchetto è consigliabile verificare che il flusso di controllo e il flusso di dati nel pacchetto della lezione 6 contengano gli oggetti visualizzati nelle figure seguenti.</span><span class="sxs-lookup"><span data-stu-id="613c7-107">Before you test the package you should verify that the control and data flows in the Lesson 6 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="613c7-108">Il flusso di controllo deve essere identico a quello nella lezione 5.</span><span class="sxs-lookup"><span data-stu-id="613c7-108">The control flow should be identical to the control flow in lesson 5.</span></span> <span data-ttu-id="613c7-109">Il flusso di dati deve essere identico a quello nella lezione 5.</span><span class="sxs-lookup"><span data-stu-id="613c7-109">The data flow should be identical to the data flow in lesson 5.</span></span>  
  
 <span data-ttu-id="613c7-110">**Flusso di controllo**</span><span class="sxs-lookup"><span data-stu-id="613c7-110">**Control Flow**</span></span>  
  
 <span data-ttu-id="613c7-111">![Flusso di controllo](../../2014/tutorials/media/task3lesson6control.jpg "Flusso di controllo")</span><span class="sxs-lookup"><span data-stu-id="613c7-111">![Control Flow](../../2014/tutorials/media/task3lesson6control.jpg "Control Flow")</span></span>  
  
 <span data-ttu-id="613c7-112">**Flusso di dati**</span><span class="sxs-lookup"><span data-stu-id="613c7-112">**Data Flow**</span></span>  
  
 <span data-ttu-id="613c7-113">![Flusso di dati](../../2014/tutorials/media/task3lesson6data.jpg "Flusso di dati")</span><span class="sxs-lookup"><span data-stu-id="613c7-113">![Data Flow](../../2014/tutorials/media/task3lesson6data.jpg "Data Flow")</span></span>  
  
### <a name="to-test-the-lesson-6-tutorial-package"></a><span data-ttu-id="613c7-114">Per testare il pacchetto creato nella lezione 6 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="613c7-114">TO test the Lesson 6 tutorial package</span></span>  
  
1.  <span data-ttu-id="613c7-115">Scegliere Avvia debug dal menu Debug.</span><span class="sxs-lookup"><span data-stu-id="613c7-115">On the Debug menu, click Start Debugging.</span></span>  
  
2.  <span data-ttu-id="613c7-116">Al termine dell'esecuzione del pacchetto, scegliere Arresta debug dal menu Debug.</span><span class="sxs-lookup"><span data-stu-id="613c7-116">After the package has completed running, on the Debug menu, and then click Stop Debugging.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="613c7-117">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="613c7-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="613c7-118">Passaggio 4: Distribuzione del pacchetto della lezione 6</span><span class="sxs-lookup"><span data-stu-id="613c7-118">Step 4: Deploying the Lesson 6 Package</span></span>](../integration-services/lesson-6-4-deploying-the-lesson-6-package.md)  
  
  
