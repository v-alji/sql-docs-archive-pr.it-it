---
title: Risolvere i problemi relativi agli utenti isolati (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- orphaned users [SQL Server]
- logins [SQL Server], orphaned users
- troubleshooting [SQL Server], user accounts
- user accounts [SQL Server], orphaned users
- failover [SQL Server], managing metadata
- database mirroring [SQL Server], metadata
- users [SQL Server], orphaned
ms.assetid: 11eefa97-a31f-4359-ba5b-e92328224133
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5df714d818949b921ff2236e50d58913eab0e0db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628284"
---
# <a name="troubleshoot-orphaned-users-sql-server"></a><span data-ttu-id="c8dbf-102">Risolvere i problemi relativi agli utenti isolati (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c8dbf-102">Troubleshoot Orphaned Users (SQL Server)</span></span>
  <span data-ttu-id="c8dbf-103">Per accedere a un'istanza di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è necessario che un'entità disponga di un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valido.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-103">To log into an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a principal must have a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="c8dbf-104">Tale account di accesso viene utilizzato nel processo di autenticazione che verifica se l'entità è autorizzata a connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8dbf-104">This login is used in the authentication process that verifies whether the principal is allowed to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c8dbf-105">Gli [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account di accesso in un'istanza del server sono visibili nella vista del catalogo **sys. server_principals** e nella vista di compatibilità **sys.sysaccessi** .</span><span class="sxs-lookup"><span data-stu-id="c8dbf-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins on a server instance are visible in the **sys.server_principals** catalog view and the **sys.syslogins** compatibility view.</span></span>  
  
 <span data-ttu-id="c8dbf-106">Gli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consentono di accedere a database singoli mediante un utente del database di cui viene eseguito il mapping all'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8dbf-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins access individual databases using a database user that is mapped to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="c8dbf-107">Sono previste due eccezioni a questa regola:</span><span class="sxs-lookup"><span data-stu-id="c8dbf-107">There are two exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="c8dbf-108">Account Guest.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-108">The guest account.</span></span>  
  
     <span data-ttu-id="c8dbf-109">Si tratta di un account che, se attivato nel database, consente agli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di cui non viene eseguito il mapping ad alcun utente del database di accedere al database come utente guest.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-109">This is an account that, when enabled in the database, enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are not mapped to a database user to enter the database as the guest user.</span></span>  
  
-   <span data-ttu-id="c8dbf-110">Appartenenza ai gruppi di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-110">Microsoft Windows group memberships.</span></span>  
  
     <span data-ttu-id="c8dbf-111">Un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creato da un utente di Windows può accedere a un database se tale utente di Windows è membro di un gruppo di Windows a sua volta utente del database.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-111">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login created from a Windows user can enter a database if the Windows user is a member of a Windows group that is also a user in the database.</span></span>  
  
 <span data-ttu-id="c8dbf-112">Le informazioni relative al mapping di un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un utente del database sono archiviate all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-112">Information about the mapping of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to a database user is stored within the database.</span></span> <span data-ttu-id="c8dbf-113">Includono il nome dell'utente del database e il SID dell'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-113">It includes the name of the database user and the SID of the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="c8dbf-114">Le autorizzazioni di tale utente del database vengono utilizzate come autorizzazioni nel database.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-114">The permissions of this database user are used for authorization in the database.</span></span>  
  
 <span data-ttu-id="c8dbf-115">Un utente del database il cui account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] corrispondente non è definito o è definito in modo errato in un'istanza del server non potrà accedere a tale istanza.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-115">A database user for which the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is undefined or is incorrectly defined on a server instance cannot log in to the instance.</span></span> <span data-ttu-id="c8dbf-116">Questo utente viene definito *utente orfano* del database nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-116">Such a user is said to be an *orphaned user* of the database on that server instance.</span></span> <span data-ttu-id="c8dbf-117">Un utente del database può diventare isolato (orfano) se l'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] corrispondente viene rimosso</span><span class="sxs-lookup"><span data-stu-id="c8dbf-117">A database user can become orphaned if the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is dropped.</span></span> <span data-ttu-id="c8dbf-118">oppure dopo il ripristino di un database in un'istanza diversa di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o il collegamento del database a tale istanza.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-118">Also, a database user can become orphaned after a database is restored or attached to a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c8dbf-119">È possibile che si verifichi l'isolamento se l'utente del database è sottoposto a mapping a un SID non presente nella nuova istanza del server.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-119">Orphaning can happen if the database user is mapped to a SID that is not present in the new server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8dbf-120">Un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account di accesso non può accedere a un database in cui manca un utente del database corrispondente, a meno che **Guest** non sia abilitato in tale database.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-120">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login cannot access a database in which it lacks a corresponding database user unless **guest** is enabled in that database.</span></span> <span data-ttu-id="c8dbf-121">Per informazioni sulla creazione di un account utente di database, vedere [create user &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8dbf-121">For information about creating a database user account, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="to-detect-orphaned-users"></a><span data-ttu-id="c8dbf-122">Per rilevare gli utenti isolati (orfani)</span><span class="sxs-lookup"><span data-stu-id="c8dbf-122">To Detect Orphaned Users</span></span>  
 <span data-ttu-id="c8dbf-123">Per rilevare gli utenti isolati (orfani), eseguire le istruzioni Transact-SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8dbf-123">To detect orphaned users, execute the following Transact-SQL statements:</span></span>  
  
```  
USE <database_name>;  
GO;   
sp_change_users_login @Action='Report';  
GO;  
```  
  
 <span data-ttu-id="c8dbf-124">Nell'output sono elencati gli utenti e gli identificatori di sicurezza (SID) corrispondenti disponibili nel database corrente e non collegati ad alcun account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8dbf-124">The output lists the users and corresponding security identifiers (SID) in the current database that are not linked to any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="c8dbf-125">Per ulteriori informazioni, vedere [sp_change_users_login &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8dbf-125">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8dbf-126">non è possibile utilizzare **sp_change_users_login** con gli [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account di accesso creati da Windows.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-126">**sp_change_users_login** cannot be used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are created from Windows.</span></span>  
  
## <a name="to-resolve-an-orphaned-user"></a><span data-ttu-id="c8dbf-127">Per risolvere un utente isolato (orfano)</span><span class="sxs-lookup"><span data-stu-id="c8dbf-127">To Resolve an Orphaned User</span></span>  
 <span data-ttu-id="c8dbf-128">Per risolvere un utente isolato (orfano), eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c8dbf-128">To resolve an orphaned user, use the following procedure:</span></span>  
  
1.  <span data-ttu-id="c8dbf-129">Il comando seguente consente di ricollegare l'account di accesso del server specificato da *<login_name>* con l'utente del database specificato da *<Database_user>*.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-129">The following command relinks the server login account specified by *<login_name>* with the database user specified by *<database_user>*.</span></span>  
  
    ```  
    USE <database_name>;  
    GO  
    sp_change_users_login @Action='update_one', @UserNamePattern='<database_user>', @LoginName='<login_name>';  
    GO  
  
    ```  
  
     <span data-ttu-id="c8dbf-130">Per ulteriori informazioni, vedere [sp_change_users_login &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8dbf-130">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
2.  <span data-ttu-id="c8dbf-131">Al termine dell'esecuzione del codice riportato nel passaggio precedente, l'utente sarà in grado di accedere al database.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-131">After you run the code in the preceding step, the user can access the database.</span></span> <span data-ttu-id="c8dbf-132">L'utente può quindi modificare la password dell' *<login_name>* account di accesso usando il stored procedure **sp_password** , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c8dbf-132">The user then can alter the password of the *<login_name>* login account by using the **sp_password** stored procedure, as follows:</span></span>  
  
    ```  
    USE master   
    GO  
    sp_password @old=NULL, @new='password', @loginame='<login_name>';  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c8dbf-133">Solo gli account di accesso con autorizzazione ALTER ANY LOGIN possono modificare la password dell'account di accesso di un altro utente.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-133">Only logins with the ALTER ANY LOGIN permission can change the password of another user's login.</span></span> <span data-ttu-id="c8dbf-134">Solo i membri del ruolo **sysadmin** possono tuttavia modificare le password dei membri del ruolo **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c8dbf-134">However, only members of the **sysadmin** role can modify passwords of **sysadmin** role members.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8dbf-135">Impossibile utilizzare **sp_password** per gli [!INCLUDE[msCoName](../../includes/msconame-md.md)] account di Windows.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-135">**sp_password** cannot be used for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows accounts.</span></span> <span data-ttu-id="c8dbf-136">L'autenticazione degli utenti che si connettono a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in base al corrispondente account di rete di Windows viene eseguita da Windows. Le password di tali utenti sono pertanto modificabili solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="c8dbf-136">Users connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through their Windows network account are authenticated by Windows; therefore, their passwords can only be changed in Windows.</span></span>  
  
     <span data-ttu-id="c8dbf-137">Per ulteriori informazioni, vedere [sp_password &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8dbf-137">For more information, see [sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8dbf-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8dbf-138">See Also</span></span>  
 <span data-ttu-id="c8dbf-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8dbf-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="c8dbf-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8dbf-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="c8dbf-141">[sp_change_users_login &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8dbf-141">[sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span></span>  
 <span data-ttu-id="c8dbf-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8dbf-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span></span>  
 <span data-ttu-id="c8dbf-143">[sp_grantlogin &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8dbf-143">[sp_grantlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span></span>  
 <span data-ttu-id="c8dbf-144">[sp_password &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8dbf-144">[sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span></span>  
 <span data-ttu-id="c8dbf-145">[sys.sysutenti &#40;&#41;Transact-SQL](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8dbf-145">[sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span></span>  
 [<span data-ttu-id="c8dbf-146">sys.sysaccount di accesso &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8dbf-146">sys.syslogins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-syslogins-transact-sql)  
  
  
