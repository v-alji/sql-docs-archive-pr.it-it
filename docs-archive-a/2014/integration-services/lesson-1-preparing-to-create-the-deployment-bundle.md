---
title: 'Lezione 1: Preparazione alla creazione del pacchetto di distribuzione | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6fe283c-9856-4ba1-a497-e3912424fd18
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0deda2a81ddd86d4e40c1c546232b8056264508a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628824"
---
# <a name="lesson-1-preparing-to-create-the-deployment-bundle"></a><span data-ttu-id="2d3ec-102">Lezione 1: Preparazione alla creazione del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="2d3ec-102">Lesson 1: Preparing to Create the Deployment Bundle</span></span>
  <span data-ttu-id="2d3ec-103">In questa lezione verranno illustrate le procedure per creare le cartelle di lavoro e le variabili di ambiente a supporto dell'esercitazione, per creare un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , per aggiungere diversi pacchetti e i rispettivi file di supporto al progetto, nonché per implementare le configurazioni nei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-103">In this lesson, you will create the working folders and environment variables that support the tutorial, create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add several packages and their supporting files to the project, and implement configurations in packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="2d3ec-104">consente di distribuire i pacchetti in base a un progetto. Il primo passaggio della creazione del pacchetto di distribuzione consiste pertanto nella raccolta di tutti i pacchetti e delle rispettive dipendenze in un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d3ec-104">deploys packages on a project basis; therefore, as the first step in creating the deployment bundle, you must collect all the packages and package dependencies into one [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="2d3ec-105">Risulta spesso utile includere altre informazioni nei pacchetti distribuiti, ad esempio un file Leggimi contenente la documentazione di base relativa al gruppo di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-105">Frequently it is useful to include other information with the deployed packages: for example you will also add to the project a Readme file that provides basic documentation for this group of packages.</span></span>  
  
 <span data-ttu-id="2d3ec-106">Dopo aver aggiunto i pacchetti e i file, si procederà all'aggiunta delle configurazioni ai pacchetti nei quali non sono ancora utilizzate.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-106">After you have added the packages and files, you will add configurations to packages that do not already use configurations.</span></span> <span data-ttu-id="2d3ec-107">Le configurazioni consentono di aggiornare le proprietà dei pacchetti e gli oggetti dei pacchetti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-107">The configurations update properties of packages and package objects at run time.</span></span> <span data-ttu-id="2d3ec-108">In una lezione successiva si procederà alla modifica dei valori di tali configurazioni durante la distribuzione dei pacchetti allo scopo di supportare i pacchetti nell'ambiente di destinazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-108">In a later lesson, you will modify the values of these configurations during package deployment to support the packages in the deployed-to environment.</span></span>  
  
 <span data-ttu-id="2d3ec-109">Dopo aver aggiunto le configurazioni, è consigliabile aprire i pacchetti in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] , ovvero lo strumento grafico di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per la compilazione di pacchetti ETL, ed esaminare le proprietà di pacchetti e relativi elementi, nonché le configurazioni dei pacchetti per acquisire una migliore comprensione delle problematiche correlate alle esigenze di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-109">After you have added the configurations, you should open the packages in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] graphical tool for building ETL packages, and examine the properties of packages and package elements as well as the package configurations to better understand the issues that the deployment needs to address.</span></span> <span data-ttu-id="2d3ec-110">Uno dei pacchetti estrae ad esempio i dati da file di testo. Ai fini della corretta esecuzione dei pacchetti distribuiti, è pertanto necessario che il percorso dei file di dati venga aggiornato.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-110">For example, one of the packages extracts data from text files, so the location of the data files must be updated before the deployed packages will run successfully.</span></span>  
  
 <span data-ttu-id="2d3ec-111">**Tempo stimato per il completamento della lezione:** 1 ora</span><span class="sxs-lookup"><span data-stu-id="2d3ec-111">**Estimated time to complete this lesson:** 1 hour</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="2d3ec-112">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="2d3ec-112">Lesson Tasks</span></span>  
 <span data-ttu-id="2d3ec-113">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d3ec-113">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="2d3ec-114">Passaggio 1: Creazione di cartelle di lavoro e variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="2d3ec-114">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
-   [<span data-ttu-id="2d3ec-115">Passaggio 2: Creazione del progetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="2d3ec-115">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
-   [<span data-ttu-id="2d3ec-116">Passaggio 3: Aggiunta di pacchetti e altri file</span><span class="sxs-lookup"><span data-stu-id="2d3ec-116">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
-   [<span data-ttu-id="2d3ec-117">Passaggio 4: Aggiunta delle configurazioni dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="2d3ec-117">Step 4: Adding Package Configurations</span></span>](../integration-services/lesson-1-4-adding-package-configurations.md)  
  
-   [<span data-ttu-id="2d3ec-118">Passaggio 5: Test dei pacchetti aggiornati</span><span class="sxs-lookup"><span data-stu-id="2d3ec-118">Step 5: Testing the Updated Packages</span></span>](../integration-services/lesson-1-5-testing-the-updated-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="2d3ec-119">Inizio della lezione</span><span class="sxs-lookup"><span data-stu-id="2d3ec-119">Start the Lesson</span></span>  
 [<span data-ttu-id="2d3ec-120">Passaggio 1: Creazione di cartelle di lavoro e variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="2d3ec-120">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
<span data-ttu-id="2d3ec-121">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2d3ec-121">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2d3ec-122">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="2d3ec-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2d3ec-123">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="2d3ec-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2d3ec-124">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
