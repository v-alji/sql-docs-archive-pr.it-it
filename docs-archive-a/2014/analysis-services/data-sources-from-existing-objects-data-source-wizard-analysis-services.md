---
title: Origini dati da oggetti esistenti (creazione guidata origine dati) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourcewizard.specifyobject.f1
ms.assetid: e6ef6dea-9db8-45c4-8959-f9febd7caf7b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 621c938f4902c95dee1e2fcccb0f292597a565f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716963"
---
# <a name="data-sources-from-existing-objects-data-source-wizard-analysis-services"></a><span data-ttu-id="a2ecb-102">Origini dati da oggetti esistenti (Creazione guidata origine dati) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="a2ecb-102">Data sources from existing objects (Data Source Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="a2ecb-103">La pagina **Origini dati da oggetti esistenti** consente di specificare un'origine dei dati o un progetto esistente su cui basare la nuova origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-103">Use the **Data sources from existing objects** page to specify an existing data source or project on which to base the new data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a2ecb-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a2ecb-104">Options</span></span>  
 <span data-ttu-id="a2ecb-105">**Crea un'origine dei dati basata su un'origine dei dati esistente nella soluzione**</span><span class="sxs-lookup"><span data-stu-id="a2ecb-105">**Create a data source based on an existing data source in your solution**</span></span>  
 <span data-ttu-id="a2ecb-106">Selezionare questa opzione per basare la nuova origine dei dati su un'origine dei dati esistente nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-106">Select to base the new data source on an existing data source in the solution.</span></span> <span data-ttu-id="a2ecb-107">Quando un progetto che utilizza la nuova origine dei dati viene compilato, aggiornato o distribuito, la nuova origine dei dati acquisisce le impostazioni dall'origine dei dati specificata quando si seleziona questa opzione.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-107">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires the settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="a2ecb-108">**Origine dati**</span><span class="sxs-lookup"><span data-stu-id="a2ecb-108">**Data source**</span></span>  
 <span data-ttu-id="a2ecb-109">Consente di selezionare un'origine dei dati su cui basare la nuova origine dei dati dall'elenco delle origini dei dati, raggruppate per progetto.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-109">Select a data source on which you want to base the new data source from the list of data sources, which is grouped by project.</span></span>  
  
 <span data-ttu-id="a2ecb-110">**Crea un'origine dei dati basata su un progetto di Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="a2ecb-110">**Create a data source based on an Analysis Services project**</span></span>  
 <span data-ttu-id="a2ecb-111">Selezionare questa finestra per creare una nuova origine dei dati che fa riferimento a un altro [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] progetto nella soluzione corrente.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-111">Select to create a new data source that references another [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in the current solution.</span></span> <span data-ttu-id="a2ecb-112">La nuova origine dei dati acquisisce le impostazioni dalle proprietà `TargetServer` e `TargetDatabase` del progetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-112">The new data source acquires settings from the `TargetServer` and `TargetDatabase` properties of the selected project.</span></span> <span data-ttu-id="a2ecb-113">Quando un progetto che utilizza la nuova origine dei dati viene compilato, aggiornato o distribuito, la nuova origine dei dati acquisisce le impostazioni dall'origine dei dati specificata quando si seleziona questa opzione.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-113">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="a2ecb-114">**Progetto**</span><span class="sxs-lookup"><span data-stu-id="a2ecb-114">**Project**</span></span>  
 <span data-ttu-id="a2ecb-115">Consente di selezionare il progetto a cui fare riferimento nella nuova origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-115">Select the project that you want to reference in the new data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ecb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2ecb-116">See Also</span></span>  
 <span data-ttu-id="a2ecb-117">[Guida sensibile al contesto della creazione guidata origine dati &#40;Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="a2ecb-117">[Data Source Wizard F1 Help &#40;Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span></span>  
 <span data-ttu-id="a2ecb-118">[Origini dati nei modelli multidimensionali](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="a2ecb-118">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="a2ecb-119">Origini dati supportate &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="a2ecb-119">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
