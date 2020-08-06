---
title: 'Passaggio 5: Test dei pacchetti aggiornati | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 683e52e5-1c7e-49ab-9ffe-6a450a1c5776
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a075af2e030c8257d01abf5eba7d330b1cc8efe7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628833"
---
# <a name="step-5-testing-the-updated-packages"></a><span data-ttu-id="49140-102">Passaggio 5: Test dei pacchetti aggiornati</span><span class="sxs-lookup"><span data-stu-id="49140-102">Step 5: Testing the Updated Packages</span></span>
  <span data-ttu-id="49140-103">Prima di passare alla lezione successiva, nella quale si procederà alla creazione del pacchetto di distribuzione da utilizzare per installare i pacchetti dell'esercitazione nel computer di destinazione, è consigliabile testare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="49140-103">Before you go on to the next lesson, in which you will create the deployment bundle to use to install the tutorial packages on the destination computer, you should test the packages.</span></span> <span data-ttu-id="49140-104">In questa attività verranno eseguiti i pacchetti DataTransfer.dtsx e LoadXMLData, precedentemente aggiunti al progetto Deployment Tutorial e opportunamente estesi mediante le configurazioni.</span><span class="sxs-lookup"><span data-stu-id="49140-104">In this task, you will run the packages, DataTransfer.dtsx and LoadXMLData, that you added to the Deployment Tutorial project and then extended with configurations.</span></span>  
  
 <span data-ttu-id="49140-105">Quando si eseguono i pacchetti, ogni file eseguibile in essi contenuto diventa di colore verde se l'esito è positivo.</span><span class="sxs-lookup"><span data-stu-id="49140-105">When the packages run, each executable in the package becomes a green color as it completes successfully.</span></span> <span data-ttu-id="49140-106">Se tutti i file eseguibili sono di colore verde, il pacchetto è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="49140-106">When all executables are green, the package has completed successfully.</span></span> <span data-ttu-id="49140-107">È inoltre possibile visualizzare lo stato di esecuzione dei pacchetti nella scheda **Stato** .</span><span class="sxs-lookup"><span data-stu-id="49140-107">You can also view the package execution progress on the **Progress** tab.</span></span>  
  
 <span data-ttu-id="49140-108">Se i pacchetti non vengono eseguiti correttamente, è necessario correggerli prima di passare alla lezione successiva.</span><span class="sxs-lookup"><span data-stu-id="49140-108">If the packages do not run successfully, you must fix them before you go on to the next lesson.</span></span>  
  
### <a name="to-run-the-datatransfer-package"></a><span data-ttu-id="49140-109">Per eseguire il pacchetto DataTransfer</span><span class="sxs-lookup"><span data-stu-id="49140-109">To run the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="49140-110">In Esplora soluzioni fare clic su DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="49140-110">In Solution Explorer, click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="49140-111">Scegliere **Avvia debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="49140-111">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="49140-112">Al termine dell'esecuzione del pacchetto, scegliere **Arresta debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="49140-112">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-run-the-loadxmldata-package"></a><span data-ttu-id="49140-113">Per eseguire il pacchetto LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="49140-113">To run the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="49140-114">In Esplora soluzioni fare clic su LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="49140-114">In Solution Explorer, click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="49140-115">Scegliere **Avvia debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="49140-115">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="49140-116">Al termine dell'esecuzione del pacchetto, scegliere **Arresta debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="49140-116">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="49140-117">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="49140-117">Next Lesson</span></span>  
 [<span data-ttu-id="49140-118">Lezione 2: Creazione del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="49140-118">Lesson 2: Creating the Deployment Bundle</span></span>](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)  
  
<span data-ttu-id="49140-119">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="49140-119">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="49140-120">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="49140-120">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="49140-121">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="49140-121">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="49140-122">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="49140-122">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
