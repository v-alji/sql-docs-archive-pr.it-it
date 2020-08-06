---
title: Proprietà ruolo utente (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.userroleproperties.f1
ms.assetid: c8b22236-a8b1-4e15-b1ff-4e1909b602d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f79953abdf5e3d1cdb03de8c5feeb6b2de34ab7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715996"
---
# <a name="user-role-properties-management-studio"></a><span data-ttu-id="ba109-102">Proprietà ruolo utente (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ba109-102">User Role Properties (Management Studio)</span></span>
  <span data-ttu-id="ba109-103">Questa pagina consente di visualizzare le attività incluse in una definizione di ruolo a livello di elemento.</span><span class="sxs-lookup"><span data-stu-id="ba109-103">Use this page to view which tasks are included in an item-level role definition.</span></span> <span data-ttu-id="ba109-104">La pagina consente inoltre di modificare l'elenco di attività o una descrizione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="ba109-104">You can also use this page to change the task list or modify a role description.</span></span>  
  
 <span data-ttu-id="ba109-105">Una definizione di ruolo a livello di elemento è una raccolta denominata di attività che possono essere eseguite dagli utenti in relazione a un elemento specifico, ovvero una cartella, un report, una risorsa o un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="ba109-105">An item-level role definition is a named collection of tasks that users perform relative to a specific item (that is, a folder, report, resource, or shared data source).</span></span> <span data-ttu-id="ba109-106">Le definizioni di ruolo vengono assegnate a un utente o a un gruppo per creare un'assegnazione di ruolo in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="ba109-106">Role definitions are assigned to a user or group to create a role assignment in Report Manager.</span></span> <span data-ttu-id="ba109-107">Le attività incluse nella definizione di ruolo indicano le operazioni consentite per un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="ba109-107">The tasks in the role definition describe what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="ba109-108">Reporting Services include varie definizioni di ruolo a livello di elemento predefinite, pronte per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="ba109-108">includes a number of predefined item-level role definitions that you can work with.</span></span> <span data-ttu-id="ba109-109">È possibile modificare le definizioni di ruolo modificando l'elenco di attività di ogni definizione.</span><span class="sxs-lookup"><span data-stu-id="ba109-109">You can modify the role definitions by changing the task list of each one.</span></span> <span data-ttu-id="ba109-110">Le modifiche apportate a una definizione di ruolo vengono propagate a tutte le assegnazioni di ruolo che includono tale definizione.</span><span class="sxs-lookup"><span data-stu-id="ba109-110">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba109-111">Le assegnazioni di ruolo a livello di utente vengono utilizzate solo in un server di report in esecuzione in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="ba109-111">User role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="ba109-112">Se il server di report è configurato per l'integrazione con SharePoint, in questa pagina vengono visualizzate informazioni di sola lettura sui ruoli e sui livelli di autorizzazione definiti nel sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ba109-112">If the report server is configured for SharePoint integration, this page displays read-only information about the roles and permission levels that are defined on the SharePoint site.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba109-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ba109-113">Options</span></span>  
 <span data-ttu-id="ba109-114">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ba109-114">**Name**</span></span>  
 <span data-ttu-id="ba109-115">Consente di specificare il nome della definizione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="ba109-115">Specifies the name of the role definition.</span></span>  
  
 <span data-ttu-id="ba109-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ba109-116">**Description**</span></span>  
 <span data-ttu-id="ba109-117">Consente di visualizzare una descrizione della definizione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="ba109-117">Shows a description of the role definition.</span></span> <span data-ttu-id="ba109-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]questa descrizione viene visualizzata solo in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="ba109-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="ba109-119">In Gestione report questa descrizione aiuta gli utenti a stabilire se utilizzare il ruolo in un'assegnazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="ba109-119">In Report Manager, this description helps users decide whether to use the role in a role assignment.</span></span>  
  
 <span data-ttu-id="ba109-120">**Attività**</span><span class="sxs-lookup"><span data-stu-id="ba109-120">**Task**</span></span>  
 <span data-ttu-id="ba109-121">Consente di visualizzare l'elenco di tutte le attività a livello di elemento che possono essere selezionate per la definizione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="ba109-121">Lists all item-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="ba109-122">È possibile aggiungere o rimuovere elementi dall'elenco di attività predefinite per specificare il modo in cui gli utenti accedono a un determinato elemento tramite questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="ba109-122">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="ba109-123">Non è possibile creare nuove attività, né modificare quelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="ba109-123">You cannot create new tasks, and you cannot modify existing tasks.</span></span> <span data-ttu-id="ba109-124">L'elenco di attività di una definizione di ruolo viene visualizzato solo in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba109-124">The task list of a role definition appears only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ba109-125">**Descrizione dell'attività**</span><span class="sxs-lookup"><span data-stu-id="ba109-125">**Task Description**</span></span>  
 <span data-ttu-id="ba109-126">Offre informazioni su ogni attività.</span><span class="sxs-lookup"><span data-stu-id="ba109-126">Provides information about each task.</span></span> <span data-ttu-id="ba109-127">Non è possibile modificare le descrizioni delle attività.</span><span class="sxs-lookup"><span data-stu-id="ba109-127">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba109-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba109-128">See Also</span></span>  
 <span data-ttu-id="ba109-129">[Attività a livello di elemento](../security/tasks-and-permissions-item-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="ba109-129">[Item-Level Tasks](../security/tasks-and-permissions-item-level-tasks.md) </span></span>  
 <span data-ttu-id="ba109-130">[Definizioni di ruolo](../security/role-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="ba109-130">[Role Definitions](../security/role-definitions.md) </span></span>  
 <span data-ttu-id="ba109-131">[Guida sensibile al contesto del server di report in Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="ba109-131">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="ba109-132">[Attività e autorizzazioni](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="ba109-132">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="ba109-133">Predefined Roles</span><span class="sxs-lookup"><span data-stu-id="ba109-133">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
