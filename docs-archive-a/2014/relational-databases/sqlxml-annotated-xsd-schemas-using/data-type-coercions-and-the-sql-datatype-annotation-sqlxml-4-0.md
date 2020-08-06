---
title: 'Coercizioni dei tipi di dati e annotazione sql: DataType (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping data types [SQLXML]
- type attribute
- sql:datatype
- data types [SQLXML], converting
- annotated XSD schemas, mapping data types
- xsd:type
- datatype annotation
- converting data types [SQLXML]
- data types [SQLXML], mapping data types
- XSD schemas [SQLXML], mapping data types
ms.assetid: db192105-e8aa-4392-b812-9d727918c005
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f1b0af93e3b596d74bc107ab6947b9855a2cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628609"
---
# <a name="data-type-coercions-and-the-sqldatatype-annotation-sqlxml-40"></a><span data-ttu-id="d5389-102">Coercizioni dei tipi di dati e annotazione sql:datatype (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d5389-102">Data Type Coercions and the sql:datatype Annotation (SQLXML 4.0)</span></span>
  <span data-ttu-id="d5389-103">In uno schema XDR l'attributo `xsd:type` specifica il tipo di dati XSD di un elemento o di un attributo.</span><span class="sxs-lookup"><span data-stu-id="d5389-103">In an XSD schema, the `xsd:type` attribute specifies the XSD data type of an element or attribute.</span></span> <span data-ttu-id="d5389-104">Quando viene utilizzato uno schema XSD per estrarre dati dal database, il tipo di dati specificato viene utilizzato per formattare i dati.</span><span class="sxs-lookup"><span data-stu-id="d5389-104">When an XSD schema is used to extract data from the database, the data type specified is used to format the data.</span></span>  
  
 <span data-ttu-id="d5389-105">Oltre a specificare un tipo XSD in uno schema, è inoltre possibile specificare un tipo di dati di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando l'annotazione `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="d5389-105">In addition to specifying an XSD type in a schema, you can also specify a Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type by using the `sql:datatype` annotation.</span></span> <span data-ttu-id="d5389-106">Le annotazioni `xsd:type` e `sql:datatype` controllano il mapping tra i tipi di dati XSD e i tipi di dati di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5389-106">The `xsd:type` and `sql:datatype` attributes control the mapping between XSD data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
## <a name="xsdtype-attribute"></a><span data-ttu-id="d5389-107">Attributo xsd:type</span><span class="sxs-lookup"><span data-stu-id="d5389-107">xsd:type Attribute</span></span>  
 <span data-ttu-id="d5389-108">È possibile utilizzare l'attributo `xsd:type` per specificare il tipo di dati XML di un attributo o di un elemento con mapping a una colonna.</span><span class="sxs-lookup"><span data-stu-id="d5389-108">You can use the `xsd:type` attribute to specify the XML data type of an attribute or element that maps to a column.</span></span> <span data-ttu-id="d5389-109">`xsd:type` influisce sul documento restituito dal server nonché sulla query XPath eseguita.</span><span class="sxs-lookup"><span data-stu-id="d5389-109">The `xsd:type` affects the document that is returned from the server and also the XPath query that is executed.</span></span> <span data-ttu-id="d5389-110">Quando viene eseguita una query XPath su uno schema di mapping contenente `xsd:type`, XPath utilizza il tipo di dati specificato durante l'elaborazione della query.</span><span class="sxs-lookup"><span data-stu-id="d5389-110">When an XPath query is executed against a mapping schema that contains `xsd:type`, XPath uses the specified data type when it processes the query.</span></span> <span data-ttu-id="d5389-111">Per ulteriori informazioni sull'utilizzo di XPath `xsd:type` , vedere [mapping dei tipi di dati XSD ai tipi di dati XPath &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d5389-111">For more information about how XPath uses `xsd:type`, see [Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="d5389-112">In un documento restituito tutti i tipi di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono convertiti in rappresentazioni di stringa.</span><span class="sxs-lookup"><span data-stu-id="d5389-112">In a returned document, all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types are converted into string representations.</span></span> <span data-ttu-id="d5389-113">Alcuni tipi di dati richiedono conversioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="d5389-113">Some data types require additional conversions.</span></span> <span data-ttu-id="d5389-114">Nella tabella seguente sono elencate le conversioni utilizzate per i diversi valori di `xsd:type`.</span><span class="sxs-lookup"><span data-stu-id="d5389-114">The following table lists the conversions that are used for various `xsd:type` values.</span></span>  
  
|<span data-ttu-id="d5389-115">Tipo di dati XSD</span><span class="sxs-lookup"><span data-stu-id="d5389-115">XSD data type</span></span>|<span data-ttu-id="d5389-116">Conversione SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5389-116">SQL Server conversion</span></span>|  
|-------------------|---------------------------|  
|<span data-ttu-id="d5389-117">Boolean</span><span class="sxs-lookup"><span data-stu-id="d5389-117">Boolean</span></span>|<span data-ttu-id="d5389-118">CONVERT(bit, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="d5389-118">CONVERT(bit, COLUMN)</span></span>|  
|<span data-ttu-id="d5389-119">Data</span><span class="sxs-lookup"><span data-stu-id="d5389-119">Date</span></span>|<span data-ttu-id="d5389-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span><span class="sxs-lookup"><span data-stu-id="d5389-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span></span>|  
|<span data-ttu-id="d5389-121">decimal</span><span class="sxs-lookup"><span data-stu-id="d5389-121">decimal</span></span>|<span data-ttu-id="d5389-122">CONVERT(money, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="d5389-122">CONVERT(money, COLUMN)</span></span>|  
|<span data-ttu-id="d5389-123">id/idref/idrefs</span><span class="sxs-lookup"><span data-stu-id="d5389-123">id/idref/idrefs</span></span>|<span data-ttu-id="d5389-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="d5389-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="d5389-125">nmtoken/nmtokens</span><span class="sxs-lookup"><span data-stu-id="d5389-125">nmtoken/nmtokens</span></span>|<span data-ttu-id="d5389-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="d5389-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="d5389-127">Tempo</span><span class="sxs-lookup"><span data-stu-id="d5389-127">Time</span></span>|<span data-ttu-id="d5389-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span><span class="sxs-lookup"><span data-stu-id="d5389-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span></span>|  
|<span data-ttu-id="d5389-129">Tutti gli altri</span><span class="sxs-lookup"><span data-stu-id="d5389-129">All others</span></span>|<span data-ttu-id="d5389-130">Nessuna conversione aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="d5389-130">No additional conversion</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="d5389-131">Alcuni dei valori restituiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] potrebbero non essere compatibili con i tipi di dati XML specificati tramite `xsd:type`, in quanto la conversione non è possibile (ad esempio, la conversione di "XYZ" in un tipo di dati `decimal` ) o perché il valore supera l'intervallo del tipo di dati (ad esempio, la conversione di -100000 in un tipo XSD `UnsignedShort`).</span><span class="sxs-lookup"><span data-stu-id="d5389-131">Some of the values returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might not be compatible with the XML data types that are specified by using `xsd:type`, either because the conversion is not possible (for example, converting "XYZ" to a `decimal` data type) or because the value exceeds the range of that data type (for example, -100000 converted to an `UnsignedShort` XSD type).</span></span> <span data-ttu-id="d5389-132">Conversioni di tipi incompatibili possono restituire documenti XML non validi o errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5389-132">Incompatible type conversions might result in XML documents that are not valid, or in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] errors.</span></span>  
  
## <a name="mapping-from-sql-server-data-types-to-xsd-data-types"></a><span data-ttu-id="d5389-133">Mapping dai tipi di dati di SQL Server a tipi di dati XSD</span><span class="sxs-lookup"><span data-stu-id="d5389-133">Mapping from SQL Server Data Types to XSD Data Types</span></span>  
 <span data-ttu-id="d5389-134">Nella tabella seguente viene illustrato un mapping evidente dai tipi di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ai tipi di dati XSD.</span><span class="sxs-lookup"><span data-stu-id="d5389-134">The following table shows an obvious mapping from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types to XSD data types.</span></span> <span data-ttu-id="d5389-135">Se il tipo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è noto, nella tabella è disponibile il tipo XSD corrispondente che è possibile specificare nello schema XSD.</span><span class="sxs-lookup"><span data-stu-id="d5389-135">If you know the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type, this table provides the corresponding XSD type that you can specify in the XSD schema.</span></span>  
  
|<span data-ttu-id="d5389-136">Tipo di dati di SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5389-136">SQL Server data type</span></span>|<span data-ttu-id="d5389-137">Tipo di dati XSD</span><span class="sxs-lookup"><span data-stu-id="d5389-137">XSD data type</span></span>|  
|--------------------------|-------------------|  
|`bigint`|`long`|  
|`binary`|`base64Binary`|  
|`bit`|`boolean`|  
|`char`|`string`|  
|`datetime`|`dateTime`|  
|`decimal`|`decimal`|  
|`float`|`double`|  
|`image`|`base64Binary`|  
|`int`|`int`|  
|`money`|`decimal`|  
|`nchar`|`string`|  
|`ntext`|`string`|  
|`nvarchar`|`string`|  
|`numeric`|`decimal`|  
|`real`|`float`|  
|`smalldatetime`|`dateTime`|  
|`smallint`|`short`|  
|`smallmoney`|`decimal`|  
|`sql_variant`|`string`|  
|`sysname`|`string`|  
|`text`|`string`|  
|`timestamp`|`dateTime`|  
|`tinyint`|`unsignedByte`|  
|`varbinary`|`base64Binary`|  
|`varchar`|`string`|  
|`uniqueidentifier`|`string`|  
  
## <a name="sqldatatype-annotation"></a><span data-ttu-id="d5389-138">Annotazione sql:datatype</span><span class="sxs-lookup"><span data-stu-id="d5389-138">sql:datatype Annotation</span></span>  
 <span data-ttu-id="d5389-139">L'annotazione `sql:datatype` viene utilizzata per indicare il tipo di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e deve essere specificata nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5389-139">The `sql:datatype` annotation is used to specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type; this annotation must be specified when:</span></span>  
  
-   <span data-ttu-id="d5389-140">Si esegue il caricamento bulk in una `dateTime` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] colonna da un `dateTime` tipo XSD, `date` o `time` .</span><span class="sxs-lookup"><span data-stu-id="d5389-140">You are bulk loading into a `dateTime`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column from an XSD `dateTime`, `date`, or `time` type.</span></span> <span data-ttu-id="d5389-141">In questo caso, è necessario identificare il tipo di dati della colonna di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="d5389-141">In this case, you must identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column data type by using `sql:datatype="dateTime"`.</span></span> <span data-ttu-id="d5389-142">Questa regola si applica anche agli updategram.</span><span class="sxs-lookup"><span data-stu-id="d5389-142">This rule also applies to updategrams.</span></span>  
  
-   <span data-ttu-id="d5389-143">Si esegue il caricamento bulk in una colonna di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` tipo e il valore XSD è un GUID che include parentesi graffe ({e}).</span><span class="sxs-lookup"><span data-stu-id="d5389-143">You are bulk loading into a column of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` type and the XSD value is a GUID that includes braces ({ and }).</span></span> <span data-ttu-id="d5389-144">Quando si specifica `sql:datatype="uniqueidentifier"`, le parentesi graffe vengono rimosse dal valore prima che questo venga inserito nella colonna.</span><span class="sxs-lookup"><span data-stu-id="d5389-144">When you specify `sql:datatype="uniqueidentifier"`, the braces are removed from the value before it is inserted in the column.</span></span> <span data-ttu-id="d5389-145">Se non si specifica `sql:datatype`, il valore viene inviato con le parentesi graffe e l'inserimento o l'aggiornamento non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="d5389-145">If `sql:datatype` is not specified, the value is sent with the braces, and the insert or update fails.</span></span>  
  
-   <span data-ttu-id="d5389-146">Viene eseguito il mapping del tipo di dati XML `base64Binary` a diversi tipi di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (`binary`, `image` o `varbinary`).</span><span class="sxs-lookup"><span data-stu-id="d5389-146">The XML data type `base64Binary` maps to various [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types (`binary`, `image`, or `varbinary`).</span></span> <span data-ttu-id="d5389-147">Per eseguire il mapping del tipo di dati XML `base64Binary` a un tipo di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specifico, utilizzare l'annotazione `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="d5389-147">To map the XML data type `base64Binary` to a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, use the `sql:datatype` annotation.</span></span> <span data-ttu-id="d5389-148">Questa annotazione specifica il tipo di dati esplicito di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] della colonna a cui viene mappato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="d5389-148">This annotation specifies the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the column to which the attribute maps.</span></span> <span data-ttu-id="d5389-149">Ciò risulta utile durante l'archiviazione dei dati nei database.</span><span class="sxs-lookup"><span data-stu-id="d5389-149">This is useful when data is being stored in the databases.</span></span> <span data-ttu-id="d5389-150">Specificando l'annotazione `sql:datatype`, è possibile identificare il tipo di dati esplicito di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5389-150">By specifying the `sql:datatype` annotation, you can identify the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="d5389-151">È in genere consigliabile specificare `sql:datatype` nello schema.</span><span class="sxs-lookup"><span data-stu-id="d5389-151">It is generally recommended that you specify `sql:datatype` in the schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d5389-152">Esempi</span><span class="sxs-lookup"><span data-stu-id="d5389-152">Examples</span></span>  
 <span data-ttu-id="d5389-153">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="d5389-153">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="d5389-154">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="d5389-154">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-xsdtype"></a><span data-ttu-id="d5389-155">R.</span><span class="sxs-lookup"><span data-stu-id="d5389-155">A.</span></span> <span data-ttu-id="d5389-156">Definizione dell'attributo xsd:type</span><span class="sxs-lookup"><span data-stu-id="d5389-156">Specifying xsd:type</span></span>  
 <span data-ttu-id="d5389-157">In questo esempio viene illustrato il modo in cui un tipo XSD `date` specificato tramite l'attributo `xsd:type` nello schema influisce sul documento XML risultante.</span><span class="sxs-lookup"><span data-stu-id="d5389-157">This example shows how an XSD `date` type that is specified by using the `xsd:type` attribute in the schema affects the resulting XML document.</span></span> <span data-ttu-id="d5389-158">Lo schema fornisce una vista XML della tabella Sales.SalesOrderHeader nel database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d5389-158">The schema provides an XML view of the Sales.SalesOrderHeader table in the AdventureWorks database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader">  
     <xsd:complexType>  
       <xsd:attribute name="SalesOrderID" type="xsd:string" />   
       <xsd:attribute name="CustomerID"   type="xsd:string" />   
       <xsd:attribute name="OrderDate"    type="xsd:date" />   
       <xsd:attribute name="DueDate"  />   
       <xsd:attribute name="ShipDate"  type="xsd:time" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="d5389-159">In questo schema XSD sono inclusi tre attributi che restituiscono un valore di data da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5389-159">In this XSD schema, there are three attributes that return a date value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d5389-160">Esaminare i casi seguenti per lo schema:</span><span class="sxs-lookup"><span data-stu-id="d5389-160">When the schema:</span></span>  
  
-   <span data-ttu-id="d5389-161">Specifica `xsd:type=date` sull'attributo **OrderDate** , viene visualizzata la parte relativa alla data del valore restituito da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'attributo **OrderDate** .</span><span class="sxs-lookup"><span data-stu-id="d5389-161">Specifies `xsd:type=date` on the **OrderDate** attribute, the date part of the value returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **OrderDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="d5389-162">Specifica nell' `xsd:type=time` attributo **ShipDate** , viene visualizzata la parte relativa all'ora del valore restituito da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'attributo **ShipDate** .</span><span class="sxs-lookup"><span data-stu-id="d5389-162">Specifies `xsd:type=time` on the **ShipDate** attribute, the time part of the value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **ShipDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="d5389-163">Non specifica `xsd:type` sull'attributo **DueDate** , viene visualizzato lo stesso valore restituito da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5389-163">Does not specify `xsd:type` on the **DueDate** attribute, the same value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is displayed.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="d5389-164">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="d5389-164">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="d5389-165">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="d5389-165">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="d5389-166">Salvare il file con il nome xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="d5389-166">Save the file as xsdType.xml.</span></span>  
  
2.  <span data-ttu-id="d5389-167">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="d5389-167">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="d5389-168">Salvare il file con il nome xsdTypeT.xml nella stessa directory in cui è stato salvato xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="d5389-168">Save the file as xsdTypeT.xml in the same directory where you saved xsdType.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="xsdType.xml">  
        /Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="d5389-169">Il percorso di directory specificato per lo schema di mapping (xsdType.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="d5389-169">The directory path specified for the mapping schema (xsdType.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="d5389-170">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5389-170">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\xsdType.xml"  
    ```  
  
3.  <span data-ttu-id="d5389-171">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="d5389-171">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="d5389-172">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d5389-172">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="d5389-173">Di seguito è riportato il set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="d5389-173">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43659"   
         CustomerID="676"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
  <Order SalesOrderID="43660"   
         CustomerID="117"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
 ...  
</ROOT>  
```  
  
 <span data-ttu-id="d5389-174">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="d5389-174">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader">  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="CustomerID"  />  
    <AttributeType name="OrderDate" dt:type="date" />  
    <AttributeType name="DueDate" />  
    <AttributeType name="ShipDate" dt:type="time" />  
  
    <attribute type="SalesOrderID" sql:field="OrderID" />  
    <attribute type="CustomerID" sql:field="CustomerID" />  
    <attribute type="OrderDate" sql:field="OrderDate" />  
    <attribute type="DueDate" sql:field="DueDate" />  
    <attribute type="ShipDate" sql:field="ShipDate" />  
</ElementType>  
</Schema>  
```  
  
### <a name="b-specifying-sql-data-type-using-sqldatatype"></a><span data-ttu-id="d5389-175">B.</span><span class="sxs-lookup"><span data-stu-id="d5389-175">B.</span></span> <span data-ttu-id="d5389-176">Definizione del tipo di dati SQL tramite sql:datatype</span><span class="sxs-lookup"><span data-stu-id="d5389-176">Specifying SQL data type using sql:datatype</span></span>  
 <span data-ttu-id="d5389-177">Per un esempio funzionante, vedere l'esempio G in [esempi di caricamento bulk XML &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d5389-177">For a working sample, see Example G in [XML Bulk Load Examples &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span></span> <span data-ttu-id="d5389-178">In questo esempio viene eseguito il caricamento bulk di un valore GUID che include"{" e "}".</span><span class="sxs-lookup"><span data-stu-id="d5389-178">In this example, a GUID value including "{" and "}" is bulk loaded.</span></span> <span data-ttu-id="d5389-179">Lo schema in questo esempio specifica `sql:datatype` per identificare il tipo di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come `uniqueidentifier`.</span><span class="sxs-lookup"><span data-stu-id="d5389-179">The schema in this example specifies `sql:datatype` to identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as `uniqueidentifier`.</span></span> <span data-ttu-id="d5389-180">In questo esempio vengono indicati i casi in cui è necessario specificare `sql:datatype` nello schema.</span><span class="sxs-lookup"><span data-stu-id="d5389-180">This example illustrate when `sql:datatype` must be specified in the schema.</span></span>  
  
  
