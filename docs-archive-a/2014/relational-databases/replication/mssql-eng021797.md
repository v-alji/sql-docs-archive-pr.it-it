---
title: MSSQL_ENG021797 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021797 error
ms.assetid: 54d83a1e-43fd-449c-a2b2-fdda2609a534
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d33ade7e7eea9fa9e95453a5b232447f7b222b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714175"
---
# <a name="mssql_eng021797"></a><span data-ttu-id="a53ef-102">MSSQL_ENG021797</span><span class="sxs-lookup"><span data-stu-id="a53ef-102">MSSQL_ENG021797</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a53ef-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="a53ef-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a53ef-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a53ef-104">Product Name</span></span>|<span data-ttu-id="a53ef-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a53ef-105">SQL Server</span></span>|  
|<span data-ttu-id="a53ef-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a53ef-106">Event ID</span></span>|<span data-ttu-id="a53ef-107">21797</span><span class="sxs-lookup"><span data-stu-id="a53ef-107">21797</span></span>|  
|<span data-ttu-id="a53ef-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a53ef-108">Event Source</span></span>|<span data-ttu-id="a53ef-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a53ef-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a53ef-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a53ef-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a53ef-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a53ef-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a53ef-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a53ef-112">Message Text</span></span>|<span data-ttu-id="a53ef-113">'%s' deve essere un account di accesso di Windows valido con formato: 'COMPUTER\\Account di accesso' o 'DOMINIO\\Account di accesso'.</span><span class="sxs-lookup"><span data-stu-id="a53ef-113">'%s' must be a valid Windows Login in the form: 'MACHINE\Login' or 'DOMAIN\Login'.</span></span> <span data-ttu-id="a53ef-114">Vedere la documentazione relativa a '%s'.</span><span class="sxs-lookup"><span data-stu-id="a53ef-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a53ef-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a53ef-115">Explanation</span></span>  
 <span data-ttu-id="a53ef-116">Questo errore viene generato dalle stored procedure di replica seguenti se il valore specificato per il **@job_login** parametro è null o non valido.</span><span class="sxs-lookup"><span data-stu-id="a53ef-116">This error is raised by the following replication stored procedures if the value specified for the **@job_login** parameter is null or not valid.</span></span> <span data-ttu-id="a53ef-117">Questo errore può verificarsi se un membro del ruolo predefinito del database **db_owner** esegue script di precedenti versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a53ef-117">This error can occur if a member of the **db_owner** fixed database role runs scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a53ef-118">Il modello di sicurezza in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]è cambiato ed è necessario aggiornare questi script.</span><span class="sxs-lookup"><span data-stu-id="a53ef-118">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   [<span data-ttu-id="a53ef-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a53ef-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql)  
  
-   [<span data-ttu-id="a53ef-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a53ef-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql)  
  
-   [<span data-ttu-id="a53ef-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a53ef-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql)  
  
-   [<span data-ttu-id="a53ef-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a53ef-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="a53ef-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a53ef-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="a53ef-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a53ef-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="a53ef-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a53ef-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-agent-transact-sql)  
  
 <span data-ttu-id="a53ef-126">Queste stored procedure possono essere eseguite da un membro del ruolo predefinito del server **sysadmin** sul server appropriato o da un membro del ruolo predefinito del database **db_owner** nel database appropriato.</span><span class="sxs-lookup"><span data-stu-id="a53ef-126">These stored procedures can be executed by a member of the **sysadmin** fixed server role on the appropriate server or a member of the **db_owner** fixed database role in the appropriate database.</span></span> <span data-ttu-id="a53ef-127">Ogni stored procedure crea un processo agente e consente di specificare l'account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows in base al quale viene eseguito l'agente.</span><span class="sxs-lookup"><span data-stu-id="a53ef-127">The stored procedures each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="a53ef-128">Per gli utenti del ruolo **sysadmin** , i processi agente vengono creati implicitamente anche se non viene specificato un account di Windows (se viene specificato, deve essere valido). Gli agenti vengono eseguiti in base al contesto dell'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, nel server appropriato.</span><span class="sxs-lookup"><span data-stu-id="a53ef-128">For users in the **sysadmin** role, agent jobs are created implicitly even if a Windows account is not specified (if an account is specified, it must be valid); agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the appropriate server.</span></span> <span data-ttu-id="a53ef-129">Sebbene l'account non sia necessario, la procedura consigliata prevede di specificare un account separato per gli agenti.</span><span class="sxs-lookup"><span data-stu-id="a53ef-129">Although the account is not required, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="a53ef-130">Per altre informazioni, vedere [Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="a53ef-130">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a53ef-131">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a53ef-131">User Action</span></span>  
 <span data-ttu-id="a53ef-132">Assicurarsi di specificare un account di Windows valido per il **@job_login** parametro di ogni procedura.</span><span class="sxs-lookup"><span data-stu-id="a53ef-132">Ensure you specify a valid Windows account for the **@job_login** parameter of each procedure.</span></span> <span data-ttu-id="a53ef-133">Se si dispone di script di replica di versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], aggiornarli in modo che includano le stored procedure e i parametri necessari per [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a53ef-133">If you have replication scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="a53ef-134">Per altre informazioni, vedere [Aggiornare gli script di replica &#40;programmazione Transact-SQL della replica&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="a53ef-134">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53ef-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a53ef-135">See Also</span></span>  
 [<span data-ttu-id="a53ef-136">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="a53ef-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
