---
title: Caching del modello (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- templates [SQLXML], caching
ms.assetid: 73e151c6-b24e-4422-a116-51e0846bc6f5
author: rothja
ms.author: jroth
ms.openlocfilehash: b2ea8a539086ada1b15abbb9cff4f838af45818c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628585"
---
# <a name="template-caching-sqlxml-40"></a><span data-ttu-id="489fb-102">Memorizzazione nella cache dei modelli (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="489fb-102">Template Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="489fb-103">La memorizzazione dei modelli nella cache migliora significativamente le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="489fb-103">Template caching significantly improves performance.</span></span> <span data-ttu-id="489fb-104">Se è impostata, il modello rimane in memoria fino alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="489fb-104">If template caching is set, the template remains in memory upon its first execution.</span></span> <span data-ttu-id="489fb-105">In questo modo vengono migliorate le prestazioni per l'esecuzione successiva.</span><span class="sxs-lookup"><span data-stu-id="489fb-105">This improves the performance for the subsequent execution of the template.</span></span>  
  
 <span data-ttu-id="489fb-106">È possibile impostare le dimensioni della cache dei modelli aggiungendo nel Registro di sistema la chiave seguente:</span><span class="sxs-lookup"><span data-stu-id="489fb-106">You can set the template cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\TemplateCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="489fb-107">È consigliabile impostare le dimensioni del modello in base alla memoria disponibile e al numero di modelli utilizzati.</span><span class="sxs-lookup"><span data-stu-id="489fb-107">The template size should be set on the basis of the available memory and the number of templates you are using.</span></span> <span data-ttu-id="489fb-108">Il valore predefinito di **TemplateCacheSize** è 31.</span><span class="sxs-lookup"><span data-stu-id="489fb-108">The default of **TemplateCacheSize** size is 31.</span></span> <span data-ttu-id="489fb-109">È possibile aumentare le dimensioni della cache se l'accesso al modello sembra lento o ridurle se la memoria è insufficiente.</span><span class="sxs-lookup"><span data-stu-id="489fb-109">You can increase the cache size if template access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="489fb-110">Per ottenere prestazioni ottimali, è consigliabile impostare **TemplateCacheSize** su un valore superiore al numero di modelli utilizzati in genere.</span><span class="sxs-lookup"><span data-stu-id="489fb-110">For better performance, it is recommended that you set **TemplateCacheSize** higher than the number of templates you usually use.</span></span> <span data-ttu-id="489fb-111">Se **TemplateCacheSize** è inferiore al numero di modelli disponibili, le prestazioni diminuiscono con l'aumentare del numero di modelli.</span><span class="sxs-lookup"><span data-stu-id="489fb-111">If **TemlateCacheSize** is less than the number of templates you have, performance degrades as the number of templates increase.</span></span> <span data-ttu-id="489fb-112">**TemplateCacheSize** può essere impostato su un massimo di 128.</span><span class="sxs-lookup"><span data-stu-id="489fb-112">The **TemplateCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="489fb-113">Ogni volta che viene utilizzato un modello memorizzato nella cache, viene controllata l'ora di modifica del file modello per vedere se deve essere aggiornata.</span><span class="sxs-lookup"><span data-stu-id="489fb-113">Every time a cached template is used, the modification time of the template file is checked to see whether it needs to be refreshed.</span></span> <span data-ttu-id="489fb-114">Ciò accade in quanto la copia su disco è più recente della copia della cache.</span><span class="sxs-lookup"><span data-stu-id="489fb-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="489fb-115">I parametri di modello e le proprietà dei comandi non vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="489fb-115">Template parameters and command properties are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489fb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="489fb-116">See Also</span></span>  
 <span data-ttu-id="489fb-117">[Caching dello schema &#40;SQLXML 4,0&#41;](schema-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="489fb-117">[Schema Caching &#40;SQLXML 4.0&#41;](schema-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="489fb-118">Caching XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="489fb-118">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
