---
title: 'Esempio: Specifica delle direttive ID e IDREFS | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- IDREFS directive
- ID directive
ms.assetid: 99b9f0d8-ecbb-4225-859f-881066c09785
author: rothja
ms.author: jroth
ms.openlocfilehash: c21ba1bd19691014f179801421322970a3dd6dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636602"
---
# <a name="example-specifying-the-id-and-idrefs-directives"></a><span data-ttu-id="6cdf5-102">Esempio: Specifica delle direttive ID e IDREFS</span><span class="sxs-lookup"><span data-stu-id="6cdf5-102">Example: Specifying the ID and IDREFS Directives</span></span>
  <span data-ttu-id="6cdf5-103">Un attributo dell'elemento può essere specificato come attributo di tipo `ID` e l'attributo `IDREFS` può quindi essere utilizzato per fare riferimento a tale attributo.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-103">An element attribute can be specified as an `ID` type attribute, and the `IDREFS` attribute can then be used to refer to it.</span></span> <span data-ttu-id="6cdf5-104">In questo modo è possibile creare collegamenti tra più documenti, in modo analogo alla relazione esistente tra chiave primaria e chiave esterna nei database relazionali.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-104">This enables intra-document links and is similar to the primary key and foreign key relationships in relational databases.</span></span>  
  
 <span data-ttu-id="6cdf5-105">Nell'esempio seguente viene illustrato l'utilizzo delle direttive `ID` e `IDREFS` per la creazione di attributi dei tipi `ID` e `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-105">This example illustrates how the `ID` and `IDREFS` directives can be used to create attributes of `ID` and `IDREFS` types.</span></span> <span data-ttu-id="6cdf5-106">Poiché gli ID non possono essere valori Integer, nell'esempio i valori di ID vengono convertiti,</span><span class="sxs-lookup"><span data-stu-id="6cdf5-106">Because IDs cannot be integer values, the ID values in this example are converted.</span></span> <span data-ttu-id="6cdf5-107">ovvero ne viene eseguito il cast di tipo.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-107">In other words, they are type casted.</span></span> <span data-ttu-id="6cdf5-108">Vengono utilizzati prefissi per i valori degli ID.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-108">Prefixes are used for the ID values.</span></span>  
  
 <span data-ttu-id="6cdf5-109">Si supponga di voler generare codice XML come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6cdf5-109">Assume that you want to construct XML as shown in the following:</span></span>  
  
```  
<Customer CustomerID="C1" SalesOrderIDList=" O11 O22 O33..." >  
    <SalesOrder SalesOrderID="O11" OrderDate="..." />  
    <SalesOrder SalesOrderID="O22" OrderDate="..." />  
    <SalesOrder SalesOrderID="O33" OrderDate="..." />  
    ...  
</Customer>  
```  
  
 <span data-ttu-id="6cdf5-110">L'attributo `SalesOrderIDList` dell'elemento < `Customer` > è un attributo multivalore che fa riferimento all'attributo `SalesOrderID` dell'elemento < `SalesOrder` >.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-110">The `SalesOrderIDList` attribute of the < `Customer` > element is a multivalued attribute that refers to the `SalesOrderID` attribute of the < `SalesOrder` > element.</span></span> <span data-ttu-id="6cdf5-111">Per stabilire il collegamento, è necessario dichiarare l'attributo `SalesOrderID` con il tipo di dati `ID` e l'attributo `SalesOrderIDList` dell'elemento < `Customer`> con il tipo di dati `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-111">To establish this link, the `SalesOrderID` attribute must be declared of `ID` type, and the `SalesOrderIDList` attribute of the < `Customer`> element must be declared of `IDREFS` type.</span></span> <span data-ttu-id="6cdf5-112">Poiché un cliente può inviare più ordini, viene utilizzato il tipo `IDREFS` .</span><span class="sxs-lookup"><span data-stu-id="6cdf5-112">Because a customer can request several orders, the `IDREFS` type is used.</span></span>  
  
 <span data-ttu-id="6cdf5-113">Anche gli attributi `IDREFS` hanno più di un valore.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-113">Elements of `IDREFS` type also have more than one value.</span></span> <span data-ttu-id="6cdf5-114">È pertanto necessario utilizzare una clausola SELECT separata che riutilizzerà le stesse informazioni di Tag, Parent e colonna chiave.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-114">Therefore, you have to use a separate select clause that will reuse the same tag, parent, and key column information.</span></span> <span data-ttu-id="6cdf5-115">È poi necessario utilizzare `ORDER BY` per garantire che le sequenze di righe che compongono i valori `IDREFS` vengano visualizzate raggruppate sotto il rispettivo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-115">The `ORDER BY` then has to ensure that the sequence of rows that make up the `IDREFS` values appears grouped together under their parent element.</span></span>  
  
 <span data-ttu-id="6cdf5-116">Di seguito è riportata la query che genera il codice XML desiderato.</span><span class="sxs-lookup"><span data-stu-id="6cdf5-116">This is the query that produces the XML you want.</span></span> <span data-ttu-id="6cdf5-117">La query utilizza le direttive `ID` e `IDREFS` per sovrascrivere i tipi nei nomi di colonna (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span><span class="sxs-lookup"><span data-stu-id="6cdf5-117">The query uses the `ID` and `IDREFS` directives to overwrite the types in the column names (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID       [Customer!1!CustomerID],  
        NULL               [Customer!1!SalesOrderIDList!IDREFS],  
        NULL               [SalesOrder!2!SalesOrderID!ID],  
        NULL               [SalesOrder!2!OrderDate]  
FROM   Sales.Customer C   
UNION ALL   
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID,  
        'O-'+CAST(SalesOrderID as varchar(10)),   
        NULL,  
        NULL  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
        C.CustomerID,  
        NULL,  
        'O-'+CAST(SalesOrderID as varchar(10)),  
        OrderDate  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerIDORDER BY [Customer!1!CustomerID] ,  
         [SalesOrder!2!SalesOrderID!ID],  
         [Customer!1!SalesOrderIDList!IDREFS]  
FOR XML EXPLICIT;  
```  
  
## <a name="see-also"></a><span data-ttu-id="6cdf5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cdf5-118">See Also</span></span>  
 [<span data-ttu-id="6cdf5-119">Usare la modalità EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="6cdf5-119">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
