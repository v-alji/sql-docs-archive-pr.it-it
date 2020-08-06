---
title: Impostare e configurare le unità di misura (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a15a96c3-7d2c-433e-a440-4ea051e967a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c01523dad9a96d2d45b96474d36873bac2484343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623791"
---
# <a name="set-and-configure-measurement-units-report-builder-and-ssrs"></a><span data-ttu-id="fde74-102">Impostare e configurare le unità di misura (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="fde74-102">Set and Configure Measurement Units (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fde74-103">Gli indicatori forniscono due unità di misura: percentuale e numerica.</span><span class="sxs-lookup"><span data-stu-id="fde74-103">Indicators provide two measurement units: percentage and numeric.</span></span> <span data-ttu-id="fde74-104">Per impostazione predefinita, gli indicatori vengono configurati in modo da utilizzare le percentuali come unità di misura.</span><span class="sxs-lookup"><span data-stu-id="fde74-104">By default, indicators are configured to use percentages as the measurement unit.</span></span> <span data-ttu-id="fde74-105">Pertanto i valori dell'indicatore assegnati a ogni icona nel set di indicatori sono determinati da un intervallo di percentuale.</span><span class="sxs-lookup"><span data-stu-id="fde74-105">This means that the indicator values assigned to each icon in the indicator set are determined by a percentage range.</span></span> <span data-ttu-id="fde74-106">Gli intervalli di percentuale sono divisi uniformemente tra le icone nel set di indicatori.</span><span class="sxs-lookup"><span data-stu-id="fde74-106">The percentage ranges are evenly divided across the icons in the indicator set.</span></span> <span data-ttu-id="fde74-107">Ogni icona rappresenta uno stato dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="fde74-107">Each icon represents an indicator state.</span></span> <span data-ttu-id="fde74-108">È possibile modificare le percentuali per ogni icona nel set di indicatori specificando percentuali di inizio e di fine differenti.</span><span class="sxs-lookup"><span data-stu-id="fde74-108">You can change the percentages for each icon in the indicator set by specifying different start and end percentages.</span></span> <span data-ttu-id="fde74-109">Gli indicatori rilevano automaticamente anche i valori minimo e massimo nei dati.</span><span class="sxs-lookup"><span data-stu-id="fde74-109">Indicators also automatically detect the minimum and maximum values in the data.</span></span>  
  
 <span data-ttu-id="fde74-110">L'unità di misura può essere cambiata in valore numerico.</span><span class="sxs-lookup"><span data-stu-id="fde74-110">You can change the measurement unit to be a numeric value.</span></span> <span data-ttu-id="fde74-111">In tal caso, non è possibile specificare i valori minimo o massimo per i dati; al contrario, vengono forniti solo i valori iniziali e finali per ogni icona utilizzata dall'indicatore.</span><span class="sxs-lookup"><span data-stu-id="fde74-111">In this case, you do not specify minimum or maximum for the data; instead, you provide only the start and end values for each icon that the indicator uses.</span></span>  
  
 <span data-ttu-id="fde74-112">Opzioni come le unità di misura possono essere impostate tramite espressioni.</span><span class="sxs-lookup"><span data-stu-id="fde74-112">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="fde74-113">Per altre informazioni, vedere [Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fde74-113">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-use-the-numeric-state-measurement-unit"></a><span data-ttu-id="fde74-114">Per utilizzare l'unità di misura di stato numerica</span><span class="sxs-lookup"><span data-stu-id="fde74-114">To use the numeric state measurement unit</span></span>  
  
1.  <span data-ttu-id="fde74-115">Fare clic con il pulsante destro del mouse sull'indicatore da modificare e scegliere **Proprietà indicatore**.</span><span class="sxs-lookup"><span data-stu-id="fde74-115">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="fde74-116">Scegliere **Valori e stati** dal riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="fde74-116">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="fde74-117">Nell'elenco **Unità di misura stati** fare clic su **Numerico**.</span><span class="sxs-lookup"><span data-stu-id="fde74-117">In the **States Measurement Unit** list, click **Numeric**.</span></span>  
  
     <span data-ttu-id="fde74-118">Facoltativamente, fare clic sul pulsante **Espressione** (*fx*) per modificare un'espressione che consente di impostare il valore per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="fde74-118">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="fde74-119">Per ogni icona nel set di indicatori, aggiornare i valori nelle caselle di testo **Iniziale** e **Finale** .</span><span class="sxs-lookup"><span data-stu-id="fde74-119">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="fde74-120">Facoltativamente, fare clic sul pulsante **Espressione** (*fx*) per modificare un'espressione che consente di impostare i valori delle opzioni **Iniziale** e **Finale** .</span><span class="sxs-lookup"><span data-stu-id="fde74-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fde74-121">I valori nelle caselle di testo **Iniziale** e **Finale** devono essere numerici.</span><span class="sxs-lookup"><span data-stu-id="fde74-121">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-percentage-measurement-unit"></a><span data-ttu-id="fde74-122">Per utilizzare l'unità di misura espressa in percentuale</span><span class="sxs-lookup"><span data-stu-id="fde74-122">To use the percentage measurement unit</span></span>  
  
1.  <span data-ttu-id="fde74-123">Fare clic con il pulsante destro del mouse sull'indicatore da modificare e scegliere **Proprietà indicatore**.</span><span class="sxs-lookup"><span data-stu-id="fde74-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="fde74-124">Scegliere **Valori e stati** dal riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="fde74-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="fde74-125">Nell'elenco **Unità di misura stati** fare clic su **Percentuale**.</span><span class="sxs-lookup"><span data-stu-id="fde74-125">In the **States Measurement Unit** list, click **Percentage**.</span></span>  
  
     <span data-ttu-id="fde74-126">Facoltativamente, fare clic sul pulsante **Espressione** (*fx*) per modificare un'espressione che consente di impostare il valore per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="fde74-126">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="fde74-127">Facoltativamente, modificare le opzioni **Minimo** e **Massimo** per usare valori specifici invece di rilevare automaticamente i valori minimo e massimo dei dati usati dall'indicatore.</span><span class="sxs-lookup"><span data-stu-id="fde74-127">Optionally, change the **Minimum** and **Maximum** options to use specific values instead of automatically detecting the minimum and maximum values of the data that the indicator uses.</span></span> <span data-ttu-id="fde74-128">Il valore di **Minimo** deve essere minore di quello indicato dal valore di **Massimo**.</span><span class="sxs-lookup"><span data-stu-id="fde74-128">The value of **Minimum** must be smaller than the value of **Maximum**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fde74-129">Se si impostano in modo esplicito i valori minimo e massimo, quell'intervallo di valori viene utilizzato dall'indicatore indipendentemente dai valori minimo e massimo effettivi nei dati.</span><span class="sxs-lookup"><span data-stu-id="fde74-129">If you explicitly set minimum and maximum values, that value range is used by the indicator regardless of the actual the minimum and maximum values in the data.</span></span> <span data-ttu-id="fde74-130">Pertanto, i valori inferiori al valore minimo e superiori a quello massimo sono esclusi dalla valutazione che determina quale icona dell'indicatore mostrare nel report.</span><span class="sxs-lookup"><span data-stu-id="fde74-130">This means that values lower than the minimum and higher than the maximum are excluded from the evaluation that determine what indictor icon to show in the report.</span></span>  
  
     <span data-ttu-id="fde74-131">Facoltativamente, fare clic sul pulsante **Espressione** (*fx*) per modificare un'espressione che consente di impostare i valori per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="fde74-131">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the option.</span></span>  
  
5.  <span data-ttu-id="fde74-132">Per ogni icona nel set di indicatori, aggiornare i valori nelle caselle di testo **Iniziale** e **Finale** .</span><span class="sxs-lookup"><span data-stu-id="fde74-132">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="fde74-133">Facoltativamente, fare clic sul pulsante **Espressione** (*fx*) per modificare un'espressione che consente di impostare i valori delle opzioni **Iniziale** e **Finale** .</span><span class="sxs-lookup"><span data-stu-id="fde74-133">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fde74-134">I valori nelle caselle di testo **Iniziale** e **Finale** devono essere numerici.</span><span class="sxs-lookup"><span data-stu-id="fde74-134">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fde74-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fde74-135">See Also</span></span>  
 [<span data-ttu-id="fde74-136">Indicatori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fde74-136">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
