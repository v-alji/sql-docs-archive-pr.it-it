---
title: 'Esempio: Configurazione del mirroring del database tramite certificati (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: df489ecd-deee-465c-a26a-6d1bef6d7b66
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea87e2de984107c5a0fda6eb2629ee5cfd197841
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726251"
---
# <a name="example-setting-up-database-mirroring-using-certificates-transact-sql"></a><span data-ttu-id="4c00f-102">Esempio: Configurazione del mirroring del database tramite certificati (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4c00f-102">Example: Setting Up Database Mirroring Using Certificates (Transact-SQL)</span></span>
  <span data-ttu-id="4c00f-103">In questo esempio vengono illustrati tutti i passaggi necessari per la creazione di una sessione di mirroring del database tramite l'autenticazione basata sui certificati.</span><span class="sxs-lookup"><span data-stu-id="4c00f-103">This example shows all the stages required to create a database mirroring session using certificate-based authentication.</span></span> <span data-ttu-id="4c00f-104">Negli esempi di questo argomento viene utilizzato [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c00f-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4c00f-105">A meno che la sicurezza della rete in uso non sia già garantita, è consigliabile utilizzare la crittografia per le connessioni per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="4c00f-105">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="4c00f-106">Quando si copia un certificato in un altro sistema, utilizzare un metodo di copia sicuro.</span><span class="sxs-lookup"><span data-stu-id="4c00f-106">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="4c00f-107">È estremamente importante garantire la protezione di tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="4c00f-107">Be extremely careful to keep all of your certificates secure.</span></span>  
  
##  <a name="example"></a><a name="ExampleH2"></a><span data-ttu-id="4c00f-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c00f-108">Example</span></span>  
 <span data-ttu-id="4c00f-109">Nell'esempio seguente vengono descritte le operazioni necessarie in un partner che risiede in HOST_A.</span><span class="sxs-lookup"><span data-stu-id="4c00f-109">The following example demonstrates what must be done on one partner that resides on HOST_A.</span></span> <span data-ttu-id="4c00f-110">Nell'esempio i due partner sono le istanze predefinite del server in tre sistemi.</span><span class="sxs-lookup"><span data-stu-id="4c00f-110">In this example, the two partners are the default server instances on three computer systems.</span></span> <span data-ttu-id="4c00f-111">Le due istanze server vengono eseguite in domini Windows non trusted, quindi è necessaria l'autenticazione basata sui certificati.</span><span class="sxs-lookup"><span data-stu-id="4c00f-111">The two server instances run in nontrusted Windows domains, so certificate-based authentication is required.</span></span>  
  
 <span data-ttu-id="4c00f-112">Il ruolo principale viene inizialmente assunto da HOST_A e il ruolo di server mirror da HOST_B.</span><span class="sxs-lookup"><span data-stu-id="4c00f-112">The initial principal role is taken by HOST_A, and the mirror role is taken by HOST_B.</span></span>  
  
 <span data-ttu-id="4c00f-113">La configurazione del mirroring del database eseguita con i certificati è costituita da quattro fasi generali. Le fasi 1, 2 e 4 vengono illustrate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="4c00f-113">Setting up database mirroring using certificates involves four general stages, of which three stages-1, 2, and 4-are demonstrated by this example.</span></span> <span data-ttu-id="4c00f-114">Le fasi sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c00f-114">These stages are as follows:</span></span>  
  
1.  [<span data-ttu-id="4c00f-115">Configurazione delle connessioni in uscita</span><span class="sxs-lookup"><span data-stu-id="4c00f-115">Configuring Outbound Connections</span></span>](#ConfiguringOutboundConnections)  
  
     <span data-ttu-id="4c00f-116">Nell'esempio riportato di seguito vengono illustrate le fasi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c00f-116">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="4c00f-117">Configurazione di Host_A per le connessioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="4c00f-117">Configuring Host_A for outbound connections.</span></span>  
  
    2.  <span data-ttu-id="4c00f-118">Configurazione di Host_B per le connessioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="4c00f-118">Configuring Host_B for outbound connections.</span></span>  
  
     <span data-ttu-id="4c00f-119">Per informazioni su questa fase di configurazione del mirroring del database, vedere [Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in uscita &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="4c00f-119">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
2.  [<span data-ttu-id="4c00f-120">Configurazione delle connessioni in ingresso</span><span class="sxs-lookup"><span data-stu-id="4c00f-120">Configuring Inbound Connections</span></span>](#ConfigureInboundConnections)  
  
     <span data-ttu-id="4c00f-121">Nell'esempio riportato di seguito vengono illustrate le fasi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c00f-121">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="4c00f-122">Configurazione di Host_A per le connessioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="4c00f-122">Configuring Host_A for inbound connections.</span></span>  
  
    2.  <span data-ttu-id="4c00f-123">Configurazione di Host_B per le connessioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="4c00f-123">Configuring Host_B for inbound connections.</span></span>  
  
     <span data-ttu-id="4c00f-124">Per informazioni su questa fase di configurazione del mirroring del database, vedere [Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="4c00f-124">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
3.  <span data-ttu-id="4c00f-125">Creazione del database mirror</span><span class="sxs-lookup"><span data-stu-id="4c00f-125">Creating the Mirror Database</span></span>  
  
     <span data-ttu-id="4c00f-126">Per informazioni su come creare un database mirror, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c00f-126">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
4.  [<span data-ttu-id="4c00f-127">Configurazione dei partner del mirroring</span><span class="sxs-lookup"><span data-stu-id="4c00f-127">Configuring the Mirroring Partners</span></span>](#ConfigureMirroringPartners)  
  
###  <a name="configuring-outbound-connections"></a><a name="ConfiguringOutboundConnections"></a> <span data-ttu-id="4c00f-128">Configurazione delle connessioni in uscita</span><span class="sxs-lookup"><span data-stu-id="4c00f-128">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="4c00f-129">**Per configurare Host_A per le connessioni in uscita**</span><span class="sxs-lookup"><span data-stu-id="4c00f-129">**To configure Host_A for outbound connections**</span></span>  
  
1.  <span data-ttu-id="4c00f-130">Nel database master creare la chiave master del database, se necessaria.</span><span class="sxs-lookup"><span data-stu-id="4c00f-130">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
2.  <span data-ttu-id="4c00f-131">Creare un certificato per questa istanza del server.</span><span class="sxs-lookup"><span data-stu-id="4c00f-131">Make a certificate for this server instance.</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate';  
    GO  
    ```  
  
3.  <span data-ttu-id="4c00f-132">Creare un endpoint del mirroring per l'istanza del server che utilizza il certificato.</span><span class="sxs-lookup"><span data-stu-id="4c00f-132">Create a mirroring endpoint for server instance using the certificate.</span></span>  
  
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
  
4.  <span data-ttu-id="4c00f-133">Eseguire il backup del certificato di HOST_A e copiarlo nell'altro sistema, HOST_B.</span><span class="sxs-lookup"><span data-stu-id="4c00f-133">Back up the HOST_A certificate, and copy it to other system, HOST_B.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
5.  <span data-ttu-id="4c00f-134">Utilizzando un metodo di copia sicuro, copiare C:\HOST_A_cert.cer in HOST_B.</span><span class="sxs-lookup"><span data-stu-id="4c00f-134">Using any secure copy method, copy C:\HOST_A_cert.cer to HOST_B.</span></span>  
  
 <span data-ttu-id="4c00f-135">**Per configurare Host_B per le connessioni in uscita**</span><span class="sxs-lookup"><span data-stu-id="4c00f-135">**To configure Host_B for outbound connections**</span></span>  
  
1.  <span data-ttu-id="4c00f-136">Nel database master creare la chiave master del database, se necessaria.</span><span class="sxs-lookup"><span data-stu-id="4c00f-136">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
    GO  
    ```  
  
2.  <span data-ttu-id="4c00f-137">Creare un certificato per l'istanza del server in HOST_B.</span><span class="sxs-lookup"><span data-stu-id="4c00f-137">Make a certificate on the HOST_B server instance.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert   
       WITH SUBJECT = 'HOST_B certificate for database mirroring';  
    GO  
    ```  
  
3.  <span data-ttu-id="4c00f-138">Creare un endpoint del mirroring per l'istanza del server in HOST_B.</span><span class="sxs-lookup"><span data-stu-id="4c00f-138">Create a mirroring endpoint for the server instance on HOST_B.</span></span>  
  
    ```  
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
    ```  
  
4.  <span data-ttu-id="4c00f-139">Eseguire il backup del certificato di HOST_B.</span><span class="sxs-lookup"><span data-stu-id="4c00f-139">Back up HOST_B certificate.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
    GO   
    ```  
  
5.  <span data-ttu-id="4c00f-140">Utilizzando un metodo di copia sicuro, copiare C:\HOST_B_cert.cer in HOST_A.</span><span class="sxs-lookup"><span data-stu-id="4c00f-140">Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.</span></span>  
  
 <span data-ttu-id="4c00f-141">Per altre informazioni, vedere [Impostare l'endpoint del mirroring del database per l'uso di certificati per le connessioni in uscita &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="4c00f-141">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
###  <a name="configuring-inbound-connections"></a><a name="ConfigureInboundConnections"></a> <span data-ttu-id="4c00f-142">Configurazione delle connessioni in ingresso</span><span class="sxs-lookup"><span data-stu-id="4c00f-142">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="4c00f-143">**Per configurare Host_A per le connessioni in ingresso**</span><span class="sxs-lookup"><span data-stu-id="4c00f-143">**To configure Host_A for inbound connections**</span></span>  
  
1.  <span data-ttu-id="4c00f-144">In HOST_A creare un account di accesso per HOST_B.</span><span class="sxs-lookup"><span data-stu-id="4c00f-144">Create a login on HOST_A for HOST_B.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_B_login WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
2.  <span data-ttu-id="4c00f-145">--Creare un utente per tale account di accesso.</span><span class="sxs-lookup"><span data-stu-id="4c00f-145">--Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="4c00f-146">--Associare il certificato all'utente.</span><span class="sxs-lookup"><span data-stu-id="4c00f-146">--Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="4c00f-147">Concedere l'autorizzazione CONNECT per l'account di accesso per l'endpoint del mirroring remoto.</span><span class="sxs-lookup"><span data-stu-id="4c00f-147">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
 <span data-ttu-id="4c00f-148">**Per configurare Host_B per le connessioni in ingresso**</span><span class="sxs-lookup"><span data-stu-id="4c00f-148">**To configure Host_B for inbound connections**</span></span>  
  
1.  <span data-ttu-id="4c00f-149">In HOST_B creare un account di accesso per HOST_A.</span><span class="sxs-lookup"><span data-stu-id="4c00f-149">Create a login on HOST_B for HOST_A.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_A_login WITH PASSWORD = '=Sample#2_Strong_Password2';  
    GO  
    ```  
  
2.  <span data-ttu-id="4c00f-150">Creare un utente per tale account di accesso.</span><span class="sxs-lookup"><span data-stu-id="4c00f-150">Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="4c00f-151">Associare il certificato all'utente.</span><span class="sxs-lookup"><span data-stu-id="4c00f-151">Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_A_cert  
       AUTHORIZATION HOST_A_user  
       FROM FILE = 'C:\HOST_A_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="4c00f-152">Concedere l'autorizzazione CONNECT per l'account di accesso per l'endpoint del mirroring remoto.</span><span class="sxs-lookup"><span data-stu-id="4c00f-152">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_A_login];  
    GO  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4c00f-153">Se si prevede di utilizzare la modalità a sicurezza elevata con failover automatico, è necessario ripetere gli stessi passaggi di impostazione per configurare il server di controllo del mirroring per connessioni in uscita e in ingresso.</span><span class="sxs-lookup"><span data-stu-id="4c00f-153">If you intend to run in high-safety mode with automatic failover, you must repeat the same setup steps to configure the witness for outbound and inbound connections.</span></span> <span data-ttu-id="4c00f-154">Per configurare le connessioni in ingresso per un server di controllo del mirroring è necessario impostare account di accesso e utenti per il server di controllo del mirroring in entrambi i partner e per entrambi i partner nel server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="4c00f-154">Setting up the inbound connections when a witness is involved requires that you set up logins and users for the witness on both of the partners and for both partners on the witness.</span></span>  
  
 <span data-ttu-id="4c00f-155">Per altre informazioni, vedere [Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="4c00f-155">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
### <a name="creating-the-mirror-database"></a><span data-ttu-id="4c00f-156">Creazione del database mirror</span><span class="sxs-lookup"><span data-stu-id="4c00f-156">Creating the Mirror Database</span></span>  
 <span data-ttu-id="4c00f-157">Per informazioni su come creare un database mirror, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c00f-157">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
###  <a name="configuring-the-mirroring-partners"></a><a name="ConfigureMirroringPartners"></a> <span data-ttu-id="4c00f-158">Configurazione dei partner del mirroring</span><span class="sxs-lookup"><span data-stu-id="4c00f-158">Configuring the Mirroring Partners</span></span>  
  
1.  <span data-ttu-id="4c00f-159">Nell'istanza del server mirror in HOST_B, impostare l'istanza del server in HOST_A come partner (rendendola l'istanza iniziale del server principale).</span><span class="sxs-lookup"><span data-stu-id="4c00f-159">On the mirror server instance on HOST_B, set the server instance on HOST_A as the partner (making it the initial principal server instance).</span></span> <span data-ttu-id="4c00f-160">Specificare un indirizzo di rete valido per `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="4c00f-160">Substitute a valid network address for `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span></span> <span data-ttu-id="4c00f-161">Per altre informazioni, vedere [Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="4c00f-161">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
    ```  
    --At HOST_B, set server instance on HOST_A as partner (principal server):  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_A.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
2.  <span data-ttu-id="4c00f-162">Nell'istanza del server principale in HOST_A, impostare l'istanza del server in HOST_B come partner (rendendola l'istanza iniziale del server mirror).</span><span class="sxs-lookup"><span data-stu-id="4c00f-162">On the principal server instance on HOST_A, set the server instance on HOST_B as the partner (making it the initial mirror server instance).</span></span> <span data-ttu-id="4c00f-163">Specificare un indirizzo di rete valido per `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="4c00f-163">Substitute a valid network address for `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span></span>  
  
    ```  
    --At HOST_A, set server instance on HOST_B as partner (mirror server).  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
3.  <span data-ttu-id="4c00f-164">In questo esempio si presuppone che la sessione verrà eseguita nella modalità a prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="4c00f-164">This example assumes that the session will be running in high-performance mode.</span></span> <span data-ttu-id="4c00f-165">Per configurare la sessione per la modalità a prestazioni elevate, nell'istanza del server principale (in HOST_A), impostare la protezione delle transazioni su OFF.</span><span class="sxs-lookup"><span data-stu-id="4c00f-165">To configure this session for high-performance mode, on the principal server instance (on HOST_A), set transaction safety to OFF.</span></span>  
  
    ```  
    --Change to high-performance mode by turning off transacton safety.  
    ALTER DATABASE AdventureWorks   
        SET PARTNER SAFETY OFF  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c00f-166">Se si prevede di eseguire in modalità a protezione elevata con failover automatico, lasciare la sicurezza delle transazioni impostata su Full (impostazione predefinita) e aggiungere il server di controllo del mirroring non appena possibile dopo l'esecuzione della seconda istruzione set partner **' *`partner_server`* '** .</span><span class="sxs-lookup"><span data-stu-id="4c00f-166">If you intend to run in high-safety mode with automatic failover, leave transaction safety set to FULL (the default setting) and add the witness as soon as possible after executing the second SET PARTNER **'*`partner_server`*'** statement.</span></span> <span data-ttu-id="4c00f-167">Si osservi che è necessario configurare prima il server di controllo del mirroring per le connessioni in uscita e in ingresso.</span><span class="sxs-lookup"><span data-stu-id="4c00f-167">Note that the witness must first be configured for outbound and inbound connections.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4c00f-168">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4c00f-168">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4c00f-169">Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c00f-169">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="4c00f-170">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4c00f-170">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="4c00f-171">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in uscita &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4c00f-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="4c00f-172">Gestione di account di accesso e di processi dopo un cambio di ruolo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c00f-172">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
-   <span data-ttu-id="4c00f-173">[Gestione dei metadati quando si rende disponibile un database in un'altra istanza del server &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4c00f-173">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span></span>  
  
-   [<span data-ttu-id="4c00f-174">Risolvere i problemi relativi alla configurazione del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c00f-174">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c00f-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c00f-175">See Also</span></span>  
 <span data-ttu-id="4c00f-176">[Sicurezza del trasporto per il mirroring del database e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="4c00f-176">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="4c00f-177">[Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="4c00f-177">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="4c00f-178">[Endpoint del mirroring del database &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4c00f-178">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="4c00f-179">[Usare certificati per un endpoint del mirroring del database &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="4c00f-179">[Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span></span>  
 <span data-ttu-id="4c00f-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c00f-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="4c00f-181">Centro sicurezza per il motore di Database di SQL Server e il Database SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="4c00f-181">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
