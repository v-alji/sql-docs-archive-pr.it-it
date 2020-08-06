---
title: 'Esempi: Utilizzo di OPENXML | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ColPattern [XML in SQL Server]
- XML [SQL Server], mapping data
- OPENXML statement, about OPENXML statement
- overflow in XML document [SQL Server]
- mapping XML data [SQL Server]
- combining attribute-centric and element centric mapping
- unconsumed data
- attribute-centric mapping
- column patterns [XML in SQL Server]
- XML [SQL Server], overflow handling
- row patterns [XML in SQL Server]
- rowpattern [XML in SQL Server]
- flags parameter
- element-centric mapping [SQL Server]
- edge tables
ms.assetid: 689297f3-adb0-4d8d-bf62-cfda26210164
author: rothja
ms.author: jroth
ms.openlocfilehash: 09fc6ad073b12df2f9fbd8ebc6a59149f6154ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726792"
---
# <a name="examples-using-openxml"></a><span data-ttu-id="40478-102">Esempi: Uso di OPENXML</span><span class="sxs-lookup"><span data-stu-id="40478-102">Examples: Using OPENXML</span></span>
  <span data-ttu-id="40478-103">Negli esempi presentati in questo argomento viene illustrato come utilizzare l'istruzione OPENXML per visualizzare un documento XML come set di righe.</span><span class="sxs-lookup"><span data-stu-id="40478-103">The examples in this topic show how OPENXML is used to create a rowset view of an XML document.</span></span> <span data-ttu-id="40478-104">Per informazioni sulla sintassi di OPENXML, vedere [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="40478-104">For information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span> <span data-ttu-id="40478-105">Negli esempi vengono illustrati tutti gli aspetti dell'istruzione OPENXML, ma non ne vengono specificate le metaproprietà.</span><span class="sxs-lookup"><span data-stu-id="40478-105">The examples show all aspects of OPENXML, but do not specify metaproperties in OPENXML.</span></span> <span data-ttu-id="40478-106">Per altre informazioni su come specificare le metaproprietà in OPENXML, vedere [Specificare metaproprietà in OPENXML](specify-metaproperties-in-openxml.md).</span><span class="sxs-lookup"><span data-stu-id="40478-106">For more information about how to specify metaproperties in OPENXML, see [Specify Metaproperties in OPENXML](specify-metaproperties-in-openxml.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="40478-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="40478-107">Examples</span></span>  
 <span data-ttu-id="40478-108">Durante il recupero dei dati è possibile usare il parametro *rowpattern* per identificare i nodi del documento XML che definiscono le righe.</span><span class="sxs-lookup"><span data-stu-id="40478-108">In retrieving the data, *rowpattern* is used to identify the nodes in the XML document that determine the rows.</span></span> <span data-ttu-id="40478-109">*rowpattern* viene espresso anche nel linguaggio del modello XPath usato nell'implementazione di XPath di MSXML.</span><span class="sxs-lookup"><span data-stu-id="40478-109">Additionally, *rowpattern* is expressed in the XPath pattern language that is used in the MSXML XPath implementation.</span></span> <span data-ttu-id="40478-110">Se ad esempio il modello termina con un elemento o con un attributo, viene creata una riga per ogni nodo di elemento o di attributo selezionato da *rowpattern*.</span><span class="sxs-lookup"><span data-stu-id="40478-110">For example, if the pattern ends in an element or an attribute, a row is created for each element or attribute node that is selected by *rowpattern*.</span></span>  
  
 <span data-ttu-id="40478-111">Il mapping predefinito è determinato dal valore di *flags* .</span><span class="sxs-lookup"><span data-stu-id="40478-111">The *flags* value provides default mapping.</span></span> <span data-ttu-id="40478-112">Se in *SchemaDeclaration* non è specificato *ColPattern*, viene usato il mapping specificato in *flags* .</span><span class="sxs-lookup"><span data-stu-id="40478-112">If no *ColPattern* is specified in the *SchemaDeclaration*, the mapping specified in *flags* is assumed.</span></span> <span data-ttu-id="40478-113">Se invece in *SchemaDeclaration* è specificato *ColPattern* , il valore *flags*viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="40478-113">The *flags* value is ignored if *ColPattern* is specified in *SchemaDeclaration*.</span></span> <span data-ttu-id="40478-114">Il valore specificato per *ColPattern* determina il tipo di mapping, che può essere incentrato sugli attributi o sugli elementi, nonché la modalità di gestione dei dati di overflow e di quelli non utilizzati.</span><span class="sxs-lookup"><span data-stu-id="40478-114">The specified *ColPattern* determines the mapping, attribute-centric or element-centric, and also the behavior in dealing with overflow and unconsumed data.</span></span>  
  
### <a name="a-executing-a-simple-select-statement-with-openxml"></a><span data-ttu-id="40478-115">R.</span><span class="sxs-lookup"><span data-stu-id="40478-115">A.</span></span> <span data-ttu-id="40478-116">Esecuzione di una semplice istruzione SELECT con OPENXML</span><span class="sxs-lookup"><span data-stu-id="40478-116">Executing a simple SELECT statement with OPENXML</span></span>  
 <span data-ttu-id="40478-117">Il documento XML utilizzato nell'esempio è costituito da elementi <`Customer`>, <`Order`> e <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="40478-117">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="40478-118">L'istruzione OPENXML recupera dal documento XML le informazioni sui clienti in un set di righe con due colonne, **CustomerID** e **ContactName**.</span><span class="sxs-lookup"><span data-stu-id="40478-118">The OPENXML statement retrieves customer information in a two-column rowset, **CustomerID** and **ContactName**, from the XML document.</span></span>  
  
 <span data-ttu-id="40478-119">Prima di tutto, viene chiamata la stored procedure **sp_xml_preparedocument** per ottenere un handle di documento.</span><span class="sxs-lookup"><span data-stu-id="40478-119">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="40478-120">L'handle del documento viene quindi passato a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-120">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="40478-121">Nell'istruzione OPENXML si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="40478-121">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="40478-122">Il parametro *rowpattern* (/ROOT/Customer) identifica i nodi <`Customer`> da elaborare.</span><span class="sxs-lookup"><span data-stu-id="40478-122">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="40478-123">Il valore del parametro *flags* è impostato su **1** , per indicare che il mapping è incentrato sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="40478-123">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="40478-124">Per gli attributi XML viene eseguito il mapping alle colonne del set di righe definite in *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="40478-124">As a result, the XML attributes map to the columns in the rowset defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="40478-125">In *SchemaDeclaration*, nella clausola WITH, i valori specificati per *ColName* corrispondono ai nomi degli attributi XML associati.</span><span class="sxs-lookup"><span data-stu-id="40478-125">In *SchemaDeclaration*, in the WITH clause, the specified *ColName* values match the corresponding XML attribute names.</span></span> <span data-ttu-id="40478-126">Quindi, in *SchemaDeclaration* non è specificato il parametro *ColPattern*.</span><span class="sxs-lookup"><span data-stu-id="40478-126">Therefore, the *ColPattern* parameter is not specified in *SchemaDeclaration*.</span></span>  
  
 <span data-ttu-id="40478-127">L'istruzione SELECT recupera quindi tutte le colonne nel set di righe specificato da OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-127">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @DocHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @DocHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@DocHandle, '/ROOT/Customer',1)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @DocHandle  
```  
  
 <span data-ttu-id="40478-128">Risultato:</span><span class="sxs-lookup"><span data-stu-id="40478-128">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="40478-129">Gli elementi <`Customer`> non hanno sottoelementi, quindi, se si esegue la stessa istruzione SELECT con il parametro *flags* impostato su **2** per indicare il mapping incentrato sugli elementi, i valori **CustomerID** e **ContactName** verranno restituiti come NULL per entrambi i clienti.</span><span class="sxs-lookup"><span data-stu-id="40478-129">Because the <`Customer`> elements do not have any subelements, if the same SELECT statement is executed with *flags* set to **2** to indicate element-centric mapping, the values of **CustomerID** and **ContactName** for both the customers are returned as NULL.</span></span>  
  
 <span data-ttu-id="40478-130">La variabile @xmlDocument può essere anche di tipo **xml** o di tipo **(n)varchar(max)**.</span><span class="sxs-lookup"><span data-stu-id="40478-130">The @xmlDocument can also be of **xml** type or of **(n)varchar(max)** type.</span></span>  
  
 <span data-ttu-id="40478-131">Se nel documento XML <`CustomerID`> e <`ContactName`> sono sottoelementi, il mapping incentrato sugli elementi ne recupererà i valori.</span><span class="sxs-lookup"><span data-stu-id="40478-131">If <`CustomerID`> and <`ContactName`> in the XML document are subelements, the element-centric mapping retrieves the values.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer>  
   <CustomerID>VINET</CustomerID>  
   <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer>     
   <CustomerID>LILAS</CustomerID>  
   <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT    *  
FROM      OPENXML (@XmlDocumentHandle, '/ROOT/Customer',2)  
           WITH (CustomerID  varchar(10),  
                 ContactName varchar(20))  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="40478-132">Risultato:</span><span class="sxs-lookup"><span data-stu-id="40478-132">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="40478-133">L'handle del documento restituito da **sp_xml_preparedocument** è valido solo per la durata del batch e non per tutta la sessione.</span><span class="sxs-lookup"><span data-stu-id="40478-133">Note that the document handle returned by **sp_xml_preparedocument** is valid for the duration of the batch and not the session.</span></span>  
  
### <a name="b-specifying-colpattern-for-mapping-between-rowset-columns-and-the-xml-attributes-and-elements"></a><span data-ttu-id="40478-134">B.</span><span class="sxs-lookup"><span data-stu-id="40478-134">B.</span></span> <span data-ttu-id="40478-135">Impostazione del parametro ColPattern per il mapping tra le colonne del set di righe e attributi o elementi XML</span><span class="sxs-lookup"><span data-stu-id="40478-135">Specifying ColPattern for mapping between rowset columns and the XML attributes and elements</span></span>  
 <span data-ttu-id="40478-136">Questo esempio mostra l'impostazione del modello XPath nel parametro facoltativo *ColPattern* per specificare il mapping tra le colonne del set di righe e gli attributi o elementi XML.</span><span class="sxs-lookup"><span data-stu-id="40478-136">This example shows how the XPath pattern is specified in the optional *ColPattern* parameter to provide mapping between rowset columns and the XML attributes and elements.</span></span>  
  
 <span data-ttu-id="40478-137">Il documento XML utilizzato nell'esempio è costituito da elementi <`Customer`>, <`Order`> e <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="40478-137">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="40478-138">L'istruzione OPENXML recupera dal documento XML le informazioni sui clienti e sugli ordini in un set di righe che include le colonne**CustomerID**, **OrderDate**, **ProdID**e **Qty**.</span><span class="sxs-lookup"><span data-stu-id="40478-138">The OPENXML statement retrieves customer and order information as a rowset (**CustomerID**, **OrderDate**, **ProdID**, and **Qty**) from the XML document.</span></span>  
  
 <span data-ttu-id="40478-139">Prima di tutto, viene chiamata la stored procedure **sp_xml_preparedocument** per ottenere un handle di documento.</span><span class="sxs-lookup"><span data-stu-id="40478-139">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="40478-140">L'handle del documento viene quindi passato a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-140">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="40478-141">Nell'istruzione OPENXML si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="40478-141">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="40478-142">Il parametro *rowpattern* (/ROOT/Customer/Order/OrderDetail) identifica i nodi <`OrderDetail`> da elaborare.</span><span class="sxs-lookup"><span data-stu-id="40478-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifies the <`OrderDetail`> nodes to process.</span></span>  
  
 <span data-ttu-id="40478-143">Nell'esempio il valore del parametro *flags* è impostato su **2** , per indicare che il mapping è incentrato sugli elementi,</span><span class="sxs-lookup"><span data-stu-id="40478-143">For illustration, the *flags* parameter value is set to **2** and indicates element-centric mapping.</span></span> <span data-ttu-id="40478-144">ma tale mapping viene sovrascritto da quello specificato in *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="40478-144">However, the mapping specified in *ColPattern* overwrites this mapping.</span></span> <span data-ttu-id="40478-145">In altre parole, il modello XPath specificato in *ColPattern* esegue il mapping delle colonne del set di righe agli attributi, il</span><span class="sxs-lookup"><span data-stu-id="40478-145">That is, the XPath pattern specified in *ColPattern* maps the columns in the rowset to attributes.</span></span> <span data-ttu-id="40478-146">che determina un mapping incentrato sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="40478-146">This results in attribute-centric mapping.</span></span>  
  
 <span data-ttu-id="40478-147">Nella clausola WITH di *SchemaDeclaration*il parametro *ColPattern* è specificato anche con i parametri *ColName* e *ColType* .</span><span class="sxs-lookup"><span data-stu-id="40478-147">In *SchemaDeclaration*, in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="40478-148">Il parametro *ColPattern* facoltativo è il modello XPath specificato e indica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="40478-148">The optional *ColPattern* is the XPath pattern specified and indicates the following:</span></span>  
  
-   <span data-ttu-id="40478-149">Il mapping delle colonne **OrderID**, **CustomerID** e **OrderDate** del set di righe viene eseguito agli attributi dell'elemento padre dei nodi identificati da *rowpattern* e *rowpattern* identifica i nodi <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="40478-149">The **OrderID**, **CustomerID**, and **OrderDate** columns in the rowset map to the attributes of the parent of the nodes identified by *rowpattern*, and *rowpattern* identifies the <`OrderDetail`> nodes.</span></span> <span data-ttu-id="40478-150">Viene quindi eseguito il mapping delle colonne **CustomerID** e **OrderDate** agli attributi **CustomerID** e **OrderDate** dell'elemento <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="40478-150">Therefore, the **CustomerID** and **OrderDate** columns map to **CustomerID** and **OrderDate** attributes of the <`Order`> element.</span></span>  
  
-   <span data-ttu-id="40478-151">Il mapping delle colonne **ProdID** e **Qty** del set di righe viene eseguito agli attributi **ProductID** e **Quantity** dei nodi identificati in *rowpattern*.</span><span class="sxs-lookup"><span data-stu-id="40478-151">The **ProdID** and **Qty** columns in the rowset map to the **ProductID** and **Quantity** attributes of the nodes identified in *rowpattern*.</span></span>  
  
 <span data-ttu-id="40478-152">L'istruzione SELECT recupera quindi tutte le colonne nel set di righe specificato da OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-152">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
           OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
           OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT stmt using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@XmlDocumentHandle, '/ROOT/Customer/Order/OrderDetail',2)  
WITH (OrderID     int         '../@OrderID',  
      CustomerID  varchar(10) '../@CustomerID',  
      OrderDate   datetime    '../@OrderDate',  
      ProdID      int         '@ProductID',  
      Qty         int         '@Quantity')  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="40478-153">Risultato:</span><span class="sxs-lookup"><span data-stu-id="40478-153">This is the result:</span></span>  
  
```  
OrderID CustomerID        OrderDate          ProdID    Qty  
-------------------------------------------------------------  
10248    VINET     1996-07-04 00:00:00.000     11       12  
10248    VINET     1996-07-04 00:00:00.000     42       10  
10283    LILAS     1996-08-16 00:00:00.000     72        3  
```  
  
 <span data-ttu-id="40478-154">Il modello XPath specificato in *ColPattern* può anche specificare il mapping degli elementi XML alle colonne del set di righe,</span><span class="sxs-lookup"><span data-stu-id="40478-154">The XPath pattern specified as *ColPattern* can also be specified to map the XML elements to the rowset columns.</span></span> <span data-ttu-id="40478-155">che determina un mapping incentrato sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="40478-155">This results in element-centric mapping.</span></span> <span data-ttu-id="40478-156">Nell'esempio seguente gli elementi <`CustomerID`> e <`OrderDate`> del documento XML sono sottoelementi dell'elemento <`Orders`>.</span><span class="sxs-lookup"><span data-stu-id="40478-156">In the following example, the XML document <`CustomerID`> and <`OrderDate`> are subelements of the <`Orders`> element.</span></span> <span data-ttu-id="40478-157">*ColPattern* sovrascrive il mapping specificato nel parametro *flags* , quindi *flags* non viene specificato nell'istruzione OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-157">Because *ColPattern* overwrites the mapping specified in the *flags* parameter, the *flags* parameter is not specified in OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order EmployeeID="5" >  
      <OrderID>10248</OrderID>  
      <CustomerID>VINET</CustomerID>  
      <OrderDate>1996-07-04T00:00:00</OrderDate>  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order  EmployeeID="3" >  
      <OrderID>10283</OrderID>  
      <CustomerID>LILAS</CustomerID>  
      <OrderDate>1996-08-16T00:00:00</OrderDate>  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail')  
WITH (CustomerID  varchar(10)   '../CustomerID',  
      OrderDate   datetime      '../OrderDate',  
      ProdID      int           '@ProductID',  
      Qty         int           '@Quantity')  
EXEC sp_xml_removedocument @docHandle  
```  
  
### <a name="c-combining-attribute-centric-and-element-centric-mapping"></a><span data-ttu-id="40478-158">C.</span><span class="sxs-lookup"><span data-stu-id="40478-158">C.</span></span> <span data-ttu-id="40478-159">Combinazione di mapping incentrato sugli attributi e mapping incentrato sugli elementi</span><span class="sxs-lookup"><span data-stu-id="40478-159">Combining attribute-centric and element-centric mapping</span></span>  
 <span data-ttu-id="40478-160">Nell'esempio seguente il parametro *flags* è impostato su **3** , per indicare che verrà applicato sia il mapping incentrato sugli attributi che quello incentrato sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="40478-160">In this example, the *flags* parameter is set to **3** and indicates that both attribute-centric and element-centric mapping will be applied.</span></span> <span data-ttu-id="40478-161">In questo caso verrà applicato per primo il mapping incentrato sugli attributi, mentre il mapping incentrato sugli elementi verrà applicato successivamente a tutte le colonne non ancora sottoposte a mapping.</span><span class="sxs-lookup"><span data-stu-id="40478-161">In this case, the attribute-centric mapping is applied first, and then element-centric mapping is applied for all the columns not yet dealt with.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument =N'<ROOT>  
<Customer CustomerID="VINET"  >  
     <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" >   
     <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer',3)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="40478-162">Risultato:</span><span class="sxs-lookup"><span data-stu-id="40478-162">This is the result</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="40478-163">A **CustomerID**viene applicato il mapping incentrato sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="40478-163">The attribute-centric mapping is applied for **CustomerID**.</span></span> <span data-ttu-id="40478-164">Nell'elemento <`Customer`> non è presente l'attributo **ContactName**, quindi</span><span class="sxs-lookup"><span data-stu-id="40478-164">There is no **ContactName** attribute in the <`Customer`> element.</span></span> <span data-ttu-id="40478-165">verrà applicato il mapping incentrato sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="40478-165">Therefore, element-centric mapping is applied.</span></span>  
  
### <a name="d-specifying-the-text-xpath-function-as-colpattern"></a><span data-ttu-id="40478-166">D.</span><span class="sxs-lookup"><span data-stu-id="40478-166">D.</span></span> <span data-ttu-id="40478-167">Impostazione della funzione XPath text() come parametro ColPattern</span><span class="sxs-lookup"><span data-stu-id="40478-167">Specifying the text() XPath function as ColPattern</span></span>  
 <span data-ttu-id="40478-168">Il documento XML utilizzato nell'esempio è costituito da elementi <`Customer`> e <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="40478-168">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="40478-169">L'istruzione OPENXML recupera un set di righe composto dall'attributo **oid** dell'elemento <`Order`>, dall'ID dell'elemento padre del nodo identificato da *rowpattern* e dalla stringa del valore foglia del contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="40478-169">The OPENXML statement retrieves a rowset that is made up of the **oid** attribute from the <`Order`> element, the ID of the parent of the node identified by *rowpattern*, and the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="40478-170">Prima di tutto, viene chiamata la stored procedure **sp_xml_preparedocument** per ottenere un handle di documento.</span><span class="sxs-lookup"><span data-stu-id="40478-170">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="40478-171">L'handle del documento viene quindi passato a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-171">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="40478-172">Nell'istruzione OPENXML si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="40478-172">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="40478-173">Il parametro *rowpattern* (/root/Customer/Order) identifica i nodi <`Order`> da elaborare.</span><span class="sxs-lookup"><span data-stu-id="40478-173">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="40478-174">Il valore del parametro *flags* è impostato su **1** , per indicare che il mapping è incentrato sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="40478-174">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="40478-175">Per gli attributi XML viene eseguito il mapping alle colonne del set di righe definite in *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="40478-175">As a result, the XML attributes map to the rowset columns defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="40478-176">In *SchemaDeclaration* , nella clausola WITH, i nomi delle colonne del set di righe **oid** e **amount** corrispondono ai nomi degli attributi XML associati.</span><span class="sxs-lookup"><span data-stu-id="40478-176">In *SchemaDeclaration* in the WITH clause, the **oid** and **amount** rowset column names match the corresponding XML attribute names.</span></span> <span data-ttu-id="40478-177">Di conseguenza, il parametro *ColPattern* non viene specificato.</span><span class="sxs-lookup"><span data-stu-id="40478-177">Therefore, the *ColPattern* parameter is not specified.</span></span> <span data-ttu-id="40478-178">Per la colonna **comment** del set di righe, la funzione XPath **text()** viene specificata come parametro *ColPattern*.</span><span class="sxs-lookup"><span data-stu-id="40478-178">For the **comment** column in the rowset, the XPath function, **text()**, is specified as *ColPattern*.</span></span> <span data-ttu-id="40478-179">Questo parametro sovrascrive il mapping incentrato sugli attributi specificato nel parametro *flags*e la colonna contiene la stringa del valore foglia del contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="40478-179">This overwrites the attribute-centric mapping specified in *flags*, and the column contains the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="40478-180">L'istruzione SELECT recupera quindi tutte le colonne nel set di righe specificato da OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-180">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied  
      </Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
            <Urgency>Important</Urgency>  
            Happy Customer.  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH (oid     char(5),   
           amount  float,   
           comment ntext 'text()')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="40478-181">Risultato:</span><span class="sxs-lookup"><span data-stu-id="40478-181">This is the result:</span></span>  
  
```  
oid   amount        comment  
----- -----------   -----------------------------  
O1    3.5           NULL  
O2    13.4          Customer was very satisfied  
O3    100.0         Happy Customer.  
O4    10000.0       NULL  
```  
  
### <a name="e-specifying-tablename-in-the-with-clause"></a><span data-ttu-id="40478-182">E.</span><span class="sxs-lookup"><span data-stu-id="40478-182">E.</span></span> <span data-ttu-id="40478-183">Impostazione del parametro TableName nella clausola WITH</span><span class="sxs-lookup"><span data-stu-id="40478-183">Specifying TableName in the WITH clause</span></span>  
 <span data-ttu-id="40478-184">Questo esempio specifica *TableName* con la clausola WITH invece di *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="40478-184">This example specifies *TableName* in the WITH clause instead of *SchemaDeclaration*.</span></span> <span data-ttu-id="40478-185">Questo risulta utile se è disponibile una tabella con la struttura desiderata e se non sono necessari i modelli di colonna definiti dal parametro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="40478-185">This is useful if you have a table that has the structure you want and no column patterns, *ColPattern* parameter, are required.</span></span>  
  
 <span data-ttu-id="40478-186">Il documento XML utilizzato nell'esempio è costituito da elementi <`Customer`> e <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="40478-186">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="40478-187">L'istruzione OPENXML recupera dal documento XML le informazioni sugli ordini in un set di righe con tre colonne,**oid**, **date**e **amount**.</span><span class="sxs-lookup"><span data-stu-id="40478-187">The OPENXML statement retrieves order information in a three-column rowset (**oid**, **date**, and **amount**) from the XML document.</span></span>  
  
 <span data-ttu-id="40478-188">Prima di tutto, viene chiamata la stored procedure **sp_xml_preparedocument** per ottenere un handle di documento.</span><span class="sxs-lookup"><span data-stu-id="40478-188">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="40478-189">L'handle del documento viene quindi passato a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-189">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="40478-190">Nell'istruzione OPENXML si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="40478-190">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="40478-191">Il parametro *rowpattern* (/root/Customer/Order) identifica i nodi <`Order`> da elaborare.</span><span class="sxs-lookup"><span data-stu-id="40478-191">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="40478-192">Nella clausola WITH non è presente *SchemaDeclaration* ,</span><span class="sxs-lookup"><span data-stu-id="40478-192">There is no *SchemaDeclaration* in the WITH clause.</span></span> <span data-ttu-id="40478-193">ma viene specificato un nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="40478-193">Instead, a table name is specified.</span></span> <span data-ttu-id="40478-194">Come schema del set di righe viene pertanto utilizzato lo schema della tabella.</span><span class="sxs-lookup"><span data-stu-id="40478-194">Therefore, the table schema is used as the rowset schema.</span></span>  
  
-   <span data-ttu-id="40478-195">Il valore del parametro *flags* è impostato su **1** , per indicare che il mapping è incentrato sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="40478-195">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="40478-196">Per gli attributi degli elementi identificati da *rowpattern*viene quindi eseguito il mapping alle colonne del set di righe con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="40478-196">Therefore, attributes of the elements, identified by *rowpattern*, map to the rowset columns with the same name.</span></span>  
  
 <span data-ttu-id="40478-197">L'istruzione SELECT recupera quindi tutte le colonne nel set di righe specificato da OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-197">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
-- Create a test table. This table schema is used by OPENXML as the  
-- rowset schema.  
CREATE TABLE T1(oid char(5), date datetime, amount float)  
GO  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
-- Sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH T1  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="40478-198">Risultato:</span><span class="sxs-lookup"><span data-stu-id="40478-198">This is the result:</span></span>  
  
```  
oid   date                        amount  
----- --------------------------- ----------  
O1    1996-01-20 00:00:00.000     3.5  
O2    1997-04-30 00:00:00.000     13.4  
O3    1999-07-14 00:00:00.000     100.0  
O4    1996-01-20 00:00:00.000     10000.0  
```  
  
### <a name="f-obtaining-the-result-in-an-edge-table-format"></a><span data-ttu-id="40478-199">F.</span><span class="sxs-lookup"><span data-stu-id="40478-199">F.</span></span> <span data-ttu-id="40478-200">Recupero di risultati in formato tabella edge</span><span class="sxs-lookup"><span data-stu-id="40478-200">Obtaining the result in an edge table format</span></span>  
 <span data-ttu-id="40478-201">In questo esempio nell'istruzione OPENXML non viene specificata la clausola WITH.</span><span class="sxs-lookup"><span data-stu-id="40478-201">In this example, the WITH clause is not specified in the OPENXML statement.</span></span> <span data-ttu-id="40478-202">Il set di righe generato dall'istruzione OPENXML ha pertanto un formato tabella edge.</span><span class="sxs-lookup"><span data-stu-id="40478-202">As a result, the rowset generated by OPENXML has an edge table format.</span></span> <span data-ttu-id="40478-203">L'istruzione SELECT restituisce tutte le colonne della tabella edge.</span><span class="sxs-lookup"><span data-stu-id="40478-203">The SELECT statement returns all the columns in the edge table.</span></span>  
  
 <span data-ttu-id="40478-204">Il documento XML utilizzato nell'esempio è costituito da elementi <`Customer`>, <`Order`> e <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="40478-204">The sample XML document in the example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span>  
  
 <span data-ttu-id="40478-205">Prima di tutto, viene chiamata la stored procedure **sp_xml_preparedocument** per ottenere un handle di documento.</span><span class="sxs-lookup"><span data-stu-id="40478-205">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="40478-206">L'handle del documento viene quindi passato a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-206">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="40478-207">Nell'istruzione OPENXML si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="40478-207">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="40478-208">Il parametro *rowpattern* (/ROOT/Customer) identifica i nodi <`Customer`> da elaborare.</span><span class="sxs-lookup"><span data-stu-id="40478-208">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="40478-209">La clausola WITH è stata omessa</span><span class="sxs-lookup"><span data-stu-id="40478-209">The WITH clause is not provided.</span></span> <span data-ttu-id="40478-210">e OPENXML restituisce pertanto un set di righe in formato tabella edge.</span><span class="sxs-lookup"><span data-stu-id="40478-210">Therefore, OPENXML returns the rowset in an edge table format.</span></span>  
  
 <span data-ttu-id="40478-211">L'istruzione SELECT recupera quindi tutte le colonne della tabella edge.</span><span class="sxs-lookup"><span data-stu-id="40478-211">The SELECT statement then retrieves all the columns in the edge table.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
SET @xmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail OrderID="10248" ProductID="11" Quantity="12"/>  
      <OrderDetail OrderID="10248" ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail OrderID="10283" ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer')  
  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="40478-212">Il risultato viene restituito sotto forma di tabella edge.</span><span class="sxs-lookup"><span data-stu-id="40478-212">The result is returned as an edge table.</span></span> <span data-ttu-id="40478-213">È possibile creare query da eseguire sulla tabella edge per recuperare informazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="40478-213">You can write queries against the edge table to obtain information.</span></span> <span data-ttu-id="40478-214">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="40478-214">For example:</span></span>  
  
-   <span data-ttu-id="40478-215">La query seguente restituisce il numero di nodi **Customer** presenti nel documento.</span><span class="sxs-lookup"><span data-stu-id="40478-215">The following query returns the number of **Customer** nodes in the document.</span></span> <span data-ttu-id="40478-216">Poiché non è stata specificata la clausola WITH, l'istruzione OPENXML restituisce una tabella edge.</span><span class="sxs-lookup"><span data-stu-id="40478-216">Because the WITH clause is not specified, OPENXML returns an edge table.</span></span> <span data-ttu-id="40478-217">L'istruzione SELECT esegue la query sulla tabella edge.</span><span class="sxs-lookup"><span data-stu-id="40478-217">The SELECT statement queries the edge table.</span></span>  
  
    ```  
    SELECT count(*)  
    FROM OPENXML(@docHandle, '/')  
    WHERE localname = 'Customer'  
    ```  
  
-   <span data-ttu-id="40478-218">La query seguente restituisce i nomi locali dei nodi XML di tipo elemento.</span><span class="sxs-lookup"><span data-stu-id="40478-218">The following query returns the local names of XML nodes of element type.</span></span>  
  
    ```  
    SELECT distinct localname   
    FROM OPENXML(@docHandle, '/')   
    WHERE nodetype = 1   
    ORDER BY localname  
    ```  
  
### <a name="g-specifying-rowpattern-ending-with-an-attribute"></a><span data-ttu-id="40478-219">G.</span><span class="sxs-lookup"><span data-stu-id="40478-219">G.</span></span> <span data-ttu-id="40478-220">Impostazione di un parametro rowpattern che termina con un attributo</span><span class="sxs-lookup"><span data-stu-id="40478-220">Specifying rowpattern ending with an attribute</span></span>  
 <span data-ttu-id="40478-221">Il documento XML utilizzato nell'esempio è costituito da elementi <`Customer`>, <`Order`> e <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="40478-221">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="40478-222">L'istruzione OPENXML recupera dal documento XML le informazioni sui dettagli degli ordini in un set di righe con tre colonne,**ProductID**, **Quantity**e **OrderID**.</span><span class="sxs-lookup"><span data-stu-id="40478-222">The OPENXML statement retrieves information about the order details in a three-column rowset (**ProductID**, **Quantity**, and **OrderID**) from the XML document.</span></span>  
  
 <span data-ttu-id="40478-223">Prima di tutto, viene chiamata la stored procedure **sp_xml_preparedocument** per ottenere un handle di documento.</span><span class="sxs-lookup"><span data-stu-id="40478-223">First, the **sp_xml_preparedocument** is called to obtain a document handle.</span></span> <span data-ttu-id="40478-224">L'handle del documento viene quindi passato a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-224">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="40478-225">Nell'istruzione OPENXML si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="40478-225">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="40478-226">Il parametro *rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) termina con l'attributo XML, **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="40478-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) ends with an XML attribute, **ProductID**.</span></span> <span data-ttu-id="40478-227">Nel set di righe risultante viene creata una riga per ogni nodo di attributo selezionato nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="40478-227">In the resulting rowset, a row is created for each attribute node selected in the XML document.</span></span>  
  
-   <span data-ttu-id="40478-228">In questo esempio il parametro *flags* non è specificato</span><span class="sxs-lookup"><span data-stu-id="40478-228">In this example, the *flags* parameter is not specified.</span></span> <span data-ttu-id="40478-229">e i mapping vengono definiti dal parametro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="40478-229">Instead, the mappings are specified by the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="40478-230">Nella clausola WITH di *SchemaDeclaration* il parametro *ColPattern* è specificato anche con i parametri *ColName* e *ColType* .</span><span class="sxs-lookup"><span data-stu-id="40478-230">In *SchemaDeclaration* in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="40478-231">Il parametro *ColPattern* facoltativo è il modello XPath specificato e indica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="40478-231">The optional *ColPattern* is the XPath pattern specified to indicate the following:</span></span>  
  
-   <span data-ttu-id="40478-232">Il modello XPath ( **.** ) specificato come *ColPattern* per la colonna **ProdID** nel set di righe identifica il nodo di contesto, ovvero il nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="40478-232">The XPath pattern (**.**) specified as *ColPattern* for the **ProdID** column in the rowset identifies the context node, current node.</span></span> <span data-ttu-id="40478-233">Il valore specificato per *rowpattern* è l'attributo **ProductID** dell'elemento <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="40478-233">As per the *rowpattern* specified, it is the **ProductID** attribute of the <`OrderDetail`> element.</span></span>  
  
-   <span data-ttu-id="40478-234">Il valore di *ColPattern*, **../\@Quantity**, specificato per la colonna **Qty** nel set di righe identifica l'attributo **Quantity** del nodo padre, <`OrderDetail`>, del nodo di contesto, \<ProductID>.</span><span class="sxs-lookup"><span data-stu-id="40478-234">The *ColPattern*, **../\@Quantity**, specified for the **Qty** column in the rowset identifies the **Quantity** attribute of the parent, <`OrderDetail`>, node of the context node, \<ProductID>.</span></span>  
  
-   <span data-ttu-id="40478-235">Analogamente, il valore di *ColPattern*, **../../\@OrderID**, specificato per la colonna **OID** nel set di righe identifica l'attributo **OrderID** dell'elemento padre, <`Order`>, del nodo padre del nodo di contesto.</span><span class="sxs-lookup"><span data-stu-id="40478-235">Similarly, the *ColPattern*, **../../\@OrderID**, specified for the **OID** column in the rowset identifies the **OrderID** attribute of the parent, <`Order`>, of the parent node of the context node.</span></span> <span data-ttu-id="40478-236">Il nodo padre è <`OrderDetail`>, mentre il nodo di contesto è <`ProductID`>.</span><span class="sxs-lookup"><span data-stu-id="40478-236">The parent node is <`OrderDetail`>, and the context node is <`ProductID`>.</span></span>  
  
 <span data-ttu-id="40478-237">L'istruzione SELECT recupera quindi tutte le colonne nel set di righe specificato da OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-237">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--Sample XML document  
SET @xmlDocument =N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail/@ProductID')  
       WITH ( ProdID  int '.',  
              Qty     int '../@Quantity',  
              OID     int '../../@OrderID')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="40478-238">Risultato:</span><span class="sxs-lookup"><span data-stu-id="40478-238">This is the result:</span></span>  
  
```  
ProdID      Qty         OID  
----------- ----------- -------   
11          12          10248  
42          10          10248  
72          3           10283  
```  
  
### <a name="h-specifying-an-xml-document-that-has-multiple-text-nodes"></a><span data-ttu-id="40478-239">H.</span><span class="sxs-lookup"><span data-stu-id="40478-239">H.</span></span> <span data-ttu-id="40478-240">Impostazione di un documento XML con più nodi di testo</span><span class="sxs-lookup"><span data-stu-id="40478-240">Specifying an XML document that has multiple text nodes</span></span>  
 <span data-ttu-id="40478-241">Se in un documento XML sono presenti più nodi di testo, un'istruzione SELECT con un parametro *ColPattern*di tipo **text()** restituirà solo il primo, invece di tutti i nodi di testo.</span><span class="sxs-lookup"><span data-stu-id="40478-241">If you have multiple text nodes in an XML document, a SELECT statement with a *ColPattern*, **text()**, returns only the first text node, instead of all of them.</span></span> <span data-ttu-id="40478-242">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="40478-242">For example:</span></span>  
  
```  
DECLARE @h int  
EXEC sp_xml_preparedocument @h OUTPUT,  
         N'<root xmlns:a="urn:1">  
           <a:Elem abar="asdf">  
             T<a>a</a>U  
           </a:Elem>  
         </root>',  
         '<ns xmlns:b="urn:1" />'  
  
SELECT * FROM openxml(@h, '/root/b:Elem')  
      WITH (Col1 varchar(20) 'text()')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="40478-243">L'istruzione SELECT restituisce **T** , invece di **TaU**.</span><span class="sxs-lookup"><span data-stu-id="40478-243">The SELECT statement returns **T** as the result, and not **TaU**.</span></span>  
  
### <a name="i-specifying-the-xml-data-type-in-the-with-clause"></a><span data-ttu-id="40478-244">I.</span><span class="sxs-lookup"><span data-stu-id="40478-244">I.</span></span> <span data-ttu-id="40478-245">Impostazione del tipo di dati xml nella clausola WITH</span><span class="sxs-lookup"><span data-stu-id="40478-245">Specifying the xml data type in the WITH clause</span></span>  
 <span data-ttu-id="40478-246">Nella clausola WITH un modello di colonna con mapping a una colonna con tipo di dati **xml** tipizzato o non tipizzato deve restituire una sequenza vuota oppure una sequenza di elementi, istruzioni di elaborazione, nodi di testo e commenti.</span><span class="sxs-lookup"><span data-stu-id="40478-246">In the WITH clause, a column pattern that is mapped to the **xml** data type column, whether typed or untyped, must return either an empty sequence or a sequence of elements, processing instructions, text nodes, and comments.</span></span> <span data-ttu-id="40478-247">Viene eseguito il cast dei dati a un tipo di dati **xml** .</span><span class="sxs-lookup"><span data-stu-id="40478-247">The data is cast to an **xml** data type.</span></span>  
  
 <span data-ttu-id="40478-248">Nell'esempio seguente la dichiarazione dello schema di tabella nella clausola WITH include colonne di tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="40478-248">In the following example, the table schema declaration in the WITH clause includes **xml** type columns.</span></span>  
  
```  
DECLARE @h int  
DECLARE @x xml  
set @x = '<Root>  
  <row id="1"><lname>Duffy</lname>  
   <Address>  
            <Street>111 Maple</Street>  
            <City>Seattle</City>  
   </Address>  
  </row>  
  <row id="2"><lname>Wang</lname>  
   <Address>  
            <Street>222 Pine</Street>  
            <City>Bothell</City>  
   </Address>  
  </row>  
</Root>'  
  
EXEC sp_xml_preparedocument @h output, @x  
SELECT *  
FROM   OPENXML (@h, '/Root/row', 10)  
      WITH (id int '@id',  
  
            lname    varchar(30),  
            xmlname  xml 'lname',  
            OverFlow xml '@mp:xmltext')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="40478-249">In particolare, viene passata una variabile di tipo **xml**, \@x, alla funzione **sp_xml_preparedocument()** .</span><span class="sxs-lookup"><span data-stu-id="40478-249">Specifically, you are passing an **xml** type variable (\@x) to the **sp_xml_preparedocument()** function.</span></span>  
  
 <span data-ttu-id="40478-250">Risultato:</span><span class="sxs-lookup"><span data-stu-id="40478-250">This is the result:</span></span>  
  
```  
id  lname   xmlname                   OverFlow  
--- ------- ------------------------------ -------------------------------  
1   Duffy   <lname>Duffy</lname>  <row><Address>  
                                   <Street>111 Maple</Street>  
                                   <City>Seattle</City>  
                                  </Address></row>  
2   Wang    <lname>Wang</lname>   <row><Address>  
                                    <Street>222 Pine</Street>  
                                    <City>Bothell</City>  
                                   </Address></row>  
```  
  
 <span data-ttu-id="40478-251">Dal risultato si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="40478-251">Note the following from the result:</span></span>  
  
-   <span data-ttu-id="40478-252">Il valore della colonna **lname** di tipo **varchar(30)** viene recuperato dall'elemento <`lname`> corrispondente.</span><span class="sxs-lookup"><span data-stu-id="40478-252">For the **lname** column of **varchar(30)** type, its value is retrieved from the corresponding <`lname`> element.</span></span>  
  
-   <span data-ttu-id="40478-253">Come valore della colonna **xmlname** di tipo **xml** , viene restituito l'elemento con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="40478-253">For the **xmlname** column of **xml** type, the same name element is returned as its value.</span></span>  
  
-   <span data-ttu-id="40478-254">Il flag è impostato su 10,</span><span class="sxs-lookup"><span data-stu-id="40478-254">The flag is set to 10.</span></span> <span data-ttu-id="40478-255">ovvero 2 + 8, dove 2 indica il mapping incentrato sugli elementi e 8 indica che solo i dati XML non utilizzati devono essere aggiunti alla colonna OverFlow definita nella clausola WITH.</span><span class="sxs-lookup"><span data-stu-id="40478-255">The 10 means 2 + 8, where 2 indicates element-centric mapping and 8 indicates that only unconsumed XML data should be added to the OverFlow column defined in the WITH clause.</span></span> <span data-ttu-id="40478-256">Se si imposta il flag su 2, nella colonna OverFlow specificata nella clausola WITH verrà copiato l'intero documento XML.</span><span class="sxs-lookup"><span data-stu-id="40478-256">If you set the flag to 2, the whole XML document is copied to the OverFlow column that is specified in the WITH clause.</span></span>  
  
-   <span data-ttu-id="40478-257">Se la colonna specificata nella clausola WITH è una colonna XML tipizzata e l'istanza XML non è conforme allo schema, verrà restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="40478-257">In case the column in the WITH clause is a typed XML column and the XML instance does not confirm to the schema, an error is returned.</span></span>  
  
### <a name="j-retrieving-individual-values-from-multivalued-attributes"></a><span data-ttu-id="40478-258">J.</span><span class="sxs-lookup"><span data-stu-id="40478-258">J.</span></span> <span data-ttu-id="40478-259">Recupero di singoli valori da attributi multivalore</span><span class="sxs-lookup"><span data-stu-id="40478-259">Retrieving individual values from multivalued attributes</span></span>  
 <span data-ttu-id="40478-260">Un documento XML può includere attributi multivalore.</span><span class="sxs-lookup"><span data-stu-id="40478-260">An XML document can have attributes that are multivalued.</span></span> <span data-ttu-id="40478-261">L'attributo **IDREFS** , ad esempio, può essere multivalore.</span><span class="sxs-lookup"><span data-stu-id="40478-261">For example, the **IDREFS** attribute can be multivalued.</span></span> <span data-ttu-id="40478-262">In un documento XML gli attributi multivalore vengono specificati come stringa, con i valori separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="40478-262">In an XML document, the multivalued attribute values are specified as a string, with the values separated by a space.</span></span> <span data-ttu-id="40478-263">Nel documento XML seguente l'attributo **attends** dell'elemento \<Student> e l'attributo **attendedBy** dell'elemento \<Class> sono multivalore.</span><span class="sxs-lookup"><span data-stu-id="40478-263">In the following XML document, the **attends** attribute of the \<Student> element and the **attendedBy** attribute of \<Class> are multivalued.</span></span> <span data-ttu-id="40478-264">Per recuperare i singoli valori da un attributo XML multivalore e archiviare ogni valore in una riga distinta del database, sono necessarie ulteriori operazioni,</span><span class="sxs-lookup"><span data-stu-id="40478-264">Retrieving individual values from a multivalued XML attribute and storing each value in a separate row in the database requires additional work.</span></span> <span data-ttu-id="40478-265">illustrate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="40478-265">This example shows the process.</span></span>  
  
 <span data-ttu-id="40478-266">Questo documento XML di esempio è costituito dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="40478-266">This sample XML document is made up of the following elements:</span></span>  
  
-   \<Student>  
  
     <span data-ttu-id="40478-267">Attributi **id** (ID dello studente), **name**e **attends** .</span><span class="sxs-lookup"><span data-stu-id="40478-267">The **id** (student ID), **name**, and **attends** attributes.</span></span> <span data-ttu-id="40478-268">L'attributo **attends** è multivalore.</span><span class="sxs-lookup"><span data-stu-id="40478-268">The **attends** attribute is a multivalued attribute.</span></span>  
  
-   \<Class>  
  
     <span data-ttu-id="40478-269">Attributi **id** (ID della classe), **name**e **attendedBy** .</span><span class="sxs-lookup"><span data-stu-id="40478-269">The **id** (class ID), **name**, and **attendedBy** attributes.</span></span> <span data-ttu-id="40478-270">L'attributo **attendedBy** è multivalore.</span><span class="sxs-lookup"><span data-stu-id="40478-270">The **attendedBy** attribute is a multivalued attribute.</span></span>  
  
 <span data-ttu-id="40478-271">L'attributo **attends** dell'elemento \<Student> e l'attributo **attendedBy** dell'elemento \<Class> rappresentano una relazione **m:n** tra le tabelle Student e Class.</span><span class="sxs-lookup"><span data-stu-id="40478-271">The **attends** attribute in \<Student> and the **attendedBy** attribute in \<Class> represent a **m:n** relationship between the Student and Class tables.</span></span> <span data-ttu-id="40478-272">Uno studente può frequentare più classi e una classe può essere frequentata da più studenti.</span><span class="sxs-lookup"><span data-stu-id="40478-272">A student can take many classes and a class can have many students.</span></span>  
  
 <span data-ttu-id="40478-273">Si supponga che sia necessario suddividere il documento e salvarlo nel database, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="40478-273">Assume that you want to shred this document and save it in the database as shown in the following:</span></span>  
  
-   <span data-ttu-id="40478-274">Salvare i dati dell'elemento \<Student> nella tabella Students.</span><span class="sxs-lookup"><span data-stu-id="40478-274">Save the \<Student> data in the Students table.</span></span>  
  
-   <span data-ttu-id="40478-275">Salvare i dati dell'elemento \<Class> nella tabella Courses.</span><span class="sxs-lookup"><span data-stu-id="40478-275">Save the \<Class> data in the Courses table.</span></span>  
  
-   <span data-ttu-id="40478-276">Salvare nella tabella CourseAttendence i dati della relazione **m:n** tra le tabelle Student e Class.</span><span class="sxs-lookup"><span data-stu-id="40478-276">Save the **m:n** relationship data, between Student and Class, in the CourseAttendence table.</span></span> <span data-ttu-id="40478-277">Per estrarre i valori sono necessarie ulteriori operazioni.</span><span class="sxs-lookup"><span data-stu-id="40478-277">Additional work is required to extract the values.</span></span> <span data-ttu-id="40478-278">Per recuperare le informazioni e archiviarle nella tabella, utilizzare le stored procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="40478-278">To retrieve this information and store it in the table, use these stored procedures:</span></span>  
  
    -   <span data-ttu-id="40478-279">**Insert_Idrefs_Values**</span><span class="sxs-lookup"><span data-stu-id="40478-279">**Insert_Idrefs_Values**</span></span>  
  
         <span data-ttu-id="40478-280">Inserisce gli ID di corsi e studenti nella tabella CourseAttendence.</span><span class="sxs-lookup"><span data-stu-id="40478-280">Inserts the values of course ID and student ID in the CourseAttendence table.</span></span>  
  
    -   <span data-ttu-id="40478-281">**Extract_idrefs_values**</span><span class="sxs-lookup"><span data-stu-id="40478-281">**Extract_idrefs_values**</span></span>  
  
         <span data-ttu-id="40478-282">Estrae gli ID dei singoli studenti da ogni elemento \<Course>.</span><span class="sxs-lookup"><span data-stu-id="40478-282">Extracts the individual student IDs from each \<Course> element.</span></span> <span data-ttu-id="40478-283">Per recuperare questi valori viene utilizzata una tabella edge.</span><span class="sxs-lookup"><span data-stu-id="40478-283">An edge table is used to retrieve these values.</span></span>  
  
 <span data-ttu-id="40478-284">I passaggi necessari sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="40478-284">Here are the steps:</span></span>  
  
```  
-- Create these tables:  
DROP TABLE CourseAttendance  
DROP TABLE Students  
DROP TABLE Courses  
GO  
CREATE TABLE Students(  
                id   varchar(5) primary key,  
                name varchar(30)  
                )  
GO  
CREATE TABLE Courses(  
               id       varchar(5) primary key,  
               name     varchar(30),  
               taughtBy varchar(5)  
)  
GO  
CREATE TABLE CourseAttendance(  
             id         varchar(5) references Courses(id),  
             attendedBy varchar(5) references Students(id),  
             constraint CourseAttendance_PK primary key (id, attendedBy)  
)  
go  
-- Create these stored procedures:  
DROP PROCEDURE f_idrefs  
GO  
CREATE PROCEDURE f_idrefs  
    @t      varchar(500),  
    @idtab  varchar(50),  
    @id     varchar(5)  
AS  
DECLARE @sp int  
DECLARE @att varchar(5)  
SET @sp = 0  
WHILE (LEN(@t) > 0)  
BEGIN   
    SET @sp = CHARINDEX(' ', @t+ ' ')  
    SET @att = LEFT(@t, @sp-1)  
    EXEC('INSERT INTO '+@idtab+' VALUES ('''+@id+''', '''+@att+''')')  
    SET @t = SUBSTRING(@t+ ' ', @sp+1, LEN(@t)+1-@sp)  
END  
Go  
  
DROP PROCEDURE fill_idrefs  
GO  
CREATE PROCEDURE fill_idrefs   
    @xmldoc     int,  
    @xpath      varchar(100),  
    @from       varchar(50),  
    @to         varchar(50),  
    @idtable    varchar(100)  
AS  
DECLARE @t varchar(500)  
DECLARE @id varchar(5)  
  
/* Temporary edge table */  
SELECT *   
INTO #TempEdge   
FROM OPENXML(@xmldoc, @xpath)  
  
DECLARE fillidrefs_cursor CURSOR FOR  
    SELECT CAST(iv.text AS nvarchar(200)) AS id,  
           CAST(av.text AS nvarchar(4000)) AS refs  
    FROM   #TempEdge c, #TempEdge i,  
           #TempEdge iv, #TempEdge a, #TempEdge av  
    WHERE  c.id = i.parentid  
    AND    UPPER(i.localname) = UPPER(@from)  
    AND    i.id = iv.parentid  
    AND    c.id = a.parentid  
    AND    UPPER(a.localname) = UPPER(@to)  
    AND    a.id = av.parentid  
  
OPEN fillidrefs_cursor  
FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
WHILE (@@FETCH_STATUS <> -1)  
BEGIN  
    IF (@@FETCH_STATUS <> -2)  
    BEGIN  
        execute f_idrefs @t, @idtable, @id  
    END  
    FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
END  
CLOSE fillidrefs_cursor  
DEALLOCATE fillidrefs_cursor  
Go  
-- This is the sample document that is shredded and the data is stored in the preceding tables.  
DECLARE @h int  
EXECUTE sp_xml_preparedocument @h OUTPUT, N'<Data>  
  <Student id = "s1" name = "Student1"  attends = "c1 c3 c6"  />  
  <Student id = "s2" name = "Student2"  attends = "c2 c4" />  
  <Student id = "s3" name = "Student3"  attends = "c2 c4 c6" />  
  <Student id = "s4" name = "Student4"  attends = "c1 c3 c5" />  
  <Student id = "s5" name = "Student5"  attends = "c1 c3 c5 c6" />  
  <Student id = "s6" name = "Student6" />  
  
  <Class id = "c1" name = "Intro to Programming"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c2" name = "Databases"   
         attendedBy = "s2 s3" />  
  <Class id = "c3" name = "Operating Systems"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c4" name = "Networks" attendedBy = "s2 s3" />  
  <Class id = "c5" name = "Algorithms and Graphs"   
         attendedBy =  "s4 s5"/>  
  <Class id = "c6" name = "Power and Pragmatism"   
         attendedBy = "s1 s3 s5" />  
</Data>'  
  
INSERT INTO Students SELECT * FROM OPENXML(@h, '//Student') WITH Students  
  
INSERT INTO Courses SELECT * FROM OPENXML(@h, '//Class') WITH Courses  
/* Using the edge table */  
EXECUTE fill_idrefs @h, '//Class', 'id', 'attendedby', 'CourseAttendance'  
  
SELECT * FROM Students  
SELECT * FROM Courses  
SELECT * FROM CourseAttendance  
  
EXECUTE sp_xml_removedocument @h  
```  
  
### <a name="k-retrieving-binary-from-base64-encoded-data-in-xml"></a><span data-ttu-id="40478-285">K.</span><span class="sxs-lookup"><span data-stu-id="40478-285">K.</span></span> <span data-ttu-id="40478-286">Recupero di dati binari da dati con codifica Base64 in un valore XML</span><span class="sxs-lookup"><span data-stu-id="40478-286">Retrieving binary from base64 encoded data in XML</span></span>  
 <span data-ttu-id="40478-287">Nei valori XML sono spesso inclusi dati binari con codifica Base64.</span><span class="sxs-lookup"><span data-stu-id="40478-287">Binary data is frequently included in XML using base64 encoding.</span></span> <span data-ttu-id="40478-288">Quando si suddivide un valore XML di questo tipo tramite l'istruzione OPENXML, vengono restituiti dati con codifica Base64.</span><span class="sxs-lookup"><span data-stu-id="40478-288">When you shred this XML by using OPENXML, you receive the base64 encoded data.</span></span> <span data-ttu-id="40478-289">In questo esempio viene illustrato come convertire in formato binario i dati con codifica Base64.</span><span class="sxs-lookup"><span data-stu-id="40478-289">This example shows how you can convert the base64 encoded data back to binary.</span></span>  
  
-   <span data-ttu-id="40478-290">Creare una tabella con dati binari di esempio.</span><span class="sxs-lookup"><span data-stu-id="40478-290">Create a table with sample binary data.</span></span>  
  
-   <span data-ttu-id="40478-291">Utilizzare una query FOR XML e l'opzione BINARY BASE64 per costruire il valore XML che include dati binari con codifica Base64.</span><span class="sxs-lookup"><span data-stu-id="40478-291">Use a FOR XML query and the BINARY BASE64 option to construct XML that has the binary data encoded as base64.</span></span>  
  
-   <span data-ttu-id="40478-292">Suddividere il valore XML tramite un'istruzione OPENXML.</span><span class="sxs-lookup"><span data-stu-id="40478-292">Shred the XML by using OPENXML.</span></span> <span data-ttu-id="40478-293">L'istruzione OPENXML restituirà dati con codifica Base64.</span><span class="sxs-lookup"><span data-stu-id="40478-293">The data returned by OPENXML will be base64 encoded data.</span></span> <span data-ttu-id="40478-294">Chiamare quindi la funzione .value per convertire i dati in formato binario.</span><span class="sxs-lookup"><span data-stu-id="40478-294">Next, call the .value function to convert it back to binary.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 varbinary(100))  
go  
-- Insert sample binary data  
INSERT T VALUES(1, 0x1234567890)   
go  
 -- Create test XML document that has base64 encoded binary data (use FOR XML query and specify BINARY BASE64 option)  
SELECT * FROM T  
FOR XML AUTO, BINARY BASE64  
go  
-- result  
-- <T Col1="1" Col2="EjRWeJA="/>  
  
-- Now shredd the sample XML using OPENXML.   
-- Call the .value function to convert   
-- the base64 encoded data returned by OPENXML to binary.  
DECLARE @h int ;  
EXEC sp_xml_preparedocument @h OUTPUT, '<T Col1="1" Col2="EjRWeJA="/>' ;  
SELECT Col1,   
CAST('<binary>' + Col2 + '</binary>' AS XML).value('.', 'varbinary(max)') AS BinaryCol   
FROM openxml(@h, '/T')   
WITH (Col1 integer, Col2 varchar(max)) ;  
EXEC sp_xml_removedocument @h ;  
GO  
```  
  
 Di seguito è riportato il risultato. <span data-ttu-id="40478-296">I dati binari restituiti sono i dati binari originali della tabella T.</span><span class="sxs-lookup"><span data-stu-id="40478-296">The binary data returned is the original binary data in table T.</span></span>  
  
```  
Col1        BinaryCol  
----------- ---------------------  
1           0x1234567890  
```  
  
## <a name="see-also"></a><span data-ttu-id="40478-297">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40478-297">See Also</span></span>  
 <span data-ttu-id="40478-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="40478-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span></span>  
 <span data-ttu-id="40478-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="40478-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span></span>  
 <span data-ttu-id="40478-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="40478-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="40478-301">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40478-301">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
