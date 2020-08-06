---
title: Consenti a un endpoint del mirroring del database di utilizzare i certificati per le connessioni in ingresso (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- inbound connections
- database mirroring [SQL Server], security
ms.assetid: 5d48bb98-61f0-4b99-8f1a-b53f831d63d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c05397dfbd1740293c4b154ace1ed5704cec11a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624921"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-inbound-connections-transact-sql"></a><span data-ttu-id="371bb-102">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in entrata (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="371bb-102">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="371bb-103">In questo argomento viene illustrata la procedura per configurare le istanze del server in modo da utilizzare i certificati per l'autenticazione delle connessioni in ingresso per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="371bb-103">This topic describes the steps for configuring server instances to use certificates to authenticate inbound connections for database mirroring.</span></span> <span data-ttu-id="371bb-104">Prima di impostare le connessioni in entrata, è necessario configurare le connessioni in uscita in ogni istanza del server.</span><span class="sxs-lookup"><span data-stu-id="371bb-104">Before you can set up inbound connections, you must configure outbound connections on each server instance.</span></span> <span data-ttu-id="371bb-105">Per altre informazioni, vedere [Impostare l'endpoint del mirroring del database per l'uso di certificati per le connessioni in uscita &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="371bb-105">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
 <span data-ttu-id="371bb-106">Il processo di configurazione delle connessioni in entrata include i passaggi generali seguenti:</span><span class="sxs-lookup"><span data-stu-id="371bb-106">The process of configuring inbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="371bb-107">Creare un account di accesso per l'altro sistema.</span><span class="sxs-lookup"><span data-stu-id="371bb-107">Create a login for other system.</span></span>  
  
2.  <span data-ttu-id="371bb-108">Creare un utente per tale account di accesso.</span><span class="sxs-lookup"><span data-stu-id="371bb-108">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="371bb-109">Ottenere il certificato per l'endpoint del mirroring dell'altra istanza del server.</span><span class="sxs-lookup"><span data-stu-id="371bb-109">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="371bb-110">Associare il certificato all'utente creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="371bb-110">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="371bb-111">Concedere l'autorizzazione CONNECT all'account di accesso per l'endpoint del mirroring.</span><span class="sxs-lookup"><span data-stu-id="371bb-111">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="371bb-112">Se è disponibile un server di controllo del mirroring, è necessario configurare le connessioni in ingresso anche per tale server.</span><span class="sxs-lookup"><span data-stu-id="371bb-112">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="371bb-113">Questa operazione prevede la configurazione di account di accesso, utenti e certificati per il server di controllo del mirroring in entrambi i partner, e viceversa.</span><span class="sxs-lookup"><span data-stu-id="371bb-113">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="371bb-114">Questa procedura descrive i vari passaggi,</span><span class="sxs-lookup"><span data-stu-id="371bb-114">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="371bb-115">Per ogni passaggio la procedura fornisce un esempio di configurazione di un istanza di server in un sistema denominato HOST_A.</span><span class="sxs-lookup"><span data-stu-id="371bb-115">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="371bb-116">Nella sezione di esempio corrispondente vengono indicati gli stessi passaggi per un'altra istanza di server in un sistema denominato HOST_B.</span><span class="sxs-lookup"><span data-stu-id="371bb-116">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
### <a name="to-configure-server-instances-for-inbound-mirroring-connections-on-host_a"></a><span data-ttu-id="371bb-117">Per configurare le istanze del server per le connessioni per il mirroring in ingresso (on HOST_A)</span><span class="sxs-lookup"><span data-stu-id="371bb-117">To configure server instances for inbound mirroring connections (on HOST_A)</span></span>  
  
1.  <span data-ttu-id="371bb-118">Creare un account di accesso per l'altro sistema.</span><span class="sxs-lookup"><span data-stu-id="371bb-118">Create a login for the other system.</span></span>  
  
     <span data-ttu-id="371bb-119">Nell'esempio seguente viene creato un account di accesso per il sistema, HOST_B, nel database **master** dell'istanza del server in HOST_A. Tale account di accesso è denominato `HOST_B_login`.</span><span class="sxs-lookup"><span data-stu-id="371bb-119">The following example creates a login for the system, HOST_B, in the **master** database of the server instance on HOST_A; in this example, the login is named `HOST_B_login`.</span></span> <span data-ttu-id="371bb-120">Sostituire la password di esempio con una password personalizzata.</span><span class="sxs-lookup"><span data-stu-id="371bb-120">Substitute a password of your own for the sample password.</span></span>  
  
    ```sql  
    USE master;  
    CREATE LOGIN HOST_B_login   
       WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
     <span data-ttu-id="371bb-121">Per altre informazioni, vedere [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="371bb-121">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
     <span data-ttu-id="371bb-122">Per visualizzare gli account di accesso in questa istanza del server, è possibile utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="371bb-122">To view the logins on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.server_principals;  
    ```  
  
     <span data-ttu-id="371bb-123">Per altre informazioni, vedere [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="371bb-123">For more information, see [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span></span>  
  
2.  <span data-ttu-id="371bb-124">Creare un utente per tale account di accesso.</span><span class="sxs-lookup"><span data-stu-id="371bb-124">Create a user for that login.</span></span>  
  
     <span data-ttu-id="371bb-125">Nell'esempio seguente viene creato l'utente `HOST_B_user` per l'account di accesso creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="371bb-125">The following example creates a user, `HOST_B_user`, for the login created in the preceding step.</span></span>  
  
    ```sql  
    USE master;  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
     <span data-ttu-id="371bb-126">Per altre informazioni, vedere [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="371bb-126">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
     <span data-ttu-id="371bb-127">Per visualizzare gli utenti in questa istanza del server, è possibile utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="371bb-127">To view the users on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.sysusers;  
    ```  
  
     <span data-ttu-id="371bb-128">Per altre informazioni, vedere [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="371bb-128">For more information, see [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span></span>  
  
3.  <span data-ttu-id="371bb-129">Ottenere il certificato per l'endpoint del mirroring dell'altra istanza del server.</span><span class="sxs-lookup"><span data-stu-id="371bb-129">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
     <span data-ttu-id="371bb-130">Se questa operazione non è già stata eseguita durante la configurazione delle connessioni in uscita, ottenere una copia del certificato per l'endpoint del mirroring dell'istanza del server remoto.</span><span class="sxs-lookup"><span data-stu-id="371bb-130">If you have not already done so when configuring outbound connections, obtain a copy of the certificate for the mirroring endpoint of the remote server instance.</span></span> <span data-ttu-id="371bb-131">A tale scopo, eseguire il backup del certificato in tale istanza del server, come illustrato in [Impostare l'endpoint del mirroring del database per l'uso di certificati per le connessioni in uscita &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="371bb-131">To do this, back up the certificate on that server instance as described in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span> <span data-ttu-id="371bb-132">Quando si copia un certificato in un altro sistema, utilizzare un metodo di copia sicuro.</span><span class="sxs-lookup"><span data-stu-id="371bb-132">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="371bb-133">È estremamente importante garantire la protezione di tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="371bb-133">Be extremely careful to keep all of your certificates secure.</span></span>  
  
     <span data-ttu-id="371bb-134">Per altre informazioni, vedere [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="371bb-134">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
4.  <span data-ttu-id="371bb-135">Associare il certificato all'utente creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="371bb-135">Associate the certificate with the user created in step 2.</span></span>  
  
     <span data-ttu-id="371bb-136">Nell'esempio seguente, il certificato di HOST_B viene associato al relativo utente in HOST_A.</span><span class="sxs-lookup"><span data-stu-id="371bb-136">The following example, associates the certificate of HOST_B with its user on HOST_A.</span></span>  
  
    ```sql  
    USE master;  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
     <span data-ttu-id="371bb-137">Per altre informazioni, vedere [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="371bb-137">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="371bb-138">Per visualizzare i certificati in questa istanza del server, utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="371bb-138">To view the certificates on this server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="371bb-139">Per altre informazioni, vedere [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="371bb-139">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
5.  <span data-ttu-id="371bb-140">Concedere l'autorizzazione CONNECT per l'account di accesso per l'endpoint del mirroring remoto.</span><span class="sxs-lookup"><span data-stu-id="371bb-140">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
     <span data-ttu-id="371bb-141">Per concedere l'autorizzazione in HOST_A all'istanza del server remoto in HOST_B per la connessione al relativo account di accesso locale `HOST_B_login`, ad esempio, usare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="371bb-141">For example, to grant permission on HOST_A to the remote server instance on HOST_B to connect to its local login-that is, to connect to `HOST_B_login`-use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```sql  
    USE master;  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
     <span data-ttu-id="371bb-142">Per altre informazioni, vedere [GRANT - autorizzazioni per endpoint &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="371bb-142">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="371bb-143">A questo punto, è stata completata la configurazione dell'autenticazione tramite un certificato per la connessione di HOST_B a HOST_A.</span><span class="sxs-lookup"><span data-stu-id="371bb-143">This completes setting up certificate authentication for HOST_B to log in to HOST_A.</span></span>  
  
 <span data-ttu-id="371bb-144">È ora necessario eseguire i rispettivi passaggi in ingresso per HOST_A in HOST_B.</span><span class="sxs-lookup"><span data-stu-id="371bb-144">You now need to perform the equivalent inbound steps for HOST_A on HOST_B.</span></span> <span data-ttu-id="371bb-145">Tali passaggi sono illustrati nella parte relativa alle connessioni in ingresso della sezione di esempio riportata più avanti.</span><span class="sxs-lookup"><span data-stu-id="371bb-145">These steps are illustrated in the inbound portion of the example in the Example section, below.</span></span>  
  
## <a name="example"></a><span data-ttu-id="371bb-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="371bb-146">Example</span></span>  
 <span data-ttu-id="371bb-147">Nell'esempio seguente viene illustrata la configurazione di HOST_B per le connessioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="371bb-147">The following example demonstrates configuring HOST_B for inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="371bb-148">L'esempio usa un file di certificato contenente il certificato di HOST_A creato da un frammento di codice in [Impostare l'endpoint del mirroring del database per l'uso di certificati per le connessioni in uscita &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="371bb-148">This example uses a certificate file containing the HOST_A certificate that is created by a code snippet in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
```sql  
USE master;  
--On HOST_B, create a login for HOST_A.  
CREATE LOGIN HOST_A_login WITH PASSWORD = 'AStrongPassword!@#';  
GO  
--Create a user, HOST_A_user, for that login.  
CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
GO  
--Obtain HOST_A certificate. (See the note   
--   preceding this example.)  
--Asscociate this certificate with the user, HOST_A_user.  
CREATE CERTIFICATE HOST_A_cert  
   AUTHORIZATION HOST_A_user  
   FROM FILE = 'C:\HOST_A_cert.cer';  
GO  
--Grant CONNECT permission for the server instance on HOST_A.  
GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO HOST_A_login;  
GO  
```  
  
 <span data-ttu-id="371bb-149">Se si prevede di utilizzare la modalità a sicurezza elevata con failover automatico, è necessario ripetere gli stessi passaggi di impostazione per configurare il server di controllo del mirroring per connessioni in uscita e in ingresso.</span><span class="sxs-lookup"><span data-stu-id="371bb-149">If you intend to run in high-safety mode with automatic failover, you must repeat the same set up steps to configure the witness for outbound and inbound connections.</span></span>  
  
 <span data-ttu-id="371bb-150">Per informazioni sulla creazione di un database mirror e un esempio di Transact-SQL, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="371bb-150">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="371bb-151">Per un esempio di Transact-SQL per stabilire una sessione in modalità a prestazioni elevate, vedere [Esempio: Configurazione del mirroring del database tramite certificati &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="371bb-151">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="371bb-152">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="371bb-152">.NET Framework Security</span></span>  
 <span data-ttu-id="371bb-153">Quando si copia un certificato in un altro sistema, utilizzare un metodo di copia sicuro.</span><span class="sxs-lookup"><span data-stu-id="371bb-153">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="371bb-154">È estremamente importante garantire la protezione di tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="371bb-154">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371bb-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="371bb-155">See Also</span></span>  
 <span data-ttu-id="371bb-156">[Sicurezza del trasporto per il mirroring del database e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="371bb-156">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="371bb-157">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="371bb-157">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 <span data-ttu-id="371bb-158">[Configurare un database mirror crittografato](set-up-an-encrypted-mirror-database.md) </span><span class="sxs-lookup"><span data-stu-id="371bb-158">[Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md) </span></span>  
 <span data-ttu-id="371bb-159">[Endpoint del mirroring del database &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="371bb-159">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 [<span data-ttu-id="371bb-160">Risolvere i problemi relativi alla configurazione del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="371bb-160">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
