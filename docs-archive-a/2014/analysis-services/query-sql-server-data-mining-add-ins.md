---
title: Query (SQL Server componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [data mining]
- Data Mining Query Advanced Editor
- query builder [data mining]
- DMX
ms.assetid: 16af4a6f-18d4-496a-a304-7a13aa32ee76
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90794aae8a3d664d47ab251ffdd954f22d48f992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723176"
---
# <a name="query-sql-server-data-mining-add-ins"></a><span data-ttu-id="037c7-102">Query (componenti aggiuntivi Data mining di SQL Server)</span><span class="sxs-lookup"><span data-stu-id="037c7-102">Query (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="037c7-103">![Pulsante Query modello, barra multifunzione Data mining](media/dmc-query.gif "Pulsante Query modello, barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="037c7-103">![Query Model button, Data Mining ribbon](media/dmc-query.gif "Query Model button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="037c7-104">La procedura guidata **query** consente di interagire con i modelli di data mining esistenti per eseguire stime basate sui dati in una tabella di Excel, un intervallo di Excel o un'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="037c7-104">The **Query** wizard helps you interact with existing mining models to make predictions based on data in an Excel table, an Excel range, or another data source.</span></span> <span data-ttu-id="037c7-105">Il processo di applicazione di nuovi dati a un modello esistente per stimare le tendenze viene definito *query di stima*.</span><span class="sxs-lookup"><span data-stu-id="037c7-105">The process of applying new data to an existing model to predict trends is called a *prediction query*.</span></span>  
  
 <span data-ttu-id="037c7-106">La procedura guidata **query** fornisce inoltre un editor avanzato per la creazione o la modifica di modelli di data mining, per la generazione di query personalizzate o per l'utilizzo di strutture non supportate negli altri strumenti, ad esempio i set di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="037c7-106">The **Query** wizard also provides an advanced editor for creating or modifying data mining models, for generating custom queries, or for working with structures not supported in the other tools, such as nested datasets.</span></span>  
  
-   <span data-ttu-id="037c7-107">Utilizzare l'editor di testo per digitare o incollare le istruzioni DMX (Data Mining Extensions) create altrove.</span><span class="sxs-lookup"><span data-stu-id="037c7-107">Use the text editor to type or paste in the Data Mining Extensions (DMX) statements you've created elsewhere.</span></span>  
  
-   <span data-ttu-id="037c7-108">Utilizzare il Generatore di query interattivo per comporre un'istruzione DMX personalizzata con l'aiuto di modelli e finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="037c7-108">Use the interactive Query Builder to compose a custom DMX statement with the help of templates and dialog boxes.</span></span>  
  
-   <span data-ttu-id="037c7-109">Creare istruzioni DMX per gestire o eseguire il backup di modelli e strutture di data mining.</span><span class="sxs-lookup"><span data-stu-id="037c7-109">Create DMX statements to manage or back up mining models and structures.</span></span>  
  
## <a name="using-the-query-wizard"></a><span data-ttu-id="037c7-110">Utilizzo della procedura guidata di query</span><span class="sxs-lookup"><span data-stu-id="037c7-110">Using the Query Wizard</span></span>  
  
1.  <span data-ttu-id="037c7-111">È innanzitutto necessario specificare un'origine per i dati da utilizzare come input.</span><span class="sxs-lookup"><span data-stu-id="037c7-111">First, you must specify a source for the data to use as input.</span></span> <span data-ttu-id="037c7-112">Si possono utilizzare i dati in una tabella o un intervallo di Excel esistente oppure è possibile specificare un'istruzione SQL per recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="037c7-112">You can use data in an existing Excel table or range, or you can specify a SQL statement to retrieve the data.</span></span>  
  
2.  <span data-ttu-id="037c7-113">Nella procedura guidata viene quindi visualizzato un elenco dei modelli di data mining disponibili nel server a cui si è connessi.</span><span class="sxs-lookup"><span data-stu-id="037c7-113">Next, the wizard presents a list of data mining models on the server to which you are connected.</span></span> <span data-ttu-id="037c7-114">Se si conosce il modello desiderato e si ha familiarità con data mining, è anche possibile fare clic su **Avanzate** per aprire l' **Editor avanzato query di data mining**.</span><span class="sxs-lookup"><span data-stu-id="037c7-114">If you know the model you want and are familiar with data mining, you can also click **Advanced** to open the **Data Mining Advanced Query Editor**.</span></span>  
  
3.  <span data-ttu-id="037c7-115">A seconda del tipo di modello scelto, è necessario specificare la colonna che contiene i dati da valutare e definire i mapping tra le colonne dei dati di input e le colonne del modello.</span><span class="sxs-lookup"><span data-stu-id="037c7-115">Depending on the type of model that you choose, you must specify the column that contains the data to be evaluated, and define mappings between the input data columns and the model columns.</span></span> <span data-ttu-id="037c7-116">In base all'algoritmo prescelto si possono impostare altre proprietà per il modello.</span><span class="sxs-lookup"><span data-stu-id="037c7-116">Depending on the algorithm you choose, you can set other properties on the model.</span></span>  
  
4.  <span data-ttu-id="037c7-117">La procedura guidata consente infine di scegliere una o più stime e di specificare la destinazione di archiviazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="037c7-117">Finally, the wizard also gives you the ability to choose one or more predictions, and specify a destination in which to store the results.</span></span>  
  
 <span data-ttu-id="037c7-118">In qualsiasi momento, è possibile fare clic su **Avanzate** per passare all' **Editor avanzato query di data mining**, che offre un maggiore controllo su ogni parte dell'istruzione DMX.</span><span class="sxs-lookup"><span data-stu-id="037c7-118">At any time, you can click **Advanced** to switch to the **Data Mining Advanced Query Editor**, which gives you more control over each part of the DMX statement.</span></span> <span data-ttu-id="037c7-119">Per ulteriori informazioni sull'utilizzo degli strumenti avanzati per la modifica delle query, vedere [Advanced Data mining query editor](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="037c7-119">For more information about how to use the advanced query editing tools, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="037c7-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="037c7-120">Requirements</span></span>  
 <span data-ttu-id="037c7-121">Per utilizzare la procedura guidata **query** , è necessario essere connessi a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="037c7-121">To use the **Query** wizard, you must be connected to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="037c7-122">Il server deve inoltre contenere almeno un modello di data mining di tipo appropriato.</span><span class="sxs-lookup"><span data-stu-id="037c7-122">Moreover, the server must contain at least one data mining model of an appropriate type.</span></span> <span data-ttu-id="037c7-123">Se non è disponibile alcun modello di data mining, è possibile crearne uno con le procedure guidate incluse nel client di data mining per Excel.</span><span class="sxs-lookup"><span data-stu-id="037c7-123">If no mining models are available, you can create one by using the wizards provided in the Data Mining Client for Excel.</span></span> <span data-ttu-id="037c7-124">Per informazioni sulla creazione di una nuova modalità di data mining tramite una procedura guidata, vedere [creazione di un modello di data mining](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="037c7-124">For information about how to create a new mining mode by using a wizard, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="037c7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="037c7-125">See Also</span></span>  
 <span data-ttu-id="037c7-126">[Distribuzione e scalabilità di modelli di data mining &#40;componenti aggiuntivi Data mining per Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="037c7-126">[Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="037c7-127">Client di data mining per Excel &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="037c7-127">Data Mining Client for Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](data-mining-client-for-excel-sql-server-data-mining-add-ins.md)  
  
  
