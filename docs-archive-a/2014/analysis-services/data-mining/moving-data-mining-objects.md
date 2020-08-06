---
title: Trasferimento di oggetti di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], models
- data mining editor [Analysis Services]
- mining models [Analysis Services], managing
- Data Mining Designer
- mining models [Analysis Services], modifying
ms.assetid: bc108407-2603-4387-b930-b5bb9df78069
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b10be3a79487376b173eab87059404b7f7a618e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712647"
---
# <a name="moving-data-mining-objects"></a><span data-ttu-id="4b733-102">Spostamento di oggetti di data mining</span><span class="sxs-lookup"><span data-stu-id="4b733-102">Moving Data Mining Objects</span></span>
  <span data-ttu-id="4b733-103">Gli scenari più comuni per lo spostamento di oggetti di data mining sono la distribuzione di un modello da un ambiente di test o analisi a un ambiente di produzione o la condivisione di modelli con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="4b733-103">The most common scenarios for moving data mining objects are to deploy a model from a testing or analysis environment to a production environment, or to share models with other users.</span></span>  
  
 <span data-ttu-id="4b733-104">Questo argomento descrive come usare gli strumenti e i linguaggi di scripting forniti da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], per lo spostamento di oggetti di data mining.</span><span class="sxs-lookup"><span data-stu-id="4b733-104">This topic describes how you can use the tools and scripting languages provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], for moving data mining objects.</span></span>  
  
## <a name="moving-data-mining-objects-between-databases-or-servers"></a><span data-ttu-id="4b733-105">Spostamento di oggetti di data mining tra database o server</span><span class="sxs-lookup"><span data-stu-id="4b733-105">Moving Data Mining Objects between Databases or Servers</span></span>  
 <span data-ttu-id="4b733-106">È possibile spostare oggetti di data mining tra database [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o tra istanze di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b733-106">You can move data mining objects between [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases or between instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="4b733-107">Ridistribuzione della soluzione in un altro database.</span><span class="sxs-lookup"><span data-stu-id="4b733-107">Re-deploying the solution to a different database.</span></span>  
  
-   <span data-ttu-id="4b733-108">Generazione di script di oggetti singoli.</span><span class="sxs-lookup"><span data-stu-id="4b733-108">Scripting individual objects.</span></span>  
  
-   <span data-ttu-id="4b733-109">Backup e ripristino di una copia del database.</span><span class="sxs-lookup"><span data-stu-id="4b733-109">Backing up and then restoring a copy of the database.</span></span>  
  
-   <span data-ttu-id="4b733-110">Esportazione e importazione di strutture e modelli.</span><span class="sxs-lookup"><span data-stu-id="4b733-110">Exporting and importing structures and models.</span></span>  
  
 <span data-ttu-id="4b733-111">Nella sezione seguente queste opzioni vengono descritte in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="4b733-111">The following section explains these options in more detail.</span></span>  
  
### <a name="deploying"></a><span data-ttu-id="4b733-112">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="4b733-112">Deploying</span></span>  
 <span data-ttu-id="4b733-113">La distribuzione della soluzione in un server o un database diverso richiede che sia disponibile il file della soluzione creato tramite [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b733-113">Deploying the solution to a different server or database requires that you have the solution file that was created by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4b733-114">Per altre informazioni sulla distribuzione di Analysis Services, vedere [Distribuire progetti di Analysis Services &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="4b733-114">For more information about deploying Analysis Services solutions, see [Deploy Analysis Services Projects &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span></span>  
  
### <a name="scripting"></a><span data-ttu-id="4b733-115">Scripting</span><span class="sxs-lookup"><span data-stu-id="4b733-115">Scripting</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="4b733-116">sono disponibili diversi linguaggi che è possibile usare per generare script di oggetti.</span><span class="sxs-lookup"><span data-stu-id="4b733-116">provides several languages that you can use to script objects.</span></span>  
  
-   <span data-ttu-id="4b733-117">**XMLA**: è possibile generare script di oggetti usando XMLA facendo clic con il pulsante destro del mouse sugli oggetti in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b733-117">**XMLA**: You can script objects using XMLA by right-clicking objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4b733-118">Per eseguire lo script, aprirlo in una finestra **Query XMLA** nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4b733-118">To execute the script, open it in an **XMLA Query** window on the target server.</span></span>  
  
-   <span data-ttu-id="4b733-119">**DMX**: è possibile creare script tramite modelli o uno dei generatori di query forniti in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] e [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b733-119">**DMX**: You can create scripts by using templates or one of the query builders provided in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4b733-120">Si noti, tuttavia, che sono presenti differenze nelle attività che è possibile eseguire con ogni linguaggio di scripting:</span><span class="sxs-lookup"><span data-stu-id="4b733-120">Note, however, that there are differences in the tasks that you can perform with each scripting language:</span></span>  
  
-   <span data-ttu-id="4b733-121">Alcune proprietà, quali la descrizione dell'oggetto e le associazioni dati, possono essere create o modificate solo tramite i linguaggi DDL di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , non tramite DMX.</span><span class="sxs-lookup"><span data-stu-id="4b733-121">Properties such as the object description and data bindings can only by created or changed by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] DDL languages, not by using DMX.</span></span>  
  
-   <span data-ttu-id="4b733-122">Solo DMX supporta l'importazione e l'esportazione di oggetti di data mining.</span><span class="sxs-lookup"><span data-stu-id="4b733-122">Only DMX supports the import and export of mining objects.</span></span>  
  
-   <span data-ttu-id="4b733-123">Solo DMX supporta la generazione di PMML o l'importazione di definizioni di modello da PMML.</span><span class="sxs-lookup"><span data-stu-id="4b733-123">Only DMX supports generating PMML or importing model definitions from PMML.</span></span>  
  
-   <span data-ttu-id="4b733-124">Solo DMX supporta il training di un modello con i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b733-124">Only DMX supports training a model with application data.</span></span> <span data-ttu-id="4b733-125">Inoltre, l'istruzione DMX INSERT INTO supporta il training di un modello senza fornire valori per una colonna chiave.</span><span class="sxs-lookup"><span data-stu-id="4b733-125">Moreover, the DMX INSERT INTO statement supports training a model without providing values for a key column.</span></span>  
  
 <span data-ttu-id="4b733-126">Per ulteriori informazioni, vedere [Sviluppo con Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="4b733-126">For more information, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
### <a name="backup-and-restore"></a><span data-ttu-id="4b733-127">Backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="4b733-127">Backup and Restore</span></span>  
 <span data-ttu-id="4b733-128">Le operazioni di backup e ripristino di un intero database di Analysis Services sono il metodo ottimale se la soluzione di data mining si basa su oggetti OLAP.</span><span class="sxs-lookup"><span data-stu-id="4b733-128">Backup and restore of an entire Analysis Services database is the method of choice if your data mining solution relies on OLAP objects.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="4b733-129">offre nuove funzionalità di backup e ripristino che rendono più veloci e facili le operazioni di backup del database.</span><span class="sxs-lookup"><span data-stu-id="4b733-129">provides backup and restore functionality that makes database backups faster and easier.</span></span>  
  
 <span data-ttu-id="4b733-130">Per altre informazioni, vedere [Backup e ripristino di database di Analysis Services](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span><span class="sxs-lookup"><span data-stu-id="4b733-130">For more information about backup, see [Backup and Restore of Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span></span>  
  
### <a name="exporting-and-importing"></a><span data-ttu-id="4b733-131">Esportazione e importazione</span><span class="sxs-lookup"><span data-stu-id="4b733-131">Exporting and Importing</span></span>  
 <span data-ttu-id="4b733-132">Le operazioni di esportazione e reimportazione di modelli e strutture di data mining mediante le istruzioni DMX costituiscono il modo più semplice per spostare o eseguire il backup di singoli oggetti di data mining relazionali.</span><span class="sxs-lookup"><span data-stu-id="4b733-132">Exporting and then re-importing mining models and structures by using DMX statements is the easiest way to move or back up individual relational data mining objects.</span></span> <span data-ttu-id="4b733-133">Per ulteriori informazioni sulla sintassi DMX per queste operazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="4b733-133">For more information about the DMX syntax for these operations, see the following topics:</span></span>  
  
-   [<span data-ttu-id="4b733-134">EXPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="4b733-134">EXPORT &#40;DMX&#41;</span></span>](/sql/dmx/export-dmx)  
  
-   [<span data-ttu-id="4b733-135">IMPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="4b733-135">IMPORT &#40;DMX&#41;</span></span>](/sql/dmx/import-dmx)  
  
 <span data-ttu-id="4b733-136">Se si specifica l'opzione INCLUDE DEPENDENCIES, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] esporterà anche la definizione di eventuali viste origine dati obbligatorie e, durante l'importazione del modello o della struttura, verrà ricreata la vista origine dati nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4b733-136">If you specify the INCLUDE DEPENDENCIES option, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will also export the definition of any required data source views, and when you import the model or structure, it will re-create the data source view on the target server.</span></span> <span data-ttu-id="4b733-137">Al termine dell'importazione del modello, assicurarsi di impostare le autorizzazioni di data mining necessarie per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="4b733-137">After you have finished importing the model, make sure to set the necessary mining permissions on the object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b733-138">Non è possibile esportare né importare modelli OLAP tramite DMX.</span><span class="sxs-lookup"><span data-stu-id="4b733-138">You cannot export and import OLAP models by using DMX.</span></span> <span data-ttu-id="4b733-139">Se il modello di data mining è basato su un cubo OLAP, è necessario usare le funzionalità di backup e ripristino di un intero database o di ridistribuzione del cubo e dei relativi modelli di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b733-139">If your mining model is based on an OLAP cube, you must use the functionality provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for backing up and restoring an entire database, or redeploy the cube and its models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b733-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b733-140">See Also</span></span>  
 [<span data-ttu-id="4b733-141">Gestione degli oggetti e delle soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="4b733-141">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
  
