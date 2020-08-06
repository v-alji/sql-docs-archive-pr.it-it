---
title: Nomi di colonna con il percorso specificato come data() | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: 0b738e44-6108-4417-a9a4-abeb7680d899
author: rothja
ms.author: jroth
ms.openlocfilehash: 61aa7f85c7ee2358ddcf99f81c87c1295fac8fb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623942"
---
# <a name="column-names-with-the-path-specified-as-data"></a><span data-ttu-id="73851-102">Nomi di colonna con il percorso specificato come dati()</span><span class="sxs-lookup"><span data-stu-id="73851-102">Column Names with the Path Specified as data()</span></span>
  <span data-ttu-id="73851-103">Se il percorso specificato come nome di colonna è "data()", il valore viene gestito nel codice XML generato come valore atomico.</span><span class="sxs-lookup"><span data-stu-id="73851-103">If the path specified as column name is "data()", the value is treated as an atomic value in the generated XML.</span></span> <span data-ttu-id="73851-104">Se anche l'elemento successivo nella serializzazione è un valore atomico, al codice XML viene aggiunto uno spazio.</span><span class="sxs-lookup"><span data-stu-id="73851-104">A space character is added to the XML if the next item in the serialization is also an atomic value.</span></span> <span data-ttu-id="73851-105">Ciò risulta utile quando si creano valori di elementi e di attributi di tipo elenco.</span><span class="sxs-lookup"><span data-stu-id="73851-105">This is useful when you are creating list typed element and attribute values.</span></span> <span data-ttu-id="73851-106">La query seguente recupera l'ID del modello di prodotto e l'elenco dei prodotti di quel modello.</span><span class="sxs-lookup"><span data-stu-id="73851-106">The following query retrieves the product model ID, name, and list of products in that product model.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID       AS "@ProductModelID",  
       Name                 AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
      FOR XML PATH (''))    AS "@ProductIDs"  
FROM  Production.ProductModel  
WHERE ProductModelID= 7   
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="73851-107">L'istruzione SELECT nidificata recupera un elenco di ID di prodotti</span><span class="sxs-lookup"><span data-stu-id="73851-107">The nested SELECT retrieves a list of product IDs.</span></span> <span data-ttu-id="73851-108">e specifica "data()" come nome di colonna per gli ID di prodotto.</span><span class="sxs-lookup"><span data-stu-id="73851-108">It specifies "data()" as the column name for product IDs.</span></span> <span data-ttu-id="73851-109">Poiché la modalità PATH specifica una stringa vuota per il nome dell'elemento riga, non viene generato alcun elemento riga.</span><span class="sxs-lookup"><span data-stu-id="73851-109">Because PATH mode specifies an empty string for the row element name, there is no row element generated.</span></span> <span data-ttu-id="73851-110">I valori vengono invece restituiti come assegnati a un attributo ProductIDs dell'elemento riga <`ProductModelData`> dell'istruzione SELECT padre.</span><span class="sxs-lookup"><span data-stu-id="73851-110">Instead, the values are returned as assigned to a ProductIDs attribute of the <`ProductModelData`> row element of the parent SELECT.</span></span> <span data-ttu-id="73851-111">Risultato:</span><span class="sxs-lookup"><span data-stu-id="73851-111">This is the result:</span></span>  
  
 `<ProductModelData ProductModelID="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 888 889 890 891 892 893" />`  
  
## <a name="see-also"></a><span data-ttu-id="73851-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73851-112">See Also</span></span>  
 [<span data-ttu-id="73851-113">Utilizzare la modalità PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="73851-113">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
