---
title: Considerazioni sulla sicurezza dello schema con annotazioni (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping schema [SQLXML], security
- annotated XDR schemas, security
- XDR schemas [SQLXML], security
- annotations [SQLXML]
- annotated XSD schemas, security
- SQLXML, annotated XSD schemas
- SQLXML, annotated XDR schemas
- security [SQLXML], annotated schemas
- XSD schemas [SQLXML], security
ms.assetid: 7d7e44dc-b6d3-4e0f-95c7-8f99930c94f2
author: rothja
ms.author: jroth
ms.openlocfilehash: 098f554410a846ed0223d17117b51025dfcf7897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623978"
---
# <a name="annotated-schema-security-considerations-sqlxml-40"></a><span data-ttu-id="a222f-102">Considerazioni relative alla sicurezza degli schemi con annotazioni (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="a222f-102">Annotated Schema Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="a222f-103">Di seguito sono riportate alcune linee guida relative alla sicurezza quando si utilizzano gli schemi con annotazioni.</span><span class="sxs-lookup"><span data-stu-id="a222f-103">The following are security guidelines for using annotated schemas:</span></span>  
  
-   <span data-ttu-id="a222f-104">Evitare di utilizzare il mapping predefinito negli schemi di mapping.</span><span class="sxs-lookup"><span data-stu-id="a222f-104">Avoid using default mapping in the mapping schemas.</span></span> <span data-ttu-id="a222f-105">Il mapping predefinito, infatti, espone le informazioni del database (nomi di tabella e di colonna) nel documento XML risultante in quanto, per impostazione predefinita, i nomi di elemento vengono mappati ai nomi di tabella e i nomi di attributo vengono mappati ai nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="a222f-105">The default mapping exposes the database information (table and column names) in the resulting XML document because, by default, the element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="a222f-106">Pertanto, qualsiasi utente che visualizza il documento XML può accedere anche alle informazioni su tabelle e colonne nel database, ponendo un problema di sicurezza potenziale.</span><span class="sxs-lookup"><span data-stu-id="a222f-106">Therefore, any user who sees the XML document has access to the table and column information in the database, presenting a potential security risk.</span></span> <span data-ttu-id="a222f-107">Per evitare questo rischio, specificare nomi di elementi e di attributi arbitrari nello schema e utilizzare le annotazioni per mapparli esplicitamente alle tabelle e alle colonne.</span><span class="sxs-lookup"><span data-stu-id="a222f-107">To avoid this risk, specify arbitrary element and attribute names in the schema and use annotations to explicitly map them to the tables and columns.</span></span> <span data-ttu-id="a222f-108">Per ulteriori informazioni sull'utilizzo del mapping predefinito durante la creazione di schemi XSD, vedere [mapping predefinito di elementi e attributi XSD a tabelle e colonne &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="a222f-108">For more information about using default mapping when you create XSD schemas, see [Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="a222f-109">Il mapping esplicito specificato mediante le annotazioni espone le informazioni del database, ad esempio i nomi di tabelle e colonne.</span><span class="sxs-lookup"><span data-stu-id="a222f-109">The explicit mapping specified using the annotations exposes the database information (such as table names and column names).</span></span> <span data-ttu-id="a222f-110">È opportuno dunque non rendere pubblici pubblicamente questi schemi.</span><span class="sxs-lookup"><span data-stu-id="a222f-110">Therefore, you may not want to make these schemas available publicly.</span></span>  
  
-   <span data-ttu-id="a222f-111">L'esecuzione di determinate query, ad esempio quelle specificate su uno schema di mapping con ricorsione utilizzando l'annotazione `max-depth` impostata su un valore più elevato, può richiedere tempi più lunghi.</span><span class="sxs-lookup"><span data-stu-id="a222f-111">Certain queries such as those specified against mapping schema with recursion (specified using `max-depth` annotation set to a higher value) may take longer to execute.</span></span> <span data-ttu-id="a222f-112">È possibile specificare facoltativamente un limite di timeout impostando la proprietà timeout comando (in secondi).</span><span class="sxs-lookup"><span data-stu-id="a222f-112">You can optionally specify a time-out limit by setting the Command Time Out property (in seconds).</span></span> <span data-ttu-id="a222f-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a222f-113">For example:</span></span>  
  
    ```  
    cn.Open "Provider=SQLOLEDB;Server=localhost;Database=tempdb;Integrated Security=SSPI;Command Properties='Command Time Out=50';"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a222f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a222f-114">See Also</span></span>  
 [<span data-ttu-id="a222f-115">Schemi XSD con annotazioni in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="a222f-115">Annotated XSD Schemas in SQLXML 4.0</span></span>](../../sqlxml/annotated-xsd-schemas/annotated-xsd-schemas-in-sqlxml-4-0.md)  
  
  
