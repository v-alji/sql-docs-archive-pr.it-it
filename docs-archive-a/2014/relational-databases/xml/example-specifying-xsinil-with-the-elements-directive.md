---
title: 'Esempio: specifica di XSINIL con la direttiva ELEMENTS | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, specifying XSINIL example
ms.assetid: 07c873ff-1f9d-480e-8536-862c39eb8249
author: rothja
ms.author: jroth
ms.openlocfilehash: 7817d2c72909ca66fb9fac10f8fcb32a759faf56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711780"
---
# <a name="example-specifying-xsinil-with-the-elements-directive"></a><span data-ttu-id="acff4-102">Esempio: specifica di XSINIL con la direttiva ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="acff4-102">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>
  <span data-ttu-id="acff4-103">Nella query seguente viene specificata la direttiva `ELEMENTS` per generare codice XML incentrato sugli elementi dai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="acff4-103">The following query specifies the `ELEMENTS` directive to generate element-centric XML from the query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acff4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="acff4-104">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductID, Name, Color  
FROM Production.Product  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="acff4-105">Di seguito è riportato il risultato parziale.</span><span class="sxs-lookup"><span data-stu-id="acff4-105">This is the partial result.</span></span>  
  
```  
<row>  
  <ProductID>1</ProductID>  
  <Name>Adjustable Race</Name>  
</row>  
...  
<row>  
  <ProductID>317</ProductID>  
  <Name>LL Crankarm</Name>  
  <Color>Black</Color>  
</row>  
```  
  
 <span data-ttu-id="acff4-106">Nella colonna `Color` sono presenti i valori Null per alcuni prodotti e pertanto nel codice XML risultante non verrà generato l'elemento <`Color`> corrispondente.</span><span class="sxs-lookup"><span data-stu-id="acff4-106">Because the `Color` column has null values for some products, the resulting XML will not generate the corresponding <`Color`> element.</span></span> <span data-ttu-id="acff4-107">Se si aggiunge la direttiva `XSINIL` insieme a `ELEMENTS`, è possibile generare l'elemento <`Color`> anche per i valori Null relativi al colore nel set dei risultati.</span><span class="sxs-lookup"><span data-stu-id="acff4-107">By adding the `XSINIL` directive with `ELEMENTS`, you can generate the <`Color`> element even for NULL color values in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductID, Name, Color  
FROM Production.Product  
FOR XML RAW, ELEMENTS XSINIL ;  
```  
  
 <span data-ttu-id="acff4-108">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="acff4-108">This is the partial result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <ProductID>1</ProductID>  
  <Name>Adjustable Race</Name>  
  <Color xsi:nil="true" />  
</row>  
...  
<row>  
  <ProductID>317</ProductID>  
  <Name>LL Crankarm</Name>  
  <Color>Black</Color>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="acff4-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acff4-109">See Also</span></span>  
 [<span data-ttu-id="acff4-110">Usare la modalità RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="acff4-110">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
