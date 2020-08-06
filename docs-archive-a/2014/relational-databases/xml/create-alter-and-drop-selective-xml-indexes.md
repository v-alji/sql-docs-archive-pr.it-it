---
title: Creare, modificare o eliminare indici XML selettivi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: c398f396-f630-4a2d-a264-f243c5346de1
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4123a46cc13359c936e6f9cfc0db3dcfdaa175
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713928"
---
# <a name="create-alter-and-drop-selective-xml-indexes"></a><span data-ttu-id="3f0bf-102">Creare, modificare o eliminare indici XML selettivi</span><span class="sxs-lookup"><span data-stu-id="3f0bf-102">Create, Alter, and Drop Selective XML Indexes</span></span>
  <span data-ttu-id="3f0bf-103">Viene descritto come creare un nuovo indice XML selettivo oppure modificarne o eliminarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="3f0bf-103">Describes how to create a new selective XML index, or alter or drop an existing selective XML index.</span></span>  
  
 <span data-ttu-id="3f0bf-104">Per altre informazioni sugli indici XML selettivi, vedere [Indici XML selettivi &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="3f0bf-104">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="creating-a-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="3f0bf-105">Creazione di un indice XML selettivo</span><span class="sxs-lookup"><span data-stu-id="3f0bf-105">Creating a Selective XML Index</span></span>  
  
### <a name="how-to-create-a-selective-xml-index"></a><span data-ttu-id="3f0bf-106">Procedura: Creare un indice XML selettivo</span><span class="sxs-lookup"><span data-stu-id="3f0bf-106">How to: Create a Selective XML Index</span></span>  
 <span data-ttu-id="3f0bf-107">**Creare un indice XML selettivo tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="3f0bf-107">**Create a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="3f0bf-108">Creare un indice XML selettivo chiamando l'istruzione CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="3f0bf-108">Create a selective XML index by calling the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="3f0bf-109">Per altre informazioni, vedere [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3f0bf-109">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
 <span data-ttu-id="3f0bf-110">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="3f0bf-110">**Example**</span></span>  
  
 <span data-ttu-id="3f0bf-111">Nell'esempio seguente viene illustrata la sintassi per la creazione di un indice XML selettivo.</span><span class="sxs-lookup"><span data-stu-id="3f0bf-111">The following example shows the syntax for creating a selective XML index.</span></span> <span data-ttu-id="3f0bf-112">Vengono inoltre mostrate diverse varianti della sintassi per la descrizione dei percorsi che si desidera indicizzare, con hint di ottimizzazione facoltativi.</span><span class="sxs-lookup"><span data-stu-id="3f0bf-112">It also shows several variations of the syntax for describing the paths to be indexed, with optional optimization hints.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX sxi_index  
ON Tbl(xmlcol)  
  
FOR(  
    pathab   = '/a/b' as XQUERY 'node()'  
    pathabc  = '/a/b/c' as XQUERY 'xs:double',   
    pathdtext = '/a/b/d/text()' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
    pathabe = '/a/b/e' as SQL NVARCHAR(100)  
)  
```  
  
  
  
##  <a name="altering-a-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="3f0bf-113">Modifica di un indice XML selettivo</span><span class="sxs-lookup"><span data-stu-id="3f0bf-113">Altering a Selective XML Index</span></span>  
  
### <a name="how-to-alter-a-selective-xml-index"></a><span data-ttu-id="3f0bf-114">Procedura: Modificare un indice XML selettivo</span><span class="sxs-lookup"><span data-stu-id="3f0bf-114">How to: Alter a Selective XML Index</span></span>  
 <span data-ttu-id="3f0bf-115">**Modificare un indice XML selettivo tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="3f0bf-115">**Alter a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="3f0bf-116">Modificare un indice XML selettivo esistente chiamando l'istruzione ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="3f0bf-116">Alter an existing selective XML index by calling the ALTER INDEX statement.</span></span> <span data-ttu-id="3f0bf-117">Per altre informazioni, vedere [ALTER INDEX &#40;indici XML selettivi&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="3f0bf-117">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="3f0bf-118">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="3f0bf-118">**Example**</span></span>  
  
 <span data-ttu-id="3f0bf-119">Nell'esempio seguente viene illustrata un'istruzione ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="3f0bf-119">The following example shows an ALTER INDEX statement.</span></span> <span data-ttu-id="3f0bf-120">Con questa istruzione il percorso `'/a/b/m'` viene aggiunto alla parte XQuery dell'indice e il percorso `'/a/b/e'` viene eliminato dalla parte SQL dell'indice creato nell'esempio nell'argomento [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3f0bf-120">This statement adds the path `'/a/b/m'` to the XQuery part of the index and deletes the path `'/a/b/e'` from the SQL part of the index created in the example in the topic [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span> <span data-ttu-id="3f0bf-121">Il percorso da eliminare viene identificato dal nome fornito al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="3f0bf-121">The path to delete is identified by the name that was given to it when it was created.</span></span>  
  
```sql  
ALTER INDEX sxi_index  
ON Tbl  
FOR   
(  
    ADD pathm = '/a/b/m' as XQUERY 'node()' ,  
    REMOVE pathabe  
)  
```  
  
  
  
##  <a name="dropping-a-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="3f0bf-122">Eliminazione di un indice XML selettivo</span><span class="sxs-lookup"><span data-stu-id="3f0bf-122">Dropping a Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-selective-xml-index"></a><span data-ttu-id="3f0bf-123">Procedura: Eliminare un indice XML selettivo</span><span class="sxs-lookup"><span data-stu-id="3f0bf-123">How to: Drop a Selective XML Index</span></span>  
 <span data-ttu-id="3f0bf-124">**Eliminare un indice XML selettivo tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="3f0bf-124">**Drop a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="3f0bf-125">Eliminare un indice XML selettivo chiamando l'istruzione DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="3f0bf-125">Drop a selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="3f0bf-126">Per altre informazioni, vedere [DROP INDEX &#40;indici XML selettivi&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span><span class="sxs-lookup"><span data-stu-id="3f0bf-126">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span></span>  
  
 <span data-ttu-id="3f0bf-127">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="3f0bf-127">**Example**</span></span>  
  
 <span data-ttu-id="3f0bf-128">Nell'esempio seguente viene illustrata un'istruzione DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="3f0bf-128">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX sxi_index ON tbl  
```  
  
 
  
  
