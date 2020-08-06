---
title: Usare codice XML nelle colonne calcolate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- computed columns, XML
- XML [SQL Server], computed columns
ms.assetid: 1313b889-69b4-4018-9868-0496dd83bf44
author: rothja
ms.author: jroth
ms.openlocfilehash: 33a7549823dc3e4a23cecfa97d7345a6421cb1b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711767"
---
# <a name="use-xml-in-computed-columns"></a><span data-ttu-id="4bd55-102">Utilizzo del codice XML nelle colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="4bd55-102">Use XML in Computed Columns</span></span>
  <span data-ttu-id="4bd55-103">Le istanze XML possono rappresentare o l'origine o il tipo di una colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="4bd55-103">XML instances can appear as a source for a computed column, or as a type of computed column.</span></span> <span data-ttu-id="4bd55-104">Gli esempi contenuti in questo argomento mostrano come utilizzare il codice XML con le colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="4bd55-104">The examples in this topic show how to use XML with computed columns.</span></span>  
  
## <a name="creating-computed-columns-from-xml-columns"></a><span data-ttu-id="4bd55-105">Creazione di colonne calcolate da colonne XML</span><span class="sxs-lookup"><span data-stu-id="4bd55-105">Creating Computed Columns from XML Columns</span></span>  
 <span data-ttu-id="4bd55-106">Ad esempio, nell'istruzione seguente `CREATE TABLE` una colonna di tipo `xml` (`col2`) viene calcolata da `col1`:</span><span class="sxs-lookup"><span data-stu-id="4bd55-106">In the following `CREATE TABLE` statement, an `xml` type column (`col2`) is computed from `col1`:</span></span>  
  
```  
CREATE TABLE T(col1 varchar(max), col2 AS CAST(col1 AS xml) )    
```  
  
 <span data-ttu-id="4bd55-107">Il tipo di dati `xml` può inoltre rappresentare l'origine per la creazione di una colonna calcolata, come illustrato nell'istruzione `CREATE TABLE` seguente:</span><span class="sxs-lookup"><span data-stu-id="4bd55-107">The `xml` data type can also appear as a source in creating a computed column, as shown in the following `CREATE TABLE` statement:</span></span>  
  
```  
CREATE TABLE T (col1 xml, col2 as cast(col1 as varchar(1000) ))   
```  
  
 <span data-ttu-id="4bd55-108">È possibile creare una colonna calcolata mediante l'estrazione di un valore da una colonna di tipo `xml` , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4bd55-108">You can create a computed column by extracting a value from an `xml` type column as shown in the following example.</span></span> <span data-ttu-id="4bd55-109">Poiché non è possibile utilizzare direttamente i metodi con tipo di dati `xml` per la creazione di colonne calcolate, nell'esempio innanzitutto viene definita una funzione (`my_udf`) che restituisce un valore da un'istanza XML.</span><span class="sxs-lookup"><span data-stu-id="4bd55-109">Because the `xml` data type methods cannot be used directly in creating computed columns, the example first defines a function (`my_udf`) that returns a value from an XML instance.</span></span> <span data-ttu-id="4bd55-110">La funzione esegue il wrapping del metodo `value()` del tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="4bd55-110">The function wraps the `value()` method of the `xml` type.</span></span> <span data-ttu-id="4bd55-111">Il nome della funzione viene quindi specificato nell'istruzione `CREATE TABLE` per la colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="4bd55-111">The function name is then specified in the `CREATE TABLE` statement for the computed column.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns int  
AS BEGIN   
RETURN @var.value('(/ProductDescription/@ProductModelID)[1]' , 'int')  
END  
GO  
-- Use the function in CREATE TABLE.  
CREATE TABLE T (col1 xml, col2 as dbo.my_udf(col1) )  
GO  
-- Try adding a row.   
INSERT INTO T values('<ProductDescription ProductModelID="1" />')  
GO  
-- Verify results.  
SELECT col2, col1  
FROM T  
  
```  
  
 <span data-ttu-id="4bd55-112">Come il precedente, l'esempio successivo definisce una funzione per la restituzione di un'istanza con tipo di dati `xml` per una colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="4bd55-112">As in the previous example, the following example defines a function to return an `xml` type instance for a computed column.</span></span> <span data-ttu-id="4bd55-113">All'interno della funzione, il metodo `query()` con tipo di dati `xml` recupera un valore da un parametro del tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="4bd55-113">Inside the function, the `query()` method of the `xml` data type retrieves a value from an `xml` type parameter.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml)   
  RETURNS xml AS   
BEGIN   
   RETURN @var.query('ProductDescription/Features')  
END  
```  
  
 <span data-ttu-id="4bd55-114">Nell'istruzione seguente `CREATE TABLE` , `Col2` rappresenta una colonna calcolata che utilizza i dati XML (elemento`<Features>` ) restituiti dalla funzione:</span><span class="sxs-lookup"><span data-stu-id="4bd55-114">In the following `CREATE TABLE` statement, `Col2` is a computed column that uses the XML data (`<Features>` element) that is returned by the function:</span></span>  
  
```  
CREATE TABLE T (Col1 xml, Col2 as dbo.my_udf(Col1) )  
-- Insert a row in table T.  
INSERT INTO T VALUES('  
<ProductDescription ProductModelID="1" >  
  <Features>  
    <Feature1>description</Feature1>  
    <Feature2>description</Feature2>  
  </Features>  
</ProductDescription>')  
-- Verify the results.  
SELECT *  
FROM T  
```  
  
### <a name="in-this-section"></a><span data-ttu-id="4bd55-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4bd55-115">In This Section</span></span>  
  
|<span data-ttu-id="4bd55-116">Argomento</span><span class="sxs-lookup"><span data-stu-id="4bd55-116">Topic</span></span>|<span data-ttu-id="4bd55-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4bd55-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4bd55-118">Promuovere i valori XML di uso frequente mediante colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="4bd55-118">Promote Frequently Used XML Values with Computed Columns</span></span>](promote-frequently-used-xml-values-with-computed-columns.md)|<span data-ttu-id="4bd55-119">Viene descritta la modalità di utilizzo della promozione della proprietà con colonne calcolate e tabelle delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4bd55-119">Describes how to use property promotion with computed columns and property tables.</span></span>|  
  
  
