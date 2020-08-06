---
title: Sicurezza agente di merge | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.MA.f1
helpviewer_keywords:
- Merge Agent Security dialog box
ms.assetid: 9b86171a-4381-4b39-869a-cdc161e7cd15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecbb044ca87ccfc74c5cb39a016667d15cf7a859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718059"
---
# <a name="merge-agent-security"></a><span data-ttu-id="b80fb-102">Sicurezza agente di merge</span><span class="sxs-lookup"><span data-stu-id="b80fb-102">Merge Agent Security</span></span>
  <span data-ttu-id="b80fb-103">La finestra di dialogo **Sicurezza agente di merge** consente di specificare l'account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] con cui viene eseguito l'agente di merge.</span><span class="sxs-lookup"><span data-stu-id="b80fb-103">The **Merge Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Merge Agent runs.</span></span> <span data-ttu-id="b80fb-104">L'agente di merge viene eseguito nel server di distribuzione per le sottoscrizioni push e nel Sottoscrittore per le sottoscrizioni pull.</span><span class="sxs-lookup"><span data-stu-id="b80fb-104">The Merge Agent runs at the Distributor for push subscriptions and at the Subscriber for pull subscriptions.</span></span> <span data-ttu-id="b80fb-105">L'account di Windows è detto anche *account di processo*, poiché si tratta dell'account con cui viene eseguito il processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="b80fb-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span> <span data-ttu-id="b80fb-106">Le opzioni aggiuntive disponibili in questa finestra di dialogo dipendono dalla modalità con cui si accede a tale finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="b80fb-106">Additional options available in the dialog box depend on how you access it:</span></span>  
  
-   <span data-ttu-id="b80fb-107">Se si accede alla finestra di dialogo dalla Creazione guidata nuova sottoscrizione, è inoltre possibile specificare il contesto in cui l'agente di merge stabilisce le connessioni al Sottoscrittore (per le sottoscrizioni push) o ai server di pubblicazione e di distribuzione (per le sottoscrizioni pull).</span><span class="sxs-lookup"><span data-stu-id="b80fb-107">If the dialog box is accessed from the New Subscription Wizard, it also allows you to specify the context under which the Merge Agent makes connections to the Subscriber (for push subscriptions) or the Publisher and Distributor (for pull subscriptions).</span></span> <span data-ttu-id="b80fb-108">È possibile stabilire la connessione usando l'account di Windows oppure nel contesto di un account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b80fb-108">The connection can be made using the Windows account or under the context of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
-   <span data-ttu-id="b80fb-109">Se si accede alla finestra di dialogo dalla finestra di dialogo **Proprietà sottoscrizione** , specificare il contesto in cui l'agente di merge stabilisce le connessioni facendo clic sul pulsante delle proprietà ( **...** ) nella riga **Connessione al Sottoscrittore** o **Connessione al server di pubblicazione** della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b80fb-109">If the dialog box is accessed from the **Subscription Properties** dialog box, specify the context under which the Merge Agent makes connections by clicking the properties button (**...**) in the **Subscriber Connection** or **Publisher Connection** row of that dialog box.</span></span> <span data-ttu-id="b80fb-110">Per altre informazioni sull'accesso alla finestra di dialogo **Proprietà sottoscrizione**, vedere [Visualizzare e modificare le proprietà delle sottoscrizioni push](view-and-modify-push-subscription-properties.md) e [Visualizzare e modificare le proprietà delle sottoscrizioni pull](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b80fb-110">For more information about accessing the **Subscription Properties** dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and how to: [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
 <span data-ttu-id="b80fb-111">Tutti gli account devono essere validi e per ogni account deve essere stata specificata la password corretta.</span><span class="sxs-lookup"><span data-stu-id="b80fb-111">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="b80fb-112">Gli account e le password vengono convalidati solo dopo l'avvio dell'esecuzione di un agente.</span><span class="sxs-lookup"><span data-stu-id="b80fb-112">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b80fb-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b80fb-113">Options</span></span>  
 <span data-ttu-id="b80fb-114">**Process Account**</span><span class="sxs-lookup"><span data-stu-id="b80fb-114">**Process Account**</span></span>  
 <span data-ttu-id="b80fb-115">Consente di immettere l'account di Windows con cui viene eseguito l'agente di merge.</span><span class="sxs-lookup"><span data-stu-id="b80fb-115">Enter a Windows account under which the Merge Agent runs.</span></span>  
  
-   <span data-ttu-id="b80fb-116">Per le sottoscrizioni push, l'account deve:</span><span class="sxs-lookup"><span data-stu-id="b80fb-116">For push subscriptions, the account must:</span></span>  
  
    -   <span data-ttu-id="b80fb-117">Essere almeno un membro del ruolo predefinito del database **db_owner** nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b80fb-117">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
    -   <span data-ttu-id="b80fb-118">Essere un membro del ruolo PAL.</span><span class="sxs-lookup"><span data-stu-id="b80fb-118">Be a member of the PAL.</span></span>  
  
    -   <span data-ttu-id="b80fb-119">Essere un account di accesso associato a un utente nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b80fb-119">Be a login associated with a user in the publication database.</span></span>  
  
    -   <span data-ttu-id="b80fb-120">Disporre delle autorizzazioni di lettura per la condivisione snapshot.</span><span class="sxs-lookup"><span data-stu-id="b80fb-120">Have read permissions on the snapshot share.</span></span>  
  
-   <span data-ttu-id="b80fb-121">Per le sottoscrizioni pull, l'account deve essere almeno un membro del ruolo predefinito del database **db_owner** nel database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b80fb-121">For pull subscriptions, the account must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
 <span data-ttu-id="b80fb-122">Sono necessarie autorizzazioni aggiuntive nel caso in cui l'account di processo sia rappresentato durante l'attivazione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="b80fb-122">Additional permissions are required if the process account is impersonated when connections are made.</span></span> <span data-ttu-id="b80fb-123">Vedere le sezioni **Connetti al server di pubblicazione e al server di distribuzione** e **Connetti al Sottoscrittore** riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b80fb-123">See the **Connect to the Publisher and Distributor** and **Connect to the Subscriber** sections below.</span></span>  
  
 <span data-ttu-id="b80fb-124">Non è possibile specificare l'**account di processo** per le sottoscrizioni pull di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], in quanto l'agente di merge non viene eseguito nelle istanze di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b80fb-124">**Process Account** cannot be specified for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], because the Merge Agent does not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
 <span data-ttu-id="b80fb-125">**Password** e **Conferma password**</span><span class="sxs-lookup"><span data-stu-id="b80fb-125">**Password** and **Confirm Password**</span></span>  
 <span data-ttu-id="b80fb-126">Immettere la password per l'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="b80fb-126">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="b80fb-127">**Connetti al server di pubblicazione e al server di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="b80fb-127">**Connect to the Publisher and Distributor**</span></span>  
 <span data-ttu-id="b80fb-128">Per le sottoscrizioni push, le connessioni al server di pubblicazione e al server di distribuzione vengono sempre stabilite tramite la rappresentazione dell'account specificato nella casella di testo **Account processo** .</span><span class="sxs-lookup"><span data-stu-id="b80fb-128">For push subscriptions, connections to the Publisher and Distributor are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="b80fb-129">Per le sottoscrizioni pull, scegliere se l'agente di merge deve stabilire le connessioni al server di pubblicazione e al server di distribuzione tramite la rappresentazione dell'account specificato nella casella di testo **Account processo** oppure utilizzando un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b80fb-129">For pull subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="b80fb-130">Se si seleziona l'opzione per l'utilizzo di un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , immettere un account di accesso e una password di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b80fb-130">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="b80fb-131">consiglia di scegliere di rappresentare l'account di Windows anziché di utilizzare un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b80fb-131">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="b80fb-132">L'account di Windows o l'account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzato per la connessione deve:</span><span class="sxs-lookup"><span data-stu-id="b80fb-132">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must:</span></span>  
  
-   <span data-ttu-id="b80fb-133">Essere un membro del ruolo PAL.</span><span class="sxs-lookup"><span data-stu-id="b80fb-133">Be a member of the PAL.</span></span>  
  
-   <span data-ttu-id="b80fb-134">Essere un account di accesso associato a un utente nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b80fb-134">Be a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="b80fb-135">Essere un account di accesso associato a un utente nel database di distribuzione (l'utente può essere l'utente Guest).</span><span class="sxs-lookup"><span data-stu-id="b80fb-135">Be a login associated with a user in the distribution database (the user can be the Guest user).</span></span>  
  
-   <span data-ttu-id="b80fb-136">Disporre delle autorizzazioni di lettura per la condivisione snapshot.</span><span class="sxs-lookup"><span data-stu-id="b80fb-136">Have read permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="b80fb-137">**Connetti al Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="b80fb-137">**Connect to the Subscriber**</span></span>  
 <span data-ttu-id="b80fb-138">Per le sottoscrizioni pull, le connessioni al Sottoscrittore vengono sempre stabilite tramite la rappresentazione dell'account specificato nella casella di testo **Account processo** .</span><span class="sxs-lookup"><span data-stu-id="b80fb-138">For pull subscriptions, connections to the Subscriber are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="b80fb-139">Per le sottoscrizioni push, scegliere se l'agente di merge deve stabilire le connessioni al server di pubblicazione e al server di distribuzione tramite la rappresentazione dell'account specificato nella casella di testo **Account processo** oppure utilizzando un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b80fb-139">For push subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="b80fb-140">Se si seleziona l'opzione per l'utilizzo di un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , immettere un account di accesso e una password di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b80fb-140">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b80fb-141">È consigliabile scegliere di rappresentare l'account di Windows anziché di utilizzare un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b80fb-141">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="b80fb-142">L'account di Windows o l'account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzato per la connessione deve essere almeno un membro del ruolo del database predefinito **db_owner** nel database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b80fb-142">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection to the Subscriber must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80fb-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b80fb-143">See Also</span></span>  
 <span data-ttu-id="b80fb-144">[Gestire gli account di accesso e le password nella replica](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="b80fb-144">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="b80fb-145">[Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="b80fb-145">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="b80fb-146">[Panoramica degli agenti di replica](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b80fb-146">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 <span data-ttu-id="b80fb-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="b80fb-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="b80fb-148">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="b80fb-148">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
