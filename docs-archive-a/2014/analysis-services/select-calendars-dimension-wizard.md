---
title: Selezione calendari (creazione guidata dimensione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.serverSpecialCalendars.f1
ms.assetid: 6e28a020-2586-4b13-9333-b499fb1b33af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2048ee20dd91c942f01982d02f3265a6bad670dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629628"
---
# <a name="select-calendars-dimension-wizard"></a><span data-ttu-id="e4bab-102">Selezione calendari (Creazione guidata dimensione)</span><span class="sxs-lookup"><span data-stu-id="e4bab-102">Select Calendars (Dimension Wizard)</span></span>
  <span data-ttu-id="e4bab-103">Usare la pagina **Selezione calendari** per creare gerarchie aggiuntive che rappresentano calendari fiscali, di report, di produzione o ISO 8601 per la dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="e4bab-103">Use the **Select Calendars** page to create additional hierarchies representing fiscal, reporting, manufacturing, or International Standards Organization (ISO) 8601 calendars for the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4bab-104">Questa pagina viene visualizzata solo se è stata selezionata l'opzione **Dimensione temporale del server** nella pagina **Selezione tipo di dimensione** oppure se sono state selezionate le opzioni **Compila dimensione senza usare un'origine dei dati** nella pagina **Selezione metodo di creazione** e **Dimensione temporale** nella pagina **Selezione tipo di dimensione** .</span><span class="sxs-lookup"><span data-stu-id="e4bab-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Dimension Definition** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e4bab-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e4bab-105">Options</span></span>  
 <span data-ttu-id="e4bab-106">**Calendario fiscale**</span><span class="sxs-lookup"><span data-stu-id="e4bab-106">**Fiscal calendar**</span></span>  
 <span data-ttu-id="e4bab-107">Selezionare questa opzione per creare una gerarchia temporale basata su un calendario fiscale.</span><span class="sxs-lookup"><span data-stu-id="e4bab-107">Select to create a time hierarchy based on a fiscal calendar.</span></span>  
  
 <span data-ttu-id="e4bab-108">**Giorno e mese di inizio**</span><span class="sxs-lookup"><span data-stu-id="e4bab-108">**Start day and month**</span></span>  
 <span data-ttu-id="e4bab-109">Consente di selezionare il giorno e il mese di inizio del calendario fiscale.</span><span class="sxs-lookup"><span data-stu-id="e4bab-109">Select the day and month on which the fiscal calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4bab-110">Questa opzione è disponibile solo quando si seleziona **Calendario fiscale** .</span><span class="sxs-lookup"><span data-stu-id="e4bab-110">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="e4bab-111">**Convenzione di denominazione calendario fiscale**</span><span class="sxs-lookup"><span data-stu-id="e4bab-111">**Fiscal calendar naming convention**</span></span>  
 <span data-ttu-id="e4bab-112">Consente di selezionare la convenzione di denominazione utilizzata dal calendario fiscale.</span><span class="sxs-lookup"><span data-stu-id="e4bab-112">Select the naming convention used by the fiscal calendar.</span></span> <span data-ttu-id="e4bab-113">Selezionare **Nome anno calendario** oppure **Nome anno calendario +1**.</span><span class="sxs-lookup"><span data-stu-id="e4bab-113">Select either **Calendar year name** or **Calendar year name +1**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4bab-114">Questa opzione è disponibile solo quando si seleziona **Calendario fiscale** .</span><span class="sxs-lookup"><span data-stu-id="e4bab-114">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="e4bab-115">**Calendario report (o marketing)**</span><span class="sxs-lookup"><span data-stu-id="e4bab-115">**Reporting (or marketing) calendar**</span></span>  
 <span data-ttu-id="e4bab-116">Selezionare questa opzione per creare una gerarchia temporale basata su un calendario di report.</span><span class="sxs-lookup"><span data-stu-id="e4bab-116">Select to create a time hierarchy based on a reporting calendar.</span></span>  
  
 <span data-ttu-id="e4bab-117">**Settimana e mese di inizio**</span><span class="sxs-lookup"><span data-stu-id="e4bab-117">**Start week and month**</span></span>  
 <span data-ttu-id="e4bab-118">Consente di selezionare la settimana e il mese di inizio del calendario di report.</span><span class="sxs-lookup"><span data-stu-id="e4bab-118">Select the week and month on which the reporting calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4bab-119">Questa opzione è disponibile se è stata selezionata l'opzione **Calendario report (o marketing)** .</span><span class="sxs-lookup"><span data-stu-id="e4bab-119">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="e4bab-120">**Schema di settimane per mese**</span><span class="sxs-lookup"><span data-stu-id="e4bab-120">**Week by month pattern**</span></span>  
 <span data-ttu-id="e4bab-121">Consente di selezionare lo schema di settimane per mese utilizzato dal calendario di report.</span><span class="sxs-lookup"><span data-stu-id="e4bab-121">Select the week by month pattern used by the reporting calendar.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4bab-122">Questa opzione è disponibile se è stata selezionata l'opzione **Calendario report (o marketing)** .</span><span class="sxs-lookup"><span data-stu-id="e4bab-122">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="e4bab-123">nella tabella riportata di seguito vengono elencate le opzioni disponibili per lo schema di settimane per mese.</span><span class="sxs-lookup"><span data-stu-id="e4bab-123">The following table lists the options available for the week by month pattern.</span></span>  
  
|<span data-ttu-id="e4bab-124">Valore</span><span class="sxs-lookup"><span data-stu-id="e4bab-124">Value</span></span>|<span data-ttu-id="e4bab-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4bab-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bab-126">**Settimana 445**</span><span class="sxs-lookup"><span data-stu-id="e4bab-126">**Week 445**</span></span>|<span data-ttu-id="e4bab-127">Il primo mese del trimestre è composto da 4 settimane, il secondo mese da 4 settimane e il terzo mese da 5 settimane.</span><span class="sxs-lookup"><span data-stu-id="e4bab-127">The first month in the quarter has 4 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 5 weeks.</span></span>|  
|<span data-ttu-id="e4bab-128">**Settimana 454**</span><span class="sxs-lookup"><span data-stu-id="e4bab-128">**Week 454**</span></span>|<span data-ttu-id="e4bab-129">Il primo mese del trimestre è composto da 4 settimane, il secondo mese da 5 settimane e il terzo mese da 4 settimane.</span><span class="sxs-lookup"><span data-stu-id="e4bab-129">The first month in the quarter has 4 weeks, the second month in the quarter has 5 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
|<span data-ttu-id="e4bab-130">**544**</span><span class="sxs-lookup"><span data-stu-id="e4bab-130">**Week 544**</span></span>|<span data-ttu-id="e4bab-131">Il primo mese del trimestre è composto da 5 settimane, il secondo mese da 4 settimane e il terzo mese 4 settimane.</span><span class="sxs-lookup"><span data-stu-id="e4bab-131">The first month in the quarter has 5 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
  
 <span data-ttu-id="e4bab-132">**Calendario produzione**</span><span class="sxs-lookup"><span data-stu-id="e4bab-132">**Manufacturing calendar**</span></span>  
 <span data-ttu-id="e4bab-133">Selezionare questa opzione per creare una gerarchia temporale basata su un calendario di produzione.</span><span class="sxs-lookup"><span data-stu-id="e4bab-133">Select to create a time hierarchy based on a manufacturing calendar.</span></span>  
  
 <span data-ttu-id="e4bab-134">**Settimana e mese di inizio**</span><span class="sxs-lookup"><span data-stu-id="e4bab-134">**Start week and month**</span></span>  
 <span data-ttu-id="e4bab-135">Consente di selezionare la settimana e il mese di inizio del calendario di produzione.</span><span class="sxs-lookup"><span data-stu-id="e4bab-135">Select the week and month on which the manufacturing calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4bab-136">Questa opzione è disponibile se è stata selezionata l'opzione **Calendario produzione** .</span><span class="sxs-lookup"><span data-stu-id="e4bab-136">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="e4bab-137">**Trimestre con periodi aggiuntivi**</span><span class="sxs-lookup"><span data-stu-id="e4bab-137">**Quarter with extra periods**</span></span>  
 <span data-ttu-id="e4bab-138">Consente di selezionare o digitare il trimestre che conterrà i periodi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e4bab-138">Select or type the quarter that will contain the extra periods.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4bab-139">Questa opzione è disponibile se è stata selezionata l'opzione **Calendario produzione** .</span><span class="sxs-lookup"><span data-stu-id="e4bab-139">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="e4bab-140">**Calendario ISO 8601**</span><span class="sxs-lookup"><span data-stu-id="e4bab-140">**ISO 8601 calendar**</span></span>  
 <span data-ttu-id="e4bab-141">Selezionare questa opzione per creare una gerarchia basata sul calendario ISO 8601.</span><span class="sxs-lookup"><span data-stu-id="e4bab-141">Select to create a hierarchy based on the ISO 8601 calendar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4bab-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4bab-142">See Also</span></span>  
 <span data-ttu-id="e4bab-143">[Guida sensibile al contesto della creazione guidata dimensione](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e4bab-143">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="e4bab-144">[Dimensioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e4bab-144">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e4bab-145">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="e4bab-145">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
