---
title: "Passaggio 1: Compilazione dell'utilità di distribuzione | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1ff4dcff-89b3-4b99-a725-5f7963e98abf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3d32dcbf4bfcf9758dfe58803b75094d1807aa90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628818"
---
# <a name="step-1-building-the-deployment-utility"></a><span data-ttu-id="7e471-102">Passaggio 1: Compilazione dell'utilità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="7e471-102">Step 1: Building the Deployment Utility</span></span>
  <span data-ttu-id="7e471-103">In questa attività verrà configurata e compilata un'utilità di distribuzione per il progetto Deployment Tutorial.</span><span class="sxs-lookup"><span data-stu-id="7e471-103">In this task, you will configure and build a deployment utility for the Deployment Tutorial project.</span></span>  
  
 <span data-ttu-id="7e471-104">Per poter compilare l'utilità di distribuzione, è necessario modificare le proprietà del progetto Deployment Tutorial.</span><span class="sxs-lookup"><span data-stu-id="7e471-104">Before you can build the deployment utility, you must modify the properties of the Deployment Tutorial project.</span></span> <span data-ttu-id="7e471-105">Verrà usata la finestra di dialogo **Deployment Tutorial Property Pages** (Pagine delle proprietà di Deployment Tutorial) per configurare queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="7e471-105">You will use the **Deployment Tutorial Property Pages** dialog box to configure these properties.</span></span> <span data-ttu-id="7e471-106">In questa finestra di dialogo è necessario abilitare la funzionalità di aggiornamento delle configurazioni durante la distribuzione e specificare il processo di compilazione che consente di generare l'utilità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7e471-106">In this dialog box, you must enable the ability to update configurations during deployment and specify that the build process generates a deployment utility.</span></span> <span data-ttu-id="7e471-107">Al termine dell'impostazione delle proprietà, il progetto verrà compilato.</span><span class="sxs-lookup"><span data-stu-id="7e471-107">After you set the properties, you will build the project.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="7e471-108">include un set di finestre che consentono di eseguire il debug dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7e471-108">provides a set of windows that you can use to debug packages.</span></span> <span data-ttu-id="7e471-109">È possibile visualizzare messaggi di errore, avviso e informativi, tenere traccia dello stato dei pacchetti in fase di esecuzione oppure visualizzare lo stato e i risultati dei processi di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7e471-109">You can view error, warning, and information messages, track about the status of packages at run time, or view the progress and results of build processes.</span></span> <span data-ttu-id="7e471-110">Per questa lezione, si utilizzerà la finestra Output per visualizzare lo stato e i risultati della compilazione dell'utilità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7e471-110">For this lesson, you will use the Output window to view the progress and results of building the deployment utility.</span></span>  
  
### <a name="to-set-the-deployment-utility-properties"></a><span data-ttu-id="7e471-111">Per impostare le proprietà dell'utilità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="7e471-111">To set the deployment utility properties</span></span>  
  
1.  <span data-ttu-id="7e471-112">Se [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] non è già aperto, fare clic sul pulsante **Start**, scegliere **Programmi**, **Microsoft SQL Server**selezionare **Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="7e471-112">If [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="7e471-113">Scegliere **Apri** dal menu **File**, fare clic su **Progetto/Soluzione**, selezionare la cartella **Deployment Tutorial** , fare clic su **Apri**e fare doppio clic su **Deployment Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="7e471-113">On the **File** menu, click **Open**, click **Project/Solution**, click the **Deployment Tutorial** folder and click **Open**, and then double-click **Deployment Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="7e471-114">In Esplora soluzioni fare clic con il pulsante destro del mouse su Deployment Tutorial e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7e471-114">In Solution Explorer, right-click Deployment Tutorial and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7e471-115">Nella finestra di dialogo **Deployment Tutorial Property Pages** (Pagine delle proprietà di Deployment Tutorial) espandere le proprietà di configurazione e fare clic su Utilità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7e471-115">In the **Deployment Tutorial Property Pages** dialog box, expand Configuration Properties, and click Deployment Utility.</span></span>  
  
5.  <span data-ttu-id="7e471-116">Nel riquadro destro della finestra di dialogo **pagine delle proprietà di Deployment Tutorial** verificare che `AllowConfigurationChanges` sia impostato su `true` , impostare `CreateDeploymentUtility` su `true` e, facoltativamente, aggiornare il valore predefinito di `DeploymentOutputPath` .</span><span class="sxs-lookup"><span data-stu-id="7e471-116">In the right pane of the **Deployment Tutorial Property Pages** dialog box, verify that `AllowConfigurationChanges` is set to `true`, set `CreateDeploymentUtility` to `true`, and optionally update the default value of `DeploymentOutputPath`.</span></span>  
  
6.  <span data-ttu-id="7e471-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e471-117">Click **OK**.</span></span>  
  
### <a name="to-build-the-deployment-utility"></a><span data-ttu-id="7e471-118">Per compilare l'utilità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="7e471-118">To build the deployment utility</span></span>  
  
1.  <span data-ttu-id="7e471-119">In Esplora soluzioni fare clic su **Deployment Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="7e471-119">In Solution Explorer, click **Deployment Tutorial**.</span></span>  
  
2.  <span data-ttu-id="7e471-120">Scegliere **Output** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="7e471-120">On the **View** menu, click **Output**.</span></span> <span data-ttu-id="7e471-121">Per impostazione predefinita, la finestra Output si trova nell'angolo inferiore sinistro di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e471-121">By default, the Output window is located in the bottom left corner of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="7e471-122">Scegliere **Build Deployment Tutorial** (Compila Deployment Tutorial) dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="7e471-122">On the **Build** menu, click **Build Deployment Tutorial**.</span></span>  
  
4.  <span data-ttu-id="7e471-123">Nella finestra Output verificare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e471-123">In the Output window, verify the following information:</span></span>  
  
     <span data-ttu-id="7e471-124">Compilazione avviata - Progetto SQL Integration Services: Incrementale ...</span><span class="sxs-lookup"><span data-stu-id="7e471-124">Build started: SQL Integration Services project: Incremental ...</span></span>  
  
     <span data-ttu-id="7e471-125">Creazione dell'utilità di distribuzione in corso...</span><span class="sxs-lookup"><span data-stu-id="7e471-125">Creating deployment utility...</span></span>  
  
     <span data-ttu-id="7e471-126">Utilità di distribuzione creata.</span><span class="sxs-lookup"><span data-stu-id="7e471-126">Deployment Utility created.</span></span>  
  
     <span data-ttu-id="7e471-127">Compilazione completata -- 0 errori, 0 avvisi</span><span class="sxs-lookup"><span data-stu-id="7e471-127">Build complete -- 0 errors, 0 warnings</span></span>  
  
     <span data-ttu-id="7e471-128">========== Compilazione: 0 completate, 0 non riuscite, 1 aggiornate, 0 ignorate ==========</span><span class="sxs-lookup"><span data-stu-id="7e471-128">========== Build: 0 succeeded, 0 failed, 1 up-to-date, 0 skipped ==========</span></span>  
  
5.  <span data-ttu-id="7e471-129">Scegliere **Esci** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="7e471-129">On the **File** menu, click **Exit**.</span></span> <span data-ttu-id="7e471-130">Se richiesto per salvare le modifiche agli elementi di Deployment Tutorial, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="7e471-130">If prompted to save changes to Deployment Tutorial items, click **Yes**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7e471-131">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="7e471-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7e471-132">Passaggio 2: Verifica del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="7e471-132">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
<span data-ttu-id="7e471-133">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="7e471-133">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="7e471-134">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="7e471-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="7e471-135">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="7e471-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="7e471-136">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="7e471-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e471-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e471-137">See Also</span></span>  
 [<span data-ttu-id="7e471-138">Creazione di un'utilità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="7e471-138">Create a Deployment Utility</span></span>](../../2014/integration-services/create-a-deployment-utility.md)  
  
  
