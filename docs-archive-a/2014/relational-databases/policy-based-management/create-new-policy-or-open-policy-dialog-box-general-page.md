---
title: Finestra di dialogo Crea nuovi criteri o Apri criteri, pagina Generale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.newgroup.f1
- sql12.swb.dmf.policy.f1
- sql12.swb.dmf.policy.filter.f1
ms.assetid: c00bebd0-d04b-4c64-840e-8b7a2c603436
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4b67cb8faf18001b841824b806e7befc0683d457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626724"
---
# <a name="create-new-policy-or-open-policy-dialog-box-general-page"></a><span data-ttu-id="c070c-102">Finestra di dialogo Crea nuovi criteri o Apri criteri, pagina Generale</span><span class="sxs-lookup"><span data-stu-id="c070c-102">Create New Policy or Open Policy Dialog Box, General Page</span></span>
  <span data-ttu-id="c070c-103">Utilizzare questa finestra di dialogo per creare nuovi criteri della gestione basata su criteri o per modificarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="c070c-103">Use this dialog box to create a new Policy-Based Management policy or modify an existing policy.</span></span> <span data-ttu-id="c070c-104">Utilizzare le aree **In base alle destinazioni** e **Restrizione server** come filtro per limitare i criteri a un subset di tutte le destinazioni possibili.</span><span class="sxs-lookup"><span data-stu-id="c070c-104">Use the **Against targets** and **Server restriction** areas as a filter to limit policies to a subset of all possible targets.</span></span> <span data-ttu-id="c070c-105">Per poter utilizzare le condizioni come filtri delle destinazioni, è necessario che siano definite in un facet fisico, che non contengano funzioni e che non contengano l'operatore LIKE.</span><span class="sxs-lookup"><span data-stu-id="c070c-105">For conditions to be used as target filters, they must be defined on a physical facet, must not contain functions, and must not contain the LIKE operator.</span></span> <span data-ttu-id="c070c-106">Durante il calcolo del set di oggetti per i criteri, per impostazione predefinita gli oggetti di sistema sono esclusi.</span><span class="sxs-lookup"><span data-stu-id="c070c-106">When the system computes the object set for a policy, by default the system objects are excluded.</span></span>  <span data-ttu-id="c070c-107">Ad esempio, se il set di oggetti dei criteri si riferisce a tutte le tabelle, i criteri non verranno applicati alle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="c070c-107">For example, if the object set of the policy refers to all tables, the policy will not apply to system tables.</span></span> <span data-ttu-id="c070c-108">Se gli utenti desiderano valutare i criteri negli oggetti di sistema, possono aggiungere in modo esplicito questi oggetti al set di oggetti.</span><span class="sxs-lookup"><span data-stu-id="c070c-108">If users want to evaluate a policy against system objects, they can explicitly add system objects to the object set.</span></span> <span data-ttu-id="c070c-109">Tuttavia, sebbene tutti i criteri siano supportati per la modalità di valutazione **Controllo su pianificazione** , per motivi di prestazioni, non tutti i criteri con i set di oggetti arbitrari sono supportati per la modalità di valutazione **Controllo su modifiche** .</span><span class="sxs-lookup"><span data-stu-id="c070c-109">However, though all policies are supported for **check on schedule** evaluation mode, for performance reason, not all policies with arbitrary object sets are supported for **check on change** evaluation mode.</span></span> <span data-ttu-id="c070c-110">Per altre informazioni, vedere [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span><span class="sxs-lookup"><span data-stu-id="c070c-110">For more information, see [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span></span>  
  
## <a name="options"></a><span data-ttu-id="c070c-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c070c-111">Options</span></span>  
 <span data-ttu-id="c070c-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c070c-112">**Name**</span></span>  
 <span data-ttu-id="c070c-113">In caso di criteri nuovi digitare il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="c070c-113">For a new policy, type the new policy name.</span></span> <span data-ttu-id="c070c-114">In caso di criteri esistenti, il nome è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="c070c-114">For an existing policy, the name is displayed.</span></span>  
  
 <span data-ttu-id="c070c-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="c070c-115">**Enabled**</span></span>  
 <span data-ttu-id="c070c-116">Selezionare la casella di controllo **Abilitato** per abilitare i criteri.</span><span class="sxs-lookup"><span data-stu-id="c070c-116">Select the **Enabled** check box to enable the policy.</span></span> <span data-ttu-id="c070c-117">Deselezionare la casella di controllo **Abilitato** per disabilitarli.</span><span class="sxs-lookup"><span data-stu-id="c070c-117">Clear the **Enabled** check box to disable the policy.</span></span> <span data-ttu-id="c070c-118">La casella **Abilitato** si applica all'automazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="c070c-118">The **Enabled** box applies to policy automation.</span></span> <span data-ttu-id="c070c-119">Consente di creare o rimuovere il sistema di automazione per i criteri.</span><span class="sxs-lookup"><span data-stu-id="c070c-119">It creates or removes the automation system for the policy.</span></span> <span data-ttu-id="c070c-120">Per l'automazione vengono utilizzati i meccanismi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c070c-120">Automation uses the following mechanisms:</span></span>  
  
 <span data-ttu-id="c070c-121">**Su modifica: impedisci esecuzione**</span><span class="sxs-lookup"><span data-stu-id="c070c-121">**On change: prevent**</span></span>  
 <span data-ttu-id="c070c-122">Un trigger del database applica la conformità.</span><span class="sxs-lookup"><span data-stu-id="c070c-122">A database trigger enforces compliance.</span></span>  
  
 <span data-ttu-id="c070c-123">**Su modifica: solo log**</span><span class="sxs-lookup"><span data-stu-id="c070c-123">**On change: log only**</span></span>  
 <span data-ttu-id="c070c-124">Un evento dei servizi di notifica verifica la conformità.</span><span class="sxs-lookup"><span data-stu-id="c070c-124">A notification services event checks for compliance.</span></span>  
  
 <span data-ttu-id="c070c-125">**Su pianificazione**</span><span class="sxs-lookup"><span data-stu-id="c070c-125">**On schedule**</span></span>  
 <span data-ttu-id="c070c-126">Viene creato un processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per verificare la conformità in base a una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c070c-126">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created to check for compliance on a schedule.</span></span>  
  
 <span data-ttu-id="c070c-127">I criteri eseguiti in modalità di valutazione **Su richiesta** non utilizzano questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="c070c-127">Policies that are run using **On demand** evaluation mode do not use this check box.</span></span>  
  
 <span data-ttu-id="c070c-128">**Condizioni di controllo**</span><span class="sxs-lookup"><span data-stu-id="c070c-128">**Check condition**</span></span>  
 <span data-ttu-id="c070c-129">Selezionare la condizione della gestione basata su criteri utilizzata dai criteri correnti.</span><span class="sxs-lookup"><span data-stu-id="c070c-129">Select the Policy-Based Management condition that this policy uses.</span></span> <span data-ttu-id="c070c-130">Vengono elencate tutte le condizioni del server relative al facet della gestione basata su criteri associato.</span><span class="sxs-lookup"><span data-stu-id="c070c-130">All conditions on the server for the associated Policy-Based Management facet are listed.</span></span> <span data-ttu-id="c070c-131">Fare clic su **Nuova condizione** per creare una nuova condizione.</span><span class="sxs-lookup"><span data-stu-id="c070c-131">Click **New condition** to create a new condition.</span></span> <span data-ttu-id="c070c-132">Fare clic sul pulsante con i puntini di sospensione ( **...** ) per modificarla.</span><span class="sxs-lookup"><span data-stu-id="c070c-132">Click the ellipsis (**...**) button to modify the condition.</span></span>  
  
 <span data-ttu-id="c070c-133">**In base alle destinazioni**</span><span class="sxs-lookup"><span data-stu-id="c070c-133">**Against targets**</span></span>  
 <span data-ttu-id="c070c-134">Selezionare i tipi di destinazione disponibili per il facet per completare un'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="c070c-134">Select the target types that are available for this facet to complete a filter expression.</span></span>  
  
 <span data-ttu-id="c070c-135">**Modalità di valutazione**</span><span class="sxs-lookup"><span data-stu-id="c070c-135">**Evaluation Mode**</span></span>  
 <span data-ttu-id="c070c-136">Consente di selezionare la modalità di valutazione per i criteri.</span><span class="sxs-lookup"><span data-stu-id="c070c-136">Select the evaluation mode for the policy.</span></span> <span data-ttu-id="c070c-137">Alcuni criteri possono essere controllati ma non applicati.</span><span class="sxs-lookup"><span data-stu-id="c070c-137">Some policies can be checked but not enforced.</span></span> <span data-ttu-id="c070c-138">Di seguito vengono elencate le modalità di valutazione:</span><span class="sxs-lookup"><span data-stu-id="c070c-138">The evaluation modes are as follows:</span></span>  
  
 <span data-ttu-id="c070c-139">**Su richiesta**</span><span class="sxs-lookup"><span data-stu-id="c070c-139">**On demand**</span></span>  
 <span data-ttu-id="c070c-140">I criteri verranno eseguiti solo se vengono avviati dalla finestra di dialogo **Valuta** .</span><span class="sxs-lookup"><span data-stu-id="c070c-140">Policy will only be run when you run it from the **Evaluate** dialog box.</span></span>  
  
 <span data-ttu-id="c070c-141">**Su pianificazione**</span><span class="sxs-lookup"><span data-stu-id="c070c-141">**On schedule**</span></span>  
 <span data-ttu-id="c070c-142">I criteri vengono valutati periodicamente. Viene registrata una voce di log per i criteri non conformi e viene creato un report.</span><span class="sxs-lookup"><span data-stu-id="c070c-142">Periodically evaluates the policy, records a log entry for policies that have out-of-compliance, and creates a report.</span></span> <span data-ttu-id="c070c-143">La casella **Pianificazione** viene abilitata.</span><span class="sxs-lookup"><span data-stu-id="c070c-143">Enables the **Schedule** box.</span></span>  
  
 <span data-ttu-id="c070c-144">**Su modifica: solo log**</span><span class="sxs-lookup"><span data-stu-id="c070c-144">**On change: log only**</span></span>  
 <span data-ttu-id="c070c-145">Quando l'utente tenta di apportare modifiche, questa opzione non impedisce le modifiche non conformi, ma registra le violazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="c070c-145">When changes are tried, this option does not prevent out-of-compliance changes, but logs policy violations.</span></span>  
  
 <span data-ttu-id="c070c-146">**Su modifica: impedisci esecuzione**</span><span class="sxs-lookup"><span data-stu-id="c070c-146">**On change: prevent**</span></span>  
 <span data-ttu-id="c070c-147">Quando l'utente tenta di apportare modifiche, questa opzione impedisce le modifiche che violerebbero i criteri.</span><span class="sxs-lookup"><span data-stu-id="c070c-147">When changes are tried, this option prevents changes that would violate the policy.</span></span>  
  
 <span data-ttu-id="c070c-148">**Pianificare**</span><span class="sxs-lookup"><span data-stu-id="c070c-148">**Schedule**</span></span>  
 <span data-ttu-id="c070c-149">Questa opzione viene visualizzata quando è selezionata la modalità di valutazione **Su pianificazione** .</span><span class="sxs-lookup"><span data-stu-id="c070c-149">This option appears when **On schedule** evaluation mode is selected.</span></span> <span data-ttu-id="c070c-150">Digitare il nome della pianificazione, fare clic su **Seleziona** per effettuare una selezione da un elenco oppure scegliere **Nuova** per creare una nuova pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c070c-150">Type the name of the schedule, click **Pick** to select a schedule from a list, or click **New** to create a new schedule.</span></span> <span data-ttu-id="c070c-151">Per abilitare l'area di pianificazione, è necessario che l'opzione **Su pianificazione** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="c070c-151">To enable the schedule area, **On schedule** must be selected.</span></span>  
  
 <span data-ttu-id="c070c-152">**Restrizione server**</span><span class="sxs-lookup"><span data-stu-id="c070c-152">**Server restriction**</span></span>  
 <span data-ttu-id="c070c-153">Selezionare i tipi di server appropriati per i criteri.</span><span class="sxs-lookup"><span data-stu-id="c070c-153">Select the types of servers that are appropriate for this policy.</span></span> <span data-ttu-id="c070c-154">Le opzioni disponibili sono **Nessuno** o la selezione di una condizione che filtra i server possibili.</span><span class="sxs-lookup"><span data-stu-id="c070c-154">Options are **None** or select a condition that filters the possible servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c070c-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c070c-155">See Also</span></span>  
 [<span data-ttu-id="c070c-156">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="c070c-156">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
