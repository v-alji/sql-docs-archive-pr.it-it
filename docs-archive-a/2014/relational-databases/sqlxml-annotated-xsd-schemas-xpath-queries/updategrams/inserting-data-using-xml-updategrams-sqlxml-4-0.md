---
title: Inserimento di dati mediante updategram XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- xsi:nil attribute
- unique values
- <after> block
- id attribute
- data insertions [SQLXML]
- nil attribute
- <before> block
- updg:guid attribute
- multiple record insertions
- returnid attribute
- updategrams [SQLXML], inserting data
- updg:at-identity attribute
- invalid characters [SQLXML]
- updg:returnid attribute
- updg:id attribute
- namespaces [SQLXML], updategrams
- IDENTITY-type column
- guid attribute
- record insertion [SQLXML]
- null values [SQLXML]
- at-identity attribute
- xml data type [SQL Server], SQLXML
ms.assetid: 4dc48762-bc12-43fb-b356-ea1b9c1e287e
author: rothja
ms.author: jroth
ms.openlocfilehash: a80f2cb157e59f30ebcbff5c14abba1003de9e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716128"
---
# <a name="inserting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="bbb4d-102">Inserimento di dati mediante updategram XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="bbb4d-102">Inserting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="bbb4d-103">Un updategram indica un'operazione di inserimento quando un'istanza di record viene visualizzata nel **\<after>** blocco ma non nel **\<before>** blocco corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-103">An updategram indicates an insert operation when a record instance appears in the **\<after>** block but not in the corresponding **\<before>** block.</span></span> <span data-ttu-id="bbb4d-104">In questo caso, l'updategram inserisce il record nel **\<after>** blocco nel database.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-104">In this case, the updategram inserts the record in the **\<after>** block into the database.</span></span>  
  
 <span data-ttu-id="bbb4d-105">Il formato dell'updategram per un'operazione di inserimento è il seguente:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-105">This is the updategram format for an insert operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   [<updg:before>  
   </updg:before>]  
    <updg:after [updg:returnid="x y ...] >  
       <ElementName [updg:id="value"]   
                   [updg:at-identity="x"]   
                   [updg:guid="y"]  
                   attribute="value"   
                   attribute="value"  
                   ...  
       />  
      [<ElementName .../>... ]  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
## <a name="before-block"></a><span data-ttu-id="bbb4d-106">\<before>Blocco</span><span class="sxs-lookup"><span data-stu-id="bbb4d-106">\<before> Block</span></span>  
 <span data-ttu-id="bbb4d-107">Il **\<before>** blocco può essere omesso per un'operazione di inserimento.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-107">The **\<before>** block can be omitted for an insert operation.</span></span> <span data-ttu-id="bbb4d-108">Se l' `mapping-schema` attributo facoltativo non viene specificato, l'oggetto **\<ElementName>** specificato nell'updategram esegue il mapping a una tabella di database e gli attributi o gli elementi figlio vengono mappati alle colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-108">If the optional `mapping-schema` attribute is not specified, the **\<ElementName>** that is specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
## <a name="after-block"></a><span data-ttu-id="bbb4d-109">\<after>Blocco</span><span class="sxs-lookup"><span data-stu-id="bbb4d-109">\<after> Block</span></span>  
 <span data-ttu-id="bbb4d-110">È possibile specificare uno o più record nel **\<after>** blocco.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-110">You can specify one or more records in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="bbb4d-111">Se il **\<after>** blocco non fornisce un valore per una colonna specifica, l'updategram utilizzerà il valore predefinito specificato nello schema con annotazioni (se è stato specificato uno schema).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-111">If the **\<after>** block does not supply a value for a particular column, the updategram uses the default value that is specified in the annotated schema (if a schema has been specified).</span></span> <span data-ttu-id="bbb4d-112">Se lo schema non specifica un valore predefinito per la colonna, l'updategram non specifica alcun valore esplicito per questa colonna e, invece, assegna il [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] valore predefinito (se specificato) a questa colonna.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-112">If the schema does not specify a default value for the column, the updategram does not specify any explicit value to this column and, instead, assigns the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value (if specified) to this column.</span></span> <span data-ttu-id="bbb4d-113">Se non è presente alcun valore predefinito di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e la colonna accetta un valore NULL, l'updategram imposta il valore della colonna su NULL.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-113">If there is no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value and the column accepts a NULL value, the updategram sets the column value to NULL.</span></span> <span data-ttu-id="bbb4d-114">Se la colonna non ha un valore predefinito e non accetta un valore NULL, il comando non riesce e l'updategram restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-114">If the column neither has a default value nor accepts a NULL value, the command fails and the updategram returns an error.</span></span> <span data-ttu-id="bbb4d-115">L'attributo `updg:returnid` facoltativo viene utilizzato per restituire il valore Identity generato dal sistema quando viene aggiunto un record in una tabella con una colonna di tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-115">The optional `updg:returnid` attribute is used to return the identity value that is generated by the system when a record is added in a table with an IDENTITY-type column.</span></span>  
  
## <a name="updgid-attribute"></a><span data-ttu-id="bbb4d-116">Attributo updg:id</span><span class="sxs-lookup"><span data-stu-id="bbb4d-116">updg:id Attribute</span></span>  
 <span data-ttu-id="bbb4d-117">Se l'updategram inserisce solo record, non richiede l'attributo `updg:id`.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-117">If the updategram is inserting only records, the updategram does not require the `updg:id` attribute.</span></span> <span data-ttu-id="bbb4d-118">Per ulteriori informazioni su `updg:id` , vedere [aggiornamento di dati mediante updategram XML &#40;SQLXML 4,0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-118">For more information about `updg:id`, see [Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="updgat-identity-attribute"></a><span data-ttu-id="bbb4d-119">Attributo updg:at-identity</span><span class="sxs-lookup"><span data-stu-id="bbb4d-119">updg:at-identity Attribute</span></span>  
 <span data-ttu-id="bbb4d-120">Quando un updategram inserisce un record in una tabella nella quale è presente una colonna di tipo IDENTITY, l'updategram può acquisire il valore assegnato al sistema mediante l'attributo `updg:at-identity` facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-120">When an updategram inserts a record in a table that has an IDENTITY-type column, the updategram can capture the system assigned value by using the optional `updg:at-identity` attribute.</span></span> <span data-ttu-id="bbb4d-121">L'updategram potrà quindi utilizzare questo valore nelle operazioni successive.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-121">The updategram can then use this value in subsequent operations.</span></span> <span data-ttu-id="bbb4d-122">Al termine dell'esecuzione dell'updategram, è possibile restituire il valore Identity generato specificando l'attributo `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-122">Upon execution of the updategram, you can return the identity value that is generated by specifying the `updg:returnid` attribute.</span></span>  
  
## <a name="updgguid-attribute"></a><span data-ttu-id="bbb4d-123">Attributo updg:guid</span><span class="sxs-lookup"><span data-stu-id="bbb4d-123">updg:guid Attribute</span></span>  
 <span data-ttu-id="bbb4d-124">L'attributo `updg:guid` è un attributo facoltativo che genera un identificatore univoco globale.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-124">The `updg:guid` attribute is an optional attribute that generates a globally unique identifier.</span></span> <span data-ttu-id="bbb4d-125">Questo valore rimane nell'ambito per l'intero **\<sync>** blocco in cui è specificato.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-125">This value remains in scope for the entire **\<sync>** block in which it is specified.</span></span> <span data-ttu-id="bbb4d-126">È possibile utilizzare questo valore in qualsiasi punto del **\<sync>** blocco.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-126">You can use this value anywhere in the **\<sync>** block.</span></span> <span data-ttu-id="bbb4d-127">L'attributo chiama la `NEWGUID()` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] funzione per generare l'identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-127">The attribute calls the `NEWGUID()`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] function to generate the unique identifier.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="bbb4d-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="bbb4d-128">Examples</span></span>  
 <span data-ttu-id="bbb4d-129">Per creare esempi funzionanti utilizzando gli esempi seguenti, è necessario soddisfare i requisiti specificati nei [requisiti per l'esecuzione di esempi SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-129">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="bbb4d-130">Prima di utilizzare gli esempi dell'updategram, si tenga presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-130">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="bbb4d-131">La maggior parte degli esempi utilizza il mapping predefinito, ovvero non viene specificato alcuno schema di mapping nell'updategram.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-131">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="bbb4d-132">Per ulteriori esempi di updategram che utilizzano schemi di mapping, vedere [specifica di uno schema di mapping con annotazioni in un Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-132">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="bbb4d-133">Nella maggior parte degli esempi viene utilizzato il database di esempio [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbb4d-133">Most of the examples use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="bbb4d-134">Tutti gli aggiornamenti vengono applicati alle tabelle di questo database.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-134">All the updates are applied to the tables in this database.</span></span>  
  
### <a name="a-inserting-a-record-by-using-an-updategram"></a><span data-ttu-id="bbb4d-135">R.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-135">A.</span></span> <span data-ttu-id="bbb4d-136">Inserimento di un record mediante un updategram</span><span class="sxs-lookup"><span data-stu-id="bbb4d-136">Inserting a record by using an updategram</span></span>  
 <span data-ttu-id="bbb4d-137">Questo updategram incentrato sugli attributi inserisce un record nella tabella HumanResources.Employee del database [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbb4d-137">This attribute-centric updategram inserts a record in the HumanResources.Employee table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="bbb4d-138">In questo esempio l'updategram non specifica uno schema di mapping,</span><span class="sxs-lookup"><span data-stu-id="bbb4d-138">In this example, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="bbb4d-139">pertanto utilizza il mapping predefinito nel quale il nome dell'elemento esegue il mapping a un nome di tabella e gli attributi o gli elementi figlio eseguono il mapping alle colonne della tabella stessa.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-139">Therefore, the updategram uses default mapping, in which the element name maps to a table name and the attributes or child elements map to columns in that table.</span></span>  
  
 <span data-ttu-id="bbb4d-140">Lo schema di [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] per la tabella HumanResources.Department impone una restrizione 'non null' per tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-140">The [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] schema for the HumanResources.Department table imposes a 'not null' restriction on all columns.</span></span> <span data-ttu-id="bbb4d-141">updategram dovrà pertanto includere i valori specificati per tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-141">Therefore, the updategram must include values specified for all columns.</span></span> <span data-ttu-id="bbb4d-142">DepartmentID è una colonna di tipo IDENTITY,</span><span class="sxs-lookup"><span data-stu-id="bbb4d-142">The DepartmentID is an IDENTITY-type column.</span></span> <span data-ttu-id="bbb4d-143">pertanto per tale colonna non viene specificato alcun valore.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-143">Therefore, no values are specified for it.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name="New Product Research"   
            GroupName="Research and Development"   
            ModifiedDate="2010-08-31"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="bbb4d-144">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="bbb4d-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="bbb4d-145">Copiare l'updategram sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-145">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-146">Salvare il file con il nome MyUpdategram.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-146">Save the file as MyUpdategram.xml.</span></span>  
  
2.  <span data-ttu-id="bbb4d-147">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-147">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="bbb4d-148">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-148">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="bbb4d-149">In un mapping incentrato sugli elementi l'updategram sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-149">In an element-centric mapping, the updategram looks like this:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department>  
            <Name> New Product Research </Name>  
            <GroupName> Research and Development </GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="bbb4d-150">In un updategram in modalità mista (incentrato sugli attributi e incentrato sugli elementi) un elemento può avere sia attributi sia sottoelementi, come mostrato in questo updategram:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-150">In a mixed-mode (element-centric and attribute-centric) updategram, an element can have both attributes and subelements, as shown in this updategram:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name=" New Product Research "   
            <GroupName>Research and Development</GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="b-inserting-multiple-records-by-using-an-updategram"></a><span data-ttu-id="bbb4d-151">B.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-151">B.</span></span> <span data-ttu-id="bbb4d-152">Inserimento di più record mediante un updategram</span><span class="sxs-lookup"><span data-stu-id="bbb4d-152">Inserting multiple records by using an updategram</span></span>  
 <span data-ttu-id="bbb4d-153">Questo updategram aggiunge due nuovi record di spostamento alla tabella HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-153">This updategram adds two new shift records to the HumanResources.Shift table.</span></span> <span data-ttu-id="bbb4d-154">L'updategram non specifica il blocco facoltativo **\<before>** .</span><span class="sxs-lookup"><span data-stu-id="bbb4d-154">The updategram does not specify the optional **\<before>** block.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="bbb4d-155">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="bbb4d-155">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="bbb4d-156">Copiare l'updategram sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-156">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-157">Salvare il file con il nome Updategram-AddShifts.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-157">Save the file as Updategram-AddShifts.xml.</span></span>  
  
2.  <span data-ttu-id="bbb4d-158">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="bbb4d-159">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="bbb4d-160">Un'altra versione di questo esempio è un updategram che usa due **\<after>** blocchi separati anziché un blocco per inserire i due dipendenti.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-160">Another version of this example is an updategram that uses two separate **\<after>** blocks instead of one block to insert the two employees.</span></span> <span data-ttu-id="bbb4d-161">Questo updategram è valido e può essere codificato come segue:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-161">This is valid and can be encoded as follows:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after >  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="c-working-with-valid-sql-server-characters-that-are-not-valid-in-xml"></a><span data-ttu-id="bbb4d-162">C.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-162">C.</span></span> <span data-ttu-id="bbb4d-163">Utilizzo di caratteri validi in SQL Server che non sono validi in XML</span><span class="sxs-lookup"><span data-stu-id="bbb4d-163">Working with valid SQL Server characters that are not valid in XML</span></span>  
 <span data-ttu-id="bbb4d-164">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] i nomi di tabella possono includere uno spazio, ad esempio la tabella Dettagli ordine nel database Northwind.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-164">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space, such as the Order Details table in the Northwind database.</span></span> <span data-ttu-id="bbb4d-165">Tuttavia, questo non è valido nei caratteri XML che sono [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identificatori validi, ma non è possibile codificare identificatori XML validi con ' __xHHHH \_ \_ ' come valore di codifica, dove HHHH rappresenta il codice UCS-2 esadecimale a quattro cifre per il carattere nell'ordine del primo bit più significativo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-165">However, this is not valid in XML characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but not valid XML identifiers can be encoded using '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bbb4d-166">In questo esempio viene utilizzato il database Northwind,</span><span class="sxs-lookup"><span data-stu-id="bbb4d-166">This example uses the Northwind database.</span></span> <span data-ttu-id="bbb4d-167">È possibile installare il database Northwind utilizzando uno script SQL disponibile per il download da questo [sito Web Microsoft](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-167">You can install the Northwind database by using an SQL script available for download from this [Microsoft Web site](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>  
  
 <span data-ttu-id="bbb4d-168">Il nome dell'elemento deve inoltre essere racchiuso tra parentesi ([ ]).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-168">Also, the element name must be enclosed within brackets ([ ]).</span></span> <span data-ttu-id="bbb4d-169">Poiché i caratteri [e] non sono validi in XML, è necessario codificarli come _x005B \_ e _x005D \_ rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-169">Because the characters [and] are not valid in XML, you must encode them as _x005B\_ and _x005D\_, respectively.</span></span> <span data-ttu-id="bbb4d-170">Se si utilizza uno schema di mapping, è possibile fornire nomi di elemento che non contengono caratteri non validi, ad esempio spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-170">(If you use a mapping schema, you can provide element names that do not contain characters that are not valid, such as white spaces.</span></span> <span data-ttu-id="bbb4d-171">Lo schema di mapping esegue il mapping richiesto, pertanto non è necessario eseguire la codifica per questi caratteri.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-171">The mapping schema does the necessary mapping; therefore, you do not need to encode for these characters).</span></span>  
  
 <span data-ttu-id="bbb4d-172">Questo updategram aggiunge un record alla tabella Dettagli ordine del database Northwind:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-172">This updategram adds a record to the Order Details table in the Northwind database:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <_x005B_Order_x0020_Details_x005D_ OrderID="1"  
            ProductID="11"  
            UnitPrice="$1.0"  
            Quantity="1"  
            Discount="0.0" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="bbb4d-173">La colonna UnitPrice della tabella Dettagli ordine è del tipo `money`.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-173">The UnitPrice column in the Order Details table is of the `money` type.</span></span> <span data-ttu-id="bbb4d-174">Per applicare la conversione di tipo appropriata (da un tipo `string` a un tipo `money`), è necessario aggiungere il simbolo del dollaro ($) come parte del valore.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-174">To apply the appropriate type conversion (from a `string` type to a `money` type), the dollar sign character ($) must be added as part of the value.</span></span> <span data-ttu-id="bbb4d-175">Se nell'updategram non è specificato uno schema di mapping, viene valutato il primo carattere del valore di `string`.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-175">If the updategram does not specify a mapping schema, the first character of the `string` value is evaluated.</span></span> <span data-ttu-id="bbb4d-176">Se il primo carattere è un segno di dollaro ($), viene applicata la conversione appropriata.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-176">If the first character is a dollar sign ($), the appropriate conversion is applied.</span></span>  
  
 <span data-ttu-id="bbb4d-177">Se l'updategram viene specificato in uno schema di mapping in cui la colonna è contrassegnata in modo appropriato come `dt:type="fixed.14.4"` o `sql:datatype="money"`, non è necessario inserire il simbolo del dollaro ($) e la conversione viene gestita dal mapping.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-177">If the updategram is specified against a mapping schema where the column is appropriately marked as either `dt:type="fixed.14.4"` or `sql:datatype="money"`, the dollar sign ($) is not required and the conversion is handled by the mapping.</span></span> <span data-ttu-id="bbb4d-178">Si tratta della modalità consigliata per garantire che venga eseguita la conversione di tipo appropriata.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-178">This is the recommended way to ensure that the appropriate type conversion occurs.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="bbb4d-179">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="bbb4d-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="bbb4d-180">Copiare l'updategram sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-180">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-181">Salvare il file con il nome UpdategramSpacesInTableName.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-181">Save the file as UpdategramSpacesInTableName.xml.</span></span>  
  
2.  <span data-ttu-id="bbb4d-182">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-182">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="bbb4d-183">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-183">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-using-the-at-identity-attribute-to-retrieve-the-value-that-has-been-inserted-in-the-identity-type-column"></a><span data-ttu-id="bbb4d-184">D.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-184">D.</span></span> <span data-ttu-id="bbb4d-185">Utilizzo dell'attributo at-identity per recuperare il valore inserito nella colonna di tipo IDENTITY</span><span class="sxs-lookup"><span data-stu-id="bbb4d-185">Using the at-identity attribute to retrieve the value that has been inserted in the IDENTITY-type column</span></span>  
 <span data-ttu-id="bbb4d-186">Nell'updategram seguente sono inseriti due record: uno nella tabella Sales.SalesOrderHeader e un altro nella tabella Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-186">The following updategram inserts two records: one in the Sales.SalesOrderHeader table and another in the Sales.SalesOrderDetail table.</span></span>  
  
 <span data-ttu-id="bbb4d-187">L'updategram aggiunge prima un record alla tabella Sales.SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-187">First, the updategram adds a record to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="bbb4d-188">In questa tabella la colonna SalesOrderID è una colonna di tipo IDENTITY,</span><span class="sxs-lookup"><span data-stu-id="bbb4d-188">In this table, the SalesOrderID column is an IDENTITY-type column.</span></span> <span data-ttu-id="bbb4d-189">pertanto quando si aggiunge questo record alla tabella, l'updategram utilizza l'attributo `at-identity` per acquisire il valore di SalesOrderID assegnato come "x" (un valore segnaposto).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-189">Therefore, when you add this record to the table, the updategram uses the `at-identity` attribute to capture the assigned SalesOrderID value as "x" (a placeholder value).</span></span> <span data-ttu-id="bbb4d-190">Utilizza specifica quindi questa `at-identity` variabile come valore dell'attributo SalesOrderID nell' \<Sales.SalesOrderDetail> elemento.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-190">The updategam then specifies this `at-identity` variable as the value of SalesOrderID attribute in the \<Sales.SalesOrderDetail> element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
   <Sales.SalesOrderHeader updg:at-identity="x"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00001111-2222-3333-4444-556677889900"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
      <Sales.SalesOrderDetail SalesOrderID="x"  
                LineNumber="1"  
                OrderQty="1"  
                ProductID="776"  
                SpecialOfferID="1"  
                UnitPrice="2429.9928"  
                UnitPriceDiscount="0.00"  
                rowguid="aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"  
                ModifiedDate="2001-07-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="bbb4d-191">Per restituire il valore Identity generato dall'attributo `updg:at-identity`, è possibile utilizzare l'attributo `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-191">If you want to return the identity value that is generated by the `updg:at-identity` attribute, you can use the `updg:returnid` attribute.</span></span> <span data-ttu-id="bbb4d-192">Di seguito viene mostrato un updategram corretto che restituisce questo valore Identity.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-192">The following is a revised updategram that returns this identity value.</span></span> <span data-ttu-id="bbb4d-193">Per rendere un po' più complesso questo esempio, l'updategram aggiunge due record dell'ordine e due record dei dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-193">(This updategram adds two order records and two order detail records, just to make the example a little more complex.)</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync>  
  <updg:before>  
  </updg:before>  
  <updg:after updg:returnid="x y" >  
       <HumanResources.Shift updg:at-identity="x" Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift updg:at-identity="y" Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:after>  
 </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="bbb4d-194">Quando viene eseguito, l'updategram restituisce risultati simili ai seguenti, che includono il valore Identity generato, ovvero il valore generato della colonna ShiftID utilizzato per l'identità della tabella:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-194">When the updategram is executed, it returns results similar to the following, which includes the identity value (the generated value of the ShiftID column used for table identity) that was generated:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">   
  <returnid>   
    <x>4</x>   
    <y>5</y>   
  </returnid>   
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="bbb4d-195">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="bbb4d-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="bbb4d-196">Copiare l'updategram sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-196">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-197">Salvare il file con il nome Updategram-returnId.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-197">Save the file as Updategram-returnId.xml.</span></span>  
  
2.  <span data-ttu-id="bbb4d-198">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-198">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="bbb4d-199">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-199">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-the-updgguid-attribute-to-generate-a-unique-value"></a><span data-ttu-id="bbb4d-200">E.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-200">E.</span></span> <span data-ttu-id="bbb4d-201">Utilizzo dell'attributo updg:guid per generare un valore univoco</span><span class="sxs-lookup"><span data-stu-id="bbb4d-201">Using the updg:guid attribute to generate a unique value</span></span>  
 <span data-ttu-id="bbb4d-202">In questo esempio l'updategram inserisce un record nelle tabelle Cust e CustOrder.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-202">In this example, the updategram inserts a record in the Cust and CustOrder tables.</span></span> <span data-ttu-id="bbb4d-203">L'updategram genera inoltre un valore univoco per l'attributo CustomerID mediante l'attributo `updg:guid`.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-203">Also, the updategram generates a unique value for the CustomerID attribute by using the `updg:guid` attribute.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after updg:returnid="x" >  
      <Cust updg:guid="x" >  
         <CustID>x</CustID>  
         <LastName>Fuller</LastName>  
      </Cust>  
      <CustOrder>  
         <CustID>x</CustID>  
         <OrderID>1</OrderID>  
      </CustOrder>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="bbb4d-204">L'updategram specifica l'attributo `returnid`.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-204">The updategram specifies the `returnid` attribute.</span></span> <span data-ttu-id="bbb4d-205">Viene restituito il GUID generato:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-205">As a result, the GUID that is generated is returned:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <returnid>  
    <x>7111BD1A-7F0B-4CEE-B411-260DADFEFA2A</x>   
  </returnid>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="bbb4d-206">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="bbb4d-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="bbb4d-207">Copiare l'updategram sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-207">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-208">Salvare il file con il nome Updategram-GenerateGuid.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-208">Save the file as Updategram-GenerateGuid.xml.</span></span>  
  
2.  <span data-ttu-id="bbb4d-209">Creare le tabelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-209">Create these tables:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust (CustID uniqueidentifier, LastName varchar(20))  
    CREATE TABLE CustOrder (CustID uniqueidentifier, OrderID int)  
    ```  
  
3.  <span data-ttu-id="bbb4d-210">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-210">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="bbb4d-211">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-211">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="f-specifying-a-schema-in-an-updategram"></a><span data-ttu-id="bbb4d-212">F.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-212">F.</span></span> <span data-ttu-id="bbb4d-213">Specifica di uno schema in un updategram</span><span class="sxs-lookup"><span data-stu-id="bbb4d-213">Specifying a schema in an updategram</span></span>  
 <span data-ttu-id="bbb4d-214">In questo esempio l'updategram inserisce un record nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-214">The updategram in this example inserts a record into the following table:</span></span>  
  
```  
CustOrder(OrderID, EmployeeID, OrderType)  
```  
  
 <span data-ttu-id="bbb4d-215">In questo updategram viene specificato uno schema XSD, ovvero non è presente alcun mapping predefinito degli attributi e degli elementi dell'updategram.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-215">An XSD schema is specified in this updategram (that is, there is no default mapping of updategram elements and attributes).</span></span> <span data-ttu-id="bbb4d-216">Lo schema fornisce il mapping necessario degli elementi e degli attributi alle colonne e alle tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-216">The schema provides the necessary mapping of the elements and attributes to the database tables and columns.</span></span>  
  
 <span data-ttu-id="bbb4d-217">Nello schema seguente (CustOrderSchema.xml) viene descritto un **\<CustOrder>** elemento costituito dagli attributi **OrderID** e **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="bbb4d-217">The following schema (CustOrderSchema.xml) describes a **\<CustOrder>** element that consists of the **OrderID** and **EmployeeID** attributes.</span></span> <span data-ttu-id="bbb4d-218">Per rendere più interessante lo schema, all'attributo **EmployeeID** viene assegnato un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-218">To make the schema more interesting, a default value is assigned to the **EmployeeID** attribute.</span></span> <span data-ttu-id="bbb4d-219">Un updategram utilizza il valore predefinito di un attributo solo per le operazioni di inserimento e quindi solo se nell'updategram non è specificato l'attributo in questione.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-219">An updategram uses an attribute's default value only for insert operations, and then only if the updategram does not specify that attribute.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="CustOrder" >  
   <xsd:complexType>  
        <xsd:attribute name="OrderID"     type="xsd:integer" />   
        <xsd:attribute name="EmployeeID"  type="xsd:integer" />  
        <xsd:attribute name="OrderType  " type="xsd:integer" default="1"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="bbb4d-220">Questo updategram inserisce un record nella tabella CustOrder.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-220">This updategram inserts a record into the CustOrder table.</span></span> <span data-ttu-id="bbb4d-221">L'updategram specifica solo i valori degli attributi OrderID e EmployeeID.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-221">The updategram specifies only the OrderID and EmployeeID attribute values.</span></span> <span data-ttu-id="bbb4d-222">Non specifica il valore dell'attributo OrderType.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-222">It does not specify the OrderType attribute value.</span></span> <span data-ttu-id="bbb4d-223">L'updategram utilizza, pertanto, il valore predefinito dell'attributo EmployeeID specificato nello schema precedente.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-223">Therefore, the updategram uses the default value of the EmployeeID attribute that is specified in the preceding schema.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
             xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync mapping-schema='CustOrderSchema.xml'>  
<updg:after>  
       <CustOrder OrderID="98000" EmployeeID="1" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="bbb4d-224">Per ulteriori esempi di updategram che specificano uno schema di mapping, vedere Specifica di uno [schema di mapping con annotazioni in un Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-224">For more examples of updategrams that specify a mapping schema, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="bbb4d-225">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="bbb4d-225">To test the updategram</span></span>  
  
1.  <span data-ttu-id="bbb4d-226">Creare questa tabella nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="bbb4d-226">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE CustOrder(  
                     OrderID int,   
                     EmployeeID int,   
                     OrderType int)  
    ```  
  
2.  <span data-ttu-id="bbb4d-227">Copiare lo schema sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-227">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-228">Salvare il file con il nome CustOrderSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-228">Save the file as CustOrderSchema.xml.</span></span>  
  
3.  <span data-ttu-id="bbb4d-229">Copiare l'updategram sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-229">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-230">Salvare il file con il nome CustOrderUpdategram.xml nella stessa cartella utilizzata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-230">Save the file as CustOrderUpdategram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="bbb4d-231">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-231">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="bbb4d-232">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-232">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="bbb4d-233">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-233">This is the equivalent XDR schema:</span></span>  
  
```  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
 <ElementType name="CustOrder" >  
    <AttributeType name="OrderID" />  
    <AttributeType name="EmployeeID" />  
    <AttributeType name="OrderType" default="1" />  
    <attribute type="OrderID"  />  
    <attribute type="EmployeeID" />  
    <attribute type="OrderType" />  
  </ElementType>  
</Schema>  
```  
  
### <a name="g-using-the-xsinil-attribute-to-insert-null-values-in-a-column"></a><span data-ttu-id="bbb4d-234">G.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-234">G.</span></span> <span data-ttu-id="bbb4d-235">Utilizzo dell'attributo xsi:nil per inserire valori Null in una colonna</span><span class="sxs-lookup"><span data-stu-id="bbb4d-235">Using the xsi:nil attribute to insert null values in a column</span></span>  
 <span data-ttu-id="bbb4d-236">Se si desidera inserire un valore null nella colonna corrispondente della tabella, è possibile specificare l'attributo `xsi:nil` per un elemento in un updategram.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-236">If you want to insert a null value in the corresponding column in the table, you can specify the `xsi:nil` attribute on an element in an updategram.</span></span> <span data-ttu-id="bbb4d-237">Nello schema XSD corrispondente è necessario specificare anche l'attributo `nillable` XSD.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-237">In the corresponding XSD schema, the XSD `nillable` attribute also must be specified.</span></span>  
  
 <span data-ttu-id="bbb4d-238">Si consideri, ad esempio, lo schema XSD seguente:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-238">For example, consider this XSD schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="Student" sql:relation="Students">  
  <xsd:complexType>  
    <xsd:all>  
      <xsd:element name="fname" sql:field="first_name"   
                                type="xsd:string"   
                                 nillable="true"/>  
    </xsd:all>  
    <xsd:attribute name="SID"   
                        sql:field="StudentID"  
                        type="xsd:ID"/>      
    <xsd:attribute name="lname"       
                        sql:field="last_name"  
                        type="xsd:string"/>  
    <xsd:attribute name="minitial"    
                        sql:field="middle_initial"   
                        type="xsd:string"/>  
    <xsd:attribute name="years"       
                         sql:field="no_of_years"  
                         type="xsd:integer"/>  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="bbb4d-239">Nello schema XSD viene specificato **nillable = "true"** per l' **\<fname>** elemento.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-239">The XSD schema specifies **nillable="true"** for the **\<fname>** element.</span></span> <span data-ttu-id="bbb4d-240">Questo schema viene utilizzato nell'updategram seguente.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-240">The following updategram uses this schema:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
      xmlns:updg="urn:schemas-microsoft-com:xml-updategram"  
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  
<updg:sync mapping-schema='StudentSchema.xml'>  
  <updg:before/>  
  <updg:after>  
    <Student SID="S00004" lname="Elmaci" minitial="" years="2">  
      <fname xsi:nil="true">  
    </fname>  
    </Student>  
  </updg:after>  
</updg:sync>  
  
</ROOT>  
```  
  
 <span data-ttu-id="bbb4d-241">L'updategram specifica `xsi:nil` per l' **\<fname>** elemento nel **\<after>** blocco.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-241">The updategram specifies `xsi:nil` for the **\<fname>** element in the **\<after>** block.</span></span> <span data-ttu-id="bbb4d-242">pertanto quando questo updategram viene eseguito, viene inserito un valore NULL per la colonna first_name della tabella.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-242">Therefore, when this updategram is executed, a value of NULL is inserted for the first_name column in the table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="bbb4d-243">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="bbb4d-243">To test the updategram</span></span>  
  
1.  <span data-ttu-id="bbb4d-244">Creare la tabella seguente nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="bbb4d-244">Create the following table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Students (  
       StudentID char(6)NOT NULL ,  
       first_name varchar(50),  
       last_name varchar(50),  
       middle_initial char(1),  
       no_of_years int NULL)  
    GO  
    ```  
  
2.  <span data-ttu-id="bbb4d-245">Copiare lo schema sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-245">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-246">Salvare il file con il nome StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-246">Save the file as StudentSchema.xml.</span></span>  
  
3.  <span data-ttu-id="bbb4d-247">Copiare l'updategram sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-247">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-248">Salvare il file con il nome StudentUpdategram.xml nella stessa cartella utilizzata nel passaggio precedente per salvare il file StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-248">Save the file as StudentUpdategram.xml in the same folder used in previous step to save StudentSchema.xml.</span></span>  
  
4.  <span data-ttu-id="bbb4d-249">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-249">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="bbb4d-250">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-250">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="h-specifying-namespaces-in-an-updategram"></a><span data-ttu-id="bbb4d-251">H.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-251">H.</span></span> <span data-ttu-id="bbb4d-252">Specifica degli spazi dei nomi in un updategram</span><span class="sxs-lookup"><span data-stu-id="bbb4d-252">Specifying namespaces in an updategram</span></span>  
 <span data-ttu-id="bbb4d-253">In un updategram possono essere presenti elementi che appartengono a uno spazio dei nomi dichiarato nello stesso elemento all'interno dell'updategram.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-253">In an updategram you can have elements that belong to a namespace declared in the same element in the updategram.</span></span> <span data-ttu-id="bbb4d-254">In questo caso anche lo schema corrispondente deve dichiarare lo stesso spazio dei nomi e l'elemento deve appartenere allo spazio dei nomi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-254">In this case, the corresponding schema must also declare the same namespace and the element must belong to that target namespace.</span></span>  
  
 <span data-ttu-id="bbb4d-255">Nell'updategram seguente (UpdateGram-ElementHavingNamespace.xml), ad esempio, l' **\<Order>** elemento appartiene a uno spazio dei nomi dichiarato nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-255">For example, in the following updategram (UpdateGram-ElementHavingNamespace.xml), the **\<Order>** element belongs to a namespace declared in the element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema='XSD-ElementHavingNameSpace.xml'>  
    <updg:after>  
       <x:Order  xmlns:x="http://server/xyz/schemas/"  
             updg:at-identity="SalesOrderID"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00009999-8888-7777-6666-554433221100"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="bbb4d-256">In questo caso lo schema deve dichiarare anche lo spazio dei nomi, come mostrato in questo schema:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-256">In this case, the schema must also declare the namespace as shown in this schema:</span></span>  
  
 <span data-ttu-id="bbb4d-257">Nello schema seguente (XSD-ElementHavingNamespace.xml) viene mostrato come devono essere dichiarati gli attributi e l'elemento corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-257">The following schema (XSD-ElementHavingNamespace.xml) shows how the corresponding element and attributes must be declared.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
     xmlns:dt="urn:schemas-microsoft-com:datatypes"   
     xmlns:sql="urn:schemas-microsoft-com:mapping-schema"    
     xmlns:x="http://server/xyz/schemas/"   
     targetNamespace="http://server/xyz/schemas/" >  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" type="x:Order_type"/>  
  <xsd:complexType name="Order_type">  
    <xsd:attribute name="SalesOrderID"  type="xsd:ID"/>  
    <xsd:attribute name="RevisionNumber" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OrderDate" type="xsd:dateTime"/>  
    <xsd:attribute name="DueDate" type="xsd:dateTime"/>  
    <xsd:attribute name="ShipDate" type="xsd:dateTime"/>  
    <xsd:attribute name="Status" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OnlineOrderFlag" type="xsd:boolean"/>  
    <xsd:attribute name="SalesOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="PurchaseOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="AccountNumber" type="xsd:string"/>  
    <xsd:attribute name="CustomerID" type="xsd:int"/>  
    <xsd:attribute name="ContactID" type="xsd:int"/>  
    <xsd:attribute name="SalesPersonID" type="xsd:int"/>  
    <xsd:attribute name="TerritoryID" type="xsd:int"/>  
    <xsd:attribute name="BillToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipMethodID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardApprovalCode" type="xsd:string"/>  
    <xsd:attribute name="CurrencyRateID" type="xsd:int"/>  
    <xsd:attribute name="SubTotal" type="xsd:decimal"/>  
    <xsd:attribute name="TaxAmt" type="xsd:decimal"/>  
    <xsd:attribute name="Freight" type="xsd:decimal"/>  
    <xsd:attribute name="TotalDue" type="xsd:decimal"/>  
    <xsd:attribute name="Comment" type="xsd:string"/>  
    <xsd:attribute name="rowguid" type="xsd:string"/>  
    <xsd:attribute name="ModifiedDate" type="xsd:dateTime"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="bbb4d-258">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="bbb4d-258">To test the updategram</span></span>  
  
1.  <span data-ttu-id="bbb4d-259">Copiare lo schema sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-259">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-260">Salvare il file con il nome XSD-ElementHavingNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-260">Save the file as XSD-ElementHavingNamespace.xml.</span></span>  
  
2.  <span data-ttu-id="bbb4d-261">Copiare l'updategram sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-261">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-262">Salvare il file con il nome Updategram-ElementHavingNamespace.xml nella stessa cartella utilizzata per salvare il file XSD-ElementHavingnamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-262">Save the file as Updategram-ElementHavingNamespace.xml in the same folder used to save XSD-ElementHavingnamespace.xml.</span></span>  
  
3.  <span data-ttu-id="bbb4d-263">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-263">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="bbb4d-264">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-264">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="i-inserting-data-into-an-xml-data-type-column"></a><span data-ttu-id="bbb4d-265">I.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-265">I.</span></span> <span data-ttu-id="bbb4d-266">Inserimento di dati in una colonna con tipo di dati XML</span><span class="sxs-lookup"><span data-stu-id="bbb4d-266">Inserting data into an XML data type column</span></span>  
 <span data-ttu-id="bbb4d-267">Il tipo di dati `xml` è stato introdotto in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbb4d-267">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="bbb4d-268">È possibile utilizzare gli updategram per inserire e aggiornare dati archiviati nelle colonne del tipo di dati `xml` seguendo le indicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-268">You can use updategrams to insert and update data stored in `xml` data type columns with the following provisions:</span></span>  
  
-   <span data-ttu-id="bbb4d-269">La colonna `xml` non può essere utilizzata per l'identificazione di una riga esistente,</span><span class="sxs-lookup"><span data-stu-id="bbb4d-269">The `xml` column cannot be used for identifying an existing row.</span></span> <span data-ttu-id="bbb4d-270">pertanto non può essere inclusa nella sezione `updg:before` di un updategram.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-270">Therefore, it cannot be included in the `updg:before` section of an updategram.</span></span>  
  
-   <span data-ttu-id="bbb4d-271">Gli spazi dei nomi che si trovano nell'ambito del frammento XML inserito nella colonna `xml` verranno mantenuti e le rispettive dichiarazioni verranno aggiunte al primo elemento del frammento inserito.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-271">Namespaces that are in scope of the XML fragment inserted into the `xml` column will be preserved and their namespace declarations are added to the top element of the inserted fragment.</span></span>  
  
 <span data-ttu-id="bbb4d-272">Nell'updategram seguente (SampleUpdateGram.xml), ad esempio, l' **\<Desc>** elemento Aggiorna la colonna ProductDescription nella tabella production>ProductModel del database di [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] esempio.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-272">For example, in the following updategram (SampleUpdateGram.xml), the **\<Desc>** element updates the ProductDescription column in the Production>productModel table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="bbb4d-273">Il risultato di questo updategram è che il contenuto XML della colonna ProductDescription viene aggiornato con il contenuto XML dell' **\<Desc>** elemento.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-273">The result of this updategram is that the XML contents of the ProductDescription column are update with the XML contents of the **\<Desc>** element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
       <updg:before>  
<ProductModel ProductModelID="19">  
   <Name>Mountain-100</Name>  
</ProductModel>  
    </updg:before>  
    <updg:after>  
 <ProductModel>  
    <Name>Mountain-100</Name>  
    <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
        <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
              xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
              xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
              xmlns:html="http://www.w3.org/1999/xhtml"   
              xmlns="">  
  <p1:Summary>  
     <html:p>Insert Example</html:p>  
  </p1:Summary>  
  <p1:Manufacturer>  
    <p1:Name>AdventureWorks</p1:Name>  
    <p1:Copyright>2002</p1:Copyright>  
    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
  </p1:Manufacturer>  
  <p1:Features>These are the product highlights.   
    <wm:Warranty>  
       <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
       <wm:Description>parts and labor</wm:Description>  
    </wm:Warranty>  
    <wm:Maintenance>  
       <wm:NoOfYears>10 years</wm:NoOfYears>  
       <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
    </wm:Maintenance>  
    <wf:wheel>High performance wheels.</wf:wheel>  
    <wf:saddle>  
      <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle>  
    <wf:pedal>  
       <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal>  
    <wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter and wall-thickness required of a premium mountain frame. The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame>  
    <wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset>  
   </p1:Features>  
   <p1:Picture>  
      <p1:Angle>front</p1:Angle>  
      <p1:Size>small</p1:Size>  
      <p1:ProductPhotoID>118</p1:ProductPhotoID>  
   </p1:Picture>  
   <p1:Specifications> These are the product specifications.  
     <Material>Almuminum Alloy</Material>  
     <Color>Available in most colors</Color>  
     <ProductLine>Mountain bike</ProductLine>  
     <Style>Unisex</Style>  
     <RiderExperience>Advanced to Professional riders</RiderExperience>  
   </p1:Specifications>  
  </p1:ProductDescription>  
 </Desc>  
      </ProductModel>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="bbb4d-274">L'updategram si riferisce allo schema XSD con annotazioni seguente (SampleSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-274">The updategram refers to the following annotated XSD schema (SampleSchema.xml).</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
     <xsd:complexType>  
       <xsd:sequence>  
          <xsd:element name="Name" type="xsd:string"></xsd:element>  
          <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
           <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="ProductDescription">  
                 <xsd:complexType>  
                   <xsd:sequence>  
                     <xsd:element name="Summary" type="xsd:anyType">  
                     </xsd:element>  
                   </xsd:sequence>  
                 </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>   
       </xsd:sequence>  
       <xsd:attribute name="ProductModelID" sql:field="ProductModelID"/>  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="bbb4d-275">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="bbb4d-275">To test the updategram</span></span>  
  
1.  <span data-ttu-id="bbb4d-276">Copiare lo schema sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-276">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-277">Salvare il file con il nome XSD-SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-277">Save the file as XSD-SampleSchema.xml.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bbb4d-278">Poiché gli updategram supportano il mapping predefinito, non c'è nessun modo per identificare l'inizio e la fine del tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-278">Because updategrams support default mapping, there is no way to identify the beginning and ending of the `xml` data type.</span></span> <span data-ttu-id="bbb4d-279">Ciò significa che è necessario uno schema di mapping quando si inseriscono o si aggiornano tabelle con colonne di tipi di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-279">This effectively means that a mapping schema is required when inserting or updating tables with `xml` data type columns.</span></span> <span data-ttu-id="bbb4d-280">Quando non viene fornito uno schema, SQLXML restituisce un errore che indica che nella tabella manca una delle colonne.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-280">When a schema is not provided, SQLXML returns an error indicating that one of the columns is missing from the table.</span></span>  
  
2.  <span data-ttu-id="bbb4d-281">Copiare l'updategram sopra riportato e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-281">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="bbb4d-282">Salvare il file con il nome SampleUpdategram.xml nella stessa cartella utilizzata per salvare il file SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-282">Save the file as SampleUpdategram.xml in the same folder used to save SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="bbb4d-283">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-283">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="bbb4d-284">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-284">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb4d-285">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbb4d-285">See Also</span></span>  
 [<span data-ttu-id="bbb4d-286">Considerazioni sulla sicurezza degli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="bbb4d-286">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
