---
title: Usare l'opzione BINARY BASE64 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, BINARY BASE64 option
ms.assetid: 86a7bb85-7f83-412a-b775-d2c379702fe9
author: rothja
ms.author: jroth
ms.openlocfilehash: 090d6a91ee56707a4eb1d545aa5a05bc25999fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722587"
---
# <a name="use-the-binary-base64-option"></a><span data-ttu-id="0373b-102">Utilizzo dell'opzione BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="0373b-102">Use the BINARY BASE64 Option</span></span>
  <span data-ttu-id="0373b-103">Se nella query è specificata l'opzione BINARY BASE64, i dati binari verranno restituiti con la codifica Base64.</span><span class="sxs-lookup"><span data-stu-id="0373b-103">If the BINARY BASE64 option is specified in the query, the binary data is returned in base64 encoding format.</span></span> <span data-ttu-id="0373b-104">Per impostazione predefinita, se l'opzione BINARY BASE64 non viene specificata la modalità AUTO supporta la codifica URL dei dati binari,</span><span class="sxs-lookup"><span data-stu-id="0373b-104">By default, if the BINARY BASE64 option is not specified, AUTO mode supports URL encoding of binary data.</span></span> <span data-ttu-id="0373b-105">ovvero, al posto dei dati binari viene restituito un riferimento a un URL relativo alla radice virtuale del database in cui è stata eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="0373b-105">That is, instead of binary data, a reference to a relative URL to the virtual root of the database where the query was executed is returned.</span></span> <span data-ttu-id="0373b-106">Tale riferimento può essere utilizzato per accedere ai dati binari effettivi nelle operazioni successive, tramite la query SQLXML ISAPI dbobject.</span><span class="sxs-lookup"><span data-stu-id="0373b-106">This reference can be used to access the actual binary data in subsequent operations by using the SQLXML ISAPI dbobject query.</span></span> <span data-ttu-id="0373b-107">La query deve restituire una quantità di informazioni sufficiente per l'identificazione dell'immagine, ad esempio le colonne chiave primarie.</span><span class="sxs-lookup"><span data-stu-id="0373b-107">The query must provide enough information, such as primary key columns, to identify the image.</span></span>  
  
 <span data-ttu-id="0373b-108">Quando si specifica una query, se per la colonna di dati binari della vista viene utilizzato un alias, tale alias verrà restituito nella codifica URL dei dati binari.</span><span class="sxs-lookup"><span data-stu-id="0373b-108">In specifying a query, if an alias is used for the binary column of the view, the alias is returned in the URL encoding of the binary data.</span></span> <span data-ttu-id="0373b-109">Nelle operazioni successive l'alias non è importante e non sarà possibile utilizzare la codifica URL per recuperare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="0373b-109">In subsequent operations, the alias is meaningless, and the URL encoding cannot be used to retrieve the image.</span></span> <span data-ttu-id="0373b-110">Non utilizzare pertanto gli alias per l'esecuzione di query su una vista utilizzando la modalità AUTO della clausola FOR XML.</span><span class="sxs-lookup"><span data-stu-id="0373b-110">Therefore, do not use aliases when querying a view using FOR XML AUTO mode.</span></span>  
  
 <span data-ttu-id="0373b-111">In una query SELECT, il cast di una colonna qualsiasi a una colonna BLOB (Binary Large Object) rende tale query un'entità temporanea, ovvero i relativi nomi di tabella e colonna associati verranno persi.</span><span class="sxs-lookup"><span data-stu-id="0373b-111">For example, in a SELECT query, casting any column to a binary large object (BLOB) makes it a temporary entity in that it loses its associated table name and column name.</span></span> <span data-ttu-id="0373b-112">La query in modalità AUTO genererà pertanto un errore in quanto non sarà in grado di determinare la posizione in cui inserire questo valore nella gerarchia XML.</span><span class="sxs-lookup"><span data-stu-id="0373b-112">This causes AUTO mode queries to generate an error, because it does not know where to put this value in the XML hierarchy.</span></span> <span data-ttu-id="0373b-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0373b-113">For example:</span></span>  
  
```  
CREATE TABLE MyTable (Col1 int PRIMARY KEY, Col2 binary)  
INSERT INTO MyTable VALUES (1, 0x7);  
```  
  
 <span data-ttu-id="0373b-114">Questa query genera un errore a causa del cast a un tipo BLOB:</span><span class="sxs-lookup"><span data-stu-id="0373b-114">This query produces an error, because of the casting to a binary large object (BLOB):</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="0373b-115">Per risolvere il problema, è possibile aggiungere l'opzione BINARY BASE64 alla clausola FOR XML.</span><span class="sxs-lookup"><span data-stu-id="0373b-115">The solution is to add the BINARY BASE64 option to the FOR XML clause.</span></span> <span data-ttu-id="0373b-116">Se si rimuove il casting, la query darà i risultati previsti:</span><span class="sxs-lookup"><span data-stu-id="0373b-116">If you remove the casting, the query produces the results as expected:</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO, BINARY BASE64;  
```  
  
 <span data-ttu-id="0373b-117">Risultato:</span><span class="sxs-lookup"><span data-stu-id="0373b-117">This is the result:</span></span>  
  
```  
<MyTable Col1="1" Col2="Bw==" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="0373b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0373b-118">See Also</span></span>  
 [<span data-ttu-id="0373b-119">Usare la modalità AUTO con FOR XML</span><span class="sxs-lookup"><span data-stu-id="0373b-119">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
