---
title: Sviluppo di un progetto di Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 6e90b016-36a5-415e-9440-a20199fffff0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da648b3b09b25fa2a7b1cf886ad1bf770296f5ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636816"
---
# <a name="development-of-an-integration-services-project"></a><span data-ttu-id="acc82-102">Sviluppo di un progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="acc82-102">Development of an Integration Services Project</span></span>
  <span data-ttu-id="acc82-103">Si aggiungono pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ai progetti.</span><span class="sxs-lookup"><span data-stu-id="acc82-103">You add [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to projects.</span></span> <span data-ttu-id="acc82-104">Per creare e usare progetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , è necessario installare l'ambiente [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="acc82-104">To create and work with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects, you must install the [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] environment.</span></span> <span data-ttu-id="acc82-105">Per altre informazioni, vedere [Installazione di Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="acc82-105">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
 <span data-ttu-id="acc82-106">Quando si crea un nuovo progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], nella finestra di dialogo **Nuovo progetto** è incluso un modello **Progetto di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="acc82-106">When you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the **New Project** dialog box includes an **Integration Services Project** template.</span></span> <span data-ttu-id="acc82-107">Questo modello consente di creare un nuovo progetto che contiene un singolo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="acc82-107">This project template creates a new project that contains a single package.</span></span>  
  
## <a name="projects-and-solutions"></a><span data-ttu-id="acc82-108">Progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="acc82-108">Projects and Solutions</span></span>  
 <span data-ttu-id="acc82-109">I progetti vengono archiviati in soluzioni.</span><span class="sxs-lookup"><span data-stu-id="acc82-109">Projects are stored in solutions.</span></span> <span data-ttu-id="acc82-110">È possibile creare una soluzione e quindi aggiungervi un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="acc82-110">You can create a solution first and then add an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the solution.</span></span> <span data-ttu-id="acc82-111">Se non esiste alcuna soluzione, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ne creerà automaticamente una al momento della creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="acc82-111">If no solution exists, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] automatically creates one for you when you first create the project.</span></span> <span data-ttu-id="acc82-112">Una soluzione può contenere più progetti di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="acc82-112">A solution can contain multiple projects of different types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="acc82-113">Per impostazione predefinita, quando si crea un nuovo progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], la soluzione non viene visualizzata nel riquadro **Esplora soluzioni** .</span><span class="sxs-lookup"><span data-stu-id="acc82-113">By default, when you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the solution is not shown in the **Solution Explorer** pane.</span></span> <span data-ttu-id="acc82-114">Per modificare questo comportamento predefinito, scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="acc82-114">To change this default behavior, on the **Tools** menus, click **Options**.</span></span> <span data-ttu-id="acc82-115">Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**e quindi fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="acc82-115">In the **Options** dialog box, expand **Projects and Solutions**, and then click **General**.</span></span> <span data-ttu-id="acc82-116">Nella pagina **Generale** selezionare **Mostra sempre soluzione**.</span><span class="sxs-lookup"><span data-stu-id="acc82-116">On the **General** page, select **Always show solution**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="acc82-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="acc82-117">Related Tasks</span></span>  
  
-   [<span data-ttu-id="acc82-118">Creare un nuovo progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="acc82-118">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="acc82-119">Aggiunta di un elemento a un progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="acc82-119">Add an Item to an Integration Services Project</span></span>](../../2014/integration-services/add-an-item-to-an-integration-services-project.md)  
  
-   [<span data-ttu-id="acc82-120">Aggiunta o rimozione di un progetto di Integration Services da una soluzione</span><span class="sxs-lookup"><span data-stu-id="acc82-120">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
