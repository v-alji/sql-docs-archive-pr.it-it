---
title: Finestra di dialogo regole colori mappa, generale | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10541"
- sql12.rtp.rptdesigner.shared.mapcolorrulesgeneral.f1
ms.assetid: 14ff5fc1-4cf8-4a45-9d98-47a1bf1c52c4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0dffc6c0b31400cb4eb9cecbbada1a52f8f41443
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637078"
---
# <a name="map-color-rules-dialog-box-general"></a><span data-ttu-id="bb0a8-102">Finestra di dialogo Proprietà regole colori mappa, Generale</span><span class="sxs-lookup"><span data-stu-id="bb0a8-102">Map Color Rules Dialog Box, General</span></span>
  <span data-ttu-id="bb0a8-103">Selezionare **Generale** nella finestra di dialogo **Proprietà regole colori mappa** per definire le opzioni relative ai colori per gli elementi mappa di questo livello.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-103">Select **General** on the **Color Rules Properties** dialog box to define color options for map elements on this layer.</span></span> <span data-ttu-id="bb0a8-104">Gli elementi della mappa includono poligoni, linee e punti.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-104">Map elements include polygons, lines, and points.</span></span> <span data-ttu-id="bb0a8-105">Le regole colore possono essere applicate quando è stata creata una relazione tra gli elementi della mappa in base ai dati spaziali e analitici di un campo del set di dati o di un campo dell'origine dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-105">Color rules can be applied when you have created a relationship between map elements based on spatial data and analytical data from a dataset field or from a spatial data source field.</span></span>  
  
 <span data-ttu-id="bb0a8-106">Per visualizzare tutti gli elementi della mappa su un livello specificando una sfumatura decorativa con colori primari e secondari diversi, utilizzare la pagina **Riempimento** della finestra di dialogo Proprietà poligono mappa.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-106">To display all map elements on a layer by specifying a decorative gradient with different primary and secondary colors, use the **Fill** page of the Map Polygon Properties Dialog Box.</span></span> <span data-ttu-id="bb0a8-107">Le regole colore hanno la precedenza sulle proprietà di visualizzazione per un livello.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-107">Color rules take precedence over display properties for a layer.</span></span> <span data-ttu-id="bb0a8-108">Per altre informazioni, vedere [Personalizzare i dati e la visualizzazione di una mappa o di un livello mappa &#40;Generatore report e SSRS&#41;](report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bb0a8-108">For more information, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bb0a8-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bb0a8-109">Options</span></span>  
 <span data-ttu-id="bb0a8-110">**Applica stile modello**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-110">**Apply template style**</span></span>  
 <span data-ttu-id="bb0a8-111">Selezionare questa opzione per utilizzare i colori in base al tema scelto nella procedura guidata o impostato nelle proprietà dei livelli Poligono, Linea o Punto.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-111">Select this option to use color based on the theme that was chosen in the wizard or set in the Polygon, Line, or Point layer properties.</span></span> <span data-ttu-id="bb0a8-112">Un tema consente di impostare le opzioni predefinite per colore, carattere e bordi della mappa.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-112">A theme sets default options for color, font, and borders for the map.</span></span> <span data-ttu-id="bb0a8-113">Per questa opzione, non viene applicata nessuna regola per assegnare colori a ogni elemento della mappa.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-113">For this option, no rule is applied to assign colors to each map element.</span></span>  
  
 <span data-ttu-id="bb0a8-114">**Visualizza dati tramite tavolozza colori**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-114">**Visualize data by using color palette**</span></span>  
 <span data-ttu-id="bb0a8-115">Selezionare questa opzione per visualizzare i dati analitici tramite i colori di una specifica tavolozza.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-115">Select this option to visualize analytical data by using colors from a specific color palette.</span></span>  
  
 <span data-ttu-id="bb0a8-116">**Visualizza dati tramite intervalli colori**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-116">**Visualize data by using color ranges**</span></span>  
 <span data-ttu-id="bb0a8-117">Selezionare questa opzione per visualizzare i dati analitici tramite un intervallo di colori per ogni elemento della mappa.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-117">Select this option to visualize analytical data by using a range of colors for each map element.</span></span> <span data-ttu-id="bb0a8-118">Ad esempio se si specifica il rosso come colore iniziale, il giallo come colore intermedio e il verde come colore finale, i valori dell'intervallo inferiore sono rossi, i valori dell'intervallo intermedio sono gialli e i valori dell'intervallo superiore sono verdi.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-118">For example, when you specify Red as a start color, Yellow as a middle color, and Green as an end color, values in the low range are Red, values in the middle range are Yellow, and values in the top range are Green.</span></span>  
  
 <span data-ttu-id="bb0a8-119">**Visualizza dati tramite colori personalizzati**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-119">**Visualize data by using custom colors**</span></span>  
 <span data-ttu-id="bb0a8-120">Selezionare questa opzione per visualizzare i dati analitici specificando il proprio elenco di colori.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-120">Select this option to visualize analytical data by specifying your own list of colors.</span></span>  
  
 <span data-ttu-id="bb0a8-121">**Campo dati**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-121">**Data field**</span></span>  
 <span data-ttu-id="bb0a8-122">Questa opzione viene visualizzata quando si seleziona una delle opzioni **Visualizza dati** .</span><span class="sxs-lookup"><span data-stu-id="bb0a8-122">This option appears when you select one of the **Visualize data** options.</span></span>  
  
 <span data-ttu-id="bb0a8-123">Selezionare il campo dei dati analitici da utilizzare dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-123">Select the analytical data field to use from the drop-down list.</span></span> <span data-ttu-id="bb0a8-124">A seconda dell'origine dati spaziali, l'elenco visualizza i campi dall'origine dati spaziali e da un set di dati del report che dispone di una relazione tra i dati spaziali e quelli analitici.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-124">Depending on the source of spatial data, the list displays fields from the spatial data source and from a report dataset that has a relationship between the spatial data and analytical data.</span></span> <span data-ttu-id="bb0a8-125">Per creare tale relazione, impostare le opzioni dei dati nella pagina Dati analitici per il livello mappa selezionato.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-125">To create such a relationship, set the data options on the Analytical Data page for the selected map layer.</span></span>  
  
 <span data-ttu-id="bb0a8-126">**Tavolozza**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-126">**Palette**</span></span>  
 <span data-ttu-id="bb0a8-127">Digitare o selezionare il nome della tavolozza colori.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-127">Type or select the name of the color palette.</span></span>  
  
 <span data-ttu-id="bb0a8-128">**Colore iniziale**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-128">**Start color**</span></span>  
 <span data-ttu-id="bb0a8-129">Specificare il colore da utilizzare per i dati nella parte inferiore dell'intervallo di dati.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-129">Specify the color to use for data at the low end of the data range.</span></span>  
  
 <span data-ttu-id="bb0a8-130">**Colore intermedio**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-130">**Middle color**</span></span>  
 <span data-ttu-id="bb0a8-131">Specificare il colore da utilizzare per i dati nella parte intermedia dell'intervallo di dati.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-131">Specify the color to use for data in the middle of the data range.</span></span> <span data-ttu-id="bb0a8-132">Selezionare **Nessun colore** per rimuovere questo intervallo.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-132">Select **No Color** to remove this range.</span></span>  
  
 <span data-ttu-id="bb0a8-133">**Colore finale**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-133">**End color**</span></span>  
 <span data-ttu-id="bb0a8-134">Specificare il colore da utilizzare per i dati nella parte superiore dell'intervallo di dati.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-134">Specify the color to use for data at the high end of the data range.</span></span>  
  
 <span data-ttu-id="bb0a8-135">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="bb0a8-135">**Add**</span></span>  
 <span data-ttu-id="bb0a8-136">Fare clic su **Aggiungi** per specificare i colori personalizzati per la regola colore.</span><span class="sxs-lookup"><span data-stu-id="bb0a8-136">Click **Add** to specify your own colors for the color rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb0a8-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb0a8-137">See Also</span></span>  
 <span data-ttu-id="bb0a8-138">[Mappe &#40;Generatore report e SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb0a8-138">[Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bb0a8-139">Modificare legende della mappa, scala dei colori e regole associate &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bb0a8-139">Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;</span></span>](report-design/change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md)  
  
  
