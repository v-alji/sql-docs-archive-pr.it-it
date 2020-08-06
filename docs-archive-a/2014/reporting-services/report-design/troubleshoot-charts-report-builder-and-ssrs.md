---
title: Risolvere i problemi relativi ai grafici (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a327ffa-3b69-40d6-8015-cc01cfae9161
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b931b50545ba2b8d7c4c06cc5c48d6415a05470a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717447"
---
# <a name="troubleshoot-charts-report-builder-and-ssrs"></a><span data-ttu-id="06b1e-102">Risoluzione dei problemi relativi ai grafici (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="06b1e-102">Troubleshoot Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="06b1e-103">Queste informazioni possono essere utili in caso di utilizzo di grafici.</span><span class="sxs-lookup"><span data-stu-id="06b1e-103">These issues can be helpful when working with charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="why-does-my-chart-count-not-sum-the-values-on-the-value-axis"></a><span data-ttu-id="06b1e-104">Nel grafico viene eseguito il conteggio, anziché la somma, dei valori sull'asse dei valori</span><span class="sxs-lookup"><span data-stu-id="06b1e-104">Why does my chart count, not sum, the values on the value axis?</span></span>  
 <span data-ttu-id="06b1e-105">Per tracciare correttamente la maggior parte dei grafici, sono necessari valori numerici lungo l'asse dei valori, che in genere corrisponde all'asse Y.</span><span class="sxs-lookup"><span data-stu-id="06b1e-105">Most chart types require numeric values along the value axis, which is typically the y-axis, in order to draw correctly.</span></span> <span data-ttu-id="06b1e-106">Se il tipo di dati del campo valori è `String`, non sarà possibile visualizzare un valore numerico, neanche se nei campi sono presenti numeri.</span><span class="sxs-lookup"><span data-stu-id="06b1e-106">If the data type of your value field is `String`, the chart cannot display a numeric value, even if there are numerals in the fields.</span></span> <span data-ttu-id="06b1e-107">Viene invece visualizzato un conteggio del numero totale di righe che contengono un valore in tale campo.</span><span class="sxs-lookup"><span data-stu-id="06b1e-107">Instead, the chart displays a count of the total number of rows that contain a value in that field.</span></span> <span data-ttu-id="06b1e-108">Per evitare questo comportamento, assicurarsi che i campi utilizzati per le serie di valori abbiano tipi di dati numerici anziché stringhe che contengono numeri formattati.</span><span class="sxs-lookup"><span data-stu-id="06b1e-108">To avoid this behavior, make sure that the fields that you use for value series have numeric data types, as opposed to strings that contain formatted numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b1e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06b1e-109">See Also</span></span>  
 [<span data-ttu-id="06b1e-110">Grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="06b1e-110">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
