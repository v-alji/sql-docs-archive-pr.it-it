---
title: Raccolte di XML Schema (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- xml_schema_namespace function
- XML schema collections [SQL Server], about XML schema collections
- metadata [SQL Server], XML schema collections
- queries [XML in SQL Server], XML schema collections
- schema collections [SQL Server]
- schemas [SQL Server], XML
- XML [SQL Server], schema collections
- XML schema collections [SQL Server]
- schema collections [SQL Server], about XML schema collections
ms.assetid: 659d41aa-ccec-4554-804a-722a96ef25c2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ee4757f1353278447ee55e97c8d4ba23aa2d649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630380"
---
# <a name="xml-schema-collections-sql-server"></a><span data-ttu-id="7c96c-102">Raccolte di XML Schema (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7c96c-102">XML Schema Collections (SQL Server)</span></span>
  <span data-ttu-id="7c96c-103">Come descritto nell'argomento [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server fornisce l'archiviazione nativa dei dati XML tramite il `xml` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7c96c-103">As described in the topic, [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server provides native storage of XML data through the `xml` data type.</span></span> <span data-ttu-id="7c96c-104">Facoltativamente, è possibile associare schemi XSD a una variabile o a una colonna di `xml` tipo tramite una raccolta di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-104">You can optionally associate XSD schemas with a variable or a column of `xml` type through an XML schema collection.</span></span> <span data-ttu-id="7c96c-105">Una raccolta di XML Schema archivia gli elementi XML Schema importati e può essere quindi utilizzata per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c96c-105">The XML schema collection stores the imported XML schemas and is then used to do the following:</span></span>  
  
-   <span data-ttu-id="7c96c-106">Convalidare istanze XML.</span><span class="sxs-lookup"><span data-stu-id="7c96c-106">Validate XML instances</span></span>  
  
-   <span data-ttu-id="7c96c-107">Tipizzare i dati XML a mano a mano che vengono archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="7c96c-107">Type the XML data as it is stored in the database</span></span>  
  
 <span data-ttu-id="7c96c-108">Si noti che una raccolta di XML Schema è un'entità di metadati analoga a una tabella in un database.</span><span class="sxs-lookup"><span data-stu-id="7c96c-108">Note that the XML schema collection is a metadata entity like a table in the database.</span></span> <span data-ttu-id="7c96c-109">Le raccolte di schemi XML possono essere create, modificate ed eliminate.</span><span class="sxs-lookup"><span data-stu-id="7c96c-109">You can create, modify, and drop them.</span></span> <span data-ttu-id="7c96c-110">Gli schemi specificati in un'istruzione [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) vengono automaticamente importati nell'oggetto raccolta di XML Schema appena creato.</span><span class="sxs-lookup"><span data-stu-id="7c96c-110">Schemas specified in a [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) statement are automatically imported into the newly created XML schema collection object.</span></span> <span data-ttu-id="7c96c-111">È possibile importare altri schemi o componenti di schema in un oggetto raccolta esistente nel database, usando l'istruzione [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="7c96c-111">You can import additional schemas or schema components into an existing collection object in the database by using the [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="7c96c-112">Come descritto nell'argomento [Confronto dati XML tipizzati con dati XML non tipizzati](../xml/compare-typed-xml-to-untyped-xml.md), i dati XML archiviati in una colonna o in una variabile a cui è associato uno schema sono detti dati XML **tipizzati** perché lo schema fornisce le informazioni sul tipo di dati necessarie per i dati dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="7c96c-112">As described in the topic, [Typed vs. Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md), the XML stored in a column or variable that a schema is associated with is referred to as **typed** XML, because the schema provides the necessary data type information for the instance data.</span></span> <span data-ttu-id="7c96c-113">SQL Server utilizza tali informazioni sul tipo per ottimizzare l'archiviazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="7c96c-113">SQL Server uses this type information to optimize data storage.</span></span>  
  
 <span data-ttu-id="7c96c-114">Lo schema viene inoltre utilizzato dal motore di elaborazione delle query per la verifica dei tipi, per l'ottimizzazione delle query e per la modifica dei dati.</span><span class="sxs-lookup"><span data-stu-id="7c96c-114">The query-processing engine also uses the schema for type checking and to optimize queries and data modification.</span></span>  
  
 <span data-ttu-id="7c96c-115">Inoltre, SQL Server usa la raccolta di XML Schema associata, nel caso di tipizzato `xml` , per convalidare l'istanza XML.</span><span class="sxs-lookup"><span data-stu-id="7c96c-115">Also, SQL Server uses the associated XML schema collection, in the case of typed `xml`, to validate the XML instance.</span></span> <span data-ttu-id="7c96c-116">Se l'istanza XML è conforme allo schema, il database consente di archiviarla nel sistema insieme alle relative informazioni sul tipo,</span><span class="sxs-lookup"><span data-stu-id="7c96c-116">If the XML instance complies with the schema, the database allows the instance to be stored in the system with their type information.</span></span> <span data-ttu-id="7c96c-117">in caso contrario la rifiuta.</span><span class="sxs-lookup"><span data-stu-id="7c96c-117">Otherwise, it rejects the instance.</span></span>  
  
 <span data-ttu-id="7c96c-118">Per recuperare la raccolta di schemi archiviata nel database è possibile utilizzare la funzione intrinseca XML_SCHEMA_NAMESPACE.</span><span class="sxs-lookup"><span data-stu-id="7c96c-118">You can use the intrinsic function XML_SCHEMA_NAMESPACE to retrieve the schema collection that is stored in the database.</span></span> <span data-ttu-id="7c96c-119">Per altre informazioni, vedere [Visualizzare una raccolta di XML Schema archiviata](../xml/view-a-stored-xml-schema-collection.md).</span><span class="sxs-lookup"><span data-stu-id="7c96c-119">For more information, see [View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md).</span></span>  
  
 <span data-ttu-id="7c96c-120">La raccolta di XML Schema può essere utilizzata anche per tipizzare variabili, parametri e colonne XML.</span><span class="sxs-lookup"><span data-stu-id="7c96c-120">You can also use the XML schema collection to type XML variables, parameters, and columns.</span></span>  
  
##  <a name="ddl-for-managing-schema-collections"></a><a name="ddl"></a> <span data-ttu-id="7c96c-121">Istruzioni DDL per la gestione di raccolte di XML Schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-121">DDL for Managing Schema Collections</span></span>  
 <span data-ttu-id="7c96c-122">È possibile creare raccolte di XML Schema nel database e associarle a variabili e colonne di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="7c96c-122">You can create XML schema collections in the database and associate them with variables and columns of `xml` type.</span></span> <span data-ttu-id="7c96c-123">Per gestire le raccolte di schemi nel database, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono disponibili le istruzioni DDL seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c96c-123">To manage schema collections in the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following DDL statements:</span></span>  
  
-   <span data-ttu-id="7c96c-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Importa i componenti di schema in un database.</span><span class="sxs-lookup"><span data-stu-id="7c96c-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Imports schema components into a database.</span></span>  
  
-   <span data-ttu-id="7c96c-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifica i componenti di schema in una raccolta XML Schema esistente.</span><span class="sxs-lookup"><span data-stu-id="7c96c-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifies the schema components in an existing XML schema collection.</span></span>  
  
-   <span data-ttu-id="7c96c-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Elimina l'intera raccolta XML Schema e tutti i relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="7c96c-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Deletes a complete XML schema collection and all its components.</span></span>  
  
 <span data-ttu-id="7c96c-127">Per utilizzare una raccolta XML Schema e i relativi schemi, è necessario innanzitutto creare la raccolta e gli schemi utilizzando l'istruzione CREATE XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="7c96c-127">To use an XML schema collection and the schemas it contains, you must first create the collection and the schemas by using the CREATE XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="7c96c-128">Dopo aver creato la raccolta di schemi, è quindi possibile creare le variabili e le colonne di tipo `xml` e associare a esse la raccolta di schemi.</span><span class="sxs-lookup"><span data-stu-id="7c96c-128">After the schema collection is created, you can then create variables and columns of `xml` type and associate the schema collection with them.</span></span> <span data-ttu-id="7c96c-129">Si noti che dopo aver creato la raccolta, nei metadati verranno archiviati diversi componenti degli schemi.</span><span class="sxs-lookup"><span data-stu-id="7c96c-129">Note that after a schema collection is created, various schema components are stored in the metadata.</span></span> <span data-ttu-id="7c96c-130">È inoltre possibile utilizzare l'istruzione ALTER XML SCHEMA COLLECTION per aggiungere altri componenti agli schemi o nuovi schemi alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="7c96c-130">You can also use the ALTER XML SCHEMA COLLECTION to add more components to the existing schemas or add new schemas to an existing collection.</span></span>  
  
 <span data-ttu-id="7c96c-131">Per eliminare la raccolta di schemi, utilizzare l'istruzione DROP XML SCHEMA COLLECTION,</span><span class="sxs-lookup"><span data-stu-id="7c96c-131">To drop the schema collection, use the DROP XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="7c96c-132">che consente di eliminare tutti gli schemi contenuti nella raccolta e di rimuovere l'oggetto raccolta.</span><span class="sxs-lookup"><span data-stu-id="7c96c-132">This drops all schemas that are contained in the collection and removes the collection object.</span></span> <span data-ttu-id="7c96c-133">Si noti che prima di eliminare una raccolta di schemi è necessario soddisfare le condizioni descritte in [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7c96c-133">Note that before you can drop a schema collection, the conditions described in [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql)must be met.</span></span>  
  
##  <a name="understanding-schema-components"></a><a name="components"></a> <span data-ttu-id="7c96c-134">Informazioni sui componenti dello schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-134">Understanding Schema Components</span></span>  
 <span data-ttu-id="7c96c-135">Quando si utilizza l'istruzione CREATE XML SCHEMA COLLECTION, vengono importati nel database diversi componenti dello schema,</span><span class="sxs-lookup"><span data-stu-id="7c96c-135">When you use the CREATE XML SCHEMA COLLECTION statement, various schema components are imported into the database.</span></span> <span data-ttu-id="7c96c-136">ad esempio elementi, attributi e definizioni di tipi dello schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-136">Schema components include schema elements, attributes, and type definitions.</span></span> <span data-ttu-id="7c96c-137">Se si utilizza l'istruzione DROP XML SCHEMA COLLECTION, verrà rimossa l'intera raccolta.</span><span class="sxs-lookup"><span data-stu-id="7c96c-137">When you use the DROP XML SCHEMA COLLECTION statement, you remove the complete collection.</span></span>  
  
 <span data-ttu-id="7c96c-138">L'istruzione CREATE XML SCHEMA COLLECTION salva i componenti dello schema in diverse tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-138">CREATE XML SCHEMA COLLECTION saves the schema components into various system tables.</span></span>  
  
 <span data-ttu-id="7c96c-139">Si consideri ad esempio lo schema seguente:</span><span class="sxs-lookup"><span data-stu-id="7c96c-139">For example, consider the following schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            targetNamespace="uri:Cust_Orders2"  
            xmlns="uri:Cust_Orders2" >  
  <xsd:attribute name="SomeAttribute" type="xsd:int" />  
  <xsd:complexType name="SomeType" />  
  <xsd:complexType name="OrderType" >  
    <xsd:sequence>  
      <xsd:element name="OrderDate" type="xsd:date" />  
      <xsd:element name="RequiredDate" type="xsd:date" />  
      <xsd:element name="ShippedDate" type="xsd:date" />  
    </xsd:sequence>  
    <xsd:attribute name="OrderID" type="xsd:ID" />  
    <xsd:attribute name="CustomerID"  />  
    <xsd:attribute name="EmployeeID"  />  
  </xsd:complexType>  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order" type="OrderType"  
                     maxOccurs="unbounded" />  
       </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
      <xsd:attribute name="OrderIDList" type="xsd:IDREFS" />  
  </xsd:complexType>  
  <xsd:element name="Customer" type="CustomerType" />  
</xsd:schema>  
```  
  
 <span data-ttu-id="7c96c-140">Questo schema mostra i diversi tipi di componenti che possono essere archiviati nel database,</span><span class="sxs-lookup"><span data-stu-id="7c96c-140">The previous schema shows the different types of components that can be stored in the database.</span></span> <span data-ttu-id="7c96c-141">tra cui `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`e `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="7c96c-141">These include `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`, and `ShippedDate`.</span></span>  
  
### <a name="component-categories"></a><span data-ttu-id="7c96c-142">Categorie di componenti</span><span class="sxs-lookup"><span data-stu-id="7c96c-142">Component Categories</span></span>  
 <span data-ttu-id="7c96c-143">I componenti dello schema archiviati nel database rientrano nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c96c-143">The Schema components stored in the database fall into the following categories:</span></span>  
  
-   <span data-ttu-id="7c96c-144">ELEMENT</span><span class="sxs-lookup"><span data-stu-id="7c96c-144">ELEMENT</span></span>  
  
-   <span data-ttu-id="7c96c-145">ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="7c96c-145">ATTRIBUTE</span></span>  
  
-   <span data-ttu-id="7c96c-146">TYPE (per tipi semplici o complessi)</span><span class="sxs-lookup"><span data-stu-id="7c96c-146">TYPE (for simple or complex types)</span></span>  
  
-   <span data-ttu-id="7c96c-147">ATTRIBUTEGROUP</span><span class="sxs-lookup"><span data-stu-id="7c96c-147">ATTRIBUTEGROUP</span></span>  
  
-   <span data-ttu-id="7c96c-148">MODELGROUP</span><span class="sxs-lookup"><span data-stu-id="7c96c-148">MODELGROUP</span></span>  
  
 <span data-ttu-id="7c96c-149">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7c96c-149">For example:</span></span>  
  
-   <span data-ttu-id="7c96c-150">**SomeAttribute** è un componente di tipo ATTRIBUTE.</span><span class="sxs-lookup"><span data-stu-id="7c96c-150">**SomeAttribute** is an ATTRIBUTE component.</span></span>  
  
-   <span data-ttu-id="7c96c-151">**SomeType**, **OrderType**e **CustomerType** sono componenti di tipo TYPE.</span><span class="sxs-lookup"><span data-stu-id="7c96c-151">**SomeType**, **OrderType**, and **CustomerType** are TYPE components.</span></span>  
  
-   <span data-ttu-id="7c96c-152">**Customer** è un componente ELEMENT.</span><span class="sxs-lookup"><span data-stu-id="7c96c-152">**Customer** is an ELEMENT component.</span></span>  
  
 <span data-ttu-id="7c96c-153">Quando si importa uno schema nel database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non archivia direttamente lo schema,</span><span class="sxs-lookup"><span data-stu-id="7c96c-153">When you import a schema into the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not store the schema itself.</span></span> <span data-ttu-id="7c96c-154">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] archivia invece i singoli componenti.</span><span class="sxs-lookup"><span data-stu-id="7c96c-154">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stores the various individual components.</span></span> <span data-ttu-id="7c96c-155">Ciò significa che il tag \<Schema> non viene archiviato, ma vengono mantenuti i componenti definiti al suo interno.</span><span class="sxs-lookup"><span data-stu-id="7c96c-155">That is, the \<Schema> tag is not stored, only the components that are defined within it are preserved.</span></span> <span data-ttu-id="7c96c-156">Non vengono mantenuti tutti gli elementi dello schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-156">All schema elements are not preserved.</span></span> <span data-ttu-id="7c96c-157">Se il tag \<Schema> contiene attributi che specificano il comportamento predefinito dei relativi componenti, tali attributi vengono spostati nei componenti dello schema durante il processo di importazione, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7c96c-157">If the \<Schema> tag contains attributes that specify default behavior of its components, these attributes are moved to the schema components within it during the import process, as shown in the following table.</span></span>  
  
|<span data-ttu-id="7c96c-158">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="7c96c-158">Attribute name</span></span>|<span data-ttu-id="7c96c-159">Comportamento</span><span class="sxs-lookup"><span data-stu-id="7c96c-159">Behavior</span></span>|  
|--------------------|--------------|  
|<span data-ttu-id="7c96c-160">**attributeFormDefault**</span><span class="sxs-lookup"><span data-stu-id="7c96c-160">**attributeFormDefault**</span></span>|<span data-ttu-id="7c96c-161">Attributo **form** applicato a tutte le dichiarazioni di attributo nello schema nelle quali non è già presente e dove il valore viene impostato sul valore dell'attributo **attributeFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="7c96c-161">The **form** attribute applied to all attribute declarations in the schema where it is not already present and the value is set to the value of the **attributeFormDefault** attribute.</span></span>|  
|<span data-ttu-id="7c96c-162">**elementFormDefault**</span><span class="sxs-lookup"><span data-stu-id="7c96c-162">**elementFormDefault**</span></span>|<span data-ttu-id="7c96c-163">Attributo **form** applicato a tutte le dichiarazioni di elemento nello schema nelle quali non è già presente e dove il valore viene impostato sul valore dell'attributo **elementFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="7c96c-163">The **form** attribute applied to all element declarations in the schema where it is not already present and the value is set to the value of the **elementFormDefault** attribute.</span></span>|  
|<span data-ttu-id="7c96c-164">**blockDefault**</span><span class="sxs-lookup"><span data-stu-id="7c96c-164">**blockDefault**</span></span>|<span data-ttu-id="7c96c-165">Attributo **block** applicato a tutte le dichiarazioni di elemento e definizioni di tipo nelle quali non è già presente e dove il valore viene impostato sul valore dell'attributo **blockDefault** .</span><span class="sxs-lookup"><span data-stu-id="7c96c-165">The **block** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **blockDefault** attribute.</span></span>|  
|<span data-ttu-id="7c96c-166">**finalDefault**</span><span class="sxs-lookup"><span data-stu-id="7c96c-166">**finalDefault**</span></span>|<span data-ttu-id="7c96c-167">Attributo **final** applicato a tutte le dichiarazioni di elemento e definizioni di tipo nelle quali non è già presente e dove il valore viene impostato sul valore dell'attributo **finalDefault** .</span><span class="sxs-lookup"><span data-stu-id="7c96c-167">The **final** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **finalDefault** attribute.</span></span>|  
|<span data-ttu-id="7c96c-168">**targetNamespace**</span><span class="sxs-lookup"><span data-stu-id="7c96c-168">**targetNamespace**</span></span>|<span data-ttu-id="7c96c-169">Le informazioni sui componenti appartenenti allo spazio dei nomi di destinazione vengono archiviate nei metadati.</span><span class="sxs-lookup"><span data-stu-id="7c96c-169">Information about the components that belong to the target namespace is stored in the metadata.</span></span>|  
  
##  <a name="permissions-on-an-xml-schema-collection"></a><a name="perms"></a> <span data-ttu-id="7c96c-170">Autorizzazioni per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-170">Permissions on an XML Schema Collection</span></span>  
 <span data-ttu-id="7c96c-171">È necessario disporre delle autorizzazioni necessarie per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c96c-171">You must have the necessary permissions to do the following:</span></span>  
  
-   <span data-ttu-id="7c96c-172">Creare o caricare la raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-172">Create/load the XML schema collection</span></span>  
  
-   <span data-ttu-id="7c96c-173">Modificare la raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-173">Modify the XML schema collection</span></span>  
  
-   <span data-ttu-id="7c96c-174">Eliminare la raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-174">Drop the XML schema collection</span></span>  
  
-   <span data-ttu-id="7c96c-175">Utilizzare la raccolta XML Schema per digitare `xml` colonne, variabili e parametri di tipo oppure utilizzarlo nei vincoli di tabella o di colonna</span><span class="sxs-lookup"><span data-stu-id="7c96c-175">Use the XML schema collection to type `xml` type columns, variables, and parameters, or use it in table or column constraints</span></span>  
  
 <span data-ttu-id="7c96c-176">Il modello di sicurezza di SQL Server consente l'autorizzazione CONTROL per tutti gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7c96c-176">The SQL Server security model allows CONTROL permission on every object.</span></span> <span data-ttu-id="7c96c-177">L'utente che dispone di questa autorizzazione ottiene tutte le altre autorizzazioni per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7c96c-177">The grantee of this permission obtains all other permissions on the object.</span></span> <span data-ttu-id="7c96c-178">Il proprietario dell'oggetto dispone anch'esso di tutte le autorizzazioni per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7c96c-178">The owner of the object also has all the permissions on the object.</span></span>  
  
 <span data-ttu-id="7c96c-179">Il proprietario e l'utente che dispongono dell'autorizzazione CONTROL per un oggetto possono concedere qualsiasi autorizzazione per l'oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="7c96c-179">The owner and the grantee of the CONTROL permission on an object can grant any permission on the object.</span></span> <span data-ttu-id="7c96c-180">Un utente che non è il proprietario e che non dispone dell'autorizzazione CONTROL può comunque concedere l'autorizzazione per un oggetto se è specificata WITH GRANT OPTION.</span><span class="sxs-lookup"><span data-stu-id="7c96c-180">A user who is not the owner and does not have CONTROL permission can still grant permission on an object when WITH GRANT OPTION is specified.</span></span> <span data-ttu-id="7c96c-181">Ad esempio, si supponga che Utente A disponga tramite WITH GRANT OPTION dell'autorizzazione REFERENCES per la raccolta XML Schema denominata S, ma di nessun'altra autorizzazione per la raccolta. Utente A può concedere a Utente B l'autorizzazione REFERENCES per la raccolta di schemi S.</span><span class="sxs-lookup"><span data-stu-id="7c96c-181">For example, assume User A has REFERENCES permission on XML schema collection S, through WITH GRANT OPTION, but no other permissions on S. User A could grant User B REFERENCES permission on schema collection S.</span></span>  
  
 <span data-ttu-id="7c96c-182">Il modello di sicurezza consente inoltre le autorizzazioni per la creazione e l'utilizzo di raccolte XML Schema o per il trasferimento della proprietà da un utente a un altro.</span><span class="sxs-lookup"><span data-stu-id="7c96c-182">The security model also allows permissions to create and use XML schema collections or transfer ownership from one user to another.</span></span> <span data-ttu-id="7c96c-183">Negli argomenti seguenti vengono illustrate le autorizzazioni per le raccolte XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-183">The following topics describe the XML schema collection permissions.</span></span>  
  
-   [<span data-ttu-id="7c96c-184">Concedere autorizzazioni per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-184">Grant Permissions on an XML Schema Collection</span></span>](../xml/grant-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="7c96c-185">Questo argomento presenta informazioni sulla concessione delle autorizzazioni per creare una raccolta XML Schema e delle autorizzazioni per un oggetto raccolta di schemi XML.</span><span class="sxs-lookup"><span data-stu-id="7c96c-185">This topic discussess how to grant permissions to create an XML schema collection and how to grant permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="7c96c-186">Revocare le autorizzazioni per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-186">Revoke Permissions on an XML Schema Collection</span></span>](../xml/revoke-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="7c96c-187">Questo argomento presenta informazioni sulla revoca delle autorizzazioni per impedire la creazione di una raccolta XML Schema e illustra la revoca delle autorizzazioni per un oggetto raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-187">This topic discusses how revoking permissions can be used to prevent the creation of an XML schema collection and how to revoke permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="7c96c-188">Negare le autorizzazioni per una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-188">Deny Permissions on an XML Schema Collection</span></span>](../xml/deny-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="7c96c-189">In questo argomento vengono fornite informazioni sulla negazione delle autorizzazioni per creare una raccolta XML Schema e delle autorizzazioni per un oggetto raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-189">This topic discusses how to deny permissions to create an XML schema collection and deny permission on an XML schema collection object.</span></span>  
  
##  <a name="getting-information-about-xml-schemas-and-schema-collections"></a><a name="info"></a> <span data-ttu-id="7c96c-190">Acquisizione di Informazioni su XML Schema e Raccolte di schemi</span><span class="sxs-lookup"><span data-stu-id="7c96c-190">Getting Information about XML Schemas and Schema Collections</span></span>  
 <span data-ttu-id="7c96c-191">Le raccolte di XML Schema sono enumerate nella vista del catalogo sys.xml_schema_collections.</span><span class="sxs-lookup"><span data-stu-id="7c96c-191">XML schema collections are enumerated in the catalog view, sys.xml_schema_collections.</span></span> <span data-ttu-id="7c96c-192">La raccolta di XML Schema "sys" è definita dal sistema</span><span class="sxs-lookup"><span data-stu-id="7c96c-192">The XML schema collection "sys" is defined by the system.</span></span> <span data-ttu-id="7c96c-193">e contiene gli spazi dei nomi predefiniti che è possibile utilizzare in tutte le raccolte di XML Schema definite dall'utente senza doverli caricare in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="7c96c-193">It contains the predefined namespaces that can be used in all user-defined XML schema collections without having to load them explicitly.</span></span> <span data-ttu-id="7c96c-194">Tale elenco contiene gli spazi dei nomi per xml, xs, xsi, fn e xdt.</span><span class="sxs-lookup"><span data-stu-id="7c96c-194">This list contains the namespaces for xml, xs, xsi, fn, and xdt.</span></span> <span data-ttu-id="7c96c-195">Sono disponibili altre due viste del catalogo: sys.xml_schema_namespaces, che enumera tutti gli spazi dei nomi in ogni raccolta di XML Schema, e sys.xml_components, che enumera tutti i componenti degli elementi XML Schema presenti in ognuno.</span><span class="sxs-lookup"><span data-stu-id="7c96c-195">Two other catalog views are sys.xml_schema_namespaces, which enumerates all namespaces within each XML schema collection, and sys.xml_components, which enumerates all XML schema components within each XML schema.</span></span>  
  
 <span data-ttu-id="7c96c-196">La funzione predefinita **XML_SCHEMA_NAMESPACE**, *SchemaName, XmlSchemaCollectionName, Namespace-URI*, produce un' `xml` istanza del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7c96c-196">The built-in function **XML_SCHEMA_NAMESPACE**, *schemaName, XmlSchemacollectionName, namespace-uri*, yields an `xml` data type instance..</span></span> <span data-ttu-id="7c96c-197">Tale istanza contiene frammenti di XML Schema per gli schemi inclusi in una raccolta di XML Schema, ad eccezione degli elementi XML Schema predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7c96c-197">This instance contains XML schema fragments for schemas that are contained in an XML schema collection, except the predefined XML schemas.</span></span>  
  
 <span data-ttu-id="7c96c-198">Per enumerare il contenuto di una raccolta di XML Schema è possibile:</span><span class="sxs-lookup"><span data-stu-id="7c96c-198">You can enumerate the contents of an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="7c96c-199">Scrivere query Transact-SQL sulle viste del catalogo appropriate per le raccolte di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-199">Write Transact-SQL queries on the appropriate catalog views for XML schema collections.</span></span>  
  
-   <span data-ttu-id="7c96c-200">Usare la funzione predefinita **XML_SCHEMA_NAMESPACE()** .</span><span class="sxs-lookup"><span data-stu-id="7c96c-200">Use the built-in function **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="7c96c-201">È possibile applicare `xml` metodi con tipo di dati nell'output di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="7c96c-201">You can apply `xml` data type methods on the output of this function.</span></span> <span data-ttu-id="7c96c-202">ma non è possibile modificare gli elementi XML Schema sottostanti.</span><span class="sxs-lookup"><span data-stu-id="7c96c-202">However, you cannot modify the underlying XML schemas.</span></span>  
  
 <span data-ttu-id="7c96c-203">Queste tecniche di enumerazione sono illustrate negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7c96c-203">These are illustrated in the following examples.</span></span>  
  
### <a name="example-enumerate-the-xml-namespaces-in-an-xml-schema-collection"></a><span data-ttu-id="7c96c-204">Esempio: Enumerazione degli spazi dei nomi XML in una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-204">Example: Enumerate the XML Namespaces in an XML Schema Collection</span></span>  
 <span data-ttu-id="7c96c-205">Per la raccolta di XML Schema "myCollection" utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="7c96c-205">Use the following query for the XML schema collection "myCollection":</span></span>  
  
```  
SELECT XSN.name  
FROM    sys.xml_schema_collections XSC JOIN sys.xml_schema_namespaces XSN  
    ON (XSC.xml_collection_id = XSN.xml_collection_id)  
WHERE    XSC.name = 'myCollection'     
```  
  
### <a name="example-enumerate-the-contents-of-an-xml-schema-collection"></a><span data-ttu-id="7c96c-206">Esempio: Enumerazione del contenuto di una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-206">Example: Enumerate the Contents of an XML Schema Collection</span></span>  
 <span data-ttu-id="7c96c-207">L'istruzione seguente enumera il contenuto della raccolta di XML Schema "myCollection" nell'ambito dello schema relazionale dbo.</span><span class="sxs-lookup"><span data-stu-id="7c96c-207">The following statement enumerates the contents of the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection')  
```  
  
 <span data-ttu-id="7c96c-208">È possibile ottenere singoli schemi XML all'interno della raccolta come `xml` istanze del tipo di dati specificando lo spazio dei nomi di destinazione come terzo argomento per **XML_SCHEMA_NAMESPACE ()**.</span><span class="sxs-lookup"><span data-stu-id="7c96c-208">Individual XML schemas within the collection can be obtained as `xml` data type instances by specifying the target namespace as the third argument to **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="7c96c-209">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7c96c-209">This is shown in the following example.</span></span>  
  
### <a name="example-output-a-specified-schema-from-an-xml-schema-collection"></a><span data-ttu-id="7c96c-210">Esempio: Restituzione di uno schema specifico da una raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-210">Example: Output a Specified Schema from an XML Schema Collection</span></span>  
 <span data-ttu-id="7c96c-211">L'istruzione seguente restituisce l'elemento XML Schema con spazio dei nomi di destinazione "<https://www.microsoft.com/books>" dalla raccolta di XML Schema "myCollection" nell'ambito dello schema relazionale dbo.</span><span class="sxs-lookup"><span data-stu-id="7c96c-211">The following statement outputs the XML schema with the target namespace "<https://www.microsoft.com/books>" from the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection',   
N'https://www.microsoft.com/books')  
```  
  
### <a name="querying-xml-schemas"></a><span data-ttu-id="7c96c-212">Esecuzione di query su elementi XML Schema</span><span class="sxs-lookup"><span data-stu-id="7c96c-212">Querying XML Schemas</span></span>  
 <span data-ttu-id="7c96c-213">Per eseguire query sugli elementi XML Schema caricati in raccolte di XML Schema è possibile:</span><span class="sxs-lookup"><span data-stu-id="7c96c-213">You can query XML schemas that you have loaded into XML schema collections in the following ways:</span></span>  
  
-   <span data-ttu-id="7c96c-214">Scrivere query Transact-SQL sulle viste del catalogo per gli spazi dei nomi degli elementi XML Schema.</span><span class="sxs-lookup"><span data-stu-id="7c96c-214">Write Transact-SQL queries on catalog views for XML schema namespaces.</span></span>  
  
-   <span data-ttu-id="7c96c-215">Creare una tabella contenente una colonna con tipo di dati `xml` per archiviare gli elementi XML Schema e quindi caricarli nel sistema di tipi XML.</span><span class="sxs-lookup"><span data-stu-id="7c96c-215">Create a table that contains an `xml` data type column to store your XML schemas and also load them into the XML type system.</span></span> <span data-ttu-id="7c96c-216">Per eseguire query sulla colonna XML, è possibile utilizzare i metodi per il tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="7c96c-216">You can query the XML column by using the `xml` data type methods.</span></span> <span data-ttu-id="7c96c-217">È inoltre possibile compilare un indice XML su questa colonna.</span><span class="sxs-lookup"><span data-stu-id="7c96c-217">Also, you can build an XML index on this column.</span></span> <span data-ttu-id="7c96c-218">Questo approccio richiede tuttavia che l'applicazione mantenga la consistenza tra gli elementi XML Schema archiviati nella colonna XML e il sistema di tipi XML.</span><span class="sxs-lookup"><span data-stu-id="7c96c-218">However, with this approach, the application must maintain consistency between the XML schemas stored in the XML column and the XML type system.</span></span> <span data-ttu-id="7c96c-219">Se ad esempio si elimina lo spazio dei nomi di un elemento XML Schema dal sistema di tipi XML, per mantenere la consistenza sarà necessario eliminarlo anche dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="7c96c-219">For example, if you drop the XML schema namespace from the XML type system, you also have to drop it from the table in order to preserve consistency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c96c-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c96c-220">See Also</span></span>  
 <span data-ttu-id="7c96c-221">[Visualizzare una raccolta di XML Schema archiviata](../xml/view-a-stored-xml-schema-collection.md) </span><span class="sxs-lookup"><span data-stu-id="7c96c-221">[View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md) </span></span>  
 <span data-ttu-id="7c96c-222">[Pre-elaborazione di uno schema per unire schemi inclusi](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="7c96c-222">[Preprocess a Schema to Merge Included Schemas](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span></span>  
 [<span data-ttu-id="7c96c-223">Requisiti e limitazioni per le raccolte di XML Schema nel server</span><span class="sxs-lookup"><span data-stu-id="7c96c-223">Requirements and Limitations for XML Schema Collections on the Server</span></span>](../xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
