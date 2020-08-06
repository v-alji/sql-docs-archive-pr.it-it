---
title: Impostare un valore minimo o massimo su un misuratore (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b4c260c0-5a88-4f30-8977-eb5cc78fc146
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 344122dbff647a8c35b838ecce637602f202864b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625144"
---
# <a name="set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="4428c-102">Impostare un valore minimo o massimo su un misuratore (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="4428c-102">Set a Minimum or Maximum on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4428c-103">A differenza del grafico in cui sono definiti più gruppi, il misuratore mostra un solo valore.</span><span class="sxs-lookup"><span data-stu-id="4428c-103">Unlike the chart, where multiple groups are defined, the gauge only shows one value.</span></span> <span data-ttu-id="4428c-104">Poiché Generatore report e Progettazione report possono determinare il significato contestuale o relativo del valore che si sta tentando di visualizzare sul misuratore, è necessario definire il valore minimo e massimo per la scala.</span><span class="sxs-lookup"><span data-stu-id="4428c-104">Since Report Builder and Report Designer determine the context or relative significance of the one value that you are trying to show on the gauge, you must define the minimum and maximum of the scale.</span></span> <span data-ttu-id="4428c-105">Se, ad esempio, i valori dei dati sono ranghi compresi tra 0 e 10, è possibile impostare il valore minimo su 0 e quello massimo su 10.</span><span class="sxs-lookup"><span data-stu-id="4428c-105">For example, if your data values are rankings between 0 and 10, you will want to set the minimum to 0 and maximum to 10.</span></span> <span data-ttu-id="4428c-106">I numeri dell'intervallo vengono calcolati automaticamente in base ai valori specificati per l'impostazione minima e massima.</span><span class="sxs-lookup"><span data-stu-id="4428c-106">The interval numbers are calculated automatically based on the values specified for the minimum and maximum.</span></span> <span data-ttu-id="4428c-107">Per impostazione predefinita, i valori minimo e massimo vengono impostati su 0 e 100, ovvero due valori arbitrari che è necessario modificare.</span><span class="sxs-lookup"><span data-stu-id="4428c-107">By default, the minimum and maximum are set to 0 and 100, but this is an arbitrary value that you should change.</span></span> <span data-ttu-id="4428c-108">L'applicazione non calcola il valore come percentuale.</span><span class="sxs-lookup"><span data-stu-id="4428c-108">The application does not calculate your value as a percentage.</span></span>  
  
 <span data-ttu-id="4428c-109">Se l'intervallo dei valori è grande, ad esempio da 0 a 10000, utilizzare un moltiplicatore per ridurre il numero di zero sul misuratore.</span><span class="sxs-lookup"><span data-stu-id="4428c-109">If the range of your values is large, for example from 0 to 10000, consider using a multiplier to reduce the number of zeroes on the gauge.</span></span> <span data-ttu-id="4428c-110">Il moltiplicatore ridurrà solo la scala dei numeri sul misuratore, non il valore stesso.</span><span class="sxs-lookup"><span data-stu-id="4428c-110">The multiplier will only reduce the scale of the numbers on the gauge, not the value itself.</span></span>  
  
 <span data-ttu-id="4428c-111">È possibile usare espressioni per impostare i valori delle opzioni **Minimo** e **Massimo** .</span><span class="sxs-lookup"><span data-stu-id="4428c-111">You can use expressions to set the values of the **Minimum** and **Maximum** options.</span></span> <span data-ttu-id="4428c-112">Per altre informazioni, vedere [Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4428c-112">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-minimum-and-maximum-on-the-gauge"></a><span data-ttu-id="4428c-113">Per impostare i valori minimo e massimo sul misuratore</span><span class="sxs-lookup"><span data-stu-id="4428c-113">To set the minimum and maximum on the gauge</span></span>  
  
1.  <span data-ttu-id="4428c-114">Fare clic con il pulsante destro del mouse sulla scala e selezionare **Proprietà scala**.</span><span class="sxs-lookup"><span data-stu-id="4428c-114">Right-click on the scale and select **Scale Properties**.</span></span> <span data-ttu-id="4428c-115">Verrà visualizzata la finestra di dialogo **Proprietà scala** .</span><span class="sxs-lookup"><span data-stu-id="4428c-115">The **Scale Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="4428c-116">In **Generale**specificare un valore per **Minimo**.</span><span class="sxs-lookup"><span data-stu-id="4428c-116">In **General**, specify a value for **Minimum**.</span></span> <span data-ttu-id="4428c-117">Per impostazione predefinita, questo valore è 0.</span><span class="sxs-lookup"><span data-stu-id="4428c-117">By default, this value is 0.</span></span> <span data-ttu-id="4428c-118">Se lo si desidera, fare clic sul pulsante **Espressione** (*fx*) per modificare l'espressione che imposta il valore per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="4428c-118">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
3.  <span data-ttu-id="4428c-119">Specificare un valore per **Massimo**.</span><span class="sxs-lookup"><span data-stu-id="4428c-119">Specify a value for **Maximum**.</span></span> <span data-ttu-id="4428c-120">Per impostazione predefinita, tale valore è 100.</span><span class="sxs-lookup"><span data-stu-id="4428c-120">By default, this value is 100.</span></span> <span data-ttu-id="4428c-121">Se lo si desidera, fare clic sul pulsante **Espressione** (*fx*) per modificare l'espressione che imposta il valore per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="4428c-121">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="4428c-122">(Facoltativo) Se i valori per le impostazioni Minimo e Massimo sono elevati, specificare un valore per l'opzione **Moltiplica etichette di scala per** .</span><span class="sxs-lookup"><span data-stu-id="4428c-122">(Optional) If the values for your minimum and maximum are large, specify a value for the **Multiply scale labels by** option.</span></span> <span data-ttu-id="4428c-123">Per specificare un moltiplicatore in modo da ridurre la scala, utilizzare un numero decimale.</span><span class="sxs-lookup"><span data-stu-id="4428c-123">To specify a multiplier that reduces your scale, use a decimal number.</span></span> <span data-ttu-id="4428c-124">Se, ad esempio, si dispone di una scala compresa tra 0 e 1000, è possibile specificare un valore di moltiplicatore pari a 0,01 per ridurre la scala ai valori compresi tra 0 e 10.</span><span class="sxs-lookup"><span data-stu-id="4428c-124">For example, if you have a scale from 0 to 1000, you can specify a multiplier value of 0.01 to reduce the scale to read 0 to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4428c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4428c-125">See Also</span></span>  
 <span data-ttu-id="4428c-126">[Formattazione di scale su un misuratore &#40;Generatore report e SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4428c-126">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4428c-127">[Formattazione degli indicatori di misura su un misuratore &#40;Generatore report e SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4428c-127">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4428c-128">Misuratori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4428c-128">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
