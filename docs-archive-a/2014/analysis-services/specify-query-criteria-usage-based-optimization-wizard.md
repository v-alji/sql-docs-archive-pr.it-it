---
title: Specificare i criteri di query (Ottimizzazione guidata basata sulle informazioni di utilizzo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.usagebasedoptimizationwizard.specifyquerycriteria.f1
ms.assetid: 3193adc2-af9f-4234-a4cc-dea0c280a724
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3b93034a089ff3121155e35de4cec96846824a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626324"
---
# <a name="specify-query-criteria-usage-based-optimization-wizard"></a><span data-ttu-id="bee48-102">Impostazione criteri di query (Ottimizzazione guidata basata sulle statistiche di utilizzo)</span><span class="sxs-lookup"><span data-stu-id="bee48-102">Specify Query Criteria (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="bee48-103">Utilizzare la pagina **Impostazione criteri di query** per scegliere una o più opzioni di filtro per identificare le query da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="bee48-103">Use the **Specify Query Criteria** page to choose one or more filter options in order to identify queries to optimize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bee48-104">Se [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] non riesce a connettersi al log di query, questa pagina non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="bee48-104">This page is disabled if [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cannot connect to the query log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bee48-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bee48-105">Options</span></span>  
 <span data-ttu-id="bee48-106">**Statistiche log di query**</span><span class="sxs-lookup"><span data-stu-id="bee48-106">**Query log statistics**</span></span>  
 <span data-ttu-id="bee48-107">Consente di visualizzare informazioni sulle query archiviate nel log di query per le partizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="bee48-107">Displays information about the queries stored in the query log for the selected partitions.</span></span> <span data-ttu-id="bee48-108">Sono disponibili gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bee48-108">The following items are displayed:</span></span>  
  
|<span data-ttu-id="bee48-109">Termine</span><span class="sxs-lookup"><span data-stu-id="bee48-109">Term</span></span>|<span data-ttu-id="bee48-110">Definizione</span><span class="sxs-lookup"><span data-stu-id="bee48-110">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="bee48-111">**Totale query**</span><span class="sxs-lookup"><span data-stu-id="bee48-111">**Total queries**</span></span>|<span data-ttu-id="bee48-112">Consente di visualizzare il numero totale di query archiviate nel log di query per le partizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="bee48-112">Displays the total number of queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="bee48-113">**Query distinte**</span><span class="sxs-lookup"><span data-stu-id="bee48-113">**Distinct queries**</span></span>|<span data-ttu-id="bee48-114">Consente di visualizzare il numero totale di query distinte archiviate nel log di query per le partizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="bee48-114">Displays the number of distinct queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="bee48-115">**Utenti distinti**</span><span class="sxs-lookup"><span data-stu-id="bee48-115">**Distinct users**</span></span>|<span data-ttu-id="bee48-116">Consente di visualizzare il numero totale di utenti distinti associati alle query archiviate nel log di query per le partizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="bee48-116">Displays the total number of distinct users associated with queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="bee48-117">**Tempo di risposta medio**</span><span class="sxs-lookup"><span data-stu-id="bee48-117">**Average response time**</span></span>|<span data-ttu-id="bee48-118">Consente di visualizzare i tempi di risposta medi per le query archiviate nel log di query per le partizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="bee48-118">Displays the average response time for queries stored in the query log for the selected partitions.</span></span>|  
  
 <span data-ttu-id="bee48-119">**Data di inizio**</span><span class="sxs-lookup"><span data-stu-id="bee48-119">**Beginning date**</span></span>  
 <span data-ttu-id="bee48-120">Consente di filtrare le query del log di query in base a una data e ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="bee48-120">Filters queries in the query log based on a starting date and time.</span></span> <span data-ttu-id="bee48-121">Selezionare o digitare una data nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bee48-121">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bee48-122">Se l'opzione **Data di fine** non è selezionata, vengono considerate tutte le query del log di query con data e ora corrispondenti o successive a quelle specificate per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="bee48-122">If **Ending date** is not selected, all queries in the query log on or after the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="bee48-123">**Data di fine**</span><span class="sxs-lookup"><span data-stu-id="bee48-123">**Ending date**</span></span>  
 <span data-ttu-id="bee48-124">Consente di filtrare le query del log di query in base a una data e ora di fine.</span><span class="sxs-lookup"><span data-stu-id="bee48-124">Filters queries in the query log based on an ending date and time.</span></span> <span data-ttu-id="bee48-125">Selezionare o digitare una data nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bee48-125">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bee48-126">Se l'opzione **Data di inizio** non è selezionata, vengono considerate tutte le query del log di query con data e ora corrispondenti o precedenti a quelle specificate per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="bee48-126">If **Beginning date** is not selected, all queries in the query log on or before the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="bee48-127">**Utenti**</span><span class="sxs-lookup"><span data-stu-id="bee48-127">**Users**</span></span>  
 <span data-ttu-id="bee48-128">Consente di filtrare le query del log di query in base a un set di utenti.</span><span class="sxs-lookup"><span data-stu-id="bee48-128">Filters queries in the query log based on a specified set of users.</span></span> <span data-ttu-id="bee48-129">Fare clic sul pulsante (**...**) per visualizzare la finestra di dialogo **Selezione utenti** e selezionare gli utenti in base ai quali filtrare le query.</span><span class="sxs-lookup"><span data-stu-id="bee48-129">Click the ellipsis (**...**) button to display the **User Selection** dialog box and choose users on which to filter queries.</span></span> <span data-ttu-id="bee48-130">Per altre informazioni sulla finestra di dialogo **Selezione utenti**, vedere [Finestra di dialogo Selezione utenti &#40;Analysis Services - Dati multidimensionali&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bee48-130">For more information about the **User Selection** dialog box, see [User Selection Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="bee48-131">**Query più frequenti**</span><span class="sxs-lookup"><span data-stu-id="bee48-131">**Most frequent queries**</span></span>  
 <span data-ttu-id="bee48-132">Consente di filtrare le query del log di query in base alla percentuale maggiore di query distinte eseguite più spesso per le partizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="bee48-132">Filters queries in the query log based on the topmost percentage of the distinct queries most often run for the selected partitions.</span></span> <span data-ttu-id="bee48-133">Selezionare o digitare un valore percentuale nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="bee48-133">Choose or type a percent value in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee48-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bee48-134">See Also</span></span>  
 <span data-ttu-id="bee48-135">[Guida sensibile al contesto dell'ottimizzazione guidata basata sull'utilizzo](usage-based-optimization-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="bee48-135">[Usage-Based Optimization Wizard F1 Help](usage-based-optimization-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="bee48-136">Procedure guidate di Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="bee48-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
