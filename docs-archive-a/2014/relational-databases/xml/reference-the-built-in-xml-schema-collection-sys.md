---
title: Fare riferimento alla raccolta di XML Schema predefinita (sys) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- sys XML schema collections [SQL Server]
- schema collections [SQL Server], predefined
- predefined XML schema collections [SQL Server]
- XML schema collections [SQL Server], predefined
- built-in XML schema collections [SQL Server]
ms.assetid: 1e118303-5df0-4ee4-bd8d-14ced7544144
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fa30107e1746b33e3f9b8eb1cfa53d1f4d25fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713923"
---
# <a name="reference-the-built-in-xml-schema-collection-sys"></a><span data-ttu-id="2c217-102">Riferimento alla raccolta di XML Schema predefinita (sys)</span><span class="sxs-lookup"><span data-stu-id="2c217-102">Reference the Built-in XML Schema Collection (sys)</span></span>
  <span data-ttu-id="2c217-103">Per ogni database creato è disponibile una raccolta di XML Schema **sys** predefinita nello schema relazionale **sys** .</span><span class="sxs-lookup"><span data-stu-id="2c217-103">Every database you create has a predefined **sys** XML schema collection in the **sys** relational schema.</span></span> <span data-ttu-id="2c217-104">Tale raccolta riserva questi schemi predefiniti, ai quali è possibile accedere da qualsiasi altra raccolta XML Schema creata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2c217-104">It reserves these predefined schemas, and they can be accessed from any other user-created XML schema collection.</span></span> <span data-ttu-id="2c217-105">I prefissi utilizzati negli schemi predefiniti sono significativi in XQuery.</span><span class="sxs-lookup"><span data-stu-id="2c217-105">The prefixes used in these predefined schemas are meaningful in XQuery.</span></span> <span data-ttu-id="2c217-106">L'unico prefisso riservato è **xml** .</span><span class="sxs-lookup"><span data-stu-id="2c217-106">Only **xml** is a reserved prefix.</span></span>  
  
```  
xml = http://www.w3.org/XML/1998/namespace  
xs = http://www.w3.org/2001/XMLSchema  
xsi = http://www.w3.org/2001/XMLSchema-instance  
fn = http://www.w3.org/2004/07/xpath-functions  
sqltypes = https://schemas.microsoft.com/sqlserver/2004/sqltypes  
xdt = http://www.w3.org/2004/07/xpath-datatypes  
(no prefix) = urn:schemas-microsoft-com:xml-sql  
(no prefix) = https://schemas.microsoft.com/sqlserver/2004/SOAP  
```  
  
 <span data-ttu-id="2c217-107">Si noti che lo spazio dei nomi **sqltypes** contiene componenti ai quali è possibile fare riferimento da qualsiasi raccolta di XML Schema creata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2c217-107">Note that the **sqltypes** namespace contains components that can be referenced from any user-created XML schema collection.</span></span> <span data-ttu-id="2c217-108">È possibile scaricare lo schema **sqltypes** da questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?linkid=31850).</span><span class="sxs-lookup"><span data-stu-id="2c217-108">You can download the **sqltypes** schema from this [Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=31850).</span></span> <span data-ttu-id="2c217-109">I componenti predefiniti sono:</span><span class="sxs-lookup"><span data-stu-id="2c217-109">The built-in components include the following:</span></span>  
  
-   <span data-ttu-id="2c217-110">I tipi XSD</span><span class="sxs-lookup"><span data-stu-id="2c217-110">XSD types</span></span>  
  
-   <span data-ttu-id="2c217-111">Gli attributi XML **lang**, **base**e **space**</span><span class="sxs-lookup"><span data-stu-id="2c217-111">XML attributes **lang**, **base**, and **space**</span></span>  
  
-   <span data-ttu-id="2c217-112">I componenti dello spazio dei nomi **sqltypes**</span><span class="sxs-lookup"><span data-stu-id="2c217-112">Components of the **sqltypes** namespace</span></span>  
  
 <span data-ttu-id="2c217-113">La query seguente restituisce i componenti predefiniti ai quali è possibile fare riferimento da una raccolta XML Schema creata dall'utente:</span><span class="sxs-lookup"><span data-stu-id="2c217-113">The following query returns built-in components that can be referenced from a user-created XML schema collection:</span></span>  
  
```  
SELECT C.name, N.name, C.symbol_space_desc from sys.xml_schema_components C join sys.xml_schema_namespaces N  
on ((C.xml_namespace_id = N.xml_namespace_id) AND (C.xml_collection_id = N.xml_collection_id))  
join sys.xml_schema_collections SC  
on SC.xml_collection_id = C.xml_collection_id  
where ((C.xml_collection_id = 1) AND (C.name is not null) AND (C.scoping_xml_component_id is null)   
AND (SC.schema_id = 4))  
GO  
```  
  
 <span data-ttu-id="2c217-114">Nell'esempio seguente viene illustrato come viene fatto riferimento a tali componenti in uno schema utente.</span><span class="sxs-lookup"><span data-stu-id="2c217-114">The following example shows how these components are referenced in a user schema.</span></span> <span data-ttu-id="2c217-115">`CREATE XML SCHEMA COLLECTION` consente di creare una raccolta di XML Schema che fa riferimento al `varchar` tipo definito nello spazio dei nomi `sqltypes` .</span><span class="sxs-lookup"><span data-stu-id="2c217-115">`CREATE XML SCHEMA COLLECTION` creates an XML schema collection that references the `varchar` type defined in the `sqltypes` namespace.</span></span> <span data-ttu-id="2c217-116">e inoltre all'attributo `lang` definito nello spazio dei nomi `xml` .</span><span class="sxs-lookup"><span data-stu-id="2c217-116">The example also references the `lang` attribute that is defined in the `xml` namespace.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema   
   xmlns="http://www.w3.org/2001/XMLSchema"   
   targetNamespace="myNS"  
   xmlns:ns="myNS"  
   xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
   <import namespace="http://www.w3.org/XML/1998/namespace"/>  
   <import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
   <element name="root">  
      <complexType>  
          <sequence>  
             <element name="a" type="string"/>  
             <element name="b" type="string"/>  
             <!-- varchar type is defined in the sys.sys collection and   
                  can be referenced in any user-defined schema -->  
             <element name="c" type="s:varchar"/>  
          </sequence>  
          <attribute name="att" type="int"/>  
          <!-- xml:lang attribute is defined in the sys.sys collection   
               and can be referenced in any user-defined schema -->  
          <attribute ref="xml:lang"/>  
      </complexType>  
    </element>  
 </schema>'  
GO  
 -- Cleanup  
DROP xml schema collection SC   
GO  
```  
  
 <span data-ttu-id="2c217-117">Si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2c217-117">You should note the following:</span></span>  
  
-   <span data-ttu-id="2c217-118">Non è possibile modificare XML Schema con questi spazi dei nomi in nessuna raccolta XML Schema definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2c217-118">You cannot modify XML schemas with these namespaces in any user-defined XML schema collection.</span></span> <span data-ttu-id="2c217-119">Ad esempio, la raccolta XML Schema seguente genera un errore perché aggiunge un componente allo spazio dei nomi protetto `sqltypes` :</span><span class="sxs-lookup"><span data-stu-id="2c217-119">For example, the following XML schema collection fails, because it is adding a component to the `sqltypes` protected namespace:</span></span>  
  
    ```  
    CREATE XML SCHEMA COLLECTION SC AS '  
    <schema xmlns="http://www.w3.org/2001/XMLSchema"   
    targetNamespace    
        ="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
          <element name="root" type="string"/>  
    </schema>'  
    GO  
    ```  
  
-   <span data-ttu-id="2c217-120">Non è possibile utilizzare la raccolta XML Schema `sys` nelle colonne, variabili o parametri di tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="2c217-120">You cannot use the `sys` XML schema collection to type `xml` columns, variables, or parameters.</span></span> <span data-ttu-id="2c217-121">Il codice seguente, ad esempio, restituisce un errore:</span><span class="sxs-lookup"><span data-stu-id="2c217-121">For example, the following code returns an error:</span></span>  
  
    ```  
    DECLARE @x xml (sys.sys)  
    ```  
  
-   <span data-ttu-id="2c217-122">La serializzazione di questi schemi predefiniti non è supportata.</span><span class="sxs-lookup"><span data-stu-id="2c217-122">Serialization of these built-in schemas is not supported.</span></span> <span data-ttu-id="2c217-123">Il codice seguente, ad esempio, restituisce un errore:</span><span class="sxs-lookup"><span data-stu-id="2c217-123">For example, the following code returns an error:</span></span>  
  
    ```  
    SELECT XML_SCHEMA_NAMESPACE(N'sys',N'sys')  
    GO  
    ```  
  
 <span data-ttu-id="2c217-124">Il codice seguente rappresenta un altro esempio nel quale viene creata una raccolta XML Schema che utilizza il tipo `varchar` definito nello spazio dei nomi `sqltypes` :</span><span class="sxs-lookup"><span data-stu-id="2c217-124">The following code is another example in which you create an XML schema collection that uses the `varchar` type defined in the `sqltypes` namespace:</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="myNS" xmlns:ns="myNS"  
        xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes">  
   <import     
     namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
      <simpleType name="myType">  
            <restriction base="s:varchar">  
                  <maxLength value="20"/>  
            </restriction>  
      </simpleType>  
      <element name="root" type="ns:myType"/>  
</schema>'  
go  
```  
  
 <span data-ttu-id="2c217-125">Come illustrato nell'esempio seguente, è possibile creare una variabile `XML` tipizzata, assegnarvi un'istanza XML e verificare che il valore del tipo di elemento <`root`> corrisponda a un tipo `varchar`.</span><span class="sxs-lookup"><span data-stu-id="2c217-125">As shown in the following, you can create a typed `XML` variable, assign an XML instance to it, and verify that the value of the <`root`> element type is a `varchar` type.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root xmlns="myNS">My data</root>'  
SELECT @var.query('declare namespace sqltypes = "https://schemas.microsoft.com/sqlserver/2004/sqltypes";  
declare namespace ns="myNS";   
data(/ns:root[1]) instance of sqltypes:varchar?')  
GO  
```  
  
 <span data-ttu-id="2c217-126">L'espressione `instance of sqltypes:varchar?`restituisce TRUE, perché il valore dell'elemento <`root`> è di un tipo derivato da **varchar** in base allo schema associato alla variabile `@var`.</span><span class="sxs-lookup"><span data-stu-id="2c217-126">The `instance of sqltypes:varchar?` expression returns TRUE, because the <`root`> element value is of a type derived from **varchar** according to the schema that is associated with the `@var` variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c217-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c217-127">See Also</span></span>  
 [<span data-ttu-id="2c217-128">Raccolte di XML Schema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c217-128">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
