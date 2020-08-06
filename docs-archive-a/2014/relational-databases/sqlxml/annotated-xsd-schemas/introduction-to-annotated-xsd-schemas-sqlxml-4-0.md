---
title: Introduzione agli schemi XSD con annotazioni (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- mapping schema [SQLXML], about mapping schema
- views [SQLXML]
- valid XSD schemas [SQLXML]
- annotations [SQLXML]
- XSD schemas [SQLXML], creating XML views
- annotated XSD schemas, creating XML views
- minimum XSD schema
- annotated XSD schemas, examples
- XML views [SQLXML]
ms.assetid: 15282db1-65c4-43be-bdb7-e9ef49cb33a2
author: rothja
ms.author: jroth
ms.openlocfilehash: b91be71569daa9e5bf4143be9f652617ba7c5b01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634931"
---
# <a name="introduction-to-annotated-xsd-schemas-sqlxml-40"></a><span data-ttu-id="43b9e-102">Introduzione agli schemi XSD con annotazioni (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="43b9e-102">Introduction to Annotated XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="43b9e-103">È possibile creare viste XML di dati relazionali mediante il linguaggio di definizione di XML Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="43b9e-103">You can create XML views of relational data by using the XML Schema Definition (XSD) language.</span></span> <span data-ttu-id="43b9e-104">In tali viste è possibile eseguire query utilizzando le query XPath (XML Path language).</span><span class="sxs-lookup"><span data-stu-id="43b9e-104">These views can then be queried by using XML Path language (XPath) queries.</span></span> <span data-ttu-id="43b9e-105">La procedura è simile a quella utilizzata per creare viste mediante le istruzioni CREATE VIEW e quindi specificare query SQL in tali viste.</span><span class="sxs-lookup"><span data-stu-id="43b9e-105">This is similar to creating views by using CREATE VIEW statements and then specifying SQL queries against the view.</span></span>  
  
 <span data-ttu-id="43b9e-106">Un elemento XML Schema descrive la struttura di un documento XML e i vari vincoli presenti sui dati del documento.</span><span class="sxs-lookup"><span data-stu-id="43b9e-106">An XML schema describes the structure of an XML document and also describes the various constraints on the data in the document.</span></span> <span data-ttu-id="43b9e-107">Quando si specificano query XPath nello schema, la struttura del documento XML restituita è determinata dallo schema nel quale viene eseguita la query XPath.</span><span class="sxs-lookup"><span data-stu-id="43b9e-107">When you specify XPath queries against the schema, the structure of the XML document returned is determined by the schema against which the XPath query is executed.</span></span>  
  
 <span data-ttu-id="43b9e-108">In uno schema XSD l' **\<xsd:schema>** elemento racchiude l'intero schema. tutte le dichiarazioni di elemento devono essere contenute all'interno dell' **\<xsd:schema>** elemento.</span><span class="sxs-lookup"><span data-stu-id="43b9e-108">In an XSD schema, the **\<xsd:schema>** element encloses the entire schema; all element declarations must be contained within the **\<xsd:schema>** element.</span></span> <span data-ttu-id="43b9e-109">È possibile descrivere gli attributi che definiscono lo spazio dei nomi in cui si trova lo schema e gli spazi dei nomi utilizzati nello schema come proprietà dell' **\<xsd:schema>** elemento.</span><span class="sxs-lookup"><span data-stu-id="43b9e-109">You can describe attributes that define the namespace in which the schema resides and the namespaces that are used in the schema as properties of the **\<xsd:schema>** element.</span></span>  
  
 <span data-ttu-id="43b9e-110">Uno schema XSD valido deve contenere l' **\<xsd:schema>** elemento definito come segue:</span><span class="sxs-lookup"><span data-stu-id="43b9e-110">A valid XSD schema must contain the **\<xsd:schema>** element defined as follows:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<!-- additional schema definitions here -->  
</xsd:schema>  
```  
  
 <span data-ttu-id="43b9e-111">L' **\<xsd:schema>** elemento è derivato dalla specifica dello spazio dei nomi XML Schema in http://www.w3.org/2001/XMLSchema .</span><span class="sxs-lookup"><span data-stu-id="43b9e-111">The **\<xsd:schema>** element is derived from the XML Schema namespace specification at http://www.w3.org/2001/XMLSchema.</span></span>  
  
## <a name="annotations-to-the-xsd-schema"></a><span data-ttu-id="43b9e-112">Annotazioni dello schema XSD</span><span class="sxs-lookup"><span data-stu-id="43b9e-112">Annotations to the XSD Schema</span></span>  
 <span data-ttu-id="43b9e-113">È possibile utilizzare uno schema XSD con annotazioni che descrivono il mapping a un database, eseguire query nel database e restituire i risultati nel formato di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="43b9e-113">You can use an XSD schema with annotations that describe the mapping to a database, query the database, and return the results in the form of an XML document.</span></span> <span data-ttu-id="43b9e-114">Le annotazioni vengono fornite per eseguire il mapping di uno schema XSD a colonne e tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="43b9e-114">Annotations are provided to map an XSD schema to database tables and columns.</span></span> <span data-ttu-id="43b9e-115">È possibile specificare le query XPath nella vista XML creata dallo schema XSD per eseguire query nel database e ottenere risultati in formato XML.</span><span class="sxs-lookup"><span data-stu-id="43b9e-115">XPath queries can be specified against the XML view created by the XSD schema to query the database and obtain results as an XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43b9e-116">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 il linguaggio dello schema XSD supporta le annotazioni introdotte con il linguaggio dello schema XDR (XML-Data Reduced) con annotazioni in [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43b9e-116">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports the annotations introduced with annotated XML-Data Reduced (XDR) schema language in [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="43b9e-117">Lo schema XDR con annotazioni è deprecato in SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="43b9e-117">Annotated XDR is deprecated in SQLXML 4.0.</span></span>  
  
 <span data-ttu-id="43b9e-118">Nel contesto del database relazionale risulta utile per eseguire il mapping dello schema XSD arbitrario a un archivio relazionale.</span><span class="sxs-lookup"><span data-stu-id="43b9e-118">In the context of the relational database, it is useful to map the arbitrary XSD schema to a relational store.</span></span> <span data-ttu-id="43b9e-119">Un modo per ottenere questo risultato è annotare lo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="43b9e-119">One way to achieve this is to annotate the XSD schema.</span></span> <span data-ttu-id="43b9e-120">Uno schema XSD con annotazioni viene definito *schema di mapping*, che fornisce informazioni relative alla modalità di mapping dei dati XML all'archivio relazionale.</span><span class="sxs-lookup"><span data-stu-id="43b9e-120">An XSD schema with the annotations is referred to as a *mapping schema*, which provides information pertaining to how XML data is to be mapped to the relational store.</span></span> <span data-ttu-id="43b9e-121">Uno schema di mapping è, di fatto, una vista XML dei dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="43b9e-121">A mapping schema is, in effect, an XML view of the relational data.</span></span> <span data-ttu-id="43b9e-122">I mapping possono essere utilizzati per recuperare dati relazionali come documento XML.</span><span class="sxs-lookup"><span data-stu-id="43b9e-122">These mappings can be used to retrieve relational data as an XML document.</span></span>  
  
## <a name="namespace-for-annotations"></a><span data-ttu-id="43b9e-123">Spazio dei nomi per le annotazioni</span><span class="sxs-lookup"><span data-stu-id="43b9e-123">Namespace for Annotations</span></span>  
 <span data-ttu-id="43b9e-124">In uno schema XSD le annotazioni vengono specificate tramite lo spazio dei nomi **urn: schemas-microsoft-com: mapping-schema**.</span><span class="sxs-lookup"><span data-stu-id="43b9e-124">In an XSD schema, annotations are specified by using the namespace **urn:schemas-microsoft-com:mapping-schema**.</span></span> <span data-ttu-id="43b9e-125">Come illustrato nell'esempio seguente, il modo più semplice per specificare lo spazio dei nomi consiste nel specificarlo nel **\<xsd:schema>** tag.</span><span class="sxs-lookup"><span data-stu-id="43b9e-125">As shown in the following example, the easiest way to specify the namespace is to specify it in the **\<xsd:schema>** tag.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
...  
</xsd:schema>  
```  
  
 <span data-ttu-id="43b9e-126">Il prefisso dello spazio dei nomi utilizzato è arbitrario.</span><span class="sxs-lookup"><span data-stu-id="43b9e-126">The namespace prefix that is used is arbitrary.</span></span> <span data-ttu-id="43b9e-127">In questa documentazione viene usato il prefisso **SQL** per indicare lo spazio dei nomi di annotazione e per distinguere le annotazioni in questo spazio dei nomi da quelle di altri spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="43b9e-127">In this documentation, the **sql** prefix is used to denote the annotation namespace and to distinguish annotations in this namespace from those in other namespaces.</span></span>  
  
## <a name="example-of-an-annotated-xsd-schema"></a><span data-ttu-id="43b9e-128">Esempio di schema XSD con annotazioni</span><span class="sxs-lookup"><span data-stu-id="43b9e-128">Example of an Annotated XSD Schema</span></span>  
 <span data-ttu-id="43b9e-129">Nell'esempio seguente lo schema XSD è costituito da un **\<Person.Contact>** elemento.</span><span class="sxs-lookup"><span data-stu-id="43b9e-129">In the following example, the XSD schema consists of an **\<Person.Contact>** element.</span></span> <span data-ttu-id="43b9e-130">L' **\<Employee>** elemento ha un attributo **ContactID** e **\<FirstName>** **\<LastName>** gli elementi figlio:</span><span class="sxs-lookup"><span data-stu-id="43b9e-130">The **\<Employee>** element has a **ContactID** attribute and **\<FirstName>** and **\<LastName>** child elements:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <xsd:element name="Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"    
                     type="xsd:string" />   
        <xsd:element name="LName"  
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID" type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="43b9e-131">A questo schema XSD vengono aggiunte annotazioni per eseguire il mapping degli elementi e degli attributi alle colonne e alle tabelle di database:</span><span class="sxs-lookup"><span data-stu-id="43b9e-131">Annotations are added to this XSD schema to map its elements and attributes to the database tables and columns:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID"   
                       sql:field="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="43b9e-132">Nello schema di mapping **\<Contact>** viene eseguito il mapping dell'elemento alla tabella Person. Contact nel database AdventureWorks di esempio tramite l' `sql:relation` annotazione.</span><span class="sxs-lookup"><span data-stu-id="43b9e-132">In the mapping schema, the **\<Contact>** element is mapped to the Person.Contact table in the sample AdventureWorks database by using the `sql:relation` annotation.</span></span> <span data-ttu-id="43b9e-133">Viene eseguito il mapping degli attributi ConID, il FName e LName alle colonne ContactID, FirstName e LastName nella tabella Person.Contact mediante le annotazioni `sql:field`.</span><span class="sxs-lookup"><span data-stu-id="43b9e-133">The attributes ConID, FName, and LName are mapped to the ContactID, FirstName, and LastName columns in the Person.Contact table by using the `sql:field` annotations.</span></span>  
  
 <span data-ttu-id="43b9e-134">Questo schema XSD con annotazioni fornisce la vista XML dei dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="43b9e-134">This annotated XSD schema provides the XML view of the relational data.</span></span> <span data-ttu-id="43b9e-135">In questa vista XML possono essere eseguite query mediante il linguaggio XPath.</span><span class="sxs-lookup"><span data-stu-id="43b9e-135">This XML view can be queried using the XPath language.</span></span> <span data-ttu-id="43b9e-136">Una query XPath restituisce come risultato un documento XML anziché il set di righe restituito dalle query SQL.</span><span class="sxs-lookup"><span data-stu-id="43b9e-136">An XPath query returns an XML document as a result, instead of the rowset that is returned by SQL queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43b9e-137">Nello schema di mapping la distinzione tra maiuscole e minuscole per i valori relazionali specificati (ad esempio il nome di tabella e il nome di colonna) dipende dall'eventuale utilizzo delle impostazioni delle regole di confronto con distinzione tra maiuscole e minuscole da parte di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43b9e-137">In the mapping schema, case-sensitivity for the specified relational values (such as table name and column name) depends upon if SQL Server is using case-sensitive collation settings.</span></span> <span data-ttu-id="43b9e-138">Per altre informazioni, vedere [Collation and Unicode Support](../../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="43b9e-138">For more information, see [Collation and Unicode Support](../../collations/collation-and-unicode-support.md).</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="43b9e-139">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="43b9e-139">Other Resources</span></span>  
 <span data-ttu-id="43b9e-140">Ulteriori informazioni sul linguaggio di definizione di XML Schema (XSD), sul linguaggio XML Path (XPath) e su Extensible Stylesheet Language Transformations (XSLT) sono disponibili nei siti Web seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b9e-140">You can find more information about XML Schema Definition language (XSD), XML Path language (XPath), and Extensible Stylesheet Language Transformations (XSLT) at the following Web sites:</span></span>  
  
-   <span data-ttu-id="43b9e-141">XML Schema Part 0: primer, raccomandazione W3C (http://www.w3.org/TR/xmlschema-0/)</span><span class="sxs-lookup"><span data-stu-id="43b9e-141">XML Schema Part 0: Primer, W3C Recommendation (http://www.w3.org/TR/xmlschema-0/)</span></span>  
  
-   <span data-ttu-id="43b9e-142">XML Schema Part 1: Structures, raccomandazione W3C (http://www.w3.org/TR/xmlschema-1/)</span><span class="sxs-lookup"><span data-stu-id="43b9e-142">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span></span>  
  
-   <span data-ttu-id="43b9e-143">XML Schema Part 2: Datatypes, raccomandazione W3C (http://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="43b9e-143">XML Schema Part 2:Datatypes, W3C Recommendation (http://www.w3.org/TR/xmlschema-2/)</span></span>  
  
-   <span data-ttu-id="43b9e-144">XPath (XML Path Language) (http://www.w3.org/TR/xpath)</span><span class="sxs-lookup"><span data-stu-id="43b9e-144">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span></span>  
  
-   <span data-ttu-id="43b9e-145">Trasformazioni XSL (XSLT) (http://www.w3.org/TR/xslt)</span><span class="sxs-lookup"><span data-stu-id="43b9e-145">XSL Transformations (XSLT) (http://www.w3.org/TR/xslt)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b9e-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43b9e-146">See Also</span></span>  
 <span data-ttu-id="43b9e-147">[Considerazioni sulla sicurezza dello schema con annotazioni &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="43b9e-147">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="43b9e-148">Schemi XDR con annotazioni &#40;deprecati in SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="43b9e-148">Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;</span></span>](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)  
  
  
