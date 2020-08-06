---
title: 'Pagina nuova assegnazione ruolo a sistema: modifica assegnazioni ruolo a sistema (Gestione report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 62a22ab9-1eb4-4ce5-8dd7-06b5ed2d9a2a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e04ec18b8ee27c5897156753c1e4f7991991eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625206"
---
# <a name="new-system-role-assignments-edit-system-role-assignments-page-report-manager"></a><span data-ttu-id="30d69-102">Pagina Nuova assegnazione ruolo a livello di sistema: Modifica assegnazioni ruolo a livello di sistema (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="30d69-102">New System Role Assignments: Edit System Role Assignments Page (Report Manager)</span></span>
  <span data-ttu-id="30d69-103">La pagina Nuova assegnazione ruolo a livello di sistema o Modifica assegnazioni ruolo a livello di sistema consente di impostare la sicurezza per il server di report.</span><span class="sxs-lookup"><span data-stu-id="30d69-103">Use the New System Role Assignments or Edit System Role Assignments page to define security for the report server.</span></span> <span data-ttu-id="30d69-104">Il sistema di sicurezza è interamente basato sulle assegnazioni di ruolo, tramite le quali utenti o gruppi specifici vengono mappati alle attività che possono eseguire.</span><span class="sxs-lookup"><span data-stu-id="30d69-104">All security is defined through role assignments that map specific users or groups to the tasks that they can perform.</span></span> <span data-ttu-id="30d69-105">L'elenco di attività è rappresentato in forma di definizione di ruolo selezionabile per la creazione dell'assegnazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="30d69-105">The task list is represented as a role definition that you select when making the role assignment.</span></span>  
  
 <span data-ttu-id="30d69-106">A livello di sistema, le assegnazioni di ruolo create o modificate vengono applicate al server di report nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="30d69-106">At the system level, the role assignments that you create or modify apply to the report server as a whole.</span></span> <span data-ttu-id="30d69-107">Ad esempio, la possibilità di creare pianificazioni condivise viene impostata a livello di sistema perché le pianificazioni condivise vengono utilizzate in tutto il sistema.</span><span class="sxs-lookup"><span data-stu-id="30d69-107">For example, the ability to create shared schedules is specified at the system level because shared schedules are used throughout the system.</span></span>  
  
 <span data-ttu-id="30d69-108">Per impostazione predefinita, Reporting Services fornisce due ruoli a livello di sistema predefiniti:</span><span class="sxs-lookup"><span data-stu-id="30d69-108">By default, Reporting Services provides two predefined system level roles:</span></span>  
  
-   <span data-ttu-id="30d69-109">Utente sistema include attività che consentono agli utenti di visualizzare le proprietà del server di report e le pianificazioni condivise e di eseguire definizioni di report che consentono di visualizzare report click-through pubblicati nel server di report.</span><span class="sxs-lookup"><span data-stu-id="30d69-109">System User includes tasks that allow users to view report server properties and shared schedules, and to execute report definitions, which allows users to view clickthrough reports that have been published to the report server.</span></span> <span data-ttu-id="30d69-110">La maggior parte degli utenti deve essere assegnata a questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="30d69-110">Most users should be assigned to this role.</span></span>  
  
-   <span data-ttu-id="30d69-111">Amministratore sistema include attività per la creazione e la gestione di pianificazioni condivise, l'impostazione di proprietà del server e la creazione di assegnazioni di ruolo a livello di sistema per altri utenti.</span><span class="sxs-lookup"><span data-stu-id="30d69-111">System Administrator includes tasks for creating and managing shared schedules, setting server properties, and creating system-level role assignments for other users.</span></span> <span data-ttu-id="30d69-112">Le autorizzazioni a questo livello sono necessarie per un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="30d69-112">Few users require permissions at this level.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="30d69-113">Spostamento</span><span class="sxs-lookup"><span data-stu-id="30d69-113">Navigation</span></span>  
 <span data-ttu-id="30d69-114">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="30d69-114">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-system-role-assignments-or-edit-system-role-assignments-page"></a><span data-ttu-id="30d69-115">Per aprire la pagina Nuova assegnazione ruolo a livello di sistema o Modifica assegnazioni ruolo a livello di sistema</span><span class="sxs-lookup"><span data-stu-id="30d69-115">To open the New System Role Assignments or Edit System Role Assignments page</span></span>  
  
1.  <span data-ttu-id="30d69-116">Aprire Gestione report.</span><span class="sxs-lookup"><span data-stu-id="30d69-116">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="30d69-117">Fare clic su **Impostazioni sito**nell'angolo superiore destro della pagina.</span><span class="sxs-lookup"><span data-stu-id="30d69-117">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="30d69-118">Viene visualizzata la pagina delle proprietà Generale per il sito.</span><span class="sxs-lookup"><span data-stu-id="30d69-118">This opens the General properties page for the site.</span></span>  
  
3.  <span data-ttu-id="30d69-119">Selezionare la scheda **sicurezza** . Per accedere a questa pagina, è necessario disporre delle autorizzazioni Gestione contenuto e amministratore sistema.</span><span class="sxs-lookup"><span data-stu-id="30d69-119">Select the **Security** tab. You must have Content Manager and System Administrator permissions to access this page.</span></span>  
  
4.  <span data-ttu-id="30d69-120">Per creare una nuova assegnazione di ruolo, nella barra degli strumenti fare clic su **Nuova assegnazione ruolo** .</span><span class="sxs-lookup"><span data-stu-id="30d69-120">To create a new role assignment, click **New Role Assignment** in the toolbar.</span></span> <span data-ttu-id="30d69-121">Per modificare un'assegnazione di ruolo esistente, fare clic su **Modifica** accanto a un gruppo o un utente nella pagina delle proprietà Sicurezza.</span><span class="sxs-lookup"><span data-stu-id="30d69-121">To edit an existing role assignment, click **Edit** next to a group or user on the Security properties page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="30d69-122">Opzioni</span><span class="sxs-lookup"><span data-stu-id="30d69-122">Options</span></span>  
 <span data-ttu-id="30d69-123">**Gruppo o utente**</span><span class="sxs-lookup"><span data-stu-id="30d69-123">**Group or User**</span></span>  
 <span data-ttu-id="30d69-124">Consente di digitare il nome di un account di gruppo o di un account utente del dominio.</span><span class="sxs-lookup"><span data-stu-id="30d69-124">Type the name of a group or user account in your domain.</span></span> <span data-ttu-id="30d69-125">Se il server di report viene eseguito nel contesto di un account locale, è necessario specificare gruppi o utenti locali.</span><span class="sxs-lookup"><span data-stu-id="30d69-125">If the report server is running under a local account, you must specify local groups or users.</span></span> <span data-ttu-id="30d69-126">Se il server di report viene eseguito nel contesto di un account di dominio, è necessario specificare gruppi o utenti del dominio.</span><span class="sxs-lookup"><span data-stu-id="30d69-126">If the report server is running under a domain account, you must specify domain groups or users.</span></span> <span data-ttu-id="30d69-127">Immettere l'account nel formato: \<domain> \\<account \> .</span><span class="sxs-lookup"><span data-stu-id="30d69-127">Enter the account in this format: \<domain>\\<account\>.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30d69-128">Questa casella è disponibile solo nella pagina Nuova assegnazione ruolo.</span><span class="sxs-lookup"><span data-stu-id="30d69-128">This box is available only on the New Role Assignment page.</span></span>  
  
 <span data-ttu-id="30d69-129">**Ruoli**</span><span class="sxs-lookup"><span data-stu-id="30d69-129">**Roles**</span></span>  
 <span data-ttu-id="30d69-130">Fornisce un elenco di ruoli a livello di sistema che è possibile assegnare agli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="30d69-130">Provides a list of system-level roles that you can assign to other users.</span></span> <span data-ttu-id="30d69-131">È possibile specificare più ruoli per una singola assegnazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="30d69-131">You can specify multiple roles for a single role assignment.</span></span>  
  
 <span data-ttu-id="30d69-132">Gestione report non consente di visualizzare le attività incluse in ogni ruolo né di aggiungere o modificare le attività.</span><span class="sxs-lookup"><span data-stu-id="30d69-132">Report Manager does not display the tasks in each role or provide a way to add or modify the tasks.</span></span> <span data-ttu-id="30d69-133">I ruoli devono essere utilizzati come sono definiti.</span><span class="sxs-lookup"><span data-stu-id="30d69-133">You must use the roles as they are defined.</span></span> <span data-ttu-id="30d69-134">Per creare, modificare o eliminare ruoli, utilizzare [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30d69-134">To create, modify, or delete roles, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="30d69-135">Per altre informazioni, vedere [Creare, eliminare o modificare un ruolo &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span><span class="sxs-lookup"><span data-stu-id="30d69-135">For more information, see [Create, Delete, or Modify a Role &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span></span>  
  
 <span data-ttu-id="30d69-136">Si noti che, se si utilizza [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services, è necessario utilizzare i ruoli predefiniti forniti.</span><span class="sxs-lookup"><span data-stu-id="30d69-136">Note that if you are using [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services, you must use the default roles that are provided.</span></span>  
  
 <span data-ttu-id="30d69-137">**Descrizioni**</span><span class="sxs-lookup"><span data-stu-id="30d69-137">**Descriptions**</span></span>  
 <span data-ttu-id="30d69-138">Visualizza informazioni aggiuntive sul ruolo.</span><span class="sxs-lookup"><span data-stu-id="30d69-138">Shows additional information about the role.</span></span> <span data-ttu-id="30d69-139">La descrizione di un ruolo predefinito, ad esempio Utente sistema o Amministratore sistema, contiene un riassunto delle attività supportate da ciascun ruolo.</span><span class="sxs-lookup"><span data-stu-id="30d69-139">For predefined roles such as System User or System Administrator, the description summarizes the tasks that each role supports.</span></span>  
  
 <span data-ttu-id="30d69-140">**Elimina assegnazione di ruolo**</span><span class="sxs-lookup"><span data-stu-id="30d69-140">**Delete Role Assignment**</span></span>  
 <span data-ttu-id="30d69-141">Fare clic per eliminare l'assegnazione ruolo esistente per un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="30d69-141">Click to delete an existing role assignment for a user or a group.</span></span> <span data-ttu-id="30d69-142">Non è possibile eliminare l'ultima assegnazione di ruolo rimasta (a ogni elemento deve essere associata almeno una assegnazione di ruolo).</span><span class="sxs-lookup"><span data-stu-id="30d69-142">You cannot delete a role assignment if it is the only one left (each item must have a minimum of one role assignment).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30d69-143">Questo pulsante è disponibile solo nella pagina Modifica assegnazione ruolo.</span><span class="sxs-lookup"><span data-stu-id="30d69-143">This button is available only on the Edit Role Assignment page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d69-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30d69-144">See Also</span></span>  
 <span data-ttu-id="30d69-145">[Guida sensibile al contesto Gestione report](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="30d69-145">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="30d69-146">[Assegnazioni di ruolo](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="30d69-146">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="30d69-147">Definizioni dei ruoli</span><span class="sxs-lookup"><span data-stu-id="30d69-147">Role Definitions</span></span>](security/role-definitions.md)  
  
  
