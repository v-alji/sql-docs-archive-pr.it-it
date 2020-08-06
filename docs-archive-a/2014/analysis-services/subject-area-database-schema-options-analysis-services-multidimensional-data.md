---
title: Opzioni schema database area di interesse (generazione guidata schema) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.subjectareaschemaopts.f1
ms.assetid: 4c109bb8-e19d-412b-908f-bfdd7f872439
author: minewiskan
ms.author: owend
ms.openlocfilehash: 98460332478d02de823addcd113fb9c1e87d6958
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627422"
---
# <a name="subject-area-database-schema-options-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="1de55-102">Opzioni schema database area di interesse (Generazione guidata schema) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="1de55-102">Subject Area Database Schema Options (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="1de55-103">Utilizzare la pagina **Opzioni schema database area di interesse** per controllare la generazione dello schema e definire la modalità di mantenimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="1de55-103">Use the **Subject Area Database Schema Options** page to control how the schema is generated, as well as to define how data is preserved.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1de55-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1de55-104">Options</span></span>  
 <span data-ttu-id="1de55-105">**Nome schema**</span><span class="sxs-lookup"><span data-stu-id="1de55-105">**Owning schema**</span></span>  
 <span data-ttu-id="1de55-106">Consente di specificare il nome dello schema all'interno del nuovo database dell'area di interesse.</span><span class="sxs-lookup"><span data-stu-id="1de55-106">Specifies the name of the schema within the new subject area database.</span></span>  
  
 <span data-ttu-id="1de55-107">**Crea chiavi primarie nelle tabelle delle dimensioni**</span><span class="sxs-lookup"><span data-stu-id="1de55-107">**Create primary keys on dimension tables**</span></span>  
 <span data-ttu-id="1de55-108">Consente di creare chiavi primarie nelle tabelle delle dimensioni nello schema generato.</span><span class="sxs-lookup"><span data-stu-id="1de55-108">Creates primary keys on the dimension tables in the generated schema.</span></span> <span data-ttu-id="1de55-109">Se non si seleziona questa opzione non viene generato alcun indice.</span><span class="sxs-lookup"><span data-stu-id="1de55-109">No index is generated if you do not select this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1de55-110">Se non si seleziona questa opzione viene applicata l'integrità referenziale.</span><span class="sxs-lookup"><span data-stu-id="1de55-110">If you do not select this option, referential integrity is enforced.</span></span>  
  
 <span data-ttu-id="1de55-111">**Creare indici**</span><span class="sxs-lookup"><span data-stu-id="1de55-111">**Create indexes**</span></span>  
 <span data-ttu-id="1de55-112">Consente di creare indici su colonne chiave esterna nello schema generato.</span><span class="sxs-lookup"><span data-stu-id="1de55-112">Creates indexes on foreign key columns in the generated schema.</span></span>  
  
 <span data-ttu-id="1de55-113">**Applica integrità referenziale**</span><span class="sxs-lookup"><span data-stu-id="1de55-113">**Enforce referential integrity**</span></span>  
 <span data-ttu-id="1de55-114">Consente di applicare l'integrità referenziale all'interno dello schema generato.</span><span class="sxs-lookup"><span data-stu-id="1de55-114">Enforces referential integrity within the generated schema.</span></span> <span data-ttu-id="1de55-115">Se non si seleziona questa opzione le relazioni vengono create ma non applicate.</span><span class="sxs-lookup"><span data-stu-id="1de55-115">If you do not select this option, relationships are created but not enforced.</span></span>  
  
 <span data-ttu-id="1de55-116">**Mantieni dati in caso di rigenerazione**</span><span class="sxs-lookup"><span data-stu-id="1de55-116">**Preserve data on regeneration**</span></span>  
 <span data-ttu-id="1de55-117">Consente di mantenere i dati nel database dell'area di interesse al termine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1de55-117">Retains data in the subject area database when the wizard finishes.</span></span> <span data-ttu-id="1de55-118">Se non si seleziona questa opzione tutti i dati nel database dell'area di interesse possono essere cancellati senza notifica.</span><span class="sxs-lookup"><span data-stu-id="1de55-118">If you do not select this option, all the data in the subject area database may be erased without warning.</span></span>  
  
 <span data-ttu-id="1de55-119">**Popola tabelle dei tempi**</span><span class="sxs-lookup"><span data-stu-id="1de55-119">**Populate time table(s)**</span></span>  
 <span data-ttu-id="1de55-120">Consente di specificare la modalità di popolamento delle tabelle dei tempi da parte della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1de55-120">Specifies how the wizard populates the time tables.</span></span> <span data-ttu-id="1de55-121">Nella tabella seguente vengono descritti i valori possibili per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="1de55-121">The following table describes the possible values for this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1de55-122">Questa opzione è disponibile solo se la Generazione guidata schema viene avviata da un progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usando [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in modalità progetto.</span><span class="sxs-lookup"><span data-stu-id="1de55-122">This option is enabled only if Schema Generation Wizard is called from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in project mode.</span></span>  
  
|<span data-ttu-id="1de55-123">Valore</span><span class="sxs-lookup"><span data-stu-id="1de55-123">Value</span></span>|<span data-ttu-id="1de55-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1de55-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1de55-125">Popola</span><span class="sxs-lookup"><span data-stu-id="1de55-125">Populate</span></span>|<span data-ttu-id="1de55-126">Le tabelle dei tempi dell'area di interesse vengono popolate.</span><span class="sxs-lookup"><span data-stu-id="1de55-126">The subject area time tables are populated.</span></span>|  
|<span data-ttu-id="1de55-127">Non popolare</span><span class="sxs-lookup"><span data-stu-id="1de55-127">Do not populate</span></span>|<span data-ttu-id="1de55-128">Le tabelle dei tempi dell'area di interesse non vengono popolate.</span><span class="sxs-lookup"><span data-stu-id="1de55-128">The subject area time tables are not populated.</span></span>|  
|<span data-ttu-id="1de55-129">Popola solo se vuota</span><span class="sxs-lookup"><span data-stu-id="1de55-129">Populate only if empty</span></span>|<span data-ttu-id="1de55-130">Le tabelle dei tempi dell'area di interesse vengono popolate solo se sono vuote.</span><span class="sxs-lookup"><span data-stu-id="1de55-130">The subject area time tables are populated only if they are empty.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1de55-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1de55-131">See Also</span></span>  
 [<span data-ttu-id="1de55-132">Guida sensibile al contesto della generazione guidata schema &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="1de55-132">Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;</span></span>](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md)  
  
  
