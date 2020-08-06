---
title: Direttiva TYPE in query FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, TYPE directive
- TYPE directive
ms.assetid: a3df6c30-1f25-45dc-b5a9-bd0e41921293
author: rothja
ms.author: jroth
ms.openlocfilehash: cddce90718ef5edfcf161ddc6cc52b617825a2e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637661"
---
# <a name="type-directive-in-for-xml-queries"></a><span data-ttu-id="62bb8-102">Direttiva TYPE in query FOR XML</span><span class="sxs-lookup"><span data-stu-id="62bb8-102">TYPE Directive in FOR XML Queries</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="62bb8-103">il supporto per [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql) consente di richiedere facoltativamente che il risultato di una query for XML venga restituito come `xml` tipo di dati specificando la direttiva Type.</span><span class="sxs-lookup"><span data-stu-id="62bb8-103">support for the [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql) enables you to optionally request that the result of a FOR XML query be returned as `xml` data type by specifying the TYPE directive.</span></span> <span data-ttu-id="62bb8-104">In questo modo è possibile elaborare il risultato di una query FOR XML sul server.</span><span class="sxs-lookup"><span data-stu-id="62bb8-104">This allows you to process the result of a FOR XML query on the server.</span></span> <span data-ttu-id="62bb8-105">È ad esempio possibile specificare una query XQuery su di essa, assegnare il risultato a una `xml` variabile di tipo o scrivere [query for XML nidificate](use-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="62bb8-105">For example, you can specify an XQuery against it, assign the result to an `xml` type variable, or write [Nested FOR XML queries](use-nested-for-xml-queries.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="62bb8-106">restituisce dati di istanza di tipo XML al client come risultato di diversi costrutti server, ad esempio query FOR XML che utilizzano la direttiva TYPE o in cui il tipo di dati `xml` viene utilizzato per la restituzione di valori dei dati dell'istanza XML da colonne di tabella e parametri di output SQL.</span><span class="sxs-lookup"><span data-stu-id="62bb8-106">returns XML data type instance data to the client as a result of different server-constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML instance data values from SQL table columns and output parameters.</span></span> <span data-ttu-id="62bb8-107">Nel codice delle applicazioni client, il provider ADO.NET richiede che le informazioni sui tipi di dati XML vengano inviate dal server in codifica binaria.</span><span class="sxs-lookup"><span data-stu-id="62bb8-107">In client application code, the ADO.NET provider requests this XML data type information to be sent in a binary encoding from the server.</span></span> <span data-ttu-id="62bb8-108">Se tuttavia si utilizza FOR XML senza la direttiva TYPE, i dati XML vengono restituiti come tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="62bb8-108">However, if you are using FOR XML without the TYPE directive, the XML data comes back as a string type.</span></span> <span data-ttu-id="62bb8-109">In tutti i casi, il provider client sarà sempre in grado di gestire entrambe i formati di XML.</span><span class="sxs-lookup"><span data-stu-id="62bb8-109">In any case, the client provider will always be able to handle either form of XML.</span></span> <span data-ttu-id="62bb8-110">La clausola FOR XML di livello principale senza la direttiva TYPE non può essere utilizzata con i cursori.</span><span class="sxs-lookup"><span data-stu-id="62bb8-110">Note that top-level FOR XML without the TYPE directive cannot be used with cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="62bb8-111">Esempi</span><span class="sxs-lookup"><span data-stu-id="62bb8-111">Examples</span></span>  
 <span data-ttu-id="62bb8-112">Nell'esempio seguente viene illustrato l'utilizzo della direttiva TYPE con le query FOR XML.</span><span class="sxs-lookup"><span data-stu-id="62bb8-112">The following examples illustrate the use of the TYPE directive with FOR XML queries.</span></span>  
  
### <a name="retrieving-for-xml-query-results-as-xml-type"></a><span data-ttu-id="62bb8-113">Recupero dei risultati di una query FOR XML come tipo xml</span><span class="sxs-lookup"><span data-stu-id="62bb8-113">Retrieving FOR XML query results as xml type</span></span>  
 <span data-ttu-id="62bb8-114">La query seguente recupera le informazioni di contatto del cliente dalla tabella `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="62bb8-114">The following query retrieves customer contact information from the `Contacts` table.</span></span> <span data-ttu-id="62bb8-115">Poiché in `TYPE` è specificata la direttiva `FOR XML`, il risultato viene restituito come tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="62bb8-115">Because the `TYPE` directive is specified in `FOR XML`, the result is returned as `xml` type.</span></span>  
  
```  
USE AdventureWorks2012;  
Go  
SELECT BusinessEntityID, FirstName, LastName  
FROM Person.Person  
ORDER BY BusinessEntityID  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="62bb8-116">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="62bb8-116">This is the partial result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez"/>`  
  
 `<Person.Person BusinessEntityID="2" FirstName="Terri" LastName="Duffy"/>`  
  
 `...`  
  
### <a name="assigning-for-xml-query-results-to-an-xml-type-variable"></a><span data-ttu-id="62bb8-117">Assegnazione dei risultati di una query FOR XML a una variabile di tipo xml</span><span class="sxs-lookup"><span data-stu-id="62bb8-117">Assigning FOR XML query results to an xml type variable</span></span>  
 <span data-ttu-id="62bb8-118">Nell'esempio seguente il risultato di una query FOR XML viene assegnato a una variabile di tipo `xml`, `@x`.</span><span class="sxs-lookup"><span data-stu-id="62bb8-118">In the following example, a FOR XML result is assigned to an `xml` type variable, `@x`.</span></span> <span data-ttu-id="62bb8-119">La query recupera le informazioni di contatto, ad esempio `BusinessEntityID` ,, `FirstName` e i `LastName` numeri di telefono aggiuntivi dalla `AdditionalContactInfo` colonna di `xml``TYPE` .</span><span class="sxs-lookup"><span data-stu-id="62bb8-119">The query retrieves contact information, such as the `BusinessEntityID`, `FirstName`, `LastName`, and additional telephone numbers, from the `AdditionalContactInfo` column of `xml``TYPE`.</span></span> <span data-ttu-id="62bb8-120">Poiché la clausola `FOR XML` specifica la direttiva `TYPE`, il codice XML viene restituito come tipo `xml` e assegnato a una variabile.</span><span class="sxs-lookup"><span data-stu-id="62bb8-120">Because the `FOR XML` clause specifies `TYPE` directive, the XML is returned as `xml` type and is assigned to a variable.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @x xml;  
SET @x = (  
   SELECT BusinessEntityID,   
          FirstName,   
          LastName,   
          AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
              //act:telephoneNumber/act:number') as MorePhoneNumbers  
   FROM Person.Person  
   FOR XML AUTO, TYPE);  
SELECT @x;  
GO  
```  
  
### <a name="querying-results-of-a-for-xml-query"></a><span data-ttu-id="62bb8-121">Esecuzione di una query sui risultati di una query FOR XML</span><span class="sxs-lookup"><span data-stu-id="62bb8-121">Querying results of a FOR XML query</span></span>  
 <span data-ttu-id="62bb8-122">La query FOR XML restituisce codice XML.</span><span class="sxs-lookup"><span data-stu-id="62bb8-122">The FOR XML queries return XML.</span></span> <span data-ttu-id="62bb8-123">È pertanto possibile applicare al risultato XML restituito dalle query FOR XML i metodi con tipo `xml`, ad esempio `query()` e `value()`.</span><span class="sxs-lookup"><span data-stu-id="62bb8-123">Therefore, you can apply `xml` type methods, such as `query()` and `value()`, to the XML result returned by FOR XML queries.</span></span>  
  
 <span data-ttu-id="62bb8-124">Nella query seguente il metodo `query()` del tipo di dati `xml` viene utilizzato per l'esecuzione di una query sui risultati della query `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="62bb8-124">In the following query, the `query()` method of the `xml` data type is used to query the result of the `FOR XML` query.</span></span> <span data-ttu-id="62bb8-125">Per altre informazioni, vedere [Metodo query&#40;&#41; con &#40;tipo di dati XML&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="62bb8-125">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT (SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
DECLARE namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
DECLARE namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
 //act:telephoneNumber/act:number  
') AS PhoneNumbers  
FROM Person.Person  
FOR XML AUTO, TYPE).query('/Person.Person[1]');  
```  
  
 <span data-ttu-id="62bb8-126">La query interna `SELECT ... FOR XML` restituisce un risultato di tipo `xml` al quale la query esterna `SELECT` applica il metodo `query()` al tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="62bb8-126">The inner `SELECT ... FOR XML` query returns an `xml` type result to which the outer `SELECT` applies the `query()` method to the `xml` type.</span></span> <span data-ttu-id="62bb8-127">Si noti la direttiva `TYPE` specificata.</span><span class="sxs-lookup"><span data-stu-id="62bb8-127">Note the `TYPE` directive specified.</span></span>  
  
 <span data-ttu-id="62bb8-128">Risultato:</span><span class="sxs-lookup"><span data-stu-id="62bb8-128">This is the result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez">`  
  
 `<PhoneNumbers>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">111-111-1111</act:number>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">112-111-1111</act:number>`  
  
 `</PhoneNumbers>`  
  
 `</Person.Person>`  
  
 <span data-ttu-id="62bb8-129">Nella query seguente il metodo `value()` con il tipo di dati `xml` viene utilizzato per recuperare un valore dal risultato XML restituito dalla query `SELECT...FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="62bb8-129">In the following query, the `value()` method of the `xml` data type is used to retrieve a value from the XML result returned by the `SELECT...FOR XML` query.</span></span> <span data-ttu-id="62bb8-130">Per altre informazioni, vedere [Metodo value&#40;&#41; &#40;tipo di dati XML&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="62bb8-130">For more information, see [value&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @FirstPhoneFromAdditionalContactInfo varchar(40);  
SELECT @FirstPhoneFromAdditionalContactInfo =   
 ( SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
   //act:telephoneNumber/act:number  
   ') AS PhoneNumbers  
   FROM Person.Person Contact  
   FOR XML AUTO, TYPE).value('  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
  /Contact[@BusinessEntityID="1"][1]/PhoneNumbers[1]/act:number[1]', 'varchar(40)'  
 )  
SELECT @FirstPhoneFromAdditionalContactInfo;  
```  
  
 <span data-ttu-id="62bb8-131">L'espressione di percorso XQuery nel metodo `value()` recupera il primo numero di telefono di un cliente il cui `BusinessEntityID` è `1`.</span><span class="sxs-lookup"><span data-stu-id="62bb8-131">The XQuery path expression in the `value()` method retrieves the first telephone number of a customer contact whose `BusinessEntityID` is `1`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62bb8-132">Se non si specifica la direttiva TYPE, il risultato della query FOR XML viene restituito come tipo `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="62bb8-132">If the TYPE directive is not specified, the FOR XML query result is returned as type `nvarchar(max)`.</span></span>  
  
### <a name="using-for-xml-query-results-in-insert-update-and-delete-transact-sql-dml"></a><span data-ttu-id="62bb8-133">Utilizzo dei risultati di query FOR XML in istruzioni INSERT, UPDATE e DELETE (DML Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="62bb8-133">Using FOR XML query results in INSERT, UPDATE, and DELETE (Transact-SQL DML)</span></span>  
 <span data-ttu-id="62bb8-134">Nell'esempio seguente viene illustrato l'utilizzo delle query FOR XML nelle istruzioni DML (Data Manipulation Language).</span><span class="sxs-lookup"><span data-stu-id="62bb8-134">The following example demonstrates how FOR XML queries can be used in Data Manipulation Language (DML) statements.</span></span> <span data-ttu-id="62bb8-135">Nell'esempio la query `FOR XML` restituisce un'istanza di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="62bb8-135">In the example, the `FOR XML` returns an instance of `xml` type.</span></span> <span data-ttu-id="62bb8-136">L'istruzione `INSERT` inserisce il codice XML in una tabella.</span><span class="sxs-lookup"><span data-stu-id="62bb8-136">The `INSERT` statement inserts this XML into a table.</span></span>  
  
```  
CREATE TABLE T1(intCol int, XmlCol xml);  
GO  
INSERT INTO T1   
VALUES(1, '<Root><ProductDescription ProductModelID="1" /></Root>');  
GO  
  
CREATE TABLE T2(XmlCol xml)  
GO  
INSERT INTO T2(XmlCol)   
SELECT (SELECT XmlCol.query('/Root')   
        FROM T1   
        FOR XML AUTO,TYPE);   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="62bb8-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62bb8-137">See Also</span></span>  
 [<span data-ttu-id="62bb8-138">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="62bb8-138">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
