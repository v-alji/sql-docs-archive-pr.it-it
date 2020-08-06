---
title: Attività a livello di sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- system-level tasks [Reporting Services]
ms.assetid: 7023b388-40b2-4590-b227-115cf380a1e7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98f9390664064cd293b80d094d65c903869bc709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723335"
---
# <a name="system-level-tasks"></a><span data-ttu-id="2d72f-102">Attività a livello di sistema</span><span class="sxs-lookup"><span data-stu-id="2d72f-102">System-Level Tasks</span></span>
  <span data-ttu-id="2d72f-103">Un'attività a livello di sistema è una raccolta di autorizzazioni correlate alle operazioni eseguibili per l'intero sito del server di report.</span><span class="sxs-lookup"><span data-stu-id="2d72f-103">A system-level task is a collection of permissions that relate to operations that apply to the report server site as a whole.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2d72f-104">include anche attività a livello di elemento applicabili a elementi specifici.</span><span class="sxs-lookup"><span data-stu-id="2d72f-104">also includes item-level tasks that apply to specific items.</span></span> <span data-ttu-id="2d72f-105">Per altre informazioni, vedere [Attività a livello di elemento](tasks-and-permissions-item-level-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="2d72f-105">For more information, see [Item-Level Tasks](tasks-and-permissions-item-level-tasks.md).</span></span> <span data-ttu-id="2d72f-106">Per ulteriori informazioni sulle attività e le autorizzazioni in generale, vedere [Tasks and Permissions](tasks-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2d72f-106">For more information about tasks and permissions in general, see [Tasks and Permissions](tasks-and-permissions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d72f-107">Se si gestiscono queste attività a livello di programmazione, è necessario utilizzare metodi che supportano attività a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="2d72f-107">If you are working with these tasks programmatically, you must use methods that support system-level tasks.</span></span> <span data-ttu-id="2d72f-108">Per altre informazioni, vedere <xref:ReportService2010.ReportingService2010.ListTasks%2A> e <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d72f-108">For more information, see <xref:ReportService2010.ReportingService2010.ListTasks%2A> and <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span></span>  
  
## <a name="permissions-in-system-level-tasks"></a><span data-ttu-id="2d72f-109">Autorizzazioni nelle attività a livello di sistema</span><span class="sxs-lookup"><span data-stu-id="2d72f-109">Permissions in System-Level Tasks</span></span>  
 <span data-ttu-id="2d72f-110">Nella tabella seguente vengono indicate le autorizzazioni per ogni attività a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="2d72f-110">The following table identifies the collection of permissions for each system task.</span></span> <span data-ttu-id="2d72f-111">L'elenco delle autorizzazioni è puramente informativo e ha lo scopo di fornire una descrizione precisa delle funzionalità disponibili tramite ogni attività.</span><span class="sxs-lookup"><span data-stu-id="2d72f-111">Permissions are listed for informational purposes only, to provide a more exact description of the functionality available through each task.</span></span>  
  
|<span data-ttu-id="2d72f-112">Attività</span><span class="sxs-lookup"><span data-stu-id="2d72f-112">Task</span></span>|<span data-ttu-id="2d72f-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2d72f-113">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2d72f-114">Esecuzione delle definizioni dei report</span><span class="sxs-lookup"><span data-stu-id="2d72f-114">Execute report definitions</span></span>|<span data-ttu-id="2d72f-115">Esecuzione delle definizioni dei report (il nome dell'autorizzazione e il nome dell'attività sono identici)</span><span class="sxs-lookup"><span data-stu-id="2d72f-115">Execute Report Definitions (the permission and task name are the same)</span></span>|  
|<span data-ttu-id="2d72f-116">Generare eventi</span><span class="sxs-lookup"><span data-stu-id="2d72f-116">Generate events</span></span>|<span data-ttu-id="2d72f-117">Generazione di eventi</span><span class="sxs-lookup"><span data-stu-id="2d72f-117">Generate Events</span></span>|  
|<span data-ttu-id="2d72f-118">Gestire i processi</span><span class="sxs-lookup"><span data-stu-id="2d72f-118">Manage jobs</span></span>|<span data-ttu-id="2d72f-119">Lettura delle proprietà di sistema</span><span class="sxs-lookup"><span data-stu-id="2d72f-119">Read System Properties</span></span><br /><br /> <span data-ttu-id="2d72f-120">Aggiornamento delle proprietà di sistema</span><span class="sxs-lookup"><span data-stu-id="2d72f-120">Update System Properties</span></span>|  
|<span data-ttu-id="2d72f-121">Gestione delle proprietà del server di report</span><span class="sxs-lookup"><span data-stu-id="2d72f-121">Manage report server properties</span></span>|<span data-ttu-id="2d72f-122">Lettura delle proprietà di sistema</span><span class="sxs-lookup"><span data-stu-id="2d72f-122">Read System Properties</span></span><br /><br /> <span data-ttu-id="2d72f-123">Aggiornamento delle proprietà di sistema</span><span class="sxs-lookup"><span data-stu-id="2d72f-123">Update System Properties</span></span>|  
|<span data-ttu-id="2d72f-124">Gestire i ruoli</span><span class="sxs-lookup"><span data-stu-id="2d72f-124">Manage roles</span></span>|<span data-ttu-id="2d72f-125">Creazione di ruoli</span><span class="sxs-lookup"><span data-stu-id="2d72f-125">Create Roles</span></span><br /><br /> <span data-ttu-id="2d72f-126">Eliminazione di ruoli</span><span class="sxs-lookup"><span data-stu-id="2d72f-126">Delete Roles</span></span><br /><br /> <span data-ttu-id="2d72f-127">Lettura delle proprietà di ruolo</span><span class="sxs-lookup"><span data-stu-id="2d72f-127">Read Role Properties</span></span><br /><br /> <span data-ttu-id="2d72f-128">Aggiornamento delle proprietà di ruolo</span><span class="sxs-lookup"><span data-stu-id="2d72f-128">Update Role Properties</span></span>|  
|<span data-ttu-id="2d72f-129">Gestione di pianificazioni condivise</span><span class="sxs-lookup"><span data-stu-id="2d72f-129">Manage shared schedules</span></span>|<span data-ttu-id="2d72f-130">Creazione di pianificazioni</span><span class="sxs-lookup"><span data-stu-id="2d72f-130">Create Schedules</span></span>|  
|<span data-ttu-id="2d72f-131">Gestione della sicurezza del server di report</span><span class="sxs-lookup"><span data-stu-id="2d72f-131">Manage report server security</span></span>|<span data-ttu-id="2d72f-132">Lettura dei criteri di sicurezza del sistema</span><span class="sxs-lookup"><span data-stu-id="2d72f-132">Read System Security Policies</span></span><br /><br /> <span data-ttu-id="2d72f-133">Aggiornamento dei criteri di sicurezza del sistema</span><span class="sxs-lookup"><span data-stu-id="2d72f-133">Update System Security Policies</span></span>|  
|<span data-ttu-id="2d72f-134">Visualizzazione delle proprietà del server di report</span><span class="sxs-lookup"><span data-stu-id="2d72f-134">View report server properties</span></span>|<span data-ttu-id="2d72f-135">Lettura delle proprietà di sistema</span><span class="sxs-lookup"><span data-stu-id="2d72f-135">Read System Properties</span></span>|  
|<span data-ttu-id="2d72f-136">Visualizzazione di pianificazioni condivise</span><span class="sxs-lookup"><span data-stu-id="2d72f-136">View shared schedules</span></span>|<span data-ttu-id="2d72f-137">Lettura di pianificazioni</span><span class="sxs-lookup"><span data-stu-id="2d72f-137">Read Schedules</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d72f-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d72f-138">See Also</span></span>  
 [<span data-ttu-id="2d72f-139">Concessione di autorizzazioni in un server di report in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="2d72f-139">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
