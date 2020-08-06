---
title: Convertire colonne esistenti in colonne XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- tables [XML]
ms.assetid: 0d951424-9862-41fe-bd46-127f1c059bcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 32447851fcfe2a54143a028a94539532bba6708d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623949"
---
# <a name="change-existing-columns-to-xml-columns"></a><span data-ttu-id="c5121-102">Conversione di colonne esistenti a colonne XML</span><span class="sxs-lookup"><span data-stu-id="c5121-102">Change Existing Columns to XML Columns</span></span>
  <span data-ttu-id="c5121-103">L'istruzione ALTER TABLE supporta il tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="c5121-103">The ALTER TABLE statement supports the `xml` data type.</span></span> <span data-ttu-id="c5121-104">Ad esempio, è possibile modificare qualsiasi colonna di tipo string nel tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="c5121-104">For example, you can alter any string type column to the `xml` data type.</span></span> <span data-ttu-id="c5121-105">Si noti che in questi casi è necessaria la correttezza del formato dei documenti contenuti nella colonna.</span><span class="sxs-lookup"><span data-stu-id="c5121-105">Note that in these cases, the documents contained in the column must be well formed.</span></span> <span data-ttu-id="c5121-106">Se inoltre si sta modificando il tipo della colonna da stringa a XML tipizzato, i documenti nella colonna vengono convalidati rispetto agli schemi XSD specificati.</span><span class="sxs-lookup"><span data-stu-id="c5121-106">Also, if you are changing the type of the column from string to typed xml, the documents in the column are validated against the specified XSD schemas.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 nvarchar(max))  
GO  
INSERT INTO T   
VALUES (1, '<Root><Product ProductID="1"/></Root>')  
GO  
ALTER TABLE T   
ALTER COLUMN Col2 xml  
GO  
```  
  
 <span data-ttu-id="c5121-107">È possibile modificare una colonna di tipo `xml` da XML non tipizzato a XML tipizzato.</span><span class="sxs-lookup"><span data-stu-id="c5121-107">You can change an `xml` type column from untyped XML to typed XML.</span></span> <span data-ttu-id="c5121-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c5121-108">For example:</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T   
values (1, '<p1:ProductDescription ProductModelID="1"   
xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
            </p1:ProductDescription>')  
GO   
-- Make it a typed xml column by specifying a schema collection.  
ALTER TABLE T   
ALTER COLUMN Col2 xml (Production.ProductDescriptionSchemaCollection)  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c5121-109">Lo script verrà eseguito sul database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , poiché la raccolta XML Schema `Production.ProductDescriptionSchemaCollection`viene creata come parte del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5121-109">The script will run against [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, because the XML schema collection, `Production.ProductDescriptionSchemaCollection`, is created as part of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="c5121-110">Nell'esempio precedente, tutte le istanze archiviate nella colonna vengono convalidate e tipizzate rispetto agli schemi XSD nella raccolta specificata.</span><span class="sxs-lookup"><span data-stu-id="c5121-110">In the previous example, all the instances stored in the column are validated and typed against the XSD schemas in the specified collection.</span></span> <span data-ttu-id="c5121-111">Se la colonna contiene una o più istanze XML non valide rispetto allo schema specificato, l'istruzione `ALTER TABLE` avrà esito negativo e non sarà possibile modificare il tipo della colonna da XML non tipizzato a XML tipizzato.</span><span class="sxs-lookup"><span data-stu-id="c5121-111">If the column contains one or more XML instances that are invalid with regard to the specified schema, the `ALTER TABLE` statement will fail and you will not be able to change your untyped XML column into typed XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5121-112">Se una tabella è di grandi dimensioni, la modifica di una colonna di tipo `xml` può risultare onerosa,</span><span class="sxs-lookup"><span data-stu-id="c5121-112">If a table is large, modifying an `xml` type column can be costly.</span></span> <span data-ttu-id="c5121-113">poiché è necessario un controllo di correttezza del formato di ogni documento e, nel caso del codice XML tipizzato, è necessaria anche la convalida.</span><span class="sxs-lookup"><span data-stu-id="c5121-113">This is because each document must be checked for being well formed and, for typed XML, must also be validated.</span></span>  
  
 <span data-ttu-id="c5121-114">Per altre informazioni sul codice XML tipizzato, vedere [Confrontare dati XML tipizzati con dati XML non tipizzati](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c5121-114">For more information about typed XML, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
  
