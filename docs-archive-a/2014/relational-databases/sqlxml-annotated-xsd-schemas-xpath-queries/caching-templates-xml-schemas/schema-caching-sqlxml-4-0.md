---
title: Memorizzazione nella cache degli schemi (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- schemas [SQLXML]
ms.assetid: 7e5fda21-b435-41fd-b637-8b616560a93f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e36711955fa28bafd3b0996b1a02f6cd71f3c4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636630"
---
# <a name="schema-caching-sqlxml-40"></a><span data-ttu-id="7331b-102">Memorizzazione nella cache degli schemi (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7331b-102">Schema Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="7331b-103">Con un'installazione side-by-side di XML per Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0 e SQLXML 3.0, è possibile controllare in modo esplicito la memorizzazione degli schemi nella cache in tutte le versioni attraverso le chiavi del Registro di sistema seguenti:</span><span class="sxs-lookup"><span data-stu-id="7331b-103">With a side-by-side installation of XML for Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0, and SQLXML 3.0, you can explicitly control the schema caching in all versions by using the following registry keys:</span></span>  
  
 <span data-ttu-id="7331b-104">Web Release 1:</span><span class="sxs-lookup"><span data-stu-id="7331b-104">Web Release 1:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXMLX\SchemaCacheSize  
```  
  
 <span data-ttu-id="7331b-105">SQLXML 2,0:</span><span class="sxs-lookup"><span data-stu-id="7331b-105">SQLXML 2.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML2\SchemaCacheSize  
```  
  
 <span data-ttu-id="7331b-106">SQLXML 3.0:</span><span class="sxs-lookup"><span data-stu-id="7331b-106">SQLXML 3.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML3\SchemaCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="7331b-107">Per ulteriori informazioni sull'installazione side-by-Side, vedere Novità [di SQLXML 4,0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span><span class="sxs-lookup"><span data-stu-id="7331b-107">For more information about side-by-side installation, see [What's New in SQLXML 4.0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span></span>  
  
 <span data-ttu-id="7331b-108">La memorizzazione nella cache degli schemi migliora notevolmente le prestazioni di una query XPath.</span><span class="sxs-lookup"><span data-stu-id="7331b-108">Schema caching significantly improves the performance of an XPath query.</span></span> <span data-ttu-id="7331b-109">Quando una query XPath viene eseguita su uno schema di mapping, lo schema viene archiviato in memoria e le strutture dei dati necessarie vengono incluse in memoria.</span><span class="sxs-lookup"><span data-stu-id="7331b-109">When an XPath query is executed against a mapping schema, the schema is stored in memory, and the necessary data structures are built in memory.</span></span> <span data-ttu-id="7331b-110">Se la memorizzazione nella cache degli schemi è impostata, lo schema resta in memoria e comporta un miglioramento delle prestazioni per le query XPath successive.</span><span class="sxs-lookup"><span data-stu-id="7331b-110">If schema caching is set, the schema remains in memory, thereby improving performance for subsequent XPath queries.</span></span>  
  
 <span data-ttu-id="7331b-111">È possibile impostare le dimensioni della cache degli schemi aggiungendo nel Registro di sistema la chiave sopra riportata.</span><span class="sxs-lookup"><span data-stu-id="7331b-111">You can set the schema cache size by adding the above key in the registry</span></span>  
  
 <span data-ttu-id="7331b-112">Le dimensioni dello schema vengono impostate in base sulla memoria disponibile e al numero di schemi utilizzati.</span><span class="sxs-lookup"><span data-stu-id="7331b-112">The schema size is set based on the available memory and the number of schemas you are using.</span></span> <span data-ttu-id="7331b-113">Le dimensioni predefinite di **SchemaCacheSize** sono 31.</span><span class="sxs-lookup"><span data-stu-id="7331b-113">The default **SchemaCacheSize** size is 31.</span></span> <span data-ttu-id="7331b-114">Se si imposta **SchemaCacheSize** su un valore superiore, viene utilizzata una quantità maggiore di memoria.</span><span class="sxs-lookup"><span data-stu-id="7331b-114">If you set **SchemaCacheSize** higher, more memory is used.</span></span> <span data-ttu-id="7331b-115">Pertanto, è possibile aumentare le dimensioni della cache se l'accesso allo schema sembra lento o ridurle se la memoria è insufficiente.</span><span class="sxs-lookup"><span data-stu-id="7331b-115">Therefore, you can increase the cache size if schema access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="7331b-116">Per motivi di prestazioni, è consigliabile impostare **SchemaCacheSize** su un valore superiore al numero di schemi di mapping utilizzati in genere.</span><span class="sxs-lookup"><span data-stu-id="7331b-116">For performance reasons, it is recommended that you set **SchemaCacheSize** higher than the number of mapping schemas you usually use.</span></span> <span data-ttu-id="7331b-117">Con l'aumentare del numero di schemi, se **SchemaCacheSize** è inferiore al numero di schemi disponibili, le prestazioni diminuiscono.</span><span class="sxs-lookup"><span data-stu-id="7331b-117">As the number of schemas increase, if **SchemaCacheSize** is less than the number of schemas you have, the performance degrades.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7331b-118">Durante lo sviluppo, è consigliabile non memorizzare nella cache gli schemi, in quanto le modifiche apportate agli schemi non vengono riflesse nella cache per circa due minuti.</span><span class="sxs-lookup"><span data-stu-id="7331b-118">During development, it is recommended that you do not cache the schemas, because the changes to the schemas are not reflected in the cache for about two minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7331b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7331b-119">See Also</span></span>  
 <span data-ttu-id="7331b-120">[Caching del modello &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="7331b-120">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="7331b-121">Caching XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7331b-121">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
