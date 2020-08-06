---
title: Soluzioni di data mining | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
- data mining [Analysis Services], development
ms.assetid: 84f6548d-ebb0-4e10-9b29-66253fa0a04a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0ab4b5ddcc9958fa36d6c8ecae0e7fd79585b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627549"
---
# <a name="data-mining-solutions"></a><span data-ttu-id="0a564-102">Soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="0a564-102">Data Mining Solutions</span></span>
  <span data-ttu-id="0a564-103">Una soluzione di data mining è una soluzione di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che contiene uno o più progetti di data mining.</span><span class="sxs-lookup"><span data-stu-id="0a564-103">A data mining solution is an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] solution that contains one or more data mining projects.</span></span>  
  
 <span data-ttu-id="0a564-104">Negli argomenti di questa sezione vengono fornite informazioni sulla progettazione e l'implementazione di una soluzione di data mining integrata utilizzando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a564-104">The topics in this section provide information about how to design and implement an integrated data mining solution by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="0a564-105">Per una panoramica sul processo di progettazione dei modelli di data mining e sugli strumenti correlati, vedere [Concetti di data mining](data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="0a564-105">For an overview of the data mining design process and related tools, see [Data Mining Concepts](data-mining-concepts.md).</span></span>  
  
 <span data-ttu-id="0a564-106">Per altre informazioni su ulteriori tipi di progetti utili per il data mining, vedere [Progetti correlati per soluzioni di data mining](data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="0a564-106">For more information about additional projects types that are useful for data mining, see [Related Projects for Data Mining Solutions](data-mining-solutions.md).</span></span>  
  
 [<span data-ttu-id="0a564-107">Modelli di data mining relazionali e multidimensionali</span><span class="sxs-lookup"><span data-stu-id="0a564-107">Relational vs. Multidimensional Solutions</span></span>](#bkmk_RelMD)  
  
 [<span data-ttu-id="0a564-108">Distribuzione di soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="0a564-108">Deploying Data Mining Solutions</span></span>](#bkmk_Deploy)  
  
 [<span data-ttu-id="0a564-109">Procedure dettagliate sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="0a564-109">Solution Walkthroughs</span></span>](#bkmk_Walkthru)  
  
##  <a name="relational-vs-multidimensional-solutions"></a><a name="bkmk_RelMD"></a><span data-ttu-id="0a564-110">Confronto tra soluzioni multidimensionali e relazionali</span><span class="sxs-lookup"><span data-stu-id="0a564-110">Relational vs. Multidimensional Solutions</span></span>  
 <span data-ttu-id="0a564-111">Una soluzione data mining può essere basata su dati multidimensionali, ovvero un cubo esistente, o su dati puramente relazionali, ad esempio tabelle e viste in una data warehouse o su file di testo, cartelle di lavoro di Excel o altre origini dati esterne.</span><span class="sxs-lookup"><span data-stu-id="0a564-111">A data mining solution can be based either on multidimensional data-that is, an existing cube-or on purely relational data, such as the tables and views in a data warehouse, or on text files, Excel workbooks, or other external data sources.</span></span>  
  
-   <span data-ttu-id="0a564-112">È possibile creare oggetti di data mining all'interno di una soluzione di database multidimensionale esistente.</span><span class="sxs-lookup"><span data-stu-id="0a564-112">You can create data mining objects within an existing multidimensional database solution.</span></span>  
  
     <span data-ttu-id="0a564-113">In genere una soluzione come questa verrebbe creata se è già stato creato un cubo e si desidera eseguire il data mining utilizzando il cubo come origine dati.</span><span class="sxs-lookup"><span data-stu-id="0a564-113">Typically you would create a solution like this if you have already created a cube and want to perform data mining by using the cube as a data source.</span></span> <span data-ttu-id="0a564-114">Quando si sposta e si esegue il backup dei modelli in base a un cubo, è necessario spostare o copiare anche il cubo.</span><span class="sxs-lookup"><span data-stu-id="0a564-114">When you move and backup models based on a cube, the cube must also be moved or copied.</span></span>  
  
-   <span data-ttu-id="0a564-115">È possibile creare una soluzione di data mining che contiene solo oggetti di data mining, incluse le origini dati e le viste origine dati di supporto, e che utilizza solo origini dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="0a564-115">You can create a data mining solution that contains only data mining objects, including the supporting data sources and data source views, and that uses relational data source only.</span></span>  
  
     <span data-ttu-id="0a564-116">Si tratta del metodo preferito per la creazione di modelli di data mining, in quanto l'elaborazione e l'esecuzione di query è generalmente più veloce rispetto alle origini dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="0a564-116">This is the preferred method for creating data mining models, as processing and querying is generally fastest against relational data sources.</span></span> <span data-ttu-id="0a564-117">È inoltre facile spostare ed eseguire il backup dei modelli tra i server tramite i comandi EXPORT e IMPORT.</span><span class="sxs-lookup"><span data-stu-id="0a564-117">You can also easily move and backup models between servers by using the EXPORT and IMPORT commands.</span></span>  
  
##  <a name="deploying-data-mining-solutions"></a><a name="bkmk_Deploy"></a><span data-ttu-id="0a564-118">Distribuzione di soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="0a564-118">Deploying Data Mining Solutions</span></span>  
 <span data-ttu-id="0a564-119">L'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a cui si distribuisce la soluzione deve essere in esecuzione in una modalità che supporta oggetti multidimensionali e oggetti di data mining; non è infatti possibile distribuire oggetti di data mining a un'istanza che ospita modelli tabulari o dati PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="0a564-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="0a564-120">Pertanto, quando si crea una soluzione di data mining in Visual Studio, assicurarsi di usare il modello **Progetto multidimensionale e di data mining di Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="0a564-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="0a564-121">Quando si distribuisce la soluzione, gli oggetti utilizzati per il data mining vengono creati nell'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] specificata, in un database con lo stesso nome del file della soluzione.</span><span class="sxs-lookup"><span data-stu-id="0a564-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
 <span data-ttu-id="0a564-122">Per altre informazioni sulla modalità di distribuzione delle soluzioni relazionali e multidimensionali, vedere [Distribuzione di soluzioni di data mining](deployment-of-data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="0a564-122">For more information about how to deploy both relational and multidimensional solutions, see [Deployment of Data Mining Solutions](deployment-of-data-mining-solutions.md).</span></span>  
  
##  <a name="solution-walkthrough"></a><a name="bkmk_Walkthru"></a> <span data-ttu-id="0a564-123">Procedura dettagliata sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="0a564-123">Solution Walkthrough</span></span>  
 <span data-ttu-id="0a564-124">Vengono forniti cenni preliminari relativi alla creazione di soluzioni di data mining tramite Creazione guidata modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="0a564-124">Provides an overview of how to create data mining solutions by using the Data Mining Wizard.</span></span>  
  
 [<span data-ttu-id="0a564-125">Creare una struttura di data mining relazionale</span><span class="sxs-lookup"><span data-stu-id="0a564-125">Create a Relational Mining Structure</span></span>](create-a-relational-mining-structure.md)  
 <span data-ttu-id="0a564-126">Creare una struttura di data mining da dati relazionali, file di testo e altre origini che è possibile combinare in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="0a564-126">Create a mining structure from relational data, text files, and other sources that can be combined in a data source view.</span></span>  
  
 [<span data-ttu-id="0a564-127">Create an OLAP Mining Structure</span><span class="sxs-lookup"><span data-stu-id="0a564-127">Create an OLAP Mining Structure</span></span>](create-an-olap-mining-structure.md)  
 <span data-ttu-id="0a564-128">Creare una struttura di data mining basata sui dati di un cubo OLAP.</span><span class="sxs-lookup"><span data-stu-id="0a564-128">Create a mining structure based on data in an OLAP cube.</span></span> <span data-ttu-id="0a564-129">È possibile salvare i modelli creati dai dati OLAP come dimensione di data mining oppure salvare il set di dati e i modelli come nuovo cubo.</span><span class="sxs-lookup"><span data-stu-id="0a564-129">Models that you create from OLAP data can be saved as a data mining dimension, or you can save the set of data and your models as a new cube.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a564-130">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0a564-130">In This Section</span></span>  
 [<span data-ttu-id="0a564-131">Progetti di data mining</span><span class="sxs-lookup"><span data-stu-id="0a564-131">Data Mining Projects</span></span>](data-mining-projects.md)  
  
 [<span data-ttu-id="0a564-132">Elaborazione di oggetti di data mining</span><span class="sxs-lookup"><span data-stu-id="0a564-132">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)  
  
 [<span data-ttu-id="0a564-133">Progetti correlati per soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="0a564-133">Related Projects for Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
 [<span data-ttu-id="0a564-134">Distribuzione di soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="0a564-134">Deployment of Data Mining Solutions</span></span>](deployment-of-data-mining-solutions.md)  
  
## <a name="related-tasks-and-topics"></a><span data-ttu-id="0a564-135">Attività e argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0a564-135">Related Tasks and Topics</span></span>  
 <span data-ttu-id="0a564-136">Dopo avere creato una soluzione di data mining di base, che include origini dati e una struttura di data mining, è possibile ampliarla aggiungendo nuovi modelli, eseguendo test e confrontando i modelli, creando stime e sperimentando l'utilizzo di subset di dati.</span><span class="sxs-lookup"><span data-stu-id="0a564-136">After you have created a basic data mining solution, including data sources and a mining structure, you can build on the solution by adding new models, testing and comparing models, creating predictions, and experimenting with subsets of data.</span></span>  
  
 <span data-ttu-id="0a564-137">Per ulteriori informazioni, vedere i seguenti collegamenti:</span><span class="sxs-lookup"><span data-stu-id="0a564-137">For more information, see the following links:</span></span>  
  
|<span data-ttu-id="0a564-138">Attività</span><span class="sxs-lookup"><span data-stu-id="0a564-138">Tasks</span></span>|<span data-ttu-id="0a564-139">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0a564-139">Topics</span></span>|  
|-----------|------------|  
|<span data-ttu-id="0a564-140">Eseguire test sui modelli creati, convalidare la qualità dei dati di training e creare grafici che rappresentano l'accuratezza dei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="0a564-140">Test the models you create, validate the quality of your training data, and create charts that represent the accuracy of data mining models.</span></span>|[<span data-ttu-id="0a564-141">Test e convalida &#40;Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="0a564-141">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)|  
|<span data-ttu-id="0a564-142">Eseguire il training del modello popolando la struttura e i modelli correlati con i dati.</span><span class="sxs-lookup"><span data-stu-id="0a564-142">Train the model by populating the structure and related models with data.</span></span> <span data-ttu-id="0a564-143">Aggiornare ed estendere i modelli con nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="0a564-143">Update and extend models with new data.</span></span>|[<span data-ttu-id="0a564-144">Elaborazione di oggetti di data mining</span><span class="sxs-lookup"><span data-stu-id="0a564-144">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)|  
|<span data-ttu-id="0a564-145">Personalizzare un modello di data mining applicando filtri ai dati di training, scegliendo un algoritmo diverso o impostando parametri avanzati dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="0a564-145">Customize a mining model by applying filters to the training data, choosing a different algorithm, or setting advanced algorithm parameters.</span></span>|[<span data-ttu-id="0a564-146">Personalizzare struttura e modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="0a564-146">Customize Mining Models and Structure</span></span>](customize-mining-models-and-structure.md)|  
|<span data-ttu-id="0a564-147">Personalizzare un modello di data mining applicando filtri ai dati utilizzati per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="0a564-147">Customize a mining model by applying filters to the data used in training the mode.</span></span>|[<span data-ttu-id="0a564-148">Aggiungere modelli di data mining a una struttura &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="0a564-148">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](add-mining-models-to-a-structure-analysis-services-data-mining.md)|  
|<span data-ttu-id="0a564-149">Aggiornare e gestire soluzioni di data mining.</span><span class="sxs-lookup"><span data-stu-id="0a564-149">Update and manage data mining solutions.</span></span>|<span data-ttu-id="0a564-150">Collegamento</span><span class="sxs-lookup"><span data-stu-id="0a564-150">Link TBD</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a564-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a564-151">See Also</span></span>  
 [<span data-ttu-id="0a564-152">Esercitazioni sul data mining &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0a564-152">Data Mining Tutorials &#40;Analysis Services&#41;</span></span>](../data-mining-tutorials-analysis-services.md)  
  
  
