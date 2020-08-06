---
title: Promuovere i valori XML di uso frequente mediante colonne calcolate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- promoting properties [XML in SQL Server]
- property promotion [XML in SQL Server]
ms.assetid: f5111896-c2fd-4209-b500-f2baa45489ad
author: rothja
ms.author: jroth
ms.openlocfilehash: bfb83b7772ffd92eab7087db11e4c3ffd96afa47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717543"
---
# <a name="promote-frequently-used-xml-values-with-computed-columns"></a><span data-ttu-id="56721-102">Promuovere i valori XML di uso frequente mediante colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="56721-102">Promote Frequently Used XML Values with Computed Columns</span></span>
  <span data-ttu-id="56721-103">Se le query vengono eseguite principalmente su un piccolo numero di valori di attributi e di elementi, sarà possibile promuovere tali quantità al livello di colonne relazionali.</span><span class="sxs-lookup"><span data-stu-id="56721-103">If queries are made principally on a small number of element and attribute values, you may want to promote those quantities into relational columns.</span></span> <span data-ttu-id="56721-104">Ciò risulta utile quando le query vengono eseguite su una piccola parte dei dati XML mentre viene recuperata l'intera istanza XML.</span><span class="sxs-lookup"><span data-stu-id="56721-104">This is helpful when queries are issued on a small part of the XML data while the whole XML instance is retrieved.</span></span> <span data-ttu-id="56721-105">Non è necessario creare un indice XML sulla colonna XML,</span><span class="sxs-lookup"><span data-stu-id="56721-105">Creating an XML index on the XML column is not required.</span></span> <span data-ttu-id="56721-106">ma è possibile indicizzare la colonna promossa.</span><span class="sxs-lookup"><span data-stu-id="56721-106">Instead, the promoted column can be indexed.</span></span> <span data-ttu-id="56721-107">Le query devono essere scritte in modo da utilizzare la colonna promossa,</span><span class="sxs-lookup"><span data-stu-id="56721-107">Queries must be written to use the promoted column.</span></span> <span data-ttu-id="56721-108">poiché il Query Optimizer non reindirizza alla colonna promossa le query eseguite sulla colonna XML.</span><span class="sxs-lookup"><span data-stu-id="56721-108">That is, the query optimizer does not target again the queries on the XML column to the promoted column.</span></span>  
  
 <span data-ttu-id="56721-109">La colonna promossa può essere una colonna calcolata nella stessa tabella oppure una colonna separata e gestita dall'utente in un'altra tabella.</span><span class="sxs-lookup"><span data-stu-id="56721-109">The promoted column can be a computed column in the same table or it can be a separate, user-maintained column in a table.</span></span> <span data-ttu-id="56721-110">Ciò è sufficiente quando i valori singleton vengono promossi da ogni istanza XML.</span><span class="sxs-lookup"><span data-stu-id="56721-110">This is sufficient when singleton values are promoted from each XML instance.</span></span> <span data-ttu-id="56721-111">Per le proprietà multivalore, invece, è necessario creare una tabella separata per la proprietà, come illustrato nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="56721-111">However, for multi-valued properties, you have to create a separate table for the property, as described in the following section.</span></span>  
  
## <a name="computed-column-based-on-the-xml-data-type"></a><span data-ttu-id="56721-112">Colonna calcolata basata sul tipo di dati xml</span><span class="sxs-lookup"><span data-stu-id="56721-112">Computed Column Based on the xml Data Type</span></span>  
 <span data-ttu-id="56721-113">Una colonna calcolata può essere creata utilizzando una funzione definita dall'utente che richiama `xml` i metodi del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="56721-113">A computed column can be created by using a user-defined function that invokes `xml` data type methods.</span></span> <span data-ttu-id="56721-114">Il tipo della colonna calcolata può essere qualsiasi tipo SQL, incluso il tipo XML,</span><span class="sxs-lookup"><span data-stu-id="56721-114">The type of the computed column can be any SQL type, including XML.</span></span> <span data-ttu-id="56721-115">Questo è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="56721-115">This is illustrated in the following example.</span></span>  
  
### <a name="example-computed-column-based-on-the-xml-data-type-method"></a><span data-ttu-id="56721-116">Esempio: Colonna calcolata basata su un metodo per il tipo di dati xml</span><span class="sxs-lookup"><span data-stu-id="56721-116">Example: Computed Column Based on the xml Data Type Method</span></span>  
 <span data-ttu-id="56721-117">Creare la funzione definita dall'utente per il codice ISBN di un libro:</span><span class="sxs-lookup"><span data-stu-id="56721-117">Create the user-defined function for a book ISBN number:</span></span>  
  
```  
CREATE FUNCTION udf_get_book_ISBN (@xData xml)  
RETURNS varchar(20)  
BEGIN  
   DECLARE @ISBN   varchar(20)  
   SELECT @ISBN = @xData.value('/book[1]/@ISBN', 'varchar(20)')  
   RETURN @ISBN   
END  
```  
  
 <span data-ttu-id="56721-118">Aggiungere alla tabella una colonna calcolata per il codice ISBN:</span><span class="sxs-lookup"><span data-stu-id="56721-118">Add a computed column to the table for the ISBN:</span></span>  
  
```  
ALTER TABLE      T  
ADD   ISBN AS dbo.udf_get_book_ISBN(xCol)  
```  
  
 <span data-ttu-id="56721-119">La colonna calcolata può essere indicizzata come di consueto.</span><span class="sxs-lookup"><span data-stu-id="56721-119">The computed column can be indexed in the usual way.</span></span>  
  
### <a name="example-queries-on-a-computed-column-based-on-xml-data-type-methods"></a><span data-ttu-id="56721-120">Esempio: Query su una colonna calcolata basata sui metodi per il tipo di dati XML</span><span class="sxs-lookup"><span data-stu-id="56721-120">Example: Queries on a Computed Column Based on xml Data Type Methods</span></span>  
 <span data-ttu-id="56721-121">Per ottenere l'elemento <`book`> il cui ISBN è 0-7356-1588-2:</span><span class="sxs-lookup"><span data-stu-id="56721-121">To obtain the <`book`> whose ISBN is 0-7356-1588-2:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  xCol.exist('/book/@ISBN[. = "0-7356-1588-2"]') = 1  
```  
  
 <span data-ttu-id="56721-122">La query sulla colonna XML può essere riscritta in modo da utilizzare la colonna calcolata, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="56721-122">The query on the XML column can be rewritten to use the computed column as follows:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  ISBN = '0-7356-1588-2'  
```  
  
 <span data-ttu-id="56721-123">È possibile creare una funzione definita dall'utente per restituire il `xml` tipo di dati e una colonna calcolata utilizzando la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="56721-123">You can create a user-defined function to return the `xml` data type and a computed column by using the user-defined function.</span></span> <span data-ttu-id="56721-124">ma non è possibile creare un indice XML sulla colonna XML calcolata.</span><span class="sxs-lookup"><span data-stu-id="56721-124">However, you cannot create an XML index on the computed, XML column.</span></span>  
  
## <a name="creating-property-tables"></a><span data-ttu-id="56721-125">Creazione di tabelle di proprietà</span><span class="sxs-lookup"><span data-stu-id="56721-125">Creating Property Tables</span></span>  
 <span data-ttu-id="56721-126">È possibile promuovere alcune delle proprietà multivalore dei dati XML fino a ottenere una o più tabelle, creare indici su tali tabelle e modificare la destinazione delle query in modo da utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="56721-126">You may want to promote some of the multivalued properties from your XML data into one or more tables, create indexes on those tables, and target again your queries to use them.</span></span> <span data-ttu-id="56721-127">Un tipico scenario è quello in cui la maggior parte del carico di lavoro delle query è costituita da un piccolo numero di proprietà.</span><span class="sxs-lookup"><span data-stu-id="56721-127">A typical scenario is one in which a small number of properties covers most of your query workload.</span></span> <span data-ttu-id="56721-128">È possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="56721-128">You can do the following:</span></span>  
  
-   <span data-ttu-id="56721-129">Creare una o più tabelle in cui inserire le proprietà multivalore.</span><span class="sxs-lookup"><span data-stu-id="56721-129">Create one or more tables to hold the multivalued properties.</span></span> <span data-ttu-id="56721-130">Risulta conveniente archiviare una proprietà per tabella e duplicare la chiave primaria della tabella di base nelle tabelle di proprietà, per poter eseguire il join all'indietro alla tabella di base.</span><span class="sxs-lookup"><span data-stu-id="56721-130">You may find it convenient to store one property per table and duplicate the primary key of the base table in the property tables for back joining with the base table.</span></span>  
  
-   <span data-ttu-id="56721-131">Se si desidera mantenere l'ordine relativo delle proprietà, sarà necessario introdurre una colonna separata per l'ordine relativo.</span><span class="sxs-lookup"><span data-stu-id="56721-131">If you want to maintain the relative order of the properties, you have to introduce a separate column for the relative order.</span></span>  
  
-   <span data-ttu-id="56721-132">Creare trigger sulla colonna XML per eseguire operazioni di manutenzione delle tabelle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="56721-132">Create triggers on the XML column to maintain the property tables.</span></span> <span data-ttu-id="56721-133">Nell'ambito dei trigger, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="56721-133">Within the triggers, do one of the following:</span></span>  
  
    -   <span data-ttu-id="56721-134">Usare `xml` i metodi con tipo di dati, ad esempio **Nodes ()** e **value ()**, per inserire ed eliminare righe delle tabelle delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="56721-134">Use `xml` data type methods, such as **nodes()** and **value()**, to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="56721-135">Creare funzioni di flusso con valori di tabella in Common Language Runtime (CLR) per inserire ed eliminare righe nelle tabelle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="56721-135">Create streaming table-valued functions in the common language runtime (CLR) to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="56721-136">Scrivere query per l'accesso SQL alle tabelle di proprietà e per l'accesso XML alla colonna XML nella tabella di base, utilizzandone la chiave primaria per creare join tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="56721-136">Write queries for SQL access to the property tables and for XML access to the XML column in the base table, with joins between the tables by using their primary key.</span></span>  
  
### <a name="example-create-a-property-table"></a><span data-ttu-id="56721-137">Esempio: Creare una tabella di proprietà</span><span class="sxs-lookup"><span data-stu-id="56721-137">Example: Create a Property Table</span></span>  
 <span data-ttu-id="56721-138">Si supponga ad esempio di voler promuovere i nomi degli autori.</span><span class="sxs-lookup"><span data-stu-id="56721-138">For illustration, assume that you want to promote the first name of the authors.</span></span> <span data-ttu-id="56721-139">Poiché un libro può avere più autori, quel nome è una proprietà multivalore.</span><span class="sxs-lookup"><span data-stu-id="56721-139">Books have one or more authors, so that first name is a multivalued property.</span></span> <span data-ttu-id="56721-140">Ogni nome è archiviato in una riga separata di una tabella di proprietà.</span><span class="sxs-lookup"><span data-stu-id="56721-140">Each first name is stored in a separate row of a property table.</span></span> <span data-ttu-id="56721-141">La chiave primaria della tabella di base viene duplicata nella tabella di proprietà per consentire il join all'indietro.</span><span class="sxs-lookup"><span data-stu-id="56721-141">The primary key of the base table is duplicated in the property table for back join.</span></span>  
  
```  
create table tblPropAuthor (propPK int, propAuthor varchar(max))  
```  
  
### <a name="example-create-a-user-defined-function-to-generate-a-rowset-from-an-xml-instance"></a><span data-ttu-id="56721-142">Esempio: Creare una funzione definita dall'utente per la generazione di un set di righe da un'istanza XML</span><span class="sxs-lookup"><span data-stu-id="56721-142">Example: Create a User-defined Function to Generate a Rowset from an XML Instance</span></span>  
 <span data-ttu-id="56721-143">La seguente funzione con valori di tabella, udf_XML2Table, accetta un valore di chiave primaria e un'istanza XML.</span><span class="sxs-lookup"><span data-stu-id="56721-143">The following table-valued function, udf_XML2Table, accepts a primary key value and an XML instance.</span></span> <span data-ttu-id="56721-144">Recupera il nome di tutti gli autori degli elementi <`book`> e restituisce un set di righe composto da coppie di chiave primaria e nome.</span><span class="sxs-lookup"><span data-stu-id="56721-144">It retrieves the first name of all authors of the <`book`> elements and returns a rowset of primary key, first name pairs.</span></span>  
  
```  
create function udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (propPK int, propAuthor varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
      select @pk, nref.value('.', 'varchar(max)')  
      from   @xCol.nodes('/book/author/first-name') R(nref)  
      return  
end  
```  
  
### <a name="example-create-triggers-to-populate-a-property-table"></a><span data-ttu-id="56721-145">Esempio: Creare trigger per il popolamento di una tabella di proprietà</span><span class="sxs-lookup"><span data-stu-id="56721-145">Example: Create Triggers to Populate a Property Table</span></span>  
 <span data-ttu-id="56721-146">Il trigger di inserimento consente di inserire righe nella tabella di proprietà:</span><span class="sxs-lookup"><span data-stu-id="56721-146">The insert trigger inserts rows into the property table:</span></span>  
  
```  
create trigger trg_docs_INS on T for insert  
as  
      declare @wantedXML xml  
      declare @FK int  
      select @wantedXML = xCol from inserted  
      select @FK = PK from inserted  
  
   insert into tblPropAuthor  
   select * from dbo.udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="56721-147">Il trigger di eliminazione consente di eliminare righe dalla tabella di proprietà, in base al valore della chiave primaria delle righe eliminate:</span><span class="sxs-lookup"><span data-stu-id="56721-147">The delete trigger deletes the rows from the property table based on the primary key value of the deleted rows:</span></span>  
  
```  
create trigger trg_docs_DEL on T for delete  
as  
   declare @FK int  
   select @FK = PK from deleted  
   delete tblPropAuthor where propPK = @FK  
```  
  
 <span data-ttu-id="56721-148">Il trigger di aggiornamento consente di eliminare dalla tabella di proprietà le righe esistenti corrispondenti all'istanza XML aggiornata e di inserire nuove righe nella tabella stessa:</span><span class="sxs-lookup"><span data-stu-id="56721-148">The update trigger deletes the existing rows in the property table corresponding to the updated XML instance and inserts new rows into the property table:</span></span>  
  
```  
create trigger trg_docs_UPD  
on T  
for update  
as  
if update(xCol) or update(pk)  
begin  
      declare @FK int  
      declare @wantedXML xml  
      select @FK = PK from deleted  
      delete tblPropAuthor where propPK = @FK  
  
   select @wantedXML = xCol from inserted  
   select @FK = pk from inserted  
  
   insert into tblPropAuthor   
      select * from dbo.udf_XML2Table(@FK, @wantedXML)  
end  
```  
  
### <a name="example-find-xml-instances-whose-authors-have-the-same-first-name"></a><span data-ttu-id="56721-149">Esempio: Cercare istanze XML i cui autori hanno lo stesso nome</span><span class="sxs-lookup"><span data-stu-id="56721-149">Example: Find XML Instances Whose Authors Have the Same First Name</span></span>  
 <span data-ttu-id="56721-150">È possibile creare la query nella colonna XML</span><span class="sxs-lookup"><span data-stu-id="56721-150">The query can be formed on the XML column.</span></span> <span data-ttu-id="56721-151">oppure è possibile ricercare il nome "David" nella tabella di proprietà ed eseguire un join all'indietro alla tabella di base, per restituire l'istanza XML.</span><span class="sxs-lookup"><span data-stu-id="56721-151">Alternatively, it can search the property table for first name "David" and perform a back join with the base table to return the XML instance.</span></span> <span data-ttu-id="56721-152">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="56721-152">For example:</span></span>  
  
```  
SELECT xCol   
FROM     T JOIN tblPropAuthor ON T.pk = tblPropAuthor.propPK  
WHERE    tblPropAuthor.propAuthor = 'David'  
```  
  
### <a name="example-solution-using-the-clr-streaming-table-valued-function"></a><span data-ttu-id="56721-153">Esempio: Soluzione che usa una funzione di flusso CLR con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="56721-153">Example: Solution Using the CLR Streaming Table-valued Function</span></span>  
 <span data-ttu-id="56721-154">Per creare questa soluzione è necessario eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="56721-154">This solution is made up of the following steps:</span></span>  
  
1.  <span data-ttu-id="56721-155">Definire una classe CLR, SqlReaderBase, che implementa ISqlReader e genera un output di flusso valutato a livello di tabella, applicando un'espressione di percorso a un'istanza XML.</span><span class="sxs-lookup"><span data-stu-id="56721-155">Define a CLR class, SqlReaderBase, that implements ISqlReader and generates a streaming, table-valued output by applying a path expression on an XML instance.</span></span>  
  
2.  <span data-ttu-id="56721-156">Creare un assembly e una funzione Transact-SQL definita dall'utente per avviare la classe CLR.</span><span class="sxs-lookup"><span data-stu-id="56721-156">Create an assembly and a Transact-SQL user-defined function to start the CLR class.</span></span>  
  
3.  <span data-ttu-id="56721-157">Definire i trigger di inserimento, aggiornamento ed eliminazione utilizzando la funzione definita dall'utente per la manutenzione delle tabelle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="56721-157">Define the insert, update, and delete triggers by using the user-defined function to maintain a property tables.</span></span>  
  
 <span data-ttu-id="56721-158">A tale scopo è innanzitutto necessario creare la funzione CLR di flusso.</span><span class="sxs-lookup"><span data-stu-id="56721-158">To do this, you first create the streaming CLR function.</span></span> <span data-ttu-id="56721-159">Il `xml` tipo di dati viene esposto come classe SqlXml gestita in ADO.NET e supporta il **Metodo CreateReader ()** che restituisce un oggetto XmlReader.</span><span class="sxs-lookup"><span data-stu-id="56721-159">The `xml` data type is exposed as a managed class SqlXml in ADO.NET and supports the **CreateReader()** method that returns an XmlReader.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56721-160">Il codice di esempio in questa sezione utilizza XPathDocument e XPathNavigator,</span><span class="sxs-lookup"><span data-stu-id="56721-160">The example code in this section uses XPathDocument and XPathNavigator.</span></span> <span data-ttu-id="56721-161">che impongono il caricamento in memoria di tutti i documenti XML.</span><span class="sxs-lookup"><span data-stu-id="56721-161">These force you to load all the XML documents into memory.</span></span> <span data-ttu-id="56721-162">Se nella propria applicazione si utilizza codice analogo per elaborare numerosi documenti XML di grandi dimensioni, sarà necessario ricordare che tale codice non è scalabile.</span><span class="sxs-lookup"><span data-stu-id="56721-162">If you are using similar code in your application to process several large XML documents, this code is not scalable.</span></span> <span data-ttu-id="56721-163">Se possibile, è preferibile utilizzare allocazioni di memoria di piccole dimensioni e utilizzare interfacce di flusso.</span><span class="sxs-lookup"><span data-stu-id="56721-163">Instead, keep memory allocations small and use streaming interfaces whenever possible.</span></span> <span data-ttu-id="56721-164">Per altre informazioni sulle prestazioni, vedere [Architettura dell'integrazione con CLR](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span><span class="sxs-lookup"><span data-stu-id="56721-164">For more information about performance, see [Architecture of CLR Integration](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span></span>  
  
```  
public class c_streaming_xml_tvf {  
   public static ISqlReader streaming_xml_tvf   
(SqlXml xmlDoc, string pathExpression) {  
      return (new TestSqlReaderBase (xmlDoc, pathExpression));  
   }  
}  
  
// Class that implements ISqlReader  
public class TestSqlReaderBase : ISqlReader {  
XPathNodeIterator m_iterator;           
   public SqlChars FirstName;  
// Metadata for current resultset  
private SqlMetaData[] m_rgSqlMetaData;        
  
   public TestSqlReaderBase (SqlXml xmlDoc, string pathExpression) {     
      // Variables for XPath navigation  
      XPathDocument xDoc;  
      XPathNavigator xNav;  
      XPathExpression xPath;  
  
      // Set sql metadata  
      m_rgSqlMetaData = new SqlMetaData[1];  
      m_rgSqlMetaData[0] = new SqlMetaData ("FirstName",    
SqlDbType.NVarChar,50);     
  
      //Set up the Navigator  
      if (!xmlDoc.IsNull)  
          xDoc = new XPathDocument (xmlDoc.CreateReader());  
      else  
          xDoc = new XPathDocument ();  
      xNav = xDoc.CreateNavigator();  
      xPath = xNav.Compile (pathExpression);  
      m_iterator = xNav.Select(xPath);  
   }  
   public bool Read() {  
      bool moreRows = true;  
      if (moreRows = m_iterator.MoveNext())  
         FirstName = new SqlChars (m_iterator.Current.Value);  
      return moreRows;  
   }  
}  
```  
  
 <span data-ttu-id="56721-165">Creare quindi un assembly e una funzione [!INCLUDE[tsql](../../includes/tsql-md.md)] definita dall'utente, SQL_streaming_xml_tvf (non illustrata), che corrisponde alla funzione CLR streaming_xml_tvf.</span><span class="sxs-lookup"><span data-stu-id="56721-165">Next, create an assembly and a [!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined function, SQL_streaming_xml_tvf (not shown), that corresponds to the CLR function, streaming_xml_tvf.</span></span> <span data-ttu-id="56721-166">La funzione definita dall'utente viene utilizzata per definire la funzione con valori di tabella, CLR_udf_XML2Table, per la generazione del set di righe:</span><span class="sxs-lookup"><span data-stu-id="56721-166">The user-defined function is used to define the table-valued function, CLR_udf_XML2Table, for rowset generation:</span></span>  
  
```  
create function CLR_udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (FK int, FirstName varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
   select @pk, FirstName   
   FROM   SQL_streaming_xml_tvf (@xCol, '/book/author/first-name')  
      return  
end  
```  
  
 <span data-ttu-id="56721-167">Definire infine i trigger come illustrato nell'esempio "Creazione di trigger per il popolamento di una tabella di proprietà", sostituendo tuttavia la funzione udf_XML2Table con la funzione CLR_udf_XML2Table.</span><span class="sxs-lookup"><span data-stu-id="56721-167">Finally, define triggers as shown in the example, "Create triggers to populate a property table", but replace udf_XML2Table with the CLR_udf_XML2Table function.</span></span> <span data-ttu-id="56721-168">Il trigger di inserimento è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="56721-168">The insert trigger is shown in the following example:</span></span>  
  
```  
create trigger CLR_trg_docs_INS on T for insert  
as  
   declare @wantedXML xml  
   declare @FK int  
   select @wantedXML = xCol from inserted  
   select @FK = PK from inserted  
  
   insert into tblPropAuthor  
      select *  
   from    dbo.CLR_udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="56721-169">Il trigger di eliminazione è identico alla versione non CLR,</span><span class="sxs-lookup"><span data-stu-id="56721-169">The delete trigger is identical to the non-CLR version.</span></span> <span data-ttu-id="56721-170">mentre nel trigger di inserimento viene semplicemente sostituita la funzione udf_XML2Table() con la funzione CLR_udf_XML2Table().</span><span class="sxs-lookup"><span data-stu-id="56721-170">However, the update trigger just replaces the function udf_XML2Table() with CLR_udf_XML2Table().</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56721-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56721-171">See Also</span></span>  
 [<span data-ttu-id="56721-172">Usare codice XML nelle colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="56721-172">Use XML in Computed Columns</span></span>](use-xml-in-computed-columns.md)  
  
  
