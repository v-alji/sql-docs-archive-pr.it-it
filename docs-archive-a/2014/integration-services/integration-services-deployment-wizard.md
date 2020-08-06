---
title: Distribuzione guidata Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.deploymentwizard.f1
ms.assetid: f3d93e13-2d85-47ff-a913-cda4046491c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9afdc529baa4546f126eb67456927e770cb345dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721608"
---
# <a name="integration-services-deployment-wizard"></a><span data-ttu-id="edebc-102">Distribuzione guidata Integration Services</span><span class="sxs-lookup"><span data-stu-id="edebc-102">Integration Services Deployment Wizard</span></span>
  <span data-ttu-id="edebc-103">Con la Distribuzione guidata [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] è possibile distribuire progetti nel catalogo SSISDB in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizzando il modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="edebc-103">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard deploys projects to the SSISDB catalog on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance using the project deployment model.</span></span>  
  
 <span data-ttu-id="edebc-104">Per avviare la [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] distribuzione guidata da un progetto aperto in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , selezionare **Distribuisci** dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="edebc-104">To start the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard from an open project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], select **Deploy** from the **Project** menu.</span></span> <span data-ttu-id="edebc-105">Per avviare la procedura guidata [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] in, espandere il nodo SSISDB **cataloghi Integration Services**  >  **SSISDB** in Esplora oggetti, fare clic con il pulsante destro del mouse sulla cartella **progetti** , quindi scegliere **Distribuisci progetto**.</span><span class="sxs-lookup"><span data-stu-id="edebc-105">To start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** > **SSISDB** node in Object Explorer, right-click the **Projects** folder, and then click **Deploy Project**.</span></span>  
  
 <span data-ttu-id="edebc-106">La procedura guidata prevede inoltre i quattro passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="edebc-106">The wizard proceeds through the following four steps.</span></span> <span data-ttu-id="edebc-107">Fare clic su **Avanti** per passare al passaggio successivo o **indietro** per tornare al passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="edebc-107">Click **Next** to move to the next step, or **Previous** to return to the previous step.</span></span>  
  
1.  <span data-ttu-id="edebc-108">**Selezionare l'origine** : selezionare il [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] progetto che si desidera distribuire.</span><span class="sxs-lookup"><span data-stu-id="edebc-108">**Select Source** - Select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that you want to deploy.</span></span>  
  
2.  <span data-ttu-id="edebc-109">**Selezionare destinazione** : selezionare la destinazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="edebc-109">**Select Destination** - Select the project destination.</span></span>  
  
3.  <span data-ttu-id="edebc-110">**Verifica** : consente di visualizzare le selezioni effettuate.</span><span class="sxs-lookup"><span data-stu-id="edebc-110">**Review** - Displays your selections.</span></span>  
  
4.  <span data-ttu-id="edebc-111">**Deploy/results** : distribuisce il progetto e Visualizza i risultati.</span><span class="sxs-lookup"><span data-stu-id="edebc-111">**Deploy/Results** - Deploys the project and displays the results.</span></span>  
  
## <a name="select-source"></a><span data-ttu-id="edebc-112">Selezionare l'origine</span><span class="sxs-lookup"><span data-stu-id="edebc-112">Select Source</span></span>  
 <span data-ttu-id="edebc-113">Per distribuire un file di distribuzione del progetto creato, selezionare **file distribuzione progetto** e immettere il percorso del file con estensione ispac oppure fare clic su **Sfoglia** per trovarlo nella [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="edebc-113">To deploy a project deployment file that you created, select **Project deployment file** and enter the path to the .ispac file or click **Browse** to find it in the [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project folder.</span></span> <span data-ttu-id="edebc-114">Per distribuire un progetto che si trova nel catalogo di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , selezionare **Catalogo di Integration Services**, quindi immettere il nome del server e il percorso del progetto nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="edebc-114">To deploy a project that resides in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, select **Integration Services catalog**, and then enter the server name and the path to the project in the catalog.</span></span>  
  
 <span data-ttu-id="edebc-115">Se si inizia la procedura guidata in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], per impostazione predefinita tramite la procedura guidata viene selezionato il progetto aperto come origine e questo passaggio viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="edebc-115">If you start the wizard in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], then by default the wizard selects the open project as the source and skips this step.</span></span> <span data-ttu-id="edebc-116">Per tornare a questo passaggio e selezionare un'altra origine, fare clic su **indietro** o su **Seleziona origine** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="edebc-116">To return to this step and select a different source, click **Previous** or click **Select Source** in the left pane.</span></span>  
  
## <a name="select-destination"></a><span data-ttu-id="edebc-117">Seleziona destinazione</span><span class="sxs-lookup"><span data-stu-id="edebc-117">Select Destination</span></span>  
 <span data-ttu-id="edebc-118">Per selezionare la cartella di destinazione per il progetto nel catalogo di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , immettere l'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o fare clic su **Sfoglia** per effettuare una selezione da un elenco di server.</span><span class="sxs-lookup"><span data-stu-id="edebc-118">To select the destination folder for the project in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, enter the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance or click **Browse** to select from a list of servers.</span></span> <span data-ttu-id="edebc-119">Immettere il percorso del progetto in SSISDB o fare clic su **Sfoglia** per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="edebc-119">Enter the project path in SSISDB or click **Browse** to select it.</span></span>  
  
 <span data-ttu-id="edebc-120">Se si inizia la procedura guidata in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], per impostazione predefinita tramite la procedura guidata viene selezionata l'istanza del server connessa e viene immesso il percorso al progetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="edebc-120">If you start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], then by default the wizard selects the connected server instance and enters the path to the selected project.</span></span> <span data-ttu-id="edebc-121">È possibile modificare questi valori per distribuire il progetto in un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="edebc-121">You can change these values to deploy the project to a different location.</span></span>  
  
## <a name="review"></a><span data-ttu-id="edebc-122">Verifica</span><span class="sxs-lookup"><span data-stu-id="edebc-122">Review</span></span>  
 <span data-ttu-id="edebc-123">Con la procedura guidata è possibile verificare le impostazioni selezionate prima di distribuire il progetto.</span><span class="sxs-lookup"><span data-stu-id="edebc-123">The wizard allows you to review the settings you have selected before deploying the project.</span></span> <span data-ttu-id="edebc-124">È possibile modificare le selezioni facendo clic su **Indietro**o selezionando un qualsiasi passaggio nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="edebc-124">You can change your selections by clicking **Previous**, or by clicking any of the steps in the left pane.</span></span>  
  
## <a name="deployresults"></a><span data-ttu-id="edebc-125">Distribuisci/Risultati</span><span class="sxs-lookup"><span data-stu-id="edebc-125">Deploy/Results</span></span>  
 <span data-ttu-id="edebc-126">Quando si fa clic su **Distribuisci** nella pagina **Verifica** , il progetto viene distribuito e nella pagina **risultati** viene visualizzato l'esito positivo o negativo di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="edebc-126">When you click **Deploy** from the **Review** page, the project is deployed and the **Results** page displays the success or failure of each action.</span></span> <span data-ttu-id="edebc-127">Se l'azione non viene completata correttamente, fare clic su **Non riuscito** nella colonna **Risultato** per visualizzare una spiegazione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="edebc-127">If the action fails, click the **Failed** in the **Result** column to display an explanation of the error.</span></span> <span data-ttu-id="edebc-128">Fare clic su **Salva report...** per salvare i risultati in un file XML.</span><span class="sxs-lookup"><span data-stu-id="edebc-128">Click **Save Report...** to save the results to an XML file.</span></span>  
  
 <span data-ttu-id="edebc-129">Per uscire dalla procedura guidata, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="edebc-129">Click **Close** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edebc-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edebc-130">See Also</span></span>  
 <span data-ttu-id="edebc-131">[Distribuire progetti nel server Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="edebc-131">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 [<span data-ttu-id="edebc-132">Distribuzione di progetti e pacchetti</span><span class="sxs-lookup"><span data-stu-id="edebc-132">Deployment of Projects and Packages</span></span>](packages/deploy-integration-services-ssis-projects-and-packages.md)  
  
  
