---
title: Funzionalità disattivate per impostazione predefinita (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9529edf-337e-4fdd-9a13-99cfe96b4fa1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87752b8760ffc80e80c87ac1132cae36f2f151b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714744"
---
# <a name="features-off-by-default-analysis-services"></a><span data-ttu-id="767de-102">Funzionalità disabilitate per impostazione predefinita (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="767de-102">Features off by default (Analysis Services)</span></span>
  <span data-ttu-id="767de-103">Un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] è progettata per garantire sicurezza per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="767de-103">An instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is designed to be secure by default.</span></span> <span data-ttu-id="767de-104">Le funzionalità che potrebbero mettere a repentaglio la sicurezza sono pertanto disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="767de-104">Therefore, features that might compromise security are disabled by default.</span></span> <span data-ttu-id="767de-105">Le funzionalità seguenti sono installate in stato disabilitato e devono essere abilitate specificamente se si desidera usarle.</span><span class="sxs-lookup"><span data-stu-id="767de-105">The following features are installed in a disabled state and must specifically be enabled if you want to use them.</span></span>  
  
## <a name="feature-list"></a><span data-ttu-id="767de-106">Elenco di funzionalità</span><span class="sxs-lookup"><span data-stu-id="767de-106">Feature List</span></span>  
 <span data-ttu-id="767de-107">Per abilitare le funzionalità seguenti, connettersi a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="767de-107">To enable the following features, connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="767de-108">Fare clic con il pulsante destro del mouse sul nome dell'istanza e scegliere **Facet**.</span><span class="sxs-lookup"><span data-stu-id="767de-108">Right-click the instance name and choose **Facets**.</span></span> <span data-ttu-id="767de-109">In alternativa, è possibile abilitare queste funzionalità tramite le proprietà del server, come illustrato nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="767de-109">Alternatively, you can enable these features through server properties, as described in the next section.</span></span>  
  
-   <span data-ttu-id="767de-110">Query di data mining ad hoc (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="767de-110">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="767de-111">Oggetti collegati (a)</span><span class="sxs-lookup"><span data-stu-id="767de-111">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="767de-112">Oggetti collegati (da)</span><span class="sxs-lookup"><span data-stu-id="767de-112">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="767de-113">Ascolto solo su connessioni locali</span><span class="sxs-lookup"><span data-stu-id="767de-113">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="767de-114">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="767de-114">User Defined Functions</span></span>  
  
## <a name="server-properties"></a><span data-ttu-id="767de-115">Proprietà del server</span><span class="sxs-lookup"><span data-stu-id="767de-115">Server properties</span></span>  
 <span data-ttu-id="767de-116">Le funzionalità aggiuntive disattivate per impostazione predefinita possono essere abilitate tramite le proprietà del server.</span><span class="sxs-lookup"><span data-stu-id="767de-116">Additional features that are off by default can be enabled through server properties.</span></span> <span data-ttu-id="767de-117">Connettersi a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="767de-117">Connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="767de-118">Fare clic con il pulsante destro del mouse sul nome dell'istanza e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="767de-118">Right-click the instance name and choose **Properties**.</span></span> <span data-ttu-id="767de-119">Fare clic su **Generale**, quindi su **Mostra avanzate** per visualizzare un elenco più ampio di proprietà.</span><span class="sxs-lookup"><span data-stu-id="767de-119">Click **General**, and then click **Show Advanced** to display a larger property list.</span></span>  
  
-   <span data-ttu-id="767de-120">Query di data mining ad hoc (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="767de-120">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="767de-121">Consenti modelli di data mining di sessione (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="767de-121">Allow Session Mining Models (Data Mining)</span></span>  
  
-   <span data-ttu-id="767de-122">Oggetti collegati (a)</span><span class="sxs-lookup"><span data-stu-id="767de-122">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="767de-123">Oggetti collegati (da)</span><span class="sxs-lookup"><span data-stu-id="767de-123">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="767de-124">Funzioni definite dall'utente basate su COM</span><span class="sxs-lookup"><span data-stu-id="767de-124">COM based user-defined functions</span></span>  
  
-   <span data-ttu-id="767de-125">Definizioni di traccia Flight Recorder (modelli).</span><span class="sxs-lookup"><span data-stu-id="767de-125">Flight Recorder Trace Definitions (templates).</span></span>  
  
-   <span data-ttu-id="767de-126">Registrazione query</span><span class="sxs-lookup"><span data-stu-id="767de-126">Query logging</span></span>  
  
-   <span data-ttu-id="767de-127">Ascolto solo su connessioni locali</span><span class="sxs-lookup"><span data-stu-id="767de-127">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="767de-128">XML binario</span><span class="sxs-lookup"><span data-stu-id="767de-128">Binary XML</span></span>  
  
-   <span data-ttu-id="767de-129">Compressione</span><span class="sxs-lookup"><span data-stu-id="767de-129">Compression</span></span>  
  
-   <span data-ttu-id="767de-130">Affinità gruppo.</span><span class="sxs-lookup"><span data-stu-id="767de-130">Group affinity.</span></span> <span data-ttu-id="767de-131">Per informazioni dettagliate, vedere [Thread Pool Properties](../server-properties/thread-pool-properties.md) .</span><span class="sxs-lookup"><span data-stu-id="767de-131">See [Thread Pool Properties](../server-properties/thread-pool-properties.md) for details.</span></span>  
  
  
