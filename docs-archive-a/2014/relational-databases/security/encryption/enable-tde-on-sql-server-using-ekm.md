---
title: Abilitare Transparent Data Encryption con EKM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], TDE using an EKM
- TDE, EKM how to
- EKM, TDE how to
- Transparent Data Encryption, using EKM
ms.assetid: b892e7a7-95bd-4903-bf54-55ce08e225af
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: e659c5ff0245fdb17192b845eafc60badf5e295e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725391"
---
# <a name="enable-tde-using-ekm"></a><span data-ttu-id="e2374-102">Abilitare TDE utilizzando EKM</span><span class="sxs-lookup"><span data-stu-id="e2374-102">Enable TDE Using EKM</span></span>
  <span data-ttu-id="e2374-103">In questo argomento viene descritto come abilitare Transparent Data Encryption (TDE) in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] per proteggere una chiave di crittografia del database tramite una chiave asimmetrica archiviata in un modulo Extensible Key Management (EKM) con [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2374-103">This topic describes how to enable transparent data encryption (TDE) in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to protect a database encryption key by using an asymmetric key stored in an extensible key management (EKM) module with [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e2374-104">TDE esegue la crittografia dello spazio di archiviazione di un intero database usando una chiave simmetrica detta "chiave di crittografia del database".</span><span class="sxs-lookup"><span data-stu-id="e2374-104">TDE encrypts the storage of an entire database by using a symmetric key called the database encryption key.</span></span> <span data-ttu-id="e2374-105">È inoltre possibile proteggere la chiave di crittografia del database utilizzando un certificato protetto dalla chiave master del database master.</span><span class="sxs-lookup"><span data-stu-id="e2374-105">The database encryption key can also be protected using a certificate which is protected by the database master key of the master database.</span></span> <span data-ttu-id="e2374-106">Per altre informazioni sulla protezione della chiave di crittografia del database tramite la chiave master del database, vedere [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="e2374-106">For more information about protecting the database encryption key by using the database master key, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span> <span data-ttu-id="e2374-107">Per informazioni sulla configurazione di TDE quando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è in esecuzione in una macchina virtuale di Azure, vedere [Extensible Key Management con l'insieme di credenziali delle chiavi di Azure &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e2374-107">For information about configuring TDE when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running on an Azure VM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
 <span data-ttu-id="e2374-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e2374-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e2374-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e2374-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e2374-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e2374-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e2374-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e2374-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="e2374-112">Per abilitare TDE utilizzando EKM tramite Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2374-112">To enable TDE using EKM, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e2374-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e2374-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e2374-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e2374-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e2374-115">Per creare una chiave di crittografia del database e crittografare un database, è necessario essere un utente con privilegi elevati, ad esempio un amministratore di sistema,</span><span class="sxs-lookup"><span data-stu-id="e2374-115">You must be a high privileged user (such as a system administrator) to create a database encryption key and encrypt a database.</span></span> <span data-ttu-id="e2374-116">che possa essere autenticato dal modulo EKM.</span><span class="sxs-lookup"><span data-stu-id="e2374-116">That user must be able to be authenticated by the EKM module.</span></span>  
  
-   <span data-ttu-id="e2374-117">All'avvio il [!INCLUDE[ssDE](../../../includes/ssde-md.md)] deve aprire il database.</span><span class="sxs-lookup"><span data-stu-id="e2374-117">Upon start up the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must open the database.</span></span> <span data-ttu-id="e2374-118">A tal fine, è necessario creare le credenziali che dovranno essere autenticate dal modulo EKM e aggiungerle a un account di accesso basato su una chiave asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="e2374-118">To do this, you should create a credential that will be authenticated by the EKM, and add it to a login that is based on an asymmetric key.</span></span> <span data-ttu-id="e2374-119">Gli utenti non possono eseguire l'accesso utilizzando tale account, ma il [!INCLUDE[ssDE](../../../includes/ssde-md.md)] sarà in grado di effettuare l'autenticazione con il dispositivo EKM.</span><span class="sxs-lookup"><span data-stu-id="e2374-119">Users cannot login using that login, but the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] will be able to authenticate itself with the EKM device.</span></span>  
  
-   <span data-ttu-id="e2374-120">In caso di perdita della chiave asimmetrica archiviata nel modulo EKM, il database non potrà essere aperto in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2374-120">If the asymmetric key stored in the EKM module is lost, the database will not be able to be opened by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e2374-121">Se il provider EKM consente di eseguire il backup della chiave asimmetrica, è consigliabile creare una copia di backup e archiviarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="e2374-121">If the EKM provider lets you back up the asymmetric key, you should create a back up and store it in a secure location.</span></span>  
  
-   <span data-ttu-id="e2374-122">Le opzioni e i parametri richiesti dal provider EKM possono differire da quanto indicato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e2374-122">The options and parameters required by your EKM provider can differ from what is provided in the code example below.</span></span> <span data-ttu-id="e2374-123">Per altre informazioni, rivolgersi al provider EKM.</span><span class="sxs-lookup"><span data-stu-id="e2374-123">For more information, see your EKM provider.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e2374-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e2374-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e2374-125">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e2374-125">Permissions</span></span>  
 <span data-ttu-id="e2374-126">In questo argomento vengono utilizzate le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2374-126">This topic uses the following permissions:</span></span>  
  
-   <span data-ttu-id="e2374-127">Per modificare un'opzione di configurazione ed eseguire l'istruzione RECONFIGURE, è necessario disporre dell'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="e2374-127">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="e2374-128">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="e2374-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
-   <span data-ttu-id="e2374-129">È richiesta l'autorizzazione ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="e2374-129">Requires ALTER ANY CREDENTIAL permission.</span></span>  
  
-   <span data-ttu-id="e2374-130">È richiesta l'autorizzazione ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="e2374-130">Requires ALTER ANY LOGIN permission.</span></span>  
  
-   <span data-ttu-id="e2374-131">È necessaria l'autorizzazione CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="e2374-131">Requires CREATE ASYMMETRIC KEY permission.</span></span>  
  
-   <span data-ttu-id="e2374-132">È necessaria l'autorizzazione CONTROL nel database per crittografare il database.</span><span class="sxs-lookup"><span data-stu-id="e2374-132">Requires CONTROL permission on the database to encrypt the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e2374-133">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2374-133">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-tde-using-ekm"></a><span data-ttu-id="e2374-134">Per abilitare Transparent Data Encryption tramite Extensible Key Management</span><span class="sxs-lookup"><span data-stu-id="e2374-134">To enable TDE using EKM</span></span>  
  
1.  <span data-ttu-id="e2374-135">Copiare i file forniti dal provider EKM in un percorso appropriato nel computer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2374-135">Copy the files supplied by the EKM provider to an appropriate location on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="e2374-136">In questo esempio viene usata la cartella **C:\EKM** .</span><span class="sxs-lookup"><span data-stu-id="e2374-136">In this example, we use the **C:\EKM** folder.</span></span>  
  
2.  <span data-ttu-id="e2374-137">Installare i certificati nel computer in base a quanto richiesto dal provider EKM.</span><span class="sxs-lookup"><span data-stu-id="e2374-137">Install certificates to the computer as required by your EKM provider.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="e2374-138">non fornisce un provider EKM.</span><span class="sxs-lookup"><span data-stu-id="e2374-138">does not supply an EKM provider.</span></span> <span data-ttu-id="e2374-139">Ogni provider EKM può richiedere procedure diverse per l'installazione, la configurazione e l'autorizzazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e2374-139">Each EKM provider can have different procedures for installing, configuring and authorizing users.</span></span>  <span data-ttu-id="e2374-140">Per completare questo passaggio, consultare la documentazione del provider EKM.</span><span class="sxs-lookup"><span data-stu-id="e2374-140">Consult your EKM provider documentation to complete this step.</span></span>  
  
3.  <span data-ttu-id="e2374-141">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2374-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
4.  <span data-ttu-id="e2374-142">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e2374-142">On the Standard bar, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="e2374-143">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e2374-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Enable advanced options.  
    sp_configure 'show advanced options', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Enable EKM provider  
    sp_configure 'EKM provider enabled', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Create a cryptographic provider, which we have chosen to call "EKM_Prov," based on an EKM provider  
  
    CREATE CRYPTOGRAPHIC PROVIDER EKM_Prov   
    FROM FILE = 'C:\EKM_Files\KeyProvFile.dll' ;  
    GO  
  
    -- Create a credential that will be used by system administrators.  
    CREATE CREDENTIAL sa_ekm_tde_cred   
    WITH IDENTITY = 'Identity1',   
    SECRET = 'q*gtev$0u#D1v'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
    GO  
  
    -- Add the credential to a high privileged user such as your   
    -- own domain login in the format [DOMAIN\login].  
    ALTER LOGIN Contoso\Mary  
    ADD CREDENTIAL sa_ekm_tde_cred ;  
    GO  
    -- create an asymmetric key stored inside the EKM provider  
    USE master ;  
    GO  
    CREATE ASYMMETRIC KEY ekm_login_key   
    FROM PROVIDER [EKM_Prov]  
    WITH ALGORITHM = RSA_512,  
    PROVIDER_KEY_NAME = 'SQL_Server_Key' ;  
    GO  
  
    -- Create a credential that will be used by the Database Engine.  
    CREATE CREDENTIAL ekm_tde_cred   
    WITH IDENTITY = 'Identity2'   
    , SECRET = 'jeksi84&sLksi01@s'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
  
    -- Add a login used by TDE, and add the new credential to the login.  
    CREATE LOGIN EKM_Login   
    FROM ASYMMETRIC KEY ekm_login_key ;  
    GO  
    ALTER LOGIN EKM_Login   
    ADD CREDENTIAL ekm_tde_cred ;  
    GO  
  
    -- Create the database encryption key that will be used for TDE.  
    USE AdventureWorks2012 ;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM  = AES_128  
    ENCRYPTION BY SERVER ASYMMETRIC KEY ekm_login_key ;  
    GO  
  
    -- Alter the database to enable transparent data encryption.  
    ALTER DATABASE AdventureWorks2012   
    SET ENCRYPTION ON ;  
    GO  
    ```  
  
 <span data-ttu-id="e2374-144">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2374-144">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="e2374-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2374-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [<span data-ttu-id="e2374-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2374-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)  
  
-   [<span data-ttu-id="e2374-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2374-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="e2374-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2374-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)  
  
-   [<span data-ttu-id="e2374-149">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2374-149">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
-   [<span data-ttu-id="e2374-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2374-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="e2374-151">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2374-151">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
-   [<span data-ttu-id="e2374-152">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2374-152">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [<span data-ttu-id="e2374-153">Extensible Key Management con l'insieme di credenziali delle chiavi di Azure &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e2374-153">Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;</span></span>](extensible-key-management-using-azure-key-vault-sql-server.md)  
  
-   [<span data-ttu-id="e2374-154">Transparent Data Encryption con il database SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="e2374-154">Transparent Data Encryption with Azure SQL Database</span></span>](../../../database-engine/transparent-data-encryption-with-azure-sql-database.md)  
  
  
