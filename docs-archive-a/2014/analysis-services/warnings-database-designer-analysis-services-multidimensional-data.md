---
title: Avvisi (Progettazione database) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.databasedesigner.warnings.f1
ms.assetid: 13f58b4d-f345-4fbc-ae2d-b3c8290a797d
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf635460187fe56f4811de5090cada002ea8ca3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626897"
---
# <a name="warnings-database-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="d40e3-102">Avvisi (Progettazione database) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="d40e3-102">Warnings (Database Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d40e3-103">Usare la scheda **Avvisi** per visualizzare e ignorare totalmente le regole e per visualizzare e riattivare istanze specifiche di avvisi ignorati.</span><span class="sxs-lookup"><span data-stu-id="d40e3-103">Use the **Warnings** tab to view and dismiss rules globally, and to view and re-enable specific instances of dismissed warnings.</span></span> <span data-ttu-id="d40e3-104">La scheda **Avvisi** visualizza due griglie: **Regole per gli avvisi di progettazione** e **Avvisi ignorati**.</span><span class="sxs-lookup"><span data-stu-id="d40e3-104">The **Warnings** tab displays two grids: **Design Warning Rules** and **Dismissed Warnings**.</span></span>  
  
 <span data-ttu-id="d40e3-105">**Per visualizzare la scheda Avvisi**</span><span class="sxs-lookup"><span data-stu-id="d40e3-105">**To display the Warnings tab**</span></span>  
  
1.  <span data-ttu-id="d40e3-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire un progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d40e3-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="d40e3-107">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , fare clic su **Modifica database**, quindi fare clic sulla scheda **Avvisi** .</span><span class="sxs-lookup"><span data-stu-id="d40e3-107">In **Solution Explorer**, right-click the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, click **Edit Database**, and then click the **Warnings** tab.</span></span>  
  
## <a name="design-warning-rules-grid"></a><span data-ttu-id="d40e3-108">Griglia Regole per gli avvisi di progettazione</span><span class="sxs-lookup"><span data-stu-id="d40e3-108">Design Warning Rules Grid</span></span>  
 <span data-ttu-id="d40e3-109">La griglia **Regole per gli avvisi di progettazione** visualizza tutte le regole dell'avviso di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d40e3-109">The **Design Warning Rules** grid displays all the design warning rules.</span></span> <span data-ttu-id="d40e3-110">Questa griglia controlla anche quali regole sono attivate nel database.</span><span class="sxs-lookup"><span data-stu-id="d40e3-110">This grid also controls which rules are enabled for the database.</span></span> <span data-ttu-id="d40e3-111">Per attivare o disabilitare una regola dell'avviso, selezionare o deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="d40e3-111">To enable or disable a warning rule, select or clear its check box.</span></span>  
  
 <span data-ttu-id="d40e3-112">La griglia **Regole per gli avvisi di progettazione** ha le seguenti colonne:</span><span class="sxs-lookup"><span data-stu-id="d40e3-112">The **Design Warning Rules** grid has the following columns:</span></span>  
  
 <span data-ttu-id="d40e3-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d40e3-113">**Description**</span></span>  
 <span data-ttu-id="d40e3-114">Visualizza il nome della regola.</span><span class="sxs-lookup"><span data-stu-id="d40e3-114">Displays the name of the rule.</span></span> <span data-ttu-id="d40e3-115">Le regole sono raggruppate per categoria.</span><span class="sxs-lookup"><span data-stu-id="d40e3-115">Rules are grouped by category.</span></span>  
  
 <span data-ttu-id="d40e3-116">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="d40e3-116">**Importance**</span></span>  
 <span data-ttu-id="d40e3-117">Visualizza la priorità assegnata alla regola.</span><span class="sxs-lookup"><span data-stu-id="d40e3-117">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="d40e3-118">**Commenti**</span><span class="sxs-lookup"><span data-stu-id="d40e3-118">**Comments**</span></span>  
 <span data-ttu-id="d40e3-119">(Facoltativo) Consente all'utente di digitare un commento che spieghi perché si sta ignorando l'avviso.</span><span class="sxs-lookup"><span data-stu-id="d40e3-119">(Optional) Allows the user to type a comment that explains why you are dismissing the warning.</span></span>  
  
## <a name="dismissed-warnings-grid"></a><span data-ttu-id="d40e3-120">Griglia Avvisi ignorati</span><span class="sxs-lookup"><span data-stu-id="d40e3-120">Dismissed Warnings Grid</span></span>  
 <span data-ttu-id="d40e3-121">La griglia **Avvisi ignorati** visualizza tutte le occorrenze specifiche dell'avviso ignorate dall' **Elenco errori**.</span><span class="sxs-lookup"><span data-stu-id="d40e3-121">The **Dismissed Warnings** grid displays all specific warning occurrences that have been dismissed from the **Error List**.</span></span> <span data-ttu-id="d40e3-122">Per riattivare un avviso, selezionarlo nella griglia, quindi fare clic su **Riabilita**.</span><span class="sxs-lookup"><span data-stu-id="d40e3-122">To re-enable a warning, select it in the grid, and then click **Re-enable**.</span></span>  
  
 <span data-ttu-id="d40e3-123">La griglia **Avvisi ignorati** ha i seguenti elementi :</span><span class="sxs-lookup"><span data-stu-id="d40e3-123">The **Dismissed Warnings** grid has the following :</span></span>  
  
 <span data-ttu-id="d40e3-124">**Object**</span><span class="sxs-lookup"><span data-stu-id="d40e3-124">**Object**</span></span>  
 <span data-ttu-id="d40e3-125">Visualizza un'icona che rappresenta il tipo di oggetto e il nome dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="d40e3-125">Displays an icon that represents the object type and the object name.</span></span>  
  
 <span data-ttu-id="d40e3-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d40e3-126">**Type**</span></span>  
 <span data-ttu-id="d40e3-127">Visualizza il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="d40e3-127">Displays the object type.</span></span>  
  
 <span data-ttu-id="d40e3-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d40e3-128">**Description**</span></span>  
 <span data-ttu-id="d40e3-129">Visualizza il nome della regola.</span><span class="sxs-lookup"><span data-stu-id="d40e3-129">Displays the name of the rule.</span></span>  
  
 <span data-ttu-id="d40e3-130">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="d40e3-130">**Importance**</span></span>  
 <span data-ttu-id="d40e3-131">Visualizza la priorità assegnata alla regola.</span><span class="sxs-lookup"><span data-stu-id="d40e3-131">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="d40e3-132">**Commenti**</span><span class="sxs-lookup"><span data-stu-id="d40e3-132">**Comments**</span></span>  
 <span data-ttu-id="d40e3-133">Visualizza il commento immesso quando l'avviso è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="d40e3-133">Displays the comment that was entered when the warning was dismissed.</span></span> <span data-ttu-id="d40e3-134">Qui è possibile aggiungere o modificare un commento.</span><span class="sxs-lookup"><span data-stu-id="d40e3-134">You can add or modify a comment here.</span></span>  
  
 <span data-ttu-id="d40e3-135">**Riabilita**</span><span class="sxs-lookup"><span data-stu-id="d40e3-135">**Re-enable**</span></span>  
 <span data-ttu-id="d40e3-136">Riattiva gli avvisi selezionati.</span><span class="sxs-lookup"><span data-stu-id="d40e3-136">Re-enables the selected warnings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d40e3-137">Se un oggetto ha un avviso, ma è in uno stato non valido o è stato rimosso manualmente dal progetto, verrà visualizzata un'icona Errori nell'elenco accanto all'avviso.</span><span class="sxs-lookup"><span data-stu-id="d40e3-137">If an object has a warning, but the object is in an invalid state or was manually removed from the project, an error icon appears next to the warning in the list.</span></span> <span data-ttu-id="d40e3-138">Per ignorare l'avviso, selezionarlo, quindi fare clic su **Riabilita**.</span><span class="sxs-lookup"><span data-stu-id="d40e3-138">To dismiss the warning, select it and then click **Re-enable**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d40e3-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d40e3-139">See Also</span></span>  
 <span data-ttu-id="d40e3-140">[Finestra di dialogo Ignora avviso &#40;Analysis Services-Dati multidimensionali&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d40e3-140">[Dismiss Warning Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d40e3-141">&#40;generale di progettazione database&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="d40e3-141">General &#40;Database Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](general-database-designer-analysis-services-multidimensional-data.md)  
  
  
