---
title: Programmazione di modelli tabulari | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 0ceb461e-12c1-44ea-97ac-b99bf308676b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2565ed28a882750ab9b37beadbce698d3a0abb19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727159"
---
# <a name="tabular-model-programming"></a><span data-ttu-id="f6bae-102">Programmazione di modelli tabulari</span><span class="sxs-lookup"><span data-stu-id="f6bae-102">Tabular Model Programming</span></span>
  <span data-ttu-id="f6bae-103">I modelli tabulari utilizzano costrutti relazionali per modellare i dati di Analysis Services utilizzati dalle applicazioni analitiche e di report.</span><span class="sxs-lookup"><span data-stu-id="f6bae-103">Tabular models use relational constructs to model the Analysis Services data used by analytical and reporting applications.</span></span> <span data-ttu-id="f6bae-104">Questi modelli vengono eseguiti in un'istanza di Analysis Services configurata per la modalità tabulare, utilizzando un motore di analisi in memoria per l'archiviazione in memoria e rapide scansioni di tabella in grado di aggregare e calcolare i dati in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="f6bae-104">These models run on an Analysis Service instance that is configured for tabular mode, using an in-memory analytics engine for storage and fast table scans that aggregate and calculate data as it is requested.</span></span>  
  
 <span data-ttu-id="f6bae-105">A livello di codice, gli oggetti utilizzati in AMO, ADOMD.NET, XMLA o OLE DB sono fondamentalmente gli stessi sia per soluzioni tabulari che multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="f6bae-105">Programmatically, the objects you work with in AMO, ADOMD.NET, XMLA, or OLE DB are fundamentally the same for both tabular and multidimensional solutions.</span></span> <span data-ttu-id="f6bae-106">Se i requisiti della soluzione BI personalizzata vengono meglio soddisfatti da un database modello tabulare, è possibile utilizzare qualsiasi libreria client di Analysis Services e interfaccia di programmazione per integrare l'applicazione con i modelli tabulari in un'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f6bae-106">If the requirements of your custom BI solution are best met by a tabular model database, you can use any of the Analysis Services client libraries and programming interfaces to integrate your application with tabular models on an Analysis Services instance.</span></span> <span data-ttu-id="f6bae-107">Per eseguire query e calcoli sui dati del modello tabulare, è possibile utilizzare il linguaggio MDX o DAX incorporato nel codice.</span><span class="sxs-lookup"><span data-stu-id="f6bae-107">To query and calculate tabular model data, you can use either embedded MDX or DAX in your code.</span></span>  
  
 <span data-ttu-id="f6bae-108">In questa sezione vengono fornite ulteriori informazioni sull'utilizzo a livello di codice delle entità del modello tabulare e delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="f6bae-108">This section provides more information about how you can programmatically work with tabular model entities and their properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6bae-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f6bae-109">In This Section</span></span>  
 [<span data-ttu-id="f6bae-110">Annotazioni CSDL per Business Intelligence &#40;CSDLBI&#41;</span><span class="sxs-lookup"><span data-stu-id="f6bae-110">CSDL Annotations for Business Intelligence &#40;CSDLBI&#41;</span></span>](/analysis-services/csdlbi/csdl-annotations-for-business-intelligence-csdlbi)  
  
 [<span data-ttu-id="f6bae-111">Informazioni sul modello a oggetti tabulare</span><span class="sxs-lookup"><span data-stu-id="f6bae-111">Understanding the Tabular Object Model</span></span>](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
 [<span data-ttu-id="f6bae-112">Riferimento tecnico per le annotazioni di Business Intelligence per CSDL</span><span class="sxs-lookup"><span data-stu-id="f6bae-112">Technical Reference for BI Annotations to CSDL</span></span>](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl)  
  
 [<span data-ttu-id="f6bae-113">Interfaccia IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="f6bae-113">IMDEmbedded Interface</span></span>](imdembeddeddata-interface.md)  
  
## <a name="see-also"></a><span data-ttu-id="f6bae-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6bae-114">See Also</span></span>  
 <span data-ttu-id="f6bae-115">[Modellazione tabulare &#40;SSAS tabulare&#41;](../tabular-models/tabular-models-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="f6bae-115">[Tabular Modeling &#40;SSAS Tabular&#41;](../tabular-models/tabular-models-ssas.md) </span></span>  
 [<span data-ttu-id="f6bae-116">Progettazione di modelli tabulari &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="f6bae-116">Tabular Model Designer &#40;SSAS Tabular&#41;</span></span>](../tabular-model-designer-ssas-tabular.md)  
  
  
