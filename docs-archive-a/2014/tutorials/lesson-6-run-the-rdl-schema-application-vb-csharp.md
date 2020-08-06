---
title: "Lezione 6: eseguire l'applicazione dello schema RDL (VB-C #) | Microsoft Docs"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2cd2386-2df8-4b69-ab81-9ad1a31f6d27
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 5a0fc2cd9c12b4b1602f517dc215ca44e686c663
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711171"
---
# <a name="lesson-6-run-the-rdl-schema-application-vb-c"></a><span data-ttu-id="ffd4c-102">Lezione 6: eseguire l'applicazione dello schema RDL (VB-C #)</span><span class="sxs-lookup"><span data-stu-id="ffd4c-102">Lesson 6: Run the RDL Schema Application (VB-C#)</span></span>
  <span data-ttu-id="ffd4c-103">In [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] sono disponibili due metodi per compilare ed eseguire un'applicazione console dall'ambiente di sviluppo integrato (IDE):</span><span class="sxs-lookup"><span data-stu-id="ffd4c-103">[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] offers two methods to build and run a console application from the integrated development environment (IDE):</span></span>  
  
-   <span data-ttu-id="ffd4c-104">Avvia (con debug)</span><span class="sxs-lookup"><span data-stu-id="ffd4c-104">Start (with Debugging)</span></span>  
  
-   <span data-ttu-id="ffd4c-105">Avvia senza eseguire debug</span><span class="sxs-lookup"><span data-stu-id="ffd4c-105">Start without Debugging</span></span>  
  
### <a name="to-build-and-run-the-samplerdlschema-application"></a><span data-ttu-id="ffd4c-106">Per compilare ed eseguire l'applicazione SampleRDLSchema</span><span class="sxs-lookup"><span data-stu-id="ffd4c-106">To build and run the SampleRDLSchema application</span></span>  
  
1.  <span data-ttu-id="ffd4c-107">Scegliere **Avvia senza eseguire debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="ffd4c-107">From the **Debug** menu, click **Start Without Debugging**.</span></span> <span data-ttu-id="ffd4c-108">In questo modo la finestra della console rimarrà aperta al termine dell'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="ffd4c-108">This ensures that the console window remains open after the program has finished executing.</span></span>  
  
     <span data-ttu-id="ffd4c-109">L'applicazione visualizzerà l'output seguente nella console:</span><span class="sxs-lookup"><span data-stu-id="ffd4c-109">The application prints the following output to the console:</span></span>  
  
    ```  
    Loading Report Definition  
    Updating Report Definition  
    - Old Description: <Old Report Description>  
    - New Description: <New Report Description>  
    Publishing Report Definition  
    ```  
  
2.  <span data-ttu-id="ffd4c-110">Premere un tasto per chiudere la console.</span><span class="sxs-lookup"><span data-stu-id="ffd4c-110">Press any key to close the console.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ffd4c-111">Gli eventuali errori vengono scritti nella console.</span><span class="sxs-lookup"><span data-stu-id="ffd4c-111">Any errors that occur are written to the console.</span></span>  
  
3.  <span data-ttu-id="ffd4c-112">Dopo aver eseguito l'applicazione di esempio nel server di report verrà salvata una copia aggiornata del report.</span><span class="sxs-lookup"><span data-stu-id="ffd4c-112">When the sample application is finished running an updated copy of the report will be saved to the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffd4c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffd4c-113">See Also</span></span>  
 <span data-ttu-id="ffd4c-114">[Aggiornamento dei report mediante le classi generate dallo schema RDL &#40;esercitazione su SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ffd4c-114">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="ffd4c-115">Report Definition Language &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ffd4c-115">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
