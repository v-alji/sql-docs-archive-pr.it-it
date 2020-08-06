---
title: Considerazioni sulla sicurezza per XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- client-side XML formatting
- FOR XML clause, security
- server-side XML formatting
- AUTO mode
- security [SQLXML], FOR XML
ms.assetid: facba279-df93-475b-ad43-0043dc5bae03
author: rothja
ms.author: jroth
ms.openlocfilehash: 9a64fa61848e4b5435b2aa944c53953a8c083ab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635989"
---
# <a name="for-xml-security-considerations-sqlxml-40"></a><span data-ttu-id="bcf06-102">Considerazioni sulla sicurezza per FOR XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="bcf06-102">FOR XML Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="bcf06-103">La modalità FOR XML AUTO genera una gerarchia XML in cui viene eseguito il mapping dei nomi di elemento ai nomi di tabella e dei nomi di attributo ai nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="bcf06-103">The FOR XML AUTO mode generates an XML hierarchy in which element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="bcf06-104">In questo modo vengono esposte le informazioni sulle colonne e sulle tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="bcf06-104">This exposes the database table and column information.</span></span> <span data-ttu-id="bcf06-105">È possibile nascondere le informazioni del database quando si utilizza la modalità AUTO (formattazione sul lato server) specificando gli alias di colonne e di tabelle nella query.</span><span class="sxs-lookup"><span data-stu-id="bcf06-105">You can hide the database information when you use AUTO mode (server-side formatting) by specifying table and column aliases in the query.</span></span> <span data-ttu-id="bcf06-106">Questi alias vengono restituiti nel documento XML risultante come nomi di elemento e di attributo.</span><span class="sxs-lookup"><span data-stu-id="bcf06-106">These aliases are returned in the resulting XML document as element and attribute names.</span></span>  
  
 <span data-ttu-id="bcf06-107">Nella query seguente ad esempio viene specificata la modalità AUTO; pertanto, la formattazione XML viene eseguita nel server:</span><span class="sxs-lookup"><span data-stu-id="bcf06-107">For example, the following query specifies AUTO mode; therefore, the XML formatting is done on the server:</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="bcf06-108">Nel documento XML risultante vengono utilizzati gli alias per i nomi di elemento e di attributo:</span><span class="sxs-lookup"><span data-stu-id="bcf06-108">In the resulting XML document, the aliases are used for element and attribute names:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <C F="Nancy" L="Fuller" />   
  <CE F="Andrew" L="Peacock" />   
  <C F="Janet" L="Leverling" />   
  ...  
</root>  
```  
  
 <span data-ttu-id="bcf06-109">Quando si utilizza la modalità NESTED (formattazione sul lato client), gli alias vengono restituiti solo per gli attributi nel documento XML risultante.</span><span class="sxs-lookup"><span data-stu-id="bcf06-109">When you use NESTED mode (client-side formatting), aliases are returned only for attributes in the resulting XML document.</span></span> <span data-ttu-id="bcf06-110">I nomi delle tabelle di base vengono restituiti sempre come nomi di elemento.</span><span class="sxs-lookup"><span data-stu-id="bcf06-110">The names of the base tables are always returned as element names.</span></span> <span data-ttu-id="bcf06-111">Ad esempio, nella query seguente viene specificata la modalità NESTED.</span><span class="sxs-lookup"><span data-stu-id="bcf06-111">For example, the following query specifies NESTED mode.</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="bcf06-112">Nel documento XML risultante i nomi delle tabelle di base vengono restituiti come nomi di elemento e gli alias di tabella non vengono utilizzati:</span><span class="sxs-lookup"><span data-stu-id="bcf06-112">In the resulting XML document, the names of the base tables are returned as element names and table aliases are not used:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Person.Contact F="Nancy" L="Fuller" />   
  <Person.Contact F="Andrew" L="Peacock" />   
  <Person.Contact F="Janet" L="Leverling" />   
       ...  
</root>  
```  
  
  
