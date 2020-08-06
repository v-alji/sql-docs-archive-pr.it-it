---
title: 'Esempio: Specifica della direttiva CDATA | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- CDATA directive
ms.assetid: 949071e6-787f-480d-bb86-3ac16a027af1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9b4f949ae1e9f309a13906efe44b329db2e47ec1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711799"
---
# <a name="example-specifying-the-cdata-directive"></a><span data-ttu-id="6cb2a-102">Esempio: Specifica della direttiva CDATA</span><span class="sxs-lookup"><span data-stu-id="6cb2a-102">Example: Specifying the CDATA Directive</span></span>
  <span data-ttu-id="6cb2a-103">Se si specifica la direttiva **CDATA**, i dati contenuti non vengono codificati come entità, ma vengono inseriti nella sezione CDATA.</span><span class="sxs-lookup"><span data-stu-id="6cb2a-103">If the directive is set to **CDATA**, the contained data is not entity encoded, but is put in the CDATA section.</span></span> <span data-ttu-id="6cb2a-104">Gli attributi **CDATA** devono essere privi di nome.</span><span class="sxs-lookup"><span data-stu-id="6cb2a-104">The **CDATA** attributes must be nameless.</span></span>  
  
 <span data-ttu-id="6cb2a-105">La query seguente riporta la descrizione di riepilogo del modello di prodotto in una sezione CDATA.</span><span class="sxs-lookup"><span data-stu-id="6cb2a-105">The following query wraps the product model summary description in a CDATA section.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        '<Summary>This is summary description</Summary>'     
            as [ProductModel!1!!CDATA] -- no attribute name so ELEMENT assumed  
FROM    Production.ProductModel  
WHERE   ProductModelID=19  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="6cb2a-106">Risultato:</span><span class="sxs-lookup"><span data-stu-id="6cb2a-106">This is the result:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
   <![CDATA[<Summary>This is summary description</Summary>]]>  
</ProductModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6cb2a-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cb2a-107">See Also</span></span>  
 [<span data-ttu-id="6cb2a-108">Usare la modalità EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="6cb2a-108">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
