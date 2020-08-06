---
title: Eliminare indici XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- dropping indexes
- XML indexes [SQL Server], dropping
ms.assetid: 7591ebea-34af-4925-8553-b2adb5b487c2
author: rothja
ms.author: jroth
ms.openlocfilehash: b7d4621cf2182b4587b12665a1cfe10ddbe0db3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623938"
---
# <a name="drop-xml-indexes"></a><span data-ttu-id="a4052-102">Eliminazione di indici XML</span><span class="sxs-lookup"><span data-stu-id="a4052-102">Drop XML Indexes</span></span>
  <span data-ttu-id="a4052-103">Per eliminare indici XML e non XML primari o secondari esistenti, è possibile usare l'istruzione [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4052-103">The [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be used to drop existing primary or secondary XML and non-XML indexes.</span></span> <span data-ttu-id="a4052-104">Tuttavia, nessuna opzione dell'istruzione DROP INDEX si applica agli indici XML.</span><span class="sxs-lookup"><span data-stu-id="a4052-104">However, no options of DROP INDEX apply to XML indexes.</span></span> <span data-ttu-id="a4052-105">Se si elimina l'indice XML primario, vengono eliminati anche gli indici secondari presenti.</span><span class="sxs-lookup"><span data-stu-id="a4052-105">If you drop the primary XML index, any secondary indexes that are present are also deleted.</span></span>  
  
 <span data-ttu-id="a4052-106">La sintassi di DROP con *TableName.IndexName* è obsoleta e non è supportata per gli indici XML.</span><span class="sxs-lookup"><span data-stu-id="a4052-106">The DROP syntax with *TableName.IndexName* is being phased out and is not supported for XML indexes.</span></span>  
  
## <a name="example-creating-and-dropping-a-primary-xml-index"></a><span data-ttu-id="a4052-107">Esempio: Creazione ed eliminazione di un indice XML primario</span><span class="sxs-lookup"><span data-stu-id="a4052-107">Example: Creating and Dropping a Primary XML Index</span></span>  
 <span data-ttu-id="a4052-108">Nell'esempio seguente viene creato un indice XML in una colonna di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="a4052-108">In the following example, an XML index is created on an `xml` type column.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create Primary XML index   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Verify the index creation.   
-- Note index type is 3 for xml indexes.  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'   
-- Drop the index.  
DROP INDEX PIdx_T_XmlCol ON T  
```  
  
 <span data-ttu-id="a4052-109">Quando si elimina una tabella, vengono eliminati automaticamente anche tutti i relativi indici XML.</span><span class="sxs-lookup"><span data-stu-id="a4052-109">When a table is dropped, all the XML indexes on it are also automatically dropped.</span></span> <span data-ttu-id="a4052-110">Non è tuttavia possibile eliminare una colonna XML da una tabella se in tale colonna è incluso un indice XML.</span><span class="sxs-lookup"><span data-stu-id="a4052-110">However, an XML column cannot be dropped from a table if an XML index exists on the column.</span></span>  
  
 <span data-ttu-id="a4052-111">Nell'esempio seguente viene creato un indice XML in una colonna di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="a4052-111">In the following example, an XML index is created on an `xml` type column.</span></span> <span data-ttu-id="a4052-112">Per altre informazioni, vedere [Confrontare dati XML tipizzati con dati XML non tipizzati](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a4052-112">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
```  
CREATE TABLE TestTable(  
 Col1 int primary key,   
 Col2 xml (Production.ProductDescriptionSchemaCollection))   
GO  
```  
  
 <span data-ttu-id="a4052-113">A questo punto, è possibile creare un indice XML primario in `Co12`.</span><span class="sxs-lookup"><span data-stu-id="a4052-113">Now, you can create a primary XML index on `Co12`.</span></span>  
  
```  
CREATE PRIMARY XML INDEX PIdx_TestTable_Col2   
ON TestTable(Col2)  
GO  
```  
  
## <a name="example-creating-an-xml-index-by-using-the-drop_existing-index-option"></a><span data-ttu-id="a4052-114">Esempio: Creazione di un indice XML tramite l'opzione DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="a4052-114">Example: Creating an XML Index by Using the DROP_EXISTING Index Option</span></span>  
 <span data-ttu-id="a4052-115">Nell'esempio seguente un indice XML viene creato in una colonna (`XmlColx`).</span><span class="sxs-lookup"><span data-stu-id="a4052-115">In the following example, an XML index is created on a column (`XmlColx`).</span></span> <span data-ttu-id="a4052-116">Successivamente, viene creato un altro indice XML con lo stesso nome in una colonna diversa, (`XmlColy`).</span><span class="sxs-lookup"><span data-stu-id="a4052-116">Then, another XML index with the same name is created on a different column, (`XmlColy`).</span></span> <span data-ttu-id="a4052-117">Poiché viene specificata l'opzione `DROP_EXISTING` , viene eliminato l'indice XML esistente in (`XmlColx)` ) e creato un nuovo indice XML in (`XmlColy`).</span><span class="sxs-lookup"><span data-stu-id="a4052-117">Because the `DROP_EXISTING` option is specified, the existing XML index on (`XmlColx)` is dropped and a new XML index on (`XmlColy`) is created.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T(Col1 int primary key, XmlColx xml, XmlColy xml)  
GO  
-- Create XML index on XmlColx.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColx)  
GO  
-- Create same name XML index on XmlColy.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColy)   
WITH (DROP_EXISTING = ON)  
-- Verify the index is created on XmlColy.d.  
SELECT sc.name   
FROM   sys.xml_indexes si inner join sys.index_columns sic   
ON     sic.object_id=si.object_id and sic.index_id=si.index_id  
INNER  join sys.columns sc on sc.object_id=sic.object_id   
AND    sc.column_id=sic.column_id  
WHERE  si.name='PIdx_T_XmlCol'   
AND    si.object_id=object_id('T')  
```  
  
 <span data-ttu-id="a4052-118">Questa query restituisce il nome della colonna in cui viene creato l'indice XML specificato.</span><span class="sxs-lookup"><span data-stu-id="a4052-118">This query returns the column name on which the specified XML index is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4052-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4052-119">See Also</span></span>  
 [<span data-ttu-id="a4052-120">Indici XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4052-120">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
