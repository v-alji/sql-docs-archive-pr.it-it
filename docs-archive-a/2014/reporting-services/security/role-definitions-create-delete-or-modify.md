---
title: Creare, eliminare o modificare un ruolo (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- roles [Reporting Services], creating
- deleting roles
- removing roles
- roles [Reporting Services], definitions
- modifying roles
- roles [Reporting Services], deleting
- roles [Reporting Services], modifying
ms.assetid: 3d1d56e6-a283-44a7-8417-36cb4d2c74d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 543bddda88e41af39d3200df4728716d46b3ae8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721060"
---
# <a name="create-delete-or-modify-a-role-management-studio"></a><span data-ttu-id="49a45-102">Creare, eliminare o modificare un ruolo (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="49a45-102">Create, Delete, or Modify a Role (Management Studio)</span></span>
  <span data-ttu-id="49a45-103">In Reporting Services sono disponibili ruoli predefiniti che definiscono un livello di accesso a un server di report.</span><span class="sxs-lookup"><span data-stu-id="49a45-103">Reporting Services provides predefined roles that define a level of access to a report server.</span></span> <span data-ttu-id="49a45-104">La richiesta di accesso al server di report da parte di ogni utente o gruppo viene effettuata tramite un ruolo che descrive le attività che possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="49a45-104">Each user or group who requires access to report server does so through a role that describes the tasks that can be performed.</span></span> <span data-ttu-id="49a45-105">I ruoli vengono definiti per il server di report complessivamente.</span><span class="sxs-lookup"><span data-stu-id="49a45-105">Roles are defined for the report server as a whole.</span></span> <span data-ttu-id="49a45-106">Non è possibile variare una definizione di ruolo per parti specifiche del server di report o specificare che un ruolo venga utilizzato in modo diverso a seconda delle circostanze.</span><span class="sxs-lookup"><span data-stu-id="49a45-106">You cannot vary a role definition for specific parts of the report server, or specify that a role be used differently depending on the circumstances.</span></span>  
  
 <span data-ttu-id="49a45-107">Per creare, modificare o eliminare ruoli, usare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49a45-107">To create, modify, or delete roles, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="49a45-108">È possibile eliminare solo ruoli che non sono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="49a45-108">You can only delete roles that are not used.</span></span>  
  
 <span data-ttu-id="49a45-109">Per assegnare utenti e gruppi ai ruoli creati, utilizzare Gestione report.</span><span class="sxs-lookup"><span data-stu-id="49a45-109">To assign users and groups to the roles that you create, use Report Manager.</span></span> <span data-ttu-id="49a45-110">Per ulteriori informazioni, vedere [concedere l'accesso utente a un server di Report &#40;Gestione report&#41;](grant-user-access-to-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="49a45-110">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](grant-user-access-to-a-report-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49a45-111">Se il server di report è configurato per la modalità integrata SharePoint e si è connessi al sito di SharePoint con cui il server di report è integrato, è possibile visualizzare e modificare i livelli di autorizzazione che controllano l'accesso al contenuto e alle operazioni del server di report.</span><span class="sxs-lookup"><span data-stu-id="49a45-111">If the report server is configured for SharePoint integrated mode, and you connected to the SharePoint site that the report server is integrated with, you can view and modify the permission levels that control access to report server content and operations.</span></span>  
  
### <a name="to-create-a-role-definition"></a><span data-ttu-id="49a45-112">Per creare una definizione di ruolo</span><span class="sxs-lookup"><span data-stu-id="49a45-112">To create a role definition</span></span>  
  
1.  <span data-ttu-id="49a45-113">Espandere il nodo di un server di report in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="49a45-113">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="49a45-114">Espandere la cartella sicurezza.</span><span class="sxs-lookup"><span data-stu-id="49a45-114">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="49a45-115">Per creare una definizione di ruolo a livello di elemento, fare clic con il pulsante destro del mouse su **Ruoli**e scegliere **Nuovo ruolo**.</span><span class="sxs-lookup"><span data-stu-id="49a45-115">If you are creating an item-level role definition, right-click **Roles**, and point to **New Role**.</span></span>  
  
     <span data-ttu-id="49a45-116">Se invece si vuole creare una definizione di ruolo a livello di sistema, fare clic con il pulsante destro del mouse su **Ruoli a livello di sistema**e scegliere **Nuovo ruolo a livello di sistema**.</span><span class="sxs-lookup"><span data-stu-id="49a45-116">Or, if you are creating a system-level role definition, right-click **System Roles**, and point to **New System Role**.</span></span>  
  
4.  <span data-ttu-id="49a45-117">Digitare un nome univoco per il ruolo.</span><span class="sxs-lookup"><span data-stu-id="49a45-117">Type a unique name for the role.</span></span> <span data-ttu-id="49a45-118">Il nome deve includere almeno un carattere.</span><span class="sxs-lookup"><span data-stu-id="49a45-118">A name must contain at least one character.</span></span> <span data-ttu-id="49a45-119">È inoltre possibile utilizzare spazi e alcuni simboli, con l'esclusione dei caratteri ; ?</span><span class="sxs-lookup"><span data-stu-id="49a45-119">It can also include spaces and certain symbols, but not the characters ; ?</span></span> <span data-ttu-id="49a45-120">: \@ & = +, $/\* \< > | "o/.</span><span class="sxs-lookup"><span data-stu-id="49a45-120">: \@ & = + , $ / \* \< > | " or /.</span></span>  
  
5.  <span data-ttu-id="49a45-121">Se lo si desidera, digitare una descrizione.</span><span class="sxs-lookup"><span data-stu-id="49a45-121">Optionally type a description.</span></span> <span data-ttu-id="49a45-122">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] questa descrizione verrà visualizzata solo in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="49a45-122">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] this description is visible only on this page.</span></span> <span data-ttu-id="49a45-123">Gli utenti che visualizzeranno l'elemento in Gestione report potranno leggere la descrizione.</span><span class="sxs-lookup"><span data-stu-id="49a45-123">Users who view this item through Report Manager can see this description in that tool.</span></span>  
  
6.  <span data-ttu-id="49a45-124">Selezionare le attività che i membri del ruolo potranno eseguire.</span><span class="sxs-lookup"><span data-stu-id="49a45-124">Select the tasks that members of this role can perform.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-or-modify-a-role-definition"></a><span data-ttu-id="49a45-125">Per eliminare o modificare una definizione di ruolo</span><span class="sxs-lookup"><span data-stu-id="49a45-125">To delete or modify a role definition</span></span>  
  
1.  <span data-ttu-id="49a45-126">Espandere il nodo di un server di report in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="49a45-126">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="49a45-127">Espandere la cartella sicurezza.</span><span class="sxs-lookup"><span data-stu-id="49a45-127">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="49a45-128">Per eliminare o modificare una definizione di ruolo a livello di elemento, espandere la cartella Ruoli.</span><span class="sxs-lookup"><span data-stu-id="49a45-128">To delete or modify an item-level role definition, expand the Roles folder.</span></span> <span data-ttu-id="49a45-129">selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="49a45-129">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="49a45-130">Per eliminare una definizione di ruolo, fare clic con il pulsante destro del mouse sull'elemento e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="49a45-130">To delete a role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="49a45-131">Verrà visualizzata la finestra di dialogo **Elimina oggetto** .</span><span class="sxs-lookup"><span data-stu-id="49a45-131">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="49a45-132">Per modificare una definizione di ruolo, fare clic con il pulsante destro del mouse sull'elemento e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="49a45-132">To modify a role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="49a45-133">Verrà visualizzata la scheda Generale della finestra di dialogo **Proprietà ruolo utente** .</span><span class="sxs-lookup"><span data-stu-id="49a45-133">The General page of the **User Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="49a45-134">Selezionare le attività che i membri del ruolo potranno eseguire e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="49a45-134">Select the tasks that members of this role can perform, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="49a45-135">Per eliminare o modificare una definizione di ruolo a livello di sistema, espandere la cartella **Ruoli a livello di sistema** .</span><span class="sxs-lookup"><span data-stu-id="49a45-135">To delete or modify a system-level role definition, expand the **System Roles** folder.</span></span> <span data-ttu-id="49a45-136">selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="49a45-136">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="49a45-137">Per eliminare una definizione di ruolo di sistema, fare clic con il pulsante destro del mouse sull'elemento e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="49a45-137">To delete a system role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="49a45-138">Verrà visualizzata la finestra di dialogo **Elimina oggetto** .</span><span class="sxs-lookup"><span data-stu-id="49a45-138">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="49a45-139">Per modificare una definizione di ruolo di sistema, fare clic con il pulsante destro del mouse sull'elemento e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="49a45-139">To modify a system role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="49a45-140">Verrà visualizzata la scheda Generale della finestra di dialogo **Proprietà ruolo a livello di sistema** .</span><span class="sxs-lookup"><span data-stu-id="49a45-140">The General page of the **System Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="49a45-141">Selezionare le attività che i membri del ruolo potranno eseguire e fare clic su **OK** per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="49a45-141">Select the tasks that members of this role can perform, and click **OK** to apply the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a45-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49a45-142">See Also</span></span>  
 <span data-ttu-id="49a45-143">[Connettersi a un server di report in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="49a45-143">[Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="49a45-144">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="49a45-144">(create-and-manage-role-assignments.md)</span></span>   
 [<span data-ttu-id="49a45-145">Reporting Services in SQL Server Management Studio &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="49a45-145">Reporting Services in SQL Server Management Studio &#40;SSRS&#41;</span></span>](../tools/reporting-services-in-sql-server-management-studio-ssrs.md)  
  
  
