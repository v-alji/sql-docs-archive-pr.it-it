---
title: Gruppo di carico di lavoro di Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group
- workload groups [SQL Server]
- workload groups [SQL Server], overview
ms.assetid: a84c3c3f-55b6-4a30-9c42-13f082d9281e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c6fa8f6fe960571f10d6a8505329fbe8f400e6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715139"
---
# <a name="resource-governor-workload-group"></a><span data-ttu-id="2cfa6-102">Gruppo di carico di lavoro di Resource Governor</span><span class="sxs-lookup"><span data-stu-id="2cfa6-102">Resource Governor Workload Group</span></span>
  <span data-ttu-id="2cfa6-103">In Resource Governor in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] un gruppo di carico di lavoro viene utilizzato come contenitore per richieste di sessione che presentano criteri di classificazione simili.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-103">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resource Governor, a workload group serves as a container for session requests that have similar classification criteria.</span></span> <span data-ttu-id="2cfa6-104">Un carico di lavoro consente il monitoraggio complessivo delle sessioni e di definire i criteri per le sessioni.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-104">A workload allows for aggregate monitoring of the sessions, and defines policies for the sessions.</span></span> <span data-ttu-id="2cfa6-105">Ogni gruppo di carico di lavoro si trova in un pool di risorse che rappresenta un subset delle risorse fisiche di un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cfa6-105">Each workload group is in a resource pool, which represents a subset of the physical resources of an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="2cfa6-106">Una volta avviata, la sessione viene assegnata a un gruppo di carico di lavoro specifico tramite la funzione di classificazione di Resource Governor e deve essere eseguita utilizzando i criteri assegnati al gruppo di carico di lavoro e alle risorse definite per il pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-106">When a session is started, the Resource Governor classifier assigns the session to a specific workload group, and the session must run using the policies assigned to the workload group and the resources defined for the resource pool.</span></span>  
  
## <a name="workload-group-concepts"></a><span data-ttu-id="2cfa6-107">Concetti sui gruppi di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="2cfa6-107">Workload Group Concepts</span></span>  
 <span data-ttu-id="2cfa6-108">Un gruppo di carico di lavoro serve come contenitore per richieste di sessione simili tra loro, secondo i criteri di classificazione applicati a ciascuna richiesta.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-108">A workload group serves as a container for session requests that are similar according to the classification criteria that are applied to each request.</span></span> <span data-ttu-id="2cfa6-109">Un gruppo del carico di lavoro consente l'aggregazione del monitoraggio dell'utilizzo delle risorse e l'applicazione di criteri uniformi a tutte le richieste nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-109">A workload group allows the aggregate monitoring of resource consumption and the application of a uniform policy to all the requests in the group.</span></span> <span data-ttu-id="2cfa6-110">Un gruppo definisce i criteri per i propri membri.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-110">A group defines the policies for its members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2cfa6-111">È possibile spostare i gruppi del carico di lavoro definiti dall'utente da un pool di risorse all'altro.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-111">User-defined workload groups can be moved from one resource pool to another.</span></span>  
  
 <span data-ttu-id="2cfa6-112">In Resource Governor sono disponibili due gruppi del carico di lavoro, il gruppo interno e il gruppo predefinito.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-112">Resource Governor predefines two workload groups: the internal group and the default group.</span></span> <span data-ttu-id="2cfa6-113">Un utente non può modificare un gruppo classificato come gruppo interno, ma può monitorarlo.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-113">A user cannot change anything classified as an internal group, but can monitor it.</span></span> <span data-ttu-id="2cfa6-114">Le richieste vengono classificate nel gruppo predefinito quando si verificano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cfa6-114">Requests are classified into the default group when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="2cfa6-115">Non è presente alcun criterio per classificare una richiesta.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-115">There are no criteria to classify a request.</span></span>  
  
-   <span data-ttu-id="2cfa6-116">È stato eseguito un tentativo di classificare la richiesta in un gruppo inesistente.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-116">There is an attempt to classify the request into a non-existent group.</span></span>  
  
-   <span data-ttu-id="2cfa6-117">Si è verificato un errore di classificazione generale.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-117">There is a general classification failure.</span></span>  
  
 <span data-ttu-id="2cfa6-118">In Resource Governor sono inoltre disponibili istruzioni DDL per la creazione, la modifica e l'eliminazione dei gruppi di carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-118">Resource Governor also provides DDL statements for creating, changing, and dropping workload groups.</span></span>  
  
## <a name="workload-group-tasks"></a><span data-ttu-id="2cfa6-119">Attività del gruppo di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="2cfa6-119">Workload Group Tasks</span></span>  
  
|<span data-ttu-id="2cfa6-120">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="2cfa6-120">Task Description</span></span>|<span data-ttu-id="2cfa6-121">Argomento</span><span class="sxs-lookup"><span data-stu-id="2cfa6-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="2cfa6-122">Viene descritto come creare un gruppo di carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-122">Describes how to create a workload group.</span></span>|[<span data-ttu-id="2cfa6-123">Creare un gruppo di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="2cfa6-123">Create a Workload Group</span></span>](create-a-workload-group.md)|  
|<span data-ttu-id="2cfa6-124">Viene descritto come modificare le impostazioni di un gruppo di carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-124">Describes how to change workload group settings.</span></span>|[<span data-ttu-id="2cfa6-125">Modificare le impostazioni dei gruppi di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="2cfa6-125">Change Workload Group Settings</span></span>](change-workload-group-settings.md)|  
|<span data-ttu-id="2cfa6-126">Viene descritto come eliminare un gruppo di carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2cfa6-126">Describes how to delete a workload group.</span></span>|[<span data-ttu-id="2cfa6-127">Eliminare un gruppo di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="2cfa6-127">Delete a Workload Group</span></span>](delete-a-workload-group.md)|  
  
## <a name="see-also"></a><span data-ttu-id="2cfa6-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cfa6-128">See Also</span></span>  
 <span data-ttu-id="2cfa6-129">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2cfa6-129">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="2cfa6-130">[Abilitare Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2cfa6-130">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="2cfa6-131">[Pool di risorse di Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="2cfa6-131">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="2cfa6-132">[Funzione di classificazione di Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="2cfa6-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="2cfa6-133">[Configurare Resource Governor utilizzando un modello](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="2cfa6-133">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="2cfa6-134">Visualizzare proprietà di Resource Governor</span><span class="sxs-lookup"><span data-stu-id="2cfa6-134">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
