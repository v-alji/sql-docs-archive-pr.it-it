---
title: Generare elementi per valori NULL tramite il parametro XSINIL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, null values
- null values [SQL Server], XML
- ELEMENTS directive
- XSINIL parameter
ms.assetid: 2dbc4e48-1cae-4d83-b371-3265da9687cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 602de12b5aa9be8997fbd49a2f23e0b73444aac0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726743"
---
# <a name="generate-elements-for-null-values-with-the-xsinil-parameter"></a><span data-ttu-id="c7db0-102">Generazione di elementi per valori NULL tramite il parametro XSINIL</span><span class="sxs-lookup"><span data-stu-id="c7db0-102">Generate Elements for NULL Values with the XSINIL Parameter</span></span>
  <span data-ttu-id="c7db0-103">La direttiva **ELEMENTS** costruisce codice XML nel quale viene eseguito il mapping di ogni valore di colonna a un elemento.</span><span class="sxs-lookup"><span data-stu-id="c7db0-103">The **ELEMENTS** directive constructs XML in which each column value maps to an element in the XML.</span></span> <span data-ttu-id="c7db0-104">Se il valore di colonna è NULL, non viene aggiunto alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="c7db0-104">If the column value is NULL, no element is added.</span></span> <span data-ttu-id="c7db0-105">Se si specifica il parametro facoltativo **XSINIL** nella direttiva ELEMENTS, è anche possibile richiedere che venga creato un elemento per il valore NULL.</span><span class="sxs-lookup"><span data-stu-id="c7db0-105">By specifying the optional **XSINIL** parameter on the ELEMENTS directive, you can request that an element also be created for the NULL value.</span></span> <span data-ttu-id="c7db0-106">In questo caso, per ogni valore di colonna NULL viene restituito un elemento con l'attributo **xsi:nil** impostato su TRUE.</span><span class="sxs-lookup"><span data-stu-id="c7db0-106">In this case, an element that has the **xsi:nil** attribute set to TRUE is returned for each NULL column value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7db0-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7db0-107">See Also</span></span>  
 [<span data-ttu-id="c7db0-108">Usare la modalità RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="c7db0-108">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
