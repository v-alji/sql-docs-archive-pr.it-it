---
title: Creazione di un progetto di Analysis Services (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 784c0401-0358-4117-9c85-4e8220ce71d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 83eb808bc7d18ebe715d309d9f911c010ee172d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624479"
---
# <a name="creating-an-analysis-services-project-basic-data-mining-tutorial"></a><span data-ttu-id="f90ac-102">Creazione di un progetto di Analysis Services (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="f90ac-102">Creating an Analysis Services Project (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="f90ac-103">Ogni [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] progetto definisce gli oggetti in un singolo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="f90ac-103">Each [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project defines the objects in a single [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="f90ac-104">Un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] può contenere molti tipi diversi di oggetti</span><span class="sxs-lookup"><span data-stu-id="f90ac-104">An [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database can contains many different types of objects</span></span>  
  
-   <span data-ttu-id="f90ac-105">Modelli multidimensionali (cubi)</span><span class="sxs-lookup"><span data-stu-id="f90ac-105">Multidimensional models (cubes)</span></span>  
  
-   <span data-ttu-id="f90ac-106">Strutture e modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="f90ac-106">Mining structures and mining models</span></span>  
  
-   <span data-ttu-id="f90ac-107">Supporto di oggetti quali origini dati, viste origine dati e assembly personalizzati</span><span class="sxs-lookup"><span data-stu-id="f90ac-107">Supporting objects such as data sources, data source views, and custom assemblies</span></span>  
  
 <span data-ttu-id="f90ac-108">Si noti che il processo di data mining **non** richiede l'uso di un cubo.</span><span class="sxs-lookup"><span data-stu-id="f90ac-108">Note that you **do not** require a cube to do data mining.</span></span> <span data-ttu-id="f90ac-109">Se è necessario eseguire il data mining in un cubo esistente, occorre aggiungere i modelli di data mining nello stesso progetto usato per compilare il cubo.</span><span class="sxs-lookup"><span data-stu-id="f90ac-109">If you need to perform data mining on an existing cube, you should add the data mining models to the same project you used to build the cube.</span></span> <span data-ttu-id="f90ac-110">Per la maggior parte delle operazioni è tuttavia possibile compilare i modelli in origini dati relazionali, ad esempio un data warehouse, evitando così l'uso di un cubo che comporta una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f90ac-110">However, for most purposes you can build your models on relational data sources, such as a data warehouse, and get better performance if a cube is not involved.</span></span>  
  
 <span data-ttu-id="f90ac-111">In questa esercitazione verrà usato un data warehouse relazionale, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], come origine dati.</span><span class="sxs-lookup"><span data-stu-id="f90ac-111">In this tutorial you will use a relational data warehouse, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], as the data source.</span></span> <span data-ttu-id="f90ac-112">Tutti gli oggetti di data mining verranno distribuiti in un database [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] denominato `BasicDataMining`, usato esclusivamente per il data mining.</span><span class="sxs-lookup"><span data-stu-id="f90ac-112">You will deploy all your data mining objects to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database named `BasicDataMining`, used just for data mining.</span></span>  
  
 <span data-ttu-id="f90ac-113">Per impostazione predefinita, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usa l'istanza **localhost** per i nuovi progetti.</span><span class="sxs-lookup"><span data-stu-id="f90ac-113">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses the **localhost** instance for new projects.</span></span> <span data-ttu-id="f90ac-114">Se si usa un'istanza denominata o un server diverso, è necessario creare e aprire il progetto prima di modificare il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="f90ac-114">If you are using a named instance or a different server, you must first create and open the project and then change the instance name.</span></span>  
  
 <span data-ttu-id="f90ac-115">Per altre informazioni sui progetti di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , vedere [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span><span class="sxs-lookup"><span data-stu-id="f90ac-115">For more information about [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projects, see [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span></span>  
  
### <a name="to-create-an-analysis-services-project"></a><span data-ttu-id="f90ac-116">Per creare un progetto di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f90ac-116">To create an Analysis Services project</span></span>  
  
1.  <span data-ttu-id="f90ac-117">Aprire [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f90ac-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="f90ac-118">Scegliere **Nuovo** dal menu **File**e quindi selezionare **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="f90ac-118">On the **File** menu, point to **New**, and then select **Project**.</span></span>  
  
3.  <span data-ttu-id="f90ac-119">Verificare che **Progetti Business Intelligence** sia selezionato nel riquadro **Tipi progetto** .</span><span class="sxs-lookup"><span data-stu-id="f90ac-119">Verify that **Business Intelligence Projects** is selected in the **Project types** pane.</span></span>  
  
4.  <span data-ttu-id="f90ac-120">Nel riquadro **Modelli** selezionare **Progetto multidimensionale e di data mining di Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f90ac-120">In the **Templates** pane, select **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
5.  <span data-ttu-id="f90ac-121">Nella casella **nome** assegnare un nome al nuovo progetto `BasicDataMining` .</span><span class="sxs-lookup"><span data-stu-id="f90ac-121">In the **Name** box, name the new project `BasicDataMining`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-change-the-instance-where-data-mining-objects-are-stored"></a><span data-ttu-id="f90ac-122">Per modificare l'istanza in cui vengono archiviati gli oggetti di data mining</span><span class="sxs-lookup"><span data-stu-id="f90ac-122">To change the instance where data mining objects are stored</span></span>  
  
1.  <span data-ttu-id="f90ac-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="f90ac-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Project** menu, select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f90ac-124">Sul lato sinistro del riquadro **Pagine delle proprietà** fare clic su **Distribuzione**in **Proprietà di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="f90ac-124">On the left side of the **Property Pages** pane, under **Configuration Properties**, click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="f90ac-125">Sul lato destro del riquadro **Pagine delle proprietà** , verificare in **Destinazione**che il nome del **Server** sia **localhost**.</span><span class="sxs-lookup"><span data-stu-id="f90ac-125">On the right side of the **Property Pages** pane, under **Target**, verify that the **Server** name is **localhost**.</span></span> <span data-ttu-id="f90ac-126">Se si usa un'altra istanza, digitarne il nome.</span><span class="sxs-lookup"><span data-stu-id="f90ac-126">If you are using a different instance, type the name of the instance.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f90ac-127">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="f90ac-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f90ac-128">Creazione di un'origine dati &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f90ac-128">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="f90ac-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f90ac-129">See Also</span></span>  
 <span data-ttu-id="f90ac-130">[Creazione di progetti di Analysis Services &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="f90ac-130">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="f90ac-131">Creare un progetto di Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="f90ac-131">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/create-an-analysis-services-project-ssdt)  
  
  
