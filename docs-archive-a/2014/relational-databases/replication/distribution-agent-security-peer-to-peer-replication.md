---
title: Sicurezza agente di distribuzione (replica peer-to-peer) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.p2pwizard.DA.f1
ms.assetid: def6bf26-c640-4caf-ad30-05d1e649541d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72b5a52fbb3ddc11d0ea6f2c0b26786463e08eaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624631"
---
# <a name="distribution-agent-security-peer-to-peer-replication"></a><span data-ttu-id="ae451-102">Sicurezza agente di distribuzione (replica peer-to-peer)</span><span class="sxs-lookup"><span data-stu-id="ae451-102">Distribution Agent Security (Peer-to-Peer Replication)</span></span>
  <span data-ttu-id="ae451-103">La pagina **Sicurezza agente di distribuzione** consente di specificare gli account utilizzati per eseguire l'agente di distribuzione e per stabilire connessioni ai computer in una topologia peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ae451-103">The **Distribution Agent Security** page allows you to specify the accounts under which the Distribution Agent runs and makes connections to the computers in a peer-to-peer topology.</span></span> <span data-ttu-id="ae451-104">Per informazioni sulle autorizzazioni necessarie per gli agenti e le procedure migliori per la sicurezza della replica, vedere [Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md) e [Procedure consigliate per la sicurezza della replica](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="ae451-104">For information on permissions required by agents and best practices for replication security, see [Replication Agent Security Model](security/replication-agent-security-model.md) and [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae451-105">Se l'agente di distribuzione per una sottoscrizione è già stato configurato in un'esecuzione precedente della procedura guidata, non è possibile modificare le credenziali utilizzate in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="ae451-105">If the Distribution Agent for a subscription has already been configured in a previous run of this wizard, you cannot change the credentials it uses in this wizard.</span></span> <span data-ttu-id="ae451-106">Se vengono specificate nuove credenziali, queste verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="ae451-106">If you specify new credentials, they are ignored.</span></span> <span data-ttu-id="ae451-107">Per modificare le credenziali, utilizzare la finestra di dialogo **Proprietà sottoscrizione** .</span><span class="sxs-lookup"><span data-stu-id="ae451-107">To change credentials, use the **Subscription Properties** dialog box.</span></span> <span data-ttu-id="ae451-108">Per altre informazioni, vedere [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ae451-108">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae451-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ae451-109">Options</span></span>  
 <span data-ttu-id="ae451-110">Fare clic sul pulsante delle proprietà ( **...** ) nella riga di ciascun Sottoscrittore per accedere alla finestra di dialogo **Sicurezza agente di distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="ae451-110">Click the properties button (**...**) in the row for each Subscriber to access the **Distribution Agent Security** dialog box.</span></span> <span data-ttu-id="ae451-111">Per ulteriori informazioni sulle autorizzazioni necessarie per gli account utilizzati dagli agenti, fare clic su **?** nella finestra di dialogo **Sicurezza agente di distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="ae451-111">Click **Help** on the **Distribution Agent Security** dialog box that is launched for more information on the permissions required for accounts used by the agents.</span></span>  
  
 <span data-ttu-id="ae451-112">Dopo l'immissione delle impostazioni in una delle finestre di dialogo, le informazioni di connessione per il Sottoscrittore vengono visualizzate nella griglia.</span><span class="sxs-lookup"><span data-stu-id="ae451-112">After settings have been entered in one of the dialog boxes, connection information for the Subscriber is displayed in the grid.</span></span>  
  
 <span data-ttu-id="ae451-113">**Agente per Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="ae451-113">**Agent for Subscriber**</span></span>  
 <span data-ttu-id="ae451-114">Nome di ciascun peer.</span><span class="sxs-lookup"><span data-stu-id="ae451-114">The name of each peer.</span></span>  
  
 <span data-ttu-id="ae451-115">**Database peer**</span><span class="sxs-lookup"><span data-stu-id="ae451-115">**Peer Database**</span></span>  
 <span data-ttu-id="ae451-116">Il database nel peer che fungerà da database di pubblicazione e da database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ae451-116">The database at the peer that will serve as both a publication database and subscription database.</span></span>  
  
 <span data-ttu-id="ae451-117">**Connessione al server di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="ae451-117">**Connection to Distributor**</span></span>  
 <span data-ttu-id="ae451-118">Contesto in cui viene creata la connessione al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ae451-118">The context under which the connection to the Distributor is made.</span></span> <span data-ttu-id="ae451-119">Le connessioni locali vengono create sempre mediante il contesto dell'account di Windows utilizzato per l'esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ae451-119">Local connections are always made using the context of the Windows account under which the agent runs.</span></span> <span data-ttu-id="ae451-120">In questa procedura guidata vengono create sottoscrizioni push (la connessione locale è quella stabilita con il server di distribuzione), pertanto in questo campo viene sempre visualizzato: **Rappresenta '\<Domain>\\<Login\>'** o **Rappresenta '\<Computer>\\<Login\>'** .</span><span class="sxs-lookup"><span data-stu-id="ae451-120">This wizard creates push subscriptions (the local connection is the connection to the Distributor), so this field will always display: **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span>  
  
 <span data-ttu-id="ae451-121">**Connessione al Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="ae451-121">**Connection to Subscriber**</span></span>  
 <span data-ttu-id="ae451-122">Contesto in cui viene creata la connessione al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="ae451-122">The context under which the connection to the Subscriber is made.</span></span> <span data-ttu-id="ae451-123">La connessione può essere creata tramite il contesto dell'account di Windows utilizzato per l'esecuzione dell'agente o nel contesto di un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae451-123">The connection can be made using the context of the Windows account under which the agent runs or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="ae451-124">In questo campo viene visualizzato uno dei valori seguenti: **Usa l'account di accesso '\<Login>'** , **Rappresenta '\<Domain>\\<Login\>'** o **Rappresenta '\<Computer>\\<Login\>'** .</span><span class="sxs-lookup"><span data-stu-id="ae451-124">The field displays one of the following: **Use login '\<Login>'**, **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ae451-125">consiglia di stabilire tutte le connessioni utilizzando il contesto dell'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="ae451-125">recommends that all connections be made using the context of the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae451-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae451-126">See Also</span></span>  
 <span data-ttu-id="ae451-127">[Amministrare una topologia peer-to-peer &#40;programmazione Transact-SQL della replica&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="ae451-127">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="ae451-128">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="ae451-128">Peer-to-Peer Transactional Replication</span></span>](transactional/peer-to-peer-transactional-replication.md)  
  
  
