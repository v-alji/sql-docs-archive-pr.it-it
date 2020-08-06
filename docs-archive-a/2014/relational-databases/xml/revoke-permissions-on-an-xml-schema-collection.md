---
title: Revocare le autorizzazioni per una raccolta di XML Schema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- revoking permissions [SQL Server]
ms.assetid: 4e542b70-2d56-4a65-8a39-96a1ed477ca6
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ab37c915f14207376e0c4a9582611bf8e65e0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713908"
---
# <a name="revoke-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="0b164-102">Revoca delle autorizzazioni per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="0b164-102">Revoke Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="0b164-103">Per revocare l'autorizzazione per creare una raccolta XML Schema, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b164-103">The permission to create an XML schema collection can be revoked by using one of the following:</span></span>  
  
-   <span data-ttu-id="0b164-104">Revocare l'autorizzazione ALTER per lo schema relazionale.</span><span class="sxs-lookup"><span data-stu-id="0b164-104">Revoke the ALTER permission for the relational schema.</span></span> <span data-ttu-id="0b164-105">L'entità non sarà quindi in grado di creare una raccolta XML Schema nello schema relazionale,</span><span class="sxs-lookup"><span data-stu-id="0b164-105">Then, the principal cannot create an XML schema collection in the relational schema.</span></span> <span data-ttu-id="0b164-106">ma potrà comunque eseguire questa operazione negli altri schemi relazionali dello stesso database.</span><span class="sxs-lookup"><span data-stu-id="0b164-106">However, the principal can still do so in other relational schemas in the same database.</span></span>  
  
-   <span data-ttu-id="0b164-107">Revocare l'autorizzazione ALTER ANY SCHEMA dell'entità per il database.</span><span class="sxs-lookup"><span data-stu-id="0b164-107">Revoke the ALTER ANY SCHEMA permission on the database for the principal.</span></span> <span data-ttu-id="0b164-108">L'entità non sarà quindi in grado di creare una raccolta XML Schema all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="0b164-108">Then, the principal cannot create an XML schema collection anywhere in the database.</span></span>  
  
-   <span data-ttu-id="0b164-109">Revocare l'autorizzazione CREATE XML SCHEMA COLLECTION o ALTER XML SCHEMA COLLECTION dell'entità per il database.</span><span class="sxs-lookup"><span data-stu-id="0b164-109">Revoke the CREATE XML SCHEMA COLLECTION or ALTER XML SCHEMA COLLECTION permission on the database for the principal.</span></span> <span data-ttu-id="0b164-110">Ciò impedisce all'entità di importare una raccolta XML Schema nel database.</span><span class="sxs-lookup"><span data-stu-id="0b164-110">This prevents the principal from importing an XML schema collection within the database.</span></span> <span data-ttu-id="0b164-111">La revoca dell'autorizzazione ALTER o CONTROL per il database produce gli stessi effetti.</span><span class="sxs-lookup"><span data-stu-id="0b164-111">Revoking the ALTER or CONTROL permission on the database has the same effect.</span></span>  
  
## <a name="revoking-permissions-on-an-existing-xml-schema-collection-object"></a><span data-ttu-id="0b164-112">Revoca delle autorizzazioni per un oggetto raccolta XML Schema esistente</span><span class="sxs-lookup"><span data-stu-id="0b164-112">Revoking Permissions on an Existing XML Schema Collection Object</span></span>  
 <span data-ttu-id="0b164-113">Di seguito sono riportate le autorizzazioni che è possibile revocare per una raccolta XML Schema e i relativi risultati:</span><span class="sxs-lookup"><span data-stu-id="0b164-113">Following are the permissions that can be revoked on an XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="0b164-114">La revoca dell'autorizzazione ALTER impedisce all'entità di modificare il contenuto della raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="0b164-114">Revoking the ALTER permission revokes a principal's ability to modify the content of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="0b164-115">La revoca dell'autorizzazione TAKE OWNERSHIP impedisce all'entità di trasferire la proprietà della raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="0b164-115">Revoking the TAKE OWNERSHIP permission revokes a principal's ability to transfer ownership of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="0b164-116">La revoca dell'autorizzazione REFERENCES impedisce all'entità di utilizzare la raccolta XML Schema per tipizzare o vincolare le colonne di tipo xml di tabelle e viste nonché i parametri.</span><span class="sxs-lookup"><span data-stu-id="0b164-116">Revoking the REFERENCES permission revokes a principal's ability to use the XML schema collection for typing or constraining xml type columns, in tables and views, and parameters.</span></span> <span data-ttu-id="0b164-117">Comporta inoltre la revoca dell'autorizzazione che consente di fare riferimento alla raccolta di schemi da altre raccolte XML Schema.</span><span class="sxs-lookup"><span data-stu-id="0b164-117">It also revokes the permission to refer to this schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="0b164-118">La revoca dell'autorizzazione VIEW DEFINITION impedisce all'entità di visualizzare il contenuto della raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="0b164-118">Revoking the VIEW DEFINITION permission revokes a principal's ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="0b164-119">La revoca dell'autorizzazione EXECUTE impedisce all'entità di inserire o aggiornare valori nelle colonne, variabili e parametri tipizzati o vincolati dalla raccolta XML.</span><span class="sxs-lookup"><span data-stu-id="0b164-119">Revoking the EXECUTE permission revokes a principal's ability to insert or update values in columns, variables, and parameters that are typed or constrained by the XML collection.</span></span> <span data-ttu-id="0b164-120">Comporta inoltre la revoca della possibilità di eseguire query su tali colonne, variabili o parametri di tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="0b164-120">It also revokes the ability to query such **xml** type columns, variables, or parameters.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0b164-121">Esempi</span><span class="sxs-lookup"><span data-stu-id="0b164-121">Examples</span></span>  
 <span data-ttu-id="0b164-122">Gli scenari degli esempi seguenti illustrano il funzionamento delle autorizzazioni per XML Schema.</span><span class="sxs-lookup"><span data-stu-id="0b164-122">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="0b164-123">In ogni esempio vengono creati il database di prova, gli schemi relazionali e gli account di accesso necessari.</span><span class="sxs-lookup"><span data-stu-id="0b164-123">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="0b164-124">A tali account di accesso vengono concesse le autorizzazioni necessarie per la raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="0b164-124">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="0b164-125">Alla fine di ogni esempio viene eseguito il processo di pulizia necessario.</span><span class="sxs-lookup"><span data-stu-id="0b164-125">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-revoking-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="0b164-126">R.</span><span class="sxs-lookup"><span data-stu-id="0b164-126">A.</span></span> <span data-ttu-id="0b164-127">Revoca delle autorizzazioni per creare una raccolta XML Schema</span><span class="sxs-lookup"><span data-stu-id="0b164-127">Revoking permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="0b164-128">In questo esempio vengono creati un account di accesso e un database di esempio</span><span class="sxs-lookup"><span data-stu-id="0b164-128">This example creates a login and a sample database.</span></span> <span data-ttu-id="0b164-129">e nel database viene inoltre aggiunto uno schema relazionale.</span><span class="sxs-lookup"><span data-stu-id="0b164-129">It also adds a relational schema in the database.</span></span> <span data-ttu-id="0b164-130">Innanzitutto, all'account di accesso vengono concesse l'autorizzazione ALTER per entrambi gli schemi relazionali e le altre autorizzazioni necessarie per creare raccolte XML Schema.</span><span class="sxs-lookup"><span data-stu-id="0b164-130">Initially, the login is granted ALTER permission on both relational schemas and other necessary permissions to create XML schema collections.</span></span> <span data-ttu-id="0b164-131">Viene quindi revocata l'autorizzazione ALTER per uno degli schemi relazionali del database,</span><span class="sxs-lookup"><span data-stu-id="0b164-131">The example then revokes the ALTER permission on one of the relational schemas in the database.</span></span> <span data-ttu-id="0b164-132">in modo tale da impedire all'account di accesso di creare una raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="0b164-132">This prevents the login from creating an XML schema collection.</span></span>  
  
```  
setuser  
go  
create login TestLogin1 with password='SQLSvrPwd1'  
go  
create database SampleDBForSchemaPermissions  
go  
use SampleDBForSchemaPermissions  
go  
-- Create another relational schema in the db (in addition to dbo schema)  
CREATE SCHEMA myOtherDBSchema  
go  
CREATE USER TestLogin1  
go  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed  
-- CREATE XML SCHEMA is a database level permission  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
go  
GRANT ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
go  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
go  
-- Now TestLogin1 can import an XML schema collection in both relational schemas.  
setuser 'TestLogin1'  
go  
CREATE XML SCHEMA COLLECTION dbo.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
-- TestLogin1 can create XML schema collection in myOtherDBSchema relational schema  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
-- Let us drop XML schema collections from both relational schemas  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
go  
DROP XML SCHEMA COLLECTION dbo.myTestSchemaCollection  
go  
-- now REVOKE permission from TestLogin1 to alter myOtherDBSchema  
setuser  
go  
REVOKE ALTER ON SCHEMA::myOtherDBSchema FROM TestLogin1  
go  
-- now TestLogin1 cannot create xml schema collection in myOtherDBSchema  
setuser 'TestLogin1'  
go  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
  
-- TestLogin1 can still create XML schema collections in dbo  
-- It cannot create XML schema collections anywhere in the database  
-- if we REVOKE CREATE XML SCHEMA COLLECTION permission  
SETUSER  
go  
REVOKE CREATE XML SCHEMA COLLECTION FROM TestLogin1  
go  
  
setuser 'TestLogin1'  
go  
-- the following now should fail  
CREATE XML SCHEMA COLLECTION dbo.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
  
-- Final cleanup  
SETUSER  
go  
USE master  
go  
DROP DATABASE SampleDBForSchemaPermissions  
go  
DROP LOGIN TestLogin1  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b164-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b164-133">See Also</span></span>  
 <span data-ttu-id="0b164-134">[Dati XML &#40;SQL Server&#41;](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0b164-134">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="0b164-135">[Confronto dati XML tipizzati con dati XML non tipizzati](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="0b164-135">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="0b164-136">[Raccolte di XML Schema &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0b164-136">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="0b164-137">Requisiti e limitazioni per le raccolte di XML Schema nel server</span><span class="sxs-lookup"><span data-stu-id="0b164-137">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
