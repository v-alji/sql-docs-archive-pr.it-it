---
title: 'Passaggio 2: Creazione del progetto di distribuzione | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 59990fe2-7036-4e9c-8efc-6ece9e66eda7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebfce8796f98628c2832c5ab7f4be665c7915d10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628846"
---
# <a name="step-2-creating-the-deployment-project"></a><span data-ttu-id="002f8-102">Passaggio 2: Creazione del progetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="002f8-102">Step 2: Creating the Deployment Project</span></span>
  <span data-ttu-id="002f8-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]l'unità distribuibile è rappresentata da un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="002f8-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the deployable unit is an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="002f8-104">Per poter distribuire i pacchetti, è necessario creare un nuovo progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e aggiungervi tutti i pacchetti e gli eventuali file ausiliari che di desidera distribuire unitamente ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="002f8-104">Before you can deploy packages, you must create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and add all the packages and any ancillary files that you want to deploy with the packages to that project.</span></span>  
  
### <a name="to-create-the-integration-services-project"></a><span data-ttu-id="002f8-105">Per creare il progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="002f8-105">To create the Integration Services project</span></span>  
  
1.  <span data-ttu-id="002f8-106">Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server**e quindi fare clic su **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="002f8-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL ServerSQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="002f8-107">Dal menu **File** scegliere **Nuovo**e quindi **Progetto** per creare un nuovo progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="002f8-107">On the **File** menu, point to **New**, and then click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="002f8-108">Nella finestra di dialogo **Nuovo progetto** selezionare **Progetto di Integration Services** nel riquadro **Modelli** .</span><span class="sxs-lookup"><span data-stu-id="002f8-108">In the **New Project** dialog box, select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="002f8-109">Nella casella **Nome** modificare il nome predefinito in **Deployment Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="002f8-109">In the **Name** box, change the default name to **Deployment Tutorial**.</span></span> <span data-ttu-id="002f8-110">Facoltativamente, deselezionare la casella di controllo **Crea directory per soluzione** .</span><span class="sxs-lookup"><span data-stu-id="002f8-110">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="002f8-111">Accettare il percorso predefinito o fare clic su **Sfoglia** per trovare la cartella che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="002f8-111">Accept the default location, or click **Browse** to locate the folder you want to use.</span></span>  
  
6.  <span data-ttu-id="002f8-112">Nella finestra di dialogo **Percorso progetto** fare clic sulla cartella e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="002f8-112">In the **Project Location** dialog box, click the folder, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="002f8-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="002f8-113">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="002f8-114">Per impostazione predefinita, viene creato e aggiunto al progetto un pacchetto vuoto denominato Package.dtsx.</span><span class="sxs-lookup"><span data-stu-id="002f8-114">By default, an empty package, named Package.dtsx, is created and added to your project.</span></span> <span data-ttu-id="002f8-115">Questo pacchetto non verrà tuttavia utilizzato. Al progetto verranno infatti aggiunti i pacchetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="002f8-115">However, you will not use this package; instead, you will add existing packages to the project.</span></span> <span data-ttu-id="002f8-116">Poiché nella distribuzione vengono inclusi tutti i pacchetti del progetto, è consigliabile eliminare Package.dtsx.</span><span class="sxs-lookup"><span data-stu-id="002f8-116">Because all the packages in a project will be included in the deployment, you should delete Package.dtsx.</span></span> <span data-ttu-id="002f8-117">A tale scopo, fare clic con il pulsante destro del mouse su di esso e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="002f8-117">To delete it, right-click it, and then click **Delete**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="002f8-118">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="002f8-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="002f8-119">Passaggio 3: Aggiunta di pacchetti e altri file</span><span class="sxs-lookup"><span data-stu-id="002f8-119">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
<span data-ttu-id="002f8-120">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="002f8-120">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="002f8-121">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="002f8-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="002f8-122">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="002f8-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="002f8-123">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="002f8-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002f8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="002f8-124">See Also</span></span>  
 [<span data-ttu-id="002f8-125">Progetti di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="002f8-125">Integration Services &#40;SSIS&#41; Projects</span></span>](integration-services-ssis-projects-and-solutions.md)  
  
  
