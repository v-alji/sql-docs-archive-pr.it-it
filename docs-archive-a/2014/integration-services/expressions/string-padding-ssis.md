---
title: Riempimento di stringhe (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- padding strings [Integration Services]
- expressions [Integration Services], string padding
- string padding
ms.assetid: d3fed73d-e0d4-4c67-9355-fb7083a72dd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3985fd1b2f29260e2313a761797d2528f5d0e328
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716464"
---
# <a name="string-padding-ssis"></a><span data-ttu-id="2e28e-102">Riempimento di stringhe (SSIS)</span><span class="sxs-lookup"><span data-stu-id="2e28e-102">String Padding (SSIS)</span></span>
  <span data-ttu-id="2e28e-103">L'analizzatore di espressioni non verifica se una stringa contiene spazi iniziali e finali, né applica riempimenti alle stringhe in modo che abbiano la stessa lunghezza, prima di confrontarle.</span><span class="sxs-lookup"><span data-stu-id="2e28e-103">The expression evaluator does not check if a string contains leading and trailing spaces, and it does not pad strings to make them the same length before it compares them.</span></span> <span data-ttu-id="2e28e-104">Nelle espressioni che richiedono il riempimento delle stringhe è possibile utilizzare l'operatore + per concatenare valori di colonna e stringhe vuote.</span><span class="sxs-lookup"><span data-stu-id="2e28e-104">If expressions requires string padding, you can use the + operator to concatenate column values and blank strings.</span></span> <span data-ttu-id="2e28e-105">Per altre informazioni, vedere [+ &#40;concatenazione&#41; &#40;espressione SSIS&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2e28e-105">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="2e28e-106">Se invece è necessario rimuovere spazi, l'analizzatore di espressioni fornisce le funzioni LTRIM, RTRIM e TRIM, che consentono di rimuovere gli spazi iniziali, gli spazi finali o entrambi.</span><span class="sxs-lookup"><span data-stu-id="2e28e-106">On the other hand, if you want to remove spaces, the expression evaluator provides the LTRIM, RTRIM, and TRIM functions, which remove leading or trailing spaces, or both.</span></span> <span data-ttu-id="2e28e-107">Per altre informazioni, vedere [LTRIM &#40;espressione SSIS&#41;](trim-ssis-expression.md), [RTRIM &#40;espressione SSIS&#41;](rtrim-ssis-expression.md) e [TRIM &#40;espressione SSIS&#41;](trim-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2e28e-107">For more information, see [LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md), [RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md), and [TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e28e-108">La funzione LEN include nel conteggio anche gli spazi vuoti iniziali e finali.</span><span class="sxs-lookup"><span data-stu-id="2e28e-108">The LEN function includes leading and trailing blanks in its count.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="2e28e-109">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="2e28e-109">Related Content</span></span>  
 <span data-ttu-id="2e28e-110">Articolo tecnico relativo al [foglio d'aiuto per le espressioni SSIS](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
)sul sito Web pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="2e28e-110">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), on pragmaticworks.com</span></span>  
  
  
