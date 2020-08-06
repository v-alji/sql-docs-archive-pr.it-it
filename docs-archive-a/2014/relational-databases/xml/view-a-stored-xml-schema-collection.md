---
title: Visualizzare una raccolta di XML Schema archiviata| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- schema collections [SQL Server], viewing
- XML schemas [SQL Server], viewing
- CREATE XML SCHEMA COLLECTION statement
- xml_schema_namespace function
- XML schema collections [SQL Server], viewing
- displaying XML schema collections
- viewing XML schema collections
ms.assetid: e38031af-22df-4cd9-a14e-e316b822f91b
author: rothja
ms.author: jroth
ms.openlocfilehash: 6383fb17183a991d2f83325044663cc9671e9442
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625254"
---
# <a name="view-a-stored-xml-schema-collection"></a><span data-ttu-id="b1919-102">Visualizzazione di una raccolta di XML Schema archiviata</span><span class="sxs-lookup"><span data-stu-id="b1919-102">View a Stored XML Schema Collection</span></span>
  <span data-ttu-id="b1919-103">Dopo aver importato una raccolta di XML Schema tramite l'istruzione [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), i componenti di schema vengono archiviati nei metadati.</span><span class="sxs-lookup"><span data-stu-id="b1919-103">After you import an XML schema collection by using [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), the schema components are stored in the metadata.</span></span> <span data-ttu-id="b1919-104">Per ricostruire la raccolta di XML Schema, è possibile usare la funzione intrinseca [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace).</span><span class="sxs-lookup"><span data-stu-id="b1919-104">You can use the [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)intrinsic function to reconstruct the XML schema collection.</span></span> <span data-ttu-id="b1919-105">Questa funzione restituisce un'istanza del tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="b1919-105">This function returns an `xml` data type instance.</span></span>  
  
 <span data-ttu-id="b1919-106">Ad esempio, la query seguente restituisce una raccolta di XML Schema (`ProductDescriptionSchemaCollection`) dallo schema relazionale di produzione nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1919-106">For example, the following query retrieves an XML schema collection (`ProductDescriptionSchemaCollection`) from the production relational schema in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection')  
GO  
```  
  
 <span data-ttu-id="b1919-107">Se si desidera visualizzare solo uno schema della raccolta di XML Schema, è possibile specificare una query XQuery sul risultato di tipo `xml` restituito dalla funzione `xml_schema_namespace`.</span><span class="sxs-lookup"><span data-stu-id="b1919-107">If you want to see only one schema from the XML schema collection, you can specify XQuery against the `xml` type result that is returned by `xml_schema_namespace`.</span></span>  
  
```  
SELECT xml_schema_namespace(N'RelationalSchemaName',N'XmlSchemaCollectionName').query('  
/xs:schema[@targetNamespace="TargetNameSpace"]  
')  
GO  
```  
  
 <span data-ttu-id="b1919-108">Ad esempio, la query seguente recupera le informazioni di XML Schema relative alla manutenzione e alla garanzia dei prodotti dalla raccolta di schemi `ProductDescriptionSchemaCollection` .</span><span class="sxs-lookup"><span data-stu-id="b1919-108">For example, the following query retrieves product warranty and maintenance XML schema information from the `ProductDescriptionSchemaCollection` XML schema collection.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection').query('  
/xs:schema[@targetNamespace="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"]  
')  
GO  
```  
  
 <span data-ttu-id="b1919-109">Per recuperare uno schema specifico dalla raccolta, è inoltre possibile passare lo spazio dei nomi di destinazione facoltativo come terzo parametro della funzione `xml_schema_namespace` , come illustrato nella query seguente:</span><span class="sxs-lookup"><span data-stu-id="b1919-109">You can also pass the optional target namespace as the third parameter to the `xml_schema_namespace` function to retrieve specific schema from the collection, as shown in the following query:</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection', N'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain')  
GO  
```  
  
 <span data-ttu-id="b1919-110">Quando si crea una raccolta di XML Schema nel database tramite l'istruzione CREATE XML SCHEMA COLLECTION, i componenti di schema vengono archiviati nei metadati.</span><span class="sxs-lookup"><span data-stu-id="b1919-110">When you create an XML schema collection by using CREATE XML SCHEMA COLLECTION in the database, the statement stores the schema components in the metadata.</span></span> <span data-ttu-id="b1919-111">Si noti che vengono archiviati solo i componenti di schema riconosciuti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1919-111">Note that only the schema components that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] understands are stored.</span></span> <span data-ttu-id="b1919-112">Non vengono archiviati commenti, annotazioni o attributi non XSD.</span><span class="sxs-lookup"><span data-stu-id="b1919-112">Any comments, annotations, or non-XSD attributes are not stored.</span></span> <span data-ttu-id="b1919-113">Dal punto di vista funzionale, pertanto, lo schema ricostruito dalla funzione **xml_schema_namespace** è equivalente allo schema originale, ma l'aspetto non sarà necessariamente identico.</span><span class="sxs-lookup"><span data-stu-id="b1919-113">Therefore, the schema reconstructed by **xml_schema_namespace** is functionally equivalent to the original schema, but it will not necessarily look the same.</span></span> <span data-ttu-id="b1919-114">Ad esempio, non verranno visualizzati gli stessi prefissi dello schema originale.</span><span class="sxs-lookup"><span data-stu-id="b1919-114">For example, you will not see the same prefixes you had in the original schema.</span></span> <span data-ttu-id="b1919-115">Lo schema restituito dalla funzione **xml_schema_namespace** usa **t** come prefisso per lo spazio dei nomi di destinazione e **ns1**, **ns2**e così via per gli altri spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b1919-115">The schema returned by **xml_schema_namespace** uses **t** as the prefix for the target namespace and **ns1**, **ns2**, and so on, for other namespaces.</span></span>  
  
 <span data-ttu-id="b1919-116">Se si desidera mantenere una copia identica di XML Schema, è consigliabile salvarli in un file o in una tabella di database all'interno di una colonna di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="b1919-116">If you want to retain an identical copy of the XML schemas, you should save your XML schema in a file or in a database table in an `xml` type column.</span></span>  
  
 <span data-ttu-id="b1919-117">La vista del catalogo [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) restituisce anche informazioni sulle raccolte di XML Schema,</span><span class="sxs-lookup"><span data-stu-id="b1919-117">The [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) catalog view also returns information about XML schema collections.</span></span> <span data-ttu-id="b1919-118">che includono il nome, la data di creazione e il proprietario della raccolta.</span><span class="sxs-lookup"><span data-stu-id="b1919-118">This information includes the name of the collection, the creation date, and the owner of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1919-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1919-119">See Also</span></span>  
 [<span data-ttu-id="b1919-120">Raccolte di XML Schema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b1919-120">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
