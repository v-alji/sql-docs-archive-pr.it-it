---
title: Informazioni sui file di input utilizzati per creare lo script di distribuzione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- Analysis Services Deployment Wizard, scripts
- deploying [Analysis Services], input files
- Analysis Services Deployment Wizard, input files
- scripts [Analysis Services], deployment
- Analysis Services deployments, input files
- modifying input files
ms.assetid: 20e080cd-6a0e-4591-b022-ea4cd3638e36
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34695993d4f153c6c0b97fef744d92c682517c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629084"
---
# <a name="understanding-the-input-files-used-to-create-the-deployment-script"></a><span data-ttu-id="cee99-102">Informazioni sui file di input utilizzati per creare uno script di distribuzione</span><span class="sxs-lookup"><span data-stu-id="cee99-102">Understanding the Input Files Used to Create the Deployment Script</span></span>
  <span data-ttu-id="cee99-103">Quando si compila un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] genera file XML per il progetto.</span><span class="sxs-lookup"><span data-stu-id="cee99-103">When you build a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generates XML files for the project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="cee99-104">inserisce questi file XML nella cartella di output del progetto [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cee99-104">puts these XML files in the Output folder of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="cee99-105">Per impostazione predefinita l'output è situato nella cartella \Bin.</span><span class="sxs-lookup"><span data-stu-id="cee99-105">By default output is out in the \Bin folder.</span></span> <span data-ttu-id="cee99-106">Nella tabella seguente vengono elencati i file XML creati da [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cee99-106">The following table lists the XML files that [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates.</span></span>  
  
|<span data-ttu-id="cee99-107">File XMLA</span><span class="sxs-lookup"><span data-stu-id="cee99-107">XMLA file</span></span>|<span data-ttu-id="cee99-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cee99-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cee99-109">\<*project name*>. asdatabase</span><span class="sxs-lookup"><span data-stu-id="cee99-109">\<*project name*>.asdatabase</span></span>|<span data-ttu-id="cee99-110">Contiene le definizioni dichiarative per tutti gli oggetti [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contenuti nel progetto.</span><span class="sxs-lookup"><span data-stu-id="cee99-110">Contains the declarative definitions for all the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in the project.</span></span>|  
|<span data-ttu-id="cee99-111">\<*project name*>. deploymenttargets</span><span class="sxs-lookup"><span data-stu-id="cee99-111">\<*project name*>.deploymenttargets</span></span>|<span data-ttu-id="cee99-112">Contiene il nome dell'istanza [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e del database in cui verranno creati gli oggetti [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cee99-112">Contains the name of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database in which the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects will be created.</span></span>|  
|<span data-ttu-id="cee99-113">\<*project name*>. configsettings</span><span class="sxs-lookup"><span data-stu-id="cee99-113">\<*project name*>.configsettings</span></span>|<span data-ttu-id="cee99-114">Contiene le impostazioni specifiche all'ambiente, quali le informazioni sulla connessione all'origine dati e i percorsi di archiviazione degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="cee99-114">Contains environment specific settings, such as data source connection information and object storage locations.</span></span> <span data-ttu-id="cee99-115">Le impostazioni in questo file eseguono l'override delle impostazioni nel \<*project name*> file con estensione asdatabase.</span><span class="sxs-lookup"><span data-stu-id="cee99-115">Settings in this file override settings in the \<*project name*>.asdatabase file.</span></span>|  
|<span data-ttu-id="cee99-116">\<*project name*>. deploymentoptions</span><span class="sxs-lookup"><span data-stu-id="cee99-116">\<*project name*>.deploymentoptions</span></span>|<span data-ttu-id="cee99-117">Contiene le opzioni di distribuzione, come ad esempio se la distribuzione è transazionale o se gli oggetti distribuiti vanno elaborati dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cee99-117">Contains deployment options, such as whether deployment is transactional and whether deployed objects should be processed after deployment.</span></span>|  
  
> [!NOTE]  
>  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="cee99-118">non archivia mai le password nei file di progetto.</span><span class="sxs-lookup"><span data-stu-id="cee99-118">never stores passwords in its project files.</span></span>  
  
## <a name="modifying-the-input-files"></a><span data-ttu-id="cee99-119">Modifica del file di input</span><span class="sxs-lookup"><span data-stu-id="cee99-119">Modifying the Input Files</span></span>  
 <span data-ttu-id="cee99-120">Se si modificano i valori nei file di input o i valori recuperati dai file di input, è possibile modificare la destinazione della distribuzione, le impostazioni di configurazione e le opzioni di distribuzione senza modificare l'intero \<*project name*> file asdatabase (o un intero file di script XMLA se si genera uno script da un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database esistente).</span><span class="sxs-lookup"><span data-stu-id="cee99-120">Modifying the values in the input files, or the values retrieved from the input files, makes it possible to change the deployment destination, the configuration settings, and deployment options without editing the whole \<*project name*>.asdatabase file (or a whole XMLA script file if you generate a script from an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database).</span></span> <span data-ttu-id="cee99-121">La possibilità di modificare singoli file facilita la creazione di script di distribuzione diversi per vari scopi.</span><span class="sxs-lookup"><span data-stu-id="cee99-121">Being able to modify individual files lets you easily create different deployment scripts for different purposes.</span></span>  
  
 <span data-ttu-id="cee99-122">Gli argomenti seguenti illustrano come modificare valori nei vari file di input:</span><span class="sxs-lookup"><span data-stu-id="cee99-122">The following topics explain how to modify values in the various input files:</span></span>  
  
-   [<span data-ttu-id="cee99-123">Impostazione della destinazione di installazione</span><span class="sxs-lookup"><span data-stu-id="cee99-123">Specifying the Installation Target</span></span>](deployment-script-files-specifying-the-installation-target.md)  
  
-   [<span data-ttu-id="cee99-124">Impostazione delle opzioni di distribuzione dei ruoli e delle partizioni</span><span class="sxs-lookup"><span data-stu-id="cee99-124">Specifying Partition and Role Deployment Options</span></span>](deployment-script-files-partition-and-role-deployment-options.md)  
  
-   [<span data-ttu-id="cee99-125">Definizione delle impostazioni di configurazione per la distribuzione di soluzioni</span><span class="sxs-lookup"><span data-stu-id="cee99-125">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
-   [<span data-ttu-id="cee99-126">Impostazione delle opzioni di elaborazione</span><span class="sxs-lookup"><span data-stu-id="cee99-126">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="cee99-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cee99-127">See Also</span></span>  
 <span data-ttu-id="cee99-128">[Esecuzione della distribuzione guidata Analysis Services](running-the-analysis-services-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="cee99-128">[Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="cee99-129">Informazioni sullo script di distribuzione di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cee99-129">Understanding the Analysis Services Deployment Script</span></span>](understanding-the-analysis-services-deployment-script.md)  
  
  
