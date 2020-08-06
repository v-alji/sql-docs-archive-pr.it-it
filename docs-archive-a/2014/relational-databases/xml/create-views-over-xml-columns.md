---
title: Creare viste su colonne XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- views [XML in SQL Server]
ms.assetid: eb5f0439-1f69-49c2-8759-e59bda1633b7
author: rothja
ms.author: jroth
ms.openlocfilehash: bf06f1107cbf4875eb63fe6747775b5c5c04810c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722615"
---
# <a name="create-views-over-xml-columns"></a><span data-ttu-id="a89cf-102">Creazione di viste</span><span class="sxs-lookup"><span data-stu-id="a89cf-102">Create Views over XML Columns</span></span>
  <span data-ttu-id="a89cf-103">Le colonne di tipo `xml` possono essere utilizzate per la creazione di viste.</span><span class="sxs-lookup"><span data-stu-id="a89cf-103">You can use an `xml` type column to create views.</span></span> <span data-ttu-id="a89cf-104">Nell'esempio seguente viene creata una vista nella quale il valore di una colonna di tipo `xml` viene recuperato utilizzando il metodo `value()` del tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="a89cf-104">The following example creates a view in which the value from an `xml` type column is retrieved using the `value()` method of the `xml` data type.</span></span>  
  
```  
-- Create the table.  
CREATE TABLE T (  
    ProductID          int primary key,   
    CatalogDescription xml)  
GO  
-- Insert sample data.  
INSERT INTO T values(1,'<ProductDescription ProductID="1" ProductName="SomeName" />')  
GO  
-- Create view (note the value() method used to retrieve ProductName   
-- attribute value from the XML).  
CREATE VIEW MyView AS   
  SELECT ProductID,  
         CatalogDescription.value('(/ProductDescription/@ProductName)[1]', 'varchar(40)') AS PName  
  FROM T  
GO   
```  
  
 <span data-ttu-id="a89cf-105">Eseguire la query seguente sulla vista:</span><span class="sxs-lookup"><span data-stu-id="a89cf-105">Execute the following query against the view:</span></span>  
  
```  
SELECT *   
FROM   MyView  
```  
  
 <span data-ttu-id="a89cf-106">Risultato:</span><span class="sxs-lookup"><span data-stu-id="a89cf-106">This is the result:</span></span>  
  
```  
ProductID   PName        
----------- ------------  
1           SomeName   
```  
  
 <span data-ttu-id="a89cf-107">Notare i punti seguenti circa l'utilizzo del tipo di dati `xml` per creare viste:</span><span class="sxs-lookup"><span data-stu-id="a89cf-107">Note the following points about using the `xml` data type to create views:</span></span>  
  
-   <span data-ttu-id="a89cf-108">Il tipo di dati xml può essere creato in una vista materializzata.</span><span class="sxs-lookup"><span data-stu-id="a89cf-108">The xml data type can be created in a materialized view.</span></span> <span data-ttu-id="a89cf-109">La vista materializzata non può essere basata su un metodo con tipo di dati XML,</span><span class="sxs-lookup"><span data-stu-id="a89cf-109">The materialized view cannot be based on an xml data type method.</span></span> <span data-ttu-id="a89cf-110">ma è possibile eseguirne il cast su una raccolta di XML Schema diversa dalla colonna di tipo xml nella tabella di base.</span><span class="sxs-lookup"><span data-stu-id="a89cf-110">However, it can be cast to an XML schema collection that is different from the xml type column in the base table.</span></span>  
  
-   <span data-ttu-id="a89cf-111">Il tipo di dati `xml` non può essere utilizzato nelle viste partizionate distribuite.</span><span class="sxs-lookup"><span data-stu-id="a89cf-111">The `xml` data type cannot be used in Distributed Partitioned Views.</span></span>  
  
-   <span data-ttu-id="a89cf-112">I predicati SQL in esecuzione sulla vista non saranno inseriti in XQuery per la definizione della vista.</span><span class="sxs-lookup"><span data-stu-id="a89cf-112">SQL predicates running against the view will not be pushed into the XQuery of the view definition.</span></span>  
  
-   <span data-ttu-id="a89cf-113">I metodi con tipo di dati XML in una vista non sono aggiornabili.</span><span class="sxs-lookup"><span data-stu-id="a89cf-113">XML data type methods in a view are not updatable.</span></span>  
  
  
