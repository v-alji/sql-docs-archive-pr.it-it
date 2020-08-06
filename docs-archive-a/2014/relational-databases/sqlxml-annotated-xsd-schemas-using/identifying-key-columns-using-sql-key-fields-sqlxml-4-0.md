---
title: 'Identificazione delle colonne chiave mediante SQL: key-fields (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nesting XML results
- proper nesting in results [SQLXML]
- sql:key-fields
- XSD schemas [SQLXML], key columns
- identifying key columns [SQLXML]
- annotated XSD schemas, key columns
- key columns [SQLXML]
- relationships [SQLXML], key columns
- hierarchical relationships [SQLXML]
- key-fields annotation
ms.assetid: 1a5ad868-8602-45c4-913d-6fbb837eebb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ab12b34874a54bad2e08a96d08ebd0cc994f946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725344"
---
# <a name="identifying-key-columns-using-sqlkey-fields-sqlxml-40"></a><span data-ttu-id="63b21-102">Identificazione delle colonne chiave mediante sql:key-fields (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="63b21-102">Identifying Key Columns Using sql:key-fields (SQLXML 4.0)</span></span>
  <span data-ttu-id="63b21-103">Quando si specifica una query XPath su uno schema XSD, nella maggior parte dei casi sono necessarie informazioni chiave per ottenere la nidificazione appropriata nel risultato.</span><span class="sxs-lookup"><span data-stu-id="63b21-103">When an XPath query is specified against an XSD schema, key information is required in most cases to obtain proper nesting in the result.</span></span> <span data-ttu-id="63b21-104">La specifica dell'annotazione `sql:key-fields` rappresenta un modo per assicurarsi che venga generata la gerarchia appropriata.</span><span class="sxs-lookup"><span data-stu-id="63b21-104">Specifying the `sql:key-fields` annotation is a way of ensuring that the appropriate hierarchy is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63b21-105">Per garantire una nidificazione appropriata, è consigliabile specificare `sql:key-fields` per gli elementi che eseguono il mapping alle tabelle.</span><span class="sxs-lookup"><span data-stu-id="63b21-105">To ensure proper nesting, it is recommended that you specify `sql:key-fields` for elements that map to tables.</span></span> <span data-ttu-id="63b21-106">Il codice XML prodotto riconosce l'ordinamento del set di risultati sottostante.</span><span class="sxs-lookup"><span data-stu-id="63b21-106">The XML produced is sensitive to the ordering of the underlying result set.</span></span> <span data-ttu-id="63b21-107">Se non si specifica `sql:key-fields`, il codice XML generato potrebbe avere un formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="63b21-107">If `sql:key-fields` is not specified, the XML generated might not be formed properly.</span></span>  
  
 <span data-ttu-id="63b21-108">Il valore di `sql:key-fields` indica le colonne che identificano in modo univoco le righe nella relazione.</span><span class="sxs-lookup"><span data-stu-id="63b21-108">The value of `sql:key-fields` identifies the column(s) that uniquely identify the rows in the relation.</span></span> <span data-ttu-id="63b21-109">Se sono necessarie più colonne per identificare in modo univoco una riga, i valori delle colonne vengono delimitati da spazi.</span><span class="sxs-lookup"><span data-stu-id="63b21-109">If more than one column is required to uniquely identify a row, the column values are delimited by spaces.</span></span>  
  
 <span data-ttu-id="63b21-110">È necessario utilizzare l' `sql:key-fields` annotazione quando un elemento contiene un oggetto **\<sql:relationship>** definito tra l'elemento e un elemento figlio ma non fornisce la chiave primaria della tabella specificata nell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="63b21-110">You must use the `sql:key-fields` annotation when an element contains a **\<sql:relationship>** that is defined between the element and a child element but does not provide the primary key of the table that is specified in the parent element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="63b21-111">Esempi</span><span class="sxs-lookup"><span data-stu-id="63b21-111">Examples</span></span>  
 <span data-ttu-id="63b21-112">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="63b21-112">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="63b21-113">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="63b21-113">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-producing-the-appropriate-nesting-when-sqlrelationship-does-not-provide-sufficient-information"></a><span data-ttu-id="63b21-114">R.</span><span class="sxs-lookup"><span data-stu-id="63b21-114">A.</span></span> <span data-ttu-id="63b21-115">Produzione della nidificazione appropriata quando non \<sql:relationship> fornisce informazioni sufficienti</span><span class="sxs-lookup"><span data-stu-id="63b21-115">Producing the appropriate nesting when \<sql:relationship> does not provide sufficient information</span></span>  
 <span data-ttu-id="63b21-116">In questo esempio viene illustrato dove specificare `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="63b21-116">This example shows where `sql:key-fields` must be specified.</span></span>  
  
 <span data-ttu-id="63b21-117">Si consideri lo schema seguente:</span><span class="sxs-lookup"><span data-stu-id="63b21-117">Consider the following schema.</span></span> <span data-ttu-id="63b21-118">Lo schema specifica una gerarchia tra gli **\<Order>** **\<Customer>** elementi e in cui l' **\<Order>** elemento è il padre e l' **\<Customer>** elemento è un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="63b21-118">The schema specifies a hierarchy between the **\<Order>** and **\<Customer>** elements in which the **\<Order>** element is the parent and the **\<Customer>** element is a child.</span></span>  
  
 <span data-ttu-id="63b21-119">Il **\<sql:relationship>** tag viene usato per specificare la relazione padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="63b21-119">The **\<sql:relationship>** tag is used to specify the parent-child relationship.</span></span> <span data-ttu-id="63b21-120">che identifica CustomerID nella tabella Sales.SalesOrderHeader come chiave padre che fa riferimento alla chiave figlio CustomerID nella tabella Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="63b21-120">It identifies CustomerID in the Sales.SalesOrderHeader table as the parent key that refers to the CustomerID child key in the Sales.Customer table.</span></span> <span data-ttu-id="63b21-121">Le informazioni fornite in **\<sql:relationship>** non sono sufficienti per identificare in modo univoco le righe nella tabella padre (Sales. SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="63b21-121">The information provided in **\<sql:relationship>** is not sufficient to uniquely identify rows in the parent table (Sales.SalesOrderHeader).</span></span> <span data-ttu-id="63b21-122">Se non si specifica l'annotazione `sql:key-fields`, la gerarchia generata non è precisa.</span><span class="sxs-lookup"><span data-stu-id="63b21-122">Therefore, without the `sql:key-fields` annotation, the hierarchy that is generated is inaccurate.</span></span>  
  
 <span data-ttu-id="63b21-123">Con `sql:key-fields` specificato on **\<Order>** , l'annotazione identifica in modo univoco le righe nel padre (tabella Sales. SalesOrderHeader) e i relativi elementi figlio vengono visualizzati al di sotto del padre.</span><span class="sxs-lookup"><span data-stu-id="63b21-123">With `sql:key-fields` specified on **\<Order>**, the annotation uniquely identifies the rows in the parent (Sales.SalesOrderHeader table), and its child elements appear below its parent.</span></span>  
  
 <span data-ttu-id="63b21-124">Lo schema è il seguente:</span><span class="sxs-lookup"><span data-stu-id="63b21-124">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrdCust"  
        parent="Sales.SalesOrderHeader"  
        parent-key="CustomerID"  
        child="Sales.Customer"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
               sql:key-fields="SalesOrderID">  
   <xsd:complexType>  
     <xsd:sequence>  
     <xsd:element name="Customer" sql:relation="Sales.Customer"   
                       sql:relationship="OrdCust"  >  
       <xsd:complexType>  
         <xsd:attribute name="CustID" sql:field="CustomerID" />  
         <xsd:attribute name="SoldBy" sql:field="SalesPersonID" />  
       </xsd:complexType>  
     </xsd:element>  
     </xsd:sequence>  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name= "CustomerID" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="63b21-125">Per creare un esempio reale di questo schema</span><span class="sxs-lookup"><span data-stu-id="63b21-125">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="63b21-126">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="63b21-126">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="63b21-127">Salvare il file come KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="63b21-127">Save the file as KeyFields1.xml.</span></span>  
  
2.  <span data-ttu-id="63b21-128">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="63b21-128">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="63b21-129">Salvare il file come KeyFields1T.xml nella stessa directory nella quale è stato salvato KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="63b21-129">Save the file as KeyFields1T.xml in the same directory where you saved KeyFields1.xml.</span></span> <span data-ttu-id="63b21-130">La query XPath nel modello restituisce tutti gli **\<Order>** elementi con un CustomerID minore di 3.</span><span class="sxs-lookup"><span data-stu-id="63b21-130">The XPath query in the template returns all the **\<Order>** elements with a CustomerID of less than 3.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="KeyFields1.xml">  
            /Order[@CustomerID < 3]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="63b21-131">Il percorso di directory specificato per lo schema di mapping (KeyFields1.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="63b21-131">The directory path specified for the mapping schema (KeyFields1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="63b21-132">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="63b21-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields1.xml"  
    ```  
  
3.  <span data-ttu-id="63b21-133">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="63b21-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="63b21-134">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="63b21-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="63b21-135">Di seguito è riportato il set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="63b21-135">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
    <Order SalesOrderID="43860" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="44501" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="45283" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    .....  
</ROOT>  
```  
  
### <a name="b-specifying-sqlkey-fields-to-produce-proper-nesting-in-the-result"></a><span data-ttu-id="63b21-136">B.</span><span class="sxs-lookup"><span data-stu-id="63b21-136">B.</span></span> <span data-ttu-id="63b21-137">Specifica di sql:key-fields per produrre una nidificazione appropriata nel risultato</span><span class="sxs-lookup"><span data-stu-id="63b21-137">Specifying sql:key-fields to produce proper nesting in the result</span></span>  
 <span data-ttu-id="63b21-138">Nello schema seguente non è specificata alcuna gerarchia usando **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="63b21-138">In the following schema, there is no hierarchy specified using **\<sql:relationship>**.</span></span> <span data-ttu-id="63b21-139">Lo schema richiede ancora la specifica dell'annotazione `sql:key-fields` per identificare in modo univoco i dipendenti nella tabella HumanResources.Employee.</span><span class="sxs-lookup"><span data-stu-id="63b21-139">The schema still requires specifying the `sql:key-fields` annotation to uniquely identify employees in the HumanResources.Employee table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="HumanResources.Employee" sql:key-fields="EmployeeID" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Title">  
          <xsd:complexType>  
            <xsd:simpleContent>  
              <xsd:extension base="xsd:string">  
                 <xsd:attribute name="EmployeeID" type="xsd:integer" />  
              </xsd:extension>  
            </xsd:simpleContent>  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="63b21-140">Per creare un esempio reale di questo schema</span><span class="sxs-lookup"><span data-stu-id="63b21-140">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="63b21-141">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="63b21-141">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="63b21-142">Salvare il file come KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="63b21-142">Save the file as KeyFields2.xml.</span></span>  
  
2.  <span data-ttu-id="63b21-143">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="63b21-143">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="63b21-144">Salvare il file come KeyField21T.xml nella stessa directory nella quale è stato salvato KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="63b21-144">Save the file as KeyFields2T.xml in the same directory where you saved KeyFields2.xml.</span></span> <span data-ttu-id="63b21-145">La query XPath nel modello restituisce tutti gli **\<HumanResources.Employee>** elementi:</span><span class="sxs-lookup"><span data-stu-id="63b21-145">The XPath query in the template returns all the **\<HumanResources.Employee>** elements:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="KeyFields2.xml">  
        /HumanResources.Employee  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="63b21-146">Il percorso di directory specificato per lo schema di mapping (KeyFields2.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="63b21-146">The directory path specified for the mapping schema (KeyFields2.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="63b21-147">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="63b21-147">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields2.xml"  
    ```  
  
3.  <span data-ttu-id="63b21-148">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="63b21-148">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="63b21-149">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="63b21-149">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="63b21-150">Risultato:</span><span class="sxs-lookup"><span data-stu-id="63b21-150">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <HumanResources.Employee>  
    <Title EmployeeID="1">Production Technician - WC60</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="2">Marketing Assistant</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="3">Engineering Manager</Title>   
  </HumanResources.Employee>  
  ...  
</ROOT>  
```  
  
  
