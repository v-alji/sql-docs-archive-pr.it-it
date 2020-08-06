---
title: Consentire a utenti non amministratori di usare Monitoraggio replica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, non-administrators access
ms.assetid: 1cf21d9e-831d-41a1-a5a0-83ff6d22fa86
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f4a7699c555086d627e4c3a52ea70acf931ea1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626646"
---
# <a name="allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="ee0a9-102">Autorizzazione di utenti non amministratori all'utilizzo di Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="ee0a9-102">Allow Non-Administrators to Use Replication Monitor</span></span>
  <span data-ttu-id="ee0a9-103">In questo argomento viene descritto come consentire agli utenti non amministratore di utilizzare Monitoraggio replica in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee0a9-103">This topic describes how to allow non-administrators to use Replication Monitor in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ee0a9-104">Monitoraggio replica può essere utilizzato da membri che appartengono ai ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee0a9-104">Replication Monitor can be used by users who are members of the following roles:</span></span>  
  
-   <span data-ttu-id="ee0a9-105">Il ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="ee0a9-105">The **sysadmin** fixed server role.</span></span>  
  
     <span data-ttu-id="ee0a9-106">Questi utenti possono monitorare la replica e avere il controllo completo sulla modifica delle proprietà di replica, ad esempio le pianificazioni degli agenti, i profili agente e così via.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-106">These users can monitor replication and have full control over changing replication properties such as agent schedules, agent profiles, and so on.</span></span>  
  
-   <span data-ttu-id="ee0a9-107">`replmonitor`Ruolo del database nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-107">The `replmonitor` database role in the distribution database.</span></span>  
  
     <span data-ttu-id="ee0a9-108">Questi utenti possono monitorare la replica, ma non possono modificare le proprietà di replica.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-108">These users can monitor replication, but cannot change any replication properties.</span></span>  
  
 <span data-ttu-id="ee0a9-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ee0a9-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ee0a9-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ee0a9-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ee0a9-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ee0a9-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ee0a9-112">**Per consentire a utenti non amministratori di utilizzare Monitoraggio replica tramite:**</span><span class="sxs-lookup"><span data-stu-id="ee0a9-112">**To allow non-administrators to use Replication Monitor, using:**</span></span>  
  
     [<span data-ttu-id="ee0a9-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee0a9-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ee0a9-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee0a9-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ee0a9-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ee0a9-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ee0a9-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ee0a9-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ee0a9-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ee0a9-117">Permissions</span></span>  
 <span data-ttu-id="ee0a9-118">Per consentire agli utenti non amministratori di utilizzare Monitoraggio replica, è necessario che un membro del ruolo predefinito del server **sysadmin** aggiunga l'utente al database di distribuzione e lo assegni al `replmonitor` ruolo.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-118">To allow non-administrators to use Replication Monitor, a member of the **sysadmin** fixed server role must add the user to the distribution database and assign that user to the `replmonitor` role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ee0a9-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee0a9-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="ee0a9-120">Per consentire a utenti non amministratori di utilizzare Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="ee0a9-120">To allow non-administrators to use Replication Monitor</span></span>  
  
1.  <span data-ttu-id="ee0a9-121">Connettersi al database di distribuzione in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-121">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the Distributor, and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="ee0a9-122">Espandere **Database**, **Database di sistema**e quindi il database di distribuzione (denominato **distribuzione** per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="ee0a9-122">Expand **Databases**, expand **System Databases**, and then expand the distribution database (named **distribution** by default).</span></span>  
  
3.  <span data-ttu-id="ee0a9-123">Espandere **Sicurezza**, fare clic con il pulsante destro del mouse su **Utenti**e quindi scegliere **Nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-123">Expand **Security**, right-click **Users**, and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="ee0a9-124">Immettere un nome utente e un account di accesso per l'utente.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-124">Enter a user name and login for the user.</span></span>  
  
5.  <span data-ttu-id="ee0a9-125">Selezionare uno schema predefinito di `replmonitor` .</span><span class="sxs-lookup"><span data-stu-id="ee0a9-125">Select a default schema of `replmonitor`.</span></span>  
  
6.  <span data-ttu-id="ee0a9-126">Selezionare la `replmonitor` casella di controllo nella griglia **appartenenza a ruoli del database** .</span><span class="sxs-lookup"><span data-stu-id="ee0a9-126">Select the `replmonitor` check box in the **Database role membership** grid.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ee0a9-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee0a9-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-user-to-the-replmonitor-fixed-database-role"></a><span data-ttu-id="ee0a9-128">Per aggiungere un utente al ruolo predefinito del database replmonitor</span><span class="sxs-lookup"><span data-stu-id="ee0a9-128">To add a user to the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="ee0a9-129">Nel database di distribuzione del server di distribuzione eseguire [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ee0a9-129">At the Distributor on the distribution database, execute [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span></span> <span data-ttu-id="ee0a9-130">Se l'utente non è elencato in `UserName` nel set di risultati, è necessario concedere all'utente l'accesso al database di distribuzione utilizzando l'istruzione [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ee0a9-130">If the user is not listed in `UserName` in the result set, the user must be granted access to the distribution database using the [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) statement.</span></span>  
  
2.  <span data-ttu-id="ee0a9-131">Nel database di distribuzione del server di distribuzione eseguire [sp_helprolemember &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), specificando il valore `replmonitor` per il **@rolename** parametro.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-131">At the Distributor on the distribution database, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), specifying a value of `replmonitor` for the **@rolename** parameter.</span></span> <span data-ttu-id="ee0a9-132">Se l'utente è elencato in `MemberName` nel set di risultati, l'utente appartiene già a questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-132">If the user is listed in `MemberName` in the result set, the user already belongs to this role.</span></span>  
  
3.  <span data-ttu-id="ee0a9-133">Se l'utente non appartiene al `replmonitor` ruolo, eseguire [sp_addrolemember &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) nel database di distribuzione del server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-133">If the user does not belong to the `replmonitor` role, execute [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="ee0a9-134">Specificare il valore `replmonitor` per **@rolename** e il nome dell'utente del database o l'account di accesso di Windows per il quale si desidera [!INCLUDE[msCoName](../../../includes/msconame-md.md)] aggiungere **@membername** .</span><span class="sxs-lookup"><span data-stu-id="ee0a9-134">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows login being added for **@membername**.</span></span>  
  
#### <a name="to-remove-a-user-from-the-replmonitor-fixed-database-role"></a><span data-ttu-id="ee0a9-135">Per rimuovere un utente dal ruolo predefinito del database replmonitor</span><span class="sxs-lookup"><span data-stu-id="ee0a9-135">To remove a user from the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="ee0a9-136">Per verificare che l'utente appartenga al `replmonitor` ruolo, eseguire [sp_helprolemember &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) nel database di distribuzione del server di distribuzione e specificare il valore `replmonitor` per **@rolename** .</span><span class="sxs-lookup"><span data-stu-id="ee0a9-136">To verify that the user belongs to the `replmonitor` role, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) at the Distributor on the distribution database, and specify a value of `replmonitor` for **@rolename**.</span></span> <span data-ttu-id="ee0a9-137">Se l'utente non è elencato in `MemberName` nel set di risultati, attualmente non appartiene al ruolo.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-137">If the user is not listed in `MemberName` in the result set, the user does not currently belong to this role.</span></span>  
  
2.  <span data-ttu-id="ee0a9-138">Se l'utente appartiene al `replmonitor` ruolo, eseguire [sp_droprolemember &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) nel database di distribuzione del server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ee0a9-138">If the user does belong to the `replmonitor` role, execute [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="ee0a9-139">Specificare il valore `replmonitor` per **@rolename** e il nome dell'utente del database o l'account di accesso di Windows da rimuovere per **@membername** .</span><span class="sxs-lookup"><span data-stu-id="ee0a9-139">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the Windows login being removed for **@membername**.</span></span>  
  
  
