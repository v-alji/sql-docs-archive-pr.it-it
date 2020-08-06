---
title: Sincronizzare una sottoscrizione mediante Gestione sincronizzazione Microsoft Windows (Gestione sincronizzazione Microsoft Windows) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], Windows Synchronization Manager
- Windows Synchronization Manager
ms.assetid: 80f15dd6-e84d-4f96-9866-5b34ea531f1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bb31c344f91c68b04e03dd218f22b09bec44830b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716236"
---
# <a name="synchronize-a-subscription-using-windows-synchronization-manager-windows-synchronization-manager"></a><span data-ttu-id="e662e-102">Sincronizzazione di una sottoscrizione mediante Gestione sincronizzazione Microsoft Windows (Gestione sincronizzazione Microsoft Windows)</span><span class="sxs-lookup"><span data-stu-id="e662e-102">Synchronize a Subscription Using Windows Synchronization Manager (Windows Synchronization Manager)</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="e662e-103">Windows Synchronization Manager può essere utilizzato solo per sincronizzare le sottoscrizioni con le pubblicazioni Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguito nello stesso computer in cui è installato il componente Gestione sincronizzazione, nonché per sincronizzare pagine Web e file offline.</span><span class="sxs-lookup"><span data-stu-id="e662e-103">Windows Synchronization Manager can only be used to synchronize subscriptions to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publications if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running on the same computer as Synchronization Manager (it can also be used to synchronize offline files and Web pages).</span></span> <span data-ttu-id="e662e-104">Per utilizzare Gestione sincronizzazione:</span><span class="sxs-lookup"><span data-stu-id="e662e-104">To use Synchronization Manager:</span></span>  
  
1.  <span data-ttu-id="e662e-105">Abilitare la sincronizzazione delle sottoscrizioni pull con Gestione sincronizzazione Microsoft Windows nella finestra di dialogo **Proprietà sottoscrizione - \<Subscriber>: \<SubscriptionDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="e662e-105">Enable the synchronization of pull subscriptions with Windows Synchronization Manager in the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box.</span></span> <span data-ttu-id="e662e-106">Per altre informazioni sull'accesso a questa finestra di dialogo, vedere [Visualizzare e modificare le proprietà delle sottoscrizioni pull](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e662e-106">For more information about accessing this dialog box, see [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
2.  <span data-ttu-id="e662e-107">Accedere a Gestione sincronizzazione mediante il menu **Start** di Windows.</span><span class="sxs-lookup"><span data-stu-id="e662e-107">Access Synchronization Manager through the **Start** menu in Windows.</span></span>  
  
 <span data-ttu-id="e662e-108">Gestione sincronizzazione consente di utilizzare il sistema di risoluzione interattivo per le sottoscrizioni di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="e662e-108">Synchronization Manager allows you to use the Interactive Resolver for merge subscriptions.</span></span> <span data-ttu-id="e662e-109">Generalmente, i conflitti rilevati durante la sincronizzazione vengono risolti automaticamente, ma se la risoluzione interattiva è abilitata, essi possono essere risolti da un utente in fase di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="e662e-109">Typically, conflicts detected during synchronization are resolved automatically, but if interactive resolution is enabled, conflicts can be resolved by a user during synchronization.</span></span> <span data-ttu-id="e662e-110">Se una sincronizzazione viene eseguita all'esterno di Gestione sincronizzazione Microsoft Windows (come sincronizzazione pianificata o sincronizzazione su richiesta in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Monitoraggio replica), i conflitti vengono risolti automaticamente senza richiedere l'intervento dell'utente, in base al sistema di risoluzione specificato per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="e662e-110">If a synchronization is performed outside of Windows Synchronization Manager (as a scheduled synchronization or an on demand synchronization in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Replication Monitor), conflicts are resolved automatically without user intervention, according to the resolver specified for the article.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e662e-111">A partire da [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] e [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], le versioni a 64 bit di Gestione sincronizzazione Microsoft Windows non possono rilevare sottoscrizioni a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="e662e-111">Beginning with [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] and [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], 64-bit versions of the Windows Synchronization Manager cannot detect 32-bit subscriptions.</span></span>  
  
### <a name="to-enable-the-synchronization-of-pull-subscriptions-with-windows-synchronization-manager"></a><span data-ttu-id="e662e-112">Per abilitare la sincronizzazione delle sottoscrizioni pull con Gestione sincronizzazione Microsoft Windows</span><span class="sxs-lookup"><span data-stu-id="e662e-112">To enable the synchronization of pull subscriptions with Windows Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="e662e-113">Nella pagina **Generale** della finestra di dialogo **Proprietà sottoscrizione - \<Subscriber>: \<SubscriptionDatabase>** selezionare il valore **Abilita** per l'opzione **Usa Gestione sincronizzazione Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="e662e-113">On the **General** page of the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select a value of **Enable** for the **Use Windows Synchronization Manager** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-synchronize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="e662e-114">Per sincronizzare una sottoscrizione pull con Gestione sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="e662e-114">To synchronize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="e662e-115">Avviare Gestione sincronizzazione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e662e-115">Launch Synchronization Manager using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="e662e-116">In Internet Explorer scegliere **Sincronizza**dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="e662e-116">In Internet Explorer, click **Tools**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="e662e-117">Fare clic sul menu **Start**, scegliere **Programmi** o **Tutti i i programmi**, quindi **Accessori**e fare clic su **Sincronizza**.</span><span class="sxs-lookup"><span data-stu-id="e662e-117">Click **Start**, point to **Programs** or **All Programs**, point to **Accessories**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="e662e-118">Fare clic sul menu **Start**dal menu **Esegui**</span><span class="sxs-lookup"><span data-stu-id="e662e-118">Click **Start**, and then click **Run.**</span></span> <span data-ttu-id="e662e-119">Nella finestra di dialogo **Esegui** Digitare `mobsync.exe` il campo **Apri** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e662e-119">In the **Run** dialog box, type `mobsync.exe` in the **Open** field, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="e662e-120">Nella finestra di dialogo **Sincronizzazione elementi** selezionare le sottoscrizioni da sincronizzare.</span><span class="sxs-lookup"><span data-stu-id="e662e-120">In the **Items to Synchronize** dialog box, select the subscriptions to synchronize.</span></span> <span data-ttu-id="e662e-121">Le sottoscrizioni vengono elencate al di sotto delle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="e662e-121">Subscriptions are listed under the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
3.  <span data-ttu-id="e662e-122">Fare clic su **Sincronizza**.</span><span class="sxs-lookup"><span data-stu-id="e662e-122">Click **Synchronize**.</span></span>  
  
### <a name="to-reinitialize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="e662e-123">Per reinizializzare una sottoscrizione pull con Gestione sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="e662e-123">To reinitialize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="e662e-124">Nella finestra di dialogo **Sincronizzazione elementi** selezionare una sottoscrizione e quindi fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e662e-124">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e662e-125">Nella finestra di dialogo **Proprietà sottoscrizione SQL Server** fare clic su **Reinizializza sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="e662e-125">In the **SQL Server Subscription Properties** dialog box, click **Reinitialize Subscription**.</span></span>  
  
3.  <span data-ttu-id="e662e-126">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e662e-126">Click **Yes**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="e662e-127">Alla successiva sincronizzazione, per impostazione predefinita verrà applicato un nuovo snapshot al database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="e662e-127">The next time the subscription is synchronized, by default a new snapshot is applied to the subscription database.</span></span> <span data-ttu-id="e662e-128">Per altre informazioni, vedere [Reinizializzare le sottoscrizioni](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="e662e-128">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e662e-129">La replica di tipo merge consente il caricamento nel server di pubblicazione delle eventuali modifiche in attesa prima dell'applicazione dello snapshot. Tale opzione tuttavia non è disponibile da Gestione sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="e662e-129">Merge replication allows any outstanding changes to be uploaded to the Publisher before the snapshot is applied, but this option is not available from Synchronization Manager.</span></span> <span data-ttu-id="e662e-130">Per caricare le modifiche, sincronizzare la sottoscrizione prima di reinizializzarla.</span><span class="sxs-lookup"><span data-stu-id="e662e-130">To upload changes, synchronize the subscription before reinitializing it.</span></span>  
  
### <a name="to-set-properties-for-a-pull-subscription-in-synchronization-manager"></a><span data-ttu-id="e662e-131">Per impostare le proprietà di una sottoscrizione pull in Gestione sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="e662e-131">To set properties for a pull subscription in Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="e662e-132">Nella finestra di dialogo **Sincronizzazione elementi** selezionare una sottoscrizione e quindi fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e662e-132">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e662e-133">Visualizzare e modificare le proprietà nelle schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="e662e-133">View and modify properties on the following tabs:</span></span>  
  
    -   <span data-ttu-id="e662e-134">**Identificazione**</span><span class="sxs-lookup"><span data-stu-id="e662e-134">**Identification**</span></span>  
  
    -   <span data-ttu-id="e662e-135">**Accesso al Sottoscrittore**, **Accesso al server di distribuzione**e **Accesso al server di pubblicazione** (solo per la replica di tipo merge)</span><span class="sxs-lookup"><span data-stu-id="e662e-135">**Subscriber Login**, **Distributor Login**, and **Publisher Login** (for merge replication only)</span></span>  
  
    -   <span data-ttu-id="e662e-136">**Informazioni server Web** (per le sottoscrizioni di tipo merge nei Sottoscrittori in cui è in esecuzione SQL Server 2005 o versione successiva)</span><span class="sxs-lookup"><span data-stu-id="e662e-136">**Web Server Information** (for merge subscriptions on Subscribers running SQL Server 2005 or later)</span></span>  
  
    -   <span data-ttu-id="e662e-137">**Altri**</span><span class="sxs-lookup"><span data-stu-id="e662e-137">**Other**</span></span>  
  
     <span data-ttu-id="e662e-138">È consigliabile utilizzare l'autenticazione di Windows per tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="e662e-138">It is recommended to use Windows Authentication for all connections.</span></span> <span data-ttu-id="e662e-139">Per informazioni sulle autorizzazioni necessarie con l'agente di distribuzione e l'agente di merge, vedere [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="e662e-139">For information about the permissions required by the Distribution Agent and the Merge Agent, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-a-pull-subscription-from-synchronization-manager"></a><span data-ttu-id="e662e-140">Per rimuovere una sottoscrizione pull da Gestione sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="e662e-140">To remove a pull subscription from Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="e662e-141">Nella finestra di dialogo **Sincronizzazione elementi** selezionare una sottoscrizione e quindi fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e662e-141">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e662e-142">Nella finestra di dialogo **Proprietà sottoscrizione SQL Server** fare clic su **Rimuovi sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="e662e-142">In the **SQL Server Subscription Properties** dialog box, click **Remove Subscription**.</span></span>  
  
3.  <span data-ttu-id="e662e-143">Selezionare un'opzione nella finestra di dialogo **Rimuovi sottoscrizione** .</span><span class="sxs-lookup"><span data-stu-id="e662e-143">Select an option in the **Remove Subscription** dialog box.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-interactive-resolver"></a><span data-ttu-id="e662e-144">Per utilizzare il sistema di risoluzione interattivo</span><span class="sxs-lookup"><span data-stu-id="e662e-144">To use the Interactive Resolver</span></span>  
  
1.  <span data-ttu-id="e662e-145">Abilitare l'articolo e la sottoscrizione per l'utilizzo della risoluzione interattiva.</span><span class="sxs-lookup"><span data-stu-id="e662e-145">Enable the article and subscription to use interactive resolution.</span></span> <span data-ttu-id="e662e-146">Per altre informazioni, vedere [Specificare la risoluzione interattiva dei conflitti per articoli di merge](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span><span class="sxs-lookup"><span data-stu-id="e662e-146">For more information, see [Specify Interactive Conflict Resolution for Merge Articles](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span></span>
  
2.  <span data-ttu-id="e662e-147">In seguito all'inizio della sincronizzazione della sottoscrizione in Gestione sincronizzazione, il sistema di risoluzione interattivo viene avviato automaticamente se la risoluzione interattiva dei conflitti è abilitata e si sono verificati conflitti tra uno o più articoli.</span><span class="sxs-lookup"><span data-stu-id="e662e-147">After the subscription begins synchronizing in Synchronization Manager, the Interactive Resolver launches automatically if interactive conflict resolution is enabled and there are conflicts for one or more articles.</span></span> <span data-ttu-id="e662e-148">In tale sistema i conflitti vengono visualizzati uno alla volta, con un suggerimento di risoluzione per ogni conflitto (in base al sistema di risoluzione dei conflitti specificato al momento della creazione della pubblicazione e della sottoscrizione).</span><span class="sxs-lookup"><span data-stu-id="e662e-148">The Interactive Resolver displays conflicts one at a time, with a suggested resolution for each conflict (based on the resolver specified when the publication and subscription were created).</span></span>  
  
3.  <span data-ttu-id="e662e-149">Facoltativamente, modificare le colonne visualizzate nel sistema di risoluzione interattivo e quindi fare clic su uno dei pulsanti seguenti per risolvere il conflitto:</span><span class="sxs-lookup"><span data-stu-id="e662e-149">Optionally edit any of the columns displayed in the Interactive Resolver, and then click one of the following buttons to resolve the conflict:</span></span>  
  
    -   <span data-ttu-id="e662e-150">**Accetta soluzione proposta**</span><span class="sxs-lookup"><span data-stu-id="e662e-150">**Accept Suggested**</span></span>  
  
    -   <span data-ttu-id="e662e-151">**Accetta server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="e662e-151">**Accept Publisher**</span></span>  
  
    -   <span data-ttu-id="e662e-152">**Accetta Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="e662e-152">**Accept Subscriber**</span></span>  
  
    -   <span data-ttu-id="e662e-153">**Risolvi tutti i conflitti automaticamente** (tutti i conflitti correnti vengono risolti senza ulteriore input)</span><span class="sxs-lookup"><span data-stu-id="e662e-153">**Resolve All Automatically** (all current conflicts are resolved without further input)</span></span>  
  
     <span data-ttu-id="e662e-154">La riga selezionata viene quindi applicata al server di pubblicazione e/o al Sottoscrittore e propagata ad altri nodi nella topologia durante le sincronizzazioni successive.</span><span class="sxs-lookup"><span data-stu-id="e662e-154">The selected row is then applied to the Publisher and/or Subscriber; it is propagated to other nodes in the topology during subsequent synchronizations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e662e-155">Le modifiche vengono applicate solo se fanno parte della riga scelta per la risoluzione.</span><span class="sxs-lookup"><span data-stu-id="e662e-155">Edits are only applied if they are part of the row that is chosen for resolution.</span></span> <span data-ttu-id="e662e-156">Se, ad esempio, si apportano modifiche nel **Server di pubblicazione**e quindi si fa clic su **Accetta Sottoscrittore**, le modifiche verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="e662e-156">For example, if you make edits under **Publisher**, and then click **Accept Subscriber**, the edits are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e662e-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e662e-157">See Also</span></span>  
 [<span data-ttu-id="e662e-158">Interactive Conflict Resolution</span><span class="sxs-lookup"><span data-stu-id="e662e-158">Interactive Conflict Resolution</span></span>](merge/advanced-merge-replication-conflict-interactive-resolution.md)  
  
