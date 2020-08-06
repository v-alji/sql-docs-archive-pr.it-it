---
title: MSSQL_ENG024070 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG024070 error
ms.assetid: 23ac7e00-fab6-429b-9f85-2736a322aa65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fcfcb96b284d46d46f63af4a650f925ef2de73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714167"
---
# <a name="mssql_eng024070"></a><span data-ttu-id="cb2fb-102">MSSQL_ENG024070</span><span class="sxs-lookup"><span data-stu-id="cb2fb-102">MSSQL_ENG024070</span></span>
    
## <a name="message-details"></a><span data-ttu-id="cb2fb-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="cb2fb-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb2fb-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="cb2fb-104">Product Name</span></span>|<span data-ttu-id="cb2fb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb2fb-105">SQL Server</span></span>|  
|<span data-ttu-id="cb2fb-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="cb2fb-106">Event ID</span></span>|<span data-ttu-id="cb2fb-107">24070</span><span class="sxs-lookup"><span data-stu-id="cb2fb-107">24070</span></span>|  
|<span data-ttu-id="cb2fb-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="cb2fb-108">Event Source</span></span>|<span data-ttu-id="cb2fb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cb2fb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cb2fb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cb2fb-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="cb2fb-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="cb2fb-111">Symbolic Name</span></span>||  
|<span data-ttu-id="cb2fb-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="cb2fb-112">Message Text</span></span>|<span data-ttu-id="cb2fb-113">Il client non dispone di un privilegio necessario.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-113">A required privilege is not held by the client.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cb2fb-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="cb2fb-114">Explanation</span></span>  
 <span data-ttu-id="cb2fb-115">Questo errore generale può essere generato indipendentemente dal fatto che la replica venga utilizzata o meno.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-115">This is a general error that can be raised regardless of whether replication is being used.</span></span> <span data-ttu-id="cb2fb-116">Per un server di una topologia di replica, l'errore viene normalmente generato in seguito alla modifica dell'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tramite Gestione controllo servizi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, anziché tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cb2fb-116">For a server in a replication topology, the error is typically raised because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account is changed by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Service Control Manager instead of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="cb2fb-117">Quando si tenta di eseguire un processo di agente dopo aver modificato l'account di servizio, il processo potrebbe avere esito negativo e restituire un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="cb2fb-117">When you try to run an agent job after changing the service account, the job might fail with an error message that is similar to the following:</span></span>  
  
 <span data-ttu-id="cb2fb-118">"Eseguito come utente: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="cb2fb-118">"Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="cb2fb-119">Replica-sottosistema snapshot replica: errore dell'agente \<AgentName> .</span><span class="sxs-lookup"><span data-stu-id="cb2fb-119">Replication-Replication Snapshot Subsystem: agent \<AgentName> failed.</span></span> <span data-ttu-id="cb2fb-120">Eseguito come utente: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="cb2fb-120">Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="cb2fb-121">Il client non dispone di un privilegio necessario.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-121">A required privilege is not held by the client.</span></span> <span data-ttu-id="cb2fb-122">Passaggio non riuscito.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-122">The step failed.</span></span> <span data-ttu-id="cb2fb-123">`[SQLSTATE 42000] (Error 14151)`.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-123">`[SQLSTATE 42000] (Error 14151)`.</span></span> <span data-ttu-id="cb2fb-124">Passaggio non riuscito."</span><span class="sxs-lookup"><span data-stu-id="cb2fb-124">The step failed."</span></span>  
  
 <span data-ttu-id="cb2fb-125">Questo problema si verifica perché Gestione controllo servizi di Windows non concede le autorizzazioni necessarie al nuovo account di servizio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-125">This problem occurs because the Windows Service Control Manager cannot grant the required permissions to the new service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cb2fb-126">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="cb2fb-126">User Action</span></span>  
 <span data-ttu-id="cb2fb-127">Per evitare questo problema in futuro, utilizzare sempre Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anziché Gestione controllo servizi di Windows per modificare gli account di servizio e le password.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-127">To avoid this problem in the future, always use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager instead of the Windows Service Control Manager to change service accounts and passwords.</span></span>  
  
 <span data-ttu-id="cb2fb-128">Per risolvere il problema, utilizzare Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per ripristinare l'account di servizio originale.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-128">To resolve this problem, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change the service account back to the original account.</span></span> <span data-ttu-id="cb2fb-129">Utilizzare quindi Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per modificare il nuovo account.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-129">Then, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change to the new account.</span></span> <span data-ttu-id="cb2fb-130">Durante questa operazione, Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aggiunge il nuovo account al gruppo di sicurezza seguente:</span><span class="sxs-lookup"><span data-stu-id="cb2fb-130">When you do this, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager adds the new account to the following security group:</span></span>  
  
 <span data-ttu-id="cb2fb-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span><span class="sxs-lookup"><span data-stu-id="cb2fb-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span></span>  
  
 <span data-ttu-id="cb2fb-132">L'appartenenza a questo gruppo di sicurezza consente al nuovo account di ottenere le autorizzazioni necessarie per eseguire il processo dell'agente di replica.</span><span class="sxs-lookup"><span data-stu-id="cb2fb-132">Being a member of this security group grants to the new account the required permissions to run the replication agent job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb2fb-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb2fb-133">See Also</span></span>  
 <span data-ttu-id="cb2fb-134">[Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="cb2fb-134">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="cb2fb-135">[Gestire gli account di accesso e le password nella replica](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="cb2fb-135">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 [<span data-ttu-id="cb2fb-136">Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb2fb-136">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
