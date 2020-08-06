---
title: 'Lezione 3: installazione dei pacchetti | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 87bc4d82-39d8-424f-886f-98cf1e4bb07a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f8b58cee7bd8e16cd0ca2e726dc8e5eff2cfec5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627884"
---
# <a name="lesson-3-installing-packages"></a><span data-ttu-id="8c618-102">Lezione 3: Installazione di pacchetti</span><span class="sxs-lookup"><span data-stu-id="8c618-102">Lesson 3: Installing Packages</span></span>
  <span data-ttu-id="8c618-103">Nella [lezione 2: creazione del pacchetto di distribuzione](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)è stata compilata un'utilità di distribuzione e è stato creato il pacchetto di distribuzione che contiene gli elementi necessari per installare i pacchetti in un altro computer.</span><span class="sxs-lookup"><span data-stu-id="8c618-103">In [Lesson 2: Creating the Deployment Bundle](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md), you built a deployment utility and created the deployment bundle that contains the items that you must install packages on another computer.</span></span> <span data-ttu-id="8c618-104">È stato inoltre verificato l'elenco dei file inclusi nel pacchetto di distribuzione ed è stato esaminato il contenuto del file manifesto creato contestualmente all'utilità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8c618-104">You also verified the file list in the deployment bundle and examined the contents of the manifest file that was created when you built the deployment utility.</span></span>  
  
 <span data-ttu-id="8c618-105">In questa lezione si procederà alla copia del pacchetto di distribuzione nel computer di destinazione e quindi all'esecuzione dell'Installazione guidata pacchetti per installare i pacchetti, le rispettive dipendenze e i file ausiliari nel computer.</span><span class="sxs-lookup"><span data-stu-id="8c618-105">In this lesson, you will copy the deployment bundle to the destination computer and then run the Package Installation Wizard to install the packages, package dependencies, and ancillary files on that computer.</span></span> <span data-ttu-id="8c618-106">I pacchetti verranno installati nel database **msdb** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e gli altri elementi verranno installati nel file System.</span><span class="sxs-lookup"><span data-stu-id="8c618-106">The packages will be installed in the **msdb**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database and the other items will be installed in the file system.</span></span> <span data-ttu-id="8c618-107">Dopo aver completato l'installazione dei pacchetti, questi ultimi verranno eseguiti in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] mediante l'Utilità di esecuzione pacchetti allo scopo di testare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8c618-107">After you complete the package installation, you will test the deployment by running the packages from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] using the Execute Package Utility.</span></span>  
  
 <span data-ttu-id="8c618-108">**Tempo stimato per il completamento della lezione:** 30 minuti</span><span class="sxs-lookup"><span data-stu-id="8c618-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="8c618-109">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="8c618-109">Lesson Tasks</span></span>  
 <span data-ttu-id="8c618-110">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c618-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="8c618-111">Passaggio 1: Copia del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="8c618-111">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
-   [<span data-ttu-id="8c618-112">Passaggio 2: Esecuzione dell'Installazione guidata pacchetti</span><span class="sxs-lookup"><span data-stu-id="8c618-112">Step 2: Running the Package Installation Wizard</span></span>](../integration-services/lesson-3-2-running-the-package-installation-wizard.md)  
  
-   [<span data-ttu-id="8c618-113">Passaggio 3: Test dei pacchetti distribuiti</span><span class="sxs-lookup"><span data-stu-id="8c618-113">Step 3: Testing the Deployed Packages</span></span>](../integration-services/lesson-3-3-testing-the-deployed-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="8c618-114">Inizio della lezione</span><span class="sxs-lookup"><span data-stu-id="8c618-114">Start the Lesson</span></span>  
 [<span data-ttu-id="8c618-115">Passaggio 1: Copia del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="8c618-115">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
<span data-ttu-id="8c618-116">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8c618-116">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8c618-117">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="8c618-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8c618-118">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="8c618-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8c618-119">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="8c618-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
