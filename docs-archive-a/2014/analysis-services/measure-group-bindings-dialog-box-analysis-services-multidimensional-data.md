---
title: Finestra di dialogo Associazioni gruppo di misure (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.dimensionusage.definerelationship.measuregroupbindings.f1
helpviewer_keywords:
- Measure Group Bindings dialog box
ms.assetid: ed642780-5350-438e-af73-b9ceab3f876d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 78693901a5898b140d6efeed16b6f0eaa7577e69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725144"
---
# <a name="measure-group-bindings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="f3cdb-102">Finestra di dialogo Associazioni gruppo di misure (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="f3cdb-102">Measure Group Bindings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="f3cdb-103">La finestra di dialogo **Associazioni gruppo di misure** consente di creare e modificare le relazioni dirette tra gli attributi di non granularità di una dimensione del cubo e le colonne di un gruppo di misure per una relazione tra dimensioni regolari nonché di specificare nella finestra di dialogo **Definisci relazione** le opzioni di elaborazione dei valori Null per tutti gli attributi di una dimensione del cubo.</span><span class="sxs-lookup"><span data-stu-id="f3cdb-103">Use the **Measure Group Bindings** dialog box to create and modify direct relationships between non-granularity attributes in a cube dimension and columns in a measure group for a regular dimension relationship, as well as to specify null processing options for any attribute in a cube dimension, from the **Define Relationship** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f3cdb-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f3cdb-104">Options</span></span>  
 <span data-ttu-id="f3cdb-105">**Tabella del gruppo di misure**</span><span class="sxs-lookup"><span data-stu-id="f3cdb-105">**Measure group table**</span></span>  
 <span data-ttu-id="f3cdb-106">Consente di visualizzare il nome della tabella dei fatti per il gruppo di misure selezionato.</span><span class="sxs-lookup"><span data-stu-id="f3cdb-106">Displays the name of the fact table for the selected measure group.</span></span>  
  
 <span data-ttu-id="f3cdb-107">**Attributes (Attributi)**</span><span class="sxs-lookup"><span data-stu-id="f3cdb-107">**Attributes**</span></span>  
 <span data-ttu-id="f3cdb-108">Consente di visualizzare una griglia di attributi e di tabelle delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f3cdb-108">Displays a grid of attributes and dimension tables.</span></span> <span data-ttu-id="f3cdb-109">Selezionare un attributo per creare o modificare le proprietà di **Relazione** per l'attributo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f3cdb-109">Select an attribute to create or modify properties in **Relationship** for the selected attribute.</span></span> <span data-ttu-id="f3cdb-110">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3cdb-110">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="f3cdb-111">Opzione</span><span class="sxs-lookup"><span data-stu-id="f3cdb-111">Option</span></span>|<span data-ttu-id="f3cdb-112">Definizione</span><span class="sxs-lookup"><span data-stu-id="f3cdb-112">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="f3cdb-113">**Nome attributo**</span><span class="sxs-lookup"><span data-stu-id="f3cdb-113">**Attribute Name**</span></span>|<span data-ttu-id="f3cdb-114">Consente di visualizzare il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f3cdb-114">Displays the name of the attribute.</span></span>|  
|<span data-ttu-id="f3cdb-115">**Tabella della dimensione**</span><span class="sxs-lookup"><span data-stu-id="f3cdb-115">**Dimension Table**</span></span>|<span data-ttu-id="f3cdb-116">Consente di visualizzare il nome della tabella della dimensione su cui è basato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="f3cdb-116">Displays the name of the dimension table on which the attribute is based.</span></span>|  
  
 <span data-ttu-id="f3cdb-117">**Relazione**</span><span class="sxs-lookup"><span data-stu-id="f3cdb-117">**Relationship**</span></span>  
 <span data-ttu-id="f3cdb-118">Consente di visualizzare una griglia di relazioni tra le colonne della tabella delle dimensioni per l'attributo selezionato e le colonne della tabella dei fatti per il gruppo di misure selezionato nonché l'opzione di elaborazione dei valori Null relativa alla relazione.</span><span class="sxs-lookup"><span data-stu-id="f3cdb-118">Displays a grid of relationships between dimension table columns for the selected attribute and fact table columns for the selected measure group as well as the null processing option for the relationship.</span></span> <span data-ttu-id="f3cdb-119">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3cdb-119">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="f3cdb-120">Opzione</span><span class="sxs-lookup"><span data-stu-id="f3cdb-120">Option</span></span>|<span data-ttu-id="f3cdb-121">Definizione</span><span class="sxs-lookup"><span data-stu-id="f3cdb-121">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="f3cdb-122">**Colonne dimensione**</span><span class="sxs-lookup"><span data-stu-id="f3cdb-122">**Dimension Columns**</span></span>|<span data-ttu-id="f3cdb-123">Consente di visualizzare le colonne della tabella delle dimensioni su cui è basato l'attributo selezionato in **Attributi** .</span><span class="sxs-lookup"><span data-stu-id="f3cdb-123">Displays the columns from the dimension table on which the attribute selected in **Attributes** is based.</span></span>|  
|<span data-ttu-id="f3cdb-124">**Colonne gruppo di misure**</span><span class="sxs-lookup"><span data-stu-id="f3cdb-124">**Measure Group Columns**</span></span>|<span data-ttu-id="f3cdb-125">Consente di selezionare **Ereditate dalla dimensione** per utilizzare la relazione del gruppo di misure ereditata dalla dimensione oppure selezionare una colonna della tabella dei fatti su cui è basato il gruppo di misure per definire in modo esplicito una relazione.</span><span class="sxs-lookup"><span data-stu-id="f3cdb-125">Select either **Inherited from dimension** to use the measure group relationship inherited from the dimension, or select a column from the fact table on which the measure group is based to explicitly define a relationship.</span></span>|  
|<span data-ttu-id="f3cdb-126">**Elaborazione valori Null**</span><span class="sxs-lookup"><span data-stu-id="f3cdb-126">**Null Processing**</span></span>|<span data-ttu-id="f3cdb-127">Consente di selezionare un'opzione di elaborazione dei valori Null per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="f3cdb-127">Select a null processing option for the attribute.</span></span> <span data-ttu-id="f3cdb-128">Per altre informazioni sulle opzioni di elaborazione dei valori Null, vedere [Elemento NullProcessing &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span><span class="sxs-lookup"><span data-stu-id="f3cdb-128">For more information about null processing options, see [NullProcessing Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3cdb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3cdb-129">See Also</span></span>  
 <span data-ttu-id="f3cdb-130">[Finestra di dialogo Definisci relazione &#40;Analysis Services-Dati multidimensionali&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f3cdb-130">[Define Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="f3cdb-131">Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="f3cdb-131">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
