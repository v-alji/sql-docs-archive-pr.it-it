---
title: Contenuto di FORE_COLOR e di BACK_COLOR (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- FORE_COLOR contents
- backgrounds [MDX]
- cells [MDX]
- colors [MDX]
- storing cell color information
- cell backgrounds
- BACK_COLOR contents
ms.assetid: ff8f40cb-2ac4-4fc2-9761-7f1b14c17c8c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 748754ec3c90bb44392d7acb7de8f815be24086e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721924"
---
# <a name="fore_color-and-back_color-contents-mdx"></a><span data-ttu-id="e93ae-102">Contenuto di FORE_COLOR e BACK_COLOR (MDX)</span><span class="sxs-lookup"><span data-stu-id="e93ae-102">FORE_COLOR and BACK_COLOR Contents (MDX)</span></span>
  <span data-ttu-id="e93ae-103">Nelle proprietà `FORE_COLOR` e `BACK_COLOR` di una cella sono archiviate, rispettivamente, informazioni sui colori del testo e dello sfondo della cella, nel formato RGB di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="e93ae-103">The `FORE_COLOR` and `BACK_COLOR` cell properties store color information for the text and the background of a cell, respectively, in the Microsoft Windows operating system red-green-blue (RGB) format.</span></span>  
  
 <span data-ttu-id="e93ae-104">I valori validi per i colori RGB standard sono compresi tra zero (0) e 16.777.215 (&H00FFFFFF).</span><span class="sxs-lookup"><span data-stu-id="e93ae-104">The valid range for an ordinary RGB color is zero (0) to 16,777,215 (&H00FFFFFF).</span></span> <span data-ttu-id="e93ae-105">Il primo byte di un numero in questo intervallo è sempre uguale a 0. I 3 byte successivi, dal meno significativo al più significativo, determinano rispettivamente le quantità di rosso, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="e93ae-105">The high byte of a number in this range always equals 0; the lower 3 bytes, from least to most significant byte, determine the amount of red, green, and blue, respectively.</span></span> <span data-ttu-id="e93ae-106">Ognuno dei componenti rosso, verde e blu è rappresentato da un numero compreso tra 0 e 255 (&HFF).</span><span class="sxs-lookup"><span data-stu-id="e93ae-106">The red, green, and blue components are each represented by a number between 0 and 255 (&HFF).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e93ae-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e93ae-107">See Also</span></span>  
 [<span data-ttu-id="e93ae-108">Uso delle proprietà delle celle &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="e93ae-108">Using Cell Properties &#40;MDX&#41;</span></span>](mdx-cell-properties-using-cell-properties.md)  
  
  
