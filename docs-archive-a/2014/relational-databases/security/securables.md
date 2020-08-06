---
title: Entità a protezione diretta | Microsoft Docs
ms.custom: ''
ms.date: 10/14/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectobject.f1
helpviewer_keywords:
- securables [SQL Server]
- schemas [SQL Server], securables
- database securables [SQL Server]
- hierarchies [SQL Server], securables
- server securables [SQL Server]
ms.assetid: bfa748f0-70b0-453c-870a-04b7b205b9ff
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ff2aaba72e2e5489694d31b35e594622c099acab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714019"
---
# <a name="securables"></a><span data-ttu-id="3ed39-102">Entità a protezione diretta</span><span class="sxs-lookup"><span data-stu-id="3ed39-102">Securables</span></span>
  <span data-ttu-id="3ed39-103">Le entità a protezione diretta sono le risorse il cui accesso è controllato dal sistema di autorizzazioni del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ed39-103">Securables are the resources to which the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] authorization system regulates access.</span></span> <span data-ttu-id="3ed39-104">Ad esempio, una tabella è un'entità a protezione diretta.</span><span class="sxs-lookup"><span data-stu-id="3ed39-104">For example, a table is a securable.</span></span> <span data-ttu-id="3ed39-105">Alcune entità a protezione diretta possono essere contenute da altre, creando gerarchie nidificate denominate ambiti, che possono a loro volta essere protetti.</span><span class="sxs-lookup"><span data-stu-id="3ed39-105">Some securables can be contained within others, creating nested hierarchies called "scopes" that can themselves be secured.</span></span> <span data-ttu-id="3ed39-106">Gli ambiti a protezione diretta sono **server**, **database**e **schema**.</span><span class="sxs-lookup"><span data-stu-id="3ed39-106">The securable scopes are **server**, **database**, and **schema**.</span></span>  
  
## <a name="securable-scope-server"></a><span data-ttu-id="3ed39-107">Ambito a protezione diretta: Server</span><span class="sxs-lookup"><span data-stu-id="3ed39-107">Securable scope: Server</span></span>  
 <span data-ttu-id="3ed39-108">L'ambito a protezione diretta **server** contiene le entità a protezione diretta seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ed39-108">The **server** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="3ed39-109">gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="3ed39-109">Availability group</span></span>  
  
-   <span data-ttu-id="3ed39-110">Endpoint</span><span class="sxs-lookup"><span data-stu-id="3ed39-110">Endpoint</span></span>  
  
-   <span data-ttu-id="3ed39-111">Login</span><span class="sxs-lookup"><span data-stu-id="3ed39-111">Login</span></span>  
  
-   <span data-ttu-id="3ed39-112">Ruolo server</span><span class="sxs-lookup"><span data-stu-id="3ed39-112">Server role</span></span>  
  
-   <span data-ttu-id="3ed39-113">Database</span><span class="sxs-lookup"><span data-stu-id="3ed39-113">Database</span></span>  
  
## <a name="securable-scope-database"></a><span data-ttu-id="3ed39-114">Ambito a protezione diretta: Database</span><span class="sxs-lookup"><span data-stu-id="3ed39-114">Securable scope: Database</span></span>  
 <span data-ttu-id="3ed39-115">L'ambito a protezione diretta **database** contiene le entità a protezione diretta seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ed39-115">The **database** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="3ed39-116">Ruolo applicazione</span><span class="sxs-lookup"><span data-stu-id="3ed39-116">Application role</span></span>  
  
-   <span data-ttu-id="3ed39-117">Assembly</span><span class="sxs-lookup"><span data-stu-id="3ed39-117">Assembly</span></span>  
  
-   <span data-ttu-id="3ed39-118">Chiave asimmetrica</span><span class="sxs-lookup"><span data-stu-id="3ed39-118">Asymmetric key</span></span>  
  
-   <span data-ttu-id="3ed39-119">Certificato</span><span class="sxs-lookup"><span data-stu-id="3ed39-119">Certificate</span></span>  
  
-   <span data-ttu-id="3ed39-120">Contratto</span><span class="sxs-lookup"><span data-stu-id="3ed39-120">Contract</span></span>  
  
-   <span data-ttu-id="3ed39-121">Catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="3ed39-121">Fulltext catalog</span></span>  
  
-   <span data-ttu-id="3ed39-122">Elenco di parole non significative full-text</span><span class="sxs-lookup"><span data-stu-id="3ed39-122">Fulltext stoplist</span></span>  
  
-   <span data-ttu-id="3ed39-123">Tipo di messaggio</span><span class="sxs-lookup"><span data-stu-id="3ed39-123">Message type</span></span>  
  
-   <span data-ttu-id="3ed39-124">Associazione al servizio remoto</span><span class="sxs-lookup"><span data-stu-id="3ed39-124">Remote Service Binding</span></span>  
  
-   <span data-ttu-id="3ed39-125">Ruolo (database)</span><span class="sxs-lookup"><span data-stu-id="3ed39-125">(Database) Role</span></span>  
  
-   <span data-ttu-id="3ed39-126">Route</span><span class="sxs-lookup"><span data-stu-id="3ed39-126">Route</span></span>  
  
-   <span data-ttu-id="3ed39-127">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3ed39-127">Schema</span></span>  
  
-   <span data-ttu-id="3ed39-128">Elenco delle proprietà di ricerca</span><span class="sxs-lookup"><span data-stu-id="3ed39-128">Search property list</span></span>  
  
-   <span data-ttu-id="3ed39-129">Service</span><span class="sxs-lookup"><span data-stu-id="3ed39-129">Service</span></span>  
  
-   <span data-ttu-id="3ed39-130">Chiave simmetrica</span><span class="sxs-lookup"><span data-stu-id="3ed39-130">Symmetric key</span></span>  
  
-   <span data-ttu-id="3ed39-131">Utente</span><span class="sxs-lookup"><span data-stu-id="3ed39-131">User</span></span>  
  
## <a name="securable-scope-schema"></a><span data-ttu-id="3ed39-132">Ambito a protezione diretta: SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3ed39-132">Securable scope: Schema</span></span>  
 <span data-ttu-id="3ed39-133">L'ambito a protezione diretta **schema** contiene le entità a protezione diretta seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ed39-133">The **schema** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="3ed39-134">Type</span><span class="sxs-lookup"><span data-stu-id="3ed39-134">Type</span></span>  
  
-   <span data-ttu-id="3ed39-135">Raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="3ed39-135">XML schema collection</span></span>  
  
-   <span data-ttu-id="3ed39-136">Oggetto - La classe oggetto include i membri seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ed39-136">Object - The object class has the following members:</span></span>  
  
    -   <span data-ttu-id="3ed39-137">Aggregate</span><span class="sxs-lookup"><span data-stu-id="3ed39-137">Aggregate</span></span>  
  
    -   <span data-ttu-id="3ed39-138">Funzione</span><span class="sxs-lookup"><span data-stu-id="3ed39-138">Function</span></span>  
  
    -   <span data-ttu-id="3ed39-139">Procedura</span><span class="sxs-lookup"><span data-stu-id="3ed39-139">Procedure</span></span>  
  
    -   <span data-ttu-id="3ed39-140">Coda</span><span class="sxs-lookup"><span data-stu-id="3ed39-140">Queue</span></span>  
  
    -   <span data-ttu-id="3ed39-141">Sinonimo</span><span class="sxs-lookup"><span data-stu-id="3ed39-141">Synonym</span></span>  
  
    -   <span data-ttu-id="3ed39-142">Tabella</span><span class="sxs-lookup"><span data-stu-id="3ed39-142">Table</span></span>  
  
    -   <span data-ttu-id="3ed39-143">Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="3ed39-143">View</span></span>  
  
## <a name="controlling-access-to-a-securable"></a><span data-ttu-id="3ed39-144">Controllo di accesso a un'entità a protezione diretta</span><span class="sxs-lookup"><span data-stu-id="3ed39-144">Controlling Access to a Securable</span></span>  
 <span data-ttu-id="3ed39-145">L'entità che riceve autorizzazione per un'entità a protezione diretta viene chiamata entità.</span><span class="sxs-lookup"><span data-stu-id="3ed39-145">The entity that receives permission to a securable is called a principal.</span></span> <span data-ttu-id="3ed39-146">Le entità più comuni sono gli account di accesso e gli utenti di database.</span><span class="sxs-lookup"><span data-stu-id="3ed39-146">The most common principals are logins and database users.</span></span> <span data-ttu-id="3ed39-147">L'accesso alle entità a protezione diretta viene controllato concedendo o negando autorizzazioni o aggiungendo accessi e utenti a ruoli che dispongono di accesso.</span><span class="sxs-lookup"><span data-stu-id="3ed39-147">Access to securables is controlled by granting or denying permissions, or by adding logins and user to roles which have access.</span></span> <span data-ttu-id="3ed39-148">Per informazioni sul controllo delle autorizzazioni, vedere [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) e [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3ed39-148">For information about controlling permissions, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql), and [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="3ed39-149">Le autorizzazioni predefinite concesso a oggetti di sistema durante l'installazione vengono valutati attentamente per individuare possibili minacce e non è quindi necessario modificarli per implementare misure di protezione avanzata dell'installazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ed39-149">The default permissions that are granted to system objects at the time of setup are carefully evaluated against possible threats and need not be altered as part of hardening the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="3ed39-150">Eventuali modifiche alle autorizzazioni per gli oggetti di sistema possono limitare o compromettere la funzionalità e potrebbero lasciare l'installazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in uno stato non supportato.</span><span class="sxs-lookup"><span data-stu-id="3ed39-150">Any changes to the permissions on the system objects could limit or break the functionality and could potentially leave your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation in an unsupported state.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="3ed39-151">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="3ed39-151">Related Content</span></span>  
 [<span data-ttu-id="3ed39-152">Sicurezza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ed39-152">Securing SQL Server</span></span>](securing-sql-server.md)  
  
 [<span data-ttu-id="3ed39-153">sys.database_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ed39-153">sys.database_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql)  
  
 [<span data-ttu-id="3ed39-154">sys.database_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ed39-154">sys.database_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql)  
  
 [<span data-ttu-id="3ed39-155">sys.server_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ed39-155">sys.server_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql)  
  
 [<span data-ttu-id="3ed39-156">sys.server_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ed39-156">sys.server_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-role-members-transact-sql)  
  
 [<span data-ttu-id="3ed39-157">sys.sql_logins &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ed39-157">sys.sql_logins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql)  
  
  
