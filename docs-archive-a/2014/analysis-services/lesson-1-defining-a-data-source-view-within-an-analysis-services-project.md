---
title: 'Lezione 1: definizione di una vista origine dati in un progetto Analysis Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7d3ffabd-78ae-4204-8323-29949d030c16
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a3d69225217154e5072d0cd34349a247730ddaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724287"
---
# <a name="lesson-1-defining-a-data-source-view-within-an-analysis-services-project"></a><span data-ttu-id="a9357-102">Lezione 1: Definizione di una vista origine dati in un progetto di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a9357-102">Lesson 1: Defining a Data Source View within an Analysis Services Project</span></span>
  <span data-ttu-id="a9357-103">La progettazione di un'applicazione di Business Intelligence in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] inizia con la creazione di un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9357-103">Designing a business intelligence application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with creating an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="a9357-104">Nel progetto vengono definiti tutti gli elementi della soluzione, a partire da una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="a9357-104">Within this project, you define all the elements of your solution, starting with a data source view.</span></span>  
  
 <span data-ttu-id="a9357-105">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9357-105">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="a9357-106">Creazione di un progetto di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a9357-106">Creating an Analysis Services Project</span></span>](lesson-1-1-creating-an-analysis-services-project.md)  
 <span data-ttu-id="a9357-107">In questa attività verrà creato il progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial basato su un modello multidimensionale di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9357-107">In this task, you create the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, based on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional model template.</span></span>  
  
 [<span data-ttu-id="a9357-108">Definizione di un'origine dei dati</span><span class="sxs-lookup"><span data-stu-id="a9357-108">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
 <span data-ttu-id="a9357-109">In questa attività verrà specificato il database **AdventureWorksDW2012** come origine dei dati per le dimensioni e i cubi di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] che verranno definiti nelle lezioni successive.</span><span class="sxs-lookup"><span data-stu-id="a9357-109">In this task, you specify the **AdventureWorksDW2012** database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dimensions and cubes that you will define in subsequent lessons.</span></span>  
  
 [<span data-ttu-id="a9357-110">Definizione di una vista origine dati</span><span class="sxs-lookup"><span data-stu-id="a9357-110">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
 <span data-ttu-id="a9357-111">In questa attività verrà definita una singola vista unificata dei metadati delle tabelle selezionate nel database **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="a9357-111">In this task, you define a single unified view of the metadata from selected tables in the **AdventureWorksDW2012** database.</span></span>  
  
 [<span data-ttu-id="a9357-112">Modifica dei nomi predefiniti delle tabelle</span><span class="sxs-lookup"><span data-stu-id="a9357-112">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
 <span data-ttu-id="a9357-113">In questa attività verranno modificati i nomi di tabella nella vista origine dati, in modo da semplificare i nomi degli oggetti di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] che saranno definiti successivamente.</span><span class="sxs-lookup"><span data-stu-id="a9357-113">In this task, you modify table names in the data source view, so that the names of subsequent [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects that you define will be more user-friendly.</span></span>  
  
 <span data-ttu-id="a9357-114">Confrontare i risultati rispetto a un file del progetto di esempio compilato per questa lezione.</span><span class="sxs-lookup"><span data-stu-id="a9357-114">Compare your results against a sample project file that was built for this lesson.</span></span> <span data-ttu-id="a9357-115">Per altre informazioni sul download dei progetti di esempio usati in questa esercitazione, vedere i [progetti dei modelli multidimensionali SSAS per SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) nella pagina di esempi del prodotto su codeplex.</span><span class="sxs-lookup"><span data-stu-id="a9357-115">For more information about downloading the sample projects that go with this tutorial, see [SSAS Multidimensional Model Projects for SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) on the product samples page on codeplex.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="a9357-116">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="a9357-116">Next Lesson</span></span>  
 [<span data-ttu-id="a9357-117">Lezione 2: Definizione e distribuzione di un cubo</span><span class="sxs-lookup"><span data-stu-id="a9357-117">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9357-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9357-118">See Also</span></span>  
 <span data-ttu-id="a9357-119">[Creare un progetto Analysis Services &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="a9357-119">[Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span></span>  
 <span data-ttu-id="a9357-120">[Origini dati supportate &#40;SSAS multidimensionale&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="a9357-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="a9357-121">[Viste origine dati in modelli multidimensionali](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="a9357-121">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="a9357-122">[Scenario di Analysis Services Tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a9357-122">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="a9357-123">Modellazione multidimensionale &#40;esercitazione di AdventureWorks&#41;</span><span class="sxs-lookup"><span data-stu-id="a9357-123">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
