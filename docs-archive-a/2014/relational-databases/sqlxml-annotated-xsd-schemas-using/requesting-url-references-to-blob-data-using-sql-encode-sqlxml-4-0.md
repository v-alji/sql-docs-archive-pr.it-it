---
title: 'Richiesta di riferimenti URL a dati BLOB tramite SQL: encode (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:encode
- encode annotation
- URL references to BLOB data [SQLXML]
- references to BLOB data [SQLXML]
- annotated XSD schemas, URL references to BLOB data
- requesting URL references to BLOB data
- BLOBs, URL references
- Base 64-encoded format
ms.assetid: 2f8cd93b-c636-462b-8291-167197233ee0
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a9f5edcfab4a9d7307327d97bc2099c78c666c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636637"
---
# <a name="requesting-url-references-to-blob-data-using-sqlencode-sqlxml-40"></a><span data-ttu-id="91b7d-102">Richiesta di riferimenti URL a dati BLOB utilizzando sql:encode (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="91b7d-102">Requesting URL References to BLOB Data Using sql:encode (SQLXML 4.0)</span></span>
  <span data-ttu-id="91b7d-103">In uno schema XSD con annotazioni quando viene eseguito il mapping di un attributo o elemento a una colonna BLOB in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], i dati vengono restituiti in formato con codifica Base 64 in XML.</span><span class="sxs-lookup"><span data-stu-id="91b7d-103">In an annotated XSD schema, when an attribute (or element) is mapped to a BLOB column in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data is returned in Base 64-encoded format within XML.</span></span>  
  
 <span data-ttu-id="91b7d-104">Se si desidera che venga restituito un riferimento ai dati (un URI) che possa essere utilizzato successivamente per recuperare i dati BLOB in un formato binario, specificare l'annotazione `sql:encode`.</span><span class="sxs-lookup"><span data-stu-id="91b7d-104">If you want a reference to the data (a URI) to be returned that can be used later to retrieve the BLOB data in a binary format, specify the `sql:encode` annotation.</span></span> <span data-ttu-id="91b7d-105">È possibile specificare `sql:encode` su un attributo o un elemento di tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="91b7d-105">You can specify `sql:encode` on an attribute or element of simple type.</span></span>  
  
 <span data-ttu-id="91b7d-106">Specificare l'annotazione `sql:encode` per indicare che deve essere restituito un URL al campo invece del valore del campo.</span><span class="sxs-lookup"><span data-stu-id="91b7d-106">Specify the `sql:encode` annotation to indicate that a URL to the field should be returned instead of the value of the field.</span></span> <span data-ttu-id="91b7d-107">`sql:encode` dipende dalla chiave primaria per generare un singleton scelto nell'URL.</span><span class="sxs-lookup"><span data-stu-id="91b7d-107">`sql:encode` depends on the primary key to generate a singleton select in the URL.</span></span> <span data-ttu-id="91b7d-108">La chiave primaria può essere specificata utilizzando l'annotazione `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="91b7d-108">The primary key can be specified using the `sql:key-fields` annotation.</span></span>  
  
 <span data-ttu-id="91b7d-109">All'annotazione `sql:encode` è possibile assegnare il valore "url" o "default".</span><span class="sxs-lookup"><span data-stu-id="91b7d-109">The `sql:encode` annotation can be assigned the "url" or the "default" value.</span></span> <span data-ttu-id="91b7d-110">Il valore "default" restituisce dati in formato con codifica Base 64.</span><span class="sxs-lookup"><span data-stu-id="91b7d-110">A value of "default" returns data in Base 64-encoded format.</span></span>  
  
 <span data-ttu-id="91b7d-111">Non è possibile utilizzare l'annotazione `sql:encode` con `sql:use-cdata` o sui tipi di attributo ID, IDREF, IDREFS, NMTOKEN o NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="91b7d-111">The `sql:encode` annotation cannot be used with `sql:use-cdata` or on the ID, IDREF, IDREFS, NMTOKEN, or NMTOKENS attribute types.</span></span> <span data-ttu-id="91b7d-112">Non è inoltre possibile utilizzarlo con l'attributo **fixed** XSD.</span><span class="sxs-lookup"><span data-stu-id="91b7d-112">It can also not be used with XSD **fixed** attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91b7d-113">Non è possibile utilizzare le colonne di tipo BLOB come parte di una chiave o di una chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="91b7d-113">BLOB-type columns cannot be used as a part of a key or foreign key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="91b7d-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="91b7d-114">Examples</span></span>  
 <span data-ttu-id="91b7d-115">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="91b7d-115">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="91b7d-116">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="91b7d-116">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlencode-to-obtain-a-url-reference-to-blob-data"></a><span data-ttu-id="91b7d-117">R.</span><span class="sxs-lookup"><span data-stu-id="91b7d-117">A.</span></span> <span data-ttu-id="91b7d-118">Specifica di sql:encode per ottenere un riferimento URL ai dati BLOB</span><span class="sxs-lookup"><span data-stu-id="91b7d-118">Specifying sql:encode to obtain a URL reference to BLOB data</span></span>  
 <span data-ttu-id="91b7d-119">In questo esempio, lo schema di mapping specifica `sql:encode` sull'attributo **LargePhoto** per recuperare il riferimento URI a una foto del prodotto specifica, anziché recuperare i dati binari nel formato con codifica base 64.</span><span class="sxs-lookup"><span data-stu-id="91b7d-119">In this example, the mapping schema specifies `sql:encode` on the **LargePhoto** attribute to retrieve the URI reference to a specific product photo (instead of retrieving the binary data in Base 64-encoded format).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="ProductPhoto" sql:relation="Production.ProductPhoto"   
               sql:key-fields="ProductPhotoID" >  
   <xsd:complexType>  
      <xsd:attribute name="ProductPhotoID"  type="xsd:int"  />  
     <xsd:attribute name="LargePhoto" type="xsd:string" sql:encode="url" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="91b7d-120">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="91b7d-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="91b7d-121">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="91b7d-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="91b7d-122">Salvare il file come sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="91b7d-122">Save the file as sqlEncode.xml.</span></span>  
  
2.  <span data-ttu-id="91b7d-123">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="91b7d-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="91b7d-124">Salvare il file come sqlEncodeT.xml nella stessa directory nella quale è stato salvato sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="91b7d-124">Save the file as sqlEncodeT.xml in the same directory where you saved sqlEncode.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sqlEncode.xml">  
            /ProductPhoto[@ProductPhotoID=100]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="91b7d-125">Il percorso di directory specificato per lo schema di mapping (sqlEncode.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="91b7d-125">The directory path specified for the mapping schema (sqlEncode.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="91b7d-126">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91b7d-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlEncode.xml"  
    ```  
  
3.  <span data-ttu-id="91b7d-127">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="91b7d-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="91b7d-128">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="91b7d-128">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="91b7d-129">Risultato:</span><span class="sxs-lookup"><span data-stu-id="91b7d-129">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <ProductPhoto ProductPhotoID="100"  
                 LargePhoto="dbobject/Production.ProductPhoto[@ProductPhotoID="100"]/@LargePhoto" />   
</ROOT>  
```  
  
  
