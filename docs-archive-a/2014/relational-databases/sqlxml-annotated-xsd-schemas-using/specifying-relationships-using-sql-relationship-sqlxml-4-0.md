---
title: 'Definizione di relazioni tramite SQL: Relationship (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- parent attribute [SQLXML]
- element relationships [SQLXML]
- multiple element relationships
- attribute relationships [SQLXML]
- sql:relationship
- relationship chains [SQLXML]
- IDREF relationships [SQLXML]
- parent-child relationships [SQLXML]
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- relationships [SQLXML], specifying
- unnamed relationships
- ID relationships [SQLXML]
- hierarchical relationships [SQLXML]
- named relationships [SQLXML]
ms.assetid: 98820afa-74e1-4e62-b336-6111a3dede4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 42c703de9d564580eb0baa1349a45b193109c87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628604"
---
# <a name="specifying-relationships-using-sqlrelationship-sqlxml-40"></a><span data-ttu-id="c09f9-102">Definizione di relazioni tramite sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c09f9-102">Specifying Relationships Using sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="c09f9-103">Gli elementi in un documento XML possono essere correlati.</span><span class="sxs-lookup"><span data-stu-id="c09f9-103">The elements in an XML document can be related.</span></span> <span data-ttu-id="c09f9-104">È possibile nidificare gerarchicamente gli elementi e specificare relazioni ID, IDREF o IDREFS tra gli elementi.</span><span class="sxs-lookup"><span data-stu-id="c09f9-104">The elements can be nested hierarchically, and ID, IDREF, or IDREFS relationships can be specified between the elements.</span></span>  
  
 <span data-ttu-id="c09f9-105">In uno schema XSD, ad esempio, un **\<Customer>** elemento contiene **\<Order>** elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="c09f9-105">For example, in an XSD schema, a **\<Customer>** element contains **\<Order>** child elements.</span></span> <span data-ttu-id="c09f9-106">Quando viene eseguito il mapping dello schema al database AdventureWorks, l'elemento viene mappato **\<Customer>** alla tabella Sales. Customer e l' **\<Order>** elemento viene mappato alla tabella Sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="c09f9-106">When the schema is mapped to the AdventureWorks database, the **\<Customer>** element maps to the Sales.Customer table and the **\<Order>** element maps to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="c09f9-107">Queste tabelle sottostanti, Sales.Customer e Sales.SalesOrderHeader, sono correlate in quanto i clienti effettuano ordini.</span><span class="sxs-lookup"><span data-stu-id="c09f9-107">These underlying tables, Sales.Customer and Sales.SalesOrderHeader, are related because customers place orders.</span></span> <span data-ttu-id="c09f9-108">L'elemento CustomerID nella tabella Sales.SalesOrderHeader è una chiave esterna che fa riferimento alla chiave primaria CustomerID nella tabella Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="c09f9-108">The CustomerID in the Sales.SalesOrderHeader table is a foreign key referring to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="c09f9-109">È possibile stabilire queste relazioni fra elementi dello schema di mapping tramite l'annotazione `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="c09f9-109">You can establish these relationships among mapping schema elements by using the `sql:relationship` annotation.</span></span>  
  
 <span data-ttu-id="c09f9-110">Nello schema XSD con annotazioni l'annotazione `sql:relationship` viene utilizzata per nidificare gerarchicamente gli elementi dello schema, sulla base di relazioni chiave primaria/chiave esterna tra le tabelle sottostanti a cui viene eseguito il mapping degli elementi.</span><span class="sxs-lookup"><span data-stu-id="c09f9-110">In the annotated XSD schema, the `sql:relationship` annotation is used to nest the schema elements hierarchically, on the basis of primary key and foreign key relationships among the underlying tables to which the elements map.</span></span> <span data-ttu-id="c09f9-111">Nello specificare l'annotazione `sql:relationship`, è necessario identificare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c09f9-111">In specifying the `sql:relationship` annotation, you must identify the following:</span></span>  
  
-   <span data-ttu-id="c09f9-112">Tabella padre (Sales.Customer) e tabella figlio (Sales.SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="c09f9-112">The parent table (Sales.Customer) and the child table (Sales.SalesOrderHeader).</span></span>  
  
-   <span data-ttu-id="c09f9-113">Colonna o colonne che costituiscono la relazione tra le tabelle padre e figlio,</span><span class="sxs-lookup"><span data-stu-id="c09f9-113">The column or columns that compose the relationship between the parent and child tables.</span></span> <span data-ttu-id="c09f9-114">ad esempio la colonna CustomerID, visualizzata sia nella tabella padre che nella tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="c09f9-114">For example, the CustomerID column, which appears in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="c09f9-115">Queste informazioni vengono utilizzate per generare la gerarchia appropriata.</span><span class="sxs-lookup"><span data-stu-id="c09f9-115">This information is used to generate the proper hierarchy.</span></span>  
  
 <span data-ttu-id="c09f9-116">Per fornire i nomi di tabella e le necessarie informazioni sull'unione in join, nell'annotazione `sql:relationship` vengono specificati gli attributi seguenti.</span><span class="sxs-lookup"><span data-stu-id="c09f9-116">To provide the table names and the necessary join information, the following attributes are specified on the `sql:relationship` annotation.</span></span> <span data-ttu-id="c09f9-117">Questi attributi sono validi solo con l' **\<sql:relationship>** elemento:</span><span class="sxs-lookup"><span data-stu-id="c09f9-117">These attributes are valid only with the **\<sql:relationship>** element:</span></span>  
  
 <span data-ttu-id="c09f9-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c09f9-118">**Name**</span></span>  
 <span data-ttu-id="c09f9-119">Specifica il nome univoco della relazione,</span><span class="sxs-lookup"><span data-stu-id="c09f9-119">Specifies the unique name of the relationship.</span></span>  
  
 <span data-ttu-id="c09f9-120">**Parent**</span><span class="sxs-lookup"><span data-stu-id="c09f9-120">**Parent**</span></span>  
 <span data-ttu-id="c09f9-121">Specifica la relazione padre (tabella).</span><span class="sxs-lookup"><span data-stu-id="c09f9-121">Specifies the parent relation (table).</span></span> <span data-ttu-id="c09f9-122">Si tratta di un attributo facoltativo. Se non è specificato, il nome della tabella padre viene ottenuto dalle informazioni presenti nella gerarchia padre-figlio del documento.</span><span class="sxs-lookup"><span data-stu-id="c09f9-122">This is an optional attribute; if the attribute is not specified, the parent table name is obtained from information in the child hierarchy in the document.</span></span> <span data-ttu-id="c09f9-123">Se lo schema specifica due gerarchie padre-figlio che utilizzano gli stessi **\<sql:relationship>** elementi padre ma diversi, non è necessario specificare l'attributo parent in **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="c09f9-123">If the schema specifies two parent-child hierarchies that use the same **\<sql:relationship>** but different parent elements, you do not specify the parent attribute in **\<sql:relationship>**.</span></span> <span data-ttu-id="c09f9-124">Queste informazioni vengono ottenute dalla gerarchia nello schema.</span><span class="sxs-lookup"><span data-stu-id="c09f9-124">This information is obtained from the hierarchy in the schema.</span></span>  
  
 <span data-ttu-id="c09f9-125">**parent-key**</span><span class="sxs-lookup"><span data-stu-id="c09f9-125">**parent-key**</span></span>  
 <span data-ttu-id="c09f9-126">Specifica la chiave padre dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="c09f9-126">Specifies the parent key of the parent.</span></span> <span data-ttu-id="c09f9-127">Se la chiave padre è costituita da più colonne, i valori vengono specificati con uno spazio tra l'uno e l'altro.</span><span class="sxs-lookup"><span data-stu-id="c09f9-127">If the parent key is composed of multiple columns, values are specified with a space between them.</span></span> <span data-ttu-id="c09f9-128">Tra i valori specificati per la chiave multicolonna e la chiave figlio corrispondente viene applicato un mapping posizionale.</span><span class="sxs-lookup"><span data-stu-id="c09f9-128">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding child key.</span></span>  
  
 <span data-ttu-id="c09f9-129">**Figlio**</span><span class="sxs-lookup"><span data-stu-id="c09f9-129">**Child**</span></span>  
 <span data-ttu-id="c09f9-130">Specifica la relazione figlio (tabella).</span><span class="sxs-lookup"><span data-stu-id="c09f9-130">Specifies the child relation (table).</span></span>  
  
 <span data-ttu-id="c09f9-131">**child-key**</span><span class="sxs-lookup"><span data-stu-id="c09f9-131">**child-key**</span></span>  
 <span data-ttu-id="c09f9-132">Specifica la chiave figlio nell'elemento figlio che fa riferimento alla chiave padre nell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="c09f9-132">Specifies the child key in the child referring to parent-key in parent.</span></span> <span data-ttu-id="c09f9-133">Se la chiave figlio è costituita da più attributi (colonne), i valori di chiave figlio vengono specificati con uno spazio tra l'uno e l'altro.</span><span class="sxs-lookup"><span data-stu-id="c09f9-133">If the child key is composed of multiple attributes (columns), the child-key values are specified with a space between them.</span></span> <span data-ttu-id="c09f9-134">Tra i valori specificati per la chiave multicolonna e la chiave padre corrispondente viene applicato un mapping posizionale.</span><span class="sxs-lookup"><span data-stu-id="c09f9-134">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding parent key.</span></span>  
  
 <span data-ttu-id="c09f9-135">**Metodo inverso**</span><span class="sxs-lookup"><span data-stu-id="c09f9-135">**Inverse**</span></span>  
 <span data-ttu-id="c09f9-136">Questo attributo specificato in **\<sql:relationship>** viene utilizzato dagli updategram.</span><span class="sxs-lookup"><span data-stu-id="c09f9-136">This attribute specified on **\<sql:relationship>** is used by updategrams.</span></span> <span data-ttu-id="c09f9-137">Per ulteriori informazioni, vedere [specifica dell'attributo SQL: inverse in SQL: Relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c09f9-137">For more information, see [Specifying the sql:inverse Attribute on sql:relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="c09f9-138">L' `sql:key-fields` annotazione deve essere specificata in un elemento che contiene un elemento figlio, che dispone di un oggetto **\<sql:relationship>** definito tra l'elemento e il figlio e che non fornisce la chiave primaria della tabella specificata nell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="c09f9-138">The `sql:key-fields` annotation must be specified in an element that contains a child element, that has a **\<sql:relationship>** defined between the element and the child, and that does not provide the primary key of the table specified in the parent element.</span></span> <span data-ttu-id="c09f9-139">Anche se lo schema non specifica **\<sql:relationship>** , è necessario specificare `sql:key-fields` per produrre la gerarchia appropriata.</span><span class="sxs-lookup"><span data-stu-id="c09f9-139">Even if the schema does not specify **\<sql:relationship>**, you must specify `sql:key-fields` to produce the proper hierarchy.</span></span> <span data-ttu-id="c09f9-140">Per ulteriori informazioni, vedere [identificazione delle colonne chiave mediante SQL: key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c09f9-140">For more information, see [Identifying Key Columns by Using sql:key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="c09f9-141">Per produrre la nidificazione appropriata nel risultato, è consigliabile specificare `sql:key-fields` in tutti gli schemi.</span><span class="sxs-lookup"><span data-stu-id="c09f9-141">To produce proper nesting in the result, it is recommended that `sql:key-fields` are specified in all schemas.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c09f9-142">Esempi</span><span class="sxs-lookup"><span data-stu-id="c09f9-142">Examples</span></span>  
 <span data-ttu-id="c09f9-143">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="c09f9-143">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="c09f9-144">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="c09f9-144">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelationship-annotation-on-an-element"></a><span data-ttu-id="c09f9-145">R.</span><span class="sxs-lookup"><span data-stu-id="c09f9-145">A.</span></span> <span data-ttu-id="c09f9-146">Specifica dell'annotazione sql:relationship in un elemento</span><span class="sxs-lookup"><span data-stu-id="c09f9-146">Specifying the sql:relationship annotation on an element</span></span>  
 <span data-ttu-id="c09f9-147">Nello schema XSD con annotazioni seguente sono inclusi **\<Customer>** **\<Order>** gli elementi e.</span><span class="sxs-lookup"><span data-stu-id="c09f9-147">The following annotated XSD schema includes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="c09f9-148">L' **\<Order>** elemento è un elemento figlio dell' **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="c09f9-148">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span>  
  
 <span data-ttu-id="c09f9-149">Nello schema l' `sql:relationship` annotazione viene specificata nell' **\<Order>** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="c09f9-149">In the schema, the `sql:relationship` annotation is specified on the **\<Order>** child element.</span></span> <span data-ttu-id="c09f9-150">La relazione stessa è definita nell' **\<xsd:appinfo>** elemento.</span><span class="sxs-lookup"><span data-stu-id="c09f9-150">The relationship itself is defined in the **\<xsd:appinfo>** element.</span></span>  
  
 <span data-ttu-id="c09f9-151">L' **\<relationship>** elemento identifica CustomerID nella tabella Sales. SalesOrderHeader come chiave esterna che fa riferimento alla chiave primaria CustomerID nella tabella Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="c09f9-151">The **\<relationship>** element identifies CustomerID in the Sales.SalesOrderHeader table as a foreign key that refers to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="c09f9-152">Gli ordini appartenenti a un cliente, pertanto, vengono visualizzati come elemento figlio di tale **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="c09f9-152">Therefore, orders that belong to a customer appear as a child element of that **\<Customer>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                    sql:relationship="CustOrders" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="c09f9-153">Lo schema precedente utilizza una relazione denominata.</span><span class="sxs-lookup"><span data-stu-id="c09f9-153">The previous schema uses a named relationship.</span></span> <span data-ttu-id="c09f9-154">È inoltre possibile specificare una relazione priva di nome.</span><span class="sxs-lookup"><span data-stu-id="c09f9-154">You can also specify an unnamed relationship.</span></span> <span data-ttu-id="c09f9-155">I risultati sono identici.</span><span class="sxs-lookup"><span data-stu-id="c09f9-155">The results are same.</span></span>  
  
 <span data-ttu-id="c09f9-156">Di seguito viene fornito lo schema corretto in cui è specificata una relazione priva di nome:</span><span class="sxs-lookup"><span data-stu-id="c09f9-156">This is the revised schema in which an unnamed relationship is specified:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer"  type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader">  
           <xsd:annotation>  
            <xsd:appinfo>  
              <sql:relationship   
                parent="Sales.Customer"  
                parent-key="CustomerID"  
                child="Sales.SalesOrderHeader"  
                child-key="CustomerID" />  
            </xsd:appinfo>  
           </xsd:annotation>  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c09f9-157">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="c09f9-157">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c09f9-158">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c09f9-158">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c09f9-159">Salvare il file con il nome sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-159">Save the file as sql-relationship.xml.</span></span>  
  
2.  <span data-ttu-id="c09f9-160">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c09f9-160">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="c09f9-161">Salvare il file con il nome sql-relationshipT.xml nella stessa directory in cui è stato salvato il file sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-161">Save the file as sql-relationshipT.xml in the same directory where you saved sql-relationship.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-relationship.xml">  
            /Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c09f9-162">Il percorso di directory specificato per lo schema di mapping (sql-relationship.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-162">The directory path specified for the mapping schema (sql-relationship.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c09f9-163">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c09f9-163">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-relationship.xml"  
    ```  
  
3.  <span data-ttu-id="c09f9-164">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-164">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c09f9-165">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c09f9-165">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c09f9-166">Set di risultati:</span><span class="sxs-lookup"><span data-stu-id="c09f9-166">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1">   
    <Order OrderID="43860" CustomerID="1" />   
    <Order OrderID="44501" CustomerID="1" />   
    <Order OrderID="45283" CustomerID="1" />   
    <Order OrderID="46042" CustomerID="1" />   
  </Customer>   
</ROOT>  
```  
  
### <a name="b-specifying-a-relationship-chain"></a><span data-ttu-id="c09f9-167">B.</span><span class="sxs-lookup"><span data-stu-id="c09f9-167">B.</span></span> <span data-ttu-id="c09f9-168">Definizione di una catena di relazioni</span><span class="sxs-lookup"><span data-stu-id="c09f9-168">Specifying a relationship chain</span></span>  
 <span data-ttu-id="c09f9-169">Per questo esempio, si supponga di voler fare in modo che il documento XML seguente utilizzi dati ottenuti dal database di AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="c09f9-169">For this example, assume that you want the following XML document using data obtained from the AdventureWorks database:</span></span>  
  
```  
<Order SalesOrderID="43659">  
  <Product Name="Mountain Bike Socks, M"/>   
  <Product Name="Sport-100 Helmet, Blue"/>  
  ...  
</Order>  
...  
```  
  
 <span data-ttu-id="c09f9-170">Per ogni ordine nella tabella Sales. SalesOrderHeader, il documento XML include un **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="c09f9-170">For each order in the Sales.SalesOrderHeader table, the XML document has one **\<Order>** element.</span></span> <span data-ttu-id="c09f9-171">E ogni **\<Order>** elemento ha un elenco di **\<Product>** elementi figlio, uno per ogni prodotto richiesto nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c09f9-171">And each **\<Order>** element has a list of **\<Product>** child elements, one for each product requested in the order.</span></span>  
  
 <span data-ttu-id="c09f9-172">Per specificare uno schema XSD che produrrà questa gerarchia, è necessario definire due relazioni: OrderOD e ODProduct.</span><span class="sxs-lookup"><span data-stu-id="c09f9-172">To specify an XSD schema that will produce this hierarchy, you must specify two relationships: OrderOD and ODProduct.</span></span> <span data-ttu-id="c09f9-173">La relazione OrderOD specifica la relazione padre-figlio tra le tabelle Sales.SalesOrderHeader e Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="c09f9-173">The OrderOD relationship specifies the parent-child relationship between the Sales.SalesOrderHeader and Sales.SalesOrderDetail tables.</span></span> <span data-ttu-id="c09f9-174">La relazione ODProduct specifica la relazione tra le tabelle Sales.SalesOrderDetail e Production.Product.</span><span class="sxs-lookup"><span data-stu-id="c09f9-174">The ODProduct relationship specifies the relationship between the Sales.SalesOrderDetail and Production.Product tables.</span></span>  
  
 <span data-ttu-id="c09f9-175">Nello schema seguente l' `msdata:relationship` annotazione nell' **\<Product>** elemento specifica due valori: OrderOD e ODProduct.</span><span class="sxs-lookup"><span data-stu-id="c09f9-175">In the following schema, the `msdata:relationship` annotation on the **\<Product>** element specifies two values: OrderOD and ODProduct.</span></span> <span data-ttu-id="c09f9-176">L'ordine in cui sono elencati gli attributi è importante.</span><span class="sxs-lookup"><span data-stu-id="c09f9-176">The order in which these values are specified is important.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <msdata:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  
    <msdata:relationship name="ODProduct"  
          parent="Sales.SalesOrderDetail"  
          parent-key="ProductID"  
          child="Production.Product"  
          child-key="ProductID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID"  
                     msdata:relationship="OrderOD ODProduct">  
          <xsd:complexType>  
             <xsd:attribute name="Name" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="c09f9-177">Anziché specificare una relazione denominata, è possibile specificare una relazione anonima.</span><span class="sxs-lookup"><span data-stu-id="c09f9-177">Instead of specifying a named relationship, you can specify an anonymous relationship.</span></span> <span data-ttu-id="c09f9-178">In questo caso, l'intero contenuto di **\<annotation>** ... **\</annotation>** , che descrive le due relazioni, viene visualizzato come elemento figlio di **\<Product>** .</span><span class="sxs-lookup"><span data-stu-id="c09f9-178">In this case, the entire contents of **\<annotation>**...**\</annotation>**, which describes the two relationships, appear as a child element of **\<Product>**.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID" >  
         <xsd:annotation>  
          <xsd:appinfo>  
           <msdata:relationship   
               parent="Sales.SalesOrderHeader"  
               parent-key="SalesOrderID"  
               child="Sales.SalesOrderDetail"  
               child-key="SalesOrderID" />  
  
           <msdata:relationship   
               parent="Sales.SalesOrderDetail"  
               parent-key="ProductID"  
               child="Production.Product"  
               child-key="ProductID" />  
         </xsd:appinfo>  
       </xsd:annotation>  
       <xsd:complexType>  
          <xsd:attribute name="Name" type="xsd:string" />  
       </xsd:complexType>  
     </xsd:element>  
   </xsd:sequence>  
   <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
  </xsd:complexType>  
 </xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c09f9-179">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="c09f9-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c09f9-180">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c09f9-180">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c09f9-181">Salvare il file con il nome relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-181">Save the file as relationshipChain.xml.</span></span>  
  
2.  <span data-ttu-id="c09f9-182">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c09f9-182">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="c09f9-183">Salvare il file con il nome relationshipChainT.xml nella stessa directory in cui è stato salvato il file relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-183">Save the file as relationshipChainT.xml in the same directory where you saved relationshipChain.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationshipChain.xml">  
            /Order  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c09f9-184">Il percorso di directory specificato per lo schema di mapping (relationshipChain.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-184">The directory path specified for the mapping schema (relationshipChain.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c09f9-185">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c09f9-185">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationshipChain.xml"  
    ```  
  
3.  <span data-ttu-id="c09f9-186">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-186">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c09f9-187">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c09f9-187">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c09f9-188">Set di risultati:</span><span class="sxs-lookup"><span data-stu-id="c09f9-188">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Order SalesOrderID="43659">  
    <Product Name="Mountain Bike Socks, M" />   
    <Product Name="Sport-100 Helmet, Blue" />   
    <Product Name="AWC Logo Cap" />   
    <Product Name="Long-Sleeve Logo Jersey, M" />   
    <Product Name="Long-Sleeve Logo Jersey, XL" />   
    ...  
  </Order>  
  ...  
</ROOT>  
```  
  
### <a name="c-specifying-the-relationship-annotation-on-an-attribute"></a><span data-ttu-id="c09f9-189">C.</span><span class="sxs-lookup"><span data-stu-id="c09f9-189">C.</span></span> <span data-ttu-id="c09f9-190">Definizione dell'annotazione sql:relationship in un attributo</span><span class="sxs-lookup"><span data-stu-id="c09f9-190">Specifying the relationship annotation on an attribute</span></span>  
 <span data-ttu-id="c09f9-191">Lo schema in questo esempio include un \<Customer> elemento con un \<CustomerID> elemento figlio e un attributo OrderID di tipo IDREFS.</span><span class="sxs-lookup"><span data-stu-id="c09f9-191">The schema in this example includes a \<Customer> element with a \<CustomerID> child element and an OrderIDList attribute of IDREFS type.</span></span> <span data-ttu-id="c09f9-192">L' \<Customer> elemento viene mappato alla tabella Sales. Customer nel database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c09f9-192">The \<Customer> element maps to the Sales.Customer table in the AdventureWorks database.</span></span> <span data-ttu-id="c09f9-193">Per impostazione predefinita, l'ambito di questo mapping si applica a tutti gli elementi o attributi figlio, a meno che non `sql:relation` sia specificato nell'attributo o nell'elemento figlio. in questo caso, è necessario definire la relazione chiave primaria/chiave esterna appropriata utilizzando l' \<relationship> elemento.</span><span class="sxs-lookup"><span data-stu-id="c09f9-193">By default, the scope of this mapping applies to all the child elements or attributes unless `sql:relation` is specified on the child element or attribute, in which case, the appropriate primary-key/foreign-key relationship must be defined using the \<relationship> element.</span></span> <span data-ttu-id="c09f9-194">L'elemento o l'attributo figlio, che specifica la tabella diversa utilizzando l'annotazione `relation`, deve specificare anche l'annotazione `relationship`.</span><span class="sxs-lookup"><span data-stu-id="c09f9-194">And the child element or attribute, which specifies the different table using the `relation` annotation, must also specify the `relationship` annotation.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="CustomerID"   type="xsd:string" />   
     </xsd:sequence>  
     <xsd:attribute name="OrderIDList"   
                     type="xsd:IDREFS"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:field="SalesOrderID"  
                     sql:relationship="CustOrders" >  
        </xsd:attribute>  
    </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c09f9-195">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="c09f9-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c09f9-196">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c09f9-196">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c09f9-197">Salvare il file con il nome relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-197">Save the file as relationship-on-attribute.xml.</span></span>  
  
2.  <span data-ttu-id="c09f9-198">Copiare il modello seguente e incollarlo in un file.</span><span class="sxs-lookup"><span data-stu-id="c09f9-198">Copy the following template and paste it into a file.</span></span> <span data-ttu-id="c09f9-199">Salvare il file con il nome relationship-on-attributeT.xml nella stessa directory in cui è stato salvato il file relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-199">Save the file as relationship-on-attributeT.xml in the same directory where you saved relationship-on-attribute.xml.</span></span> <span data-ttu-id="c09f9-200">La query nel modello seleziona un cliente con CustomerID 1.</span><span class="sxs-lookup"><span data-stu-id="c09f9-200">The query in the template selects a customer with the CustomerID of 1.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-on-attribute.xml">  
        /Customer[CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c09f9-201">Il percorso di directory specificato per lo schema di mapping (relationship-on-attribute.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-201">The directory path specified for the mapping schema (relationship-on-attribute.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c09f9-202">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c09f9-202">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-on-attribute.xml"  
    ```  
  
3.  <span data-ttu-id="c09f9-203">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-203">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c09f9-204">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c09f9-204">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c09f9-205">Set di risultati:</span><span class="sxs-lookup"><span data-stu-id="c09f9-205">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer OrderIDList="43860 44501 45283 46042">  
    <CustomerID>1</CustomerID>   
  </Customer>  
</ROOT>  
```  
  
### <a name="d-specifying-sqlrelationship-on-multiple-elements"></a><span data-ttu-id="c09f9-206">D.</span><span class="sxs-lookup"><span data-stu-id="c09f9-206">D.</span></span> <span data-ttu-id="c09f9-207">Specifica di sql:relationship in più elementi</span><span class="sxs-lookup"><span data-stu-id="c09f9-207">Specifying sql:relationship on multiple elements</span></span>  
 <span data-ttu-id="c09f9-208">In questo esempio lo schema XSD con annotazioni contiene **\<Customer>** gli **\<Order>** elementi, e **\<OrderDetail>** .</span><span class="sxs-lookup"><span data-stu-id="c09f9-208">In this example, the annotated XSD schema contains the **\<Customer>**, **\<Order>**, and **\<OrderDetail>** elements.</span></span>  
  
 <span data-ttu-id="c09f9-209">L' **\<Order>** elemento è un elemento figlio dell' **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="c09f9-209">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span> <span data-ttu-id="c09f9-210">**\<sql:relationship>** viene specificato nell' **\<Order>** elemento figlio. gli ordini appartenenti a un cliente, pertanto, vengono visualizzati come elementi figlio di **\<Customer>** .</span><span class="sxs-lookup"><span data-stu-id="c09f9-210">**\<sql:relationship>** is specified on the **\<Order>** child element; therefore, orders that belong to a customer appear as child elements of **\<Customer>**.</span></span>  
  
 <span data-ttu-id="c09f9-211">L' **\<Order>** elemento include l' **\<OrderDetail>** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="c09f9-211">The **\<Order>** element includes the **\<OrderDetail>** child element.</span></span> <span data-ttu-id="c09f9-212">**\<sql:relationship>** viene specificato nell' **\<OrderDetail>** elemento figlio, quindi i dettagli dell'ordine relativi a un ordine vengono visualizzati come elementi figlio di tale **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="c09f9-212">**\<sql:relationship>** is specified on **\<OrderDetail>** child element, so the order details that pertain to an order appear as child elements of that **\<Order>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
        parent="Sales.Customer"  
        parent-key="CustomerID"  
        child="Sales.SalesOrderHeader"  
        child-key="CustomerID" />  
  
    <sql:relationship name="OrderOrderDetail"  
        parent="Sales.SalesOrderHeader"  
        parent-key="SalesOrderID"  
        child="Sales.SalesOrderDetail"  
        child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"    
              sql:relationship="CustOrders" maxOccurs="unbounded" >  
          <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OrderDetail"   
                             sql:relation="Sales.SalesOrderDetail"   
                             sql:relationship="OrderOrderDetail"   
                             maxOccurs="unbounded" >  
                  <xsd:complexType>  
                    <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                    <xsd:attribute name="ProductID" type="xsd:string" />  
                    <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  </xsd:complexType>  
                </xsd:element>  
              </xsd:sequence>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c09f9-213">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="c09f9-213">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c09f9-214">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c09f9-214">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c09f9-215">Salvare il file con il nome relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-215">Save the file as relationship-multiple-elements.xml.</span></span>  
  
2.  <span data-ttu-id="c09f9-216">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c09f9-216">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="c09f9-217">Salvare il file con il nome relationship-multiple-elementsT.xml nella stessa directory in cui è stato salvato il file relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-217">Save the file as relationship-multiple-elementsT.xml in the same directory where you saved relationship-multiple-elements.xml.</span></span> <span data-ttu-id="c09f9-218">La query nel modello restituisce informazioni sull'ordine per un cliente con CustomerID 1 e SalesOrderID 43860.</span><span class="sxs-lookup"><span data-stu-id="c09f9-218">The query in the template returns order information for a customer with the CustomerID of 1 and SalesOrderID of 43860.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-multiple-elements.xml">  
        /Customer[@CustomerID=1]/Order[@SalesOrderID=43860]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c09f9-219">Il percorso di directory specificato per lo schema di mapping (relationship-multiple-elements.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-219">The directory path specified for the mapping schema (relationship-multiple-elements.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c09f9-220">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c09f9-220">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-multiple-elements.xml"  
    ```  
  
3.  <span data-ttu-id="c09f9-221">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-221">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c09f9-222">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c09f9-222">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c09f9-223">Set di risultati:</span><span class="sxs-lookup"><span data-stu-id="c09f9-223">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1">  
     <OrderDetail SalesOrderID="43860" ProductID="761" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="770" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="758" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="765" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="762" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="768" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="763" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="756" OrderQty="1" />   
  </Order>  
</ROOT>  
```  
  
### <a name="e-specifying-the-sqlrelationship-without-the-parent-attribute"></a><span data-ttu-id="c09f9-224">E.</span><span class="sxs-lookup"><span data-stu-id="c09f9-224">E.</span></span> <span data-ttu-id="c09f9-225">Specifica \<sql:relationship> senza l'attributo parent</span><span class="sxs-lookup"><span data-stu-id="c09f9-225">Specifying the \<sql:relationship> without the parent attribute</span></span>  
 <span data-ttu-id="c09f9-226">In questo esempio viene illustrato come specificare l'oggetto **\<sql:relationship>** senza l'attributo **padre** .</span><span class="sxs-lookup"><span data-stu-id="c09f9-226">This example illustrates specifying the **\<sql:relationship>** without the **parent** attribute.</span></span> <span data-ttu-id="c09f9-227">Si supponga, ad esempio, di disporre delle tabelle relative ai dipendenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c09f9-227">For example, assume you have the following employee tables:</span></span>  
  
```  
Emp1(SalesPersonID, FirstName, LastName, ReportsTo)  
Emp2(SalesPersonID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="c09f9-228">Nella vista XML seguente sono presenti **\<Emp1>** gli **\<Emp2>** elementi e che vengono mappati alle tabelle Sales. Emp1 e Sales. emp2:</span><span class="sxs-lookup"><span data-stu-id="c09f9-228">The following XML view has the **\<Emp1>** and **\<Emp2>** elements mapping to the Sales.Emp1 and Sales.Emp2 tables:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="EmpOrders"  
          parent-key="SalesPersonID"  
          child="Sales.SalesOrderHeader"  
          child-key="SalesPersonID" />  
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Emp1" sql:relation="Sales.Emp1" type="EmpType" />  
  <xsd:element name="Emp2" sql:relation="Sales.Emp2" type="EmpType" />  
   <xsd:complexType name="EmpType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:relationship="EmpOrders" >  
          <xsd:complexType>  
             <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesPersonID"   type="xsd:integer" />   
        <xsd:attribute name="LastName"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="c09f9-229">Nello schema, sia l' **\<Emp1>** elemento sia l' **\<Emp2>** elemento sono di tipo `EmpType` .</span><span class="sxs-lookup"><span data-stu-id="c09f9-229">In the schema, both the **\<Emp1>** element and **\<Emp2>** element are of type `EmpType`.</span></span> <span data-ttu-id="c09f9-230">Il tipo `EmpType` descrive un **\<Order>** elemento figlio e l'oggetto corrispondente **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="c09f9-230">The type `EmpType` describes an **\<Order>** child element and the corresponding **\<sql:relationship>**.</span></span> <span data-ttu-id="c09f9-231">In questo caso, non esiste un singolo elemento padre che possa essere identificato in utilizzando **\<sql:relationship>** l'attributo **padre** .</span><span class="sxs-lookup"><span data-stu-id="c09f9-231">In this case, there is no single parent that can be identified in **\<sql:relationship>** by using the **parent** attribute.</span></span> <span data-ttu-id="c09f9-232">In questa situazione non si specifica l'attributo **Parent** in. **\<sql:relationship>** le informazioni sugli attributi **padre** vengono ottenute dalla gerarchia nello schema.</span><span class="sxs-lookup"><span data-stu-id="c09f9-232">In this situation, you don't specify the **parent** attribute in **\<sql:relationship>**; the **parent** attribute information is obtained from the hierarchy in the schema.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c09f9-233">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="c09f9-233">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c09f9-234">Creare le tabelle seguenti nel database AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="c09f9-234">Create these tables in the AdventureWorks database:</span></span>  
  
    ```  
    USE AdventureWorks  
    CREATE TABLE Sales.Emp1 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    CREATE TABLE Sales.Emp2 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    ```  
  
2.  <span data-ttu-id="c09f9-235">Aggiungere i dati di esempio seguenti nelle tabelle:</span><span class="sxs-lookup"><span data-stu-id="c09f9-235">Add this sample data in the tables:</span></span>  
  
    ```  
    INSERT INTO Sales.Emp1 values (279, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Sales.Emp1 values (282, 'Andrew', 'Fuller',1)  
    INSERT INTO Sales.Emp1 values (276, 'Janet', 'Leverling',1)  
    INSERT INTO Sales.Emp2 values (277, 'Margaret', 'Peacock',3)  
    INSERT INTO Sales.Emp2 values (283, 'Steven', 'Devolio',4)  
    INSERT INTO Sales.Emp2 values (275, 'Nancy', 'Buchanan',5)  
    INSERT INTO Sales.Emp2 values (281, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="c09f9-236">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c09f9-236">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c09f9-237">Salvare il file con il nome relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-237">Save the file as relationship-noparent.xml.</span></span>  
  
4.  <span data-ttu-id="c09f9-238">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c09f9-238">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="c09f9-239">Salvare il file con il nome relationship-noparentT.xml nella stessa directory in cui è stato salvato il file relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="c09f9-239">Save the file as relationship-noparentT.xml in the same directory where you saved relationship-noparent.xml.</span></span> <span data-ttu-id="c09f9-240">La query nel modello seleziona tutti gli \<Emp1> elementi (pertanto, l'elemento padre è Emp1).</span><span class="sxs-lookup"><span data-stu-id="c09f9-240">The query in the template selects all the \<Emp1> elements (therefore, the parent is Emp1).</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationship-noparent.xml">  
            /Emp1  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c09f9-241">Il percorso di directory specificato per lo schema di mapping (relationship-noparent.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-241">The directory path specified for the mapping schema (relationship-noparent.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c09f9-242">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c09f9-242">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-noparent.xml"  
    ```  
  
5.  <span data-ttu-id="c09f9-243">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="c09f9-243">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c09f9-244">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c09f9-244">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c09f9-245">Di seguito viene fornito un set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="c09f9-245">Here is a partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<Emp1 SalesPersonID="276" LastName="Leverling">  
  <Order SalesOrderID="43663" CustomerID="510" />   
  <Order SalesOrderID="43666" CustomerID="511" />   
  <Order SalesOrderID="43859" CustomerID="259" />  
  ...  
</Emp1>  
```  
  
  
