---
title: Modificare o eliminare un'assegnazione di ruolo (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing role assignments
- roles [Reporting Services], assignments
- system roles [Reporting Services]
- modifying role assignments
- deleting role assignments
ms.assetid: 523bdd32-92cb-4b48-a3a9-d58b2385bde7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d67c5cdb7647d50008f72890e4ac3e3c7eed456e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716072"
---
# <a name="modify-or-delete-a-role-assignment-report-manager"></a><span data-ttu-id="a68c3-102">Modificare o eliminare un'assegnazione di ruolo (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="a68c3-102">Modify or Delete a Role Assignment (Report Manager)</span></span>
  <span data-ttu-id="a68c3-103">Un'assegnazione di ruolo esegue il mapping di un account utente o di gruppo a una definizione di ruolo predefinita che include le attività che possono essere eseguite</span><span class="sxs-lookup"><span data-stu-id="a68c3-103">A role assignment maps a group or user account to a predefined role definition that includes tasks that can be performed.</span></span> <span data-ttu-id="a68c3-104">e determina i tipi di operazioni che un utente può eseguire in relazione a una cartella, un report, un modello o ad altro tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="a68c3-104">It determines the types of operations that a user can perform relative to a folder, report, model, or other content type.</span></span> <span data-ttu-id="a68c3-105">Per creare, modificare o eliminare assegnazioni di ruolo, utilizzare Gestione report.</span><span class="sxs-lookup"><span data-stu-id="a68c3-105">To create, modify, or delete role assignments, you use Report Manager.</span></span> <span data-ttu-id="a68c3-106">Dopo avere creato un'assegnazione di ruolo per un particolare utente o gruppo, è possibile modificarla in un secondo momento selezionando un ruolo diverso.</span><span class="sxs-lookup"><span data-stu-id="a68c3-106">After you create a role assignment for a particular user or group, you can modify it later by selecting a different role.</span></span> <span data-ttu-id="a68c3-107">Se si desidera revocare autorizzazioni a un server di report, è possibile eliminare un'assegnazione di ruolo dal server di report stesso.</span><span class="sxs-lookup"><span data-stu-id="a68c3-107">If you want to revoke permissions to a report server, you can delete a role assignment from the report server.</span></span>  
  
 <span data-ttu-id="a68c3-108">A seconda degli scopi, alcuni approcci potrebbero essere più appropriati rispetto ad altri.</span><span class="sxs-lookup"><span data-stu-id="a68c3-108">Depending on your objective, alternative approaches might be more appropriate.</span></span> <span data-ttu-id="a68c3-109">Gli esempi includono la personalizzazione o la creazione di una nuova definizione di ruolo o la modifica dell'appartenenza di un account di gruppo in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a68c3-109">Examples include customizing or creating a new role definition, or modifying the membership of a group account in Active Directory.</span></span>  
  
 <span data-ttu-id="a68c3-110">Se ad esempio un gruppo di utenti deve gestire completamente il contenuto, ma non deve disporre del set completo di autorizzazioni associato a Gestione contenuto,</span><span class="sxs-lookup"><span data-stu-id="a68c3-110">For example, suppose you have a group of users who need to fully manage their content, but should not have the full set of permissions associated with Content Manager.</span></span> <span data-ttu-id="a68c3-111">è possibile creare una nuova definizione di ruolo denominata Gestione contenuto reparto, in cui sono incluse tutte le attività di Gestione contenuto ad eccezione di **Set security policies for items**(Impostazione dei criteri di sicurezza per gli elementi).</span><span class="sxs-lookup"><span data-stu-id="a68c3-111">In this case, you could create a new role definition called Department Content Manager that includes all of the tasks in Content Manager except **Set security policies for items**.</span></span>  
  
 <span data-ttu-id="a68c3-112">Analogamente, se per un amministratore di sistema o di rete è più semplice gestire account di gruppo di Active Directory rispetto alle assegnazioni di ruolo in Gestione report, è possibile ridurre l'overhead della gestione delle assegnazioni di ruolo creando una sola assegnazione per un account di gruppo e successivamente adattare l'appartenenza a un gruppo quando gli utenti non richiedono più l'accesso ai report.</span><span class="sxs-lookup"><span data-stu-id="a68c3-112">Similarly, if you are a system or network administrator and it is easier for you to manage Active Directory group accounts than role assignments in Report Manager, you could reduce the overhead of managing role assignments by creating a single role assignment for a group account, and then adjust group membership when users no longer require access to reports.</span></span>  
  
 <span data-ttu-id="a68c3-113">Se si stabilisce che la modifica o l'eliminazione di un'assegnazione di ruolo costituisce l'approccio migliore, tenere presente di controllare che le assegnazioni di ruolo vengano eseguite sia a livello di sistema che di elemento.</span><span class="sxs-lookup"><span data-stu-id="a68c3-113">If you determine that modifying or deleting a role assignment is the best approach, remember to check for both system role assignments and item role assignments.</span></span> <span data-ttu-id="a68c3-114">Ogni tipo di assegnazione di ruolo viene configurato tramite pagine diverse in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="a68c3-114">Each type of role assignment is configured through different pages in Report Manager.</span></span>  
  
### <a name="to-modify-or-delete-a-system-role-assignment"></a><span data-ttu-id="a68c3-115">Per eliminare o modificare un'assegnazione di ruolo a livello di sistema</span><span class="sxs-lookup"><span data-stu-id="a68c3-115">To modify or delete a system role assignment</span></span>  
  
1.  <span data-ttu-id="a68c3-116">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a68c3-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="a68c3-117">Fare clic su **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a68c3-117">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="a68c3-118">Fare clic su **Security**.</span><span class="sxs-lookup"><span data-stu-id="a68c3-118">Click **Security**.</span></span> <span data-ttu-id="a68c3-119">Tutte le assegnazioni di ruolo a livello di sistema definite attualmente per il server o la distribuzione con scalabilità orizzontale vengono elencate in base al nome dell'account.</span><span class="sxs-lookup"><span data-stu-id="a68c3-119">All system-level role assignments currently defined for the server or scale-out deployment are listed by account name.</span></span>  
  
4.  <span data-ttu-id="a68c3-120">Individuare l'assegnazione di ruolo da modificare o eliminare.</span><span class="sxs-lookup"><span data-stu-id="a68c3-120">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="a68c3-121">Per aggiungere o rimuovere il ruolo per un particolare utente o gruppo, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a68c3-121">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="a68c3-122">Per eliminare un'assegnazione di ruolo, fare clic sulla casella di controllo accanto al nome dell'utente o del gruppo, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="a68c3-122">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
### <a name="to-modify-or-delete-an-item-role-assignment"></a><span data-ttu-id="a68c3-123">Per modificare o eliminare un'assegnazione di ruolo a livello di elemento</span><span class="sxs-lookup"><span data-stu-id="a68c3-123">To modify or delete an item role assignment</span></span>  
  
1.  <span data-ttu-id="a68c3-124">Avviare **Gestione report** e individuare l'elemento per il quale si desidera modificare o eliminare un'assegnazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="a68c3-124">Start **Report Manager** and locate the item for which you want to edit or delete a role assignment.</span></span>  
  
2.  <span data-ttu-id="a68c3-125">Posizionare il puntatore del mouse sull'elemento, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="a68c3-125">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="a68c3-126">Scegliere **Sicurezza**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="a68c3-126">In the drop-down menu, click **Security**.</span></span>  
  
4.  <span data-ttu-id="a68c3-127">Individuare l'assegnazione di ruolo da modificare o eliminare.</span><span class="sxs-lookup"><span data-stu-id="a68c3-127">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="a68c3-128">Per aggiungere o rimuovere il ruolo per un particolare utente o gruppo, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a68c3-128">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="a68c3-129">Per eliminare un'assegnazione di ruolo, fare clic sulla casella di controllo accanto al nome dell'utente o del gruppo, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="a68c3-129">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a68c3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a68c3-130">See Also</span></span>  
 <span data-ttu-id="a68c3-131">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="a68c3-131">(create-and-manage-role-assignments.md)</span></span>   
 <span data-ttu-id="a68c3-132">[Assegnazioni di ruolo](role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="a68c3-132">[Role Assignments](role-assignments.md) </span></span>  
 <span data-ttu-id="a68c3-133">[Pagina Impostazioni sito &#40;Gestione report&#41;](../site-settings-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a68c3-133">[Site Settings Page &#40;Report Manager&#41;](../site-settings-page-report-manager.md) </span></span>  
 [<span data-ttu-id="a68c3-134">Pagina Nuova assegnazione ruolo a livello di sistema: Modifica assegnazioni ruolo a livello di sistema &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="a68c3-134">New System Role Assignments: Edit System Role Assignments Page &#40;Report Manager&#41;</span></span>](../new-system-role-assignments-edit-system-role-assignments-page-report-manager.md)  
  
  
