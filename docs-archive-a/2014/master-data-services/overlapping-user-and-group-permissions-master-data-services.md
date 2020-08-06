---
title: Autorizzazioni utenti e gruppi sovrapposte (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services], resolving permissions
- permissions [Master Data Services], user and group overlaps
- groups [Master Data Services], resolving permissions
ms.assetid: 31c3cf7d-17d4-4474-b6a7-ffcb9fc45b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7044bf6260170cbc598719ec204ddb6f861f6301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714460"
---
# <a name="overlapping-user-and-group-permissions-master-data-services"></a><span data-ttu-id="2c55b-102">Autorizzazioni utenti e gruppi sovrapposte (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2c55b-102">Overlapping User and Group Permissions (Master Data Services)</span></span>
  <span data-ttu-id="2c55b-103">Le autorizzazioni di un utente si basano su:</span><span class="sxs-lookup"><span data-stu-id="2c55b-103">A user's permissions are based on:</span></span>  
  
-   <span data-ttu-id="2c55b-104">Autorizzazioni ereditate dalle appartenenze a gruppi.</span><span class="sxs-lookup"><span data-stu-id="2c55b-104">Permissions from group memberships.</span></span>  
  
-   <span data-ttu-id="2c55b-105">Autorizzazioni assegnate in modo esplicito all'utente.</span><span class="sxs-lookup"><span data-stu-id="2c55b-105">Permissions assigned explicitly to the user.</span></span>  
  
 <span data-ttu-id="2c55b-106">Se un utente è un membro di più gruppi e questi gruppi dispongono dell'accesso a Gestione dati master, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c55b-106">If a user is a member of multiple groups, and those groups have access to Master Data Manager, the following rules apply:</span></span>  
  
-   <span data-ttu-id="2c55b-107">**Nega** esegue l'override di tutte le altre autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2c55b-107">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="2c55b-108">**Aggiornamento** esegue l'override **di sola lettura**.</span><span class="sxs-lookup"><span data-stu-id="2c55b-108">**Update** overrides **Read-only**.</span></span>  
  
 <span data-ttu-id="2c55b-109">Queste regole si applicano a entrambe le schede **Modelli** e **Membri gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="2c55b-109">These rules apply to both the **Models** and **Hierarchy Members** tabs.</span></span> <span data-ttu-id="2c55b-110">Le autorizzazioni vengono risolte per ogni scheda e quindi combinate.</span><span class="sxs-lookup"><span data-stu-id="2c55b-110">Permissions are resolved for each tab and then combined.</span></span> <span data-ttu-id="2c55b-111">Per altre informazioni, vedere [Modalità di determinazione delle autorizzazioni &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2c55b-111">For more information, see [How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c55b-112">Nell'interfaccia utente è possibile visualizzare la risoluzione delle autorizzazioni di utenti e gruppi sovrapposte.</span><span class="sxs-lookup"><span data-stu-id="2c55b-112">You can view the resolution of user and group overlapping permissions in the user interface.</span></span> <span data-ttu-id="2c55b-113">Nelle schede **Modelli** e **Membri gerarchia** è presente un elenco a discesa da cui è possibile scegliere **Valide** per visualizzare le autorizzazioni valide.</span><span class="sxs-lookup"><span data-stu-id="2c55b-113">Both the **Models** and **Hierarchy Members** tab have a drop-down list from which you can choose **Effective** to view effective permissions.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="2c55b-114">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="2c55b-114">Example 1</span></span>  
 <span data-ttu-id="2c55b-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span><span class="sxs-lookup"><span data-stu-id="2c55b-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span></span>  
  
 <span data-ttu-id="2c55b-116">L'utente appartiene al Gruppo 1 e al Gruppo 2.</span><span class="sxs-lookup"><span data-stu-id="2c55b-116">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="2c55b-117">L'utente dispone delle autorizzazioni di sola **lettura** per l'entità Product.</span><span class="sxs-lookup"><span data-stu-id="2c55b-117">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="2c55b-118">Il gruppo 1 ha l'autorizzazione **Update** per l'entità Product.</span><span class="sxs-lookup"><span data-stu-id="2c55b-118">Group 1 has **Update** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="2c55b-119">Il gruppo 2 dispone dell'autorizzazione di sola **lettura** per l'entità Product.</span><span class="sxs-lookup"><span data-stu-id="2c55b-119">Group 2 has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="2c55b-120">Risultato: l'autorizzazione valida dell'utente è **Update** per l'entità Product.</span><span class="sxs-lookup"><span data-stu-id="2c55b-120">Result: The user's effective permission is **Update** to the Product entity.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="2c55b-121">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="2c55b-121">Example 2</span></span>  
 <span data-ttu-id="2c55b-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span><span class="sxs-lookup"><span data-stu-id="2c55b-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span></span>  
  
 <span data-ttu-id="2c55b-123">L'utente appartiene al Gruppo 1 e al Gruppo 2.</span><span class="sxs-lookup"><span data-stu-id="2c55b-123">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="2c55b-124">L'utente dispone delle autorizzazioni di sola **lettura** per l'entità Product.</span><span class="sxs-lookup"><span data-stu-id="2c55b-124">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="2c55b-125">Il gruppo 1 ha l'autorizzazione **Update** per l'entità Product.</span><span class="sxs-lookup"><span data-stu-id="2c55b-125">Group 1 has **Update** permission to Product entity.</span></span>  
  
 <span data-ttu-id="2c55b-126">Il gruppo 2 ha l'autorizzazione **Deny** per l'entità Product.</span><span class="sxs-lookup"><span data-stu-id="2c55b-126">Group 2 has **Deny** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="2c55b-127">Risultato: l'autorizzazione valida dell'utente è **Deny** per l'entità Product.</span><span class="sxs-lookup"><span data-stu-id="2c55b-127">Result: The user's effective permission is **Deny** to the Product entity.</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="2c55b-128">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="2c55b-128">Example 3</span></span>  
 <span data-ttu-id="2c55b-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span><span class="sxs-lookup"><span data-stu-id="2c55b-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span></span>  
  
 <span data-ttu-id="2c55b-130">L'utente appartiene al Gruppo 1 e al Gruppo 2.</span><span class="sxs-lookup"><span data-stu-id="2c55b-130">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="2c55b-131">L'utente dispone dell'autorizzazione **Update** per un gruppo di membri in un nodo gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2c55b-131">The user has **Update** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="2c55b-132">Il gruppo 1 dispone dell'autorizzazione di sola **lettura** per un gruppo di membri in un nodo della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2c55b-132">Group 1 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="2c55b-133">Il gruppo 2 dispone dell'autorizzazione di sola **lettura** per un gruppo di membri in un nodo della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2c55b-133">Group 2 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="2c55b-134">Risultato: l'autorizzazione utente valida è **Update** per i membri.</span><span class="sxs-lookup"><span data-stu-id="2c55b-134">Result: The user's effective permission is **Update** to the members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c55b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c55b-135">See Also</span></span>  
 <span data-ttu-id="2c55b-136">[Modalità di determinazione delle autorizzazioni &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2c55b-136">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="2c55b-137">Autorizzazioni per modelli e membri sovrapposte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2c55b-137">Overlapping Model and Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)  
  
  
