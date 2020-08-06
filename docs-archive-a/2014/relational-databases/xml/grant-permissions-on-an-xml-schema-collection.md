---
title: Concedere le autorizzazioni per una raccolta di XML Schema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- granting permissions [SQL Server], XML schema collections
- ALTER permission
ms.assetid: ffbb829c-3b8f-4e5d-97d9-ab4059aab0db
author: rothja
ms.author: jroth
ms.openlocfilehash: 2dc6384acb2f079245c80923e683ebe2c03d2562
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712843"
---
# <a name="grant-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="e6d95-102">Concedere autorizzazioni per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="e6d95-102">Grant Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="e6d95-103">È possibile concedere autorizzazioni per la creazione di una raccolta di XML Schema, nonché per un oggetto di una raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e6d95-103">You can grant permissions to create an XML schema collection and also grant permissions on an XML schema collection object.</span></span>  
  
## <a name="granting-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="e6d95-104">Concessione dell'autorizzazione per la creazione di una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="e6d95-104">Granting Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="e6d95-105">Per creare una raccolta di XML Schema, sono necessarie le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6d95-105">To create an XML schema collection, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="e6d95-106">Per l'entità è necessaria l'autorizzazione CREATE XML SCHEMA COLLECTION a livello di database.</span><span class="sxs-lookup"><span data-stu-id="e6d95-106">The principal requires CREATE XML SCHEMA COLLECTION permission at the database-level.</span></span>  
  
-   <span data-ttu-id="e6d95-107">Poiché le raccolte di XML Schema rientrano nell'ambito dello schema relazionale, l'entità deve disporre inoltre dell'autorizzazione ALTER per lo schema relazionale.</span><span class="sxs-lookup"><span data-stu-id="e6d95-107">Because the XML schema collections are relational schema-scoped, the principal must also have ALTER permission on the relational schema.</span></span>  
  
 <span data-ttu-id="e6d95-108">Le autorizzazioni seguenti consentono a un'entità di creare una raccolta XML Schema in uno schema relazionale all'interno di un database in un server:</span><span class="sxs-lookup"><span data-stu-id="e6d95-108">The following permissions let a principal create an XML schema collection in a relational schema in a database on a server:</span></span>  
  
-   <span data-ttu-id="e6d95-109">Autorizzazione CONTROL nel server</span><span class="sxs-lookup"><span data-stu-id="e6d95-109">CONTROL permission on the server</span></span>  
  
-   <span data-ttu-id="e6d95-110">Autorizzazione ALTER ANY DATABASE nel server</span><span class="sxs-lookup"><span data-stu-id="e6d95-110">ALTER ANY DATABASE permission on the server</span></span>  
  
-   <span data-ttu-id="e6d95-111">Autorizzazione ALTER per il database</span><span class="sxs-lookup"><span data-stu-id="e6d95-111">ALTER permission on the database</span></span>  
  
-   <span data-ttu-id="e6d95-112">Autorizzazione CONTROL per il database</span><span class="sxs-lookup"><span data-stu-id="e6d95-112">CONTROL permission in the database</span></span>  
  
-   <span data-ttu-id="e6d95-113">Autorizzazioni ALTER ANY SCHEMA e CREATE XML SCHEMA COLLECTION per il database</span><span class="sxs-lookup"><span data-stu-id="e6d95-113">ALTER ANY SCHEMA permission and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
-   <span data-ttu-id="e6d95-114">Autorizzazione ALTER o CONTROL nello schema relazionale e autorizzazione CREATE XML SCHEMA COLLECTION nel database</span><span class="sxs-lookup"><span data-stu-id="e6d95-114">ALTER or CONTROL permission on the relational schema and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
 <span data-ttu-id="e6d95-115">L'ultimo metodo di autorizzazione viene utilizzato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d95-115">This last method of permissions is used in the following example.</span></span>  
  
 <span data-ttu-id="e6d95-116">Il proprietario dello schema relazionale diventa il proprietario della raccolta di XML Schema creata in tale schema</span><span class="sxs-lookup"><span data-stu-id="e6d95-116">The owner of the relational schema becomes the owner of the XML schema collection created in that schema.</span></span> <span data-ttu-id="e6d95-117">e dispone quindi del controllo completo sulla raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e6d95-117">This owner then has full control over the XML schema collection.</span></span> <span data-ttu-id="e6d95-118">Pertanto, questo proprietario può modificare la raccolta di XML Schema, tipizzare una colonna XML o eliminare la raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e6d95-118">Therefore, this owner can modify the XML schema collection, type an xml column, or drop the XML schema collection.</span></span>  
  
## <a name="granting-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="e6d95-119">Concessione di autorizzazioni per un oggetto della raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="e6d95-119">Granting Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="e6d95-120">Per la raccolta di XML Schema sono consentite le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6d95-120">The following permissions are allowed on the XML schema collection:</span></span>  
  
-   <span data-ttu-id="e6d95-121">L'autorizzazione ALTER è necessaria per la modifica del contenuto di una raccolta di XML Schema esistente tramite l'istruzione ALTER XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="e6d95-121">The ALTER permission is required when modifying contents of an existing XML schema collection by using the ALTER XML SCHEMA COLLECTION statement.</span></span>  
  
-   <span data-ttu-id="e6d95-122">L'autorizzazione CONTROL consente a un utente di eseguire qualsiasi operazione sulla raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e6d95-122">The CONTROL permission lets a user perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="e6d95-123">L'autorizzazione TAKE OWNERSHIP è necessaria per trasferire la proprietà della raccolta di XML Schema da un'entità a un'altra.</span><span class="sxs-lookup"><span data-stu-id="e6d95-123">The TAKE OWNERSHIP permission is required to transfer ownership of the XML schema collection from one principal to another.</span></span>  
  
-   <span data-ttu-id="e6d95-124">L'autorizzazione REFERENCES consente all'entità di utilizzare la raccolta di XML Schema per tipizzare o vincolare colonne di tipo `xml` in tabelle, viste e parametri.</span><span class="sxs-lookup"><span data-stu-id="e6d95-124">The REFERENCES permission authorizes the principal to use the XML schema collection to type or constrain `xml` type columns, in tables and views and parameters.</span></span> <span data-ttu-id="e6d95-125">L'autorizzazione REFERENCES è necessaria inoltre quando una raccolta di XML Schema fa riferimento a un'altra.</span><span class="sxs-lookup"><span data-stu-id="e6d95-125">The REFERENCES permission is also required when one XML schema collection refers to another.</span></span>  
  
-   <span data-ttu-id="e6d95-126">L'autorizzazione VIEW DEFINITION consente all'entità di eseguire query sul contenuto di una raccolta di XML Schema tramite XML_SCHEMA_NAMESPACE o mediante le viste del catalogo, a condizione che l'entità disponga inoltre di una delle autorizzazioni ALTER, REFERENCES o CONTROL per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="e6d95-126">The VIEW DEFINITION permission allows the principal to query the contents of an XML schema collection either through XML_SCHEMA_NAMESPACE or through the catalog views, provided this principal also has one of the ALTER, REFERENCES, or CONTROL permissions on the collection.</span></span>  
  
-   <span data-ttu-id="e6d95-127">L'autorizzazione EXECUTE è necessaria per convalidare i valori inseriti o aggiornati dall'entità in base alla raccolta di XML Schema utilizzato per tipizzare o vincolare le colonne di tipo `xml`, le variabili e i parametri.</span><span class="sxs-lookup"><span data-stu-id="e6d95-127">The EXECUTE permission is required to validate values inserted or updated by the principal against the XML schema collection that is typing or constraining the `xml` type columns, variables, and parameters.</span></span> <span data-ttu-id="e6d95-128">Questa autorizzazione è necessaria inoltre quando si eseguono query sui dati XML archiviati in tali colonne e variabili.</span><span class="sxs-lookup"><span data-stu-id="e6d95-128">You also need this permission when you are querying the XML stored in these columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e6d95-129">Esempi</span><span class="sxs-lookup"><span data-stu-id="e6d95-129">Examples</span></span>  
 <span data-ttu-id="e6d95-130">Gli scenari degli esempi seguenti illustrano il funzionamento delle autorizzazioni per XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e6d95-130">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="e6d95-131">In ogni esempio vengono creati il database di prova, gli schemi relazionali e gli account di accesso necessari.</span><span class="sxs-lookup"><span data-stu-id="e6d95-131">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="e6d95-132">A tali account di accesso vengono concesse le autorizzazioni necessarie per la raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e6d95-132">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="e6d95-133">Alla fine di ogni esempio viene eseguito il processo di eliminazione necessario.</span><span class="sxs-lookup"><span data-stu-id="e6d95-133">Each example does the necessary clean up at the end.</span></span>  
  
### <a name="a-granting-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="e6d95-134">R.</span><span class="sxs-lookup"><span data-stu-id="e6d95-134">A.</span></span> <span data-ttu-id="e6d95-135">Concessione di autorizzazioni per la creazione di una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="e6d95-135">Granting permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="e6d95-136">Nell'esempio seguente viene illustrato come concedere autorizzazioni per consentire a un'entità di creare una raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e6d95-136">The following example shows how to grant permissions so that a principal can create an XML schema collection.</span></span> <span data-ttu-id="e6d95-137">Nell'esempio vengono creati un database di esempio e un utente di prova, `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="e6d95-137">The example creates a sample database and a test user, `TestLogin1`.</span></span> <span data-ttu-id="e6d95-138">`TestLogin1` viene fornita quindi l'autorizzazione `ALTER` per lo schema relazionale e l'autorizzazione `CREATE XML SCHEMA COLLECTION` per il database.</span><span class="sxs-lookup"><span data-stu-id="e6d95-138">`TestLogin1` is then given `ALTER` permission on the relational schema and given `CREATE XML SCHEMA COLLECTION` permission on the database.</span></span> <span data-ttu-id="e6d95-139">Con tali autorizzazioni, `TestLogin1` può creare una raccolta di XML Schema di esempio.</span><span class="sxs-lookup"><span data-stu-id="e6d95-139">With these permissions, `TestLogin1` succeeds in creating a sample XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Execute CREATE XML SCHEMA COLLECTION.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="root" type="xsd:byte"/>  
</xsd:schema>'  
GO  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="b-granting-permission-to-use-an-existing-xml-schema-collection"></a><span data-ttu-id="e6d95-140">B.</span><span class="sxs-lookup"><span data-stu-id="e6d95-140">B.</span></span> <span data-ttu-id="e6d95-141">Concessione dell'autorizzazione per l'utilizzo di una raccolta di XML Schema esistente</span><span class="sxs-lookup"><span data-stu-id="e6d95-141">Granting permission to use an existing XML schema collection</span></span>  
 <span data-ttu-id="e6d95-142">Nell'esempio seguente viene illustrato ulteriormente il modello di autorizzazione per la raccolta di XML Schema,</span><span class="sxs-lookup"><span data-stu-id="e6d95-142">The following example further shows the permission model for the XML schema collection.</span></span> <span data-ttu-id="e6d95-143">con le diverse autorizzazioni necessarie per creare e utilizzare tale raccolta.</span><span class="sxs-lookup"><span data-stu-id="e6d95-143">The example shows how different permissions are required to create and use the XML schema collection.</span></span>  
  
 <span data-ttu-id="e6d95-144">Nell'esempio vengono creati un database di prova e l'account di accesso `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="e6d95-144">The example creates a test database and a login, `TestLogin1`.</span></span> <span data-ttu-id="e6d95-145">`TestLogin1` crea una raccolta di XML Schema nel database.</span><span class="sxs-lookup"><span data-stu-id="e6d95-145">`TestLogin1` creates an XML schema collection in the database.</span></span> <span data-ttu-id="e6d95-146">L'account di accesso crea quindi una tabella e utilizza la raccolta di XML Schema per creare una colonna XML tipizzata.</span><span class="sxs-lookup"><span data-stu-id="e6d95-146">The login then creates a table and uses the XML schema collection to create a typed xml column.</span></span> <span data-ttu-id="e6d95-147">Successivamente, l'utente inserisce i dati ed esegue le relative query.</span><span class="sxs-lookup"><span data-stu-id="e6d95-147">The user then inserts data and queries it.</span></span> <span data-ttu-id="e6d95-148">Tutti questi passaggi richiedono le autorizzazioni necessarie per lo schema, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d95-148">All these steps require the necessary schema permissions, as shown in the code.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Create a table by using the collection to type an XML column.   
--TestLogin1 must have permission to create a table.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also must have REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- Now user can create a table and use the XML schema collection to create   
-- a typed XML column.  
SETUSER 'TestLogin1'  
GO  
CREATE TABLE MyTestTable (xmlCol xml (dbo.myTestSchemaCollection))  
GO  
-- To insert data in the table, the user needs EXECUTE permission on the XML schema collection.  
-- GRANT EXECUTE permission to TestLogin2 on the xml schema collection.  
SETUSER  
GO  
GRANT EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- TestLogin1 does not own the dbo schema. This user must have INSERT permission.  
GRANT INSERT TO TestLogin1  
GO  
-- Now the user can insert data into the table.  
SETUSER 'TestLogin1'  
GO  
INSERT INTO MyTestTable VALUES('  
<telephone xmlns="http://schemas.adventure-works.com/Additional/ContactInfo">111-1111</telephone>  
')  
GO  
-- To query the table, TestLogin1 must have permissions: SELECT on the table and EXECUTE on the XML schema collection.  
SETUSER  
GO  
GRANT SELECT TO TestLogin1  
GO  
-- TestLogin1 already has EXECUTE permission on the schema (granted before inserting a record in the table).  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- To show that the user must have EXECUTE permission to query, revoke the  
-- previously granted permission and return the query.  
SETUSER  
GO  
REVOKE EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection to TestLogin1  
Go  
-- Now TestLogin1 cannot execute the query.  
SETUSER 'TestLogin1'  
GO  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="c-granting-alter-permission-on-an-xml-schema-collection"></a><span data-ttu-id="e6d95-149">C.</span><span class="sxs-lookup"><span data-stu-id="e6d95-149">C.</span></span> <span data-ttu-id="e6d95-150">Concessione dell'autorizzazione ALTER per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="e6d95-150">Granting ALTER permission on an XML schema collection</span></span>  
 <span data-ttu-id="e6d95-151">Un utente deve disporre dell'autorizzazione ALTER per modificare una raccolta di XML Schema esistente nel database.</span><span class="sxs-lookup"><span data-stu-id="e6d95-151">A user must have ALTER permission to modify an existing XML schema collection in the database.</span></span> <span data-ttu-id="e6d95-152">Nell'esempio seguente viene illustrato come concedere l'autorizzazione `ALTER` .</span><span class="sxs-lookup"><span data-stu-id="e6d95-152">The following example shows how to grant `ALTER` permission.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant ALTER permission to TestLogin1.  
setuser  
GO  
GRANT ALTER ON XML SCHEMA COLLECTION::myTestSchemaCollection TO TestLogin1  
GO  
-- TestLogin1 should be able to add components to the collection.  
SETUSER 'TestLogin1'  
GO  
ALTER XML SCHEMA COLLECTION myTestSchemaCollection ADD '  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns="http://schemas.adventure-works.com/Additional/ContactInfo"   
elementFormDefault="qualified">  
 <xsd:element name="pager" type="xsd:string"/>  
</xsd:schema>  
'  
Go  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="d-granting-take-ownership-permission-on-an-xml-schema-collection"></a><span data-ttu-id="e6d95-153">D.</span><span class="sxs-lookup"><span data-stu-id="e6d95-153">D.</span></span> <span data-ttu-id="e6d95-154">Concessione dell'autorizzazione TAKE OWNERSHIP per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="e6d95-154">Granting TAKE OWNERSHIP permission on an XML schema collection</span></span>  
 <span data-ttu-id="e6d95-155">Nell'esempio seguente viene illustrato il trasferimento della proprietà di XML Schema da un utente a un altro.</span><span class="sxs-lookup"><span data-stu-id="e6d95-155">The following example shows how to transfer XML schema ownership from one user to another.</span></span> <span data-ttu-id="e6d95-156">Per rendere più interessante l'esempio, si supponga che gli utenti utilizzino schemi relazionali diversi.</span><span class="sxs-lookup"><span data-stu-id="e6d95-156">To make the example more interesting, the users in this example work in different default relational schemas.</span></span>  
  
 <span data-ttu-id="e6d95-157">In questo esempio vengono eseguite le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6d95-157">This example does the following:</span></span>  
  
-   <span data-ttu-id="e6d95-158">Viene creato un database con due schemi relazionali, `dbo` e `myOtherDBSchema`.</span><span class="sxs-lookup"><span data-stu-id="e6d95-158">Creates a database with two relational schemas, `dbo` and `myOtherDBSchema`).</span></span>  
  
-   <span data-ttu-id="e6d95-159">Vengono creati due account utente, `TestLogin1` e `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="e6d95-159">Creates two users, `TestLogin1` and `TestLogin2`.</span></span> <span data-ttu-id="e6d95-160">`TestLogin2` viene definito come proprietario dello schema relazionale `myOtherDBSchema` .</span><span class="sxs-lookup"><span data-stu-id="e6d95-160">`TestLogin2` is made the owner of the `myOtherDBSchema` relational schema.</span></span>  
  
-   <span data-ttu-id="e6d95-161">`TestLogin1` crea una raccolta di XML Schema nello schema relazionale `dbo` .</span><span class="sxs-lookup"><span data-stu-id="e6d95-161">`TestLogin1` creates an XML schema collection in the `dbo` relational schema.</span></span>  
  
-   <span data-ttu-id="e6d95-162">`TestLogin1` concede quindi l'autorizzazione `TAKE OWNERSHIP` per la raccolta di XML Schema a `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="e6d95-162">`TestLogin1` then gives `TAKE OWNERSHIP` permission on the XML schema collection to `TestLogin2`.</span></span>  
  
-   <span data-ttu-id="e6d95-163">`TestLogin2` diventa il proprietario della raccolta di XML Schema in `myOtherDBSchema`senza modificarne lo schema relazionale.</span><span class="sxs-lookup"><span data-stu-id="e6d95-163">`TestLogin2` becomes the owner of the XML schema collection in `myOtherDBSchema`, without changing the relational schema of the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 with password='SQLSvrPwd1'  
GO  
CREATE LOGIN TestLogin2 with password='SQLSvrPwd2'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
-- Create users in the database. Note TestLogin2's default schema is  
-- myOtherDBSchema.  
CREATE USER TestLogin1  
GO  
CREATE USER TestLogin2 WITH DEFAULT_SCHEMA=myOtherDBSchema  
GO  
-- TestLogin2 will own myOtherDBSchema relational schema.  
ALTER AUTHORIZATION ON SCHEMA::myOtherDBSchema TO TestLogin2  
GO  
  
-- For TestLogin1 to create XML schema collection, the following  
-- permission is required.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- Now TestLogin1 can create an XML schema collection.  
setuser 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
 <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"   
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
 </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Grant TAKE OWNERSHIP to TestLogin2.  
SETUSER  
GO  
GRANT TAKE OWNERSHIP ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Verify the owner. Note the UserName and Principal_id is null.   
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections   
      JOIN sys.schemas   
      ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- TestLogin2 can take ownership now.  
setuser 'TestLogin2'  
GO  
ALTER AUTHORIZATION ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Note that although TestLogin2 is the owner,the XML schema collection   
-- is still in dbo.  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
      sys.schemas.name as RelSchemaName,*   
FROM sys.xml_schema_collections JOIN sys.schemas   
     ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
  
-- TestLogin2 moves the collection from dbo to myOtherDBSchema relational schema.  
-- TestLogin2 already has all necessary permissions.  
-- 1) TestLogin2 owns the destination relational schema so he can alter it.  
-- 2) TestLogin2 owns the XML schema collection (therefore, has CONTROL permission).  
ALTER SCHEMA myOtherDBSchema  
TRANSFER XML SCHEMA COLLECTION::dbo.myTestSchemaCollection  
GO  
  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections JOIN sys.schemas   
       ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
DROP LOGIN TestLogin2  
go   
```  
  
### <a name="e-granting-view-definition-permission-on-an-xml-schema-collection"></a><span data-ttu-id="e6d95-164">E.</span><span class="sxs-lookup"><span data-stu-id="e6d95-164">E.</span></span> <span data-ttu-id="e6d95-165">Concessione dell'autorizzazione VIEW DEFINITION per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="e6d95-165">Granting VIEW DEFINITION permission on an XML schema collection</span></span>  
 <span data-ttu-id="e6d95-166">Nell'esempio seguente viene illustrato come concedere autorizzazioni VIEW DEFINITION per una raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e6d95-166">The following example shows how to grant VIEW DEFINITION permissions for an XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
IF EXISTS( SELECT * FROM sysdatabases WHERE name='permissionsDB' )  
   DROP DATABASE permissionsDB  
GO  
IF EXISTS( SELECT * FROM sys.sql_logins WHERE name='schemaUser' )  
   DROP LOGIN schemaUser  
GO  
CREATE DATABASE permissionsDB  
GO  
CREATE LOGIN schemaUser WITH PASSWORD='Pass#123',DEFAULT_DATABASE=permissionsDB  
GO  
GRANT CONNECT SQL TO schemaUser  
GO  
USE permissionsDB  
GO  
CREATE USER schemaUser WITH DEFAULT_SCHEMA=dbo  
GO  
CREATE XML SCHEMA COLLECTION MySC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns"  
xmlns:ns="http://ns">  
  
   <simpleType name="ListOfIntegers">  
      <list itemType="integer"/>  
   </simpleType>  
  
   <element name="root" type="ns:ListOfIntegers"/>  
  
   <element name="gRoot" type="gMonth"/>  
  
</schema>  
'  
GO  
-- schemaUser cannot see the contents of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
  
-- Grant schemaUser VIEW DEFINITION and REFERENCES permissions  
-- on the XML schema collection.  
SETUSER  
GO  
GRANT VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
GRANT REFERENCES ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
-- Now schemaUser can see the content of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
-- Revoke schemaUser VIEW DEFINITION permissions  
-- on the XML schema collection.  
SETUSER  
GO  
REVOKE VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC FROM schemaUser  
GO  
-- Now schemaUser cannot see the contents of   
-- the collection.  
setuser 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6d95-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6d95-167">See Also</span></span>  
 <span data-ttu-id="e6d95-168">[Dati XML &#40;SQL Server&#41;](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e6d95-168">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="e6d95-169">[Confronto dati XML tipizzati con dati XML non tipizzati](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e6d95-169">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="e6d95-170">[Raccolte di XML Schema &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e6d95-170">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="e6d95-171">Requisiti e limitazioni per le raccolte di XML Schema nel server</span><span class="sxs-lookup"><span data-stu-id="e6d95-171">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
