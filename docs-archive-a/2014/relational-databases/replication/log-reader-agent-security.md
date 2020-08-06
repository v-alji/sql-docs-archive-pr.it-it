---
title: Sicurezza agente di lettura log | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.LRA.f1
helpviewer_keywords:
- Log Reader Agent Security dialog box
ms.assetid: d6981e74-ddb8-41b8-9ea1-56c2ece63b8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4be41aa9135e20a334616b9cb9d76a773f8d0e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723691"
---
# <a name="log-reader-agent-security"></a><span data-ttu-id="a0a43-102">Sicurezza agente di lettura log</span><span class="sxs-lookup"><span data-stu-id="a0a43-102">Log Reader Agent Security</span></span>
  <span data-ttu-id="a0a43-103">La finestra di dialogo **Sicurezza agente di lettura log** consente di specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0a43-103">The **Log Reader Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="a0a43-104">L'account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows utilizzato per l'esecuzione dell'agente di lettura log nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a0a43-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="a0a43-105">L'account di Windows è detto anche *account di processo*, poiché si tratta dell'account con cui viene eseguito il processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="a0a43-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="a0a43-106">Il contesto in cui l'agente di lettura log stabilisce le connessioni al server di pubblicazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0a43-106">The context under which the Log Reader Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="a0a43-107">La connessione può essere stabilita tramite rappresentazione dell'account di Windows oppure nel contesto di un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a0a43-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0a43-108">L'agente di lettura log stabilisce le connessioni al server di pubblicazione anche se il server di pubblicazione e il server di distribuzione si trovano sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="a0a43-108">The Log Reader Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="a0a43-109">L'agente di lettura log stabilisce inoltre le connessioni al server di distribuzione, sempre tramite la rappresentazione dell'account di Windows utilizzato per l'esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="a0a43-109">The Log Reader Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="a0a43-110">Per i server di pubblicazione Oracle specificare un contesto utilizzato dall'agente di lettura log per creare la connessione al server di pubblicazione nella finestra di dialogo **Proprietà server di pubblicazione** , disponibile tramite la finestra di dialogo **Proprietà server di distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="a0a43-110">For Oracle Publishers, specify the context under which the Log Reader Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="a0a43-111">Per altre informazioni, vedere [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a0a43-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="a0a43-112">Tutti gli account devono essere validi e per ogni account deve essere stata specificata la password corretta.</span><span class="sxs-lookup"><span data-stu-id="a0a43-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="a0a43-113">Gli account e le password vengono convalidati solo dopo l'avvio dell'esecuzione di un agente.</span><span class="sxs-lookup"><span data-stu-id="a0a43-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a0a43-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a0a43-114">Options</span></span>  
 <span data-ttu-id="a0a43-115">**Account processo**</span><span class="sxs-lookup"><span data-stu-id="a0a43-115">**Process account**</span></span>  
 <span data-ttu-id="a0a43-116">Consente di immettere un account di Windows utilizzato per l'esecuzione dell'agente di lettura log nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a0a43-116">Enter a Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="a0a43-117">L'account di Windows specificato deve essere almeno membro del ruolo predefinito del database **db_owner** nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a0a43-117">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="a0a43-118">**Password** e **Conferma password**</span><span class="sxs-lookup"><span data-stu-id="a0a43-118">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="a0a43-119">Immettere la password per l'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="a0a43-119">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="a0a43-120">**Connessione al server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="a0a43-120">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="a0a43-121">Consente di specificare se l'agente di lettura log deve stabilire connessioni al server di pubblicazione tramite la rappresentazione dell'account specificato nella casella di testo **Account processo** o tramite un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0a43-121">Select whether the Log Reader Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="a0a43-122">Se si seleziona l'opzione per l'utilizzo di un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , immettere un account di accesso e una password di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0a43-122">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="a0a43-123">consiglia di scegliere di rappresentare l'account di Windows anziché di utilizzare un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0a43-123">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="a0a43-124">L'account di Windows o l'account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzato per la connessione deve essere almeno un membro del ruolo del database predefinito **db_owner** nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="a0a43-124">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a43-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0a43-125">See Also</span></span>  
 <span data-ttu-id="a0a43-126">[Gestire gli account di accesso e le password nella replica](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="a0a43-126">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="a0a43-127">[Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="a0a43-127">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="a0a43-128">[Panoramica degli agenti di replica](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="a0a43-128">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="a0a43-129">Procedure consigliate per la sicurezza della replica</span><span class="sxs-lookup"><span data-stu-id="a0a43-129">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
