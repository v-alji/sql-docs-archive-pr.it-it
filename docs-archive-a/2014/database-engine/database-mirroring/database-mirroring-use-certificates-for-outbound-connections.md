---
title: Consenti a un endpoint del mirroring del database di utilizzare i certificati per le connessioni in uscita (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- outbound connections [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 464c9096-10d6-4c5e-8bb1-19acba27ad9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f380f268f8d0f8d033db9c28f83d066d3f134571
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624920"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-outbound-connections-transact-sql"></a><span data-ttu-id="53977-102">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in uscita (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="53977-102">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="53977-103">In questo argomento vengono illustrati i passaggi per la configurazione delle istanze del server per l'utilizzo di certificati per l'autenticazione delle connessioni in uscita per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="53977-103">This topic describes the steps for configuring server instances to use certificates to authenticate outbound connections for database mirroring.</span></span> <span data-ttu-id="53977-104">Prima di impostare le connessioni in ingresso, è necessario configurare quelle in uscita.</span><span class="sxs-lookup"><span data-stu-id="53977-104">Outbound connection configuration must be done before you can set up inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53977-105">Tutte le connessioni per il mirroring in un'istanza del server utilizzano un singolo endpoint del mirroring del database ed è necessario specificare il metodo di autenticazione dell'istanza del server quando si crea l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="53977-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span>  
  
 <span data-ttu-id="53977-106">Il processo di configurazione delle connessioni in uscita comprende i passaggi generali seguenti:</span><span class="sxs-lookup"><span data-stu-id="53977-106">The process of configuring outbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="53977-107">Nel database **master** creare una chiave master del database.</span><span class="sxs-lookup"><span data-stu-id="53977-107">In the **master** database, create a database Master Key.</span></span>  
  
2.  <span data-ttu-id="53977-108">Nel database **master** creare un certificato crittografato nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="53977-108">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="53977-109">Creare un endpoint per l'istanza del server utilizzando il relativo certificato.</span><span class="sxs-lookup"><span data-stu-id="53977-109">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="53977-110">Eseguire il backup del certificato in un file e copiarlo nell'altro sistema o negli altri sistemi.</span><span class="sxs-lookup"><span data-stu-id="53977-110">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="53977-111">È necessario eseguire questa procedura per ogni partner e per il server di controllo del mirroring, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="53977-111">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="53977-112">Questa procedura descrive i vari passaggi,</span><span class="sxs-lookup"><span data-stu-id="53977-112">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="53977-113">Per ogni passaggio la procedura fornisce un esempio di configurazione di un istanza di server in un sistema denominato HOST_A.</span><span class="sxs-lookup"><span data-stu-id="53977-113">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="53977-114">Nella sezione di esempio corrispondente vengono indicati gli stessi passaggi per un'altra istanza di server in un sistema denominato HOST_B.</span><span class="sxs-lookup"><span data-stu-id="53977-114">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="53977-115">Procedura</span><span class="sxs-lookup"><span data-stu-id="53977-115">Procedure</span></span>  
  
#### <a name="to-configure-server-instances-for-outbound-mirroring-connections-on-host_a"></a><span data-ttu-id="53977-116">Per configurare le istanze del server per le connessioni per il mirroring in uscita (On HOST_A)</span><span class="sxs-lookup"><span data-stu-id="53977-116">To configure server instances for outbound mirroring connections (On HOST_A)</span></span>  
  
1.  <span data-ttu-id="53977-117">Nel database **master** creare la chiave master del database, se non è già presente.</span><span class="sxs-lookup"><span data-stu-id="53977-117">On the **master** database, create the database Master Key, if none exists.</span></span> <span data-ttu-id="53977-118">Per visualizzare le chiavi esistenti per un database, usare la vista del catalogo [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="53977-118">To view the existing keys for a database, use the [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) catalog view.</span></span>  
  
     <span data-ttu-id="53977-119">Per creare la chiave master del database, utilizzare il comando [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="53977-119">To create the database Master Key, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command:</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
     <span data-ttu-id="53977-120">Utilizzare una password complessa univoca e archiviarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="53977-120">Use a unique, strong password, and record it in a safe place.</span></span>  
  
     <span data-ttu-id="53977-121">Per altre informazioni, vedere [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) e [Creazione della chiave master di un database](../../relational-databases/security/encryption/create-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="53977-121">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) and [Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md).</span></span>  
  
2.  <span data-ttu-id="53977-122">Nel database **master** creare un certificato crittografato nell'istanza del server da usare per le connessioni in uscita per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="53977-122">In the **master** database, create an encrypted certificate on the server instance to use for its outbound connections for database mirroring.</span></span>  
  
     <span data-ttu-id="53977-123">Per creare, ad esempio, un certificato per il sistema HOST_A:</span><span class="sxs-lookup"><span data-stu-id="53977-123">For example, to create a certificate for the HOST_A system.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="53977-124">Se si desidera utilizzare il certificato per più di un anno, specificare la data di scadenza in base all'ora UTC tramite l'opzione EXPIRY_DATE nell'istruzione CREATE CERTIFICATE.</span><span class="sxs-lookup"><span data-stu-id="53977-124">If you intend to use the certificate for more than one year, specify the expiry date in UTC time by using the EXPIRY_DATE option in your CREATE CERTIFICATE statement.</span></span> <span data-ttu-id="53977-125">È inoltre consigliabile utilizzare SQL Server Management Studio per creare una regola di gestione basata su criteri per ricevere un avviso quando i certificati stanno scadendo.</span><span class="sxs-lookup"><span data-stu-id="53977-125">Also, we recommend that you use SQL Server Management Studio to create a Policy-Based Management rule to alert you when your certificates are expiring.</span></span> <span data-ttu-id="53977-126">Usando la finestra di dialogo **Crea nuova condizione** di Gestione criteri creare questa regola nel campo **@ExpirationDate** del facet **Certificato** .</span><span class="sxs-lookup"><span data-stu-id="53977-126">Using the Policy Management **Create New Condition** dialog box, create this rule on the **@ExpirationDate** field of the **Certificate** facet.</span></span> <span data-ttu-id="53977-127">Per altre informazioni, vedere [Amministrazione di server tramite la gestione basata su criteri](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) e [Sicurezza di SQL Server](../../relational-databases/security/securing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="53977-127">For more information, see [Administer Servers by Using Policy-Based Management](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) and [Securing SQL Server](../../relational-databases/security/securing-sql-server.md).</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate for database mirroring',   
       EXPIRY_DATE = '11/30/2013';  
    GO  
    ```  
  
     <span data-ttu-id="53977-128">Per altre informazioni, vedere [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53977-128">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="53977-129">Per visualizzare i certificati nel database**master**, usare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="53977-129">To view the certificates in the **master** database, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="53977-130">Per altre informazioni, vedere [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53977-130">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
3.  <span data-ttu-id="53977-131">Verificare che in ognuna delle istanze del server sia presente l'endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="53977-131">Ensure that the database mirroring endpoint exist on each of the server instances.</span></span>  
  
     <span data-ttu-id="53977-132">Se per l'istanza del server è già presente un endpoint del mirroring del database, riutilizzare tale endpoint per tutte le altre sessioni avviate nella stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="53977-132">If a database mirroring endpoint already exists for the server instance, you should reuse that endpoint for any other sessions you establish on the server instance.</span></span> <span data-ttu-id="53977-133">Per determinare se in un'istanza del server è presente un endpoint del mirroring del database e per visualizzarne la configurazione, utilizzare l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="53977-133">To determine whether a database mirroring endpoint exists on a server instance and to view its configuration, use the following statement:</span></span>  
  
    ```  
    SELECT name, role_desc, state_desc, connection_auth_desc, encryption_algorithm_desc   
       FROM sys.database_mirroring_endpoints;  
    ```  
  
     <span data-ttu-id="53977-134">Se non sono presenti endpoint, creare un endpoint che utilizzi questo certificato per le connessioni in uscita e che utilizzi le credenziali del certificato per la verifica nell'altro sistema.</span><span class="sxs-lookup"><span data-stu-id="53977-134">If no endpoint exists, create an endpoint that uses this certificate for outbound connections and that uses the certificate's credentials for verification on the other system.</span></span> <span data-ttu-id="53977-135">Si tratta di un endpoint valido per l'intero server, utilizzato da tutte le sessioni di mirroring a cui partecipa l'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="53977-135">This is a server-wide endpoint that is used by all mirroring sessions in which the server instance participates.</span></span>  
  
     <span data-ttu-id="53977-136">Per creare, ad esempio, un endpoint del mirroring per l'istanza del server di esempio in HOST_A.</span><span class="sxs-lookup"><span data-stu-id="53977-136">For example, to create a mirroring endpoint for the example server instance on HOST_A.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_A_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
     <span data-ttu-id="53977-137">Per altre informazioni, vedere [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53977-137">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
4.  <span data-ttu-id="53977-138">Eseguire il backup del certificarlo e copiarlo nell'altro o negli altri sistemi.</span><span class="sxs-lookup"><span data-stu-id="53977-138">Back up the certificate and copy it to the other system or systems.</span></span> <span data-ttu-id="53977-139">Si tratta di un'operazione necessaria per configurare le connessioni in ingresso nell'altro sistema.</span><span class="sxs-lookup"><span data-stu-id="53977-139">This is necessary in order to configure inbound connections on the other system.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
     <span data-ttu-id="53977-140">Per altre informazioni, vedere [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53977-140">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="53977-141">Copiare questo certificato utilizzando un metodo che ne garantisca la protezione.</span><span class="sxs-lookup"><span data-stu-id="53977-141">Copy this certificate using any secure method you choose.</span></span> <span data-ttu-id="53977-142">È estremamente importante garantire la protezione di tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="53977-142">Be extremely careful to keep all of your certificates secure.</span></span>  
  
 <span data-ttu-id="53977-143">Tramite il codice di esempio del passaggio precedente vengono configurate le connessioni in uscita in HOST_A.</span><span class="sxs-lookup"><span data-stu-id="53977-143">The example code in the preceding steps configure outbound connections on HOST_A.</span></span>  
  
 <span data-ttu-id="53977-144">È ora necessario eseguire i rispettivi passaggi in uscita per HOST_B.</span><span class="sxs-lookup"><span data-stu-id="53977-144">You now need to perform the equivalent outbound steps for HOST_B.</span></span> <span data-ttu-id="53977-145">I passaggi sono illustrati nella sezione di esempio indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="53977-145">These steps are illustrated in the following Example section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53977-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="53977-146">Example</span></span>  
 <span data-ttu-id="53977-147">Nell'esempio seguente viene illustrata la configurazione di HOST_B per le connessioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="53977-147">The following example demonstrates configuring HOST_B for outbound connections.</span></span>  
  
```  
USE master;  
--Create the database Master Key, if needed.  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
GO  
-- Make a certifcate on HOST_B server instance.  
CREATE CERTIFICATE HOST_B_cert   
   WITH SUBJECT = 'HOST_B certificate for database mirroring',   
   EXPIRY_DATE = '11/30/2013';  
GO  
--Create a mirroring endpoint for the server instance on HOST_B.  
CREATE ENDPOINT Endpoint_Mirroring  
   STATE = STARTED  
   AS TCP (  
      LISTENER_PORT=7024  
      , LISTENER_IP = ALL  
   )   
   FOR DATABASE_MIRRORING (   
      AUTHENTICATION = CERTIFICATE HOST_B_cert  
      , ENCRYPTION = REQUIRED ALGORITHM AES  
      , ROLE = ALL  
   );  
GO  
--Backup HOST_B certificate.  
BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
GO   
--Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.  
```  
  
 <span data-ttu-id="53977-148">Copiare il certificato nell'altro sistema utilizzando un metodo che ne garantisca la protezione.</span><span class="sxs-lookup"><span data-stu-id="53977-148">Copy the certificate to the other system using any secure method you choose.</span></span> <span data-ttu-id="53977-149">È estremamente importante garantire la protezione di tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="53977-149">Be extremely careful to keep all of your certificates secure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="53977-150">Dopo avere configurato le connessioni in uscita, è necessario configurare quelle in ingresso in ogni istanza del server per l'altra o le altre istanze.</span><span class="sxs-lookup"><span data-stu-id="53977-150">After you set up outbound connections, you must configure inbound connections on each server instance for the other server instance or instances.</span></span> <span data-ttu-id="53977-151">Per altre informazioni, vedere [Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="53977-151">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
 <span data-ttu-id="53977-152">Per informazioni sulla creazione di un database mirror e un esempio di Transact-SQL, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="53977-152">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="53977-153">Per un esempio di Transact-SQL per stabilire una sessione in modalità a prestazioni elevate, vedere [Esempio: Configurazione del mirroring del database tramite certificati &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="53977-153">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="53977-154">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="53977-154">.NET Framework Security</span></span>  
 <span data-ttu-id="53977-155">A meno che la sicurezza della rete in uso non sia già garantita, è consigliabile utilizzare la crittografia per le connessioni per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="53977-155">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="53977-156">Quando si copia un certificato in un altro sistema, utilizzare un metodo di copia sicuro.</span><span class="sxs-lookup"><span data-stu-id="53977-156">When copying a certificate to another system, use a secure copy method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53977-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53977-157">See Also</span></span>  
 <span data-ttu-id="53977-158">[Scelta di un algoritmo di crittografia](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="53977-158">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="53977-159">[Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="53977-159">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="53977-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="53977-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="53977-161">[Esempio: Configurazione del mirroring del database tramite certificati &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="53977-161">[Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span></span>  
 <span data-ttu-id="53977-162">[Endpoint del mirroring del database &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="53977-162">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="53977-163">[Risolvere i problemi relativi alla configurazione del mirroring del database &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="53977-163">[Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span></span>  
 [<span data-ttu-id="53977-164">Impostazione di un database mirror crittografato</span><span class="sxs-lookup"><span data-stu-id="53977-164">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
