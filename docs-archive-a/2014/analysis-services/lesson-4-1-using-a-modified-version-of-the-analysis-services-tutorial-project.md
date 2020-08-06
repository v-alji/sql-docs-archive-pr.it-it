---
title: Uso di una versione modificata del progetto Analysis Services Tutorial | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 685aa217-de1b-4df2-bf22-095228c40775
author: minewiskan
ms.author: owend
ms.openlocfilehash: b833a05a567f37443cf89f7356a0855e0827ea73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630130"
---
# <a name="using-a-modified-version-of-the-analysis-services-tutorial-project"></a><span data-ttu-id="40c09-102">Utilizzo di una versione modificata del progetto Analysis Services Tutorial</span><span class="sxs-lookup"><span data-stu-id="40c09-102">Using a Modified Version of the Analysis Services Tutorial Project</span></span>
  <span data-ttu-id="40c09-103">Le lezioni rimanenti di questa esercitazione sono basate su una versione migliorata del progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial completato nelle prime tre lezioni.</span><span class="sxs-lookup"><span data-stu-id="40c09-103">The remaining lessons in this tutorial are based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons.</span></span> <span data-ttu-id="40c09-104">Altre tabelle e calcoli denominati sono stati aggiunti alla vista origine dati **Adventure Works DW 2012** ; sono state aggiunte altre dimensioni al progetto e al cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="40c09-104">Additional tables and named calculations have been added to the **Adventure Works DW 2012** data source view, additional dimensions have been added to the project, and these new dimensions have been added to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="40c09-105">Infine, è stato aggiunto un secondo gruppo di misure contenente le misure di una seconda tabella dei fatti.</span><span class="sxs-lookup"><span data-stu-id="40c09-105">In addition, a second measure group has been added, which contains measures from a second fact table.</span></span> <span data-ttu-id="40c09-106">Il progetto migliorato consente di approfondire la conoscenza delle tecniche per l'aggiunta di funzionalità alla propria applicazione di Business Intelligence senza la necessità di tornare su informazioni già acquisite.</span><span class="sxs-lookup"><span data-stu-id="40c09-106">This enhanced project will enable you to continue learning how to add functionality to your business intelligence application without having to repeat the skills you have already learned.</span></span>  
  
 <span data-ttu-id="40c09-107">Per continuare l'esercitazione è necessario scaricare, estrarre, caricare ed elaborare la versione migliorata del progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="40c09-107">Before you can continue with the tutorial, you must download, extract, load and process the enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span>  <span data-ttu-id="40c09-108">Utilizzare le istruzioni riportate in questa lezione per verificare di avere eseguito tutti i passaggi.</span><span class="sxs-lookup"><span data-stu-id="40c09-108">Use the instructions in this lesson to ensure you have performed all the steps.</span></span>  
  
## <a name="downloading-and-extracting-the-project-file"></a><span data-ttu-id="40c09-109">Download ed estrazione del file di progetto</span><span class="sxs-lookup"><span data-stu-id="40c09-109">Downloading and Extracting the Project File</span></span>  
  
1.  <span data-ttu-id="40c09-110">[Fare clic qui](https://go.microsoft.com/fwlink/?LinkID=221866) per accedere alla pagina di download in cui si trovano i progetti di esempio usati in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="40c09-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to go to the download page that provides the sample projects that go with this tutorial.</span></span> <span data-ttu-id="40c09-111">I progetti dell'esercitazione sono inclusi nel download **Analysis Services Tutorial SQL Server 2012** .</span><span class="sxs-lookup"><span data-stu-id="40c09-111">The tutorial projects are included in the **Analysis Services Tutorial SQL Server 2012** download.</span></span>  
  
2.  <span data-ttu-id="40c09-112">Fare clic su **Analysis Services Tutorial SQL Server 2012** per scaricare il pacchetto in cui sono contenuti i progetti per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="40c09-112">Click **Analysis Services Tutorial SQL Server 2012** to download the package that contains the projects for this tutorial.</span></span>  
  
     <span data-ttu-id="40c09-113">Per impostazione predefinita, nella cartella Downloads viene salvato un file con estensione ZIP.</span><span class="sxs-lookup"><span data-stu-id="40c09-113">By default, a .zip file is saved to the Downloads folder.</span></span> <span data-ttu-id="40c09-114">È necessario spostare il file ZIP in un percorso più breve, ad esempio creare una cartella C:\Tutorials per archiviare i file.</span><span class="sxs-lookup"><span data-stu-id="40c09-114">You must move the .zip file to a location that has a shorter path (for example, create a C:\Tutorials folder to store the files).</span></span>  <span data-ttu-id="40c09-115">È quindi possibile estrarre i file contenuti nel file ZIP.</span><span class="sxs-lookup"><span data-stu-id="40c09-115">You can then extract the files contained in the .zip file.</span></span> <span data-ttu-id="40c09-116">Se si tenta di decomprimere i file dalla cartella Downloads il cui percorso è più lungo, si otterrà solo la Lezione 1.</span><span class="sxs-lookup"><span data-stu-id="40c09-116">If you attempt to unzip the files from the Downloads folder, which has a longer path, you will only get Lesson 1.</span></span>  
  
3.  <span data-ttu-id="40c09-117">Creare una sottocartella al livello dell'unità radice, ad esempio C:\Tutorial, o a un livello immediatamente inferiore.</span><span class="sxs-lookup"><span data-stu-id="40c09-117">Create a subfolder at or near the root drive, for example, C:\Tutorial.</span></span>  
  
4.  <span data-ttu-id="40c09-118">Spostare il file **Analysis Services Tutorial SQL Server 2012.zip** nella sottocartella.</span><span class="sxs-lookup"><span data-stu-id="40c09-118">Move the **Analysis Services Tutorial SQL Server 2012.zip** file to the subfolder.</span></span>  
  
5.  <span data-ttu-id="40c09-119">Fare clic con il pulsante destro del mouse sul file e scegliere **Estrai tutto**.</span><span class="sxs-lookup"><span data-stu-id="40c09-119">Right-click the file and select **Extract All**.</span></span>  
  
6.  <span data-ttu-id="40c09-120">Passare alla cartella **Lesson 4 Start** per trovare il file **Analysis Services Tutorial.sln** .</span><span class="sxs-lookup"><span data-stu-id="40c09-120">Browse to the **Lesson 4 Start** folder to find the **Analysis Services Tutorial.sln** file.</span></span>  
  
## <a name="loading-and-processing-the-enhanced-project"></a><span data-ttu-id="40c09-121">Caricamento ed elaborazione del progetto migliorato</span><span class="sxs-lookup"><span data-stu-id="40c09-121">Loading and Processing the Enhanced Project</span></span>  
  
1.  <span data-ttu-id="40c09-122">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] scegliere **Chiudi soluzione** dal menu **file** per chiudere i file che non verranno utilizzati.</span><span class="sxs-lookup"><span data-stu-id="40c09-122">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **File** menu, click **Close Solution** to close files you won't be using.</span></span>  
  
2.  <span data-ttu-id="40c09-123">Scegliere **Apri** dal menu **File**e fare clic su **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="40c09-123">On the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="40c09-124">Passare al percorso in cui sono stati estratti i file di progetto dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="40c09-124">Browse to the location where you extracted the tutorial project files.</span></span>  
  
     <span data-ttu-id="40c09-125">Trovare la cartella denominata **Lesson 4 Start**, quindi fare doppio clic sul file Analysis Services Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="40c09-125">Find the folder named **Lesson 4 Start**, and then double-click Analysis Services Tutorial.sln.</span></span>  
  
4.  <span data-ttu-id="40c09-126">Distribuire la versione migliorata del progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial nell'istanza locale di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]o in un'altra istanza e verificare che l'elaborazione venga completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="40c09-126">Deploy the enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project to the local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or to another instance, and verify that processing completes successfully.</span></span>  
  
## <a name="understanding-the-enhancements-to-the-project"></a><span data-ttu-id="40c09-127">Informazioni sui miglioramenti apportati al progetto</span><span class="sxs-lookup"><span data-stu-id="40c09-127">Understanding the Enhancements to the Project</span></span>  
 <span data-ttu-id="40c09-128">La versione migliorata del progetto è diversa dalla versione del progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial completata nelle prime tre lezioni.</span><span class="sxs-lookup"><span data-stu-id="40c09-128">The enhanced version of the project is different from the version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons.</span></span> <span data-ttu-id="40c09-129">Le differenze verranno descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="40c09-129">The differences are described in the following sections.</span></span> <span data-ttu-id="40c09-130">Leggere attentamente queste informazioni prima di passare alle lezioni rimanenti dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="40c09-130">Review this information before continuing with the remaining lessons in the tutorial.</span></span>  
  
### <a name="data-source-view"></a><span data-ttu-id="40c09-131">Vista origine dati</span><span class="sxs-lookup"><span data-stu-id="40c09-131">Data Source View</span></span>  
 <span data-ttu-id="40c09-132">Nella vista origine dati del progetto migliorato è inclusa un'ulteriore tabella dei fatti e quattro tabelle delle dimensioni aggiuntive del database [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40c09-132">The data source view in the enhanced project contains one additional fact table and four additional dimension tables from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="40c09-133">Si noti che con dieci tabelle nella vista origine dati, il diagramma \<All Tables> risulta molto pieno.</span><span class="sxs-lookup"><span data-stu-id="40c09-133">Notice that with ten tables in the data source view, the \<All Tables> diagram is becoming crowded.</span></span> <span data-ttu-id="40c09-134">Di conseguenza, risulta difficile individuare sia le relazioni tra le tabelle che tabelle specifiche.</span><span class="sxs-lookup"><span data-stu-id="40c09-134">This makes it difficult to easily understand the relationships between the tables and to locate specific tables.</span></span> <span data-ttu-id="40c09-135">Per risolvere questo problema, le tabelle vengono organizzate in due diagrammi logici, ovvero **Internet Sales** e **Reseller Sales** .</span><span class="sxs-lookup"><span data-stu-id="40c09-135">To solve this problem, the tables are organized into two logical diagrams, the **Internet Sales** diagram and the **Reseller Sales** diagram.</span></span> <span data-ttu-id="40c09-136">Ogni diagramma è organizzato in base a una singola tabella dei fatti.</span><span class="sxs-lookup"><span data-stu-id="40c09-136">These diagrams are each organized around a single fact table.</span></span> <span data-ttu-id="40c09-137">La creazione di diagrammi logici consente di visualizzare e utilizzare un subset specifico delle tabelle in una vista origine dati anziché visualizzare sempre tutte le tabelle e le relative relazioni in un unico diagramma.</span><span class="sxs-lookup"><span data-stu-id="40c09-137">Creating logical diagrams lets you view and work with a specific subset of the tables in a data source view instead of always viewing all the tables and their relationships in a single diagram.</span></span>  
  
#### <a name="internet-sales-diagram"></a><span data-ttu-id="40c09-138">Diagramma Internet Sales</span><span class="sxs-lookup"><span data-stu-id="40c09-138">Internet Sales Diagram</span></span>  
 <span data-ttu-id="40c09-139">Il diagramma **Internet Sales** contiene le tabelle relative alla vendita dei prodotti [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] direttamente ai clienti tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="40c09-139">The **Internet Sales** diagram contains the tables that are related to the sale of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] products directly to customers through the Internet.</span></span> <span data-ttu-id="40c09-140">Le tabelle del diagramma sono le quattro tabelle delle dimensioni e una sola tabella dei fatti aggiunte alla vista origine dati di **Adventure Works DW 2012** nella Lezione 1.</span><span class="sxs-lookup"><span data-stu-id="40c09-140">The tables in the diagram are the four dimension tables and one fact table that you added to the **Adventure Works DW 2012** data source view in Lesson 1.</span></span> <span data-ttu-id="40c09-141">Le tabelle sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="40c09-141">These tables are as follows:</span></span>  
  
-   <span data-ttu-id="40c09-142">**Area geografica**</span><span class="sxs-lookup"><span data-stu-id="40c09-142">**Geography**</span></span>  
  
-   <span data-ttu-id="40c09-143">**Customer**</span><span class="sxs-lookup"><span data-stu-id="40c09-143">**Customer**</span></span>  
  
-   <span data-ttu-id="40c09-144">**Data**</span><span class="sxs-lookup"><span data-stu-id="40c09-144">**Date**</span></span>  
  
-   <span data-ttu-id="40c09-145">**Prodotto**</span><span class="sxs-lookup"><span data-stu-id="40c09-145">**Product**</span></span>  
  
-   <span data-ttu-id="40c09-146">**InternetSales**</span><span class="sxs-lookup"><span data-stu-id="40c09-146">**InternetSales**</span></span>  
  
#### <a name="reseller-sales-diagram"></a><span data-ttu-id="40c09-147">Diagramma Reseller Sales</span><span class="sxs-lookup"><span data-stu-id="40c09-147">Reseller Sales Diagram</span></span>  
 <span data-ttu-id="40c09-148">Il diagramma **Reseller Sales** contiene le tabelle relative alla vendita dei prodotti [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] da parte dei rivenditori.</span><span class="sxs-lookup"><span data-stu-id="40c09-148">The **Reseller Sales** diagram contains the tables that are related to the sale of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] products by resellers.</span></span> <span data-ttu-id="40c09-149">Nel diagramma sono incluse le seguenti sette tabelle delle dimensioni e una tabella dei fatti del database [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40c09-149">This diagram contains the following seven dimension tables and one fact table from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database:</span></span>  
  
-   <span data-ttu-id="40c09-150">**Reseller**</span><span class="sxs-lookup"><span data-stu-id="40c09-150">**Reseller**</span></span>  
  
-   <span data-ttu-id="40c09-151">**Promotion**</span><span class="sxs-lookup"><span data-stu-id="40c09-151">**Promotion**</span></span>  
  
-   <span data-ttu-id="40c09-152">**SalesTerritory**</span><span class="sxs-lookup"><span data-stu-id="40c09-152">**SalesTerritory**</span></span>  
  
-   <span data-ttu-id="40c09-153">**Area geografica**</span><span class="sxs-lookup"><span data-stu-id="40c09-153">**Geography**</span></span>  
  
-   <span data-ttu-id="40c09-154">**Data**</span><span class="sxs-lookup"><span data-stu-id="40c09-154">**Date**</span></span>  
  
-   <span data-ttu-id="40c09-155">**Prodotto**</span><span class="sxs-lookup"><span data-stu-id="40c09-155">**Product**</span></span>  
  
-   <span data-ttu-id="40c09-156">**Employee**</span><span class="sxs-lookup"><span data-stu-id="40c09-156">**Employee**</span></span>  
  
-   <span data-ttu-id="40c09-157">**ResellerSales**</span><span class="sxs-lookup"><span data-stu-id="40c09-157">**ResellerSales**</span></span>  
  
 <span data-ttu-id="40c09-158">Si noti che le tabelle **DimGeography**, **DimDate**e **DimProduct** sono usate sia nel diagramma **Internet Sales** sia nel diagramma **Reseller Sales** .</span><span class="sxs-lookup"><span data-stu-id="40c09-158">Notice that the **DimGeography**, **DimDate**, and **DimProduct** tables are used in both the **Internet Sales** diagram and the **Reseller Sales** diagram.</span></span> <span data-ttu-id="40c09-159">È possibile collegare le tabelle delle dimensioni a più tabelle dei fatti.</span><span class="sxs-lookup"><span data-stu-id="40c09-159">Dimension tables can be linked to multiple fact tables.</span></span>  
  
### <a name="database-and-cube-dimensions"></a><span data-ttu-id="40c09-160">Dimensioni del database e del cubo</span><span class="sxs-lookup"><span data-stu-id="40c09-160">Database and Cube Dimensions</span></span>  
 <span data-ttu-id="40c09-161">Nel progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial sono incluse cinque nuove dimensioni del database e il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial contiene queste stesse cinque dimensioni come dimensioni del cubo.</span><span class="sxs-lookup"><span data-stu-id="40c09-161">The [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project contains five new database dimensions, and the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube contains these same five dimensions as cube dimensions.</span></span> <span data-ttu-id="40c09-162">Tali dimensioni sono state definite in modo da avere attributi e gerarchie utente modificati utilizzando calcoli denominati, chiavi dei membri per la composizione e cartelle di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="40c09-162">These dimensions have been defined to have user hierarchies and attributes that were modified by using named calculations, composition member keys, and display folders.</span></span> <span data-ttu-id="40c09-163">Nell'elenco seguente vengono descritte le nuove dimensioni.</span><span class="sxs-lookup"><span data-stu-id="40c09-163">The new dimensions are described in the following list.</span></span>  
  
 <span data-ttu-id="40c09-164">Dimensione Reseller</span><span class="sxs-lookup"><span data-stu-id="40c09-164">Reseller Dimension</span></span>  
 <span data-ttu-id="40c09-165">La dimensione Reseller è basata sulla tabella **Reseller** della vista origine dati di **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="40c09-165">The Reseller dimension is based on the **Reseller** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="40c09-166">Dimensione Promotion</span><span class="sxs-lookup"><span data-stu-id="40c09-166">Promotion Dimension</span></span>  
 <span data-ttu-id="40c09-167">La dimensione Promotion è basata sulla tabella **Promotion** della vista origine dati di **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="40c09-167">The Promotion dimension is based on the **Promotion** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="40c09-168">Dimensione Sales Territory</span><span class="sxs-lookup"><span data-stu-id="40c09-168">Sales Territory Dimension</span></span>  
 <span data-ttu-id="40c09-169">La dimensione Sales Territory è basata sulla tabella **SalesTerritory** della vista origine dati di **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="40c09-169">The Sales Territory dimension is based on the **SalesTerritory** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="40c09-170">Dimensione Employee</span><span class="sxs-lookup"><span data-stu-id="40c09-170">Employee Dimension</span></span>  
 <span data-ttu-id="40c09-171">La dimensione Employee è basata sulla tabella **Employee** della vista origine dati di **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="40c09-171">The Employee dimension is based on the **Employee** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="40c09-172">Dimensione Geography</span><span class="sxs-lookup"><span data-stu-id="40c09-172">Geography Dimension</span></span>  
 <span data-ttu-id="40c09-173">La dimensione Geography è basata sulla tabella **Geography** della vista origine dati di **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="40c09-173">The Geography dimension is based on the **Geography** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
#### <a name="analysis-services-cube"></a><span data-ttu-id="40c09-174">Cubo di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="40c09-174">Analysis Services Cube</span></span>  
 <span data-ttu-id="40c09-175">Il cubo **Analysis Services Tutorial** contiene ora due gruppi di misure, ovvero il gruppo di misure originale basato sulla tabella **InternetSales** e un secondo gruppo di misure basato sulla tabella **ResellerSales** della vista origine dati di **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="40c09-175">The **Analysis Services Tutorial** cube now contains two measure groups, the original measure group based on the **InternetSales** table and a second measure group based on the **ResellerSales** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="40c09-176">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="40c09-176">Next Task in Lesson</span></span>  
 [<span data-ttu-id="40c09-177">Definizione delle proprietà degli attributi padre in una gerarchia padre-figlio</span><span class="sxs-lookup"><span data-stu-id="40c09-177">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md) 
  
## <a name="see-also"></a><span data-ttu-id="40c09-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40c09-178">See Also</span></span>  
 [<span data-ttu-id="40c09-179">Distribuzione di un progetto di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="40c09-179">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
  
  
