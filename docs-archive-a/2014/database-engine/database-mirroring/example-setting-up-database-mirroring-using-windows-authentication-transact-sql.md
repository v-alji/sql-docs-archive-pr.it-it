---
title: "Esempio: impostazione del mirroring del database tramite l'autenticazione di Windows (Transact-SQL) | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- Windows authentication [SQL Server]
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: 35800769-aede-4aac-b077-0e0e487e302f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95df855e8e41c5937aae02884c71792537eb2bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624903"
---
# <a name="example-setting-up-database-mirroring-using-windows-authentication-transact-sql"></a><span data-ttu-id="1a791-102">Esempio: Impostazione del mirroring del database tramite l'autenticazione di Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1a791-102">Example: Setting Up Database Mirroring Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="1a791-103">In questo esempio vengono illustrate tutte le fasi necessarie per creare una sessione di mirroring del database con un server di controllo del mirroring con l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1a791-103">This example shows all the stages required to create a database mirroring session with a witness using Windows Authentication.</span></span> <span data-ttu-id="1a791-104">Negli esempi di questo argomento viene utilizzato [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a791-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1a791-105">Si osservi che per impostare il mirroring del database è possibile utilizzare, in alternativa alle procedure di [!INCLUDE[tsql](../../includes/tsql-md.md)], la Configurazione guidata sicurezza mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="1a791-105">Note that as an alternative to using [!INCLUDE[tsql](../../includes/tsql-md.md)] steps, you can use the Configure Database Mirroring Security Wizard for database mirroring setup.</span></span> <span data-ttu-id="1a791-106">Per altre informazioni, vedere [Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1a791-106">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="1a791-107">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="1a791-107">Prerequisite</span></span>  
 <span data-ttu-id="1a791-108">Nell'esempio viene utilizzato il database di esempio **AdventureWorks** , in cui, per impostazione predefinita, viene utilizzato il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="1a791-108">The example uses the **AdventureWorks** sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="1a791-109">Per utilizzare il mirroring del database con questo database, è necessario modificarlo in modo che venga utilizzato il modello di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="1a791-109">To use database mirroring with this database, you must alter it to use the full recovery model.</span></span> <span data-ttu-id="1a791-110">Per eseguire questa operazione in [!INCLUDE[tsql](../../includes/tsql-md.md)], utilizzare l'istruzione ALTER DATABASE, come segue:</span><span class="sxs-lookup"><span data-stu-id="1a791-110">To do this in [!INCLUDE[tsql](../../includes/tsql-md.md)], use the ALTER DATABASE statement, as follows:</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE AdventureWorks   
SET RECOVERY FULL;  
GO  
```  
  
 <span data-ttu-id="1a791-111">Per informazioni sulla modifica del modello di recupero in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vedere [Visualizzazione o modifica del modello di recupero di un database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1a791-111">For information on changing the recovery model in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="1a791-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1a791-112">Permissions</span></span>  
 <span data-ttu-id="1a791-113">È richiesta l'autorizzazione ALTER per il database e l'autorizzazione CREATE ENDPOINT o l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="1a791-113">Requires ALTER permission on the database and CREATE ENDPOINT permission, or membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a791-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a791-114">Example</span></span>  
 <span data-ttu-id="1a791-115">In questo esempio i due partner e il server di controllo del mirroring sono le istanze predefinite del server in tre sistemi.</span><span class="sxs-lookup"><span data-stu-id="1a791-115">In this example, the two partners and the witness are the default server instances on three computer systems.</span></span> <span data-ttu-id="1a791-116">Le tre istanze del server sono eseguite nello stesso dominio Windows, ma per l'istanza del server di controllo del mirroring l'account utente (utilizzato come account del servizio di avvio) è diverso.</span><span class="sxs-lookup"><span data-stu-id="1a791-116">The three server instances run the same Windows domain, but the user account (used as the startup service account) is different for the example's witness server instance.</span></span>  
  
 <span data-ttu-id="1a791-117">Nella tabella seguente sono riepilogati i valori utilizzati nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="1a791-117">The following table summarizes the values used in this example.</span></span>  
  
|<span data-ttu-id="1a791-118">Ruolo di mirroring iniziale</span><span class="sxs-lookup"><span data-stu-id="1a791-118">Initial mirroring role</span></span>|<span data-ttu-id="1a791-119">Sistema host</span><span class="sxs-lookup"><span data-stu-id="1a791-119">Host system</span></span>|<span data-ttu-id="1a791-120">Account utente di dominio</span><span class="sxs-lookup"><span data-stu-id="1a791-120">Domain user account</span></span>|  
|----------------------------|-----------------|-------------------------|  
|<span data-ttu-id="1a791-121">Server principale</span><span class="sxs-lookup"><span data-stu-id="1a791-121">Principal</span></span>|<span data-ttu-id="1a791-122">PARTNERHOST1</span><span class="sxs-lookup"><span data-stu-id="1a791-122">PARTNERHOST1</span></span>|<span data-ttu-id="1a791-123">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="1a791-123">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="1a791-124">Mirror</span><span class="sxs-lookup"><span data-stu-id="1a791-124">Mirror</span></span>|<span data-ttu-id="1a791-125">PARTNERHOST5</span><span class="sxs-lookup"><span data-stu-id="1a791-125">PARTNERHOST5</span></span>|<span data-ttu-id="1a791-126">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="1a791-126">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="1a791-127">Controllo</span><span class="sxs-lookup"><span data-stu-id="1a791-127">Witness</span></span>|<span data-ttu-id="1a791-128">WITNESSHOST4</span><span class="sxs-lookup"><span data-stu-id="1a791-128">WITNESSHOST4</span></span>|<span data-ttu-id="1a791-129">*\<Somedomain>\\<witnessuser\>*</span><span class="sxs-lookup"><span data-stu-id="1a791-129">*\<Somedomain>\\<witnessuser\>*</span></span>|  
  
1.  <span data-ttu-id="1a791-130">Creare un endpoint nell'istanza del server principale, ovvero l'istanza predefinita in PARTNERHOST1.</span><span class="sxs-lookup"><span data-stu-id="1a791-130">Create an endpoint on the principal server instance (default instance on PARTNERHOST1).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=PARTNER)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    -- Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
2.  <span data-ttu-id="1a791-131">Creare un endpoint nell'istanza del server mirror, ovvero l'istanza predefinita in PARTNERHOST5.</span><span class="sxs-lookup"><span data-stu-id="1a791-131">Create an endpoint on the mirror server instance (default instance on PARTNERHOST5).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="1a791-132">Creare un endpoint nell'istanza del server di controllo del mirroring, ovvero l'istanza predefinita in WITNESSHOST4.</span><span class="sxs-lookup"><span data-stu-id="1a791-132">Create an endpoint on the witness server instance (default instance on WITNESSHOST4).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    --Create a login for the partner server instances,  
    --which are both running as Mydomain\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [Mydomain\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
4.  <span data-ttu-id="1a791-133">Creare il database mirror.</span><span class="sxs-lookup"><span data-stu-id="1a791-133">Create the mirror database.</span></span> <span data-ttu-id="1a791-134">Per altre informazioni, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1a791-134">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="1a791-135">Nell'istanza del server mirror in PARTNERHOST5 impostare l'istanza del server in PARTNERHOST1 come partner, rendendola l'istanza del server principale iniziale.</span><span class="sxs-lookup"><span data-stu-id="1a791-135">On the mirror server instance on PARTNERHOST5, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1.COM:7022'  
    GO  
    ```  
  
6.  <span data-ttu-id="1a791-136">Nell'istanza del server principale in PARTNERHOST1 impostare l'istanza del server in PARTNERHOST5 come partner, rendendola l'istanza del server mirror iniziale.</span><span class="sxs-lookup"><span data-stu-id="1a791-136">On the principal server instance on PARTNERHOST1, set the server instance on PARTNERHOST5 as the partner (making it the initial mirror server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5.COM:7022'  
    GO  
    ```  
  
7.  <span data-ttu-id="1a791-137">Nel server principale impostare il server di controllo del mirroring, che si trova in WITNESSHOST4.</span><span class="sxs-lookup"><span data-stu-id="1a791-137">On the principal server, set the witness (which is on WITNESSHOST4).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4.COM:7022'  
    GO  
    ```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1a791-138">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="1a791-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1a791-139">Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1a791-139">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="1a791-140">Avvio della Configurazione guidata sicurezza mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1a791-140">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
-   [<span data-ttu-id="1a791-141">Impostazione di un database mirror per l'utilizzo della proprietà Trustworthy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a791-141">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
-   [<span data-ttu-id="1a791-142">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in uscita &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a791-142">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="1a791-143">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a791-143">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="1a791-144">Esempio: Configurazione del mirroring del database tramite certificati &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a791-144">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a791-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a791-145">See Also</span></span>  
 <span data-ttu-id="1a791-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a791-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="1a791-147">[Endpoint del mirroring del database &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1a791-147">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="1a791-148">[Sicurezza del trasporto per il mirroring del database e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="1a791-148">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="1a791-149">[Gestire i metadati quando si rende disponibile un database in un'altra istanza del server &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span><span class="sxs-lookup"><span data-stu-id="1a791-149">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span></span>  
 [<span data-ttu-id="1a791-150">Centro sicurezza per il motore di Database di SQL Server e il Database SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="1a791-150">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
