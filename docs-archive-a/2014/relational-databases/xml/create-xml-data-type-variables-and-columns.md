---
title: Creare variabili e colonne con tipo di dati XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- xml data type [SQL Server], columns
ms.assetid: 8994ab6e-5519-4ba2-97a1-fac8af6f72db
author: rothja
ms.author: jroth
ms.openlocfilehash: 08b79888eb47634deaccc910b2ea3c93800b7c78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722611"
---
# <a name="create-xml-data-type-variables-and-columns"></a><span data-ttu-id="652c0-102">Creazione di variabili e colonne con tipo di dati XML</span><span class="sxs-lookup"><span data-stu-id="652c0-102">Create XML Data Type Variables and Columns</span></span>
  <span data-ttu-id="652c0-103">Il tipo di dati `xml` è un tipo di dati predefinito in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ed è simile ad altri tipi predefiniti quali `int` e `varchar`.</span><span class="sxs-lookup"><span data-stu-id="652c0-103">The `xml` data type is a built-in data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is somewhat similar to other built-in types such as `int` and `varchar`.</span></span> <span data-ttu-id="652c0-104">Come per gli altri tipi incorporati, è possibile usare il `xml` tipo di dati come tipo di colonna quando si crea una tabella come tipo di variabile, un tipo di parametro, un tipo restituito dalla funzione o in [cast e Convert](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="652c0-104">As with other built-in types, you can use the `xml` data type as a column type when you create a table as a variable type, a parameter type, a function-return type, or in [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
## <a name="creating-columns-and-variables"></a><span data-ttu-id="652c0-105">Creazione di colonne e variabili</span><span class="sxs-lookup"><span data-stu-id="652c0-105">Creating Columns and Variables</span></span>  
 <span data-ttu-id="652c0-106">Per creare una colonna di tipo `xml` come parte di una tabella, usare un'istruzione `CREATE TABLE` come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="652c0-106">To create an `xml` type column as part of a table, use a `CREATE TABLE` statement, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T1(Col1 int primary key, Col2 xml)   
```  
  
 <span data-ttu-id="652c0-107">È possibile usare una `DECLARE statement` per creare una variabile del tipo `xml` , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="652c0-107">You can use a `DECLARE statement` to create a variable of `xml` type, as the following example shows.</span></span>  
  
```  
DECLARE @x xml   
```  
  
 <span data-ttu-id="652c0-108">Creare una variabile `xml` tipizzata specificando una raccolta di XML Schema, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="652c0-108">Create a typed `xml` variable by specifying an XML schema collection, as shown in the following example.</span></span>  
  
```  
DECLARE @x xml (Sales.StoreSurveySchemaCollection)  
```  
  
 <span data-ttu-id="652c0-109">Per passare un parametro di tipo `xml` a una stored procedure, usare un'istruzione `CREATE PROCEDURE` come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="652c0-109">To pass an `xml` type parameter to a stored procedure, use a `CREATE PROCEDURE` statement, as shown in the following example.</span></span>  
  
```  
CREATE PROCEDURE SampleProc(@XmlDoc xml) AS ...   
```  
  
 <span data-ttu-id="652c0-110">È possibile utilizzare XQuery per eseguire query su istanze XML archiviate in colonne, parametri o variabili.</span><span class="sxs-lookup"><span data-stu-id="652c0-110">You can use XQuery to query XML instances stored in columns, parameters, or variables.</span></span> <span data-ttu-id="652c0-111">È inoltre possibile utilizzare il linguaggio XML DML (Data Manipulation Language) per l'applicazione di aggiornamenti alle istanze XML.</span><span class="sxs-lookup"><span data-stu-id="652c0-111">You can also use the XML Data Manipulation Language (XML DML) to apply updates to the XML instances.</span></span> <span data-ttu-id="652c0-112">Poiché al momento dello sviluppo lo standard XQuery non prevedeva istruzioni DML per il linguaggio XQuery, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] introduce in XQuery le estensioni del [linguaggio XML DML (Data Modification Language)](/sql/t-sql/xml/xml-data-modification-language-xml-dml) .</span><span class="sxs-lookup"><span data-stu-id="652c0-112">Because the XQuery standard did not define XQuery DML at the time of development, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] introduces [XML Data Modification Language](/sql/t-sql/xml/xml-data-modification-language-xml-dml) extensions to XQuery.</span></span> <span data-ttu-id="652c0-113">Queste estensioni consentono l'esecuzione di operazioni di inserimento, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="652c0-113">These extensions allow you to perform insert, update, and delete operations.</span></span>  
  
## <a name="assigning-defaults"></a><span data-ttu-id="652c0-114">Assegnazione di valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="652c0-114">Assigning Defaults</span></span>  
 <span data-ttu-id="652c0-115">All'interno di una tabella è possibile assegnare un'istanza XML predefinita a una colonna di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="652c0-115">In a table, you can assign a default XML instance to a column of `xml` type.</span></span> <span data-ttu-id="652c0-116">È possibile fornire dati XML predefiniti in una delle due modalità: utilizzando una costante XML o utilizzando un cast esplicito al tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="652c0-116">You can provide the default XML in one of two ways: by using an XML constant, or by using an explicit cast to the `xml` type.</span></span>  
  
 <span data-ttu-id="652c0-117">Per fornire dati XML predefiniti come costante XML, utilizzare la sintassi come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="652c0-117">To provide the default XML as an XML constant, use syntax as shown in the following example.</span></span> <span data-ttu-id="652c0-118">Considerare che la stringa è di tipo CAST implicito al tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="652c0-118">Note that the string is implicitly CAST to `xml` type.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml default N'<element1/><element2/>')  
```  
  
 <span data-ttu-id="652c0-119">Per fornire i dati XML predefiniti come un `CAST` esplicito a `xml`, utilizzare la sintassi come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="652c0-119">To provide the default XML as an explicit `CAST` to `xml`, use syntax as shown in the following example.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml   
                  default CAST(N'<element1/><element2/>' AS xml))  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="652c0-120">supporta inoltre i vincoli NULL e NOT NULL sulle colonne di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="652c0-120">also supports NULL and NOT NULL constraints on columns of `xml` type.</span></span> <span data-ttu-id="652c0-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="652c0-121">For example:</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml NOT NULL)  
```  
  
## <a name="specifying-constraints"></a><span data-ttu-id="652c0-122">Specifica dei vincoli</span><span class="sxs-lookup"><span data-stu-id="652c0-122">Specifying Constraints</span></span>  
 <span data-ttu-id="652c0-123">Durante la creazione di colonne di tipo `xml` è possibile definire vincoli a livello di colonna o di tabella.</span><span class="sxs-lookup"><span data-stu-id="652c0-123">When you create columns of `xml` type, you can define column-level or table-level constraints.</span></span> <span data-ttu-id="652c0-124">Utilizzare i vincoli nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="652c0-124">Use constraints in the following situations:</span></span>  
  
-   <span data-ttu-id="652c0-125">Le regole business non possono essere espresse negli elementi XML Schema.</span><span class="sxs-lookup"><span data-stu-id="652c0-125">Your business rules cannot be expressed in XML schemas.</span></span> <span data-ttu-id="652c0-126">Se ad esempio l'indirizzo di recapito di un fiorista deve essere entro 80 Km dal negozio,</span><span class="sxs-lookup"><span data-stu-id="652c0-126">For example, the delivery address of a flower shop must be within 50 miles of its business location.</span></span> <span data-ttu-id="652c0-127">tale condizione può essere espressa come vincolo sulla colonna XML.</span><span class="sxs-lookup"><span data-stu-id="652c0-127">This can be written as a constraint on the XML column.</span></span> <span data-ttu-id="652c0-128">Il vincolo può includere metodi per il tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="652c0-128">The constraint may involve `xml` data type methods.</span></span>  
  
-   <span data-ttu-id="652c0-129">Il vincolo coinvolge altre colonne XML o non XML nella tabella.</span><span class="sxs-lookup"><span data-stu-id="652c0-129">Your constraint involves other XML or non-XML columns in the table.</span></span> <span data-ttu-id="652c0-130">Un esempio è l'applicazione dell'ID di un cliente (`/Customer/@CustId`) trovato in un'istanza XML per la corrispondenza con il valore in una colonna relazionale CustomerID.</span><span class="sxs-lookup"><span data-stu-id="652c0-130">An example is the enforcement of the ID of a Customer (`/Customer/@CustId`) found in an XML instance to match the value in a relational CustomerID column.</span></span>  
  
 <span data-ttu-id="652c0-131">È possibile specificare vincoli per le colonne di tipi di dati `xml` tipizzate o non tipizzate.</span><span class="sxs-lookup"><span data-stu-id="652c0-131">You can specify constraints for typed or untyped `xml` data type columns.</span></span> <span data-ttu-id="652c0-132">Nella specifica dei vincoli non è tuttavia possibile usare i [metodi con tipo di dati XML](/sql/t-sql/xml/xml-data-type-methods) .</span><span class="sxs-lookup"><span data-stu-id="652c0-132">However, you cannot use the [XML data type methods](/sql/t-sql/xml/xml-data-type-methods) when you specify constraints.</span></span> <span data-ttu-id="652c0-133">Inoltre, notare che il tipo di dati `xml` non supporta la colonna seguente e vincoli della tabella:</span><span class="sxs-lookup"><span data-stu-id="652c0-133">Also, note that the `xml` data type does not support the following column and table constraints:</span></span>  
  
-   <span data-ttu-id="652c0-134">PRIMARY KEY/ FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="652c0-134">PRIMARY KEY/ FOREIGN KEY</span></span>  
  
-   <span data-ttu-id="652c0-135">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="652c0-135">UNIQUE</span></span>  
  
-   <span data-ttu-id="652c0-136">COLLATE</span><span class="sxs-lookup"><span data-stu-id="652c0-136">COLLATE</span></span>  
  
     <span data-ttu-id="652c0-137">XML fornisce una codifica specifica.</span><span class="sxs-lookup"><span data-stu-id="652c0-137">XML provides its own encoding.</span></span> <span data-ttu-id="652c0-138">Le regole di confronto sono applicabili unicamente ai tipi stringa.</span><span class="sxs-lookup"><span data-stu-id="652c0-138">Collations apply to string types only.</span></span> <span data-ttu-id="652c0-139">Il tipo di dati `xml` non è di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="652c0-139">The `xml` data type is not a string type.</span></span> <span data-ttu-id="652c0-140">Fornisce tuttavia la rappresentazione di stringa e consente il cast a e da i tipi di dati stringa.</span><span class="sxs-lookup"><span data-stu-id="652c0-140">However, it does have string representation and allows casting to and from string data types.</span></span>  
  
-   <span data-ttu-id="652c0-141">RULE</span><span class="sxs-lookup"><span data-stu-id="652c0-141">RULE</span></span>  
  
 <span data-ttu-id="652c0-142">Un'alternativa all'utilizzo di vincoli è la creazione di un wrapper, una funzione definita dall'utente per eseguire il wrapping del metodo con tipo di dati `xml` e specificare la funzione definita dall'utente nel vincolo CHECK, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="652c0-142">An alternative to using constraints is to create a wrapper, user-defined function to wrap the `xml` data type method and specify user-defined function in the check constraint as shown in the following example.</span></span>  
  
 <span data-ttu-id="652c0-143">Nell'esempio seguente, il vincolo in `Col2` specifica che tutte le istanze XML archiviate nella colonna devono avere un elemento `<ProductDescription>` contenente un attributo `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="652c0-143">In the following example, the constraint on `Col2` specifies that each XML instance stored in this column must have a `<ProductDescription>` element that contains a `ProductID` attribute.</span></span> <span data-ttu-id="652c0-144">Il vincolo viene imposto da questa funzione definita dall'utente:</span><span class="sxs-lookup"><span data-stu-id="652c0-144">This constraint is enforced by this user-defined function:</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns bit  
AS BEGIN   
RETURN @var.exist('/ProductDescription/@ProductID')  
END  
GO  
```  
  
 <span data-ttu-id="652c0-145">Si noti che il metodo `exist()` con tipo di dati `xml` restituisce `1` se l'elemento `<ProductDescription>` nell'istanza contiene l'attributo `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="652c0-145">Note that the `exist()` method of the `xml` data type returns `1` if the `<ProductDescription>` element in the instance contains the `ProductID` attribute.</span></span> <span data-ttu-id="652c0-146">In caso contrario, viene restituito `0`.</span><span class="sxs-lookup"><span data-stu-id="652c0-146">Otherwise, it returns `0`.</span></span>  
  
 <span data-ttu-id="652c0-147">A questo punto è possibile creare una colonna con vincoli a livello di colonna come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="652c0-147">Now, you can create a table with a column-level constraint as follows:</span></span>  
  
```  
CREATE TABLE T (  
    Col1 int primary key,   
    Col2 xml check(dbo.my_udf(Col2)=1))  
GO  
```  
  
 <span data-ttu-id="652c0-148">L'inserimento seguente ha esito positivo:</span><span class="sxs-lookup"><span data-stu-id="652c0-148">The following insert succeeds:</span></span>  
  
```  
INSERT INTO T values(1,'<ProductDescription ProductID="1" />')  
```  
  
 <span data-ttu-id="652c0-149">L'inserimento seguente ha invece esito negativo, a causa del vincolo:</span><span class="sxs-lookup"><span data-stu-id="652c0-149">Because of the constraint, the following insert fails:</span></span>  
  
```  
INSERT INTO T values(1,'<Product />')  
```  
  
## <a name="same-or-different-table"></a><span data-ttu-id="652c0-150">Utilizzo di un'unica tabella o di più tabelle</span><span class="sxs-lookup"><span data-stu-id="652c0-150">Same or Different Table</span></span>  
 <span data-ttu-id="652c0-151">`xml`È possibile creare una colonna con tipo di dati in una tabella che contiene altre colonne relazionali oppure in una tabella separata con una relazione di chiave esterna con una tabella principale.</span><span class="sxs-lookup"><span data-stu-id="652c0-151">An `xml` data type column can be created in a table that contains other relational columns, or in a separate table with a foreign key relationship to a main table.</span></span>  
  
 <span data-ttu-id="652c0-152">Creare una `xml` colonna con tipo di dati nella stessa tabella quando si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="652c0-152">Create an `xml` data type column in the same table when one of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="652c0-153">L'applicazione esegue operazioni di recupero dei dati sulla colonna XML e non richiede un indice XML su tale colonna.</span><span class="sxs-lookup"><span data-stu-id="652c0-153">Your application performs data retrieval on the XML column and does not require an XML index on the XML column.</span></span>  
  
-   <span data-ttu-id="652c0-154">Si desidera compilare un indice XML sulla colonna con tipo di dati `xml` e la chiave primaria della tabella principale coincide con la chiave di clustering.</span><span class="sxs-lookup"><span data-stu-id="652c0-154">You want to build an XML index on the `xml` data type column and the primary key of the main table is the same as its clustering key.</span></span> <span data-ttu-id="652c0-155">Per altre informazioni, vedere [Indici XML &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="652c0-155">For more information, see [XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span></span>  
  
 <span data-ttu-id="652c0-156">È consigliabile creare la colonna con tipo di dati `xml` in una tabella separata se si verificano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="652c0-156">Create the `xml` data type column in a separate table if the following conditions are true:</span></span>  
  
-   <span data-ttu-id="652c0-157">Si desidera compilare un indice XML sulla colonna con tipo di dati `xml`, ma la chiave primaria della tabella principale è diversa dalla chiave di clustering, la tabella principale non ha una chiave primaria, oppure la tabella principale è un heap, ovvero è priva di chiave di clustering.</span><span class="sxs-lookup"><span data-stu-id="652c0-157">You want to build an XML index on the `xml` data type column, but the primary key of the main table is different from its clustering key, or the main table does not have a primary key, or the main table is a heap (no clustering key).</span></span> <span data-ttu-id="652c0-158">Questa situazione può verificarsi quando si utilizza una tabella principale esistente.</span><span class="sxs-lookup"><span data-stu-id="652c0-158">This may be true if the main table already exists.</span></span>  
  
-   <span data-ttu-id="652c0-159">Si desidera evitare che l'analisi della tabella venga rallentata a causa della presenza della colonna XML,</span><span class="sxs-lookup"><span data-stu-id="652c0-159">You do not want table scans to slow down because of the presence of the XML column in the table.</span></span> <span data-ttu-id="652c0-160">che utilizza spazio sia che venga archiviata all'interno delle righe che all'esterno delle righe.</span><span class="sxs-lookup"><span data-stu-id="652c0-160">This uses space whether it is stored in-row or out-of-row.</span></span>  
  
  
