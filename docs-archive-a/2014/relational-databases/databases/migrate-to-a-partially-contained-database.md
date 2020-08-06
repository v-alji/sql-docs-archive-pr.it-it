---
title: Eseguire la migrazione in un database parzialmente indipendente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, migrating to
ms.assetid: 90faac38-f79e-496d-b589-e8b2fe01c562
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6142d46dc0540e5998fa66d463538d1453a17d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725840"
---
# <a name="migrate-to-a-partially-contained-database"></a><span data-ttu-id="c764d-102">Migrate to a Partially Contained Database</span><span class="sxs-lookup"><span data-stu-id="c764d-102">Migrate to a Partially Contained Database</span></span>
  <span data-ttu-id="c764d-103">In questo argomento viene descritto come prepararsi al passaggio al modello del database parzialmente indipendente, quindi viene illustrata la procedura di migrazione.</span><span class="sxs-lookup"><span data-stu-id="c764d-103">This topic discusses how to prepare to change to the partially contained database model and then provides the migration steps.</span></span>  
  
 <span data-ttu-id="c764d-104">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="c764d-104">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="c764d-105">Preparazione della migrazione di un database</span><span class="sxs-lookup"><span data-stu-id="c764d-105">Preparing to Migrate a Database</span></span>](#prepare)  
  
-   [<span data-ttu-id="c764d-106">Abilitazione di database indipendenti</span><span class="sxs-lookup"><span data-stu-id="c764d-106">Enable Contained Databases</span></span>](#enable)  
  
-   [<span data-ttu-id="c764d-107">Conversione di un database a parzialmente indipendente</span><span class="sxs-lookup"><span data-stu-id="c764d-107">Converting a Database to Partially Contained</span></span>](#convert)  
  
-   [<span data-ttu-id="c764d-108">Migrazione di utenti a utenti di database indipendenti</span><span class="sxs-lookup"><span data-stu-id="c764d-108">Migrating Users to Contained Database Users</span></span>](#users)  
  
##  <a name="preparing-to-migrate-a-database"></a><a name="prepare"></a> <span data-ttu-id="c764d-109">Preparazione della migrazione di un database</span><span class="sxs-lookup"><span data-stu-id="c764d-109">Preparing to Migrate a Database</span></span>  
 <span data-ttu-id="c764d-110">Quando si considera la migrazione di un database al modello di database parzialmente indipendente, esaminare gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="c764d-110">Review the following items when considering migrating a database to the partially contained database model.</span></span>  
  
-   <span data-ttu-id="c764d-111">È necessario comprendere il modello del database parzialmente indipendente.</span><span class="sxs-lookup"><span data-stu-id="c764d-111">You should understand the partially contained database model.</span></span> <span data-ttu-id="c764d-112">Per altre informazioni, vedere [Database indipendenti](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="c764d-112">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
-   <span data-ttu-id="c764d-113">È necessario comprendere rischi specifici dei database parzialmente indipendenti.</span><span class="sxs-lookup"><span data-stu-id="c764d-113">You should understand risks that are unique to partially contained databases.</span></span> <span data-ttu-id="c764d-114">Per altre informazioni, vedere [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="c764d-114">For more information, see [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span></span>  
  
-   <span data-ttu-id="c764d-115">Nei database indipendenti non è supportato l'utilizzo di funzionalità di replica, di rilevamento modifiche o Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="c764d-115">Contained databases do not support replication, change data capture, or change tracking.</span></span> <span data-ttu-id="c764d-116">Verificare che nel database non vengano utilizzate queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c764d-116">Confirm the database does not use these features.</span></span>  
  
-   <span data-ttu-id="c764d-117">Esaminare l'elenco di funzionalità del database che vengono modificate per i database parzialmente indipendenti.</span><span class="sxs-lookup"><span data-stu-id="c764d-117">Review the list of database features that are modified for partially contained databases.</span></span> <span data-ttu-id="c764d-118">Per altre informazioni, vedere [Funzionalità modificate &#40;database indipendente&#41;](modified-features-contained-database.md).</span><span class="sxs-lookup"><span data-stu-id="c764d-118">For more information, see [Modified Features &#40;Contained Database&#41;](modified-features-contained-database.md).</span></span>  
  
-   <span data-ttu-id="c764d-119">Eseguire una query su [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) per trovare oggetti o funzionalità indipendenti nel database.</span><span class="sxs-lookup"><span data-stu-id="c764d-119">Query [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) to find uncontained objects or features in the database.</span></span> <span data-ttu-id="c764d-120">Per altre informazioni, vedere</span><span class="sxs-lookup"><span data-stu-id="c764d-120">For more information, see.</span></span>  
  
-   <span data-ttu-id="c764d-121">Controllare l'XEvent **database_uncontained_usage** per vedere quando vengono usate le funzionalità indipendenti.</span><span class="sxs-lookup"><span data-stu-id="c764d-121">Monitor the **database_uncontained_usage** XEvent to see when uncontained features are used.</span></span>  
  
##  <a name="enable-contained-databases"></a><a name="enable"></a> <span data-ttu-id="c764d-122">Abilitazione di database indipendenti</span><span class="sxs-lookup"><span data-stu-id="c764d-122">Enable Contained Databases</span></span>  
 <span data-ttu-id="c764d-123">Prima di poter creare database indipendenti, è necessario abilitarli nell'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c764d-123">Contained databases must be enabled on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], before contained databases can be created.</span></span>  
  
### <a name="enabling-contained-databases-using-transact-sql"></a><span data-ttu-id="c764d-124">Abilitazione di database indipendenti tramite Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c764d-124">Enabling Contained Databases Using Transact-SQL</span></span>  
 <span data-ttu-id="c764d-125">Nell'esempio seguente vengono abilitati database indipendenti nell'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c764d-125">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE ;  
GO  
```  
  
#### <a name="enabling-contained-databases-using-management-studio"></a><span data-ttu-id="c764d-126">Abilitazione di database indipendenti tramite Management Studio</span><span class="sxs-lookup"><span data-stu-id="c764d-126">Enabling Contained Databases Using Management Studio</span></span>  
 <span data-ttu-id="c764d-127">Nell'esempio seguente vengono abilitati database indipendenti nell'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c764d-127">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="c764d-128">In Esplora oggetti fare clic con il pulsante destro del mouse sul nome del server e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c764d-128">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c764d-129">Nella sezione **Indipendenza** della pagina **Avanzate** impostare l'opzione **Abilita database indipendenti** su **True**.</span><span class="sxs-lookup"><span data-stu-id="c764d-129">On the **Advanced** page, in the **Containment** section, set the **Enable Contained Databases** option to **True**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="converting-a-database-to-partially-contained"></a><a name="convert"></a> <span data-ttu-id="c764d-130">Conversione di un database a parzialmente indipendente</span><span class="sxs-lookup"><span data-stu-id="c764d-130">Converting a Database to Partially Contained</span></span>  
 <span data-ttu-id="c764d-131">Un database viene convertito in un database indipendente modificando l'opzione **CONTAINMENT** .</span><span class="sxs-lookup"><span data-stu-id="c764d-131">A database is converted to a contained database by changing the **CONTAINMENT** option.</span></span>  
  
### <a name="converting-a-database-to-partially-contained-using-transact-sql"></a><span data-ttu-id="c764d-132">Conversione di un database in parzialmente indipendente tramite Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c764d-132">Converting a Database to Partially Contained Using Transact-SQL</span></span>  
 <span data-ttu-id="c764d-133">Nell'esempio seguente un database denominato `Accounting` viene convertito in un database parzialmente indipendente.</span><span class="sxs-lookup"><span data-stu-id="c764d-133">The following example converts a database named `Accounting` to a partially contained database.</span></span>  
  
```sql  
USE [master]  
GO  
ALTER DATABASE [Accounting] SET CONTAINMENT = PARTIAL  
GO  
```  
  
### <a name="converting-a-database-to-partially-contained-using-management-studio"></a><span data-ttu-id="c764d-134">Conversione di un database in parzialmente indipendente tramite Management Studio</span><span class="sxs-lookup"><span data-stu-id="c764d-134">Converting a Database to Partially contained Using Management Studio</span></span>  
 <span data-ttu-id="c764d-135">Nell'esempio seguente un database viene convertito in un database parzialmente indipendente.</span><span class="sxs-lookup"><span data-stu-id="c764d-135">The following example converts a database to a partially contained database.</span></span>  
  
1.  <span data-ttu-id="c764d-136">In Esplora oggetti espandere **Database**, fare clic con il pulsante destro del mouse sul database da convertire, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c764d-136">In Object Explorer, expand **Databases**, right-click the database to be converted, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c764d-137">Nella pagina **Opzioni** impostare l'opzione **Tipo di indipendenza** su **Parziale**.</span><span class="sxs-lookup"><span data-stu-id="c764d-137">On the **Options** page, change the **Containment type** option to **Partial**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="migrating-users-to-contained-database-users"></a><a name="users"></a> <span data-ttu-id="c764d-138">Migrazione di utenti a utenti di database indipendenti</span><span class="sxs-lookup"><span data-stu-id="c764d-138">Migrating Users to Contained Database Users</span></span>  
 <span data-ttu-id="c764d-139">Nell'esempio seguente viene eseguita la migrazione di tutti gli utenti basati sugli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a utenti del database indipendente con password.</span><span class="sxs-lookup"><span data-stu-id="c764d-139">The following example migrates all users that are based on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins to contained database users with passwords.</span></span> <span data-ttu-id="c764d-140">Nell'esempio sono inclusi account di accesso non abilitati.</span><span class="sxs-lookup"><span data-stu-id="c764d-140">The example excludes logins that are not enabled.</span></span> <span data-ttu-id="c764d-141">L'esempio deve essere eseguito nel database indipendente.</span><span class="sxs-lookup"><span data-stu-id="c764d-141">The example must be executed in the contained database.</span></span>  
  
```sql  
DECLARE @username sysname ;  
DECLARE user_cursor CURSOR  
    FOR   
        SELECT dp.name   
        FROM sys.database_principals AS dp  
        JOIN sys.server_principals AS sp   
        ON dp.sid = sp.sid  
        WHERE dp.authentication_type = 1 AND sp.is_disabled = 0;  
OPEN user_cursor  
FETCH NEXT FROM user_cursor INTO @username  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        EXECUTE sp_migrate_user_to_contained   
        @username = @username,  
        @rename = N'keep_name',  
        @disablelogin = N'disable_login';  
    FETCH NEXT FROM user_cursor INTO @username  
    END  
CLOSE user_cursor ;  
DEALLOCATE user_cursor ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c764d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c764d-142">See Also</span></span>  
 <span data-ttu-id="c764d-143">[Database indipendenti](contained-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c764d-143">[Contained Databases](contained-databases.md) </span></span>  
 <span data-ttu-id="c764d-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c764d-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span></span>  
 [<span data-ttu-id="c764d-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c764d-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql)  
  
  
