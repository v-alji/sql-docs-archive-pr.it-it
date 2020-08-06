---
title: Modificare un pacchetto di distribuzione di modelli | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6b0fdb7d-83dd-4392-9011-4ae642c471f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b8bfd7083e2ba763d15a405266260b5a096c8378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638425"
---
# <a name="edit-a-model-deployment-package"></a><span data-ttu-id="3182c-102">Modificare un pacchetto di distribuzione di modelli</span><span class="sxs-lookup"><span data-stu-id="3182c-102">Edit a Model Deployment Package</span></span>
  <span data-ttu-id="3182c-103">Questo argomento descrive come distribuire parti selezionate di un modello in MDS, piuttosto che un modello intero.</span><span class="sxs-lookup"><span data-stu-id="3182c-103">This topic describes how to deploy selected parts of a model in MDS, rather than an entire model.</span></span> <span data-ttu-id="3182c-104">A tale scopo, modificare un pacchetto del modello MDS utilizzando l'Editor pacchetti di modelli.</span><span class="sxs-lookup"><span data-stu-id="3182c-104">To do so, you edit an MDS model package using the Model Package Editor.</span></span>  
  
 <span data-ttu-id="3182c-105">La procedura guidata dell'Editor pacchetti di modelli consente di selezionare le entità specifiche, le gerarchie derivate, le viste delle sottoscrizioni e le regole business in un modello che si desidera includere in un pacchetto MDS e quindi successivamente effettuare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3182c-105">The Model Package Editor wizard enables you to select the specific entities, derived hierarchies, subscription views, and business rules in a model that you want to include in an MDS package, and then later deploy.</span></span> <span data-ttu-id="3182c-106">È possibile tralasciare quelle parti del modello che non si desidera distribuire.</span><span class="sxs-lookup"><span data-stu-id="3182c-106">You can leave out those parts of the model that you do not want to deploy.</span></span> <span data-ttu-id="3182c-107">Quando si seleziona un'entità, anche tutti gli oggetti dipendenti di quell'entità vengono selezionati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3182c-107">When you select an entity, all of the dependent objects in that entity are also automatically selected.</span></span>  
  
 <span data-ttu-id="3182c-108">Utilizzare l'Editor pacchetti di modelli per selezionare parti di un modello in un file di pacchetto creato dallo strumento MDSModelDeploy (che crea un file di pacchetto che include oggetti e dati) o la Distribuzione guidata modello (che crea un file che include solo la struttura del modello).</span><span class="sxs-lookup"><span data-stu-id="3182c-108">You use the Model Package Editor to select parts of a model in a package file that was created by either the MDSModelDeploy tool (which creates a package file that includes objects and data) or the Model Deployment wizard (which creates a file that includes only the model structure).</span></span> <span data-ttu-id="3182c-109">Dopo avere modificato il modello nel pacchetto, utilizzare lo strumento MDSModelDeploy per distribuire oggetti e dati o la Distribuzione guidata modello per distribuire solo la struttura del modello.</span><span class="sxs-lookup"><span data-stu-id="3182c-109">After editing the model in the package, you use the MDSModelDeploy tool to deploy objects and data, or the Model Deployment wizard to deploy just the model structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3182c-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3182c-110">Prerequisites</span></span>  
 <span data-ttu-id="3182c-111">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="3182c-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="3182c-112">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="3182c-112">You must be a model administrator.</span></span> <span data-ttu-id="3182c-113">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3182c-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="3182c-114">È necessario che esista un pacchetto del modello da modificare.</span><span class="sxs-lookup"><span data-stu-id="3182c-114">A model package must exist for you to edit.</span></span> <span data-ttu-id="3182c-115">Per altre informazioni, vedere [Distribuzione di modelli &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) e [Creare un pacchetto di distribuzione di modelli tramite la procedura guidata](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) o [Creare un pacchetto di distribuzione di modelli tramite MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="3182c-115">For more information, see [Deploying Models &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) and [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) or [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
### <a name="to-edit-a-model-deployment-package"></a><span data-ttu-id="3182c-116">Per modificare un pacchetto di distribuzione di modelli</span><span class="sxs-lookup"><span data-stu-id="3182c-116">To edit a model deployment package</span></span>  
  
1.  <span data-ttu-id="3182c-117">In Esplora risorse sul server MDS, spostarsi in *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="3182c-117">In Windows Explorer on the MDS server, move to *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
2.  <span data-ttu-id="3182c-118">Eseguire ModelPackageEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="3182c-118">Execute ModelPackageEditor.exe.</span></span>  
  
3.  <span data-ttu-id="3182c-119">Nella procedura guidata dell'Editor pacchetti di modelli, fare clic su **Sfoglia**, spostarsi nella cartella che contiene i pacchetti, selezionare un pacchetto, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3182c-119">In the Model Package Editor wizard, click **Browse**, move to the folder containing your packages, select a package, and then click **Open**.</span></span> <span data-ttu-id="3182c-120">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3182c-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="3182c-121">Selezionare quelle entità, gerarchie derivate, viste delle sottoscrizioni o regole business che si desidera distribuire.</span><span class="sxs-lookup"><span data-stu-id="3182c-121">Select those entities, derived hierarchies, subscriptions views, or business rules that you want to deploy.</span></span> <span data-ttu-id="3182c-122">Deselezionare quelli che non si desidera distribuire.</span><span class="sxs-lookup"><span data-stu-id="3182c-122">Deselect those that you do not want to deploy.</span></span> <span data-ttu-id="3182c-123">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3182c-123">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="3182c-124">Verificare l'elenco delle selezioni da distribuire.</span><span class="sxs-lookup"><span data-stu-id="3182c-124">Verify the list of selections to deploy.</span></span> <span data-ttu-id="3182c-125">Per apportare modifiche, fare clic su **Indietro** e ripetizione il passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="3182c-125">To change, click **Back** and repeat step 4.</span></span>  
  
6.  <span data-ttu-id="3182c-126">Fare clic su **Sfoglia**, spostarsi nella cartella nella quale si vuole salvare il pacchetto parziale, quindi immettere il nome file del pacchetto parziale (con estensione pkg).</span><span class="sxs-lookup"><span data-stu-id="3182c-126">Click **Browse**, move to the folder that you want to save the partial package in, and then enter the file name of the partial package (with a .pkg extension).</span></span> <span data-ttu-id="3182c-127">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3182c-127">Click **Save**.</span></span>  
  
7.  <span data-ttu-id="3182c-128">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="3182c-128">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3182c-129">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3182c-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="3182c-130">Distribuire un pacchetto di distribuzione di modelli tramite la procedura guidata</span><span class="sxs-lookup"><span data-stu-id="3182c-130">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
-   [<span data-ttu-id="3182c-131">Distribuire un pacchetto di distribuzione di modelli tramite MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="3182c-131">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
  
