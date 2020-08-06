---
title: 'Lezione 1: preparazione del database di Analysis Services (esercitazione di base sul data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a796977-6568-4705-9d27-86a9b36658c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 07647a940851fbdbdc65357e168747662dc88380
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726396"
---
# <a name="lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial"></a><span data-ttu-id="7b712-102">Lezione 1: Preparazione del database di Analysis Services (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="7b712-102">Lesson 1: Preparing the Analysis Services Database (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="7b712-103">L'utente è un nuovo dipendente di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] chi ha eseguito attività di progettazione di un'applicazione Business Intelligence in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b712-103">You are a new employee of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] who has been tasked with designing a business intelligence application in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]<span data-ttu-id="7b712-104">spera di sfruttare la tua [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] esperienza di data mining per individuare informazioni interessanti e interoperabili sulle persone che hanno acquistato biciclette.</span><span class="sxs-lookup"><span data-stu-id="7b712-104">hopes to leverage your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data mining experience to discover interesting and actionable information about people who have purchased bicycles.</span></span> <span data-ttu-id="7b712-105">Si è quindi incaricati di eseguire una stima dei potenziali clienti che con maggiore probabilità acquisteranno una bicicletta in futuro.</span><span class="sxs-lookup"><span data-stu-id="7b712-105">They then want you to predict which prospective customers are most likely to purchase a bicycle in the future.</span></span>  
  
 <span data-ttu-id="7b712-106">La progettazione di questa applicazione in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] inizia con la creazione in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] di un [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] progetto basato sul [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] modello di progetto per la modellazione multidimensionale e la data mining.</span><span class="sxs-lookup"><span data-stu-id="7b712-106">Designing this application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with the creation in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project template for multidimensional modeling and data mining.</span></span> <span data-ttu-id="7b712-107">Dopo aver creato un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], è possibile definire una o più origini dei dati.</span><span class="sxs-lookup"><span data-stu-id="7b712-107">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you define one or more data sources.</span></span> <span data-ttu-id="7b712-108">Viene quindi definita una vista dei metadati, denominata *vista origine dati*, dalle tabelle e dalle viste selezionate dalle origini dati.</span><span class="sxs-lookup"><span data-stu-id="7b712-108">Then, you define a view of the metadata, called a *data source view*, from selected tables and views from the data sources.</span></span>  
  
 <span data-ttu-id="7b712-109">In questa esercitazione verranno illustrate le procedure per la creazione di un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], la definizione di una singola origine dei dati e l'aggiunta di un subset di tabelle alla vista origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="7b712-109">In this lesson, you will create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, define a single data source, and add a subset of tables to a data source view.</span></span> <span data-ttu-id="7b712-110">Questa lezione include le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b712-110">This lesson includes the following tasks:</span></span>  
  
 [<span data-ttu-id="7b712-111">Creazione di un progetto Analysis Services &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7b712-111">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="7b712-112">Creazione di un'origine dati &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7b712-112">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="7b712-113">Creazione di una vista origine dati &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7b712-113">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="7b712-114">Prima attività della lezione</span><span class="sxs-lookup"><span data-stu-id="7b712-114">First Task in Lesson</span></span>  
 [<span data-ttu-id="7b712-115">Creazione di un progetto Analysis Services &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7b712-115">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="7b712-116">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="7b712-116">Next Lesson</span></span>  
 [<span data-ttu-id="7b712-117">Lezione 2: creazione di una struttura di mailing diretto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7b712-117">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b712-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b712-118">See Also</span></span>  
 <span data-ttu-id="7b712-119">[Viste origine dati in modelli multidimensionali](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span><span class="sxs-lookup"><span data-stu-id="7b712-119">[Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span></span>  
 <span data-ttu-id="7b712-120">[Origini dati supportate &#40;SSAS multidimensionale&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="7b712-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span></span>  
 <span data-ttu-id="7b712-121">[Creazione di progetti di Analysis Services &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="7b712-121">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="7b712-122">Creazione di un progetto di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7b712-122">Creating an Analysis Services Project</span></span>](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md)  
  
  
