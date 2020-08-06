---
title: 'Esempio: Recupero delle informazioni relative al modello del prodotto in formato XML | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, retrieving XML information example
ms.assetid: 3828b4ca-3ab2-444f-9c58-8be6e7f064a6
author: rothja
ms.author: jroth
ms.openlocfilehash: d580f53c4b5185a8b1b1467c75a08fc6929bdcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629280"
---
# <a name="example-retrieving-product-model-information-as-xml"></a><span data-ttu-id="6356f-102">Esempio: Recupero delle informazioni relative al modello del prodotto in formato XML</span><span class="sxs-lookup"><span data-stu-id="6356f-102">Example: Retrieving Product Model Information as XML</span></span>
  <span data-ttu-id="6356f-103">La query seguente restituisce le informazioni relative al modello del prodotto.</span><span class="sxs-lookup"><span data-stu-id="6356f-103">The following query returns product model information.</span></span> <span data-ttu-id="6356f-104">`RAW` la modalità è specificata nella clausola `FOR XML` .</span><span class="sxs-lookup"><span data-stu-id="6356f-104">`RAW` mode is specified in the `FOR XML` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6356f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6356f-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW;  
GO  
```  
  
 <span data-ttu-id="6356f-106">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="6356f-106">This is the partial result:</span></span>  
  
 `<row ProductModelID="122" Name="All-Purpose Bike Stand" />`  
  
 `<row ProductModelID="119" Name="Bike Wash" />`  
  
 <span data-ttu-id="6356f-107">Per recuperare il codice XML incentrato sugli elementi, è necessario specificare la direttiva `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="6356f-107">You can retrieve element-centric XML by specifying the `ELEMENTS` directive.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="6356f-108">Risultato:</span><span class="sxs-lookup"><span data-stu-id="6356f-108">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</row>  
<row>  
  <ProductModelID>119</ProductModelID>  
  <Name>Bike Wash</Name>  
</row>  
```  
  
 <span data-ttu-id="6356f-109">È possibile specificare facoltativamente la direttiva `TYPE` per recuperare risultati di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="6356f-109">You can optionally specify the `TYPE` directive to retrieve the results as `xml` type.</span></span> <span data-ttu-id="6356f-110">La direttiva `TYPE` non modifica il contenuto dei risultati.</span><span class="sxs-lookup"><span data-stu-id="6356f-110">The `TYPE` directive does not change the content of the results.</span></span> <span data-ttu-id="6356f-111">Solo il tipo di dati dei risultati viene modificato.</span><span class="sxs-lookup"><span data-stu-id="6356f-111">Only the data type of the results is affected.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, TYPE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6356f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6356f-112">See Also</span></span>  
 [<span data-ttu-id="6356f-113">Usare la modalità RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="6356f-113">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
