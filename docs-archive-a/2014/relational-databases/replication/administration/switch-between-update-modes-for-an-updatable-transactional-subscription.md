---
title: Passare da una modalità di aggiornamento all'altra per una sottoscrizione transazionale aggiornabile | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, updatable subscriptions
- updatable subscriptions, update modes
- subscriptions [SQL Server replication], updatable
ms.assetid: ab5ebab1-7ee4-41f4-999b-b4f0c420c921
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c31814d1e2ab6fac64ffcde883f3cac2439828a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638387"
---
# <a name="switch-between-update-modes-for-an-updatable-transactional-subscription"></a><span data-ttu-id="f5295-102">Passaggio da una modalità di aggiornamento all'altra per una sottoscrizione transazionale aggiornabile</span><span class="sxs-lookup"><span data-stu-id="f5295-102">Switch Between Update Modes for an Updatable Transactional Subscription</span></span>
  <span data-ttu-id="f5295-103">In questo argomento viene descritto come passare da una modalità di aggiornamento all'altra per una sottoscrizione con transazione aggiornabile in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5295-103">This topic describes how to switch between update modes for an updatable transaction subscription in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f5295-104">Per specificare la modalità per le sottoscrizioni aggiornabili, utilizzare la Creazione guidata nuova sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="f5295-104">Specify the mode for updatable subscriptions using the New Subscription Wizard.</span></span> <span data-ttu-id="f5295-105">Per informazioni sull'impostazione della modalità durante l'uso di questa procedura guidata, vedere [Visualizzare e modificare le proprietà delle sottoscrizioni pull](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f5295-105">For information about setting the mode when using this wizard, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f5295-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f5295-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f5295-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f5295-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f5295-108">È possibile eseguire il failover dall'aggiornamento immediato a quello in coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="f5295-108">You can fail over from immediate to queued updating at any time.</span></span> <span data-ttu-id="f5295-109">In seguito, sarà tuttavia possibile tornare all'aggiornamento immediato solo dopo la connessione del Sottoscrittore e del server di pubblicazione e l'applicazione da parte dell'agente di lettura coda di tutti i messaggi in sospeso nella coda al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="f5295-109">After you do, however, you cannot return to immediate updating until the Subscriber and Publisher are connected and the Queue Reader Agent has applied all pending messages in the queue to the Publisher.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f5295-110">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="f5295-110">Recommendations</span></span>  
  
-   <span data-ttu-id="f5295-111">Se una sottoscrizione ad aggiornamento di una pubblicazione transazionale supporta il failover da una modalità di aggiornamento a un'altra, è possibile passare a livello programmatico tra le modalità di aggiornamento, al fine di gestire situazioni in cui la connettività cambia per un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="f5295-111">When an updating subscription to a transactional publication supports failover from one updating mode to another, you can programmatically switch update modes to handle situations when connectivity changes for a short period of time.</span></span> <span data-ttu-id="f5295-112">La modalità di aggiornamento può essere impostata a livello di programmazione e su richiesta utilizzando le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="f5295-112">The update mode can be set programmatically and on demand using replication stored procedures.</span></span> <span data-ttu-id="f5295-113">Per altre informazioni, vedere [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="f5295-113">For more information, see [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f5295-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f5295-114">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5295-115">Per cambiare la modalità di aggiornamento dopo avere creato la sottoscrizione, è necessario impostare la proprietà **update_mode** sul valore **failover** , che consente di passare dall'aggiornamento immediato all'aggiornamento in coda, oppure sul valore **queued failover** , che consente di passare dall'aggiornamento in coda all'aggiornamento immediato, quando viene creata la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="f5295-115">To change the update mode after the subscription is created, the **update_mode** property must be set to **failover** (which allows a switch from immediate updating to queued updating) or **queued failover** (which allows a switch from queued updating to immediate updating) when the subscription is created.</span></span> <span data-ttu-id="f5295-116">Queste proprietà vengono impostate automaticamente nella Creazione guidata nuova sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="f5295-116">These properties are set automatically in the New Subscription Wizard.</span></span>  
  
#### <a name="to-set-the-updating-mode-for-a-push-subscription"></a><span data-ttu-id="f5295-117">Per impostare la modalità di aggiornamento per una sottoscrizione push</span><span class="sxs-lookup"><span data-stu-id="f5295-117">To set the updating mode for a push subscription</span></span>  
  
1.  <span data-ttu-id="f5295-118">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="f5295-118">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="f5295-119">Espandere la cartella **Replica** e quindi la cartella **Sottoscrizioni locali** .</span><span class="sxs-lookup"><span data-stu-id="f5295-119">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="f5295-120">Fare clic con il pulsante destro del mouse sulla sottoscrizione per la quale si desidera impostare la modalità di aggiornamento e quindi scegliere **Imposta metodo di aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="f5295-120">Right-click the subscription for which you want to set the update mode, and then click **Set Update Method**.</span></span>  
  
4.  <span data-ttu-id="f5295-121">Nella finestra di dialogo **Imposta metodo di aggiornamento - \<Subscriber>:\<SubscriptionDatabase>** selezionare il pulsante di opzione **Aggiornamento immediato** o **Aggiornamento in coda**.</span><span class="sxs-lookup"><span data-stu-id="f5295-121">In the **Set Update Method - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select **Immediate updating** or **Queued updating**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-set-the-updating-mode-for-a-pull-subscription"></a><span data-ttu-id="f5295-122">Per impostare la modalità di aggiornamento per una sottoscrizione pull</span><span class="sxs-lookup"><span data-stu-id="f5295-122">To set the updating mode for a pull subscription</span></span>  
  
1.  <span data-ttu-id="f5295-123">Nella finestra di dialogo **Proprietà sottoscrizione - \<Publisher>:\<PublicationDatabase>** selezionare **Replica le modifiche immediatamente** o **Accoda le modifiche** per l'opzione **Metodo di aggiornamento del Sottoscrittore**.</span><span class="sxs-lookup"><span data-stu-id="f5295-123">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, select a value of **Immediately replicate changes** or **Queue changes** for the **Subscriber update method** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="f5295-124">Per altre informazioni sull'accesso alla finestra di dialogo **Proprietà sottoscrizione - \<Publisher>:\<PublicationDatabase>** , vedere [Visualizzare e modificare le proprietà delle sottoscrizioni push](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f5295-124">For more information about accessing the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f5295-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f5295-125">Using Transact-SQL</span></span>  
  
#### <a name="to-switch-between-update-modes"></a><span data-ttu-id="f5295-126">Per passare da una modalità di aggiornamento all'altra</span><span class="sxs-lookup"><span data-stu-id="f5295-126">To switch between update modes</span></span>  
  
1.  <span data-ttu-id="f5295-127">Verificare che la sottoscrizione supporti il failover eseguendo [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) per una sottoscrizione pull o [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) per una sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="f5295-127">Verify that the subscription supports failover by executing [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) for a pull subscription or [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) for a push subscription.</span></span> <span data-ttu-id="f5295-128">Se il valore di **update mode** nel set di risultati è **3** o **4**, il failover è supportato.</span><span class="sxs-lookup"><span data-stu-id="f5295-128">If the value of **update mode** in the result set is **3** or **4**, failover is supported.</span></span>  
  
2.  <span data-ttu-id="f5295-129">Nel database di sottoscrizione del Sottoscrittore eseguire [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f5295-129">At the Subscriber on the subscription database, execute [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span></span> <span data-ttu-id="f5295-130">Specificare **@publisher** , **@publisher_db** , **@publication** e uno dei valori seguenti per **@failover_mode** :</span><span class="sxs-lookup"><span data-stu-id="f5295-130">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@failover_mode**:</span></span>  
  
    -   <span data-ttu-id="f5295-131">**queued** : viene eseguito il failover all'aggiornamento in coda in caso di perdita temporanea della connettività.</span><span class="sxs-lookup"><span data-stu-id="f5295-131">**queued** - fail over to queued updating when connectivity has been temporarily lost.</span></span>  
  
    -   <span data-ttu-id="f5295-132">**immediate** : viene eseguito il failover all'aggiornamento immediato quando la connettività viene ripristinata.</span><span class="sxs-lookup"><span data-stu-id="f5295-132">**immediate** - fail over to immediate updating when connectivity has been restored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5295-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5295-133">See Also</span></span>  
 [<span data-ttu-id="f5295-134">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="f5295-134">Updatable Subscriptions for Transactional Replication</span></span>](../transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
