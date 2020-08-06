---
title: Negare le autorizzazioni per una raccolta di XML Schema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- denying permissions [SQL Server], XML server collections
ms.assetid: e2b300b0-e734-4c43-a4da-c78e6e5d4fba
author: rothja
ms.author: jroth
ms.openlocfilehash: 0791a9bd9c7f6b323886a38bed27bea84940770d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623937"
---
# <a name="deny-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="d9a8d-102">Negazione delle autorizzazioni per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="d9a8d-102">Deny Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="d9a8d-103">È possibile negare l'autorizzazione per la creazione di una nuova raccolta di XML Schema o per l'utilizzo di una raccolta esistente.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-103">Permission can be denied to either create a new XML schema collection or use an existing one.</span></span>  
  
## <a name="denying-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="d9a8d-104">Negazione dell'autorizzazione per la creazione di una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="d9a8d-104">Denying Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="d9a8d-105">È possibile negare l'autorizzazione per la creazione di una raccolta di XML Schema nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9a8d-105">You can deny permission to create an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="d9a8d-106">Negando l'autorizzazione ALTER per lo schema relazionale.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-106">Deny ALTER permission on the relational schema.</span></span>  
  
-   <span data-ttu-id="d9a8d-107">Negando l'autorizzazione CONTROL per lo schema relazionale in modo da negare tutte le autorizzazioni per lo schema relazionale e per tutti gli oggetti contenuti.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-107">Deny CONTROL on the relational schema to deny all permissions on the relational schema and on all the contained objects.</span></span>  
  
-   <span data-ttu-id="d9a8d-108">Negando l'autorizzazione ALTER ANY SCHEMA per il database.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-108">Deny ALTER ANY SCHEMA on the database.</span></span> <span data-ttu-id="d9a8d-109">In tal caso, l'entità non può creare una raccolta di XML Schema in una posizione all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-109">In this case, the principal cannot create an XML schema collection anywhere in the database.</span></span> <span data-ttu-id="d9a8d-110">Si noti inoltre che tramite la negazione dell'autorizzazione ALTER o CONTROL vengono negate tutte le autorizzazioni per tutti gli oggetti del database.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-110">Note also that denying ALTER or CONTROL permission on the database denies all permissions on all objects in the database.</span></span>  
  
## <a name="denying-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="d9a8d-111">Negazione di autorizzazioni per un oggetto di una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="d9a8d-111">Denying Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="d9a8d-112">Per una raccolta di XML Schema esistente e i relativi risultati è possibile negare le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9a8d-112">Following are the permission that can be denied on an existing XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="d9a8d-113">Tramite la negazione dell'autorizzazione ALTER, all'entità viene negata la possibilità di modificare il contenuto di una raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-113">Denying the ALTER permission denies the principal the ability to modify the contents of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="d9a8d-114">Tramite la negazione dell'autorizzazione CONTROL, all'entità viene negata la possibilità di eseguire qualsiasi operazione sulla raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-114">Denying the CONTROL permission denies the principal the ability to perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="d9a8d-115">Tramite la negazione dell'autorizzazione REFERENCES, all'entità viene negata la possibilità di tipizzare o vincolare parametri e colonne di tipo XML mediante la raccolta di XML Schema,</span><span class="sxs-lookup"><span data-stu-id="d9a8d-115">Denying the REFERENCES permission denies the principal the ability to type or constrain xml type columns and parameters using the XML schema collection.</span></span> <span data-ttu-id="d9a8d-116">nonché la possibilità di fare riferimento a tale raccolta da altre raccolte di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-116">It also denies the principal the ability to refer to this XML schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="d9a8d-117">Tramite la negazione dell'autorizzazione VIEW DEFINITION, all'entità viene negata la possibilità di visualizzare il contenuto di una raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-117">Denying the VIEW DEFINITION permission denies the principal the ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="d9a8d-118">Tramite la negazione dell'autorizzazione EXECUTE, all'entità viene negata la possibilità di inserire o aggiornare i valori in colonne, variabili e parametri tipizzati o vincolati dalla raccolta di XML Schema,</span><span class="sxs-lookup"><span data-stu-id="d9a8d-118">Denying the EXECUTE permission denies the principal the ability to insert or update the values in columns, variables, and parameters that are typed or constrained by the XML schema collection.</span></span> <span data-ttu-id="d9a8d-119">nonché la possibilità di eseguire query sui valori nelle stesse variabili e colonne di tipo XML.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-119">It also denies the principal the ability to query the values in those same xml type columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d9a8d-120">Esempi</span><span class="sxs-lookup"><span data-stu-id="d9a8d-120">Examples</span></span>  
 <span data-ttu-id="d9a8d-121">Gli scenari degli esempi seguenti illustrano il funzionamento delle autorizzazioni per XML Schema.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-121">The scenarios in the following examples show how XML schema permissions work.</span></span> <span data-ttu-id="d9a8d-122">In ogni esempio vengono creati il database di prova, gli schemi relazionali e gli account di accesso necessari.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-122">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="d9a8d-123">A tali account di accesso vengono concesse le autorizzazioni necessarie per la raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-123">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="d9a8d-124">Alla fine di ogni esempio viene eseguito il processo di pulizia necessario.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-124">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-preventing-a-user-from-creating-an-xml-schema-collection"></a><span data-ttu-id="d9a8d-125">R.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-125">A.</span></span> <span data-ttu-id="d9a8d-126">Procedura per impedire a un utente di creare una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="d9a8d-126">Preventing a user from creating an XML schema collection</span></span>  
 <span data-ttu-id="d9a8d-127">Uno dei modi per impedire a un utente di creare una raccolta di XML Schema consiste nel negare l'autorizzazione ALTER per uno schema relazionale,</span><span class="sxs-lookup"><span data-stu-id="d9a8d-127">One of the ways to prevent a user from creating an XML schema collection is by denying the ALTER permission on a relational schema.</span></span> <span data-ttu-id="d9a8d-128">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-128">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="d9a8d-129">Nell'esempio vengono creati l'account utente `TestLogin1`e un database,</span><span class="sxs-lookup"><span data-stu-id="d9a8d-129">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="d9a8d-130">nonché uno schema relazionale, in aggiunta allo schema `dbo` , nel database.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-130">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="d9a8d-131">Inizialmente, l'autorizzazione `CREATE XML SCHEMA` consente all'utente di creare una raccolta di schemi in una posizione qualsiasi all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-131">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span> <span data-ttu-id="d9a8d-132">Nell'esempio viene negata all'utente l'autorizzazione `ALTER` per uno degli schemi relazionali.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-132">The example then denies `ALTER` permission to the user on one of the relational schemas.</span></span> <span data-ttu-id="d9a8d-133">In questo modo, viene impedito all'utente di creare una raccolta di XML Schema in tale schema relazionale.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-133">This prevents the user from creating an XML schema collection in that relational schema.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
GO  
-- Now deny permission from TestLogin1 to alter myOtherDBSchema.  
setuser  
GO  
DENY ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
GO  
-- Now TestLogin1 cannot create xml schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
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
  
### <a name="b-denying-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="d9a8d-134">B.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-134">B.</span></span> <span data-ttu-id="d9a8d-135">Procedura per negare autorizzazioni per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="d9a8d-135">Denying permissions on an XML schema collection</span></span>  
 <span data-ttu-id="d9a8d-136">Nell'esempio seguente viene illustrato come negare a un account di accesso un'autorizzazione specifica per una raccolta di XML Schema esistente.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-136">The following example shows how a specific permission on an existing XML schema collection can be denied to a login.</span></span> <span data-ttu-id="d9a8d-137">In questo esempio, a un account di accesso di prova viene negata l'autorizzazione REFERENCES per una raccolta di XML Schema esistente.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-137">In this example, a test login is denied REFERENCES permission on an existing XML schema collection.</span></span>  
  
 <span data-ttu-id="d9a8d-138">Nell'esempio vengono creati l'account utente `TestLogin1`e un database,</span><span class="sxs-lookup"><span data-stu-id="d9a8d-138">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="d9a8d-139">nonché uno schema relazionale, in aggiunta allo schema `dbo` , nel database.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-139">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="d9a8d-140">Inizialmente, l'autorizzazione `CREATE XML SCHEMA` consente all'utente di creare una raccolta di schemi in una posizione qualsiasi all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-140">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span>  
  
 <span data-ttu-id="d9a8d-141">L'autorizzazione `REFERENCES` per la raccolta di XML Schema consente a `TestLogin1` di utilizzare lo schema nella creazione di una colonna `xml` tipizzata in una tabella.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-141">The `REFERENCES` permission on the XML schema collection lets `TestLogin1` use the schema in creating a typed `xml` column in a table.</span></span> <span data-ttu-id="d9a8d-142">Se viene negata l'autorizzazione `REFERENCES` per la raccolta di XML Schema, `TestLogin1` non potrà utilizzare tale raccolta.</span><span class="sxs-lookup"><span data-stu-id="d9a8d-142">If the `REFERENCES` permission on the XML schema collection is denied, it prevents the `TestLogin1` from using the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, the following  
-- permission is required.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant permission to TestLogin1 to create a table and reference the XML schema collection.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also needs REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on the schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection   
TO TestLogin1  
GO  
  
--TestLogin1 can use the schema.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
GO  
-- Drop the table.  
DROP TABLE T  
GO  
-- Now deny REFERENCES permission to TestLogin1 on the schema created previously.  
SETUSER  
GO  
DENY REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection TO TestLogin1  
  
GO  
-- Now TestLogin1 cannot create xml schema collection  
SETUSER 'TestLogin1'  
GO  
-- Following statement fails. TestLogin1 does not have REFERENCES   
-- permission on the XML schema collection.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
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
  
## <a name="see-also"></a><span data-ttu-id="d9a8d-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9a8d-143">See Also</span></span>  
 <span data-ttu-id="d9a8d-144">[Confronto dati XML tipizzati con dati XML non tipizzati](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="d9a8d-144">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="d9a8d-145">[Raccolte di XML Schema &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d9a8d-145">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 <span data-ttu-id="d9a8d-146">[Requisiti e limitazioni per l'utilizzo di raccolte di XML Schema nel server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span><span class="sxs-lookup"><span data-stu-id="d9a8d-146">[Requirements and Limitations for XML Schema Collections on the Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span></span>  
 <span data-ttu-id="d9a8d-147">[DENY - autorizzazioni per oggetti &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d9a8d-147">[DENY Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="d9a8d-148">[GRANT - autorizzazioni per oggetti &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d9a8d-148">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="d9a8d-149">Dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d9a8d-149">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
