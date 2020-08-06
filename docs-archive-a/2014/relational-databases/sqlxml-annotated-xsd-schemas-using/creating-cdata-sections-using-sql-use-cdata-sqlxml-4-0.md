---
title: 'Creazione di sezioni CDATA mediante SQL: Use-CDATA (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- markup characters [SQLXML]
- special characters [SQLXML]
- use-cdata annotation
- plain text [SQLXML]
- CDATA sections
- escaping blocks of text [SQLXML]
- annotated XSD schemas, CDATA sections
- sql:use-cdata
ms.assetid: 26d2b9dc-f857-44ff-bcd4-aaf64ff809d0
author: rothja
ms.author: jroth
ms.openlocfilehash: c0ba0787efbda400590a75f0f3529e3df8819e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636645"
---
# <a name="creating-cdata-sections-using-sqluse-cdata-sqlxml-40"></a><span data-ttu-id="ecc49-102">Creazione di sezioni CDATA mediante sql:use-cdata (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ecc49-102">Creating CDATA Sections Using sql:use-cdata (SQLXML 4.0)</span></span>
  <span data-ttu-id="ecc49-103">In XML vengono utilizzate le sezioni CDATA per eseguire l'escape di blocchi di testo contenenti caratteri che, altrimenti, verrebbero riconosciuti come caratteri di markup.</span><span class="sxs-lookup"><span data-stu-id="ecc49-103">In XML, CDATA sections are used to escape blocks of text that contain characters that would otherwise be recognized as markup characters.</span></span>  
  
 <span data-ttu-id="ecc49-104">Un database in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può talvolta contenere caratteri che vengono trattati come caratteri di markup dal parser XML, ad esempio le parentesi angolari ( \< and > ), il simbolo di minore o uguale a (<=) e la e commerciale (&) vengono trattati come caratteri di markup.</span><span class="sxs-lookup"><span data-stu-id="ecc49-104">A database in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can sometimes contain characters that are treated as markup characters by the XML parser; for example, angle brackets (\< and >), the less-than-or-equal-to symbol (<=), and the ampersand (&) are treated as markup characters.</span></span> <span data-ttu-id="ecc49-105">Per evitare che ciò accada, è tuttavia possibile eseguire il wrapping di questo tipo di caratteri speciali in una sezione CDATA.</span><span class="sxs-lookup"><span data-stu-id="ecc49-105">However, you can wrap this type of special characters in a CDATA section to prevent them from being treated as markup characters.</span></span> <span data-ttu-id="ecc49-106">Il testo nella sezione CDATA viene considerato testo normale dal parser XML.</span><span class="sxs-lookup"><span data-stu-id="ecc49-106">The text within the CDATA section is treated by the XML parser as plain text.</span></span>  
  
 <span data-ttu-id="ecc49-107">L'annotazione `sql:use-cdata` viene utilizzata per specificare che è necessario eseguire il wrapping dei dati restituiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in una sezione CDATA. In altre parole, indica se il valore di una colonna specificata da `sql:field` deve essere incluso in una sezione CDATA.</span><span class="sxs-lookup"><span data-stu-id="ecc49-107">The `sql:use-cdata` annotation is used to specify that the data returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should be wrapped in a CDATA section (that is, it indicates whether the value from a column that is specified by `sql:field` should be enclosed in a CDATA section).</span></span> <span data-ttu-id="ecc49-108">L'annotazione `sql:use-cdata` può essere specificata solo su elementi che eseguono il mapping a una colonna di database.</span><span class="sxs-lookup"><span data-stu-id="ecc49-108">The `sql:use-cdata` annotation can be specified only on elements that map to a database column.</span></span>  
  
 <span data-ttu-id="ecc49-109">L'annotazione `sql:use-cdata` accetta un valore booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="ecc49-109">The `sql:use-cdata` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="ecc49-110">I valori possibili sono 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="ecc49-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="ecc49-111">Non è possibile utilizzare l'annotazione con `sql:url-encode` o sui tipi di attributo ID, IDREF, IDREFS, NMTOKEN e NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="ecc49-111">This annotation cannot be used with `sql:url-encode` or on the ID, IDREF, IDREFS, NMTOKEN, and NMTOKENS attribute types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ecc49-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="ecc49-112">Examples</span></span>  
 <span data-ttu-id="ecc49-113">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="ecc49-113">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="ecc49-114">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="ecc49-114">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqluse-cdata-on-an-element"></a><span data-ttu-id="ecc49-115">R.</span><span class="sxs-lookup"><span data-stu-id="ecc49-115">A.</span></span> <span data-ttu-id="ecc49-116">Specifica di sql:use-cdata su un elemento</span><span class="sxs-lookup"><span data-stu-id="ecc49-116">Specifying sql:use-cdata on an element</span></span>  
 <span data-ttu-id="ecc49-117">Nello schema seguente, `sql:use-cdata` viene impostato su 1 (true) per l'oggetto **\<AddressLine1>** all'interno dell' **\<Address>** elemento.</span><span class="sxs-lookup"><span data-stu-id="ecc49-117">In the following schema, `sql:use-cdata` is set to 1 (True) for the **\<AddressLine1>** within the **\<Address>** element.</span></span> <span data-ttu-id="ecc49-118">I dati vengono quindi restituiti in una sezione CDATA.</span><span class="sxs-lookup"><span data-stu-id="ecc49-118">As a result, the data is returned in a CDATA section.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Address"   
               sql:relation="Person.Address"   
               sql:key-fields="AddressID" >  
   <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="AddressID"  type="xsd:string" />  
          <xsd:element name="AddressLine1" type="xsd:string"   
                       sql:use-cdata="1" />  
        </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="ecc49-119">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="ecc49-119">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="ecc49-120">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="ecc49-120">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="ecc49-121">Salvare il file con il nome UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="ecc49-121">Save the file as UseCData.xml.</span></span>  
  
2.  <span data-ttu-id="ecc49-122">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="ecc49-122">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="ecc49-123">Salvare il file con il nome UseCDataT.xml nella stessa directory nella quale è stato salvato UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="ecc49-123">Save the file as UseCDataT.xml in the same directory where you saved UseCData.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="UseCData.xml">  
            /Address[AddressID < 11]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="ecc49-124">Il percorso della directory specificato per lo schema di mapping (UseCData.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="ecc49-124">The directory path specified for the mapping schema (UseCData.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="ecc49-125">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ecc49-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\UseCData.xml"  
    ```  
  
3.  <span data-ttu-id="ecc49-126">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="ecc49-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="ecc49-127">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ecc49-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="ecc49-128">Di seguito è riportato il set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="ecc49-128">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Address>   
    <AddressID>1</CustomerID>   
    <AddressLine1>   
      <![CDATA[ 1970 Napa Ct.  ]]>   
    </AddressLine1>   
  </Address>  
  <Address>  
    <AddressLine1>   
      <![CDATA[ 9833 Mt. Dias Blv. ]]>   
    </AddressLine1>   
  </Address>  
  ...  
</ROOT>  
```  
  
  
