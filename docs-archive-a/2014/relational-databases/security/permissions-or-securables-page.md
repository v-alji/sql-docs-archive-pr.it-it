---
title: Pagina Autorizzazioni o Entità a sicurezza diretta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.permissions.f1
- sql12.swb.SecurableAndEffectPermissions.f1
- sql12.swb.availabilitygroupproperties.permission.f1
- sql12.swb.common.columnperm.f1
- sql12.swb.SecurableAndEffectivePermission.f1
ms.assetid: b3bf077a-bec2-4161-ac0c-460586199906
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 80417c720258833850f07eb67f83f5c47f487ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714031"
---
# <a name="permissions-or-securables-page"></a><span data-ttu-id="a0538-102">Pagina Autorizzazioni o Entità a sicurezza diretta</span><span class="sxs-lookup"><span data-stu-id="a0538-102">Permissions or Securables Page</span></span>
  <span data-ttu-id="a0538-103">Usare la pagina **Autorizzazioni** o la pagina **Entità a protezione diretta** per visualizzare o impostare le autorizzazioni per le entità a protezione diretta.</span><span class="sxs-lookup"><span data-stu-id="a0538-103">Use the **Permissions** page or the **Securables** page to view or set the permissions for securables.</span></span> <span data-ttu-id="a0538-104">È possibile accedere a questa pagina da diversi tipi di oggetti.</span><span class="sxs-lookup"><span data-stu-id="a0538-104">This page can be opened from many locations.</span></span> <span data-ttu-id="a0538-105">Il contenuto della pagina può modificare leggermente, in base alle modalità in cui la pagina è aperta e al contenuto.</span><span class="sxs-lookup"><span data-stu-id="a0538-105">The contents of the page can change slightly, depending on how the page is opened and what it contains.</span></span> <span data-ttu-id="a0538-106">Quando la pagina viene visualizzata, la griglia superiore della pagina potrebbe contenere alcuni elementi o potrebbe essere vuota.</span><span class="sxs-lookup"><span data-stu-id="a0538-106">The top grid of the page might be populated when the page opens, or it might be empty.</span></span> <span data-ttu-id="a0538-107">Per aggiungere elementi alla griglia superiore, fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="a0538-107">To add items to the upper grid, click **Search**.</span></span> <span data-ttu-id="a0538-108">Selezionare un elemento in tale griglia, quindi impostare le autorizzazioni appropriate nella scheda **Esplicita** . Per visualizzare autorizzazioni aggregate, usare la scheda **Valide** .</span><span class="sxs-lookup"><span data-stu-id="a0538-108">In the upper grid, select an item, and then set the appropriate permissions on the **Explicit** tab. To view aggregated permissions, use the **Effective** tab.</span></span>  
  
 <span data-ttu-id="a0538-109">Per comprendere le possibili combinazioni di entità a protezione diretta ed entità, vedere i collegamenti relativi alla sintassi specifica delle entità a protezione diretta nell'argomento [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0538-109">To understand the possible combinations of securables and principals, see the securable-specific syntax links in the topic [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="a0538-110">Per altre informazioni, vedere [Entità a protezione diretta](securables.md).</span><span class="sxs-lookup"><span data-stu-id="a0538-110">For more information, see [Securables](securables.md).</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="a0538-111">Intestazione di pagina</span><span class="sxs-lookup"><span data-stu-id="a0538-111">Page Header</span></span>  
 <span data-ttu-id="a0538-112">L'intestazione della pagina **Autorizzazioni** o **Entità a protezione diretta** dipende dall'entità a protezione diretta o dall'entità.</span><span class="sxs-lookup"><span data-stu-id="a0538-112">The header of the **Permissions** or **Securables** page varies depending on the securable or principal.</span></span> <span data-ttu-id="a0538-113">Vengono visualizzate informazioni significative sull'elemento, ad esempio il nome.</span><span class="sxs-lookup"><span data-stu-id="a0538-113">It displays information relevant to the item, such as its name.</span></span>  
  
## <a name="upper-grid"></a><span data-ttu-id="a0538-114">Griglia superiore</span><span class="sxs-lookup"><span data-stu-id="a0538-114">Upper Grid</span></span>  
 <span data-ttu-id="a0538-115">La griglia superiore include uno o più elementi per i quali è possibile impostare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a0538-115">The upper grid contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="a0538-116">In questa finestra di dialogo è disponibile un pulsante **Cerca** che consente di selezionare oggetti o entità da aggiungere alla griglia superiore.</span><span class="sxs-lookup"><span data-stu-id="a0538-116">This dialog box provides the **Search** button for selecting objects or principals to add to the upper grid.</span></span> <span data-ttu-id="a0538-117">Nel nome della griglia potrebbe essere visualizzato **Entità a protezione diretta** oppure uno o più tipi di entità o di entità a protezione diretta.</span><span class="sxs-lookup"><span data-stu-id="a0538-117">The name of the grid might display **Securables** or one or more types of securables or principals.</span></span> <span data-ttu-id="a0538-118">Le colonne visualizzate nella griglia superiore variano a seconda del tipo di entità o di entità a sicurezza diretta.</span><span class="sxs-lookup"><span data-stu-id="a0538-118">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="a0538-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a0538-119">**Name**</span></span>  
 <span data-ttu-id="a0538-120">Nome di ogni entità o entità a sicurezza diretta aggiunto alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a0538-120">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="a0538-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a0538-121">**Type**</span></span>  
 <span data-ttu-id="a0538-122">Descrive il tipo di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="a0538-122">Describes the type of each item.</span></span>  
  
## <a name="explicit-tab"></a><span data-ttu-id="a0538-123">Scheda Esplicita</span><span class="sxs-lookup"><span data-stu-id="a0538-123">Explicit Tab</span></span>  
 <span data-ttu-id="a0538-124">Nella scheda **Esplicita** sono elencate le possibili autorizzazioni per l'entità a protezione diretta selezionate nella griglia superiore.</span><span class="sxs-lookup"><span data-stu-id="a0538-124">The **Explicit** tab lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="a0538-125">Per configurare le autorizzazioni, selezionare o deselezionare le caselle di controllo **Concedi** (o **Consenti**), **Con diritto di concessione**e **Nega** .</span><span class="sxs-lookup"><span data-stu-id="a0538-125">To configure the permissions, select or clear the **Grant** (or **Allow**), **With Grant**, and **Deny** check boxes.</span></span> <span data-ttu-id="a0538-126">Le opzioni effettivamente disponibili dipendono dall'autorizzazione esplicita in questione.</span><span class="sxs-lookup"><span data-stu-id="a0538-126">All options are not available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="a0538-127">**Autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="a0538-127">**Permissions**</span></span>  
 <span data-ttu-id="a0538-128">Nome dell'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0538-128">The name of the permission.</span></span>  
  
 <span data-ttu-id="a0538-129">**Utente che concede le autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="a0538-129">**Grantor**</span></span>  
 <span data-ttu-id="a0538-130">Entità che ha concesso l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0538-130">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="a0538-131">**Concedi**</span><span class="sxs-lookup"><span data-stu-id="a0538-131">**Grant**</span></span>  
 <span data-ttu-id="a0538-132">Selezionare questa opzione per concedere l'autorizzazione all'account di accesso,</span><span class="sxs-lookup"><span data-stu-id="a0538-132">Select to grant this permission to the login.</span></span> <span data-ttu-id="a0538-133">deselezionarla per revocare l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0538-133">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="a0538-134">**Con diritto di concessione**</span><span class="sxs-lookup"><span data-stu-id="a0538-134">**With Grant**</span></span>  
 <span data-ttu-id="a0538-135">Riflette lo stato dell'opzione WITH GRANT relativo all'autorizzazione elencata.</span><span class="sxs-lookup"><span data-stu-id="a0538-135">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="a0538-136">Il contenuto di questa casella è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a0538-136">This box is read-only.</span></span> <span data-ttu-id="a0538-137">Per applicare questa autorizzazione, utilizzare l'istruzione [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="a0538-137">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="a0538-138">**Nega**</span><span class="sxs-lookup"><span data-stu-id="a0538-138">**Deny**</span></span>  
 <span data-ttu-id="a0538-139">Selezionare questa opzione per negare l'autorizzazione all'account di accesso,</span><span class="sxs-lookup"><span data-stu-id="a0538-139">Select to deny this permission to the login.</span></span> <span data-ttu-id="a0538-140">deselezionarla per revocare l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0538-140">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="a0538-141">**Autorizzazioni colonna**</span><span class="sxs-lookup"><span data-stu-id="a0538-141">**Column Permissions**</span></span>  
 <span data-ttu-id="a0538-142">Per oggetti che contengono colonne, ad esempio tabelle, viste o funzioni con valori di tabella, il pulsante **Autorizzazioni colonna** consente di visualizzare la finestra di dialogo **Autorizzazioni colonna** .</span><span class="sxs-lookup"><span data-stu-id="a0538-142">For objects that contain columns (such as tables, views, or table-valued functions), the **Column Permissions** button opens the **Column Permissions** dialog box.</span></span> <span data-ttu-id="a0538-143">In questa finestra di dialogo è possibile impostare le autorizzazioni **Concedi**, **Consenti**o **Nega** in colonne singole di una tabella o di una vista.</span><span class="sxs-lookup"><span data-stu-id="a0538-143">In this dialog box, you can set **Grant**, **Allow**, or **Deny** permissions on individual columns of a table or view.</span></span> <span data-ttu-id="a0538-144">Questa opzione non è disponibile per tutti i tipi di oggetti o tutte le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a0538-144">This option is not available for all object types or permissions.</span></span>  
  
## <a name="effective-tab"></a><span data-ttu-id="a0538-145">Scheda Valide</span><span class="sxs-lookup"><span data-stu-id="a0538-145">Effective Tab</span></span>  
 <span data-ttu-id="a0538-146">Le autorizzazioni di un'entità correlate a quelle di un'entità a sicurezza diretta possono derivare da autorizzazioni impostate per numerose entità diverse.</span><span class="sxs-lookup"><span data-stu-id="a0538-146">The permissions that a principal has related to a securable may come from permissions that are set for several different principals.</span></span> <span data-ttu-id="a0538-147">A un account di accesso, ad esempio, potrebbero essere concesse autorizzazioni sia a livello individuale che come appartenente a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="a0538-147">For example, a login might be granted permissions individually and also as a member of a group.</span></span> <span data-ttu-id="a0538-148">Nella scheda **Valide** viene visualizzato il risultato della combinazione di autorizzazioni esplicite e di quelle ricevute in base all'appartenenza a un gruppo oppure a un ruolo.</span><span class="sxs-lookup"><span data-stu-id="a0538-148">The **Effective** tab shows the result of combining explicit permissions and the permissions that are received from group or role memberships.</span></span> <span data-ttu-id="a0538-149">Le autorizzazioni concesse vengono aggregate.</span><span class="sxs-lookup"><span data-stu-id="a0538-149">Grant permissions are aggregated.</span></span> <span data-ttu-id="a0538-150">Un'autorizzazione negata ha la priorità su tutte le autorizzazioni concesse.</span><span class="sxs-lookup"><span data-stu-id="a0538-150">A deny permission overrides all grant permissions.</span></span>  
  
 <span data-ttu-id="a0538-151">**Autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="a0538-151">**Permissions**</span></span>  
 <span data-ttu-id="a0538-152">Nome dell'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0538-152">The name of the permission.</span></span>  
  
 <span data-ttu-id="a0538-153">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a0538-153">**Column**</span></span>  
 <span data-ttu-id="a0538-154">Nomi delle colonne interessate dall'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0538-154">The names of columns that are affected by the permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0538-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0538-155">See Also</span></span>  
 <span data-ttu-id="a0538-156">[Ruoli a livello di database](authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="a0538-156">[Database-Level Roles](authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="a0538-157">Centro sicurezza per il motore di Database di SQL Server e il Database SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="a0538-157">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
