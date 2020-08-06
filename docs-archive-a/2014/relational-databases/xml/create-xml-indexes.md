---
title: Creare indici XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- indexes [XML in SQL Server]
- XML indexes [SQL Server], creating
ms.assetid: 6ecac598-355d-4408-baf7-1b2e8d4cf7c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9e7800193222b8c9060fee1b247cc5585654cde4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722603"
---
# <a name="create-xml-indexes"></a><span data-ttu-id="7eb29-102">Creazione di indici XML</span><span class="sxs-lookup"><span data-stu-id="7eb29-102">Create XML Indexes</span></span>
  <span data-ttu-id="7eb29-103">Questo argomento descrive come creare, modificare e utilizzare indici XML primari e secondari.</span><span class="sxs-lookup"><span data-stu-id="7eb29-103">This topic describes how to create primary and secondary XML indexes.</span></span>  
  
## <a name="creating-a-primary-xml-index"></a><span data-ttu-id="7eb29-104">Creazione di un indice XML primario</span><span class="sxs-lookup"><span data-stu-id="7eb29-104">Creating a Primary XML Index</span></span>  
 <span data-ttu-id="7eb29-105">Per creare un indice XML primario, usare l'istruzione DDL [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7eb29-105">To create a primary XML index, use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement.</span></span> <span data-ttu-id="7eb29-106">Negli indici XML non sono supportate tutte le opzioni disponibili per gli indici non XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-106">Not all options available for non-XML indexes are supported on XML indexes.</span></span>  
  
 <span data-ttu-id="7eb29-107">Per la creazione di un indice XML, si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7eb29-107">Note the following when you are creating an XML index:</span></span>  
  
-   <span data-ttu-id="7eb29-108">Per creare un indice XML primario, è necessario che la tabella contenente la colonna XML da indicizzare, denominata tabella di base, includa un indice cluster nella chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="7eb29-108">To create a primary XML index, the table that contains the XML column being indexed, called the base table, must have a clustered index on the primary key.</span></span> <span data-ttu-id="7eb29-109">In tal modo si garantisce che, nel caso in cui la tabella di base sia partizionata, sia possibile partizionare l'indice XML primario tramite lo stesso schema e la stessa funzione di partizionamento.</span><span class="sxs-lookup"><span data-stu-id="7eb29-109">This makes sure that if the base table is partitioned, the primary XML index can be partitioned by using the same partitioning scheme and partitioning function.</span></span>  
  
-   <span data-ttu-id="7eb29-110">Se è presente un indice XML, non è possibile modificare la chiave primaria cluster della tabella.</span><span class="sxs-lookup"><span data-stu-id="7eb29-110">If an XML index exists, the clustered, primary key of the table cannot be modified.</span></span> <span data-ttu-id="7eb29-111">Prima di modificarla, sarà necessario eliminare tutti gli indici XML dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="7eb29-111">You will have to drop all XML indexes on the table before modifying the primary key.</span></span>  
  
-   <span data-ttu-id="7eb29-112">È possibile creare un indice XML primario in una singola colonna di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="7eb29-112">A primary XML index can be created on a single `xml` type column.</span></span> <span data-ttu-id="7eb29-113">Non è possibile creare nessun altro tipo di indice se la colonna di tipo XML è una colonna chiave.</span><span class="sxs-lookup"><span data-stu-id="7eb29-113">You cannot create any other type of index with the XML type column as a key column.</span></span> <span data-ttu-id="7eb29-114">È tuttavia possibile includere la colonna di tipo L `xml` in un indice non XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-114">However, you can include the `xml` L type column in a non-XML index.</span></span> <span data-ttu-id="7eb29-115">Ogni colonna di tipo `xml` in una tabella può includere l'indice XML primario corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7eb29-115">Each `xml` type column in a table can have its own primary XML index.</span></span> <span data-ttu-id="7eb29-116">È tuttavia consentito solo un indice XML primario per ogni colonna di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="7eb29-116">However, only one primary XML index per `xml` type column is permitted.</span></span>  
  
-   <span data-ttu-id="7eb29-117">Gli indici XML si trovano nello stesso spazio dei nomi degli indici non XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-117">XML indexes exist in the same namespace as non-XML indexes.</span></span> <span data-ttu-id="7eb29-118">Pertanto, nella stessa tabella non possono esistere un indice XML e un indice non XML con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="7eb29-118">Therefore, you cannot have an XML index and a non-XML index on the same table with the same name.</span></span>  
  
-   <span data-ttu-id="7eb29-119">Per gli indici XML, le opzioni IGNORE_DUP_KEY e ONLINE sono sempre impostate su OFF.</span><span class="sxs-lookup"><span data-stu-id="7eb29-119">IGNORE_DUP_KEY and ONLINE options of are always set to OFF for XML indexes.</span></span> <span data-ttu-id="7eb29-120">È possibile specificare queste opzioni con il valore OFF.</span><span class="sxs-lookup"><span data-stu-id="7eb29-120">You can specify these options with a value of OFF.</span></span>  
  
-   <span data-ttu-id="7eb29-121">Le informazioni sul filegroup o sul partizionamento della tabella utente vengono applicate all'indice XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-121">The filegroup or partitioning information of the user table is applied to the XML index.</span></span> <span data-ttu-id="7eb29-122">Gli utenti non possono specificare tali informazioni separatamente in un indice XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-122">Users cannot specify these separately on an XML index.</span></span>  
  
-   <span data-ttu-id="7eb29-123">L'opzione per gli indici DROP_EXISTING consente di eliminare un indice XML primario e di crearne uno nuovo oppure di eliminare un indice XML secondario e di crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="7eb29-123">The DROP_EXISTING index option can drop a primary XML index and create a new primary XML index, or drop a secondary XML index and create a new secondary XML index.</span></span> <span data-ttu-id="7eb29-124">Tale opzione, tuttavia, non consente di eliminare un indice XML secondario per creare un nuovo indice XML primario o viceversa.</span><span class="sxs-lookup"><span data-stu-id="7eb29-124">However, this option cannot drop a secondary XML index to create a new primary XML index or vice versa.</span></span>  
  
-   <span data-ttu-id="7eb29-125">Per i nomi degli indici XML primari vengono applicate le stesse restrizioni valide per i nomi delle viste.</span><span class="sxs-lookup"><span data-stu-id="7eb29-125">Primary XML index names have the same restrictions as view names.</span></span>  
  
 <span data-ttu-id="7eb29-126">Non è possibile creare un indice XML in una `xml` colonna di tipo in una vista, in una variabile con valori di **tabella** con `xml` colonne di tipo o variabili di `xml` tipo.</span><span class="sxs-lookup"><span data-stu-id="7eb29-126">You cannot create an XML index on an `xml` type column in a view, on a **table** valued variable with `xml` type columns, or `xml` type variables.</span></span>  
  
-   <span data-ttu-id="7eb29-127">Per modificare una colonna di tipo `xml` da XML non tipizzato a XML tipizzato, o viceversa, tramite l'opzione ALTER TABLE ALTER COLUMN, nella colonna non deve esistere alcun indice XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-127">To change an `xml` type column from untyped to typed XML, or vice versa, by using the ALTER TABLE ALTER COLUMN option, no XML index on the column should exist.</span></span> <span data-ttu-id="7eb29-128">In caso contrario, è necessario eliminarlo prima di provare a modificare il tipo della colonna.</span><span class="sxs-lookup"><span data-stu-id="7eb29-128">If one does exist, it must be dropped before the column type change is tried.</span></span>  
  
-   <span data-ttu-id="7eb29-129">Dopo la creazione di un indice XML, è necessario impostare l'opzione ARITHABORT su ON.</span><span class="sxs-lookup"><span data-stu-id="7eb29-129">The option ARITHABORT must be set to ON when an XML index is created.</span></span> <span data-ttu-id="7eb29-130">Per eseguire operazioni di query, inserimento, eliminazione o aggiornamento sui valori della colonna XML utilizzando i metodi con tipo di dati XML, è necessario impostare la stessa opzione nella connessione.</span><span class="sxs-lookup"><span data-stu-id="7eb29-130">To query, insert, delete, or update values in the XML column using XML data type methods, the same option must be set on the connection.</span></span> <span data-ttu-id="7eb29-131">In caso contrario, i metodi con tipo di dati XML avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="7eb29-131">If it is not, the XML data type methods will fail.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7eb29-132">Le informazioni su un indice XML sono disponibili nelle viste del catalogo.</span><span class="sxs-lookup"><span data-stu-id="7eb29-132">Information about an XML index can be found in catalog views.</span></span> <span data-ttu-id="7eb29-133">Tuttavia, **sp_helpindex** non è supportato.</span><span class="sxs-lookup"><span data-stu-id="7eb29-133">However, **sp_helpindex** is not supported.</span></span> <span data-ttu-id="7eb29-134">In questo argomento sono disponibili esempi che illustrano l'esecuzione di query sulle viste del catalogo per trovare informazioni sugli indici XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-134">Examples provided later in this topic show how to query the catalog views to find XML index information.</span></span>  
  
 <span data-ttu-id="7eb29-135">Quando si crea o si ricrea un indice XML primario in una colonna con tipo di dati XML che contiene valori dei tipi XML Schema **xs:date** o **xs:dateTime** o dei relativi sottotipi, non meno recenti di un anno, la creazione dell'indice non riuscirà in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="7eb29-135">When creating or recreating a primary XML index on an XML data type column that contains values of the XML Schema types **xs:date** or **xs:dateTime** (or any subtypes of these types) that have a year of less than 1, the index creation will fail in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="7eb29-136">sono consentiti questi valori, quindi questo problema può verificarsi quando si creano indici in un database generato in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7eb29-136">allowed these values, so this problem can occur when creating indexes in a database generated in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="7eb29-137">Per altre informazioni, vedere [Confrontare dati XML tipizzati con dati XML non tipizzati](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7eb29-137">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
### <a name="example-creating-a-primary-xml-index"></a><span data-ttu-id="7eb29-138">Esempio: Creazione di un indice XML primario</span><span class="sxs-lookup"><span data-stu-id="7eb29-138">Example: Creating a Primary XML Index</span></span>  
 <span data-ttu-id="7eb29-139">Nella maggior parte degli esempi viene utilizzata la tabella T (pk INT PRIMARY KEY, xCol XML), che include una colonna XML non tipizzata.</span><span class="sxs-lookup"><span data-stu-id="7eb29-139">Table T (pk INT PRIMARY KEY, xCol XML) with an untyped XML column is used in most of the examples.</span></span> <span data-ttu-id="7eb29-140">Gli esempi possono essere estesi senza difficoltà ai dati XML tipizzati.</span><span class="sxs-lookup"><span data-stu-id="7eb29-140">These can be extended to typed XML in a straightforward way.</span></span> <span data-ttu-id="7eb29-141">Per semplicità vengono descritte le query per le istanze di dati XML, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="7eb29-141">For simplicity, queries are described for XML data instances as shown in the following:</span></span>  
  
```  
<book genre="security" publicationdate="2002" ISBN="0-7356-1588-2">  
   <title>Writing Secure Code</title>  
   <author>  
      <first-name>Michael</first-name>  
      <last-name>Howard</last-name>  
   </author>  
   <author>  
      <first-name>David</first-name>  
      <last-name>LeBlanc</last-name>  
   </author>  
   <price>39.99</price>  
</book>  
```  
  
 <span data-ttu-id="7eb29-142">L'istruzione seguente crea un indice XML chiamato idx_xCol sulla colonna XML chiamata xCol della tabella T:</span><span class="sxs-lookup"><span data-stu-id="7eb29-142">The following statement creates an XML index, called idx_xCol, on the XML column xCol of table T:</span></span>  
  
```  
CREATE PRIMARY XML INDEX idx_xCol on T (xCol)  
```  
  
## <a name="creating-a-secondary-xml-index"></a><span data-ttu-id="7eb29-143">Creazione di un indice XML secondario</span><span class="sxs-lookup"><span data-stu-id="7eb29-143">Creating a Secondary XML Index</span></span>  
 <span data-ttu-id="7eb29-144">Usare l'istruzione DDL [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] per creare indici XML secondari e specificare il tipo di indice XML secondario desiderato.</span><span class="sxs-lookup"><span data-stu-id="7eb29-144">Use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement to create secondary XML indexes and specify the type of the secondary XML index that you want.</span></span>  
  
 <span data-ttu-id="7eb29-145">Per la creazione di indici XML secondari, si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7eb29-145">Note the following when you are creating secondary XML indexes:</span></span>  
  
-   <span data-ttu-id="7eb29-146">Per gli indici XML secondari sono consentite tutte le opzioni applicate a un indice non cluster, ad eccezione di IGNORE_DUP_KEY e di ONLINE.</span><span class="sxs-lookup"><span data-stu-id="7eb29-146">All indexing options that apply to a nonclustered index, except IGNORE_DUP_KEY and ONLINE, are permitted on secondary XML indexes.</span></span> <span data-ttu-id="7eb29-147">Per gli indici XML secondari, le due opzioni devono essere impostate sempre su OFF.</span><span class="sxs-lookup"><span data-stu-id="7eb29-147">The two options must always be set to OFF for secondary XML indexes.</span></span>  
  
-   <span data-ttu-id="7eb29-148">Gli indici secondari vengono partizionati esattamente come l'indice XML primario.</span><span class="sxs-lookup"><span data-stu-id="7eb29-148">The secondary indexes are partitioned just like the primary XML index.</span></span>  
  
-   <span data-ttu-id="7eb29-149">L'opzione DROP_EXISTING consente di eliminare un indice secondario dalla tabella utente e di crearne un altro.</span><span class="sxs-lookup"><span data-stu-id="7eb29-149">DROP_EXISTING can drop a secondary index on the user table and create another secondary index on the user table.</span></span>  
  
 <span data-ttu-id="7eb29-150">È possibile eseguire una query nella vista del catalogo **sys.xml_indexes** per recuperare informazioni sull'indice XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-150">You can query the **sys.xml_indexes** catalog view to retrieve XML index information.</span></span> <span data-ttu-id="7eb29-151">La colonna **seconday_type_desc** nella vista del catalogo **sys.xml_indexes** include il tipo di indice secondario:</span><span class="sxs-lookup"><span data-stu-id="7eb29-151">Note that the **secondary_type_desc** column in the **sys.xml_indexes** catalog view provides the type of secondary index:</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="7eb29-152">I valori restituiti nella colonna **seconday_type_desc** possono essere NULL, PATH, VALUE o PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="7eb29-152">The values returned in the **secondary_type_desc** column can be NULL, PATH, VALUE, or PROPERTY.</span></span> <span data-ttu-id="7eb29-153">Per l'indice XML primario, il valore restituito è NULL.</span><span class="sxs-lookup"><span data-stu-id="7eb29-153">For the primary XML index, the value returned is NULL.</span></span>  
  
### <a name="example-creating-secondary-xml-indexes"></a><span data-ttu-id="7eb29-154">Esempio: Creazione di indici XML secondari</span><span class="sxs-lookup"><span data-stu-id="7eb29-154">Example: Creating Secondary XML Indexes</span></span>  
 <span data-ttu-id="7eb29-155">Nell'esempio seguente viene illustrata la creazione di indici XML secondari.</span><span class="sxs-lookup"><span data-stu-id="7eb29-155">The following example illustrates how secondary XML indexes are created.</span></span> <span data-ttu-id="7eb29-156">Vengono inoltre fornite informazioni sugli indici XML creati.</span><span class="sxs-lookup"><span data-stu-id="7eb29-156">The example also shows information about the XML indexes that you created.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML);  
GO  
-- Create primary index.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol);  
GO  
-- Create secondary indexes (PATH, VALUE, PROPERTY).  
CREATE XML INDEX PIdx_T_XmlCol_PATH ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PATH;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_VALUE ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR VALUE;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_PROPERTY ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PROPERTY;  
GO  
```  
  
 <span data-ttu-id="7eb29-157">È possibile eseguire query in `sys.xml_indexes` per recuperare informazioni sugli indici XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-157">You can query the `sys.xml_indexes` to retrieve XML indexes information.</span></span> <span data-ttu-id="7eb29-158">La colonna `secondary_type_desc` contiene il tipo di indice secondario.</span><span class="sxs-lookup"><span data-stu-id="7eb29-158">The `secondary_type_desc` column provides the secondary index type.</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="7eb29-159">È inoltre possibile eseguire una query nella vista del catalogo per ottenere informazioni sugli indici.</span><span class="sxs-lookup"><span data-stu-id="7eb29-159">You can also query the catalog view for index information.</span></span>  
  
```  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T');  
```  
  
 <span data-ttu-id="7eb29-160">È possibile aggiungere dati di esempio e quindi rivedere le informazioni sugli indici XML.</span><span class="sxs-lookup"><span data-stu-id="7eb29-160">You can add sample data and then review the XML index information.</span></span>  
  
```  
INSERT INTO T VALUES (1,  
'<doc id="123">  
<sections>  
<section num="2">  
<heading>Background</heading>  
</section>  
<section num="3">  
<heading>Sort</heading>  
</section>  
<section num="4">  
<heading>Search</heading>  
</section>  
</sections>  
</doc>');  
GO  
-- Check XML index information.  
SELECT *  
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, NULL, 'DETAILED');  
GO  
-- Space usage of primary XML index  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id  
FROM    sys.xml_indexes i   
WHERE   i.name = 'PIdx_T_XmlCol' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
--- Space usage of secondary XML index (for example PATH secondary index)  PIdx_T_XmlCol_PATH  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id   
FROM    sys.xml_indexes i   
WHERE  i.name = 'PIdx_T_XmlCol_PATH' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
  
-- Space usage of all secondary XML indexes for a particular table  
SELECT i.name, object_name(i.object_id), stats.*   
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, DEFAULT, 'DETAILED') stats  
JOIN sys.xml_indexes i ON (stats.object_id = i.object_id and stats.index_id = i.index_id)  
WHERE secondary_type is not null;  
-- Drop secondary indexes.  
DROP INDEX PIdx_T_XmlCol_PATH ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_VALUE ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_PROPERTY ON T;  
GO  
-- Drop primary index.  
DROP INDEX PIdx_T_XmlCol ON T;  
-- Drop table T.  
DROP TABLE T;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="7eb29-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7eb29-161">See Also</span></span>  
 <span data-ttu-id="7eb29-162">[Indici XML &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7eb29-162">[XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span></span>  
 [<span data-ttu-id="7eb29-163">Dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7eb29-163">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
