---
title: "Passaggio 4: Aggiunta di un'attività Flusso di dati al pacchetto | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 96af3073-8f11-4444-b934-fe8613a2d084
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4fda1de99e9fcaa683f9063e2feb1b71886a5cd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628839"
---
# <a name="step-4-adding-a-data-flow-task-to-the-package"></a><span data-ttu-id="6ac2e-102">Passaggio 4: Aggiunta di un'attività Flusso di dati al pacchetto</span><span class="sxs-lookup"><span data-stu-id="6ac2e-102">Step 4: Adding a Data Flow Task to the Package</span></span>
  <span data-ttu-id="6ac2e-103">Dopo aver creato le gestioni connessioni per i dati di origine e di destinazione, l'operazione successiva consiste nell'aggiunta di un'attività Flusso di dati al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6ac2e-103">After you have created the connection managers for the source and destination data, the next task is to add a Data Flow task to your package.</span></span> <span data-ttu-id="6ac2e-104">L'attività Flusso di dati incapsula il motore del flusso di dati che gestisce lo spostamento dei dati tra origini e destinazioni, offrendo funzionalità di trasformazione, pulitura e modifica dei dati durante lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="6ac2e-104">The Data Flow task encapsulates the data flow engine that moves data between sources and destinations, and provides the functionality for transforming, cleaning, and modifying data as it is moved.</span></span> <span data-ttu-id="6ac2e-105">Nell'attività Flusso di dati avviene gran parte del lavoro di un processo ETL (Extract, Transform and Load).</span><span class="sxs-lookup"><span data-stu-id="6ac2e-105">The Data Flow task is where most of the work of an extract, transform, and load (ETL) process occurs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="6ac2e-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]separa il flusso di dati dal flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="6ac2e-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates data flow from control flow.</span></span>  
  
### <a name="to-add-a-data-flow-task"></a><span data-ttu-id="6ac2e-107">Per aggiungere un'attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="6ac2e-107">To add a Data Flow task</span></span>  
  
1.  <span data-ttu-id="6ac2e-108">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="6ac2e-108">Click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="6ac2e-109">Nella **Casella degli strumenti SSIS**espandere **Preferiti**, quindi trascinare un' **Attività Flusso di dati** sulla superficie di progettazione della scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="6ac2e-109">In the **SSIS Toolbox**, expand **Favorites**, and drag a **Data Flow Task** onto the design surfaceof the **Control Flow** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ac2e-110">Se la Casella degli strumenti SSIS non è disponibile, selezionare SSIS nel menu principale e quindi Casella degli strumenti SSIS per visualizzare la casella degli strumenti in questione.</span><span class="sxs-lookup"><span data-stu-id="6ac2e-110">If the SSIS Toolbox isn't available, on the main menu select SSIS then SSIS Toolbox to display the SSIS Toolbox.</span></span>  
  
3.  <span data-ttu-id="6ac2e-111">Nell'area di progettazione **flusso di controllo** fare clic con il pulsante destro del mouse sull' **attività flusso di dati**appena aggiunta, scegliere **Rinomina**e modificare il nome in `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="6ac2e-111">On the **Control Flow** design surface, right-click the newly added **Data Flow Task**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
     <span data-ttu-id="6ac2e-112">È consigliabile fornire nomi univoci a tutti i componenti aggiunti a una superficie di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6ac2e-112">It is good practice to provide unique names to all components that you add to a design surface.</span></span> <span data-ttu-id="6ac2e-113">Per facilità d'uso e manutenzione, i nomi dovrebbero descrivere la funzione svolta da ogni componente.</span><span class="sxs-lookup"><span data-stu-id="6ac2e-113">For ease of use and maintainability, the names should describe the function that each component performs.</span></span> <span data-ttu-id="6ac2e-114">Se vengono applicate queste linee guida per la denominazione, i pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] avranno un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="6ac2e-114">Following these naming guidelines allows your [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to be self-documenting.</span></span> <span data-ttu-id="6ac2e-115">Come descrizione dei pacchetti è inoltre possibile utilizzare le annotazioni.</span><span class="sxs-lookup"><span data-stu-id="6ac2e-115">Another way to document your packages is by using annotations.</span></span> <span data-ttu-id="6ac2e-116">Per altre informazioni sulle annotazioni, vedere [Utilizzo di annotazioni nei pacchetti](use-annotations-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6ac2e-116">For more information about annotations, see [Use Annotations in Packages](use-annotations-in-packages.md).</span></span>  
  
4.  <span data-ttu-id="6ac2e-117">Fare clic con il pulsante destro del mouse sull'attività flusso di dati, scegliere **Proprietà**e nella finestra Proprietà verificare che la `LocaleID` proprietà sia impostata su **inglese (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="6ac2e-117">Right-click the Data Flow task, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6ac2e-118">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="6ac2e-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6ac2e-119">Passaggio 5: Aggiunta e configurazione dell'origine file flat</span><span class="sxs-lookup"><span data-stu-id="6ac2e-119">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ac2e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ac2e-120">See Also</span></span>  
 [<span data-ttu-id="6ac2e-121">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="6ac2e-121">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
