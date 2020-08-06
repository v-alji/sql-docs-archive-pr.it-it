---
title: Confrontare dati XML tipizzati con dati XML non tipizzati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- parameters [XML in SQL Server]
- facets [XML in SQL Server]
- xml data type [SQL Server], columns
- untyped XML
- xml data type [SQL Server], typed xml
- XML [SQL Server], typed
- variables [XML in SQL Server], creating
- xml data type [SQL Server], untyped xml
- columns [XML in SQL Server], creating
- typed XML
- document mode processing [SQL Server]
- XML [SQL Server], untyped
- xml data type [SQL Server], parameters
ms.assetid: 4bc50af9-2f7d-49df-bb01-854d080c72c7
author: rothja
ms.author: jroth
ms.openlocfilehash: fae9ca930bd8741a1332b61c8272f2133590483e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713936"
---
# <a name="compare-typed-xml-to-untyped-xml"></a><span data-ttu-id="806a4-102">Confronto dati XML tipizzati con dati XML non tipizzati</span><span class="sxs-lookup"><span data-stu-id="806a4-102">Compare Typed XML to Untyped XML</span></span>
  <span data-ttu-id="806a4-103">È possibile creare variabili, parametri e colonne di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="806a4-103">You can create variables, parameters, and columns of the `xml` type.</span></span> <span data-ttu-id="806a4-104">Se si desidera, è inoltre possibile associare una raccolta XML Schema a una variabile, un parametro o una colonna di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="806a4-104">You can optionally associate a collection of XML schemas with a variable, parameter, or column of `xml` type.</span></span> <span data-ttu-id="806a4-105">In questo caso, l' `xml` istanza del tipo di dati viene chiamata *tipizzata*.</span><span class="sxs-lookup"><span data-stu-id="806a4-105">In this case, the `xml` data type instance is called *typed*.</span></span> <span data-ttu-id="806a4-106">In caso contrario, l'istanza XML è definita *non tipizzata*.</span><span class="sxs-lookup"><span data-stu-id="806a4-106">Otherwise, the XML instance is called *untyped*.</span></span>  
  
## <a name="well-formed-xml-and-the-xml-data-type"></a><span data-ttu-id="806a4-107">Tipi di dati XML corretti e xml</span><span class="sxs-lookup"><span data-stu-id="806a4-107">Well-formed XML and the xml Data Type</span></span>  
 <span data-ttu-id="806a4-108">Il tipo di dati `xml` utilizza il tipo di dati standard ISO `xml`.</span><span class="sxs-lookup"><span data-stu-id="806a4-108">The `xml` data type implements the ISO standard `xml` data type.</span></span> <span data-ttu-id="806a4-109">Ciò consente pertanto l'archiviazione in una colonna XML non tipizzata di documenti di formato XML 1.0 corretto e frammenti di contenuto XML, con nodi di testo e un numero arbitrario di elementi di livello principale.</span><span class="sxs-lookup"><span data-stu-id="806a4-109">Therefore, it can store well-formed XML version 1.0 documents and also so-called XML content fragments with text nodes and an arbitrary number of top-level elements in an untyped XML column.</span></span> <span data-ttu-id="806a4-110">Il sistema verifica che il formato dei dati sia corretto, non richiede che la colonna sia associata a XML Schema e rifiuta i dati con formato non corretto in senso esteso.</span><span class="sxs-lookup"><span data-stu-id="806a4-110">The system checks that the data is well-formed, does not require the column to be bound to XML schemas, and rejects data that is not well-formed in the extended sense.</span></span> <span data-ttu-id="806a4-111">Questo vale anche per le variabili e i parametri XML non tipizzati.</span><span class="sxs-lookup"><span data-stu-id="806a4-111">This is true also of untyped XML variables and parameters.</span></span>  
  
## <a name="xml-schemas"></a><span data-ttu-id="806a4-112">XML Schema</span><span class="sxs-lookup"><span data-stu-id="806a4-112">XML Schemas</span></span>  
 <span data-ttu-id="806a4-113">XML Schema fornisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="806a4-113">An XML schema provides the following:</span></span>  
  
-   <span data-ttu-id="806a4-114">**Vincoli di convalida.**</span><span class="sxs-lookup"><span data-stu-id="806a4-114">**Validation constraints.**</span></span> <span data-ttu-id="806a4-115">Ogni volta che un'istanza xml tipizzata viene assegnata o modificata, tale istanza viene convalidata da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="806a4-115">Whenever a typed xml instance is assigned to or modified, SQL Server validates the instance.</span></span>  
  
-   <span data-ttu-id="806a4-116">**Informazioni sui tipi di dati.**</span><span class="sxs-lookup"><span data-stu-id="806a4-116">**Data type information.**</span></span> <span data-ttu-id="806a4-117">Gli schemi forniscono informazioni sui tipi di attributi e di elementi presenti nell'istanza del tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="806a4-117">Schemas provide information about the types of attributes and elements in the `xml` data type instance.</span></span> <span data-ttu-id="806a4-118">Le informazioni sul tipo forniscono una semantica operativa più precisa ai valori contenuti nell'istanza rispetto a quanto sia possibile con `xml` non tipizzato.</span><span class="sxs-lookup"><span data-stu-id="806a4-118">The type information provides more precise operational semantics to the values contained in the instance than is possible with untyped `xml`.</span></span> <span data-ttu-id="806a4-119">ad esempio è possibile eseguire le operazioni aritmetiche decimali su un valore decimale, ma non su un valore stringa.</span><span class="sxs-lookup"><span data-stu-id="806a4-119">For example, decimal arithmetic operations can be performed on a decimal value, but not on a string value.</span></span> <span data-ttu-id="806a4-120">Per questo motivo, i tipi di dati XML archiviati possono essere estremamente più compatti rispetto ai dati XML non tipizzati.</span><span class="sxs-lookup"><span data-stu-id="806a4-120">Because of this, typed XML storage can be made significantly more compact than untyped XML.</span></span>  
  
## <a name="choosing-typed-or-untyped-xml"></a><span data-ttu-id="806a4-121">Scelta tra dati XML tipizzati o non tipizzati</span><span class="sxs-lookup"><span data-stu-id="806a4-121">Choosing Typed or Untyped XML</span></span>  
 <span data-ttu-id="806a4-122">Utilizzare il tipo di dati `xml` non tipizzato nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="806a4-122">Use untyped `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="806a4-123">Non è disponibile uno schema per i dati XML.</span><span class="sxs-lookup"><span data-stu-id="806a4-123">You do not have a schema for your XML data.</span></span>  
  
-   <span data-ttu-id="806a4-124">Gli schemi sono disponibili ma non si desidera che i dati vengano convalidati dal server.</span><span class="sxs-lookup"><span data-stu-id="806a4-124">You have schemas, but you do not want the server to validate the data.</span></span> <span data-ttu-id="806a4-125">Questo avviene talvolta quando un'applicazione esegue una convalida sul lato client prima di archiviare i dati sul server, archivia temporaneamente dati XML non validi in base allo schema oppure utilizza componenti di schema non supportati dal server.</span><span class="sxs-lookup"><span data-stu-id="806a4-125">This is sometimes the case when an application performs client-side validation before storing the data at the server, or temporarily stores XML data that is invalid according to the schema, or uses schema components that are not supported at the server.</span></span>  
  
 <span data-ttu-id="806a4-126">Utilizzare `xml` il tipo di dati tipizzato nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="806a4-126">Use typed `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="806a4-127">Gli schemi per i dati XML sono disponibili e si desidera che i dati XML vengano convalidati dal server in base a XML Schema.</span><span class="sxs-lookup"><span data-stu-id="806a4-127">You have schemas for your XML data and you want the server to validate your XML data according to the XML schemas.</span></span>  
  
-   <span data-ttu-id="806a4-128">Si desidera avvalersi delle ottimizzazioni query e dell'archiviazione basandosi sulle informazioni sui tipi.</span><span class="sxs-lookup"><span data-stu-id="806a4-128">You want to take advantage of storage and query optimizations based on type information.</span></span>  
  
-   <span data-ttu-id="806a4-129">Si desidera avvalersi delle informazioni sui tipi durante la compilazione delle query.</span><span class="sxs-lookup"><span data-stu-id="806a4-129">You want to take better advantage of type information during compilation of your queries.</span></span>  
  
 <span data-ttu-id="806a4-130">Nelle colonne, nelle variabili e nei parametri XML tipizzati è possibile archiviare documenti o contenuto XML.</span><span class="sxs-lookup"><span data-stu-id="806a4-130">Typed XML columns, parameters, and variables can store XML documents or content.</span></span> <span data-ttu-id="806a4-131">Nella dichiarazione è tuttavia necessario specificare, tramite un flag, se si desidera archiviare un documento o del contenuto.</span><span class="sxs-lookup"><span data-stu-id="806a4-131">However, you have to specify with a flag whether you are storing a document or content at the time of declaration.</span></span> <span data-ttu-id="806a4-132">È inoltre necessario fornire la raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="806a4-132">Additionally, you have to provide the collection of XML schemas.</span></span> <span data-ttu-id="806a4-133">Specificare DOCUMENT se ogni istanza XML include esattamente un elemento di livello principale,</span><span class="sxs-lookup"><span data-stu-id="806a4-133">Specify DOCUMENT if each XML instance has exactly one top-level element.</span></span> <span data-ttu-id="806a4-134">CONTENT in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="806a4-134">Otherwise, use CONTENT.</span></span> <span data-ttu-id="806a4-135">Nella verifica dei tipi eseguita durante la compilazione delle query il compilatore utilizza il flag DOCUMENT per derivare gli elementi singleton di livello principale.</span><span class="sxs-lookup"><span data-stu-id="806a4-135">The query compiler uses the DOCUMENT flag in type checks during query compilation to infer singleton top-level elements.</span></span>  
  
## <a name="creating-typed-xml"></a><span data-ttu-id="806a4-136">Creazione di dati XML tipizzati</span><span class="sxs-lookup"><span data-stu-id="806a4-136">Creating Typed XML</span></span>  
 <span data-ttu-id="806a4-137">Prima di poter creare variabili tipizzate `xml` , parametri o colonne, è necessario innanzitutto registrare la raccolta di XML schema utilizzando [Create XML schema collection &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="806a4-137">Before you can create typed `xml` variables, parameters, or columns, you must first register the XML schema collection by using [CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span> <span data-ttu-id="806a4-138">È quindi possibile associare la raccolta XML Schema alle variabili, ai parametri o alle colonne del tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="806a4-138">You can then associate the XML schema collection with variables, parameters, or columns of the `xml` data type.</span></span>  
  
 <span data-ttu-id="806a4-139">Negli esempi seguenti, per specificare il nome della raccolta XML Schema viene utilizzata una convenzione di denominazione in due parti.</span><span class="sxs-lookup"><span data-stu-id="806a4-139">In the following examples, a two-part naming convention is used for specifying the XML schema collection name.</span></span> <span data-ttu-id="806a4-140">La prima parte è il nome dello schema e la seconda parte è il nome della raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="806a4-140">The first part is the schema name, and the second part is the XML schema collection name.</span></span>  
  
### <a name="example-associating-a-schema-collection-with-an-xml-type-variable"></a><span data-ttu-id="806a4-141">Esempio: Associazione di una raccolta di schemi a una variabile di tipo XML</span><span class="sxs-lookup"><span data-stu-id="806a4-141">Example: Associating a Schema Collection with an xml Type Variable</span></span>  
 <span data-ttu-id="806a4-142">Nell'esempio seguente viene creata una `xml` variabile di tipo a cui viene associata una raccolta di schemi.</span><span class="sxs-lookup"><span data-stu-id="806a4-142">The following example creates an`xml` type variable and associates a schema collection with it.</span></span> <span data-ttu-id="806a4-143">La raccolta di schemi specificata è già stata importata nel database **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="806a4-143">The schema collection specified in the example is already imported in the **AdventureWorks** database.</span></span>  
  
```  
DECLARE @x xml (Production.ProductDescriptionSchemaCollection);   
```  
  
### <a name="example-specifying-a-schema-for-an-xml-type-column"></a><span data-ttu-id="806a4-144">Esempio: Specifica di uno schema per una colonna di tipo XML</span><span class="sxs-lookup"><span data-stu-id="806a4-144">Example: Specifying a Schema for an xml Type Column</span></span>  
 <span data-ttu-id="806a4-145">Nell'esempio seguente viene creata una tabella con una colonna di tipo `xml` e viene specificato uno schema per la colonna:</span><span class="sxs-lookup"><span data-stu-id="806a4-145">The following example creates a table with an `xml` type column and specifies a schema for the column:</span></span>  
  
```  
CREATE TABLE T1(  
 Col1 int,   
 Col2 xml (Production.ProductDescriptionSchemaCollection)) ;  
```  
  
### <a name="example-passing-an-xml-type-parameter-to-a-stored-procedure"></a><span data-ttu-id="806a4-146">Esempio: Passaggio di un parametro di tipo XML a una stored procedure</span><span class="sxs-lookup"><span data-stu-id="806a4-146">Example: Passing an xml Type Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="806a4-147">Nell'esempio seguente viene passato un parametro di tipo `xml` a una stored procedure e viene specificato uno schema per la variabile:</span><span class="sxs-lookup"><span data-stu-id="806a4-147">The following example passes an `xml` type parameter to a stored procedure and specifies a schema for the variable:</span></span>  
  
```  
CREATE PROCEDURE SampleProc   
  @ProdDescription xml (Production.ProductDescriptionSchemaCollection)   
AS   
...  
```  
  
 <span data-ttu-id="806a4-148">Per la raccolta XML Schema, si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="806a4-148">Note the following about the XML schema collection:</span></span>  
  
-   <span data-ttu-id="806a4-149">Una raccolta XML Schema è disponibile solo nel database in cui è stata registrata tramite [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="806a4-149">An XML schema collection is available only in the database in which it was registered by using [Creating an XML Schema Collection](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span>  
  
-   <span data-ttu-id="806a4-150">Se si esegue il cast da una stringa a un tipo di dati `xml` tipizzato, durante l'analisi vengono inoltre eseguite la convalida e la tipizzazione, in base agli spazi dei nomi XML Schema della raccolta specificata.</span><span class="sxs-lookup"><span data-stu-id="806a4-150">If you cast from a string to a typed `xml` data type, the parsing also performs validation and typing, based on the XML schema namespaces in the collection specified.</span></span>  
  
-   <span data-ttu-id="806a4-151">È possibile eseguire il cast da un tipo di dati `xml` tipizzato a un tipo di dati `xml` non tipizzato e viceversa.</span><span class="sxs-lookup"><span data-stu-id="806a4-151">You can cast from a typed `xml` data type to an untyped `xml` data type, and vice versa.</span></span>  
  
 <span data-ttu-id="806a4-152">Per altre informazioni sugli altri modi disponibili per generare codice XML in SQL Server, vedere [Creare istanze di dati XML](create-instances-of-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="806a4-152">For more information about other ways to generate XML in SQL Server, see [Create Instances of XML Data](create-instances-of-xml-data.md).</span></span> <span data-ttu-id="806a4-153">Dopo avere generato il codice XML, è possibile assegnarlo a una variabile con tipo di dati `xml` o archiviarlo in colonne di tipo `xml` per elaborazioni successive.</span><span class="sxs-lookup"><span data-stu-id="806a4-153">After XML is generated, it can be assigned either to an `xml` data type variable or stored in `xml` type columns for additional processing.</span></span>  
  
 <span data-ttu-id="806a4-154">Nella gerarchia dei tipi di dati, il tipo di dati `xml` è visualizzato sotto al tipo `sql_variant` e ai tipi definiti dall'utente, ma sopra ai tipi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="806a4-154">In the data type hierarchy, the `xml` data type appears below `sql_variant` and user-defined types, but above any of the built-in types.</span></span>  
  
### <a name="example-specifying-facets-to-constrain-a-typed-xml-column"></a><span data-ttu-id="806a4-155">Esempio: Specifica di facet per vincolare una colonna xml tipizzata</span><span class="sxs-lookup"><span data-stu-id="806a4-155">Example: Specifying Facets to Constrain a Typed xml Column</span></span>  
 <span data-ttu-id="806a4-156">È possibile vincolare le colonne `xml` tipizzate in modo tale che in ogni istanza archiviata in tali colonne siano consentiti solo elementi principali singoli.</span><span class="sxs-lookup"><span data-stu-id="806a4-156">For typed `xml` columns, you can constrain the column to allow only single, top-level elements for each instance stored in it.</span></span> <span data-ttu-id="806a4-157">A tale scopo, è possibile specificare il facet facoltativo `DOCUMENT` durante la creazione di una tabella, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="806a4-157">You do this by specifying the optional `DOCUMENT` facet when a table is created, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml   
   (DOCUMENT Production.ProductDescriptionSchemaCollection));  
GO  
DROP TABLE T;  
GO  
```  
  
 <span data-ttu-id="806a4-158">Per impostazione predefinita, le istanze archiviate nella colonna `xml` tipizzata sono archiviate come contenuto XML e non come documenti XML.</span><span class="sxs-lookup"><span data-stu-id="806a4-158">By default, instances stored in the typed `xml` column are stored as XML content and not as XML documents.</span></span> <span data-ttu-id="806a4-159">Ciò consente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="806a4-159">This allows for the following:</span></span>  
  
-   <span data-ttu-id="806a4-160">Zero elementi principali oppure nessuno</span><span class="sxs-lookup"><span data-stu-id="806a4-160">Zero or many top-level elements</span></span>  
  
-   <span data-ttu-id="806a4-161">Nodi di testo negli elementi principali</span><span class="sxs-lookup"><span data-stu-id="806a4-161">Text nodes in top-level elements</span></span>  
  
 <span data-ttu-id="806a4-162">È inoltre possibile specificare in modo esplicito questo comportamento aggiungendo il facet `CONTENT` , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="806a4-162">You can also explicitly specify this behavior by adding `CONTENT` facet, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml(CONTENT Production.ProductDescriptionSchemaCollection));  
GO -- Default  
```  
  
 <span data-ttu-id="806a4-163">Si noti che è possibile specificare i facet facoltativi DOCUMENT/CONTENT in qualsiasi posizione in cui viene definito il tipo `xml` (xml tipizzato).</span><span class="sxs-lookup"><span data-stu-id="806a4-163">Note that you can specify the optional DOCUMENT/CONTENT facets anywhere you define `xml` type (typed xml).</span></span> <span data-ttu-id="806a4-164">Ad esempio, quando si crea una variabile `xml` tipizzata, è possibile aggiungere il facet DOCUMENT/CONTENT, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="806a4-164">For example, when you create a typed `xml` variable, you can add the DOCUMENT/CONTENT facet, as shown in the following:</span></span>  
  
```  
declare @x xml (DOCUMENT Production.ProductDescriptionSchemaCollection);  
```  
  
## <a name="document-type-definition-dtd"></a><span data-ttu-id="806a4-165">Definizione del tipo di documento (DTD, Document Type Definition)</span><span class="sxs-lookup"><span data-stu-id="806a4-165">Document Type Definition (DTD)</span></span>  
 <span data-ttu-id="806a4-166">Le colonne, le variabili e i parametri con tipo di dati `xml` possono essere tipizzati tramite XML Schema, ma non tramite una definizione DTD.</span><span class="sxs-lookup"><span data-stu-id="806a4-166">The `xml` data type columns, variables, and parameters can be typed by using XML schema, but not by using DTD.</span></span> <span data-ttu-id="806a4-167">Sia per i tipi di dati XML tipizzati che non tipizzati, è tuttavia possibile utilizzare DTD inline per specificare valori predefiniti e sostituire i riferimenti alle entità con le corrispondenti forme espanse.</span><span class="sxs-lookup"><span data-stu-id="806a4-167">However, inline DTD can be used for both untyped and typed XML to supply default values and to replace entity references with their expanded form.</span></span>  
  
 <span data-ttu-id="806a4-168">È possibile convertire DTD in documenti di XML Schema tramite strumenti di terze parti e caricare XML Schema nel database.</span><span class="sxs-lookup"><span data-stu-id="806a4-168">You can convert DTDs to XML schema documents by using third-party tools, and load the XML schemas into the database.</span></span>  
  
## <a name="upgrading-typed-xml-from-sql-server-2005"></a><span data-ttu-id="806a4-169">Aggiornamento di dati XML tipizzati da SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="806a4-169">Upgrading Typed XML from SQL Server 2005</span></span>  
 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="806a4-170">include diverse estensioni per il supporto di XML Schema, compreso il supporto per la convalida di tipo lax, la gestione migliorata dei dati delle istanze **xs:date**, **xs:time** e **xs:dateTime** e il supporto aggiunto per i tipi elenco e unione.</span><span class="sxs-lookup"><span data-stu-id="806a4-170">made several extensions to the XML Schema support, including support for lax validation, improved handling of **xs:date**, **xs:time** and **xs:dateTime** instance data, and added support for list and union types.</span></span> <span data-ttu-id="806a4-171">Nella maggior parte dei casi le modifiche non influiscono sull'esperienza dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="806a4-171">In most cases the changes do not affect the upgrade experience.</span></span> <span data-ttu-id="806a4-172">Se tuttavia è stata utilizzata una raccolta XML Schema in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] che consentiva valori di tipo **xs:date**, **xs:time**o **xs:dateTime** (o qualsiasi sottotipo), quando si collega il database [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] a una versione successiva di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]si verificano i seguenti passaggi di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="806a4-172">However if you used an XML Schema collection in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] that allowed values of type **xs:date**, **xs:time**, or **xs:dateTime** (or any subtype) then the following upgrade steps occur when you attach your [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database to a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="806a4-173">Per ogni colonna XML, tipizzata con una raccolta XML Schema che contiene elementi o attributi tipizzati come **xs:anyType**, **xs:anySimpleType**, **xs:date** o uno qualsiasi dei sottotipi, **xs:time** o uno qualsiasi dei suoi sottotipi oppure **xs:dateTime** o uno qualsiasi dei suoi sottotipi o i tipi unione ed elenco che contengono uno di questi tipi, si verifica quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="806a4-173">For every XML column, that is typed with an XML Schema Collection that contains elements or attributes that are typed as either **xs:anyType**, **xs:anySimpleType**, **xs:date** or any of its subtypes, **xs:time** or any subtype thereof, or **xs:dateTime** or any of its subtypes, or are union or list types containing any of these types the following occurs:</span></span>  
  
    1.  <span data-ttu-id="806a4-174">Tutti gli indici XML nella colonna saranno disabilitati.</span><span class="sxs-lookup"><span data-stu-id="806a4-174">All XML indices on the column will be disabled.</span></span>  
  
    2.  <span data-ttu-id="806a4-175">Tutti i valori [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] continueranno a essere rappresentati nel fuso orario Z, perché sono stati normalizzati al fuso orario Z.</span><span class="sxs-lookup"><span data-stu-id="806a4-175">All [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] values will continue to be represented in the Z timezone, because they have been normalized to the Z timezone.</span></span>  
  
    3.  <span data-ttu-id="806a4-176">Qualsiasi valore **xs:date** o **xs:dateTime** precedente al 1° gennaio dell'anno 1 determinerà un errore di runtime quando l'indice viene ricompilato oppure viene eseguita un'istruzione XQuery o SML-DML rispetto al tipo di dati XML contenente quel valore.</span><span class="sxs-lookup"><span data-stu-id="806a4-176">Any **xs:date** or **xs:dateTime** values that are smaller than January 1st of year 1 will lead to a runtime error when the index gets rebuild or an XQuery or XML-DML statements gets executed against the XML data type containing that value.</span></span>  
  
2.  <span data-ttu-id="806a4-177">Ogni anno negativo nei facet **xs:date** o **xs:dateTime** o nei valori predefiniti in una raccolta XML Schema sarà aggiornato automaticamente al valore più piccolo consentito dal tipo di base **xs:date** o **xs:dateTime** (ad esempio, 0001-01-01T00: 00:00.0000000 Z per **xs:dateTime**).</span><span class="sxs-lookup"><span data-stu-id="806a4-177">Any negative years in **xs:date** or **xs:dateTime** facets or default values in an XML Schema collection will automatically be updated to the smallest value allowed by the base **xs:date** or **xs:dateTime** type (e.g., 0001-01-01T00:00:00.0000000Z for **xs:dateTime**).</span></span>  
  
 <span data-ttu-id="806a4-178">Si noti che ancora è possibile utilizzare una semplice istruzione Select di SQL per recuperare il tipo di dati XML intero, anche se contiene anni negativi.</span><span class="sxs-lookup"><span data-stu-id="806a4-178">Note that you can still use a simple SQL select statement to retrieve the whole XML data type, even if it contains negative years.</span></span> <span data-ttu-id="806a4-179">Si consiglia di sostituire gli anni negativi con un anno all'interno del nuovo intervallo supportato o modificare il tipo dell'elemento o dell'attributo in **xs:string**.</span><span class="sxs-lookup"><span data-stu-id="806a4-179">It is recommended that you replace negative years with a year within the newly supported range or change the type of the element or attribute to **xs:string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="806a4-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="806a4-180">See Also</span></span>  
 <span data-ttu-id="806a4-181">[Creare istanze di dati XML](create-instances-of-xml-data.md) </span><span class="sxs-lookup"><span data-stu-id="806a4-181">[Create Instances of XML Data](create-instances-of-xml-data.md) </span></span>  
 <span data-ttu-id="806a4-182">[metodi con tipo di dati XML](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="806a4-182">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="806a4-183">[Linguaggio XML di manipolazione dei dati &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="806a4-183">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="806a4-184">Dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="806a4-184">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
