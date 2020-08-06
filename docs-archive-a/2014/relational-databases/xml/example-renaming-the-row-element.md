---
title: "Esempio: Ridenominazione dell'elemento &lt;row&gt; | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, renaming <row> example
ms.assetid: b042292a-0b6e-40a3-b254-71c06e626706
author: rothja
ms.author: jroth
ms.openlocfilehash: 39375fa125f451f21d936b3a6897b93928fa2f02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623933"
---
# <a name="example-renaming-the-ltrowgt-element"></a><span data-ttu-id="54920-102">Esempio: Ridenominazione dell'elemento &lt;row&gt;</span><span class="sxs-lookup"><span data-stu-id="54920-102">Example: Renaming the &lt;row&gt; Element</span></span>
  <span data-ttu-id="54920-103">Nella modalità RAW viene creato un elemento `<row>`per ogni riga del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="54920-103">For each row in the result set, the RAW mode generates an element `<row>`.</span></span> <span data-ttu-id="54920-104">È possibile specificare un nome diverso per l'elemento impostando un argomento facoltativo per la modalità RAW, come illustrato nella query seguente.</span><span class="sxs-lookup"><span data-stu-id="54920-104">You can optionally specify another name for this element by specifying an optional argument to the RAW mode, as shown in this query.</span></span> <span data-ttu-id="54920-105">La query restituisce un elemento <`ProductModel`> per ogni riga del set di righe.</span><span class="sxs-lookup"><span data-stu-id="54920-105">The query returns a <`ProductModel`> element for each row in the rowset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54920-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="54920-106">Example</span></span>  
  
```  
SELECT ProductModelID, Name   
FROM Production.ProductModel  
WHERE ProductModelID=122  
FOR XML RAW ('ProductModel'), ELEMENTS  
GO  
```  
  
 <span data-ttu-id="54920-107">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="54920-107">This is the result.</span></span> <span data-ttu-id="54920-108">Nella query viene aggiunta la direttiva `ELEMENTS` e pertanto il risultato è incentrato sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="54920-108">Because the `ELEMENTS` directive is added in the query, the result is element-centric.</span></span>  
  
```  
<ProductModel>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</ProductModel>   
```  
  
## <a name="see-also"></a><span data-ttu-id="54920-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54920-109">See Also</span></span>  
 [<span data-ttu-id="54920-110">Usare la modalità RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="54920-110">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
