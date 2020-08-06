---
title: Impostazione delle opzioni di elaborazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services deployments, processing options
- input files [Analysis Services]
- deploying [Analysis Services], processing options
- modifying processing options
- Analysis Services Deployment Wizard, processing options
ms.assetid: e9e50817-908e-4210-bc3d-8e2957568241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9690aaa7e1d3b3870eb6ab01630b98027263655f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712563"
---
# <a name="specifying-processing-options"></a><span data-ttu-id="ecfbe-102">Impostazione delle opzioni di elaborazione</span><span class="sxs-lookup"><span data-stu-id="ecfbe-102">Specifying Processing Options</span></span>
  <span data-ttu-id="ecfbe-103">La [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] distribuzione guidata legge le opzioni di elaborazione dal \<*project name*> file con estensione deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the processing options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="ecfbe-104">crea questo file quando si compila il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="ecfbe-105">utilizza le opzioni di elaborazione specificate nella pagina **distribuzione** della finestra di *\<project name>* dialogo Pagine delle **proprietà** per creare il \<*project name*> file con estensione deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-105">uses the processing options specified on the **Deployment** page of *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.deploymentoptions file.</span></span>  
  
## <a name="reviewing-the-processing-options-for-deployment"></a><span data-ttu-id="ecfbe-106">Esame delle opzioni di elaborazione per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="ecfbe-106">Reviewing the Processing Options for Deployment</span></span>  
 <span data-ttu-id="ecfbe-107">Di seguito sono riportate le impostazioni di configurazione archiviate nel \<*project name*> file con estensione deploymentoptions:</span><span class="sxs-lookup"><span data-stu-id="ecfbe-107">The configuration settings stored within the \<*project name*>.deploymentoptions file are as follows:</span></span>  
  
-   <span data-ttu-id="ecfbe-108">**Metodo di elaborazione** Questa impostazione determina se gli oggetti distribuiti vengono elaborati dopo la distribuzione e il tipo di elaborazione a cui verranno sottoposti.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-108">**Processing Method** This setting controls whether the deployed objects are processed after deployment and the type of processing that will be performed.</span></span> <span data-ttu-id="ecfbe-109">Sono previste tre opzioni di elaborazione:</span><span class="sxs-lookup"><span data-stu-id="ecfbe-109">There are three processing options:</span></span>  
  
    -   <span data-ttu-id="ecfbe-110">Elaborazione predefinita (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="ecfbe-110">Default processing (default)</span></span>  
  
    -   <span data-ttu-id="ecfbe-111">Elaborazione completa</span><span class="sxs-lookup"><span data-stu-id="ecfbe-111">Full processing</span></span>  
  
    -   <span data-ttu-id="ecfbe-112">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ecfbe-112">None</span></span>  
  
-   <span data-ttu-id="ecfbe-113">**Opzioni tabella writeback** Se il writeback è attivato nel progetto [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , questa impostazione stabilisce come verrà gestito.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-113">**Writeback Table Options** If writeback is enabled in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, this setting defines how writeback is handled.</span></span> <span data-ttu-id="ecfbe-114">Sono previste tre opzioni per la tabella writeback:</span><span class="sxs-lookup"><span data-stu-id="ecfbe-114">There are three writeback table options:</span></span>  
  
    -   <span data-ttu-id="ecfbe-115">Per impostazione predefinita, se esiste una tabella writeback essa verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-115">By default, if a writeback table exists, it will be used.</span></span> <span data-ttu-id="ecfbe-116">Se non esiste alcuna tabella writeback, ne verrà creata una nuova.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-116">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="ecfbe-117">Se la tabella writeback esiste già, non potrà essere portata a termine la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-117">If a writeback table already exists, the deployment fails.</span></span> <span data-ttu-id="ecfbe-118">Se non esiste alcuna tabella writeback, ne verrà creata una nuova.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-118">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="ecfbe-119">Anche se dovesse esistere già una tabella writeback, ne verrà creata una nuova.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-119">Regardless of whether a writeback table already exists, a new writeback table will be created.</span></span> <span data-ttu-id="ecfbe-120">In questo caso, Distribuzione guidata [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] elimina ogni eventuale tabella esistente e la sostituisce con una nuova tabella writeback.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-120">In this case, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard will delete any existing table and replace it with a new writeback table.</span></span>  
  
-   <span data-ttu-id="ecfbe-121">**Distribuzione transazionale** Questa impostazione stabilisce se la distribuzione delle modifiche dei metadati e dei comandi di elaborazione viene eseguita attraverso una singola transazione o in transazioni separate.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-121">**Transactional Deployment** This setting controls whether the deployment of metadata changes and process commands occurs in a single transaction or in separate transactions.</span></span>  
  
    -   <span data-ttu-id="ecfbe-122">Se questa opzione è impostata su `True` (impostazione predefinita), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] distribuisce tutte le modifiche dei metadati e tutti i comandi di elaborazione attraverso una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-122">If this option is `True` (default), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys all metadata changes and all process commands within a single transaction.</span></span>  
  
    -   <span data-ttu-id="ecfbe-123">Se invece questa opzione è impostata su `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] distribuisce le modifiche dei metadati attraverso una singola transazione e distribuisce ogni comando di elaborazione in transazioni separate.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-123">If this option is `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys the metadata changes in a single transaction, and deploys each processing command in its own transaction.</span></span>  
  
## <a name="modifying-the-processing-options-for-deployment"></a><span data-ttu-id="ecfbe-124">Modifica delle opzioni di elaborazione per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="ecfbe-124">Modifying the Processing Options for Deployment</span></span>  
 <span data-ttu-id="ecfbe-125">Potrebbe tuttavia essere necessario distribuire il [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto utilizzando diverse opzioni di elaborazione rispetto a quelle archiviate nel \<*project name*> file con estensione deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-125">However, you may need to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different processing options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="ecfbe-126">Potrebbe ad esempio essere preferibile elaborare tutti gli oggetti in modo completo o elaborarli utilizzando l'opzione di elaborazione predefinita o infine non elaborarli affatto.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-126">For example, you may want to have all objects fully processed, or processed using the default processing option, or have no processing occur.</span></span> <span data-ttu-id="ecfbe-127">Se i cubi o le dimensioni sono abilitati per la scrittura, è possibile specificare se verrà utilizzata una tabella writeback nuova o preesistente.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-127">If the cubes or dimensions are write-enabled, you can specify whether a new or existing writeback table be used.</span></span>  
  
 <span data-ttu-id="ecfbe-128">Per modificare le opzioni di elaborazione da utilizzare durante la distribuzione, è possibile modificare o ricompilare il progetto, oppure è possibile modificare le opzioni di elaborazione nel file di input utilizzando uno dei metodi descritti nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-128">To modify the processing options used during deployment, you can either edit and rebuild the project, or change the processing options in the input file by using one of the methods as described in the following procedure.</span></span>  
  
#### <a name="to-change-processing-options-after-the-input-files-have-been-generated"></a><span data-ttu-id="ecfbe-129">Per modificare le opzioni di elaborazione dopo la generazione dei file di input</span><span class="sxs-lookup"><span data-stu-id="ecfbe-129">To change processing options after the input files have been generated</span></span>  
  
-   <span data-ttu-id="ecfbe-130">Eseguire Distribuzione guidata di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="ecfbe-131">Nella pagina **Opzioni di elaborazione** specificare le opzioni di elaborazione per il progetto da distribuire.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-131">On the **Processing Options** page, specify the processing options for the project being deployed.</span></span>  
  
     <span data-ttu-id="ecfbe-132">-oppure-</span><span class="sxs-lookup"><span data-stu-id="ecfbe-132">-or-</span></span>  
  
-   <span data-ttu-id="ecfbe-133">Eseguire Distribuzione guidata di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] attraverso il prompt dei comandi e impostarla in modo che venga eseguita in modalità file di risposte.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-133">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="ecfbe-134">Per altre informazioni sulla modalità file di risposte, vedere [Esecuzione della Distribuzione guidata Analysis Services](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="ecfbe-134">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="ecfbe-135">-oppure-</span><span class="sxs-lookup"><span data-stu-id="ecfbe-135">-or-</span></span>  
  
-   <span data-ttu-id="ecfbe-136">Modificare il \<*project name*> file con estensione deploymentoptions utilizzando un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="ecfbe-136">Modify the \<*project name*>.deploymentoptions file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecfbe-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecfbe-137">See Also</span></span>  
 <span data-ttu-id="ecfbe-138">[Impostazione della destinazione di installazione](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="ecfbe-138">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="ecfbe-139">[Impostazione delle opzioni di distribuzione di partizioni e ruoli](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="ecfbe-139">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 [<span data-ttu-id="ecfbe-140">Definizione delle impostazioni di configurazione per la distribuzione di soluzioni</span><span class="sxs-lookup"><span data-stu-id="ecfbe-140">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
  
