---
title: 'Lezione 2: definizione e distribuzione di un cubo | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bb62e3c9-462f-4ad2-ac8e-92e2f9e9cc28
author: minewiskan
ms.author: owend
ms.openlocfilehash: a2c043920ac646ec4da9eaa2aace4bf6f48e694c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635851"
---
# <a name="lesson-2-defining-and-deploying-a-cube"></a><span data-ttu-id="13f43-102">Lezione 2: Definizione e distribuzione di un cubo</span><span class="sxs-lookup"><span data-stu-id="13f43-102">Lesson 2: Defining and Deploying a Cube</span></span>
  <span data-ttu-id="13f43-103">Dopo aver definito una vista origine dati nel [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] progetto, si è pronti per definire un cubo iniziale [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13f43-103">After you define a data source view in your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you are ready to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 <span data-ttu-id="13f43-104">È possibile definire un cubo e le rispettive dimensioni in un solo passaggio utilizzando la Creazione guidata cubo.</span><span class="sxs-lookup"><span data-stu-id="13f43-104">You can define a cube and its dimensions in a single pass using the Cube Wizard.</span></span> <span data-ttu-id="13f43-105">In alternativa, è possibile definire una o più dimensioni, quindi utilizzare la Creazione guidata cubo per definire un cubo che utilizza tali dimensioni.</span><span class="sxs-lookup"><span data-stu-id="13f43-105">Alternatively, you can define one or more dimensions and then use the Cube Wizard to define a cube that uses those dimensions.</span></span> <span data-ttu-id="13f43-106">Se si progetta una soluzione complessa, in genere si inizia con la definizione delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="13f43-106">If you are designing a complex solution, you generally start by defining the dimensions.</span></span> <span data-ttu-id="13f43-107">Per altre informazioni, vedere [Dimensioni nei modelli multidimensionali](multidimensional-models/dimensions-in-multidimensional-models.md) o [Cubi nei modelli multidimensionali](multidimensional-models/cubes-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="13f43-107">For more information, see [Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) or [Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13f43-108">I progetti completati per tutte le lezioni in questa esercitazione sono disponibili online.</span><span class="sxs-lookup"><span data-stu-id="13f43-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="13f43-109">È possibile passare a qualsiasi lezione utilizzando il progetto completato della lezione precedente come punto iniziale.</span><span class="sxs-lookup"><span data-stu-id="13f43-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="13f43-110">[Fare clic qui](https://go.microsoft.com/fwlink/?LinkID=221866) per scaricare i progetti di esempio usati in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="13f43-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="13f43-111">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="13f43-111">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="13f43-112">Definizione di una dimensione</span><span class="sxs-lookup"><span data-stu-id="13f43-112">Defining a Dimension</span></span>](lesson-2-1-defining-a-dimension.md)  
 <span data-ttu-id="13f43-113">In questa attività si utilizza la Creazione guidata dimensione per definire una dimensione.</span><span class="sxs-lookup"><span data-stu-id="13f43-113">In this task, you use the Dimension Wizard to define a dimension.</span></span>  
  
 [<span data-ttu-id="13f43-114">Definizione di un cubo</span><span class="sxs-lookup"><span data-stu-id="13f43-114">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
 <span data-ttu-id="13f43-115">In questa attività si utilizza la Creazione guidata cubo per definire un cubo iniziale di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13f43-115">In this task, you use the Cube Wizard to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 [<span data-ttu-id="13f43-116">Aggiunta di attributi alle dimensioni</span><span class="sxs-lookup"><span data-stu-id="13f43-116">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
 <span data-ttu-id="13f43-117">In questa attività si aggiungono attributi alle dimensioni create.</span><span class="sxs-lookup"><span data-stu-id="13f43-117">In this task, you add attributes to the dimensions that you created.</span></span>  
  
 [<span data-ttu-id="13f43-118">Esame delle proprietà del cubo e delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="13f43-118">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
 <span data-ttu-id="13f43-119">In questa attività si controlla la struttura del cubo definito tramite la Creazione guidata cubo.</span><span class="sxs-lookup"><span data-stu-id="13f43-119">In this task, you review the structure of the cube that you defined by using the Cube Wizard.</span></span>  
  
 [<span data-ttu-id="13f43-120">Distribuzione di un progetto di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="13f43-120">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
 <span data-ttu-id="13f43-121">In questa attività il progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] viene distribuito all'istanza locale di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. Vengono inoltre illustrate alcune proprietà di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="13f43-121">In this task, you deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project to your local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], and learn about certain deployment properties.</span></span>  
  
 [<span data-ttu-id="13f43-122">Esplorazione del cubo</span><span class="sxs-lookup"><span data-stu-id="13f43-122">Browsing the Cube</span></span>](lesson-2-6-browsing-the-cube.md)  
 <span data-ttu-id="13f43-123">In questa attività verranno illustrate le procedure per esplorare i dati del cubo e delle dimensioni utilizzando Excel o la progettazione query MDX.</span><span class="sxs-lookup"><span data-stu-id="13f43-123">In this task, you browse the cube and dimension data by using Excel or the MDX query designer.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="13f43-124">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="13f43-124">Next Lesson</span></span>  
 [<span data-ttu-id="13f43-125">Lezione 3: Modifica di misure, attributi e gerarchie</span><span class="sxs-lookup"><span data-stu-id="13f43-125">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>](lesson-3-modifying-measures-attributes-and-hierarchies.md)  
  
## <a name="see-also"></a><span data-ttu-id="13f43-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13f43-126">See Also</span></span>  
 <span data-ttu-id="13f43-127">[Scenario di Analysis Services Tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="13f43-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="13f43-128">[Esercitazione di modellazione multidimensionale &#40;Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="13f43-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="13f43-129">[Dimensioni nei modelli multidimensionali](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="13f43-129">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="13f43-130">[Cubi nei modelli multidimensionali](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="13f43-130">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="13f43-131">[Configurare Analysis Services proprietà del progetto &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="13f43-131">[Configure Analysis Services Project Properties &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span></span>  
 <span data-ttu-id="13f43-132">[Creazione di progetti di Analysis Services &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="13f43-132">[Build Analysis Services Projects &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span></span>  
 [<span data-ttu-id="13f43-133">Distribuire progetti di Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="13f43-133">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
  
