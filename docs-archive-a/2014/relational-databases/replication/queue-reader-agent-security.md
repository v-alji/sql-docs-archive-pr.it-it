---
title: Sicurezza agente di lettura coda | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.QRA.f1
helpviewer_keywords:
- Queue Reader Agent Security dialog box
ms.assetid: 77938da0-2afd-4455-8826-f4a6a9440cb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 22a5e5751184b626ab1af86f01782a42028b5ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636684"
---
# <a name="queue-reader-agent-security"></a><span data-ttu-id="aa30f-102">Sicurezza agente di lettura coda</span><span class="sxs-lookup"><span data-stu-id="aa30f-102">Queue Reader Agent Security</span></span>
  <span data-ttu-id="aa30f-103">La finestra di dialogo **Sicurezza agente di lettura coda** consente di specificare l'account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con cui viene eseguito l'agente di lettura coda e vengono stabilite le connessioni locali al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="aa30f-103">The **Queue Reader Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Queue Reader Agent runs and makes local connections to the Distributor.</span></span> <span data-ttu-id="aa30f-104">L'agente si connette al server di pubblicazione utilizzando l'account specificato nella finestra di dialogo **Proprietà server di pubblicazione** , alla quale è possibile accedere dalla finestra di dialogo **Proprietà server di distribuzione** . L'agente si connette al Sottoscrittore utilizzando lo stesso contesto dell'agente di distribuzione per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="aa30f-104">The agent connects to the Publisher using the account specified in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box); the agent connects to the Subscriber using the same context as the Distribution Agent for the subscription.</span></span> <span data-ttu-id="aa30f-105">Per altre informazioni, vedere [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="aa30f-105">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="aa30f-106">L'account deve essere valido è deve essere stata specificata la password corretta.</span><span class="sxs-lookup"><span data-stu-id="aa30f-106">The account must be valid with the correct password specified.</span></span> <span data-ttu-id="aa30f-107">Gli account e le password vengono convalidati solo dopo l'avvio dell'esecuzione di un agente.</span><span class="sxs-lookup"><span data-stu-id="aa30f-107">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa30f-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="aa30f-108">Options</span></span>  
 <span data-ttu-id="aa30f-109">**Account processo**</span><span class="sxs-lookup"><span data-stu-id="aa30f-109">**Process account**</span></span>  
 <span data-ttu-id="aa30f-110">Consente di immettere l'account di Windows con cui viene eseguito l'agente di lettura coda nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="aa30f-110">Enter a Windows account under which the Queue Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="aa30f-111">L'account di Windows specificato deve essere almeno membro del ruolo predefinito del database **db_owner** nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="aa30f-111">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="aa30f-112">**Password** e **Conferma password**</span><span class="sxs-lookup"><span data-stu-id="aa30f-112">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="aa30f-113">Immettere la password per l'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="aa30f-113">Enter the password for the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa30f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa30f-114">See Also</span></span>  
 <span data-ttu-id="aa30f-115">[Gestire gli account di accesso e le password nella replica](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="aa30f-115">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="aa30f-116">[Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="aa30f-116">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="aa30f-117">[Panoramica degli agenti di replica](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="aa30f-117">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="aa30f-118">Procedure consigliate per la sicurezza della replica</span><span class="sxs-lookup"><span data-stu-id="aa30f-118">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
