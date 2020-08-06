---
title: Modificare indici XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML indexes [SQL Server], modifying
- modifying indexes
ms.assetid: 24d50fe1-c6ec-49e6-91a3-9791851ba53d
author: rothja
ms.author: jroth
ms.openlocfilehash: c5c67470fc9aaaeefe49e5ccb1a8602e082c4054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712835"
---
# <a name="modify-xml-indexes"></a><span data-ttu-id="d35ec-102">Modifica di indici XML</span><span class="sxs-lookup"><span data-stu-id="d35ec-102">Modify XML Indexes</span></span>
  <span data-ttu-id="d35ec-103">È possibile usare l’istruzione DDL di [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] per modificare gli indici XML e non XML esistenti.</span><span class="sxs-lookup"><span data-stu-id="d35ec-103">The [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement can be used to modify existing XML and non-XML indexes.</span></span> <span data-ttu-id="d35ec-104">Per gli indici XML, tuttavia, non sono disponibili tutte le opzioni ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="d35ec-104">However, not all the ALTER INDEX options are available to XML indexes.</span></span> <span data-ttu-id="d35ec-105">Per la modifica degli indici XML non sono valide le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d35ec-105">The following options are not valid when modifying XML indexes:</span></span>  
  
-   <span data-ttu-id="d35ec-106">Per gli indici XML non è valida l'opzione di ricompilazione e impostazione IGNORE_DUP_KEY.</span><span class="sxs-lookup"><span data-stu-id="d35ec-106">The rebuild and set option IGNORE_DUP_KEY is not valid for XML indexes.</span></span> <span data-ttu-id="d35ec-107">Per gli indici XML secondari è necessario impostare l'opzione di ricompilazione ONLINE su OFF.</span><span class="sxs-lookup"><span data-stu-id="d35ec-107">The rebuild option ONLINE must be set to OFF for secondary XML indexes.</span></span> <span data-ttu-id="d35ec-108">Nell'istruzione ALTER INDEX non è consentita l'opzione DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="d35ec-108">The option DROP_EXISTING is not permitted in the ALTER INDEX statement.</span></span>  
  
-   <span data-ttu-id="d35ec-109">Le modifiche al vincolo di chiave primaria nella tabella utente non vengono automaticamente propagate agli indici XML.</span><span class="sxs-lookup"><span data-stu-id="d35ec-109">The modifications of the primary key constraint in the user table are not automatically propagated to XML indexes.</span></span> <span data-ttu-id="d35ec-110">L'utente deve prima eliminare gli indici XML e quindi ricrearli.</span><span class="sxs-lookup"><span data-stu-id="d35ec-110">The user must drop the XML indexes first and then re-create them.</span></span>  
  
-   <span data-ttu-id="d35ec-111">Se viene specificata l'opzione ALTER INDEX ALL, questa viene applicata agli indici sia XML che non XML.</span><span class="sxs-lookup"><span data-stu-id="d35ec-111">If ALTER INDEX ALL is specified, it applies to both non-XML and XML indexes.</span></span> <span data-ttu-id="d35ec-112">È possibile che vengano specificate opzioni di indicizzazione che non sono valide per entrambi i tipi di indici.</span><span class="sxs-lookup"><span data-stu-id="d35ec-112">Indexing options may be specified that are not valid for both types of indexes.</span></span> <span data-ttu-id="d35ec-113">In tal caso, l'intera istruzione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d35ec-113">In this case, the whole statement fails.</span></span>  
  
## <a name="example-modifying-an-xml-index"></a><span data-ttu-id="d35ec-114">Esempio: Modifica di un indice XML</span><span class="sxs-lookup"><span data-stu-id="d35ec-114">Example: Modifying an XML Index</span></span>  
 <span data-ttu-id="d35ec-115">Nell'esempio seguente viene creato, e quindi modificato, un indice XML impostando l'opzione `ALLOW_ROW_LOCKS` su `OFF`.</span><span class="sxs-lookup"><span data-stu-id="d35ec-115">In the following example, an XML index is created and then modified by setting the option `ALLOW_ROW_LOCKS` to `OFF`.</span></span> <span data-ttu-id="d35ec-116">Quando l'opzione `ALLOW_ROW_LOCKS` è impostata su `OFF`, le righe non sono bloccate ed è possibile ottenere l'accesso agli indici specificati tramite blocchi a livello di pagina e di tabella.</span><span class="sxs-lookup"><span data-stu-id="d35ec-116">When `ALLOW_ROW_LOCKS` is `OFF`, rows are not locked and access to the specified indexes is obtained by using page-and table-level locks.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create primary XML index.   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
  
-- Modify and set an index option.  
ALTER INDEX PIdx_T_XmlCol on T   
SET (ALLOW_ROW_LOCKS = OFF)  
```  
  
## <a name="example-disabling-and-enabling-an-xml-index"></a><span data-ttu-id="d35ec-117">Esempio: Disabilitazione e abilitazione di un indice XML</span><span class="sxs-lookup"><span data-stu-id="d35ec-117">Example: Disabling and Enabling an XML Index</span></span>  
 <span data-ttu-id="d35ec-118">Per impostazione predefinita, viene attivato un indice XML.</span><span class="sxs-lookup"><span data-stu-id="d35ec-118">By default, an XML index is enabled.</span></span> <span data-ttu-id="d35ec-119">Se si disabilita un indice XML, per le query in esecuzione sulla colonna XML non viene utilizzato l'indice XML.</span><span class="sxs-lookup"><span data-stu-id="d35ec-119">If an XML index is disabled, the queries running against the XML column do not use the XML index.</span></span> <span data-ttu-id="d35ec-120">Per abilitare un indice XML, utilizzare `ALTER INDEX` con l'opzione `REBUILD` .</span><span class="sxs-lookup"><span data-stu-id="d35ec-120">To enable an XML index, use `ALTER INDEX` with the `REBUILD` option.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol ON T(XmlCol)  
GO  
ALTER INDEX PIdx_T_XmlCol on T DISABLE  
Go  
-- Verify index is disabled.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
-- Rebuild the index.  
ALTER INDEX PIdx_T_XmlCol on T REBUILD  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="d35ec-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d35ec-121">See Also</span></span>  
 [<span data-ttu-id="d35ec-122">Indici XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d35ec-122">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
