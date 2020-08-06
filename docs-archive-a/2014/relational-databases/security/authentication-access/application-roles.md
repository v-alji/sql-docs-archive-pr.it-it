---
title: Ruoli applicazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- application roles [SQL Server], about application roles
- principals [SQL Server], application roles
- credentials [SQL Server], roles
- application roles [SQL Server]
- roles [SQL Server], application
- permissions [SQL Server], roles
- users [SQL Server], application roles
- authentication [SQL Server], roles
- groups [SQL Server], roles
ms.assetid: dca18b8a-ca03-4b7f-9a46-8474d5b66f76
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: f2fcc7b1e333bb42a00675da5bb9fd559d1c34f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625275"
---
# <a name="application-roles"></a><span data-ttu-id="ea1de-102">Ruoli applicazione</span><span class="sxs-lookup"><span data-stu-id="ea1de-102">Application Roles</span></span>
  <span data-ttu-id="ea1de-103">Un ruolo applicazione è un'entità di database che consente a un'applicazione di funzionare con proprie autorizzazioni simili a quelle per utenti.</span><span class="sxs-lookup"><span data-stu-id="ea1de-103">An application role is a database principal that enables an application to run with its own, user-like permissions.</span></span> <span data-ttu-id="ea1de-104">I ruoli applicazione possono essere utilizzati per consentire l'accesso a dati specifici solo agli utenti che si collegano attraverso un'applicazione particolare.</span><span class="sxs-lookup"><span data-stu-id="ea1de-104">You can use application roles to enable access to specific data to only those users who connect through a particular application.</span></span> <span data-ttu-id="ea1de-105">A differenza dei ruoli di database, i ruoli applicazione non contengono membri e sono inattivi per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ea1de-105">Unlike database roles, application roles contain no members and are inactive by default.</span></span> <span data-ttu-id="ea1de-106">I ruoli applicazione funzionano con entrambe le modalità di autenticazione</span><span class="sxs-lookup"><span data-stu-id="ea1de-106">Application roles work with both authentication modes.</span></span> <span data-ttu-id="ea1de-107">I ruoli applicazione vengono abilitati usando **sp_setapprole**, che richiede una password.</span><span class="sxs-lookup"><span data-stu-id="ea1de-107">Application roles are enabled by using **sp_setapprole**, which requires a password.</span></span> <span data-ttu-id="ea1de-108">Poiché si tratta di entità a livello di database, i ruoli applicazione possono accedere ad altri database solo tramite le autorizzazioni concesse in questi database all'account utente **guest**.</span><span class="sxs-lookup"><span data-stu-id="ea1de-108">Because application roles are a database-level principal, they can access other databases only through permissions granted in those databases to **guest**.</span></span> <span data-ttu-id="ea1de-109">Ogni database in cui l'account utente **guest** è stato disabilitato non sarà quindi accessibile ai ruoli applicazione di altri database.</span><span class="sxs-lookup"><span data-stu-id="ea1de-109">Therefore, any database in which **guest** has been disabled will be inaccessible to application roles in other databases.</span></span>  
  
 <span data-ttu-id="ea1de-110">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]i ruoli applicazione non possono accedere ai metadati a livello di server perché non sono associati a un'entità a livello di server.</span><span class="sxs-lookup"><span data-stu-id="ea1de-110">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], application roles cannot access server-level metadata because they are not associated with a server-level principal.</span></span> <span data-ttu-id="ea1de-111">Per disabilitare questa limitazione e consentire quindi ai ruoli applicazione di accedere ai metadati a livello di server, impostare il flag globale 4616.</span><span class="sxs-lookup"><span data-stu-id="ea1de-111">To disable this restriction and thereby allow application roles to access server-level metadata, set the global flag 4616.</span></span> <span data-ttu-id="ea1de-112">Per altre informazioni, vedere [Flag di traccia &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql) e [DBCC TRACEON &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea1de-112">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql) and [DBCC TRACEON &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql).</span></span>  
  
## <a name="connecting-with-an-application-role"></a><span data-ttu-id="ea1de-113">Connessione attraverso un ruolo applicazione</span><span class="sxs-lookup"><span data-stu-id="ea1de-113">Connecting with an Application Role</span></span>  
 <span data-ttu-id="ea1de-114">Il passaggio da un contesto di sicurezza all'altro da parte di un ruolo applicazione si svolge nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ea1de-114">The following steps make up the process by which an application role switches security contexts:</span></span>  
  
1.  <span data-ttu-id="ea1de-115">Un utente esegue un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="ea1de-115">A user executes a client application.</span></span>  
  
2.  <span data-ttu-id="ea1de-116">L'applicazione client si collega a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] come utente.</span><span class="sxs-lookup"><span data-stu-id="ea1de-116">The client application connects to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the user.</span></span>  
  
3.  <span data-ttu-id="ea1de-117">L'applicazione esegue quindi la stored procedure **sp_setapprole** con una password nota solo all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea1de-117">The application then executes the **sp_setapprole** stored procedure with a password known only to the application.</span></span>  
  
4.  <span data-ttu-id="ea1de-118">Se il nome del ruolo applicazione e la password sono validi, il ruolo applicazione viene abilitato.</span><span class="sxs-lookup"><span data-stu-id="ea1de-118">If the application role name and password are valid, the application role is enabled.</span></span>  
  
5.  <span data-ttu-id="ea1de-119">A questo punto la connessione perde le autorizzazioni dell'utente e assume le autorizzazioni del ruolo applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea1de-119">At this point the connection loses the permissions of the user and assumes the permissions of the application role.</span></span>  
  
 <span data-ttu-id="ea1de-120">Le autorizzazioni acquisite attraverso il ruolo applicazione rimangono valide per tutta la durata della connessione.</span><span class="sxs-lookup"><span data-stu-id="ea1de-120">The permissions acquired through the application role remain in effect for the duration of the connection.</span></span>  
  
 <span data-ttu-id="ea1de-121">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'unico modo per un utente di ritornare al contesto di sicurezza originale dopo l'avvio di un ruolo applicazione consiste nel disconnettersi e riconnettersi a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea1de-121">In earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the only way for a user to reacquire its original security context after starting an application role is to disconnect and reconnect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ea1de-122">A partire da [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], **sp_setapprole** dispone di un'opzione che crea un cookie.</span><span class="sxs-lookup"><span data-stu-id="ea1de-122">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], **sp_setapprole** has an option that creates a cookie.</span></span> <span data-ttu-id="ea1de-123">Il cookie contiene informazioni di contesto precedenti all'abilitazione del ruolo applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea1de-123">The cookie contains context information before the application role is enabled.</span></span> <span data-ttu-id="ea1de-124">Questo cookie può essere usato da **sp_unsetapprole** per riportare la sessione al contesto originale.</span><span class="sxs-lookup"><span data-stu-id="ea1de-124">The cookie can be used by **sp_unsetapprole** to revert the session to its original context.</span></span> <span data-ttu-id="ea1de-125">Per informazioni su questa nuova opzione e un esempio, vedere [sp_setapprole &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setapprole-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea1de-125">For information about this new option and an example, see [sp_setapprole &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setapprole-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ea1de-126">L'opzione ODBC **encrypt** non è supportata da **SqlClient**.</span><span class="sxs-lookup"><span data-stu-id="ea1de-126">The ODBC **encrypt** option is not supported by **SqlClient**.</span></span> <span data-ttu-id="ea1de-127">Per trasmettere informazioni riservate su una rete, utilizzare SSL (Secure Sockets Layer) o IPSec per crittografare il canale.</span><span class="sxs-lookup"><span data-stu-id="ea1de-127">When you are transmitting confidential information over a network, use Secure Sockets Layer (SSL) or IPsec to encrypt the channel.</span></span> <span data-ttu-id="ea1de-128">Se è necessario mantenere le credenziali nell'applicazione client, crittografarle utilizzando le funzioni Crypto API.</span><span class="sxs-lookup"><span data-stu-id="ea1de-128">If you must persist credentials in the client application, encrypt the credentials by using the crypto API functions.</span></span> <span data-ttu-id="ea1de-129">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] e versioni successive, il parametro *password* è archiviato come hash unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="ea1de-129">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] and later versions, the parameter *password* is stored as a one-way hash.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ea1de-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="ea1de-130">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea1de-131">Creare un ruolo applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea1de-131">Create an application role.</span></span>|<span data-ttu-id="ea1de-132">[Creare un ruolo applicazione](create-an-application-role.md) e [CREATE APPLICATION ROLE & #40; Transact-SQL & #41;](/sql/t-sql/statements/create-application-role-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="ea1de-132">[Create an Application Role](create-an-application-role.md) and [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql)</span></span>|  
|<span data-ttu-id="ea1de-133">Modificare un ruolo applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea1de-133">Alter an application role.</span></span>|[<span data-ttu-id="ea1de-134">ALTER APPLICATION ROLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ea1de-134">ALTER APPLICATION ROLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-application-role-transact-sql)|  
|<span data-ttu-id="ea1de-135">Eliminare un ruolo applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea1de-135">Delete an application role.</span></span>|[<span data-ttu-id="ea1de-136">DROP APPLICATION ROLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ea1de-136">DROP APPLICATION ROLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-application-role-transact-sql)|  
|<span data-ttu-id="ea1de-137">Utilizzo di un ruolo applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea1de-137">Using an application role.</span></span>|[<span data-ttu-id="ea1de-138">sp_setapprole &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ea1de-138">sp_setapprole &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-setapprole-transact-sql)|  
  
## <a name="see-also"></a><span data-ttu-id="ea1de-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea1de-139">See Also</span></span>  
 [<span data-ttu-id="ea1de-140">Sicurezza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea1de-140">Securing SQL Server</span></span>](../securing-sql-server.md)  
  
  