---
title: Colonne senza nome | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns without
ms.assetid: 440de44e-3a56-4531-b4e4-1533ca933cac
author: rothja
ms.author: jroth
ms.openlocfilehash: 43d1cbce816e4666e6dab52fdffe5850e65740e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713939"
---
# <a name="columns-without-a-name"></a><span data-ttu-id="d343c-102">Colonne senza nome</span><span class="sxs-lookup"><span data-stu-id="d343c-102">Columns without a Name</span></span>
  <span data-ttu-id="d343c-103">Qualsiasi colonna priva di nome verrà resa inline.</span><span class="sxs-lookup"><span data-stu-id="d343c-103">Any column without a name will be inlined.</span></span> <span data-ttu-id="d343c-104">Le colonne calcolate o le query scalari nidificate, ad esempio, che non specificano un alias di colonna genereranno colonne senza nome.</span><span class="sxs-lookup"><span data-stu-id="d343c-104">For example, computed columns or nested scalar queries that do not specify column alias will generate columns without any name.</span></span> <span data-ttu-id="d343c-105">Se la colonna è di tipo `xml`, viene inserito il contenuto dell'istanza di quel tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d343c-105">If the column is of `xml` type, the content of that data type instance is inserted.</span></span> <span data-ttu-id="d343c-106">In caso contrario, il contenuto della colonna viene inserito come nodo di testo.</span><span class="sxs-lookup"><span data-stu-id="d343c-106">Otherwise, the column content is inserted as a text node.</span></span>  
  
```  
SELECT 2+2  
FOR XML PATH  
```  
  
 <span data-ttu-id="d343c-107">Produrre questo codice XML.</span><span class="sxs-lookup"><span data-stu-id="d343c-107">Produce this XML.</span></span> <span data-ttu-id="d343c-108">Per impostazione predefinita, per ogni riga del set di righe viene generato un elemento <`row`> nel codice XML risultante,</span><span class="sxs-lookup"><span data-stu-id="d343c-108">By default, for each row in the rowset, a <`row`> element is generated in the resulting XML.</span></span> <span data-ttu-id="d343c-109">come avviene in modalità RAW.</span><span class="sxs-lookup"><span data-stu-id="d343c-109">This is the same as RAW mode.</span></span>  
  
 `<row>4</row>`  
  
 <span data-ttu-id="d343c-110">La query seguente restituisce un set di righe a tre colonne.</span><span class="sxs-lookup"><span data-stu-id="d343c-110">The following query returns a three-column rowset.</span></span> <span data-ttu-id="d343c-111">La terza colonna priva di nome contiene dati XML.</span><span class="sxs-lookup"><span data-stu-id="d343c-111">The third column without a name has XML data.</span></span> <span data-ttu-id="d343c-112">La modalità PATH inserisce un'istanza del tipo XML.</span><span class="sxs-lookup"><span data-stu-id="d343c-112">The PATH mode inserts an instance of the xml type.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ;  
GO  
```  
  
 <span data-ttu-id="d343c-113">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="d343c-113">This is the partial result:</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location ...LocationID="10" ...></MI:Location>`  
  
 `<MI:Location ...LocationID="20" ...></MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="d343c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d343c-114">See Also</span></span>  
 [<span data-ttu-id="d343c-115">Utilizzare la modalità PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="d343c-115">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
