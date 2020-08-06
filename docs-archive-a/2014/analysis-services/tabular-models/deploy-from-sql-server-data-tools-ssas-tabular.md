---
title: Eseguire la distribuzione da SQL Server Data Tools (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.deploystatus.f1
ms.assetid: 67dde3fe-ba43-41f3-b56c-c656029ee93f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8bc8008e7c79e1652b54b21e6afb116301d1700b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629625"
---
# <a name="deploy-from-sql-server-data-tools-ssas-tabular"></a><span data-ttu-id="fa1e5-102">Distribuire da SQL Server Data Tools (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="fa1e5-102">Deploy From SQL Server Data Tools (SSAS Tabular)</span></span>
  <span data-ttu-id="fa1e5-103">Utilizzare le attività contenute in questo argomento per distribuire una soluzione del modello tabulare utilizzando il comando Distribuisci in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa1e5-103">Use the tasks in this topic to deploy a tabular model solution by using the Deploy command in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="fa1e5-104">Sezioni dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="fa1e5-104">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="fa1e5-105">Configurare le proprietà opzioni di distribuzione e server di distribuzione</span><span class="sxs-lookup"><span data-stu-id="fa1e5-105">Configure Deployment Options and Deployment Server Properties</span></span>](#bkmk_deploy)  
  
-   [<span data-ttu-id="fa1e5-106">Distribuire una soluzione del modello tabulare</span><span class="sxs-lookup"><span data-stu-id="fa1e5-106">Deploy a Tabular Model Solution</span></span>](#bkmk_deploy_proc)  
  
-   [<span data-ttu-id="fa1e5-107">Stato distribuzione</span><span class="sxs-lookup"><span data-stu-id="fa1e5-107">Deploy Status</span></span>](#bkmk_deploy_status)  
  
##  <a name="configure-deployment-options-and-deployment-server-properties"></a><a name="bkmk_deploy"></a><span data-ttu-id="fa1e5-108">Configurare le proprietà opzioni di distribuzione e server di distribuzione</span><span class="sxs-lookup"><span data-stu-id="fa1e5-108">Configure Deployment Options and Deployment Server Properties</span></span>  
 <span data-ttu-id="fa1e5-109">Prima di distribuire tale soluzione, è necessario innanzitutto specificare le proprietà Opzioni di distribuzione e Server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-109">Before you deploy your tabular model solution, you must first specify the Deployment Options and Deployment Server properties.</span></span> <span data-ttu-id="fa1e5-110">Per altre informazioni sulle impostazioni e le proprietà di distribuzione, vedere [Distribuzione di una soluzione del modello tabulare &#40;SSAS tabulare&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="fa1e5-110">For more information about deployment properties and settings, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
#### <a name="to-configure-deployment-options-and-deployment-server-properties"></a><span data-ttu-id="fa1e5-111">Per configurare le proprietà Opzioni di distribuzione e Server di distribuzione</span><span class="sxs-lookup"><span data-stu-id="fa1e5-111">To configure Deployment Options and Deployment Server properties</span></span>  
  
1.  <span data-ttu-id="fa1e5-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]Esplora soluzioni **di**fare clic con il pulsante destro del mouse sul nome del progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fa1e5-113">In **Opzioni di distribuzione**della finestra di dialogo \*\* \<project name> Proprietà\*\* specificare le impostazioni delle proprietà se diverse dalle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-113">In the **\<project name> Properties** dialog, in **Deployment Options**, specify property settings if different from the default settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fa1e5-114">Per i modelli in modalità cache, in corrispondenza di **Modalità query** è sempre selezionata l'opzione **In-Memory**.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-114">For models in cached mode, **Query Mode** is always **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fa1e5-115">Non è possibile specificare **Impostazioni di rappresentazione** per i modelli in modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-115">You cannot specify **Impersonation Settings** for models in DirectQuery mode.</span></span>  
  
3.  <span data-ttu-id="fa1e5-116">In **Server di distribuzione**specificare le impostazioni delle proprietà **Server** (nome), **Edizione**, **Database** (nome) e **Nome cubo** , se diverse dalle impostazioni predefinite, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-116">In **Deployment Server**, specify the **Server** (name), **Edition**, **Database** (name), and **Cube Name** property settings, if different from the default settings, and then click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa1e5-117">È inoltre possibile specificare l'impostazione della proprietà Server di distribuzione predefinito in modo che tutti i nuovi progetti creati vengano distribuiti automaticamente nel server specificato.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-117">You can also specify the Default Deployment Server property setting so any new projects you create will automatically be deployed to the specified server.</span></span> <span data-ttu-id="fa1e5-118">Per altre informazioni, vedere [Configurare la modellazione dei dati e le proprietà di distribuzione predefinite &#40;SSAS tabulare&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="fa1e5-118">For more information, see [Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
##  <a name="deploy-a-tabular-model-solution"></a><a name="bkmk_deploy_proc"></a><span data-ttu-id="fa1e5-119">Distribuire una soluzione di modello tabulare</span><span class="sxs-lookup"><span data-stu-id="fa1e5-119">Deploy a Tabular Model Solution</span></span>  
  
#### <a name="to-deploy-a-tabular-model-solution"></a><span data-ttu-id="fa1e5-120">Per distribuire una soluzione del modello tabulare</span><span class="sxs-lookup"><span data-stu-id="fa1e5-120">To deploy a tabular model solution</span></span>  
  
-   <span data-ttu-id="fa1e5-121">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] scegliere \*\*Distribuisci \<project name> \*\*dal menu **Compila** .</span><span class="sxs-lookup"><span data-stu-id="fa1e5-121">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **Build** menu, click **Deploy \<project name>**.</span></span>  
  
     <span data-ttu-id="fa1e5-122">Verrà visualizzata la finestra di dialogo **Distribuisci** e verrà fornita l'indicazione dello stato della distribuzione dei metadati e dell'elaborazione di ogni tabella inclusa nel modello, a meno che la proprietà Opzione di elaborazione non sia impostata su Non elaborare.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-122">The **Deploy** dialog box will appear and indicate the status of the metadata deployment and the processing (unless Processing Option property is set to Do Not Process) of each table included in the model.</span></span> <span data-ttu-id="fa1e5-123">Una volta completato il processo di distribuzione, utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per connettersi all'istanza di Analysis Services e verificare il nuovo oggetto di database modello creato. In alternativa, utilizzare un'applicazione client di creazione report per connettersi al modello distribuito.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-123">After the deployment process is complete, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to connect to the Analysis Services instance and verify the new model database object has been created or use a client reporting application to connect to the deployed model.</span></span>  
  
##  <a name="deploy-status"></a><a name="bkmk_deploy_status"></a><span data-ttu-id="fa1e5-124">Stato distribuzione</span><span class="sxs-lookup"><span data-stu-id="fa1e5-124">Deploy Status</span></span>  
 <span data-ttu-id="fa1e5-125">La finestra di dialogo **Distribuisci** consente di monitorare lo stato di un'operazione di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-125">The **Deploy** dialog box enables you to monitor the progress of a Deploy operation.</span></span> <span data-ttu-id="fa1e5-126">Inoltre è possibile arrestare un'operazione di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-126">A deploy operation can also be stopped.</span></span>  
  
 <span data-ttu-id="fa1e5-127">**Status**</span><span class="sxs-lookup"><span data-stu-id="fa1e5-127">**Status**</span></span>  
 <span data-ttu-id="fa1e5-128">Viene indicato se l'operazione di distribuzione ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-128">Indicates whether the Deploy operation was successful or not.</span></span>  
  
 <span data-ttu-id="fa1e5-129">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="fa1e5-129">**Details**</span></span>  
 <span data-ttu-id="fa1e5-130">Vengono elencati gli elementi dei metadati distribuiti, lo stato di ogni elemento dei metadati e viene fornito un messaggio relativo a eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-130">Lists the metadata items that were deployed, the status for each metadata item, and provides a message of any issues.</span></span>  
  
 <span data-ttu-id="fa1e5-131">**Arresta distribuzione**</span><span class="sxs-lookup"><span data-stu-id="fa1e5-131">**Stop Deploy**</span></span>  
 <span data-ttu-id="fa1e5-132">Fare clic su questa opzione per arrestare l'operazione di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-132">Click to halt the Deploy operation.</span></span> <span data-ttu-id="fa1e5-133">Questa opzione è utile se l'operazione di distribuzione è troppo lunga o se si sono verificati troppi errori.</span><span class="sxs-lookup"><span data-stu-id="fa1e5-133">This option is useful if the Deploy operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa1e5-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa1e5-134">See Also</span></span>  
 <span data-ttu-id="fa1e5-135">[Distribuzione di soluzioni di modelli tabulari &#40;SSAS tabulare&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="fa1e5-135">[Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="fa1e5-136">Configurare la modellazione dei dati e le proprietà di distribuzione predefinite &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="fa1e5-136">Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
