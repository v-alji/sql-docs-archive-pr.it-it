---
title: Distribuzione e scalabilità di modelli di data mining (componenti aggiuntivi Data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- manage
ms.assetid: 4c617375-6b01-4a71-9680-de0cbf2cff05
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd2839144d4d1667da09830aaabd1ec3f17a9c21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635260"
---
# <a name="deploying-and-scaling-mining-models-data-mining-add-ins-for-excel"></a><span data-ttu-id="538b3-102">Distribuzione e scalabilità di modelli di data mining (componenti aggiuntivi Data mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="538b3-102">Deploying and Scaling Mining Models (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="538b3-103">Gli strumenti del gruppo di **gestione** e **utilizzo del modello** vengono forniti per semplificare la gestione e la visualizzazione dei modelli di data mining esistenti.</span><span class="sxs-lookup"><span data-stu-id="538b3-103">The tools in the **Model Usage** and **Management** group are provided to help you manage and browse existing mining models.</span></span> <span data-ttu-id="538b3-104">È possibile utilizzare questi strumenti per visualizzare tutti i modelli archiviati in un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e non solo quelli creati utilizzando i componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="538b3-104">You can use these tools to view any models that are stored on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], not just those created using the add-ins.</span></span>  
  
 <span data-ttu-id="538b3-105">Se si dispone delle autorizzazioni necessarie, è possibile eliminare, modificare, rinominare o elaborare modelli e strutture di data mining esistenti senza uscire da Excel.</span><span class="sxs-lookup"><span data-stu-id="538b3-105">If you have the necessary permissions, you can delete, modify, rename, or process existing mining models and structures without leaving Excel.</span></span>  
  
## <a name="model-usage-toolbar"></a><span data-ttu-id="538b3-106">Barra degli strumenti Utilizzo modelli</span><span class="sxs-lookup"><span data-stu-id="538b3-106">Model Usage Toolbar</span></span>  
  
### <a name="browse"></a><span data-ttu-id="538b3-107">Esplora</span><span class="sxs-lookup"><span data-stu-id="538b3-107">Browse</span></span>  
 <span data-ttu-id="538b3-108">Utilizzare la procedura guidata **Sfoglia** per selezionare un modello di data mining esistente, quindi visualizzare ed esplorare il modello in un visualizzatore che contiene più grafici e strumenti.</span><span class="sxs-lookup"><span data-stu-id="538b3-108">Use the **Browse** wizard to select an existing data mining model, and then view and explore the model in a viewer that contains multiple graphs and tools.</span></span>  
  
 <span data-ttu-id="538b3-109">Per ulteriori informazioni, vedere [esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data Mining&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="538b3-109">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="document-model"></a><span data-ttu-id="538b3-110">Modello di documento</span><span class="sxs-lookup"><span data-stu-id="538b3-110">Document Model</span></span>  
 <span data-ttu-id="538b3-111">Fare clic su **modello di documento** per avviare una procedura guidata che consente di creare un report delle strutture di data mining e dei modelli di data mining creati.</span><span class="sxs-lookup"><span data-stu-id="538b3-111">Click **Document Model** to start a wizard that creates a report of the mining structures and mining models that you have created.</span></span> <span data-ttu-id="538b3-112">È possibile creare report di base e avanzati.</span><span class="sxs-lookup"><span data-stu-id="538b3-112">You can create basic or advanced reports.</span></span> <span data-ttu-id="538b3-113">Nei report sono inclusi i metadati delle colonne e del modello, pertanto sono utili per documentare le attività svolte e le modifiche apportate ai modelli.</span><span class="sxs-lookup"><span data-stu-id="538b3-113">The reports include column and model metadata, so are useful for documenting your work and tracking changes in models.</span></span>  
  
 <span data-ttu-id="538b3-114">Per ulteriori informazioni, vedere la documentazione relativa ai [modelli di data mining &#40;componenti aggiuntivi Data mining per Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="538b3-114">For more information, see [Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span></span>  
  
### <a name="query"></a><span data-ttu-id="538b3-115">Query</span><span class="sxs-lookup"><span data-stu-id="538b3-115">Query</span></span>  
 <span data-ttu-id="538b3-116">Fare clic su **query** per avviare la procedura guidata **query** .</span><span class="sxs-lookup"><span data-stu-id="538b3-116">Click **Query** to start the **Query** wizard.</span></span> <span data-ttu-id="538b3-117">La procedura guidata è interattiva e guida l'utente nell'esecuzione dei passaggi necessari per creare una query di stima su un modello di data mining esistente.</span><span class="sxs-lookup"><span data-stu-id="538b3-117">The wizard interactively walks you through the process of creating a prediction query against an existing data mining model.</span></span>  
  
 <span data-ttu-id="538b3-118">Per personalizzare ulteriormente la query o compilare query non incluse nella procedura guidata, è sufficiente fare clic sul pulsante **Avanzate** per avviare la **query di data mining Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="538b3-118">To further customize the query, or build queries not included in the wizard, just click the **Advanced** button to start the **Data Mining Query Advanced Editor**.</span></span>  
  
 <span data-ttu-id="538b3-119">Per ulteriori informazioni, vedere [Query &#40;SQL Server componenti aggiuntivi Data Mining&#41;](query-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="538b3-119">For more information, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="data-mining-advanced-query-editor"></a><span data-ttu-id="538b3-120">Editor avanzato query di data mining</span><span class="sxs-lookup"><span data-stu-id="538b3-120">Data Mining Advanced Query Editor</span></span>  
 <span data-ttu-id="538b3-121">In questo editor è possibile utilizzare modelli DMX (Data Mining Extensions) per avviare la creazione di una query e quindi modificare in modo interattivo gli input, gli output, gli algoritmi e i parametri per creare una struttura di data mining, una query di stima o un modello di data mining personalizzato.</span><span class="sxs-lookup"><span data-stu-id="538b3-121">In this editor, you can use Data Mining Extensions (DMX) templates to jumpstart a query, and then modify the inputs, outputs, algorithms, and parameters to create a custom mining model, mining structure, or prediction query.</span></span>  
  
 <span data-ttu-id="538b3-122">Per ulteriori informazioni, vedere [Advanced Data mining query editor](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="538b3-122">For more information, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="management"></a><span data-ttu-id="538b3-123">Gestione</span><span class="sxs-lookup"><span data-stu-id="538b3-123">Management</span></span>  
 <span data-ttu-id="538b3-124">Utilizzare la procedura guidata **Gestisci modelli** per visualizzare i modelli esistenti sulla connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="538b3-124">Use the **Manage Models** wizard to view existing models on the current connection.</span></span> <span data-ttu-id="538b3-125">È inoltre possibile eliminare, rinominare, elaborare oppure importare ed esportare modelli e strutture di data mining.</span><span class="sxs-lookup"><span data-stu-id="538b3-125">You can also delete, rename, process, or import and export mining models and structures.</span></span>  
  
 <span data-ttu-id="538b3-126">Per ulteriori informazioni, vedere [Manage models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="538b3-126">For more information, see [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538b3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="538b3-127">See Also</span></span>  
 <span data-ttu-id="538b3-128">[Creazione di un modello di data mining](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="538b3-128">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="538b3-129">Convalida di modelli e utilizzo di modelli per la stima &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="538b3-129">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
