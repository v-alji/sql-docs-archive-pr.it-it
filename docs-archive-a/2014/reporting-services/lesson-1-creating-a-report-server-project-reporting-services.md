---
title: 'Lesson 1: Creating a Report Server Project (Reporting Services) (Lezione 1: Creazione di un progetto server report (Reporting Services)) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 675671ca-e6c9-48a2-82e9-386778f3a49f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a708e5114344e87edd620ef58bc50594a9b9ef8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726595"
---
# <a name="lesson-1-creating-a-report-server-project-reporting-services"></a><span data-ttu-id="e678e-102">Lezione 1: Creazione di un progetto server report (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="e678e-102">Lesson 1: Creating a Report Server Project (Reporting Services)</span></span>
  <span data-ttu-id="e678e-103">Per creare un report in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], è innanzitutto necessario creare un progetto server di report in cui verranno salvati il file della definizione del report (con estensione rdl) e altri file di risorse necessari per il report.</span><span class="sxs-lookup"><span data-stu-id="e678e-103">To create a report in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you must first create a report server project where you will save your report definition (.rdl) file and any other resource files that you need for your report.</span></span> <span data-ttu-id="e678e-104">Verrà quindi creato il file della definizione del report, verranno definiti un'origine dei dati per il report, un set di dati e il layout del report.</span><span class="sxs-lookup"><span data-stu-id="e678e-104">Then you will create the actual report definition file, define a data source for your report, define a dataset, and define the report layout.</span></span> <span data-ttu-id="e678e-105">Quando si esegue il report, i dati effettivi vengono recuperati e combinati con il layout, e quindi visualizzati sullo schermo. Sarà quindi possibile esportarli, stamparli o salvarli.</span><span class="sxs-lookup"><span data-stu-id="e678e-105">When you run the report, the actual data is retrieved and combined with the layout, and then rendered on your screen, from where you can export it, print it, or save it.</span></span>  
  
 <span data-ttu-id="e678e-106">In questa lezione verranno descritte le procedure per creare il progetto server di report in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e678e-106">In this lesson, you will learn how to create a report server project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="e678e-107">Un progetto server di report consente di creare report che vengono eseguiti in un server di report.</span><span class="sxs-lookup"><span data-stu-id="e678e-107">A report server project is used to create reports that run on a report server.</span></span>  
  
### <a name="to-create-a-report-server-project"></a><span data-ttu-id="e678e-108">Per creare un progetto server di report</span><span class="sxs-lookup"><span data-stu-id="e678e-108">To create a report server project</span></span>  
  
1.  <span data-ttu-id="e678e-109">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] , quindi fare clic su **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="e678e-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)], and then click **SQL Server Data Tools**.</span></span> <span data-ttu-id="e678e-110">Se è la prima volta che si apre [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , fare clic su **impostazioni di business intelligence** per le impostazioni di ambiente predefinite.</span><span class="sxs-lookup"><span data-stu-id="e678e-110">If this is the first time you have opened [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Business Intelligence Settings** for the default environment settings.</span></span>  
  
2.  <span data-ttu-id="e678e-111">Scegliere **Nuovo** dal menu **File**e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e678e-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="e678e-112">Nell'elenco **Modelli installati** fare clic su **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="e678e-112">In the **Installed Templates** list, click **Business Intelligence**.</span></span>  
  
4.  <span data-ttu-id="e678e-113">Fare clic su **progetto server report**.</span><span class="sxs-lookup"><span data-stu-id="e678e-113">Click **Report Server Project**.</span></span>  
  
5.  <span data-ttu-id="e678e-114">In **Nome**digitare **Esercitazione**.</span><span class="sxs-lookup"><span data-stu-id="e678e-114">In **Name**, type **Tutorial**.</span></span>  
  
6.  <span data-ttu-id="e678e-115">Fare clic su **OK** per creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="e678e-115">Click **OK** to create the project.</span></span>  
  
     <span data-ttu-id="e678e-116">In Esplora soluzioni verrà visualizzato il progetto Esercitazione.</span><span class="sxs-lookup"><span data-stu-id="e678e-116">The Tutorial project is displayed in Solution Explorer.</span></span>  
  
### <a name="to-create-a-new-report-definition-file"></a><span data-ttu-id="e678e-117">Per creare un nuovo file di definizione del report</span><span class="sxs-lookup"><span data-stu-id="e678e-117">To create a new report definition file</span></span>  
  
1.  <span data-ttu-id="e678e-118">In Esplora soluzioni fare clic con il pulsante destro del mouse su **report**, scegliere **Aggiungi**, quindi fare clic su **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e678e-118">In Solution Explorer, right-click **Reports**, point to **Add**, and click **New Item**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e678e-119">Se la finestra **Esplora soluzioni** non è visualizzata, scegliere **Esplora soluzioni** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="e678e-119">If the **Solution Explorer** window is not visible, from the **View** menu, click **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="e678e-120">Nella finestra di dialogo **Aggiungi nuovo elemento** , in **modelli**, fare clic su **report**.</span><span class="sxs-lookup"><span data-stu-id="e678e-120">In the **Add New Item** dialog box, under **Templates**, click **Report**.</span></span>  
  
3.  <span data-ttu-id="e678e-121">Digitare **Sales Orders.rdl**in **Nome** , quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e678e-121">In **Name**, type **Sales Orders.rdl** and then click **Add**.</span></span>  
  
     <span data-ttu-id="e678e-122">Verranno visualizzati Progettazione report e il nuovo file con estensione rdl nella visualizzazione Progettazione.</span><span class="sxs-lookup"><span data-stu-id="e678e-122">Report Designer opens and displays the new .rdl file in Design view.</span></span>  
  
 <span data-ttu-id="e678e-123">Progettazione report è il componente di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] eseguito in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e678e-123">Report Designer is a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] component that runs in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="e678e-124">e ha due viste: **Progettazione** e **Anteprima**.</span><span class="sxs-lookup"><span data-stu-id="e678e-124">It has two views: **Design** and **Preview**.</span></span> <span data-ttu-id="e678e-125">Fare clic sulla scheda corrispondente per cambiare la vista.</span><span class="sxs-lookup"><span data-stu-id="e678e-125">Click each tab to change views.</span></span>  
  
 <span data-ttu-id="e678e-126">I dati vengono definiti nel riquadro **Dati report** .</span><span class="sxs-lookup"><span data-stu-id="e678e-126">You define your data in the **Report Data** pane.</span></span> <span data-ttu-id="e678e-127">Il layout dei report viene definito nella vista **Progettazione** .</span><span class="sxs-lookup"><span data-stu-id="e678e-127">You define your report layout in **Design** view.</span></span> <span data-ttu-id="e678e-128">Dopo aver eseguito il report, è possibile vederne l'aspetto nella vista **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="e678e-128">You can run the report and see what it looks like in **Preview** view.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="e678e-129">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="e678e-129">Next Task</span></span>  
 <span data-ttu-id="e678e-130">In questo modo è stato creato un progetto di report denominato Esercitazione, cui è stato aggiunto un file di definizione del report (con estensione rdl).</span><span class="sxs-lookup"><span data-stu-id="e678e-130">You have successfully created a report project called "Tutorial" and added a report definition (.rdl) file to the report project.</span></span> <span data-ttu-id="e678e-131">Il passaggio successivo consiste nello specificare un'origine dei dati per il report.</span><span class="sxs-lookup"><span data-stu-id="e678e-131">Next, you will specify a data source to use for the report.</span></span> <span data-ttu-id="e678e-132">Vedere [Lezione 2: Specifica delle informazioni di connessione &#40;Reporting Services&#41;](lesson-2-specifying-connection-information-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="e678e-132">See [Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;](lesson-2-specifying-connection-information-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e678e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e678e-133">See Also</span></span>  
 [<span data-ttu-id="e678e-134">Creare un report tabella semplice &#40;esercitazione su SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e678e-134">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
