---
title: Definire il comportamento di funzioni semiadditive (configurazione guidata funzionalità di Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.semiadditivememberdetection.f1
ms.assetid: e57080ba-ce96-40f8-bca7-6701d1725b3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5a3c46de038a7e45dcb39805e324260676a03228
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712632"
---
# <a name="define-semiadditive-behavior-business-intelligence-wizard"></a><span data-ttu-id="f8870-102">Definizione funzioni semiadditive (Configurazione guidata funzionalità di Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="f8870-102">Define Semiadditive Behavior (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="f8870-103">La pagina **Definizione funzioni semiadditive** consente di attivare o disattivare le funzioni semiadditive sulle misure.</span><span class="sxs-lookup"><span data-stu-id="f8870-103">Use the **Define Semiadditive Behavior** page to enable or disable semi-additive behavior on measures.</span></span> <span data-ttu-id="f8870-104">Tali funzioni determinano le modalità di aggregazione in base a una dimensione temporale delle misure contenute in un cubo.</span><span class="sxs-lookup"><span data-stu-id="f8870-104">Semi-additive behavior determines how measures that are contained by a cube are aggregated over a time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8870-105">Ad eccezione di LastChild disponibile nell'edizione Standard, le funzioni semiadditive sono disponibili solo in Business Intelligence o nelle edizioni Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f8870-105">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span> <span data-ttu-id="f8870-106">Inoltre, poiché le funzioni semiadditive vengono definite solo sulle misure e non sulle dimensioni, questa pagina non verrà visualizzata nella Configurazione guidata funzionalità di Business Intelligence se avviata da Progettazione dimensioni oppure facendo clic con il pulsante destro del mouse su una dimensione in Esplora soluzioni in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8870-106">Furthermore, because semiadditive behavior is defined only on measures and not dimensions, you will not find this page in the Business Intelligence Wizard if it was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="f8870-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f8870-107">Options</span></span>  
 <span data-ttu-id="f8870-108">**Disabilita funzioni semiadditive**</span><span class="sxs-lookup"><span data-stu-id="f8870-108">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="f8870-109">Consente di disabilitare le funzioni semiadditive in tutte le misure contenute nel cubo.</span><span class="sxs-lookup"><span data-stu-id="f8870-109">Disables semi-additive behavior in all measures contained by the cube.</span></span>  
  
 <span data-ttu-id="f8870-110">**La procedura guidata ha rilevato la \<dimension name> dimensione di tipo conti, che contiene membri funzioni semiadditive. Il server aggrega i membri di questa dimensione in base al comportamento funzioni semiadditive specificato per ogni tipo di conto.**</span><span class="sxs-lookup"><span data-stu-id="f8870-110">**The wizard has detected the \<dimension name> account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="f8870-111">Abilita le funzioni semiadditive per le dimensioni di tipo Conti che contengono membri semiadditivi.</span><span class="sxs-lookup"><span data-stu-id="f8870-111">Enables semi-additive behavior for account dimensions that contain semi-additive members.</span></span> <span data-ttu-id="f8870-112">Se si seleziona questa opzione, le funzioni di aggregazione vengono impostate per tutti i gruppi di misure che fanno riferimento alla dimensione di tipo Conti in `ByAccount`.</span><span class="sxs-lookup"><span data-stu-id="f8870-112">Selecting this option sets the aggregation function of all measures in measure groups that reference the account dimension to `ByAccount`.</span></span>  
  
 <span data-ttu-id="f8870-113">Per altre informazioni sulle dimensioni di tipo Conti, vedere [Creare un conto finanziario della dimensione di tipo padre-figlio](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span><span class="sxs-lookup"><span data-stu-id="f8870-113">For more information about account dimensions, see [Create a Finance Account of parent-child type Dimension](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span></span>  
  
 <span data-ttu-id="f8870-114">**Definisci funzioni semiadditive per singole misure**</span><span class="sxs-lookup"><span data-stu-id="f8870-114">**Define semiadditive behavior for individual members**</span></span>  
 <span data-ttu-id="f8870-115">Abilita le funzioni semiadditive e specifica la funzione di aggregazione semiadditiva per misure specifiche.</span><span class="sxs-lookup"><span data-stu-id="f8870-115">Enables semi-additive behavior and specifies the semi-additive aggregation function for specific measures.</span></span> <span data-ttu-id="f8870-116">La funzione di aggregazione viene applicata a tutte le dimensioni a cui fa riferimento il gruppo di misure che contiene la misura.</span><span class="sxs-lookup"><span data-stu-id="f8870-116">The aggregation function applies to all dimensions that are referenced by the measure group that contains the measure.</span></span>  
  
 <span data-ttu-id="f8870-117">**Misure**</span><span class="sxs-lookup"><span data-stu-id="f8870-117">**Measures**</span></span>  
 <span data-ttu-id="f8870-118">Consente di visualizzare il nome di una misura contenuta nel cubo.</span><span class="sxs-lookup"><span data-stu-id="f8870-118">Displays the name of a measure contained by the cube.</span></span>  
  
 <span data-ttu-id="f8870-119">**Funzioni semiadditive (funzione)**</span><span class="sxs-lookup"><span data-stu-id="f8870-119">**Semiadditive Function**</span></span>  
 <span data-ttu-id="f8870-120">Consente di selezionare la funzione di aggregazione per la misura selezionata.</span><span class="sxs-lookup"><span data-stu-id="f8870-120">Select the aggregation function for the selected measure.</span></span> <span data-ttu-id="f8870-121">Nella tabella seguente vengono elencate le funzioni di aggregazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="f8870-121">The following table lists the aggregation functions that are available.</span></span>  
  
|<span data-ttu-id="f8870-122">Valore</span><span class="sxs-lookup"><span data-stu-id="f8870-122">Value</span></span>|<span data-ttu-id="f8870-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8870-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8870-124">**AverageOfChildren**</span><span class="sxs-lookup"><span data-stu-id="f8870-124">**AverageOfChildren**</span></span>|<span data-ttu-id="f8870-125">Aggregazione eseguita restituendo la media degli elementi figlio della misura.</span><span class="sxs-lookup"><span data-stu-id="f8870-125">Aggregated by returning the average of the measure's children.</span></span>|  
|`ByAccount`|<span data-ttu-id="f8870-126">Aggregazione eseguita mediante la funzione di aggregazione associata al tipo di conto specificato di un attributo in una dimensione di tipo Conti.</span><span class="sxs-lookup"><span data-stu-id="f8870-126">Aggregated by the aggregation function associated with the specified account type of an attribute in an account dimension.</span></span>|  
|`Count`|<span data-ttu-id="f8870-127">Aggregazione eseguita mediante la funzione `Count`.</span><span class="sxs-lookup"><span data-stu-id="f8870-127">Aggregated using the `Count` function.</span></span>|  
|`DistinctCount`|<span data-ttu-id="f8870-128">Aggregazione eseguita mediante la funzione `DistinctCount`.</span><span class="sxs-lookup"><span data-stu-id="f8870-128">Aggregated using the `DistinctCount` function.</span></span>|  
|<span data-ttu-id="f8870-129">**FirstChild**</span><span class="sxs-lookup"><span data-stu-id="f8870-129">**FirstChild**</span></span>|<span data-ttu-id="f8870-130">Aggregazione eseguita restituendo il primo membro figlio della misura in base a una dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="f8870-130">Aggregated by returning the measure's first child member over a time dimension.</span></span>|  
|<span data-ttu-id="f8870-131">**FirstNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="f8870-131">**FirstNonEmpty**</span></span>|<span data-ttu-id="f8870-132">Aggregazione eseguita restituendo il primo membro non vuoto della misura in base a una dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="f8870-132">Aggregated by returning the measure's first nonempty member over a time dimension.</span></span>|  
|<span data-ttu-id="f8870-133">**LastChild**</span><span class="sxs-lookup"><span data-stu-id="f8870-133">**LastChild**</span></span>|<span data-ttu-id="f8870-134">Aggregazione eseguita restituendo l'ultimo membro figlio della misura in base a una dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="f8870-134">Aggregated by returning the measure's last child member over a time dimension.</span></span>|  
|<span data-ttu-id="f8870-135">**LastNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="f8870-135">**LastNonEmpty**</span></span>|<span data-ttu-id="f8870-136">Aggregazione eseguita restituendo l'ultimo membro non vuoto della misura in base a una dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="f8870-136">Aggregated by returning the measure's last nonempty member over a time dimension.</span></span>|  
|`Max`|<span data-ttu-id="f8870-137">Aggregazione eseguita mediante la funzione `Max`.</span><span class="sxs-lookup"><span data-stu-id="f8870-137">Aggregated using the `Max` function.</span></span>|  
|`Min`|<span data-ttu-id="f8870-138">Aggregazione eseguita mediante la funzione `Min`.</span><span class="sxs-lookup"><span data-stu-id="f8870-138">Aggregated using the `Min` function.</span></span>|  
|<span data-ttu-id="f8870-139">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="f8870-139">**None**</span></span>|<span data-ttu-id="f8870-140">Aggregazione non eseguita.</span><span class="sxs-lookup"><span data-stu-id="f8870-140">No aggregation performed.</span></span>|  
|`Sum`|<span data-ttu-id="f8870-141">Aggregazione eseguita mediante la funzione `Sum`.</span><span class="sxs-lookup"><span data-stu-id="f8870-141">Aggregated using the `Sum` function.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f8870-142">Le selezioni effettuate per questa opzione vengono applicate solo se **Definisci funzioni semiadditive per singole misure** è selezionato.</span><span class="sxs-lookup"><span data-stu-id="f8870-142">Selections made for this option apply only if **Define semiadditive behavior for individual members** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8870-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8870-143">See Also</span></span>  
 <span data-ttu-id="f8870-144">[Guida sensibile al contesto della configurazione guidata funzionalità di Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="f8870-144">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="f8870-145">[Progettazione cubi &#40;Analysis Services-Dati multidimensionali&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f8870-145">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="f8870-146">Progettazione dimensioni &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="f8870-146">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
