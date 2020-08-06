---
title: Finestra di dialogo Proprietà viewport mappa, allineamento al centro e zoom | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.centerandzoom.f1
- "10506"
ms.assetid: 642a06f5-293f-48e0-97a6-1489dbefa719
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 913c00773abf71ca627b8cc2a94a873484e8ab30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626560"
---
# <a name="map-viewport-properties-dialog-box-center-and-zoom"></a><span data-ttu-id="6cb21-102">Finestra di dialogo Proprietà viewport mappa, Allineamento al centro e zoom</span><span class="sxs-lookup"><span data-stu-id="6cb21-102">Map Viewport Properties Dialog Box, Center and Zoom</span></span>
  <span data-ttu-id="6cb21-103">Selezionare **Centra e zoom** affinché tramite la finestra di dialogo **Proprietà viewport mappa** venga impostata la vista con allineamento al centro e il fattore di zoom per una mappa.</span><span class="sxs-lookup"><span data-stu-id="6cb21-103">Select **Center and Zoom** for the **Map Viewport Properties** dialog box to set the center view and zoom factor for a map.</span></span> <span data-ttu-id="6cb21-104">Dopo aver specificato un'origine dati della mappa e i limiti della mappa che si desidera includere nel report, è possibile specificare l'allineamento al centro della vista e il fattore di zoom per controllare ulteriormente la visualizzazione della mappa.</span><span class="sxs-lookup"><span data-stu-id="6cb21-104">After you specify a map data source and the boundaries of the map that you want to include in your report, you can specify the view center and the zoom factor to further control the map display.</span></span> <span data-ttu-id="6cb21-105">Le opzioni variano a seconda del metodo utilizzato per specificare i valori di allineamento al centro e zoom.</span><span class="sxs-lookup"><span data-stu-id="6cb21-105">Options change depending on which method you use to specify the center and zoom values.</span></span> <span data-ttu-id="6cb21-106">Fare clic sul pulsante **Espressione** (*fx*) per modificare un'espressione che imposta il valore per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="6cb21-106">Click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6cb21-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6cb21-107">Options</span></span>  
 <span data-ttu-id="6cb21-108">**Imposta un livello di allineamento al centro e zoom della vista**</span><span class="sxs-lookup"><span data-stu-id="6cb21-108">**Set a view center and zoom level**</span></span>  
 <span data-ttu-id="6cb21-109">Scegliere questa opzione per specificare valori personalizzati per il livello di allineamento al centro e zoom della vista.</span><span class="sxs-lookup"><span data-stu-id="6cb21-109">Choose this option to specify custom values for the view center and the zoom level.</span></span>  
  
 <span data-ttu-id="6cb21-110">**Allinea al centro la mappa per mostrare un livello mappa**</span><span class="sxs-lookup"><span data-stu-id="6cb21-110">**Center map to show a map layer**</span></span>  
 <span data-ttu-id="6cb21-111">Scegliere questa opzione per specificare un livello e allineare automaticamente al centro la vista sui dati della mappa.</span><span class="sxs-lookup"><span data-stu-id="6cb21-111">Choose this option to specify a layer and automatically center the view on its map data.</span></span> <span data-ttu-id="6cb21-112">Ad esempio allineare al centro la vista su LineLayer1.</span><span class="sxs-lookup"><span data-stu-id="6cb21-112">For example, center the view on LineLayer1.</span></span>  
  
 <span data-ttu-id="6cb21-113">**Allinea al centro la mappa per mostrare un elemento della mappa incorporato**</span><span class="sxs-lookup"><span data-stu-id="6cb21-113">**Center map to show an embedded map element**</span></span>  
 <span data-ttu-id="6cb21-114">Scegliere questa opzione per allineare al centro la vista su un elemento della mappa associato a dati specifico.</span><span class="sxs-lookup"><span data-stu-id="6cb21-114">Choose this option to center the view on a specific data-bound map element.</span></span> <span data-ttu-id="6cb21-115">I dati spaziali devono disporre di una relazione con i dati analitici per specificare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="6cb21-115">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="6cb21-116">Ad esempio allineare al centro la vista sull'elemento della mappa in cui il nome del campo delle corrispondenze è [Città] e il valore della corrispondenza è "Seattle".</span><span class="sxs-lookup"><span data-stu-id="6cb21-116">For example, center the view on the map element where the name of the match field is [City] and the match value is "Seattle".</span></span>  
  
 <span data-ttu-id="6cb21-117">**Allinea al centro la mappa per mostrare tutti gli elementi associati a dati**</span><span class="sxs-lookup"><span data-stu-id="6cb21-117">**Center map to show all data-bound map elements**</span></span>  
 <span data-ttu-id="6cb21-118">Scegliere questa opzione per allineare al centro la vista su tutti gli elementi della mappa del livello.</span><span class="sxs-lookup"><span data-stu-id="6cb21-118">Choose this option to center the view on all map elements in the layer.</span></span> <span data-ttu-id="6cb21-119">I dati spaziali devono disporre di una relazione con i dati analitici per specificare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="6cb21-119">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="6cb21-120">Ad esempio allineare al centro la vista sul livello bolle poligono che visualizza le città. Le dimensioni delle bolle sono correlate alla popolazione.</span><span class="sxs-lookup"><span data-stu-id="6cb21-120">For example, center the view on the polygon bubble layer that shows cities and the bubble size is related to population.</span></span> <span data-ttu-id="6cb21-121">Vengono incluse solo le città con un valore della popolazione corrispondente quando si calcola il centro per il viewport.</span><span class="sxs-lookup"><span data-stu-id="6cb21-121">Only those cities with a matching population value are included when calculating the center for the viewport.</span></span>  
  
 <span data-ttu-id="6cb21-122">**Opzioni di allineamento al centro e zoom**</span><span class="sxs-lookup"><span data-stu-id="6cb21-122">**Center and zoom options**</span></span>  
 <span data-ttu-id="6cb21-123">Selezionare un'opzione per specificare il livello di allineamento al centro e zoom della vista.</span><span class="sxs-lookup"><span data-stu-id="6cb21-123">Select an option to specify the view center and zoom level.</span></span>  
  
 <span data-ttu-id="6cb21-124">**Centro visualizzazione X (percentuale)**</span><span class="sxs-lookup"><span data-stu-id="6cb21-124">**View center (X) %**</span></span>  
 <span data-ttu-id="6cb21-125">Coordinata orizzontale.</span><span class="sxs-lookup"><span data-stu-id="6cb21-125">The horizontal coordinate.</span></span> <span data-ttu-id="6cb21-126">Il valore predefinito 50%</span><span class="sxs-lookup"><span data-stu-id="6cb21-126">The default value, 50%.</span></span> <span data-ttu-id="6cb21-127">consente di allineare al centro la vista sul punto medio tra i valori orizzontali minimo e massimo.</span><span class="sxs-lookup"><span data-stu-id="6cb21-127">centers the view at the midpoint between the minimum and maximum horizontal values.</span></span>  
  
 <span data-ttu-id="6cb21-128">**Centro visualizzazione Y (percentuale)**</span><span class="sxs-lookup"><span data-stu-id="6cb21-128">**View center (Y) %**</span></span>  
 <span data-ttu-id="6cb21-129">Coordinata verticale.</span><span class="sxs-lookup"><span data-stu-id="6cb21-129">The vertical coordinate.</span></span> <span data-ttu-id="6cb21-130">Il valore predefinito, 50%, allinea al centro la vista sul punto medio tra i valori verticali minimo e massimo.</span><span class="sxs-lookup"><span data-stu-id="6cb21-130">The default value, 50%, centers the view at the midpoint between the minimum and maximum vertical values.</span></span>  
  
 <span data-ttu-id="6cb21-131">**Livello zoom (%)**</span><span class="sxs-lookup"><span data-stu-id="6cb21-131">**Zoom level (%)**</span></span>  
 <span data-ttu-id="6cb21-132">Fattore di zoom.</span><span class="sxs-lookup"><span data-stu-id="6cb21-132">The zoom factor.</span></span> <span data-ttu-id="6cb21-133">Il valore predefinito, 100%, indica nessun ingrandimento.</span><span class="sxs-lookup"><span data-stu-id="6cb21-133">The default value, 100%, indicates no magnification.</span></span>  
  
 <span data-ttu-id="6cb21-134">**Allinea al centro la visualizzazione su questo livello**</span><span class="sxs-lookup"><span data-stu-id="6cb21-134">**Center view on this layer**</span></span>  
 <span data-ttu-id="6cb21-135">Specificare il nome del livello.</span><span class="sxs-lookup"><span data-stu-id="6cb21-135">Specify the name of the layer.</span></span>  
  
 <span data-ttu-id="6cb21-136">**Allinea al centro la visualizzazione sull'elemento della mappa che soddisfa questa condizione**</span><span class="sxs-lookup"><span data-stu-id="6cb21-136">**Center view on the map element that matches this condition**</span></span>  
 <span data-ttu-id="6cb21-137">Il campo di sola lettura visualizzato viene utilizzato per far corrispondere i dati della mappa e quelli analitici.</span><span class="sxs-lookup"><span data-stu-id="6cb21-137">The read-only field that is displayed is used to match map data and analytical data.</span></span> <span data-ttu-id="6cb21-138">Specificare il valore con cui eseguire la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="6cb21-138">Specify the value that you want to match on.</span></span> <span data-ttu-id="6cb21-139">La vista viene allineata automaticamente al centro su questo elemento della mappa.</span><span class="sxs-lookup"><span data-stu-id="6cb21-139">The view automatically centers on this map element.</span></span> <span data-ttu-id="6cb21-140">Ad esempio NAME = TEXAS.</span><span class="sxs-lookup"><span data-stu-id="6cb21-140">For example, NAME = TEXAS.</span></span> <span data-ttu-id="6cb21-141">Per impostazione predefinita, il tipo di dati per la condizione è String e la corrispondenza supporta la distinzione tra lettere maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="6cb21-141">By default, the data type for the condition is String and the match is case-sensitive.</span></span>  
  
 <span data-ttu-id="6cb21-142">Per eseguire la corrispondenza con un campo che dispone di un tipo di dati diverso, è necessario scrivere un'espressione che restituisce tale tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="6cb21-142">To match on a field that has a different data type, you must write an expression that evaluates to that data type.</span></span> <span data-ttu-id="6cb21-143">Ad esempio se il campo delle corrispondenze è un codice postale di 5 cifre archiviato come un numero intero, per specificare il codice postale 98053 è necessario utilizzare l'espressione = 98053.</span><span class="sxs-lookup"><span data-stu-id="6cb21-143">For example, if the match field is a 5 digit postal code that is stored as an integer, then to specify the postal code 98053, you must use the expression =98053.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb21-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cb21-144">See Also</span></span>  
 [<span data-ttu-id="6cb21-145">Mappe &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6cb21-145">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
