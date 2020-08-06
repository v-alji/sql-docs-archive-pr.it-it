---
title: Creare, modificare o eliminare indici XML selettivi secondari | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 45128105-833b-40a9-9cc9-1ae03ac0b52b
author: rothja
ms.author: jroth
ms.openlocfilehash: e6f7296896b6421db5329565403cdcbaf10b26a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713931"
---
# <a name="create-alter-and-drop-secondary-selective-xml-indexes"></a><span data-ttu-id="47aa3-102">Creare, modificare o eliminare indici XML selettivi secondari</span><span class="sxs-lookup"><span data-stu-id="47aa3-102">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>
  <span data-ttu-id="47aa3-103">Viene descritto come creare un nuovo indice XML selettivo secondario oppure modificarne o eliminarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="47aa3-103">Describes how to create a new secondary selective XML index, or alter or drop an existing secondary selective XML index.</span></span>  
  
##  <a name="creating-a-secondary-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="47aa3-104">Creazione di un indice XML selettivo secondario</span><span class="sxs-lookup"><span data-stu-id="47aa3-104">Creating a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-create-a-secondary-selective-xml-index"></a><span data-ttu-id="47aa3-105">Procedura: Creare un indice XML selettivo secondario</span><span class="sxs-lookup"><span data-stu-id="47aa3-105">How to: Create a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="47aa3-106">**Creare un indice XML selettivo secondario tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="47aa3-106">**Create a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="47aa3-107">Creare un indice XML selettivo secondario chiamando l'istruzione CREATE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="47aa3-107">Create a secondary selective XML index by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="47aa3-108">Per ulteriori informazioni, vedere [CREATE XML INDEX &#40;indici XML selettivi&#41;] (~/t-SQL/Statements/create-XML-index-Selective-XML-Indexes.</span><span class="sxs-lookup"><span data-stu-id="47aa3-108">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="47aa3-109">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="47aa3-109">**Example**</span></span>  
  
 <span data-ttu-id="47aa3-110">Nell'esempio seguente viene creato un indice XML selettivo secondario nel percorso `'pathabc'`.</span><span class="sxs-lookup"><span data-stu-id="47aa3-110">The following example creates a secondary selective XML index on the path `'pathabc'`.</span></span> <span data-ttu-id="47aa3-111">Il percorso dell'indice viene identificato dal nome fornito al momento della creazione con l'istruzione CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="47aa3-111">The path to index is identified by the name that was given to it when it was created with the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="47aa3-112">Per altre informazioni, vedere [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="47aa3-112">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
```sql  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="altering-a-secondary-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="47aa3-113">Modifica di un indice XML selettivo secondario</span><span class="sxs-lookup"><span data-stu-id="47aa3-113">Altering a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="47aa3-114">L'istruzione ALTER non è supportata per gli indici XML selettivi secondari.</span><span class="sxs-lookup"><span data-stu-id="47aa3-114">The ALTER statement is not supported for secondary selective XML indexes.</span></span> <span data-ttu-id="47aa3-115">Per modificare un indice XML selettivo secondario, eliminare l'indice esistente e ricrearlo.</span><span class="sxs-lookup"><span data-stu-id="47aa3-115">To change a secondary selective XML index, drop the existing index and recreate it.</span></span>  
  
### <a name="how-to-alter-a-secondary-selective-xml-index"></a><span data-ttu-id="47aa3-116">Procedura: Modificare un indice XML selettivo secondario</span><span class="sxs-lookup"><span data-stu-id="47aa3-116">How to: Alter a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="47aa3-117">**Modificare un indice XML selettivo secondario tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="47aa3-117">**Alter a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 1.  <span data-ttu-id="47aa3-118">Eliminare l'indice XML selettivo secondario esistente chiamando l'istruzione DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="47aa3-118">Drop the existing secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="47aa3-119">Per altre informazioni, vedere [DROP INDEX &#40;indici XML selettivi&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="47aa3-119">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
2.  <span data-ttu-id="47aa3-120">Ricreare l'indice con le opzioni desiderate chiamando l'istruzione CREATE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="47aa3-120">Recreate the index with the desired options by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="47aa3-121">Per ulteriori informazioni, vedere [CREATE XML INDEX &#40;indici XML selettivi&#41;] (~/t-SQL/Statements/create-XML-index-Selective-XML-Indexes.</span><span class="sxs-lookup"><span data-stu-id="47aa3-121">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="47aa3-122">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="47aa3-122">**Example**</span></span>  
  
 <span data-ttu-id="47aa3-123">Nell'esempio seguente viene modificato un indice XML selettivo secondario eliminandolo e ricreandolo.</span><span class="sxs-lookup"><span data-stu-id="47aa3-123">The following example changes a secondary selective XML index by dropping it and recreating it.</span></span>  
  
```sql  
DROP INDEX filt_sxi_index_c  
  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="dropping-a-secondary-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="47aa3-124">Eliminazione di un indice XML selettivo secondario</span><span class="sxs-lookup"><span data-stu-id="47aa3-124">Dropping a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-secondary-selective-xml-index"></a><span data-ttu-id="47aa3-125">Procedura: Eliminare un indice XML selettivo secondario</span><span class="sxs-lookup"><span data-stu-id="47aa3-125">How to: Drop a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="47aa3-126">**Eliminare un indice XML selettivo secondario tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="47aa3-126">**Drop a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="47aa3-127">Eliminare un indice XML selettivo secondario chiamando l'istruzione DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="47aa3-127">Drop a secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="47aa3-128">Per altre informazioni, vedere [DROP INDEX &#40;indici XML selettivi&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="47aa3-128">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="47aa3-129">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="47aa3-129">**Example**</span></span>  
  
 <span data-ttu-id="47aa3-130">Nell'esempio seguente viene illustrata un'istruzione DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="47aa3-130">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX ssxi_index  
ON tbl  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="47aa3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47aa3-131">See Also</span></span>  
 [<span data-ttu-id="47aa3-132">Indici XML selettivi &#40;SXI&#41;</span><span class="sxs-lookup"><span data-stu-id="47aa3-132">Selective XML Indexes &#40;SXI&#41;</span></span>](selective-xml-indexes-sxi.md)  
  
  
