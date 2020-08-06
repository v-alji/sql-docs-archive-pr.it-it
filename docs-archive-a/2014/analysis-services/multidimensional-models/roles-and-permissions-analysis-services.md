---
title: Ruoli e autorizzazioni (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], about security
- security [Analysis Services - multidimensional data], about security
ms.assetid: bb885447-868b-4686-853c-8241f63d4370
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6595d931b2c2760e5fd3013ff6bec88f85106d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727223"
---
# <a name="roles-and-permissions-analysis-services"></a><span data-ttu-id="9a9c5-102">Ruoli e autorizzazioni (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="9a9c5-102">Roles and Permissions (Analysis Services)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="9a9c5-103">fornisce il modello di autorizzazione basata sui ruoli che concede l'accesso a operazioni, oggetti e dati.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-103">provides a role-based authorization model that grants access to operations, objects, and data.</span></span> <span data-ttu-id="9a9c5-104">È necessario che tutti gli utenti che accedono a un database o un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] si attengano a questa procedura all'interno del contesto di un ruolo.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-104">All users who access an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance or database must do so within the context of a role.</span></span>  
  
 <span data-ttu-id="9a9c5-105">L'amministratore di sistema di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] può concedere l'appartenenza al **ruolo di amministratore del server** che fornisce l'accesso illimitato alle operazioni sul server.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-105">As an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] system administrator, you are in charge of granting membership to the **server administrator role** that conveys unrestricted access to operations on the server.</span></span> <span data-ttu-id="9a9c5-106">Le autorizzazioni di questo ruolo sono fisse e non possono essere personalizzate.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-106">This role has fixed permissions and cannot be customized.</span></span> <span data-ttu-id="9a9c5-107">Per impostazione predefinita, i membri del gruppo Administrators locale sono automaticamente amministratori di sistema di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-107">By default, members of the local Administrators group are automatically Analysis Services system administrators.</span></span>  
  
 <span data-ttu-id="9a9c5-108">Agli utenti non amministratori che elaborano o eseguono query sui dati, l'accesso viene concesso tramite i **ruoli di database**.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-108">Non-administrative users who query or process data are granted access through **database roles**.</span></span> <span data-ttu-id="9a9c5-109">Gli amministratori di sistema e di database possono creare i ruoli che descrivono i diversi livelli di accesso all'interno di un database e quindi assegnare l'appartenenza a ogni utente che richiede l'accesso.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-109">Both system administrators and database administrators can create the roles that describe different levels of access within a given database, and then assign membership to every user who requires access.</span></span> <span data-ttu-id="9a9c5-110">Ogni ruolo dispone di un set di autorizzazioni personalizzato per l'accesso a oggetti e operazioni all'interno di un database specifico.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-110">Each role has a customized set of permissions for accessing objects and operations within a particular database.</span></span> <span data-ttu-id="9a9c5-111">È possibile assegnare le autorizzazioni a livello di database, di oggetti interni quali cubi e dimensioni (ma non prospettive) e di righe.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-111">You can assign permissions at these levels: database, interior objects such as cubes and dimensions (but not perspectives), and rows.</span></span>  
  
 <span data-ttu-id="9a9c5-112">È pratica comune creare i ruoli e assegnare l'appartenenza con operazioni separate.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-112">It is common practice to create roles and assign membership as separate operations.</span></span> <span data-ttu-id="9a9c5-113">Spesso, Progettazione modelli aggiunge i ruoli durante la fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-113">Often, the model designer adds roles during the design phase.</span></span> <span data-ttu-id="9a9c5-114">In questo modo, tutte le definizioni di ruolo vengono riflesse nei file di progetto che definiscono il modello.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-114">This way, all role definitions are reflected in the project files that define the model.</span></span> <span data-ttu-id="9a9c5-115">L'appartenenza al ruolo viene in genere implementata in un secondo momento quando il database passa in produzione, generalmente dagli amministratori del database che creano script che possono essere sviluppati, testati ed eseguiti come un'operazione indipendente.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-115">Role membership is typically rolled out later as the database moves into production, usually by database administrators who create scripts that can be developed, tested, and run as an independent operation.</span></span>  
  
 <span data-ttu-id="9a9c5-116">Ogni autorizzazione viene concessa su un'identità utente di Windows valida.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-116">All authorization is predicated on a valid Windows user identity.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="9a9c5-117">usa l'autenticazione di Windows esclusivamente per autenticare le identità utente.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-117">uses Windows authentication exclusively to authenticate user identities.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="9a9c5-118">non fornisce alcun metodo di autenticazione proprietario. Vedere le [metodologie di autenticazione supportate da Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a9c5-118">provides no proprietary authentication method.See [Authentication methodologies supported by Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9a9c5-119">Le autorizzazioni si sommano tra loro per ogni utente o gruppo di Windows in tutti i ruoli del database.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-119">Permissions are additive for each Windows user or group, across all roles in the database.</span></span> <span data-ttu-id="9a9c5-120">Se un ruolo nega a un utente o a un gruppo le autorizzazioni per eseguire determinate attività o per visualizzare determinati dati, mentre un altro ruolo concede a tale utente o gruppo queste autorizzazioni, l'utente o il gruppo disporrà delle autorizzazioni per eseguire l'attività o visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="9a9c5-120">If one role denies a user or group permission to perform certain tasks or view certain data, but another role grants this permission to that user or group, the user or group will have permission to perform the task or view the data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a9c5-121">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9a9c5-121">In this section</span></span>  
  
-   [<span data-ttu-id="9a9c5-122">Autorizzazione dell'accesso a oggetti e operazioni &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-122">Authorizing access to objects and operations &#40;Analysis Services&#41;</span></span>](authorizing-access-to-objects-and-operations-analysis-services.md)  
  
-   [<span data-ttu-id="9a9c5-123">Concedere le autorizzazioni per il database &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-123">Grant database permissions &#40;Analysis Services&#41;</span></span>](grant-database-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="9a9c5-124">Concedere le autorizzazioni per un cubo o un modello &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-124">Grant cube or model permissions &#40;Analysis Services&#41;</span></span>](grant-cube-or-model-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="9a9c5-125">Concedere le autorizzazioni di elaborazione &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-125">Grant process permissions &#40;Analysis Services&#41;</span></span>](grant-process-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="9a9c5-126">Concedere le autorizzazioni di lettura definizione per i metadati degli oggetti &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-126">Grant read definition permissions on object metadata &#40;Analysis Services&#41;</span></span>](grant-read-definition-permissions-on-object-metadata-analysis-services.md)  
  
-   [<span data-ttu-id="9a9c5-127">Concedere le autorizzazioni per un oggetto origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-127">Grant permissions on a data source object &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-data-source-object-analysis-services.md)  
  
-   [<span data-ttu-id="9a9c5-128">Concedere le autorizzazioni per le strutture e i modelli di data mining &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-128">Grant permissions on data mining structures and models &#40;Analysis Services&#41;</span></span>](grant-permissions-on-data-mining-structures-and-models-analysis-services.md)  
  
-   [<span data-ttu-id="9a9c5-129">Concedere le autorizzazioni per una dimensione &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-129">Grant permissions on a dimension &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-dimension-analysis-services.md)  
  
-   [<span data-ttu-id="9a9c5-130">Concedere l'accesso personalizzato ai dati della dimensione &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-130">Grant custom access to dimension data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-dimension-data-analysis-services.md)  
  
-   [<span data-ttu-id="9a9c5-131">Concedere l'accesso personalizzato ai dati delle celle &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-131">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a9c5-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a9c5-132">See Also</span></span>  
 [<span data-ttu-id="9a9c5-133">Creare e gestire ruoli &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="9a9c5-133">Create and Manage Roles &#40;SSAS Tabular&#41;</span></span>](../tabular-models/roles-ssas-tabular.md)  
  
  
