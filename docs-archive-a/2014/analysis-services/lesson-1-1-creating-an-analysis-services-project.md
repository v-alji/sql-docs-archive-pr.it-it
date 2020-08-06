---
title: Creazione di un progetto Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 065fdc60-1791-4e27-9ed5-51d751b3f8c4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50640dd7821943dfc3914326f7e8cba32253d307
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623560"
---
# <a name="creating-an-analysis-services-project"></a><span data-ttu-id="ab706-102">Creazione di un progetto di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ab706-102">Creating an Analysis Services Project</span></span>
  <span data-ttu-id="ab706-103">Nell'attività seguente viene usato [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per creare un nuovo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] progetto denominato `Analysis Services Tutorial` , basato sul [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] modello di progetto.</span><span class="sxs-lookup"><span data-stu-id="ab706-103">In the following task, you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project named `Analysis Services Tutorial`, based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Project template.</span></span> <span data-ttu-id="ab706-104">Un *progetto* è una raccolta di oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="ab706-104">A *project* is a collection of related objects.</span></span> <span data-ttu-id="ab706-105">I progetti sono contenuti in una soluzione che include uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="ab706-105">Projects exist within a solution, which includes one or more projects.</span></span> <span data-ttu-id="ab706-106">Per altre informazioni, vedere [Creare un progetto di Analysis Services &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="ab706-106">For more information, see [Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span></span>  
  
### <a name="to-create-a-new-analysis-services-project"></a><span data-ttu-id="ab706-107">Per creare un nuovo progetto di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ab706-107">To create a new Analysis Services project</span></span>  
  
1.  <span data-ttu-id="ab706-108">Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server 2012**, quindi fare clic su **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="ab706-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
     <span data-ttu-id="ab706-109">[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Viene aperto l'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="ab706-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment opens.</span></span>  
  
2.  <span data-ttu-id="ab706-110">Nella pagina iniziale di [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]fare clic su **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="ab706-110">On the Start page of [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New Project**.</span></span>  
  
3.  <span data-ttu-id="ab706-111">Nella finestra di dialogo **Nuovo progetto** nel riquadro **modelli installati** espandere **Business Intelligence**, quindi selezionare **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="ab706-111">In the **New Project** dialog box, in the **Installed Templates** pane, expand **Business Intelligence**, and then select **Analysis Services**.</span></span> <span data-ttu-id="ab706-112">Scegliere il modello **Progetto multidimensionale e di data mining di Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="ab706-112">Choose the **Analysis Services Multidimensional and Data Mining Project** template.</span></span>  
  
     <span data-ttu-id="ab706-113">Si noti che il nome predefinito del progetto, la posizione, e il nome predefinito della soluzione vengono generati nella parte inferiore della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ab706-113">Notice the default project name, location, and the default solution name are generated in the bottom of the dialog box.</span></span> <span data-ttu-id="ab706-114">Per impostazione predefinita, viene creata una nuova directory per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="ab706-114">By default, a new directory is created for the solution.</span></span>  
  
4.  <span data-ttu-id="ab706-115">Modificare il nome del progetto in `Analysis Services Tutorial` , che modifica anche la casella **Nome soluzione** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab706-115">Change the project Name to `Analysis Services Tutorial`, which also changes the **Solution name** box, and then click **OK**.</span></span>  
  
 <span data-ttu-id="ab706-116">Il progetto è stato creato `Analysis Services Tutorial` in base al modello di **progetto multidimensionale e di Data Mining di Analysis Services** , all'interno di una nuova soluzione anch ' essa denominata `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="ab706-116">You have successfully created the `Analysis Services Tutorial` project, based on the **Analysis Services Multidimensional and Data Mining Project** template, within a new solution that is also named `Analysis Services Tutorial`.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ab706-117">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="ab706-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ab706-118">Definizione di un'origine dei dati</span><span class="sxs-lookup"><span data-stu-id="ab706-118">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="ab706-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab706-119">See Also</span></span>  
 <span data-ttu-id="ab706-120">[Creazione di modelli multidimensionali tramite SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="ab706-120">[Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span></span>  
 [<span data-ttu-id="ab706-121">Creare un progetto di Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-121">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](multidimensional-models/create-an-analysis-services-project-ssdt.md)  
  
  
