---
title: Sicurezza agente snapshot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.SSA.f1
helpviewer_keywords:
- Snapshot Agent Security dialog box
ms.assetid: 64e84c67-acc6-4906-98d4-3451767363fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 288dc294b7ace9ea5cb098c8deec53c3ae4569a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637753"
---
# <a name="snapshot-agent-security"></a><span data-ttu-id="621af-102">Sicurezza agente snapshot</span><span class="sxs-lookup"><span data-stu-id="621af-102">Snapshot Agent Security</span></span>
  <span data-ttu-id="621af-103">La finestra di dialogo **Sicurezza agente snapshot** consente di specificare:</span><span class="sxs-lookup"><span data-stu-id="621af-103">The **Snapshot Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="621af-104">L'account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con cui viene eseguito l'agente snapshot nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="621af-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="621af-105">L'account di Windows è detto anche *account di processo*, poiché si tratta dell'account con cui viene eseguito il processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="621af-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="621af-106">Il contesto nel quale l'agente snapshot stabilisce le connessioni al server di pubblicazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="621af-106">The context under which the Snapshot Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="621af-107">La connessione può essere stabilita tramite rappresentazione dell'account di Windows oppure nel contesto di un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="621af-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="621af-108">L'agente snapshot stabilisce le connessioni al server di pubblicazione anche quando il server di pubblicazione e il server di distribuzione si trovano nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="621af-108">The Snapshot Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="621af-109">L'agente snapshot stabilisce inoltre le connessioni al server di distribuzione. Tali connessioni vengono sempre stabilite tramite rappresentazione dell'account di  Windows con cui viene eseguito l'agente.</span><span class="sxs-lookup"><span data-stu-id="621af-109">The Snapshot Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="621af-110">Per i server di pubblicazione Oracle, specificare il contesto in cui l'agente snapshot si connette al server di pubblicazione nella finestra di dialogo **Proprietà server di pubblicazione** , alla quale è possibile accedere dalla finestra di dialogo **Proprietà server di distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="621af-110">For Oracle Publishers, specify the context under which the Snapshot Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="621af-111">Per altre informazioni, vedere [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="621af-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="621af-112">Tutti gli account devono essere validi e per ogni account deve essere stata specificata la password corretta.</span><span class="sxs-lookup"><span data-stu-id="621af-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="621af-113">Gli account e le password vengono convalidati solo dopo l'avvio dell'esecuzione di un agente.</span><span class="sxs-lookup"><span data-stu-id="621af-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="621af-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="621af-114">Options</span></span>  
 <span data-ttu-id="621af-115">**Account processo**</span><span class="sxs-lookup"><span data-stu-id="621af-115">**Process account**</span></span>  
 <span data-ttu-id="621af-116">Consente di immettere un account di Windows con cui eseguire l'agente snapshot nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="621af-116">Enter a Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="621af-117">L'account di Windows specificato deve:</span><span class="sxs-lookup"><span data-stu-id="621af-117">The Windows account you specify must:</span></span>  
  
-   <span data-ttu-id="621af-118">Essere almeno un membro del ruolo predefinito del database **db_owner** nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="621af-118">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
-   <span data-ttu-id="621af-119">Disporre delle autorizzazioni di scrittura per la condivisione snapshot.</span><span class="sxs-lookup"><span data-stu-id="621af-119">Have write permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="621af-120">**Password** e **Conferma password**</span><span class="sxs-lookup"><span data-stu-id="621af-120">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="621af-121">Immettere la password per l'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="621af-121">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="621af-122">**Connessione al server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="621af-122">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="621af-123">Consente di scegliere se l'agente snapshot deve stabilire le connessioni al server di distribuzione tramite rappresentazione dell'account specificato nella casella di testo **Account processo** oppure utilizzando un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="621af-123">Select whether the Snapshot Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="621af-124">Se si seleziona l'opzione per l'utilizzo di un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , immettere un account di accesso e una password di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="621af-124">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="621af-125">È consigliabile scegliere di rappresentare l'account di Windows anziché di utilizzare un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="621af-125">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="621af-126">L'account di Windows o l'account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzato per la connessione deve essere almeno un membro del ruolo del database predefinito **db_owner** nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="621af-126">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621af-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="621af-127">See Also</span></span>  
 <span data-ttu-id="621af-128">[Gestire gli account di accesso e le password nella replica](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="621af-128">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="621af-129">[Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="621af-129">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="621af-130">[Panoramica degli agenti di replica](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="621af-130">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="621af-131">Procedure consigliate per la sicurezza della replica</span><span class="sxs-lookup"><span data-stu-id="621af-131">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
