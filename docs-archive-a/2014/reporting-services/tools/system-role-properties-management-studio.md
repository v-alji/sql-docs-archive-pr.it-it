---
title: Proprietà ruolo a livello di sistema (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.systemroleproperties.f1
ms.assetid: 0210fc2a-74fb-41dd-8e39-4830047ec417
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b37ebb1cb95d6628884d81156c9c1bc29bff86fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625964"
---
# <a name="system-role-properties-management-studio"></a><span data-ttu-id="9aeee-102">Proprietà ruolo a livello di sistema (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9aeee-102">System Role Properties (Management Studio)</span></span>
  <span data-ttu-id="9aeee-103">La pagina Ruoli a livello di sistema consente di visualizzare le definizioni di ruolo a livello di sistema attualmente definite per il server di report.</span><span class="sxs-lookup"><span data-stu-id="9aeee-103">Use the System Roles page to view the system role definitions that are currently defined for the report server.</span></span> <span data-ttu-id="9aeee-104">Una definizione di ruolo a livello di sistema contiene una raccolta denominata di attività eseguite in relazione all'intero sito, anziché a un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="9aeee-104">A system role definition contains a named collection of tasks that are performed relative to the entire site, instead of an individual item.</span></span> <span data-ttu-id="9aeee-105">Le definizioni di ruolo vengono assegnate a un utente o a gruppi per creare un'assegnazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="9aeee-105">Role definitions are assigned to a user or groups to create a resulting role assignment.</span></span> <span data-ttu-id="9aeee-106">Le attività indicate nella definizione di ruolo specificano le operazioni consentite per un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="9aeee-106">The tasks in the role definition specify what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="9aeee-107">sono disponibili due definizioni di ruolo a livello di sistema predefinite, ovvero **Amministratore sistema** e **Utente sistema**.</span><span class="sxs-lookup"><span data-stu-id="9aeee-107">has two predefined system role definitions: **System Administrator** and **System User**.</span></span> <span data-ttu-id="9aeee-108">Tali definizioni di ruolo possono essere personalizzate modificando l'elenco di attività oppure è possibile creare nuovi ruoli a livello di sistema per supportare combinazioni di attività diverse.</span><span class="sxs-lookup"><span data-stu-id="9aeee-108">You can modify these role definitions by changing the task list, or you can create a new system role that supports a different combination of tasks.</span></span> <span data-ttu-id="9aeee-109">Le modifiche apportate a una definizione di ruolo vengono propagate a tutte le assegnazioni di ruolo che includono tale definizione.</span><span class="sxs-lookup"><span data-stu-id="9aeee-109">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9aeee-110">Le assegnazioni di ruolo a livello di sistema vengono utilizzate solo in un server di report in esecuzione in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="9aeee-110">System role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="9aeee-111">Se il server di report è configurato per l'integrazione con SharePoint, questa pagina non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="9aeee-111">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9aeee-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9aeee-112">Options</span></span>  
 <span data-ttu-id="9aeee-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9aeee-113">**Name**</span></span>  
 <span data-ttu-id="9aeee-114">Consente di specificare il nome della definizione di ruolo a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="9aeee-114">Specifies the name of the system role definition.</span></span>  
  
 <span data-ttu-id="9aeee-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9aeee-115">**Description**</span></span>  
 <span data-ttu-id="9aeee-116">Consente di visualizzare una descrizione della definizione di ruolo a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="9aeee-116">Shows a description of the system role definition.</span></span> <span data-ttu-id="9aeee-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] questa descrizione viene visualizzata solo in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="9aeee-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="9aeee-118">Gli utenti che visualizzano questo elemento tramite Gestione report potrebbero vedere questa descrizione durante l'esplorazione della gerarchia di cartelle.</span><span class="sxs-lookup"><span data-stu-id="9aeee-118">Users who view this item through Report Manager may see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="9aeee-119">**Attività**</span><span class="sxs-lookup"><span data-stu-id="9aeee-119">**Task**</span></span>  
 <span data-ttu-id="9aeee-120">Elenca tutte le attività di sistema che è possibile selezionare per la definizione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="9aeee-120">Lists all system-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="9aeee-121">È possibile aggiungere o rimuovere elementi dall'elenco di attività predefinite per specificare il modo in cui gli utenti accedono a un determinato elemento tramite questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="9aeee-121">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="9aeee-122">Non è possibile creare nuove attività, né modificare quelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="9aeee-122">You cannot create new tasks, and you cannot modify existing tasks.</span></span>  
  
 <span data-ttu-id="9aeee-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9aeee-123">**Description**</span></span>  
 <span data-ttu-id="9aeee-124">Offre informazioni su ogni attività.</span><span class="sxs-lookup"><span data-stu-id="9aeee-124">Provides information about each task.</span></span> <span data-ttu-id="9aeee-125">Non è possibile modificare le descrizioni delle attività.</span><span class="sxs-lookup"><span data-stu-id="9aeee-125">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aeee-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9aeee-126">See Also</span></span>  
 <span data-ttu-id="9aeee-127">[Guida sensibile al contesto del server di report in Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="9aeee-127">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="9aeee-128">[Attività a livello di sistema](../security/tasks-and-permissions-system-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="9aeee-128">[System-Level Tasks](../security/tasks-and-permissions-system-level-tasks.md) </span></span>  
 <span data-ttu-id="9aeee-129">[Attività e autorizzazioni](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="9aeee-129">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="9aeee-130">Predefined Roles</span><span class="sxs-lookup"><span data-stu-id="9aeee-130">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
