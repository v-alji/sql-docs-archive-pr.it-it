---
title: 'Lezione 14: distribuire | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 24863a8a-9017-415a-a97b-fbac76ed0675
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1a55960a0c33a386d978f3c15e489ed7bd861ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623540"
---
# <a name="lesson-14-deploy"></a><span data-ttu-id="b6af5-102">Lezione 14: Distribuire</span><span class="sxs-lookup"><span data-stu-id="b6af5-102">Lesson 14: Deploy</span></span>
  <span data-ttu-id="b6af5-103">In questa lezione verranno configurate proprietà di distribuzione, specificando un'istanza del server di distribuzione di Analysis Services in esecuzione in modalità tabulare e un nome per il modello distribuito.</span><span class="sxs-lookup"><span data-stu-id="b6af5-103">In this lesson, you will configure deployment properties; specifying a deployment server instance of Analysis Services running in Tabular mode, and a name for the model you deploy.</span></span> <span data-ttu-id="b6af5-104">Si distribuirà quindi il modello nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b6af5-104">You will then deploy the model to that instance.</span></span> <span data-ttu-id="b6af5-105">Dopo la distribuzione, gli utenti possono connettersi al modello utilizzando un'applicazione client di creazione di report.</span><span class="sxs-lookup"><span data-stu-id="b6af5-105">After it is deployed, users can connect to the model by using a reporting client application.</span></span> <span data-ttu-id="b6af5-106">Per altre informazioni, vedere [Distribuzione di una soluzione del modello tabulare &#40;SSAS tabulare&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b6af5-106">To learn more, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="b6af5-107">Tempo stimato per il completamento della lezione: **5 minuti**</span><span class="sxs-lookup"><span data-stu-id="b6af5-107">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b6af5-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b6af5-108">Prerequisites</span></span>  
 <span data-ttu-id="b6af5-109">Questo argomento fa parte di un'esercitazione sulla creazione di modelli tabulari, con lezioni che è consigliabile completare nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="b6af5-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="b6af5-110">Prima di eseguire le attività in questa lezione è necessario aver completato la lezione precedente: [Lezione 13: Analizza in Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="b6af5-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
## <a name="deploy-the-model"></a><span data-ttu-id="b6af5-111">Distribuire il modello</span><span class="sxs-lookup"><span data-stu-id="b6af5-111">Deploy the Model</span></span>  
  
#### <a name="to-configure-deployment-properties"></a><span data-ttu-id="b6af5-112">Per configurare le proprietà di distribuzione</span><span class="sxs-lookup"><span data-stu-id="b6af5-112">To configure deployment properties</span></span>  
  
1.  <span data-ttu-id="b6af5-113">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **Adventure Works Internet Sales Tabular Model** e scegliere **Proprietà**dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b6af5-113">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click on the **Adventure Works Internet Sales Tabular Model** project, and then in the context menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b6af5-114">Nella finestra di dialogo **Deployment Tutorial Property Pages** (Pagine delle proprietà di Deployment Tutorial), in **Server di distribuzione**digitare il nome dell'istanza di Analysis Services in esecuzione in modalità tabulare nella proprietà **Server** .</span><span class="sxs-lookup"><span data-stu-id="b6af5-114">In the **AW Internet Sales Tabular Model Property Pages** dialog box, under **Deployment Server**, in the **Server** property, type the name of an Analysis Services instance running in Tabular mode.</span></span> <span data-ttu-id="b6af5-115">Si tratta dell'istanza in cui verrà distribuito il modello.</span><span class="sxs-lookup"><span data-stu-id="b6af5-115">This will be the instance your model will be deployed to.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b6af5-116">Per eseguire la distribuzione in un'istanza remota di Analysis Services, è necessario disporre delle autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b6af5-116">You must have Administrator permissions on a remote Analysis Services instance in-order to deploy to it.</span></span>  
  
3.  <span data-ttu-id="b6af5-117">Verificare che la proprietà **modalità query** sia impostata su **in-Memory**.</span><span class="sxs-lookup"><span data-stu-id="b6af5-117">Verify the **Query Mode** property is set to **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b6af5-118">Il modello creato tramite questa esercitazione non è supportato in modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b6af5-118">The model created by using this tutorial is not supported in DirectQuery mode.</span></span>  
  
4.  <span data-ttu-id="b6af5-119">Nella proprietà **database** Digitare `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="b6af5-119">In the **Database** property, type `Adventure Works Internet Sales Model`.</span></span>  
  
5.  <span data-ttu-id="b6af5-120">Nella proprietà nome **cubo** Digitare `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="b6af5-120">In the **Cube** Name property, type `Adventure Works Internet Sales Model`.</span></span>  
  
6.  <span data-ttu-id="b6af5-121">Verificare le selezioni e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6af5-121">Verify your selections and then click **OK**.</span></span>  
  
#### <a name="to-deploy-the-adventure-works-internet-sales-tabular-model"></a><span data-ttu-id="b6af5-122">Per distribuire il modello tabulare Adventure Works Internet Sales</span><span class="sxs-lookup"><span data-stu-id="b6af5-122">To deploy the Adventure Works Internet Sales tabular model</span></span>  
  
1.  <span data-ttu-id="b6af5-123">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]scegliere **Deploy AW Internet Sales Tabular Model** (Distribuisci AW Internet Sales Tabular Model) dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="b6af5-123">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Build** menu, and then click **Deploy AW Internet Sales Tabular Model**.</span></span>  
  
     <span data-ttu-id="b6af5-124">Verrà visualizzata la finestra di dialogo Distribuisci in cui sono indicati lo stato della distribuzione e ogni tabella inclusa nel modello.</span><span class="sxs-lookup"><span data-stu-id="b6af5-124">The Deploy dialog box appears and displays the deployment status of the metadata as well as each table included in the model.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="b6af5-125">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="b6af5-125">Conclusion</span></span>  
 <span data-ttu-id="b6af5-126">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b6af5-126">Congratulations!</span></span> <span data-ttu-id="b6af5-127">La procedura di creazione e distribuzione del primo modello tabulare di Analysis Services è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b6af5-127">You are finished authoring and deploying your first Analysis Services tabular model.</span></span> <span data-ttu-id="b6af5-128">In questa esercitazione sono state descritte le procedure per eseguire in modo guidato la maggior parte delle attività più comuni per la creazione di un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="b6af5-128">This tutorial has helped guide you through completing the most common tasks in creating a tabular model.</span></span> <span data-ttu-id="b6af5-129">Ora che il modello Adventure Works Internet Sales è stato distribuito, è possibile utilizzare SQL Server Management Studio per gestire il modello, nonché creare script di processo e un piano di backup.</span><span class="sxs-lookup"><span data-stu-id="b6af5-129">Now that your Adventure Works Internet Sales Model is deployed, you can use SQL Server Management Studio to manage the model; create process scripts and a backup plan.</span></span> <span data-ttu-id="b6af5-130">Gli utenti possono connettersi al modello utilizzando un'applicazione client di creazione report, ad esempio Microsoft Excel o [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6af5-130">Users can connect to the model using a reporting client application such as Microsoft Excel or [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="b6af5-131">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b6af5-131">Additional Resources</span></span>  
 <span data-ttu-id="b6af5-132">Per altre informazioni sulle proprietà dei modelli tabulari che supportano i report [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)], vedere [Proprietà report Power View &#40;SSAS tabulare&#41;](tabular-models/properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b6af5-132">To learn more about tabular model properties that support [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)] reports, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](tabular-models/properties-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6af5-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6af5-133">See Also</span></span>  
 <span data-ttu-id="b6af5-134">[Modalità DirectQuery &#40;SSAS tabulare&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b6af5-134">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 <span data-ttu-id="b6af5-135">[Configurare la modellazione dei dati e le proprietà di distribuzione predefinite &#40;SSAS tabulare&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b6af5-135">[Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b6af5-136">Database modello tabulare &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="b6af5-136">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-models/tabular-model-databases-ssas-tabular.md)  
  
  
