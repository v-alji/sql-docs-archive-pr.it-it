---
title: MSSQL_ENG021798 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021798 error
ms.assetid: 596f5092-75ab-4a19-8582-588687c7b089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 327b4a373c28376701ea12400215ab00367df66a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714171"
---
# <a name="mssql_eng021798"></a><span data-ttu-id="ed674-102">MSSQL_ENG021798</span><span class="sxs-lookup"><span data-stu-id="ed674-102">MSSQL_ENG021798</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ed674-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="ed674-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed674-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ed674-104">Product Name</span></span>|<span data-ttu-id="ed674-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed674-105">SQL Server</span></span>|  
|<span data-ttu-id="ed674-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="ed674-106">Event ID</span></span>|<span data-ttu-id="ed674-107">21798</span><span class="sxs-lookup"><span data-stu-id="ed674-107">21798</span></span>|  
|<span data-ttu-id="ed674-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="ed674-108">Event Source</span></span>|<span data-ttu-id="ed674-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ed674-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ed674-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ed674-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ed674-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="ed674-111">Symbolic Name</span></span>||  
|<span data-ttu-id="ed674-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ed674-112">Message Text</span></span>|<span data-ttu-id="ed674-113">Per continuare è necessario aggiungere il processo agente '%s' tramite '%s'.</span><span class="sxs-lookup"><span data-stu-id="ed674-113">The '%s' agent job must be added through '%s' before continuing.</span></span> <span data-ttu-id="ed674-114">Vedere la documentazione relativa a '%s'.</span><span class="sxs-lookup"><span data-stu-id="ed674-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ed674-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ed674-115">Explanation</span></span>  
 <span data-ttu-id="ed674-116">Per creare una pubblicazione, è necessario essere un membro del ruolo predefinito del server **sysadmin** sul server di pubblicazione o del ruolo predefinito del database **db_owner** nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ed674-116">To create a publication, you must be a member of the **sysadmin** fixed server role on the Publisher or a member of the **db_owner** fixed database role in the publication database.</span></span> <span data-ttu-id="ed674-117">Se si un è membro del ruolo **db_owner** , questo errore viene generato nei casi in cui:</span><span class="sxs-lookup"><span data-stu-id="ed674-117">If you are a member of the **db_owner** role, this error is raised if:</span></span>  
  
-   <span data-ttu-id="ed674-118">Vengono eseguiti script da [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed674-118">You run scripts from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="ed674-119">Il modello di sicurezza in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]è cambiato ed è necessario aggiornare questi script.</span><span class="sxs-lookup"><span data-stu-id="ed674-119">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   <span data-ttu-id="ed674-120">La stored procedure **sp_addpublication** viene eseguita prima di eseguire [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ed674-120">The stored procedure **sp_addpublication** is executed before executing [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span></span> <span data-ttu-id="ed674-121">Questo vale per tutte le pubblicazioni transazionali.</span><span class="sxs-lookup"><span data-stu-id="ed674-121">This applies to all transactional publications.</span></span>  
  
-   <span data-ttu-id="ed674-122">La stored procedure **sp_addpublication** viene eseguita prima di eseguire [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ed674-122">The stored procedure **sp_addpublication** is executed before executing [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span></span> <span data-ttu-id="ed674-123">Questo vale per le pubblicazioni transazionali abilitate per le sottoscrizioni ad aggiornamento in coda (valore TRUE per il **@allow_queued_tran** parametro di **sp_addpublication**).</span><span class="sxs-lookup"><span data-stu-id="ed674-123">This applies to transactional publications that are enabled for queued updating subscriptions (a value of TRUE for the **@allow_queued_tran** parameter of **sp_addpublication**).</span></span>  
  
 <span data-ttu-id="ed674-124">Le stored procedure **sp_addlogreader_agent** e **sp_addqreader_agent** creano ognuna un processo agente e consentono di specificare l'account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows in base al quale viene eseguito l'agente.</span><span class="sxs-lookup"><span data-stu-id="ed674-124">The stored procedures **sp_addlogreader_agent** and **sp_addqreader_agent** each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="ed674-125">Per gli utenti del ruolo **sysadmin** , i processi agente vengono creati implicitamente se non vengono eseguite **sp_addlogreader_agent** e **sp_addqreader_agent** . Gli agenti vengono eseguiti in base al contesto dell'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ed674-125">For users in the **sysadmin** role, agent jobs are created implicitly if **sp_addlogreader_agent** and **sp_addqreader_agent** are not executed; agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the Distributor.</span></span> <span data-ttu-id="ed674-126">Sebbene **sp_addlogreader_agent** e **sp_addqreader_agent** non siano necessarie per gli utenti del ruolo **sysadmin** , la procedura consigliata prevede di specificare un account separato per gli agenti.</span><span class="sxs-lookup"><span data-stu-id="ed674-126">Although **sp_addlogreader_agent** and **sp_addqreader_agent** are not required for users in the **sysadmin** role, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="ed674-127">Per altre informazioni, vedere [Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="ed674-127">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ed674-128">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="ed674-128">User Action</span></span>  
 <span data-ttu-id="ed674-129">Accertarsi di eseguire le procedure nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="ed674-129">Ensure you execute procedures in the correct order.</span></span> <span data-ttu-id="ed674-130">Per ulteriori informazioni, vedere [creazione di una pubblicazione](publish/create-a-publication.md), aggiornamento di questi script per includere le stored procedure e i parametri richiesti da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ed674-130">For more information, see [Create a Publication](publish/create-a-publication.md), update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="ed674-131">Per altre informazioni, vedere [Aggiornare gli script di replica &#40;programmazione Transact-SQL della replica&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="ed674-131">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed674-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed674-132">See Also</span></span>  
 [<span data-ttu-id="ed674-133">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="ed674-133">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
