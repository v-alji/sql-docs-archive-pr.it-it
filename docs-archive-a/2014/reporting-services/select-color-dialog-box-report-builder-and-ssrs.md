---
title: Finestra di dialogo Seleziona colore (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.selectcolor.f1
- "10090"
helpviewer_keywords:
- Select Color dialog box
ms.assetid: ac7089a3-5c7b-4f53-8348-180610e86da2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a2526b755fd4e08faf79998d351e824371fac2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723324"
---
# <a name="select-color-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="f2604-102">Finestra di dialogo Seleziona colore (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f2604-102">Select Color Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f2604-103">Utilizzare la finestra di dialogo **Seleziona colore** per specificare le opzioni relative al colore per lo sfondo di una o più celle in un'area dati o in una casella di testo oppure per un grafico.</span><span class="sxs-lookup"><span data-stu-id="f2604-103">Use the **Select Color** dialog box to specify color options for the background of a single cell or multiple cells within a data region or a text box, or for a chart.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f2604-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f2604-104">Options</span></span>  
 <span data-ttu-id="f2604-105">**Selettore colori**</span><span class="sxs-lookup"><span data-stu-id="f2604-105">**Color selector**</span></span>  
 <span data-ttu-id="f2604-106">Scegliere una delle tre opzioni disponibili per specificare la modalità di selezione dei colori:</span><span class="sxs-lookup"><span data-stu-id="f2604-106">Choose from three options that specify how you want to select colors:</span></span>  
  
-   <span data-ttu-id="f2604-107">**Selezione - Cerchio colori** Consente di scegliere un colore specificando i relativi valori HSB (Hue/Saturation/Brightness, tonalità/saturazione/luminosità).</span><span class="sxs-lookup"><span data-stu-id="f2604-107">**Picker - Color circle** Choose a color using Hue/Saturation/Brightness (HSB) color values.</span></span>  
  
-   <span data-ttu-id="f2604-108">**Selezione - Quadrato colori** Consente di scegliere un colore specificando i relativi valori RGB (Red/Green/Blue, rosso/verde/blu).</span><span class="sxs-lookup"><span data-stu-id="f2604-108">**Picker - Color square** Choose a color using Red/Green/Blue (RGB) color values.</span></span>  
  
-   <span data-ttu-id="f2604-109">**Tavolozza - Colori standard** Consente di scegliere un colore da un elenco predefinito di valori.</span><span class="sxs-lookup"><span data-stu-id="f2604-109">**Palette - Standard colors** Choose a color from a predefined list of color values.</span></span>  
  
 <span data-ttu-id="f2604-110">**Cerchio colori**</span><span class="sxs-lookup"><span data-stu-id="f2604-110">**Color circle**</span></span>  
 <span data-ttu-id="f2604-111">Utilizzare questa opzione per i colori HSB perché il mapping dei valori HSB viene eseguito su un sistema di coordinate cilindrico.</span><span class="sxs-lookup"><span data-stu-id="f2604-111">Use for HSB colors because HSB values are mapped onto a cylindrical coordinate system.</span></span> <span data-ttu-id="f2604-112">La tonalità corrisponde al colore effettivo, la saturazione alla purezza del colore, la luminosità alla luminosità o alla oscurità relativa.</span><span class="sxs-lookup"><span data-stu-id="f2604-112">Hue is the actual color, saturation is purity of color, brightness is relative brightness or darkness.</span></span>  
  
 <span data-ttu-id="f2604-113">Quando si effettua una scelta, il centro del cerchio determina il colore.</span><span class="sxs-lookup"><span data-stu-id="f2604-113">When you pick a color, the center of the circle determines the color.</span></span> <span data-ttu-id="f2604-114">Utilizzare il dispositivo di scorrimento del colore per cambiare la tonalità.</span><span class="sxs-lookup"><span data-stu-id="f2604-114">Use the color slider to change the hue.</span></span> <span data-ttu-id="f2604-115">Le coordinate x e y rappresentano rispettivamente i valori di saturazione e luminosità.</span><span class="sxs-lookup"><span data-stu-id="f2604-115">The x and y coordinates represent saturation and brightness values respectively.</span></span>  
  
 <span data-ttu-id="f2604-116">**Quadrato colori**</span><span class="sxs-lookup"><span data-stu-id="f2604-116">**Color square**</span></span>  
 <span data-ttu-id="f2604-117">Utilizzare questa opzione per i colori RGB perché il mapping dei valori RGB viene eseguito su un sistema di coordinate cartesiano.</span><span class="sxs-lookup"><span data-stu-id="f2604-117">Use for RGB colors because RGB values are mapped to a Cartesian coordinate system.</span></span> <span data-ttu-id="f2604-118">R corrisponde al valore del rosso, G al valore del verde e B al valore del blu.</span><span class="sxs-lookup"><span data-stu-id="f2604-118">R is the value for Red, G is the value for Green, B is the value for Blue.</span></span>  
  
 <span data-ttu-id="f2604-119">Quando si effettua una scelta, il centro del quadrato determina il colore.</span><span class="sxs-lookup"><span data-stu-id="f2604-119">When you pick a color, the center of the square determines the color.</span></span> <span data-ttu-id="f2604-120">Utilizzare il dispositivo di scorrimento del colore per cambiare la gamma del colore scelto.</span><span class="sxs-lookup"><span data-stu-id="f2604-120">Use the color slider to change the range of the chosen color.</span></span> <span data-ttu-id="f2604-121">Le coordinate x e y rappresentano gli altri due colori.</span><span class="sxs-lookup"><span data-stu-id="f2604-121">The x and y coordinates represent the other two colors.</span></span> <span data-ttu-id="f2604-122">Se ad esempio si sceglie il colore verde, il dispositivo di scorrimento visualizza la gamma di valori del verde, mentre le coordinate x e y rappresentano rispettivamente i valori del rosso e del blu.</span><span class="sxs-lookup"><span data-stu-id="f2604-122">For example, if you pick green, the slider shows the range of green values, the x and y coordinates represent red and blue values respectively.</span></span>  
  
 <span data-ttu-id="f2604-123">**Tavolozza colori standard**</span><span class="sxs-lookup"><span data-stu-id="f2604-123">**Standard palette color**</span></span>  
 <span data-ttu-id="f2604-124">Utilizzare per i colori denominati dall' [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f2604-124">Use for named colors from the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` enumeration.</span></span>  
  
 <span data-ttu-id="f2604-125">**Sistema colori**</span><span class="sxs-lookup"><span data-stu-id="f2604-125">**Color system**</span></span>  
 <span data-ttu-id="f2604-126">Specificare i colori RGB o HSB.</span><span class="sxs-lookup"><span data-stu-id="f2604-126">Specify RGB or HSB colors.</span></span> <span data-ttu-id="f2604-127">Questa opzione consente di visualizzare i valori RGB o HSB, che vengono aggiornati in modo interattivo quando si utilizza un cerchio o un quadrato di colori per **Selettore colori**.</span><span class="sxs-lookup"><span data-stu-id="f2604-127">This choice changes the display to show RGB or HSB values, which are updated interactively when you use a color circle or color square for the **Color selector**.</span></span>  
  
 <span data-ttu-id="f2604-128">Il valore **Alfa** viene visualizzato per alcune proprietà quando un colore può includere un valore di trasparenza,</span><span class="sxs-lookup"><span data-stu-id="f2604-128">The **Alpha** value displays for some properties when a color can include a transparency value.</span></span> <span data-ttu-id="f2604-129">ad esempio nel caso del riempimento della serie del grafico.</span><span class="sxs-lookup"><span data-stu-id="f2604-129">For example, Chart series fill.</span></span> <span data-ttu-id="f2604-130">Per le proprietà che non supportano la trasparenza, questo valore è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="f2604-130">For properties that do not support transparency, this value is disabled.</span></span>  
  
 <span data-ttu-id="f2604-131">**Red**</span><span class="sxs-lookup"><span data-stu-id="f2604-131">**Red**</span></span>  
 <span data-ttu-id="f2604-132">Valore decimale relativo alla parte rossa del colore RGB.</span><span class="sxs-lookup"><span data-stu-id="f2604-132">The decimal value for the red part of the RGB color.</span></span> <span data-ttu-id="f2604-133">Utilizzare la casella di selezione per modificare il valore o digitare un valore compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="f2604-133">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="f2604-134">**Green**</span><span class="sxs-lookup"><span data-stu-id="f2604-134">**Green**</span></span>  
 <span data-ttu-id="f2604-135">Valore decimale relativo alla parte verde del colore RGB.</span><span class="sxs-lookup"><span data-stu-id="f2604-135">The decimal value for the green part of the RGB color.</span></span> <span data-ttu-id="f2604-136">Utilizzare la casella di selezione per modificare il valore o digitare un valore compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="f2604-136">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="f2604-137">**Blue**</span><span class="sxs-lookup"><span data-stu-id="f2604-137">**Blue**</span></span>  
 <span data-ttu-id="f2604-138">Valore decimale relativo alla parte blu del colore RGB.</span><span class="sxs-lookup"><span data-stu-id="f2604-138">The decimal value for the blue part of the RGB color.</span></span> <span data-ttu-id="f2604-139">Utilizzare la casella di selezione per modificare il valore o digitare un valore compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="f2604-139">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="f2604-140">**Alfa**</span><span class="sxs-lookup"><span data-stu-id="f2604-140">**Alpha**</span></span>  
 <span data-ttu-id="f2604-141">Valore decimale relativo alla parte alfa o di trasparenza del colore.</span><span class="sxs-lookup"><span data-stu-id="f2604-141">The decimal value for the alpha or transparency part of the color.</span></span> <span data-ttu-id="f2604-142">Quando questo valore è abilitato, è possibile utilizzare il dispositivo di scorrimento per regolare il grado di trasparenza desiderato.</span><span class="sxs-lookup"><span data-stu-id="f2604-142">When this value is enabled, you can use the slider switch to adjust the degree of transparency you want.</span></span>  
  
 <span data-ttu-id="f2604-143">**Hue**</span><span class="sxs-lookup"><span data-stu-id="f2604-143">**Hue**</span></span>  
 <span data-ttu-id="f2604-144">Valore decimale relativo alla tonalità del colore HSB.</span><span class="sxs-lookup"><span data-stu-id="f2604-144">The decimal value for the hue of the HSB color.</span></span> <span data-ttu-id="f2604-145">Utilizzare la casella di selezione per modificare il valore o digitare un valore compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="f2604-145">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="f2604-146">**Saturazione**</span><span class="sxs-lookup"><span data-stu-id="f2604-146">**Saturation**</span></span>  
 <span data-ttu-id="f2604-147">Valore decimale relativo alla saturazione del colore HSB.</span><span class="sxs-lookup"><span data-stu-id="f2604-147">The decimal value for the saturation of the HSB color.</span></span> <span data-ttu-id="f2604-148">Utilizzare la casella di selezione per modificare il valore o digitare un valore compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="f2604-148">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="f2604-149">**Brightness (Luminosità)**</span><span class="sxs-lookup"><span data-stu-id="f2604-149">**Brightness**</span></span>  
 <span data-ttu-id="f2604-150">Valore decimale relativo alla luminosità del colore HSB.</span><span class="sxs-lookup"><span data-stu-id="f2604-150">The decimal value for the brightness of the HSB color.</span></span> <span data-ttu-id="f2604-151">Utilizzare la casella di selezione per modificare il valore o digitare un valore compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="f2604-151">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="f2604-152">**Esempio di colore**</span><span class="sxs-lookup"><span data-stu-id="f2604-152">**Color sample**</span></span>  
 <span data-ttu-id="f2604-153">Visualizza il colore corrente nella parte sinistra del riquadro e mostra in modo interattivo il nuovo colore scelto nella parte destra.</span><span class="sxs-lookup"><span data-stu-id="f2604-153">Shows the current color on the left half of the pane and interactively shows the new color you are choosing on the right half of the pane.</span></span> <span data-ttu-id="f2604-154">Se non è presente un colore predefinito, la parte sinistra del riquadro è bianca.</span><span class="sxs-lookup"><span data-stu-id="f2604-154">If there is no default color, the left half of the pane is white.</span></span> <span data-ttu-id="f2604-155">Per la maggior parte delle proprietà RDL non è disponibile alcun colore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f2604-155">Most RDL properties have no default color.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2604-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2604-156">See Also</span></span>  
 <span data-ttu-id="f2604-157">[Formattazione degli elementi del report &#40;Generatore report e SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2604-157">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f2604-158">Formattazione di testo e segnaposto &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f2604-158">Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;</span></span>](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md)  
  
  
