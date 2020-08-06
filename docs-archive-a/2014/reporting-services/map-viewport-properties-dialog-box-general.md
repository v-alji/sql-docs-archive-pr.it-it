---
title: Finestra di dialogo Proprietà viewport mappa, generale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.general.f1
- "10505"
ms.assetid: 6c9c773e-5c56-4571-95ed-8a157cfdfe52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d760d6a0572cbbd1bd948eab382c0727eb276c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623888"
---
# <a name="map-viewport-properties-dialog-box-general"></a><span data-ttu-id="e4926-102">Finestra di dialogo Proprietà viewport mappa, Generale</span><span class="sxs-lookup"><span data-stu-id="e4926-102">Map Viewport Properties Dialog Box, General</span></span>
  <span data-ttu-id="e4926-103">Selezionare **Generale** nella finestra di dialogo **Proprietà viewport mappa** per modificare le opzioni del sistema di coordinate, della proiezione e dei limiti.</span><span class="sxs-lookup"><span data-stu-id="e4926-103">Select **General** on the **Map Viewport Properties** dialog box to change the coordinate system, the projection, and the boundary options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e4926-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e4926-104">Options</span></span>  
 <span data-ttu-id="e4926-105">**Sistema di coordinate**</span><span class="sxs-lookup"><span data-stu-id="e4926-105">**Coordinate system**</span></span>  
 <span data-ttu-id="e4926-106">Indicare il tipo di sistema di coordinate utilizzato dai dati della mappa.</span><span class="sxs-lookup"><span data-stu-id="e4926-106">Indicate the type of coordinate system that the map data uses.</span></span>  
  
-   <span data-ttu-id="e4926-107">**Planare** Scegliere questa opzione quando i dati della mappa sono espressi con le coordinate X e Y, ad esempio per la compilazione di piani.</span><span class="sxs-lookup"><span data-stu-id="e4926-107">**Planar** Choose this option when map data is in X and Y coordinates, for example, for building plans.</span></span>  
  
-   <span data-ttu-id="e4926-108">**Geografico** Scegliere questa opzione quando i dati della mappa sono espressi con le coordinate della longitudine e della latitudine, ad esempio per la posizione delle città.</span><span class="sxs-lookup"><span data-stu-id="e4926-108">**Geographic** Choose this option when map data is in longitude and latitude coordinates, for example, for city locations.</span></span>  
  
 <span data-ttu-id="e4926-109">**Proiezione**</span><span class="sxs-lookup"><span data-stu-id="e4926-109">**Projection**</span></span>  
 <span data-ttu-id="e4926-110">Specificare il metodo da utilizzare per proiettare le coordinate geografiche su una superficie bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="e4926-110">Specify the method to use to project geographic coordinates onto a two-dimensional surface.</span></span> <span data-ttu-id="e4926-111">Scegliere una proiezione compatibile con i dati che si stanno visualizzando.</span><span class="sxs-lookup"><span data-stu-id="e4926-111">Choose a projection that is compatible with the data that you are visualizing.</span></span> <span data-ttu-id="e4926-112">Le quattro proprietà spaziali interessate dalla proiezione sono area, forma, distanza e direzione.</span><span class="sxs-lookup"><span data-stu-id="e4926-112">The four spatial properties that are affected by projection are area, shape, distance, and direction.</span></span> <span data-ttu-id="e4926-113">Per le viste della terra, la scelta di una proiezione ottimale dipende dalla vista con allineamento al centro, dai limiti della mappa e dal fattore di zoom.</span><span class="sxs-lookup"><span data-stu-id="e4926-113">For views of the earth, a good choice of projection depends on the center view, the map boundaries, and the zoom factor.</span></span>  
  
 <span data-ttu-id="e4926-114">Ognuna delle proiezioni seguenti mantiene almeno una di queste proprietà spaziali:</span><span class="sxs-lookup"><span data-stu-id="e4926-114">Each of the following projections preserves one or more of these spatial properties:</span></span>  
  
-   <span data-ttu-id="e4926-115">**Equirettangolare** Scegliere questa opzione per utilizzare longitudine e latitudine come coordinate rettangolari.</span><span class="sxs-lookup"><span data-stu-id="e4926-115">**Equirectangular** Choose this option to use longitude and latitude as rectangular coordinates.</span></span>  
  
-   <span data-ttu-id="e4926-116">**Mercator** Scegliere questa proiezione comune per le aree più piccole, per una minor distorsione attorno all'equatore o quando si desidera aggiungere un livello mappa con un livello sezione esistente che utilizza la proiezione Mercator.</span><span class="sxs-lookup"><span data-stu-id="e4926-116">**Mercator** Choose this popular projection for smaller areas, for less distortion around the equator, or when you want to add a map layer with an existing tile layer that uses the Mercator projection.</span></span>  
  
-   <span data-ttu-id="e4926-117">**Robinson** Scegliere questa opzione per una minor distorsione delle aree grandi che si estendono dall'equatore ai poli.</span><span class="sxs-lookup"><span data-stu-id="e4926-117">**Robinson** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="e4926-118">Sviluppata da Arthur H. Robinson nel 1963.</span><span class="sxs-lookup"><span data-stu-id="e4926-118">Developed by Arthur H. Robinson in 1963.</span></span>  
  
-   <span data-ttu-id="e4926-119">**Fahey** Scegliere questa opzione per una minor distorsione delle aree grandi che si estendono dall'equatore ai poli.</span><span class="sxs-lookup"><span data-stu-id="e4926-119">**Fahey** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="e4926-120">Sviluppata da Lawrence Fahey nel 1975.</span><span class="sxs-lookup"><span data-stu-id="e4926-120">Developed by Lawrence Fahey in 1975.</span></span>  
  
-   <span data-ttu-id="e4926-121">**Eckert1** Scegliere questa opzione per utilizzare paralleli equidistanti in latitudine e linee rette per i meridiani in longitudine.</span><span class="sxs-lookup"><span data-stu-id="e4926-121">**Eckert1** Choose this option to use equally spaced parallels in latitude and straight lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="e4926-122">**Eckert3** Scegliere questa opzione per utilizzare paralleli equidistanti in latitudine e linee curve per i meridiani in longitudine.</span><span class="sxs-lookup"><span data-stu-id="e4926-122">**Eckert3** Choose this option to use equally spaced parallels in latitude and curved lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="e4926-123">**HammerAitoff** Scegliere questa opzione per le mappe polari o del mondo.</span><span class="sxs-lookup"><span data-stu-id="e4926-123">**HammerAitoff** Choose this option for polar maps or world maps.</span></span>  
  
-   <span data-ttu-id="e4926-124">**Wagner3** Scegliere questa opzione per le mappe del mondo.</span><span class="sxs-lookup"><span data-stu-id="e4926-124">**Wagner3** Choose this option for world maps.</span></span>  
  
-   <span data-ttu-id="e4926-125">**Bonne** Scegliere questa opzione per visualizzare il mondo come è presentato in un atlante.</span><span class="sxs-lookup"><span data-stu-id="e4926-125">**Bonne** Choose this option to view the world as it appears in an atlas.</span></span>  
  
 <span data-ttu-id="e4926-126">**Opzioni di interruzione pagina**</span><span class="sxs-lookup"><span data-stu-id="e4926-126">**Page break options**</span></span>  
 <span data-ttu-id="e4926-127">Selezionare le opzioni per indicare il modo in cui il contenuto viene adattato alla pagina di un report.</span><span class="sxs-lookup"><span data-stu-id="e4926-127">Select options to indicate how content is fitted to a report page.</span></span>  
  
 <span data-ttu-id="e4926-128">**Opzioni relative ai limiti**</span><span class="sxs-lookup"><span data-stu-id="e4926-128">**Boundary options**</span></span>  
 <span data-ttu-id="e4926-129">Specificare i limiti inferiore e superiore affinché le coordinate controllino quale parte della mappa viene visualizzata nel report.</span><span class="sxs-lookup"><span data-stu-id="e4926-129">Specify the lower and upper boundaries for coordinates to control which part of the map appears in the report.</span></span>  
  
 <span data-ttu-id="e4926-130">**X minimo**</span><span class="sxs-lookup"><span data-stu-id="e4926-130">**Minimum X**</span></span>  
 <span data-ttu-id="e4926-131">Valore X minimo.</span><span class="sxs-lookup"><span data-stu-id="e4926-131">Lowest X value.</span></span> <span data-ttu-id="e4926-132">Disponibile solo per **Planare** .</span><span class="sxs-lookup"><span data-stu-id="e4926-132">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="e4926-133">**X massimo**</span><span class="sxs-lookup"><span data-stu-id="e4926-133">**Maximum X**</span></span>  
 <span data-ttu-id="e4926-134">Valore X massimo.</span><span class="sxs-lookup"><span data-stu-id="e4926-134">Highest X value.</span></span> <span data-ttu-id="e4926-135">Disponibile solo per **Planare** .</span><span class="sxs-lookup"><span data-stu-id="e4926-135">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="e4926-136">**Y minimo**</span><span class="sxs-lookup"><span data-stu-id="e4926-136">**Minimum Y**</span></span>  
 <span data-ttu-id="e4926-137">Valore Y minimo.</span><span class="sxs-lookup"><span data-stu-id="e4926-137">Lowest Y value.</span></span> <span data-ttu-id="e4926-138">Disponibile solo per **Planare** .</span><span class="sxs-lookup"><span data-stu-id="e4926-138">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="e4926-139">**Y massimo**</span><span class="sxs-lookup"><span data-stu-id="e4926-139">**Maximum Y**</span></span>  
 <span data-ttu-id="e4926-140">Valore Y massimo.</span><span class="sxs-lookup"><span data-stu-id="e4926-140">Highest Y value.</span></span> <span data-ttu-id="e4926-141">Disponibile solo per **Planare** .</span><span class="sxs-lookup"><span data-stu-id="e4926-141">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="e4926-142">**Longitudine minima**</span><span class="sxs-lookup"><span data-stu-id="e4926-142">**Minimum Longitude**</span></span>  
 <span data-ttu-id="e4926-143">Valore della longitudine minimo.</span><span class="sxs-lookup"><span data-stu-id="e4926-143">Lowest longitude value.</span></span> <span data-ttu-id="e4926-144">Disponibile solo per **Geografico** .</span><span class="sxs-lookup"><span data-stu-id="e4926-144">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="e4926-145">**Longitudine massima**</span><span class="sxs-lookup"><span data-stu-id="e4926-145">**Maximum Longitude**</span></span>  
 <span data-ttu-id="e4926-146">Valore della longitudine massimo.</span><span class="sxs-lookup"><span data-stu-id="e4926-146">Highest longitude value.</span></span> <span data-ttu-id="e4926-147">Disponibile solo per **Geografico** .</span><span class="sxs-lookup"><span data-stu-id="e4926-147">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="e4926-148">**Latitudine minima**</span><span class="sxs-lookup"><span data-stu-id="e4926-148">**Minimum Latitude**</span></span>  
 <span data-ttu-id="e4926-149">Valore della latitudine minimo.</span><span class="sxs-lookup"><span data-stu-id="e4926-149">Lowest latitude value.</span></span> <span data-ttu-id="e4926-150">Disponibile solo per **Geografico** .</span><span class="sxs-lookup"><span data-stu-id="e4926-150">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="e4926-151">**Latitudine massima**</span><span class="sxs-lookup"><span data-stu-id="e4926-151">**Maximum Latitude**</span></span>  
 <span data-ttu-id="e4926-152">Valore della latitudine massimo.</span><span class="sxs-lookup"><span data-stu-id="e4926-152">Highest latitude value.</span></span> <span data-ttu-id="e4926-153">Disponibile solo per **Geografico** .</span><span class="sxs-lookup"><span data-stu-id="e4926-153">Available for **Geographic** only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4926-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4926-154">See Also</span></span>  
 [<span data-ttu-id="e4926-155">Mappe &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e4926-155">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
