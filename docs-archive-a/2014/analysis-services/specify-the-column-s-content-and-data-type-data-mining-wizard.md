---
title: Specificare il tipo di dati e il contenuto della colonna&#39;(creazione guidata modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifycontentdatatype.f1
ms.assetid: 7061f674-e806-46f2-8c15-e260a3c69a17
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66af7280e444036468b9cc33a131993524d3586d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635755"
---
# <a name="specify-the-column39s-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="b58af-102">Specificare il contenuto e il tipo di dati della colonna&#39;(creazione guidata modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="b58af-102">Specify the Column&#39;s Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="b58af-103">Utilizzare la pagina **Impostazione tipo di dati e contenuto delle colonne** per modificare la colonna e i tipi di contenuto già impostati durante la creazione guidata.</span><span class="sxs-lookup"><span data-stu-id="b58af-103">Use the **Specify the Column's Content and Data Type** page to modify the column and content types that have already been set by the wizard.</span></span> <span data-ttu-id="b58af-104">Nella creazione guidata vengono utilizzati i tipi di dati delle colonne di origine e le funzionalità dell'algoritmo selezionato per stabilire i dati predefiniti e i tipi di contenuto per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="b58af-104">The wizard uses the data types of the source columns and the capabilities of the selected algorithm to determine the default data and content types for each column.</span></span>  
  
 <span data-ttu-id="b58af-105">**Per altre informazioni:** [Creazione guidata modello di data mining &#40;Analysis Services - Data mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md) e [Creare una struttura di data mining relazionale](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="b58af-105">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="b58af-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b58af-106">Options</span></span>  
 <span data-ttu-id="b58af-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b58af-107">**Columns**</span></span>  
 <span data-ttu-id="b58af-108">Elenco delle colonne definite nella pagina **Impostazione dati di training** della creazione guidata.</span><span class="sxs-lookup"><span data-stu-id="b58af-108">A list of the columns that are defined in the **Specify the Training Data** page of the wizard.</span></span>  
  
 <span data-ttu-id="b58af-109">**Tipo di contenuto**</span><span class="sxs-lookup"><span data-stu-id="b58af-109">**Content Type**</span></span>  
 <span data-ttu-id="b58af-110">Tipo di contenuto assegnato a ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="b58af-110">The content type that is assigned to each column.</span></span> <span data-ttu-id="b58af-111">Fare clic in una cella per modificare il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b58af-111">Click inside a cell to change the content type.</span></span> <span data-ttu-id="b58af-112">Per altre informazioni sui tipi di contenuto, vedere [Tipi di contenuto &#40;Data mining&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b58af-112">For more information about content types, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="b58af-113">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="b58af-113">**Data Type**</span></span>  
 <span data-ttu-id="b58af-114">Tipo di dati assegnato a ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="b58af-114">The data types that are assigned to each column.</span></span> <span data-ttu-id="b58af-115">Fare clic in una cella per modificare il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="b58af-115">Click inside a cell to change the data type.</span></span> <span data-ttu-id="b58af-116">Per altre informazioni sui tipi di dati di, vedere [Tipi di dati &#40;data mining&#41;](data-mining/data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b58af-116">For more information about data types, see [Data Types &#40;Data Mining&#41;](data-mining/data-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="b58af-117">**Detect**</span><span class="sxs-lookup"><span data-stu-id="b58af-117">**Detect**</span></span>  
 <span data-ttu-id="b58af-118">Fare clic su questa opzione per rilevare automaticamente i tipi di contenuto continui e discreti per le colonne numeriche.</span><span class="sxs-lookup"><span data-stu-id="b58af-118">Click to automatically detect the continuous and discrete content types for numeric column.</span></span> <span data-ttu-id="b58af-119">Questa opzione non si applica alle strutture di data mining basate su origini dei dati OLAP.</span><span class="sxs-lookup"><span data-stu-id="b58af-119">This does not apply to mining structures that are based on OLAP data sources.</span></span> <span data-ttu-id="b58af-120">Per le strutture di data mining OLAP, durante la creazione guidata vengono rilevati automaticamente i tipi di contenuto e scelti quelli compatibili con l'algoritmo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b58af-120">For OLAP mining structures, the wizard automatically detects content types and chooses a type that is compatible with the selected algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58af-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b58af-121">See Also</span></span>  
 <span data-ttu-id="b58af-122">[Completamento della procedura guidata &#40;creazione guidata modello di data mining&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="b58af-122">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="b58af-123">[Guida sensibile al contesto della creazione guidata modello di data mining &#40;Analysis Services-&#41;di data mining](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b58af-123">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="b58af-124">Specificare i dati di training &#40;creazione guidata modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b58af-124">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
