---
title: Sottoscrittori | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscribers.f1
helpviewer_keywords:
- Subscribers [SQL Server replication]
ms.assetid: 43fb2454-c220-4d25-a826-83c332eb00d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c5281a53b755bc171cdf96e7856e38ee6a54a1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626626"
---
# <a name="subscribers"></a><span data-ttu-id="04d59-102">Sottoscrittori</span><span class="sxs-lookup"><span data-stu-id="04d59-102">Subscribers</span></span>
  <span data-ttu-id="04d59-103">Specificare i [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sottoscrittori o non che riceveranno una sottoscrizione alla pubblicazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="04d59-103">Specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers that will receive a subscription to the selected publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="04d59-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="04d59-104">Options</span></span>  
 <span data-ttu-id="04d59-105">**Sottoscrittori**</span><span class="sxs-lookup"><span data-stu-id="04d59-105">**Subscribers**</span></span>  
 <span data-ttu-id="04d59-106">Selezionare la casella di controllo nella griglia per abilitare l'origine dei dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o non[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] corrispondente come Sottoscrittore della pubblicazione scelta nella pagina **Pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="04d59-106">Select the check box in the grid to enable the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source as a Subscriber to the publication chosen on the **Publication** page.</span></span> <span data-ttu-id="04d59-107">Se il Sottoscrittore non è incluso nell'elenco, fare clic su **Aggiungi Sottoscrittore** o su **Aggiungi Sottoscrittore SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="04d59-107">If the Subscriber is not listed, click **Add Subscriber** or **Add SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="04d59-108">**Database di sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="04d59-108">**Subscription database**</span></span>  
 <span data-ttu-id="04d59-109">Le informazioni visualizzate e le azioni disponibili in questa colonna dipendono dal tipo di Sottoscrittore visualizzato nella colonna **Sottoscrittori** :</span><span class="sxs-lookup"><span data-stu-id="04d59-109">The information displayed in and actions available from this column depend on the type of Subscriber listed in the **Subscribers** column:</span></span>  
  
-   <span data-ttu-id="04d59-110">Per i Sottoscrittori [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] selezionare un database di sottoscrizione nell'elenco **Database di sottoscrizione** oppure creare un nuovo database selezionando il comando **Nuovo database** nello stesso elenco.</span><span class="sxs-lookup"><span data-stu-id="04d59-110">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, select a subscription database from the **Subscription Database** list or create a new database by selecting the **New database** command from the same list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04d59-111">Se si sta abilitando il server di pubblicazione come Sottoscrittore, il database di sottoscrizione deve essere diverso dal database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="04d59-111">If you are enabling the Publisher as a Subscriber, the subscription database must be different from the publication database.</span></span>  
  
-   <span data-ttu-id="04d59-112">Il database di sottoscrizione non viene visualizzato per i Sottoscrittori non[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04d59-112">For non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, the subscription database is not displayed.</span></span> <span data-ttu-id="04d59-113">Specificare il database e le altre informazioni di connessione nel campo **Nome origine dati** della finestra di dialogo **Aggiungi Sottoscrittore non SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="04d59-113">Specify the database, along with other connection information, in the **Data source name** field of the **Add Non-SQL Server** dialog box.</span></span> <span data-ttu-id="04d59-114">Questa finestra di dialogo è disponibile facendo clic su **Aggiungi Sottoscrittore** e quindi facendo clic su **Aggiungi Sottoscrittore non SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="04d59-114">This dialog box is available by clicking **Add Subscriber** and then clicking **Add Non-SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="04d59-115">**Aggiungi Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="04d59-115">**Add Subscriber**</span></span>  
 <span data-ttu-id="04d59-116">Consente di aggiungere un server all'elenco dei server attivabili come Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="04d59-116">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="04d59-117">Questo pulsante viene visualizzato se vengono soddisfatte tutte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04d59-117">This button is displayed when all of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="04d59-118">La pubblicazione selezionata è una pubblicazione snapshot o transazionale che non supporta le sottoscrizioni aggiornabili.</span><span class="sxs-lookup"><span data-stu-id="04d59-118">The publication you selected is a snapshot or transactional publication that does not support updating subscriptions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04d59-119">Se la pubblicazione che si sta sottoscrivendo dispone di sottoscrizioni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e non è ancora abilitata per i Sottoscrittori non[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , non è possibile aggiungere una sottoscrizione non[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04d59-119">If the publication you are subscribing to has [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscriptions and the publication is not already enabled for non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, you cannot add a non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscription.</span></span>  
  
-   <span data-ttu-id="04d59-120">La sottoscrizione è una sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="04d59-120">The subscription is a push subscription.</span></span>  
  
-   <span data-ttu-id="04d59-121">Il server della pubblicazione selezionata è [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="04d59-121">The Publisher of the selected publication is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later.</span></span>  
  
 <span data-ttu-id="04d59-122">Facendo clic su **Aggiungi Sottoscrittore** viene visualizzato un menu con due opzioni: **Aggiungi Sottoscrittore SQL Server** e **Aggiungi Sottoscrittore non SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="04d59-122">Clicking **Add Subscriber** shows a menu with two choices: **Add SQL Server Subscriber** and **Add Non-SQL Server Subscriber**.</span></span> <span data-ttu-id="04d59-123">Scegliere **Aggiungi Sottoscrittore non SQL Server** per aggiungere un Sottoscrittore Oracle o IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="04d59-123">Click **Add Non-SQL Server Subscriber** to add an Oracle or IBM DB2 Subscriber.</span></span>  
  
 <span data-ttu-id="04d59-124">**Aggiungi Sottoscrittore SQL Server**</span><span class="sxs-lookup"><span data-stu-id="04d59-124">**Add SQL Server Subscriber**</span></span>  
 <span data-ttu-id="04d59-125">Consente di aggiungere un server all'elenco dei server attivabili come Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="04d59-125">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="04d59-126">Questo pulsante viene visualizzato se viene soddisfatta una o più delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04d59-126">This button is displayed when one or more of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="04d59-127">La pubblicazione selezionata è una pubblicazione di tipo merge, snapshot o transazionale che supporta le sottoscrizioni aggiornabili.</span><span class="sxs-lookup"><span data-stu-id="04d59-127">The publication you selected is a merge publication, or a snapshot or transactional publication that supports updating subscriptions.</span></span>  
  
-   <span data-ttu-id="04d59-128">La sottoscrizione è una sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="04d59-128">The subscription is a pull subscription.</span></span>  
  
-   <span data-ttu-id="04d59-129">Nel server di pubblicazione della pubblicazione selezionata è in esecuzione una versione di SQL Server precedente a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04d59-129">The Publisher of the selected publication is earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="04d59-130">Per le versioni precedenti il pulsante viene visualizzato solo se viene soddisfatta una o più delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04d59-130">For earlier versions, the button is displayed only if one or more of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="04d59-131">L'utente è membro del ruolo predefinito del server **sysadmin** nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="04d59-131">You are a member of the **sysadmin** fixed server role at the Publisher.</span></span>  
  
    -   <span data-ttu-id="04d59-132">Il Sottoscrittore è stato aggiunto nella pagina **Sottoscrittori** della finestra di dialogo **Proprietà server di pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="04d59-132">The Subscriber has been added on the **Subscribers** page of the **Publisher Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="04d59-133">La pubblicazione consente le sottoscrizioni anonime.</span><span class="sxs-lookup"><span data-stu-id="04d59-133">The publication allows anonymous subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d59-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04d59-134">See Also</span></span>  
 <span data-ttu-id="04d59-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="04d59-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="04d59-136">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="04d59-136">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="04d59-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="04d59-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="04d59-138">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="04d59-138">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
