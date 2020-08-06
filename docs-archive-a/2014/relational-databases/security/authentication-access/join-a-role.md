---
title: Aggiungere un ruolo | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.MEMBERSHIP.F1
helpviewer_keywords:
- adding a member to a role
- join a role
ms.assetid: 05c8d10d-5823-46c6-8b1a-81722da6a42b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 58e8c071672c8c3afba8d6c424488899dcf76be7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625271"
---
# <a name="join-a-role"></a><span data-ttu-id="a2b95-102">aggiungere un ruolo</span><span class="sxs-lookup"><span data-stu-id="a2b95-102">Join a Role</span></span>
  <span data-ttu-id="a2b95-103">In questo argomento si descrive come assegnare ruoli agli account di accesso e agli utenti di database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2b95-103">This topic describes how to assign roles to logins and database users in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a2b95-104">Utilizzare i ruoli disponibili in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per gestire in modo efficace le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a2b95-104">Use roles in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to efficiently manage permissions.</span></span> <span data-ttu-id="a2b95-105">Assegnare autorizzazioni ai ruoli, quindi aggiungere e rimuovere utenti e account di accesso ai ruoli.</span><span class="sxs-lookup"><span data-stu-id="a2b95-105">Assign permissions to roles, and then add and remove users and logins to the roles.</span></span> <span data-ttu-id="a2b95-106">Utilizzando i ruoli, non è necessario gestire singolarmente le autorizzazioni per ciascun utente.</span><span class="sxs-lookup"><span data-stu-id="a2b95-106">By using roles, permissions do not have to be individually maintained for each user.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="a2b95-107">supporta quattro tipi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="a2b95-107">supports four types of roles.</span></span>  
  
-   <span data-ttu-id="a2b95-108">Ruoli predefiniti del server</span><span class="sxs-lookup"><span data-stu-id="a2b95-108">Fixed server roles</span></span>  
  
-   <span data-ttu-id="a2b95-109">Ruoli del server definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="a2b95-109">User-defined server roles</span></span>  
  
-   <span data-ttu-id="a2b95-110">Ruoli predefiniti del database</span><span class="sxs-lookup"><span data-stu-id="a2b95-110">Fixed database roles</span></span>  
  
-   <span data-ttu-id="a2b95-111">Ruoli del database definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="a2b95-111">User-defined database roles</span></span>  
  
 <span data-ttu-id="a2b95-112">I ruoli predefiniti sono automaticamente disponibili in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2b95-112">The fixed roles are automatically available in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a2b95-113">I ruoli predefiniti dispongono delle autorizzazioni necessarie per completare attività comuni.</span><span class="sxs-lookup"><span data-stu-id="a2b95-113">Fixed roles have the necessary permissions to accomplish common tasks.</span></span> <span data-ttu-id="a2b95-114">Per ulteriori informazioni sui ruoli predefiniti, vedere i collegamenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="a2b95-114">For more information about fixed roles, see the following links.</span></span> <span data-ttu-id="a2b95-115">I ruoli definiti dall'utente vengono creati dall'utente e possono essere personalizzati con le autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="a2b95-115">User-defined roles are created by you, and can be customized with the permissions that you select.</span></span> <span data-ttu-id="a2b95-116">Per ulteriori informazioni sui ruoli definiti dall'utente, vedere i collegamenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="a2b95-116">For more information about user-defined roles, see the following links.</span></span>  
  
 <span data-ttu-id="a2b95-117">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a2b95-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a2b95-118">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a2b95-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a2b95-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a2b95-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a2b95-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a2b95-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a2b95-121">**Per assegnare ruoli ad account di accesso e utenti di database tramite:**</span><span class="sxs-lookup"><span data-stu-id="a2b95-121">**To assign roles to logins and database users, using:**</span></span>  
  
     [<span data-ttu-id="a2b95-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a2b95-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a2b95-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a2b95-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a2b95-124">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a2b95-124">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a2b95-125">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a2b95-125">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a2b95-126">La modifica del nome di un ruolo del database non comporta la modifica del numero di ID, del proprietario o delle autorizzazioni del ruolo.</span><span class="sxs-lookup"><span data-stu-id="a2b95-126">Changing the name of a database role does not change ID number, owner, or permissions of the role.</span></span>  
  
-   <span data-ttu-id="a2b95-127">I ruoli del database sono visibili nelle viste del catalogo sys.database_role_members e sys.database_principals.</span><span class="sxs-lookup"><span data-stu-id="a2b95-127">Database roles are visible in the sys.database_role_members and sys.database_principals catalog views.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a2b95-128">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a2b95-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a2b95-129">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a2b95-129">Permissions</span></span>  
 <span data-ttu-id="a2b95-130">È richiesta `ALTER ANY ROLE` l'autorizzazione per il database, l' `ALTER` autorizzazione per il ruolo o l'appartenenza a **db_securityadmin**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-130">Requires `ALTER ANY ROLE` permission on the database, `ALTER` permission on the role, or membership in **db_securityadmin**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a2b95-131">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a2b95-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="a2b95-132">Per aggiungere un membro a un ruolo predefinito del server</span><span class="sxs-lookup"><span data-stu-id="a2b95-132">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="a2b95-133">In Esplora oggetti espandere il server in cui si desidera modificare un ruolo predefinito del server.</span><span class="sxs-lookup"><span data-stu-id="a2b95-133">In Object Explorer, expand the server in which you want to edit a fixed server role.</span></span>  
  
2.  <span data-ttu-id="a2b95-134">Espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="a2b95-134">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="a2b95-135">Espandere la cartella **Ruoli del server** .</span><span class="sxs-lookup"><span data-stu-id="a2b95-135">Expand the **Server Roles** folder</span></span>  
  
4.  <span data-ttu-id="a2b95-136">Fare clic con il pulsante destro del mouse sul ruolo da modificare e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-136">Right-click the role you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="a2b95-137">Nella finestra di dialogo **Proprietà ruolo server-**_server_role_name_ , nella pagina **membri** , fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-137">In the **Server Role Properties -**_server_role_name_ dialog box, on the **Members** page, click **Add**.</span></span>  
  
6.  <span data-ttu-id="a2b95-138">Nella finestra di dialogo **Seleziona account di accesso o ruolo del server** immettere l'account di accesso o il ruolo del server da aggiungere a questo ruolo del server in **Immettere i nomi degli oggetti da selezionare (esempi)** .</span><span class="sxs-lookup"><span data-stu-id="a2b95-138">In the **Select Server Login or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or server role to add to this server role.</span></span> <span data-ttu-id="a2b95-139">In alternativa, fare clic su **Sfoglia...** e selezionare uno, alcuni o tutti gli oggetti disponibili nella finestra di dialogo **Cerca oggetti**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-139">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="a2b95-140">Fare clic su **OK** per tornare alla finestra di dialogo **Proprietà ruolo server-**_server_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="a2b95-140">Click **OK** to return to the **Server Role Properties -**_server_role_name_ dialog box.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="a2b95-141">Per aggiungere un membro a un ruolo del database definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="a2b95-141">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="a2b95-142">In Esplora oggetti espandere il server in cui si desidera modificare un ruolo del database definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a2b95-142">In Object Explorer, expand the server in which you want to edit a user-defined database role.</span></span>  
  
2.  <span data-ttu-id="a2b95-143">Espandere la cartella **Database** .</span><span class="sxs-lookup"><span data-stu-id="a2b95-143">Expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="a2b95-144">Espandere il database in cui si desidera modificare un ruolo del database definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a2b95-144">Expand the database in which you want to edit a user-defined database role.</span></span>  
  
4.  <span data-ttu-id="a2b95-145">Espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="a2b95-145">Expand the **Security** folder.</span></span>  
  
5.  <span data-ttu-id="a2b95-146">Espandere la cartella **Ruoli** .</span><span class="sxs-lookup"><span data-stu-id="a2b95-146">Expand the **Roles** folder.</span></span>  
  
6.  <span data-ttu-id="a2b95-147">Espandere la cartella **Ruoli del server** .</span><span class="sxs-lookup"><span data-stu-id="a2b95-147">Expand the **Server Roles** folder.</span></span>  
  
7.  <span data-ttu-id="a2b95-148">Fare clic con il pulsante destro del mouse sul ruolo da modificare e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-148">Right-click the role you want to edit and select **Properties**.</span></span>  
  
8.  <span data-ttu-id="a2b95-149">Nella finestra di dialogo **Proprietà ruolo database-**_database_role_name_ , nella pagina **generale** , fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-149">In the **Database Role Properties -**_database_role_name_ dialog box, in the **General** page, click **Add**.</span></span>  
  
9. <span data-ttu-id="a2b95-150">Nella finestra di dialogo **Seleziona utente o ruolo del database** immettere l'account di accesso o il ruolo del database da aggiungere a questo ruolo del database in **Immettere i nomi degli oggetti da selezionare (esempi)** .</span><span class="sxs-lookup"><span data-stu-id="a2b95-150">In the **Select Database User or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or database role to add to this database role.</span></span> <span data-ttu-id="a2b95-151">In alternativa, fare clic su **Sfoglia...** e selezionare uno, alcuni o tutti gli oggetti disponibili nella finestra di dialogo **Cerca oggetti**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-151">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="a2b95-152">Fare clic su **OK** per tornare alla finestra di dialogo **Proprietà ruolo database-**_database_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="a2b95-152">Click **OK** to return to the **Database Role Properties -**_database_role_name_ dialog box.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a2b95-153">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a2b95-153">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="a2b95-154">Per aggiungere un membro a un ruolo predefinito del server</span><span class="sxs-lookup"><span data-stu-id="a2b95-154">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="a2b95-155">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2b95-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a2b95-156">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-156">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a2b95-157">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-157">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER SERVER ROLE diskadmin ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="a2b95-158">Per altre informazioni, vedere [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a2b95-158">For more information, see [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span></span>  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="a2b95-159">Per aggiungere un membro a un ruolo del database definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="a2b95-159">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="a2b95-160">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2b95-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a2b95-161">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a2b95-162">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a2b95-162">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER ROLE Marketing ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="a2b95-163">Per altre informazioni, vedere [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a2b95-163">For more information, see [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b95-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2b95-164">See Also</span></span>  
 <span data-ttu-id="a2b95-165">[Ruoli a livello di server](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="a2b95-165">[Server-Level Roles](server-level-roles.md) </span></span>  
 <span data-ttu-id="a2b95-166">[Ruoli a livello di database](../authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="a2b95-166">[Database-Level Roles](../authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="a2b95-167">Ruoli applicazione</span><span class="sxs-lookup"><span data-stu-id="a2b95-167">Application Roles</span></span>](../authentication-access/application-roles.md)  
  
  
