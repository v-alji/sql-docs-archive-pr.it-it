---
title: Memorizzazione nella cache di modelli, XSL e schemi (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, caching
- cache [SQLXML]
- memory [SQLXML]
ms.assetid: 80b4fa79-243f-442c-9f22-74ad66186501
author: rothja
ms.author: jroth
ms.openlocfilehash: 4df25909cf156957908abf0691964fd66a76343a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629743"
---
# <a name="caching-templates-xsl-and-schemas-sqlxml-40"></a><span data-ttu-id="d6745-102">Memorizzazione nella cache di modelli, file XSL e schemi (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d6745-102">Caching Templates, XSL, and Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="d6745-103">Per migliorare le prestazioni,  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 supporta la memorizzazione di modelli, file XSL e schemi nella cache.</span><span class="sxs-lookup"><span data-stu-id="d6745-103">To improve performance, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 supports caching templates, XSL, and schemas.</span></span>  
  
 <span data-ttu-id="d6745-104">Tutti gli schemi, i modelli e i file XSL (ad eccezione dei file provenienti da un percorso http:// o ftp://) vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="d6745-104">All schemas, templates, and XSL files (except the files from an http:// or ftp:// location) are cached.</span></span> <span data-ttu-id="d6745-105">I file memorizzati nella cache restano in memoria mentre il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d6745-105">The cached files remain in memory while the process is running.</span></span> <span data-ttu-id="d6745-106">Al termine del processo, il contenuto della cache va perso.</span><span class="sxs-lookup"><span data-stu-id="d6745-106">As the process exits, all the cache is lost.</span></span> <span data-ttu-id="d6745-107">Di conseguenza, se si esegue un processo per query, i vantaggi della memorizzazione nella cache potrebbero essere irrilevanti.</span><span class="sxs-lookup"><span data-stu-id="d6745-107">Therefore, if you run one process per query, the caching benefit may not be noticeable.</span></span>  
  
 <span data-ttu-id="d6745-108">Negli argomenti di questa sezione vengono fornite ulteriori informazioni sulla memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="d6745-108">The topics in this section provide more information about caching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6745-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d6745-109">In This Section</span></span>  
 [<span data-ttu-id="d6745-110">Caching del modello &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d6745-110">Template Caching &#40;SQLXML 4.0&#41;</span></span>](template-caching-sqlxml-4-0.md)  
 <span data-ttu-id="d6745-111">Viene illustrata e quindi fornita una chiave del Registro di sistema per la memorizzazione nella cache dei modelli.</span><span class="sxs-lookup"><span data-stu-id="d6745-111">Describes and provides a registry key for template caching.</span></span>  
  
 [<span data-ttu-id="d6745-112">Caching XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d6745-112">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
 <span data-ttu-id="d6745-113">Viene illustrata e quindi fornita una chiave del Registro di sistema per la memorizzazione nella cache dei file XSL.</span><span class="sxs-lookup"><span data-stu-id="d6745-113">Describes and provides a registry key for XSL caching.</span></span>  
  
 [<span data-ttu-id="d6745-114">Caching dello schema &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d6745-114">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
 <span data-ttu-id="d6745-115">Vengono illustrati i problemi dell'installazione affiancata di SQLXML relativi alla memorizzazione nella cache degli schemi e vengono fornite chiavi del Registro di sistema per la memorizzazione nella cache degli schemi.</span><span class="sxs-lookup"><span data-stu-id="d6745-115">Discusses SQLXML side-by-side installation issues related to schema caching, and provides registry keys for schema caching.</span></span>  
  
  
