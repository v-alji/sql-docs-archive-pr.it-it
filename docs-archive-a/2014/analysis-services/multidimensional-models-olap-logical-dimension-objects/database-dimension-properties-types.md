---
title: Tipi di dimensione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- time dimensions [Analysis Services]
- quantitative dimensions [Analysis Services]
- BillOfMaterials dimension [Analysis Services]
- geography dimensions
- utility dimensions [Analysis Services]
- channel dimensions
- dimensions [Analysis Services], types
- products dimensions [Analysis Services]
- account dimensions [Analysis Services]
- organization dimensions
- currency dimensions [Analysis Services]
- rates dimensions
- promotion dimensions
- scenario dimensions [Analysis Services]
- customers dimensions [Analysis Services]
- Type property
ms.assetid: bd3195da-e762-4c98-b643-34c76e842343
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5e0c16a57081aa1d9ed3cc6964d1f17fa7135986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638126"
---
# <a name="dimension-types"></a><span data-ttu-id="5c45f-102">Tipi di dimensioni</span><span class="sxs-lookup"><span data-stu-id="5c45f-102">Dimension Types</span></span>
  <span data-ttu-id="5c45f-103">L'impostazione della proprietà `Type` offre informazioni sui contenuti di una dimensione alle applicazioni server e client.</span><span class="sxs-lookup"><span data-stu-id="5c45f-103">The `Type` property setting provides information about the contents of a dimension to server and client applications.</span></span> <span data-ttu-id="5c45f-104">In alcuni casi, l'impostazione `Type` offre informazioni solo alle applicazioni client ed è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="5c45f-104">In some cases, the `Type` setting only provides guidance for client applications and is optional.</span></span> <span data-ttu-id="5c45f-105">In altri casi, ad esempio le dimensioni `Accounts` o `Time`, le impostazioni della proprietà `Type` per la dimensione e i relativi attributi determinano comportamenti specifici basati sul server e possono essere necessarie per implementare determinati comportamenti nel cubo.</span><span class="sxs-lookup"><span data-stu-id="5c45f-105">In other cases, such as `Accounts` or `Time` dimensions, the `Type` property settings for the dimension and its attributes determine specific server-based behaviors and may be required to implement certain behaviors in the cube.</span></span> <span data-ttu-id="5c45f-106">La proprietà `Type` di una dimensione, ad esempio, può essere impostata su `Accounts` per indicare alle applicazioni client che la dimensione standard contiene attributi Conto.</span><span class="sxs-lookup"><span data-stu-id="5c45f-106">For example, the `Type` property of a dimension can be set to `Accounts` to indicate to client applications that the standard dimension contains account attributes.</span></span> <span data-ttu-id="5c45f-107">Per ulteriori informazioni sulle dimensioni dell'ora, dell'account e della valuta, vedere [creare una dimensione di tipo date](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [creare un account Finance della dimensione di tipo padre-figlio](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md)e [creare una dimensione di tipo valuta](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="5c45f-107">For more information about time, account, and currency dimensions, see [Create a Date type Dimension](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [Create a Finance Account of parent-child type Dimension](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md), and [Create a Currency type Dimension](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md).</span></span>  
  
 <span data-ttu-id="5c45f-108">L'impostazione predefinita per il tipo di dimensione è `Regular`, che non indica alcun tipo specifico di contenuto della dimensione.</span><span class="sxs-lookup"><span data-stu-id="5c45f-108">The default setting for the dimension type is `Regular`, which makes no assumptions about the contents of the dimension.</span></span> <span data-ttu-id="5c45f-109">Questa è l'impostazione predefinita per tutte le dimensioni al momento della creazione, a meno che in fase di definizione della dimensione tramite la Creazione guidata dimensione non si specifichi `Time`.</span><span class="sxs-lookup"><span data-stu-id="5c45f-109">This is the default setting for all dimensions when you initially define a dimension unless you specify `Time` when defining the dimension using the Dimension Wizard.</span></span> <span data-ttu-id="5c45f-110">È inoltre consigliabile lasciare `Regular` come tipo di dimensione impostato, se nella Creazione guidata dimensione non è elencato alcun tipo di dimensione appropriato.</span><span class="sxs-lookup"><span data-stu-id="5c45f-110">You should also leave `Regular` as the dimension type if the Dimension Wizard does not list an appropriate type for Dimension type.</span></span>  
  
## <a name="available-dimension-types"></a><span data-ttu-id="5c45f-111">Tipi di dimensioni disponibili</span><span class="sxs-lookup"><span data-stu-id="5c45f-111">Available Dimension Types</span></span>  
 <span data-ttu-id="5c45f-112">Nella tabella seguente vengono descritti i tipi di dimensione disponibili in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c45f-112">The following table describes the dimension types available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="5c45f-113">Tipo dimensione</span><span class="sxs-lookup"><span data-stu-id="5c45f-113">Dimension type</span></span>|<span data-ttu-id="5c45f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c45f-114">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5c45f-115">Normale</span><span class="sxs-lookup"><span data-stu-id="5c45f-115">Regular</span></span>|<span data-ttu-id="5c45f-116">Dimensione il cui tipo non è stato impostato in base a un valore speciale.</span><span class="sxs-lookup"><span data-stu-id="5c45f-116">A dimension whose type has not been set to a special dimension type.</span></span>|  
|<span data-ttu-id="5c45f-117">Tempo</span><span class="sxs-lookup"><span data-stu-id="5c45f-117">Time</span></span>|<span data-ttu-id="5c45f-118">Dimensione i cui attributi rappresentano periodi di tempo, ad esempio anni, semestri, trimestri, mesi e giorni.</span><span class="sxs-lookup"><span data-stu-id="5c45f-118">A dimension whose attributes represent time periods, such as years, semesters, quarters, months, and days.</span></span>|  
|<span data-ttu-id="5c45f-119">Organization</span><span class="sxs-lookup"><span data-stu-id="5c45f-119">Organization</span></span>|<span data-ttu-id="5c45f-120">Dimensione i cui attributi rappresentano informazioni sull'organizzazione, ad esempio dipendenti o filiali.</span><span class="sxs-lookup"><span data-stu-id="5c45f-120">A dimension whose attributes represent organizational information, such as employees or subsidiaries.</span></span>|  
|<span data-ttu-id="5c45f-121">Area geografica</span><span class="sxs-lookup"><span data-stu-id="5c45f-121">Geography</span></span>|<span data-ttu-id="5c45f-122">Dimensione i cui attributi rappresentano informazioni geografiche, ad esempio città o CAP.</span><span class="sxs-lookup"><span data-stu-id="5c45f-122">A dimension whose attributes represent geographic information, such as cities or postal codes.</span></span>|  
|<span data-ttu-id="5c45f-123">BillOfMaterials</span><span class="sxs-lookup"><span data-stu-id="5c45f-123">BillOfMaterials</span></span>|<span data-ttu-id="5c45f-124">Dimensione i cui attributi rappresentano informazioni relative alle scorte o alla produzione, ad esempio elenchi di parti di prodotti.</span><span class="sxs-lookup"><span data-stu-id="5c45f-124">A dimension whose attributes represent inventory or manufacturing information, such as parts lists for products.</span></span>|  
|<span data-ttu-id="5c45f-125">Account</span><span class="sxs-lookup"><span data-stu-id="5c45f-125">Accounts</span></span>|<span data-ttu-id="5c45f-126">Dimensione i cui attributi rappresentano un grafico dei conti per la generazione di report finanziari.</span><span class="sxs-lookup"><span data-stu-id="5c45f-126">A dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>|  
|<span data-ttu-id="5c45f-127">Clienti</span><span class="sxs-lookup"><span data-stu-id="5c45f-127">Customers</span></span>|<span data-ttu-id="5c45f-128">Dimensione i cui attributi rappresentano informazioni sui clienti o sui contatti.</span><span class="sxs-lookup"><span data-stu-id="5c45f-128">A dimension whose attributes represent customer or contact information.</span></span>|  
|<span data-ttu-id="5c45f-129">Prodotti</span><span class="sxs-lookup"><span data-stu-id="5c45f-129">Products</span></span>|<span data-ttu-id="5c45f-130">Dimensione i cui attributi rappresentano informazioni sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="5c45f-130">A dimension whose attributes represent product information.</span></span>|  
|<span data-ttu-id="5c45f-131">Scenario</span><span class="sxs-lookup"><span data-stu-id="5c45f-131">Scenario</span></span>|<span data-ttu-id="5c45f-132">Dimensione i cui attributi rappresentano informazioni di pianificazione o di analisi strategica.</span><span class="sxs-lookup"><span data-stu-id="5c45f-132">A dimension whose attributes represent planning or strategic analysis information.</span></span>|  
|<span data-ttu-id="5c45f-133">Quantitative</span><span class="sxs-lookup"><span data-stu-id="5c45f-133">Quantitative</span></span>|<span data-ttu-id="5c45f-134">Dimensione i cui attributi rappresentano informazioni sulle quantità.</span><span class="sxs-lookup"><span data-stu-id="5c45f-134">A dimension whose attributes represent quantitative information.</span></span>|  
|<span data-ttu-id="5c45f-135">Utilità</span><span class="sxs-lookup"><span data-stu-id="5c45f-135">Utility</span></span>|<span data-ttu-id="5c45f-136">Dimensione i cui attributi rappresentano informazioni di vario tipo.</span><span class="sxs-lookup"><span data-stu-id="5c45f-136">A dimension whose attributes represent miscellaneous information.</span></span>|  
|<span data-ttu-id="5c45f-137">Valuta</span><span class="sxs-lookup"><span data-stu-id="5c45f-137">Currency</span></span>|<span data-ttu-id="5c45f-138">Questo tipo di dimensione contiene dati e metadati relativi alla valuta.</span><span class="sxs-lookup"><span data-stu-id="5c45f-138">This type of dimension contains currency data and metadata.</span></span>|  
|<span data-ttu-id="5c45f-139">Rates</span><span class="sxs-lookup"><span data-stu-id="5c45f-139">Rates</span></span>|<span data-ttu-id="5c45f-140">Dimensione i cui attributi rappresentano informazioni sui tassi valutari.</span><span class="sxs-lookup"><span data-stu-id="5c45f-140">A dimension whose attributes represent currency rate information.</span></span>|  
|<span data-ttu-id="5c45f-141">Channel</span><span class="sxs-lookup"><span data-stu-id="5c45f-141">Channel</span></span>|<span data-ttu-id="5c45f-142">Dimensione i cui attributi rappresentano informazioni sul canale.</span><span class="sxs-lookup"><span data-stu-id="5c45f-142">A dimension whose attributes represent channel information.</span></span>|  
|<span data-ttu-id="5c45f-143">Promotion</span><span class="sxs-lookup"><span data-stu-id="5c45f-143">Promotion</span></span>|<span data-ttu-id="5c45f-144">Dimensione i cui attributi rappresentano informazioni sulle promozioni marketing.</span><span class="sxs-lookup"><span data-stu-id="5c45f-144">A dimension whose attributes represent marketing promotion information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c45f-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c45f-145">See Also</span></span>  
 <span data-ttu-id="5c45f-146">[Creare una dimensione utilizzando una tabella esistente](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="5c45f-146">[Create a Dimension by Using an Existing Table](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="5c45f-147">Dimensioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="5c45f-147">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
