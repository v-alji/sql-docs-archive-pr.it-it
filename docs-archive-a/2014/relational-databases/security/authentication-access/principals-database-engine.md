---
title: Entità (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectroll.f1
- sql12.swb.databaseuser.permissions.user.f1--May use common.permissions
helpviewer_keywords:
- certificates [SQL Server], principals
- roles [SQL Server], principals
- permissions [SQL Server], principals
- '##MS_SQLAuthenticatorCertificate##'
- principals [SQL Server]
- '##MS_SQLResourceSigningCertificate##'
- groups [SQL Server], principals
- '##MS_AgentSigningCertificate##'
- authentication [SQL Server], principals
- schemas [SQL Server], principals
- principals [SQL Server], about principals
- security [SQL Server], principals
- users [SQL Server], principals
- '##MS_SQLReplicationSigningCertificate##'
ms.assetid: 3f7adbf7-6e40-4396-a8ca-71cbb843b5c2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 808c8516b3ed9e95ea4c724736461cb00923a7fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637721"
---
# <a name="principals-database-engine"></a><span data-ttu-id="6cd90-102">Entità (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="6cd90-102">Principals (Database Engine)</span></span>
  <span data-ttu-id="6cd90-103">Le*entità* possono richiedere risorse di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cd90-103">*Principals* are entities that can request [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources.</span></span> <span data-ttu-id="6cd90-104">Analogamente ad altri componenti del modello di autorizzazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , le entità possono essere organizzate in una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="6cd90-104">Like other components of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authorization model, principals can be arranged in a hierarchy.</span></span> <span data-ttu-id="6cd90-105">L'ambito di influenza di un'entità dipende dall'ambito della definizione dell'entità: Windows, server, database e se l'entità è indivisibile o una raccolta.</span><span class="sxs-lookup"><span data-stu-id="6cd90-105">The scope of influence of a principal depends on the scope of the definition of the principal: Windows, server, database; and whether the principal is indivisible or a collection.</span></span> <span data-ttu-id="6cd90-106">Un account di accesso di Windows è un esempio di entità indivisibile mentre un gruppo di Windows è un esempio di entità costituita da una raccolta.</span><span class="sxs-lookup"><span data-stu-id="6cd90-106">A Windows Login is an example of an indivisible principal, and a Windows Group is an example of a principal that is a collection.</span></span> <span data-ttu-id="6cd90-107">Ogni entità dispone di un ID di sicurezza (SID).</span><span class="sxs-lookup"><span data-stu-id="6cd90-107">Every principal has a security identifier (SID).</span></span>  
  
 <span data-ttu-id="6cd90-108">**Entità a livello di Windows**</span><span class="sxs-lookup"><span data-stu-id="6cd90-108">**Windows-level principals**</span></span>  
  
-   <span data-ttu-id="6cd90-109">Account di dominio di Windows</span><span class="sxs-lookup"><span data-stu-id="6cd90-109">Windows Domain Login</span></span>  
  
-   <span data-ttu-id="6cd90-110">Account di accesso locale di Windows</span><span class="sxs-lookup"><span data-stu-id="6cd90-110">Windows Local Login</span></span>  
  
 <span data-ttu-id="6cd90-111">**SQL Server** - **level** **entità** di livello</span><span class="sxs-lookup"><span data-stu-id="6cd90-111">**SQL Server**-**level** **principals**</span></span>  
  
-   <span data-ttu-id="6cd90-112">Account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cd90-112">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Login</span></span>  
  
-   <span data-ttu-id="6cd90-113">Ruolo del server</span><span class="sxs-lookup"><span data-stu-id="6cd90-113">Server Role</span></span>  
  
 <span data-ttu-id="6cd90-114">**Entità a livello di database**</span><span class="sxs-lookup"><span data-stu-id="6cd90-114">**Database-level principals**</span></span>  
  
-   <span data-ttu-id="6cd90-115">Utente di database</span><span class="sxs-lookup"><span data-stu-id="6cd90-115">Database User</span></span>  
  
-   <span data-ttu-id="6cd90-116">Ruolo del database</span><span class="sxs-lookup"><span data-stu-id="6cd90-116">Database Role</span></span>  
  
-   <span data-ttu-id="6cd90-117">Ruolo applicazione</span><span class="sxs-lookup"><span data-stu-id="6cd90-117">Application Role</span></span>  
  
## <a name="the-sql-server-sa-login"></a><span data-ttu-id="6cd90-118">Account di accesso sa di SQL Server</span><span class="sxs-lookup"><span data-stu-id="6cd90-118">The SQL Server sa Login</span></span>  
 <span data-ttu-id="6cd90-119">L'account di accesso sa di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è un'entità a livello di server.</span><span class="sxs-lookup"><span data-stu-id="6cd90-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sa log in is a server-level principal.</span></span> <span data-ttu-id="6cd90-120">Per impostazione predefinita, questo account viene creato durante l'installazione di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="6cd90-120">By default, it is created when an instance is installed.</span></span> <span data-ttu-id="6cd90-121">A partire da [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], il database predefinito di sa è il database master.</span><span class="sxs-lookup"><span data-stu-id="6cd90-121">Beginning in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the default database of sa is master.</span></span> <span data-ttu-id="6cd90-122">diversamente da quanto consentito nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cd90-122">This is a change of behavior from earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="public-database-role"></a><span data-ttu-id="6cd90-123">Ruolo di database public</span><span class="sxs-lookup"><span data-stu-id="6cd90-123">public Database Role</span></span>  
 <span data-ttu-id="6cd90-124">Ogni utente di database appartiene al ruolo di database public.</span><span class="sxs-lookup"><span data-stu-id="6cd90-124">Every database user belongs to the public database role.</span></span> <span data-ttu-id="6cd90-125">Quando a un utente non sono state concesse o negate autorizzazioni specifiche per un'entità a protezione diretta, l'utente eredita le autorizzazioni concesse al ruolo public su tale entità a protezione diretta.</span><span class="sxs-lookup"><span data-stu-id="6cd90-125">When a user has not been granted or denied specific permissions on a securable, the user inherits the permissions granted to public on that securable.</span></span>  
  
## <a name="information_schema-and-sys"></a><span data-ttu-id="6cd90-126">INFORMATION_SCHEMA e sys</span><span class="sxs-lookup"><span data-stu-id="6cd90-126">INFORMATION_SCHEMA and sys</span></span>  
 <span data-ttu-id="6cd90-127">Ogni database comprende due entità che appaiono come utenti in viste di catalogo: INFORMATION_SCHEMA e sys.</span><span class="sxs-lookup"><span data-stu-id="6cd90-127">Every database includes two entities that appear as users in catalog views: INFORMATION_SCHEMA and sys.</span></span> <span data-ttu-id="6cd90-128">Queste entità sono richieste da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="6cd90-128">These entities are required by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6cd90-129">e non posso essere modificate o eliminate.</span><span class="sxs-lookup"><span data-stu-id="6cd90-129">They are not principals, and they cannot be modified or dropped.</span></span>  
  
## <a name="certificate-based-sql-server-logins"></a><span data-ttu-id="6cd90-130">Account di accesso basati su certificati di SQL Server</span><span class="sxs-lookup"><span data-stu-id="6cd90-130">Certificate-based SQL Server Logins</span></span>  
 <span data-ttu-id="6cd90-131">Le entità del server i cui nomi sono racchiusi tra due simboli di cancelletto (##) sono solo per uso interno di sistema.</span><span class="sxs-lookup"><span data-stu-id="6cd90-131">Server principals with names enclosed by double hash marks (##) are for internal system use only.</span></span> <span data-ttu-id="6cd90-132">Al momento dell'installazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vengono create le seguenti entità che non devono essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="6cd90-132">The following principals are created from certificates when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is installed, and should not be deleted.</span></span>  
  
-   <span data-ttu-id="6cd90-133">\##MS_SQLResourceSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="6cd90-133">\##MS_SQLResourceSigningCertificate##</span></span>  
  
-   <span data-ttu-id="6cd90-134">\##MS_SQLReplicationSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="6cd90-134">\##MS_SQLReplicationSigningCertificate##</span></span>  
  
-   <span data-ttu-id="6cd90-135">\##MS_SQLAuthenticatorCertificate##</span><span class="sxs-lookup"><span data-stu-id="6cd90-135">\##MS_SQLAuthenticatorCertificate##</span></span>  
  
-   <span data-ttu-id="6cd90-136">\##MS_AgentSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="6cd90-136">\##MS_AgentSigningCertificate##</span></span>  
  
-   <span data-ttu-id="6cd90-137">\##MS_PolicyEventProcessingLogin##</span><span class="sxs-lookup"><span data-stu-id="6cd90-137">\##MS_PolicyEventProcessingLogin##</span></span>  
  
-   <span data-ttu-id="6cd90-138">\##MS_PolicySigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="6cd90-138">\##MS_PolicySigningCertificate##</span></span>  
  
-   <span data-ttu-id="6cd90-139">\##MS_PolicyTsqlExecutionLogin##</span><span class="sxs-lookup"><span data-stu-id="6cd90-139">\##MS_PolicyTsqlExecutionLogin##</span></span>  
  
## <a name="the-guest-user"></a><span data-ttu-id="6cd90-140">L'utente Guest</span><span class="sxs-lookup"><span data-stu-id="6cd90-140">The guest User</span></span>  
 <span data-ttu-id="6cd90-141">Ogni database include un **guest**.</span><span class="sxs-lookup"><span data-stu-id="6cd90-141">Each database includes a **guest**.</span></span> <span data-ttu-id="6cd90-142">Le autorizzazioni garantite all'utente **guest** sono ereditate dagli utenti che hanno accesso al database ma non dispongono di un account utente nel database.</span><span class="sxs-lookup"><span data-stu-id="6cd90-142">Permissions granted to the **guest** user are inherited by users who have access to the database, but who do not have a user account in the database.</span></span> <span data-ttu-id="6cd90-143">Non è possibile eliminare l'utente **Guest** , ma è possibile disabilitarlo revocando l' `CONNECT` autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="6cd90-143">The **guest** user cannot be dropped, but it can be disabled by revoking it's `CONNECT` permission.</span></span> <span data-ttu-id="6cd90-144">`CONNECT`È possibile revocare l'autorizzazione eseguendo `REVOKE CONNECT FROM GUEST` all'interno di qualsiasi database diverso da master o tempdb.</span><span class="sxs-lookup"><span data-stu-id="6cd90-144">The `CONNECT` permission can be revoked by executing `REVOKE CONNECT FROM GUEST` within any database other than master or tempdb.</span></span>  
  
## <a name="client-and-database-server"></a><span data-ttu-id="6cd90-145">Client e server di database</span><span class="sxs-lookup"><span data-stu-id="6cd90-145">Client and Database Server</span></span>  
 <span data-ttu-id="6cd90-146">Per definizione, un client e un server di database sono entità di sicurezza e possono essere protetti.</span><span class="sxs-lookup"><span data-stu-id="6cd90-146">By definition, a client and a database server are security principals and can be secured.</span></span> <span data-ttu-id="6cd90-147">È possibile autenticare queste entità mutuamente prima che sia stabilita una connessione di rete sicura.</span><span class="sxs-lookup"><span data-stu-id="6cd90-147">These entities can be mutually authenticated before a secure network connection is established.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="6cd90-148">supporta il protocollo di autenticazione [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) , che definisce il modo in cui i client interagiscono con un servizio di autenticazione di rete.</span><span class="sxs-lookup"><span data-stu-id="6cd90-148">supports the [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) authentication protocol, which defines how clients interact with a network authentication service.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6cd90-149">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="6cd90-149">Related Tasks</span></span>  
 <span data-ttu-id="6cd90-150">In questa sezione della documentazione online di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , sono inclusi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="6cd90-150">The following topics are included in this section of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="6cd90-151">Procedure per la gestione di account di accesso, utenti e schemi</span><span class="sxs-lookup"><span data-stu-id="6cd90-151">Managing Logins, Users, and Schemas How-to Topics</span></span>](managing-logins-users-and-schemas-how-to-topics.md)  
  
-   [<span data-ttu-id="6cd90-152">Ruoli a livello di server</span><span class="sxs-lookup"><span data-stu-id="6cd90-152">Server-Level Roles</span></span>](server-level-roles.md)  
  
-   [<span data-ttu-id="6cd90-153">Ruoli a livello di database</span><span class="sxs-lookup"><span data-stu-id="6cd90-153">Database-Level Roles</span></span>](database-level-roles.md)  
  
-   [<span data-ttu-id="6cd90-154">Ruoli applicazione</span><span class="sxs-lookup"><span data-stu-id="6cd90-154">Application Roles</span></span>](application-roles.md)  
  
## <a name="see-also"></a><span data-ttu-id="6cd90-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cd90-155">See Also</span></span>  
 <span data-ttu-id="6cd90-156">[Sicurezza di SQL Server](../securing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6cd90-156">[Securing SQL Server](../securing-sql-server.md) </span></span>  
 <span data-ttu-id="6cd90-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cd90-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span></span>  
 <span data-ttu-id="6cd90-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cd90-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span></span>  
 <span data-ttu-id="6cd90-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cd90-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span></span>  
 <span data-ttu-id="6cd90-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cd90-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span></span>  
 <span data-ttu-id="6cd90-161">[Ruoli a livello di server](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="6cd90-161">[Server-Level Roles](server-level-roles.md) </span></span>  
 [<span data-ttu-id="6cd90-162">Ruoli a livello di database</span><span class="sxs-lookup"><span data-stu-id="6cd90-162">Database-Level Roles</span></span>](database-level-roles.md)  
  
  
