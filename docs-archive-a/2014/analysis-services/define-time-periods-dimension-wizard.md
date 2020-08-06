---
title: Definizione periodi di tempo (creazione guidata dimensione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.timefrequency.f1
ms.assetid: 6bda6b7e-d306-4e68-9acb-84de8f44d1b4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88b69eaa265b7a98f7d32063b602897d02016fa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636940"
---
# <a name="define-time-periods-dimension-wizard"></a><span data-ttu-id="48aca-102">Definizione periodi di tempo (Creazione guidata dimensione)</span><span class="sxs-lookup"><span data-stu-id="48aca-102">Define Time Periods (Dimension Wizard)</span></span>
  <span data-ttu-id="48aca-103">Utilizzare la pagina **Definizione periodi di tempo** per definire le informazioni sull'anno di calendario e le frequenze temporali da includere nella dimensione temporale o nella dimensione temporale del server.</span><span class="sxs-lookup"><span data-stu-id="48aca-103">Use the **Define Time Periods** page to define the calendar year information and time frequencies to include in the time dimension or server time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48aca-104"> Questa pagina viene visualizzata solo se è stata selezionata l'opzione **Dimensione temporale del server** nella pagina **Selezione tipo di dimensione** oppure se sono state selezionate le opzioni **Compila dimensione senza utilizzare un'origine dei dati** nella pagina **Selezione metodo di compilazione** e **Dimensione temporale** nella pagina **Selezione tipo di dimensione** .</span><span class="sxs-lookup"><span data-stu-id="48aca-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Select Build Method** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48aca-105">questa pagina consente di definire l'anno di calendario di una dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="48aca-105">This page is for defining the calendar year of a time dimension.</span></span> <span data-ttu-id="48aca-106">Per definire un anno fiscale, di produzione, di report o ISO 8601 per la dimensione temporale, usare la pagina **Selezione calendari** .</span><span class="sxs-lookup"><span data-stu-id="48aca-106">To define a fiscal, manufacturing, reporting, or International Standards Organization (ISO) 8601 year for the time dimension, use the **Select Calendars** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="48aca-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="48aca-107">Options</span></span>  
 <span data-ttu-id="48aca-108">**Primo giorno del calendario**</span><span class="sxs-lookup"><span data-stu-id="48aca-108">**First calendar day**</span></span>  
 <span data-ttu-id="48aca-109">Consente di digitare o selezionare il giorno di inizio dell'anno corrente.</span><span class="sxs-lookup"><span data-stu-id="48aca-109">Type or select the day that begins the current year.</span></span>  
  
 <span data-ttu-id="48aca-110">**Ultimo giorno del calendario**</span><span class="sxs-lookup"><span data-stu-id="48aca-110">**Last calendar day**</span></span>  
 <span data-ttu-id="48aca-111">Consente di digitare o selezionare il giorno di fine dell'anno corrente.</span><span class="sxs-lookup"><span data-stu-id="48aca-111">Type or select the day that ends the current year.</span></span>  
  
 <span data-ttu-id="48aca-112">**Primo giorno della settimana**</span><span class="sxs-lookup"><span data-stu-id="48aca-112">**First day of the week**</span></span>  
 <span data-ttu-id="48aca-113">Consente di selezionare il giorno di inizio di una settimana.</span><span class="sxs-lookup"><span data-stu-id="48aca-113">Select the day that begins a week.</span></span>  
  
 <span data-ttu-id="48aca-114">**Periodi di tempo**</span><span class="sxs-lookup"><span data-stu-id="48aca-114">**Time periods**</span></span>  
 <span data-ttu-id="48aca-115">Consente di selezionare i periodi di tempo per l'anno di calendario della dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="48aca-115">Select the time periods for the calendar year of the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48aca-116">È necessario selezionare il periodo di tempo `Date`.</span><span class="sxs-lookup"><span data-stu-id="48aca-116">The `Date` time period is required.</span></span>  
  
 <span data-ttu-id="48aca-117">**Lingua per i nomi dei membri della dimensione temporale**</span><span class="sxs-lookup"><span data-stu-id="48aca-117">**Language for time member names**</span></span>  
 <span data-ttu-id="48aca-118">Consente di selezionare la lingua per i membri della dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="48aca-118">Select the language for the members in the time dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48aca-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48aca-119">See Also</span></span>  
 <span data-ttu-id="48aca-120">[Guida sensibile al contesto della creazione guidata dimensione](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="48aca-120">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="48aca-121">[Dimensioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="48aca-121">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="48aca-122">[Dimensioni nei modelli multidimensionali](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="48aca-122">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="48aca-123">Selezione guidata calendari &#40;dimensioni&#41;</span><span class="sxs-lookup"><span data-stu-id="48aca-123">Select Calendars &#40;Dimension Wizard&#41;</span></span>](select-calendars-dimension-wizard.md)  
  
  
