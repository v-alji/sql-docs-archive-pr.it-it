---
title: Architettura logica (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, architecture
- logical architecture [Analysis Services Multidimensional Data]
ms.assetid: 1b9cae0a-8990-4194-af5f-a1ea5f2aff06
author: minewiskan
ms.author: owend
ms.openlocfilehash: d93361fb14bc6544ffa7376439c2da0c8e06c3fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635810"
---
# <a name="logical-architecture-analysis-services---multidimensional-data"></a><span data-ttu-id="02bc9-102">Architettura logica (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="02bc9-102">Logical Architecture (Analysis Services - Multidimensional Data)</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="02bc9-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] usa componenti server e client per fornire Online Analytical Processing (OLAP) e data mining funzionalità per le applicazioni business intelligence:</span><span class="sxs-lookup"><span data-stu-id="02bc9-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses both server and client components to supply online analytical processing (OLAP) and data mining functionality for business intelligence applications:</span></span>  
  
-   <span data-ttu-id="02bc9-104">Il componente server di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] viene implementato come un servizio di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="02bc9-104">The server component of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] is implemented as a Microsoft Windows service.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="02bc9-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]supporta più istanze di nello stesso computer, ognuna delle quali è [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implementata come istanza separata del servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="02bc9-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] supports multiple instances on the same computer, with each instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implemented as a separate instance of the Windows service.</span></span>  
  
-   <span data-ttu-id="02bc9-106">I client comunicano con [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] mediante lo standard pubblico XML for Analysis (XMLA), un protocollo basato su SOAP per l'esecuzione di comandi e la ricezione di risposte che viene esposto come un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="02bc9-106">Clients communicate with [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] using the public standard XML for Analysis (XMLA), a SOAP-based protocol for issuing commands and receiving responses, exposed as a Web service.</span></span> <span data-ttu-id="02bc9-107">Tramite XMLA vengono inoltre offerti modelli a oggetti client a cui è possibile accedere usando un provider gestito, ad esempio ADOMD.NET, o un provider OLE DB nativo.</span><span class="sxs-lookup"><span data-stu-id="02bc9-107">Client object models are also provided over XMLA, and can be accessed either by using a managed provider, such as ADOMD.NET, or a native OLE DB provider.</span></span>  
  
-   <span data-ttu-id="02bc9-108">I comandi di query possono essere eseguiti tramite i linguaggi seguenti: SQL, MDX (Multidimensional Expressions), un linguaggio di query standard del settore per l'analisi, o DMX (Data Mining Extensions), un linguaggio di query standard del settore orientato al data mining.</span><span class="sxs-lookup"><span data-stu-id="02bc9-108">Query commands can be issued using the following languages: SQL; Multidimensional Expressions (MDX), an industry standard query language for analysis; or Data Mining Extensions (DMX), an industry standard query language oriented toward data mining.</span></span> <span data-ttu-id="02bc9-109">e il linguaggio ASSL (Analysis Services Scripting Language), che consente di gestire gli oggetti di database [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02bc9-109">Analysis Services Scripting Language (ASSL) can also be used to manage [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database objects.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="02bc9-110">supporta anche un motore dei cubi locali che permette alle applicazioni in client senza connessione di esplorare dati multidimensionali archiviati localmente.</span><span class="sxs-lookup"><span data-stu-id="02bc9-110">also supports a local cube engine that enables applications on disconnected clients to browse locally stored multidimensional data.</span></span> <span data-ttu-id="02bc9-111">Per ulteriori informazioni, vedere [requisiti dell'architettura client per lo sviluppo di Analysis Services](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span><span class="sxs-lookup"><span data-stu-id="02bc9-111">For more information, see [Client Architecture Requirements for Analysis Services Development](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02bc9-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="02bc9-112">In This Section</span></span>  
 <span data-ttu-id="02bc9-113">**Panoramica dell'architettura logica**</span><span class="sxs-lookup"><span data-stu-id="02bc9-113">**Logical Architecture Overview**</span></span>  
 [<span data-ttu-id="02bc9-114">Cenni preliminari sull'architettura logica &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="02bc9-114">Logical Architecture Overview &#40;Analysis Services - Multidimensional Data&#41;</span></span>](logical-architecture-overview-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="02bc9-115">**Oggetti server**</span><span class="sxs-lookup"><span data-stu-id="02bc9-115">**Server Objects**</span></span>  
 [<span data-ttu-id="02bc9-116">Oggetti server &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="02bc9-116">Server Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](server-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="02bc9-117">**Oggetti di database**</span><span class="sxs-lookup"><span data-stu-id="02bc9-117">**Database Objects**</span></span>  
 [<span data-ttu-id="02bc9-118">Oggetti di database &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="02bc9-118">Database Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](database-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="02bc9-119">**Oggetti Dimension**</span><span class="sxs-lookup"><span data-stu-id="02bc9-119">**Dimension Objects**</span></span>  
 [<span data-ttu-id="02bc9-120">Oggetti Dimension &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="02bc9-120">Dimension Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimension-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="02bc9-121">**Oggetti cubo**</span><span class="sxs-lookup"><span data-stu-id="02bc9-121">**Cube Objects**</span></span>  
 [<span data-ttu-id="02bc9-122">Oggetti Cube &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="02bc9-122">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="02bc9-123">**Sicurezza dall'accesso utente**</span><span class="sxs-lookup"><span data-stu-id="02bc9-123">**User Access Security**</span></span>  
 [<span data-ttu-id="02bc9-124">Architettura di sicurezza dall'accesso utente</span><span class="sxs-lookup"><span data-stu-id="02bc9-124">User Access Security Architecture</span></span>](understanding-microsoft-olap-logical-architecture.md)  
  
## <a name="see-also"></a><span data-ttu-id="02bc9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02bc9-125">See Also</span></span>  
 <span data-ttu-id="02bc9-126">[Informazioni sull'architettura Microsoft OLAP](../olap-physical/understanding-microsoft-olap-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="02bc9-126">[Understanding Microsoft OLAP Architecture](../olap-physical/understanding-microsoft-olap-architecture.md) </span></span>  
 [<span data-ttu-id="02bc9-127">Architettura fisica &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="02bc9-127">Physical Architecture &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../olap-physical/understanding-microsoft-olap-physical-architecture.md)  
  
  
