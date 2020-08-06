---
title: Aggiungere o rimuovere un progetto Integration Services in una soluzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- Integration Services projects, adding
- SQL Server Integration Services projects, adding
- SSIS projects, adding
- projects [Integration Services], adding
ms.assetid: f01f6475-b63c-41dc-82ac-b62162b3adf7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49984c61047a6b716015bd72e518b73cb08b3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623463"
---
# <a name="add-or-remove-an-integration-services-project-in-a-solution"></a><span data-ttu-id="078c5-102">Aggiunta o rimozione di un progetto di Integration Services da una soluzione</span><span class="sxs-lookup"><span data-stu-id="078c5-102">Add or Remove an Integration Services Project in a Solution</span></span>
  <span data-ttu-id="078c5-103">Nelle procedure seguenti viene descritto come aggiungere o rimuovere un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] da una soluzione.</span><span class="sxs-lookup"><span data-stu-id="078c5-103">The following procedures descibe how to add or remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in a solution.</span></span>  
  
 <span data-ttu-id="078c5-104">È possibile aggiungere o rimuovere un progetto da una soluzione solo se la soluzione è visibile in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="078c5-104">You can only add a project to an existing solution, or remove a project from a solution, when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="078c5-105">Se è stata selezionata l'opzione **Mostra sempre soluzione** in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] viene visualizzata una soluzione anche se tale soluzione contiene un solo progetto.</span><span class="sxs-lookup"><span data-stu-id="078c5-105">If you have selected the **Always show solution** option in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution even when that solution contains only one project.</span></span> <span data-ttu-id="078c5-106">In caso contrario, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] visualizzerà una soluzione solo se questa contiene più di un progetto.</span><span class="sxs-lookup"><span data-stu-id="078c5-106">Otherwise, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution only when that solution contains more than one project.</span></span> <span data-ttu-id="078c5-107">I progetti aggiuntivi possono essere progetti di [!INCLUDE[ssIS](../includes/ssis-md.md)] o di altri tipi.</span><span class="sxs-lookup"><span data-stu-id="078c5-107">The additional projects can be either [!INCLUDE[ssIS](../includes/ssis-md.md)] projects or projects of other types.</span></span>  
  
## <a name="adding-an-integration-services-project"></a><span data-ttu-id="078c5-108">Aggiunta di un progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="078c5-108">Adding an Integration Services Project</span></span>  
 <span data-ttu-id="078c5-109">È possibile aggiungere un nuovo progetto vuoto tramite [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] oppure aggiungere un progetto già creato per una soluzione diversa.</span><span class="sxs-lookup"><span data-stu-id="078c5-109">When you add a project, you can have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] create a new, blank project, or you can add a project that you have already created for a different solution.</span></span> <span data-ttu-id="078c5-110">È possibile aggiungere un progetto in una soluzione esistente solo se la soluzione è visibile in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="078c5-110">You can only add a project to an existing solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
#### <a name="to-add-a-new-integration-services-project-to-a-solution"></a><span data-ttu-id="078c5-111">Per aggiungere un nuovo progetto di Integration Services a una soluzione</span><span class="sxs-lookup"><span data-stu-id="078c5-111">To add a new Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="078c5-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] aprire la soluzione a cui si vuole aggiungere un nuovo progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="078c5-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="078c5-113">Fare clic con il pulsante destro del mouse sulla soluzione, scegliere **Aggiungi** e quindi fare clic su **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="078c5-113">Right-click the solution, click **Add**, and then click **New Project**.</span></span>  
  
    -   <span data-ttu-id="078c5-114">Scegliere **Aggiungi** dal menu **File** e quindi fare clic su **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="078c5-114">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="078c5-115">Nella finestra di dialogo **Aggiungi nuovo progetto** fare clic su **Progetto di Integration Services** nel riquadro **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="078c5-115">In the **Add New Project** dialog box, click **Integration Services Project** in the **Templates** pane.</span></span>  
  
3.  <span data-ttu-id="078c5-116">È inoltre possibile modificare il nome e il percorso del progetto.</span><span class="sxs-lookup"><span data-stu-id="078c5-116">Optionally, edit the project name and location.</span></span>  
  
4.  <span data-ttu-id="078c5-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="078c5-117">Click **OK**.</span></span>  
  
#### <a name="to-add-an-existing-integration-services-project-to-a-solution"></a><span data-ttu-id="078c5-118">Per aggiungere un progetto di Integration Services esistente a una soluzione</span><span class="sxs-lookup"><span data-stu-id="078c5-118">To add an existing Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="078c5-119">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] aprire la soluzione a cui si desidera aggiungere un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] esistente ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="078c5-119">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="078c5-120">Fare clic con il pulsante destro del mouse sulla soluzione, scegliere **Aggiungi** e quindi fare clic su **Progetto esistente**.</span><span class="sxs-lookup"><span data-stu-id="078c5-120">Right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  
  
    -   <span data-ttu-id="078c5-121">Scegliere **Aggiungi** dal menu **File** e quindi fare clic su **Progetto esistente**.</span><span class="sxs-lookup"><span data-stu-id="078c5-121">On the **File** menu, click **Add**, and then click **Existing Project**.</span></span>  
  
2.  <span data-ttu-id="078c5-122">Nella finestra di dialogo **Aggiungi progetto esistente** usare il pulsante Sfoglia per individuare il progetto da aggiungere e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="078c5-122">In the **Add Existing Project** dialog box, browse to locate the project you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="078c5-123">Il progetto verrà aggiunto alla cartella della soluzione in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="078c5-123">The project is added to the solution folder in **Solution Explorer**.</span></span>  
  
## <a name="removing-an-integration-services-project"></a><span data-ttu-id="078c5-124">Rimozione di un progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="078c5-124">Removing an Integration Services Project</span></span>  
 <span data-ttu-id="078c5-125">È possibile rimuovere un progetto da una soluzione solo se la soluzione è visibile in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="078c5-125">You can only remove a project from a solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="078c5-126">Quando la soluzione è visibile, è possibile rimuovere tutti i progetti tranne uno.</span><span class="sxs-lookup"><span data-stu-id="078c5-126">After the solution is visible, you can remove all except one project.</span></span> <span data-ttu-id="078c5-127">Se rimane un solo progetto, la cartella della soluzione non verrà più visualizzata in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e non sarà possibile rimuovere l'ultimo progetto.</span><span class="sxs-lookup"><span data-stu-id="078c5-127">As soon as only one project remains, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no longer displays the solution folder and you cannot remove the last project.</span></span>  
  
#### <a name="to-remove-an-integration-services-project-from-a-solution"></a><span data-ttu-id="078c5-128">Per rimuovere un progetto di Integration Services da una soluzione</span><span class="sxs-lookup"><span data-stu-id="078c5-128">To remove an Integration Services project from a solution</span></span>  
  
1.  <span data-ttu-id="078c5-129">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] aprire la soluzione da cui si vuole rimuovere un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="078c5-129">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution from which you want to remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="078c5-130">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Scarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="078c5-130">In Solution Explorer, right-click the project, and then click **Unload Project**.</span></span>  
  
3.  <span data-ttu-id="078c5-131">Fare clic su **OK** per confermare la rimozione.</span><span class="sxs-lookup"><span data-stu-id="078c5-131">Click **OK** to confirm the removal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="078c5-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="078c5-132">See Also</span></span>  
 <span data-ttu-id="078c5-133">[Integration Services &#40;progetti SSIS&#41;](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="078c5-133">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="078c5-134">Creare un nuovo progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="078c5-134">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
  
