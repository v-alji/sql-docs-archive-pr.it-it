---
title: Linee guida e limitazioni del caricamento bulk XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], about XML Bulk Load
- bulk load [SQLXML], about bulk load
ms.assetid: c5885d14-c7c1-47b3-a389-455e99a7ece1
author: rothja
ms.author: jroth
ms.openlocfilehash: 08c0020ac7b28702f5a573c6158ec9d50c735b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634963"
---
# <a name="guidelines-and-limitations-of-xml-bulk-load-sqlxml-40"></a><span data-ttu-id="aaed2-102">Linee guida e limitazioni per il caricamento bulk XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="aaed2-102">Guidelines and Limitations of XML Bulk Load (SQLXML 4.0)</span></span>
  <span data-ttu-id="aaed2-103">Quando si utilizza il caricamento bulk XML, è consigliabile disporre di una certa familiarità con le linee guida e le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aaed2-103">When you use XML Bulk Load, you should be familiar with the following guidelines and limitations:</span></span>  
  
-   <span data-ttu-id="aaed2-104">Gli schemi inline non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="aaed2-104">Inline schemas are not supported.</span></span>  
  
     <span data-ttu-id="aaed2-105">Se nel documento XML di origine è presente uno schema inline, questo viene ignorato dal caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="aaed2-105">If you have an inline schema in the source XML document, XML Bulk Load ignores that schema.</span></span> <span data-ttu-id="aaed2-106">È necessario specificare lo schema di mapping per il caricamento bulk XML come esterno ai dati XML.</span><span class="sxs-lookup"><span data-stu-id="aaed2-106">You specify the mapping schema for XML Bulk Load external to the XML data.</span></span> <span data-ttu-id="aaed2-107">Non è possibile specificare lo schema di mapping in un nodo usando l'attributo **xmlns = "x:schema"** .</span><span class="sxs-lookup"><span data-stu-id="aaed2-107">You cannot specify the mapping schema at a node by using the **xmlns="x:schema"** attribute.</span></span>  
  
-   <span data-ttu-id="aaed2-108">Un documento XML viene controllato per verificare che utilizzi un formato corretto, ma non viene convalidato.</span><span class="sxs-lookup"><span data-stu-id="aaed2-108">An XML document is checked for being well-formed, but it is not validated.</span></span>  
  
     <span data-ttu-id="aaed2-109">Il caricamento bulk XML controlla il documento XML per determinare se il formato è corretto, ovvero per garantire che il codice XML sia conforme ai requisiti di sintassi della raccomandazione XML 1,0 del World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="aaed2-109">XML Bulk Load checks the XML document to determine whether it is well-formed-that is, to ensure that the XML conforms to the syntax requirements of the World Wide Web Consortium's XML 1.0 recommendation.</span></span> <span data-ttu-id="aaed2-110">Se il formato del documento non è corretto, il caricamento bulk XML annulla l'elaborazione e restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="aaed2-110">If the document is not well-formed, XML Bulk Load cancels processing and returns an error.</span></span> <span data-ttu-id="aaed2-111">L'unica eccezione a questo comportamento è costituita dal caso in cui il documento è un frammento, ad esempio non dispone di un singolo elemento radice. In questo caso, il documento verrà caricato.</span><span class="sxs-lookup"><span data-stu-id="aaed2-111">The only exception to this is when the document is a fragment (for example, the document has no single root element), in which case XML Bulk Load will load the document.</span></span>  
  
     <span data-ttu-id="aaed2-112">Il caricamento bulk XML non convalida il documento rispetto ad alcuno schema dati XML o DTD definito o a cui si fa riferimento all'interno del file di dati XML.</span><span class="sxs-lookup"><span data-stu-id="aaed2-112">XML Bulk Load does not validate the document with respect to any XML-Data or DTD schema that is defined or referenced within the XML data file.</span></span> <span data-ttu-id="aaed2-113">Il caricamento bulk XML, inoltre, non convalida il file di dati XML rispetto allo schema di mapping fornito.</span><span class="sxs-lookup"><span data-stu-id="aaed2-113">In addition, XML Bulk Load does not validate the XML data file against the mapping schema supplied.</span></span>  
  
-   <span data-ttu-id="aaed2-114">Vengono ignorate tutte le informazioni sui prologhi XML.</span><span class="sxs-lookup"><span data-stu-id="aaed2-114">Any XML prolog information is ignored.</span></span>  
  
     <span data-ttu-id="aaed2-115">Il caricamento bulk XML ignora tutte le informazioni prima e dopo l' \<root> elemento nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="aaed2-115">XML Bulk Load ignores all the information before and after the \<root> element in the XML document.</span></span> <span data-ttu-id="aaed2-116">Il caricamento bulk XML, ad esempio, ignora qualsiasi dichiarazione XML, qualsiasi definizione DTD interna e tutti i riferimenti DTD esterni, i commenti e così via.</span><span class="sxs-lookup"><span data-stu-id="aaed2-116">For example, XML Bulk Load ignores any XML declarations, internal DTD definitions, external DTD references, comments, and so on.</span></span>  
  
-   <span data-ttu-id="aaed2-117">Se è presente uno schema di mapping che definisce una relazione di chiave primaria/chiave esterna tra due tabelle, ad esempio tra Customer e CustOrder, la tabella con la chiave primaria deve essere descritta per prima nello schema.</span><span class="sxs-lookup"><span data-stu-id="aaed2-117">If you have a mapping schema that defines a primary key/foreign key relationship between two tables (such as between Customer and CustOrder), the table with the primary key must be described first in the schema.</span></span> <span data-ttu-id="aaed2-118">La tabella con la colonna chiave esterna deve essere visualizzata come successiva nello schema.</span><span class="sxs-lookup"><span data-stu-id="aaed2-118">The table with the foreign key column must appear later in the schema.</span></span> <span data-ttu-id="aaed2-119">Il motivo è che l'ordine in cui le tabelle vengono identificate nello schema è l'ordine utilizzato per caricarle nel database. Lo schema XDR seguente, ad esempio, genera un errore quando viene utilizzato nel caricamento bulk XML, in quanto l' **\<Order>** elemento viene descritto prima dell' **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="aaed2-119">The reason for this is that the order in which the tables are identified in the schema is the order that is used to load them into the database.For example, the following XDR schema will produce an error when it is used in XML Bulk Load because the **\<Order>** element is described before the **\<Customer>** element.</span></span> <span data-ttu-id="aaed2-120">La colonna CustomerID in CustOrder è una colonna chiave esterna che fa riferimento alla colonna chiave primaria CustomerID nella tabella Cust.</span><span class="sxs-lookup"><span data-stu-id="aaed2-120">The CustomerID column in CustOrder is a foreign key column that refers to the CustomerID primary key column in the Cust table.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
        <ElementType name="Order" sql:relation="CustOrder" >  
          <AttributeType name="OrderID" />  
          <AttributeType name="CustomerID" />  
          <attribute type="OrderID" />  
          <attribute type="CustomerID" />  
        </ElementType>  
  
       <ElementType name="CustomerID" dt:type="int" />  
       <ElementType name="CompanyName" dt:type="string" />  
       <ElementType name="City" dt:type="string" />  
  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
       <ElementType name="Customers" sql:relation="Cust"   
                         sql:overflow-field="OverflowColumn"  >  
          <element type="CustomerID" sql:field="CustomerID" />  
          <element type="CompanyName" sql:field="CompanyName" />  
          <element type="City" sql:field="City" />  
          <element type="Order" >   
               <sql:relationship  
                   key-relation="Cust"  
                    key="CustomerID"  
                    foreign-key="CustomerID"  
                    foreign-relation="CustOrder" />  
          </element>  
       </ElementType>  
    </Schema>  
    ```  
  
-   <span data-ttu-id="aaed2-121">Se lo schema non specifica colonne di overflow tramite l'annotazione `sql:overflow-field`, il caricamento bulk XML ignora tutti i dati presenti nel documento XML ma che non sono descritti nello schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="aaed2-121">If the schema does not specify overflow columns by using the `sql:overflow-field` annotation, XML Bulk Load ignores any data that is present in the XML document but is not described in the mapping schema.</span></span>  
  
     <span data-ttu-id="aaed2-122">Il caricamento bulk XML applica lo schema di mapping specificato ogni volta che rileva tag noti nel flusso di dati XML</span><span class="sxs-lookup"><span data-stu-id="aaed2-122">XML Bulk Load applies the mapping schema that you have specified whenever it encounters known tags in the XML data stream.</span></span> <span data-ttu-id="aaed2-123">e ignora i dati presenti nel documento XML ma che non sono descritti nello schema.</span><span class="sxs-lookup"><span data-stu-id="aaed2-123">It ignores data that is present in the XML document but is not described in the schema.</span></span> <span data-ttu-id="aaed2-124">Si supponga, ad esempio, di disporre di uno schema di mapping che descrive un **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="aaed2-124">For example, assume you have a mapping schema that describes a **\<Customer>** element.</span></span> <span data-ttu-id="aaed2-125">Il file di dati XML contiene un **\<AllCustomers>** tag radice, che non è descritto nello schema, che racchiude tutti gli **\<Customer>** elementi:</span><span class="sxs-lookup"><span data-stu-id="aaed2-125">The XML data file has an **\<AllCustomers>** root tag (which is not described in the schema) that encloses all the **\<Customer>** elements:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
      <Customer>...</Customer>  
       ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="aaed2-126">In questo caso, il caricamento bulk XML ignora l' **\<AllCustomers>** elemento e inizia il mapping nell' **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="aaed2-126">In this case, XML Bulk Load ignores the **\<AllCustomers>** element and begins mapping at the **\<Customer>** element.</span></span> <span data-ttu-id="aaed2-127">Il caricamento bulk XML ignora gli elementi non descritti nello schema ma che sono presenti nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="aaed2-127">XML Bulk Load ignores the elements that are not described in the schema but are present in the XML document.</span></span>  
  
     <span data-ttu-id="aaed2-128">Si consideri un altro file di dati di origine XML contenente **\<Order>** elementi.</span><span class="sxs-lookup"><span data-stu-id="aaed2-128">Consider another XML source data file that contains **\<Order>** elements.</span></span> <span data-ttu-id="aaed2-129">Tali elementi non vengono descritti nello schema di mapping:</span><span class="sxs-lookup"><span data-stu-id="aaed2-129">These elements are not described in the mapping schema:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="aaed2-130">Questi elementi vengono ignorati dal caricamento bulk XML **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="aaed2-130">XML Bulk Load ignores these **\<Order>** elements.</span></span> <span data-ttu-id="aaed2-131">Tuttavia, se si utilizza l' `sql:overflow-field` annotazione nello schema per identificare una colonna come colonna di overflow, il caricamento bulk XML archivia tutti i dati non utilizzati in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="aaed2-131">But if you use the `sql:overflow-field`annotation in the schema to identify a column as an overflow column, XML Bulk Load stores all unconsumed data in this column.</span></span>  
  
-   <span data-ttu-id="aaed2-132">Le sezioni CDATA e i riferimenti a entità vengono convertiti nei rispettivi equivalenti in formato stringa prima di essere archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="aaed2-132">CDATA sections and entity references are translated to their string equivalents before they are stored in the database.</span></span>  
  
     <span data-ttu-id="aaed2-133">In questo esempio una sezione CDATA esegue il wrapping del valore per l' **\<City>** elemento.</span><span class="sxs-lookup"><span data-stu-id="aaed2-133">In this example, a CDATA section wraps the value for the **\<City>** element.</span></span> <span data-ttu-id="aaed2-134">Il caricamento bulk XML estrae il valore stringa ("NY") prima di inserire l' **\<City>** elemento nel database.</span><span class="sxs-lookup"><span data-stu-id="aaed2-134">XML Bulk Load extracts the string value ("NY") before it inserts the **\<City>** element into the database.</span></span>  
  
    ```  
    <City><![CDATA[NY]]> </City>  
    ```  
  
     <span data-ttu-id="aaed2-135">Il caricamento bulk XML non mantiene i riferimenti alle entità.</span><span class="sxs-lookup"><span data-stu-id="aaed2-135">XML Bulk Load does not preserve entity references.</span></span>  
  
-   <span data-ttu-id="aaed2-136">Se lo schema di mapping specifica il valore predefinito per un attributo e i dati di origine XML non contengono tale attributo, il caricamento bulk XML utilizza il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="aaed2-136">If the mapping schema specifies the default value for an attribute and the XML source data does not contain that attribute, XML Bulk Load uses the default value.</span></span>  
  
     <span data-ttu-id="aaed2-137">Nello schema XDR di esempio seguente viene assegnato un valore predefinito all'attributo **hirete** :</span><span class="sxs-lookup"><span data-stu-id="aaed2-137">The following sample XDR schema assigns a default value to the **HireDate** attribute:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
  
       <ElementType name="Customers" sql:relation="Cust3" >  
          <AttributeType name="CustomerID" dt:type="int"  />  
          <AttributeType name="HireDate"  default="2000-01-01" />  
          <AttributeType name="Salary"   />  
  
          <attribute type="CustomerID" sql:field="CustomerID" />  
          <attribute type="HireDate"   sql:field="HireDate"  />  
          <attribute type="Salary"     sql:field="Salary"    />  
       </ElementType>  
    </Schema>  
    ```  
  
     <span data-ttu-id="aaed2-138">In questi dati XML non è presente l'attributo **Hiret** dal secondo **\<Customers>** elemento.</span><span class="sxs-lookup"><span data-stu-id="aaed2-138">In this XML data, the **HireDate** attribute is missing from the second **\<Customers>** element.</span></span> <span data-ttu-id="aaed2-139">Quando il caricamento bulk XML inserisce il secondo **\<Customers>** elemento nel database, utilizza il valore predefinito specificato nello schema.</span><span class="sxs-lookup"><span data-stu-id="aaed2-139">When XML Bulk Load inserts the second **\<Customers>** element into the database, it uses the default value that is specified in the schema.</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1" HireDate="1999-01-01" Salary="10000" />  
      <Customers CustomerID="2" Salary="10000" />  
    </ROOT>  
    ```  
  
-   <span data-ttu-id="aaed2-140">L'annotazione `sql:url-encode` non è supportata.</span><span class="sxs-lookup"><span data-stu-id="aaed2-140">The `sql:url-encode` annotation is not supported:</span></span>  
  
     <span data-ttu-id="aaed2-141">Non è possibile specificare un URL nei dati XML di input e prevedere che il caricamento bulk legga i dati da tale posizione.</span><span class="sxs-lookup"><span data-stu-id="aaed2-141">You cannot specify a URL in the XML data input and expect Bulk Load to read data from that location.</span></span>  
  
     <span data-ttu-id="aaed2-142">Vengono create le tabelle identificate nello schema di mapping (il database deve essere presente).</span><span class="sxs-lookup"><span data-stu-id="aaed2-142">The tables that are identified in the mapping schema are created (the database must exist).</span></span> <span data-ttu-id="aaed2-143">Se una o più tabelle sono già presenti nel database, la proprietà SGDropTables determina se le tabelle preesistenti devono essere eliminate e ricreate.</span><span class="sxs-lookup"><span data-stu-id="aaed2-143">If one or more of the tables already exists in the database, the SGDropTables property determines whether these preexisting tables are to be dropped and re-created.</span></span>  
  
-   <span data-ttu-id="aaed2-144">Se si specifica la proprietà SchemaGen, ad esempio SchemaGen = true, vengono create le tabelle identificate nello schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="aaed2-144">If you specify the SchemaGen property (for example, SchemaGen = true), the tables that are identified in the mapping schema are created.</span></span> <span data-ttu-id="aaed2-145">Tuttavia, SchemaGen non crea vincoli, ad esempio i vincoli PRIMARY KEY o FOREIGN KEY, in queste tabelle con un'unica eccezione: se i nodi XML che costituiscono la chiave primaria in una relazione sono definiti con un tipo XML di ID (ovvero `type="xsd:ID"` per XSD) e la proprietà SGUseID è impostata su true per SchemaGen, non solo le chiavi primarie vengono create dai nodi con ID tipizzato, ma le relazioni tra chiave primaria e chiave esterna vengono create dalle relazioni dello schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="aaed2-145">But SchemaGen does not create any constraints (such as the PRIMARY KEY/FOREIGN KEY constraints) on these tables with one exception: If the XML nodes that constitute the primary key in a relationship are defined as having an XML type of ID (that is, `type="xsd:ID"` for XSD) AND the SGUseID property is set to True for SchemaGen, then not only are primary keys created from the ID typed nodes, but primary key/foreign key relationships are created from mapping schema relationships.</span></span>  
  
-   <span data-ttu-id="aaed2-146">In SchemaGen non vengono utilizzati facet e estensioni dello schema XSD per generare lo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] schema relazionale.</span><span class="sxs-lookup"><span data-stu-id="aaed2-146">SchemaGen does not use XSD schema facets and extensions to generate the relational [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] schema.</span></span>  
  
-   <span data-ttu-id="aaed2-147">Se si specifica la proprietà SchemaGen (ad esempio, SchemaGen = true) per il caricamento bulk, verranno aggiornate solo le tabelle (e non le visualizzazioni di nome condiviso) specificate.</span><span class="sxs-lookup"><span data-stu-id="aaed2-147">If you specify the SchemaGen property (for example, SchemaGen = true) on Bulk Load, only tables (and not views of shared name) that are specified are updated.</span></span>  
  
-   <span data-ttu-id="aaed2-148">SchemaGen fornisce solo le funzionalità di base per la generazione dello schema relazionale da XSD con annotazioni.</span><span class="sxs-lookup"><span data-stu-id="aaed2-148">SchemaGen only provides basic functionality for generating the relational schema from annotated XSD.</span></span> <span data-ttu-id="aaed2-149">Se necessario, l'utente deve modificare manualmente le tabelle generate.</span><span class="sxs-lookup"><span data-stu-id="aaed2-149">The user should modify the generated tables manually, if needed.</span></span>  
  
-   <span data-ttu-id="aaed2-150">Quando tra le tabelle è presente più di una relazione, SchemaGen tenta di creare una singola relazione che include tutte le chiavi incluse tra le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="aaed2-150">Where more than relationship exists between tables,SchemaGen tries to create a single relationship that includes all the keys involved between the two tables.</span></span> <span data-ttu-id="aaed2-151">Questa limitazione può essere la causa di un errore [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaed2-151">This limitation might be the cause of a [!INCLUDE[tsql](../../../includes/tsql-md.md)] error.</span></span>  
  
-   <span data-ttu-id="aaed2-152">Quando si esegue il caricamento bulk di dati XML in un database, deve essere presente almeno un attributo o un elemento figlio nello schema di mapping mappato a una colonna del database.</span><span class="sxs-lookup"><span data-stu-id="aaed2-152">When you are bulk loading XML data into a database, there must be at least one attribute or child element in the mapping schema that is mapped to a database column.</span></span>  
  
-   <span data-ttu-id="aaed2-153">Se si inseriscono valori di data tramite il caricamento bulk XML, i valori devono essere specificati nel formato (-)AAAA-MM-GG((+-)FO).</span><span class="sxs-lookup"><span data-stu-id="aaed2-153">If you are inserting date values by using XML Bulk Load, the values must be specified in the (-)CCYY-MM-DD((+-)TZ) format.</span></span> <span data-ttu-id="aaed2-154">Si tratta del formato XSD standard per la data.</span><span class="sxs-lookup"><span data-stu-id="aaed2-154">This is the standard XSD format for the date.</span></span>  
  
-   <span data-ttu-id="aaed2-155">Alcuni flag della proprietà non sono compatibili con altri flag della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="aaed2-155">Some property flags are not compatible with other property flags.</span></span> <span data-ttu-id="aaed2-156">Il caricamento bulk, ad esempio, non supporta il flag `Ignoreduplicatekeys=true` utilizzato con `Keepidentity=false`.</span><span class="sxs-lookup"><span data-stu-id="aaed2-156">For example, bulk load does not support `Ignoreduplicatekeys=true` together with `Keepidentity=false`.</span></span> <span data-ttu-id="aaed2-157">Nel caso in cui `Keepidentity=false`, durante il caricamento bulk si prevede che il server generi i valori della chiave.</span><span class="sxs-lookup"><span data-stu-id="aaed2-157">When `Keepidentity=false`, bulk load expects the server to generate the key values.</span></span> <span data-ttu-id="aaed2-158">Nelle tabelle deve essere presente un vincolo `IDENTITY` sulla chiave.</span><span class="sxs-lookup"><span data-stu-id="aaed2-158">Tables should have an `IDENTITY` constraint on the key.</span></span> <span data-ttu-id="aaed2-159">Il server non genererà chiavi duplicate, il che significa che non c'è bisogno di impostare `Ignoreduplicatekeys` su `true`.</span><span class="sxs-lookup"><span data-stu-id="aaed2-159">The server will not generate duplicate keys, which means there is no need for `Ignoreduplicatekeys` to be set to `true`.</span></span> <span data-ttu-id="aaed2-160">`Ignoreduplicatekeys` deve essere impostato su `true` solo quando viene eseguito il caricamento di valori di chiave primaria dai dati in entrata in una tabella con righe ed è possibile un conflitto di valori di chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="aaed2-160">`Ignoreduplicatekeys` should be set to `true` only when uploading primary key values from the incoming data into a table that has rows and there is a potential for conflict of primary key values.</span></span>  
  
  
