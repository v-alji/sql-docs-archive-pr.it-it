---
title: Aggiungere un server di controllo del mirroring del database tramite l'autenticazione di Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- Windows authentication [SQL Server]
- database mirroring [SQL Server], witness
ms.assetid: bf5e87df-91a4-49f9-ae88-2a6dcf644510
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 88684c3a1ca12ea579859759ed804ca281647fa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626294"
---
# <a name="add-a-database-mirroring-witness-using-windows-authentication-transact-sql"></a><span data-ttu-id="82d34-102">Aggiungere un server di controllo del mirroring del database tramite l'autenticazione di Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="82d34-102">Add a Database Mirroring Witness Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="82d34-103">Per installare un server di controllo per un database, il proprietario del database assegna un'istanza di Motore di database al ruolo di server di controllo.</span><span class="sxs-lookup"><span data-stu-id="82d34-103">To set up a witness for a database, the database owner assigns a Database Engine instance to the role of witness server.</span></span> <span data-ttu-id="82d34-104">L'istanza del server di controllo può essere eseguita sullo stesso computer dell'istanza del server principale o mirror, ma questo riduce in modo significativo l'affidabilità del failover automatico.</span><span class="sxs-lookup"><span data-stu-id="82d34-104">The witness server instance can run on the same computer as the principal or mirror server instance, but this substantially reduces the robustness of automatic failover.</span></span>  
  
 <span data-ttu-id="82d34-105">È fortemente consigliabile che il server di controllo risieda su un computer separato.</span><span class="sxs-lookup"><span data-stu-id="82d34-105">We strongly recommend that the witness reside on a separate computer.</span></span> <span data-ttu-id="82d34-106">Un determinato server può prendere parte a più sessioni di mirroring del database simultanee con lo stesso o diversi partner.</span><span class="sxs-lookup"><span data-stu-id="82d34-106">A given server can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="82d34-107">Un determinato server può essere partner in alcune sessioni e server di controllo in altre.</span><span class="sxs-lookup"><span data-stu-id="82d34-107">A given server can be a partner in some sessions and a witness in other sessions.</span></span>  
  
 <span data-ttu-id="82d34-108">Il server di controllo del mirroring è destinato unicamente alla modalità a sicurezza elevata con failover automatico.</span><span class="sxs-lookup"><span data-stu-id="82d34-108">The witness is intended exclusively for high-safety mode with automatic failover.</span></span> <span data-ttu-id="82d34-109">Prima di impostare un server di controllo del mirroring, è consigliabile verificare che la proprietà SAFETY sia impostata su FULL.</span><span class="sxs-lookup"><span data-stu-id="82d34-109">Before you set a witness, we strongly recommend that you ensure that the SAFETY property is currently set to FULL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="82d34-110">È consigliabile configurare il mirroring del database durante le fasce orarie di minore attività, in quanto la configurazione può influire sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="82d34-110">We recommend that you configure database mirroring during off-peak hours because configuration can impact performance.</span></span>  
  
### <a name="to-establish-a-witness"></a><span data-ttu-id="82d34-111">Per creare un server di controllo</span><span class="sxs-lookup"><span data-stu-id="82d34-111">To establish a witness</span></span>  
  
1.  <span data-ttu-id="82d34-112">Sull'istanza del server di controllo, assicurarsi che sia presente un endpoint per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="82d34-112">On the witness server instance, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="82d34-113">Indipendentemente dal numero di sessioni di mirroring da supportare, è necessario che l'istanza del server disponga di un unico endpoint di mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="82d34-113">Regardless of the number of mirroring session to be supported, the server instance must have only one database mirroring endpoint.</span></span> <span data-ttu-id="82d34-114">Se si intende utilizzare questa istanza del server esclusivamente come server di controllo del mirroring nelle sessioni di mirroring del database, assegnare il ruolo di server di controllo del mirroring all'endpoint (ROLE **=** Witness).</span><span class="sxs-lookup"><span data-stu-id="82d34-114">If you intend to use this server instance exclusively as a witness in database mirroring sessions, assign the role of witness to the endpoint (ROLE **=** WITNESS).</span></span> <span data-ttu-id="82d34-115">Se si desidera utilizzare l'istanza del server come partner in una o più sessioni di mirroring del database, assegnare il ruolo di server dell'endpoint come ALL.</span><span class="sxs-lookup"><span data-stu-id="82d34-115">If you intend to use this server instance as a partner in one or more other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="82d34-116">Per eseguire un'istruzione SET WITNESS, è necessario che la sessione di mirroring del database sia già iniziata (tra i partner) e che il valore STATE dell'endpoint del server di controllo sia impostato su STARTED.</span><span class="sxs-lookup"><span data-stu-id="82d34-116">To execute a SET WITNESS statement, the database mirroring session must already be started (between the partners), and the STATE of the endpoint of the witness must be set to STARTED.</span></span>  
  
     <span data-ttu-id="82d34-117">Per informazioni sulle situazioni in cui l'istanza del server di controllo del mirroring dispone di un endpoint del mirroring del database e sul suo ruolo e stato, eseguire l'istruzione Transact-SQL seguente sull'istanza:</span><span class="sxs-lookup"><span data-stu-id="82d34-117">To learn whether the witness server instance has its database mirroring endpoint and to learn its role and state, on that instance, use the following Transact-SQL statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="82d34-118">Se un endpoint di mirroring del database è presente e già in uso, è consigliabile utilizzarlo per ogni sessione sull'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="82d34-118">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="82d34-119">L'eliminazione di un endpoint in uso determina la chiusura di tutte le connessioni delle sessioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="82d34-119">Dropping an in-use endpoint disrupts the connections of the existing sessions.</span></span> <span data-ttu-id="82d34-120">Se un server di controllo del mirroring è stato impostato per una sessione, l'eliminazione dell'endpoint del mirroring del database può determinare la perdita del quorum da parte del server principale della sessione. Se questo si verifica, il database viene portato offline e i suoi utenti vengono disconnessi.</span><span class="sxs-lookup"><span data-stu-id="82d34-120">If a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="82d34-121">Per altre informazioni, vedere [Quorum: Impatto di un server di controllo del mirroring sulla disponibilità del database &#40;mirroring del database&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="82d34-121">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="82d34-122">Se il server di controllo manca di un endpoint, vedere [Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="82d34-122">If the witness lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="82d34-123">Se le istanze dei partner sono in esecuzione con account utente di dominio diversi, creare un account di accesso per i diversi account sul database master di ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="82d34-123">If the partner instances are running under different domain user accounts, create a login for the different accounts in the master database of each instance.</span></span> <span data-ttu-id="82d34-124">Per altre informazioni, vedere [Concessione dell'accesso alla rete a un endpoint per il mirroring del database utilizzando l'autenticazione di Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="82d34-124">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="82d34-125">Connettersi al server principale ed eseguire la seguente istruzione:</span><span class="sxs-lookup"><span data-stu-id="82d34-125">Connect to the principal server and issue the following statement:</span></span>  
  
     <span data-ttu-id="82d34-126">ALTER DATABASE *<database_name>* set di controllo **=** _<server_network_address>_</span><span class="sxs-lookup"><span data-stu-id="82d34-126">ALTER DATABASE *<database_name>* SET WITNESS **=** _<server_network_address>_</span></span>  
  
     <span data-ttu-id="82d34-127">dove *<database_name>* è il nome del database di cui eseguire il mirroring (tale nome è lo stesso per entrambi i partner) e *<server_network_address>* è l'indirizzo di rete dell'istanza del server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="82d34-127">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the witness server instance.</span></span>  
  
     <span data-ttu-id="82d34-128">La sintassi per un indirizzo di rete del server presenta la seguente struttura:</span><span class="sxs-lookup"><span data-stu-id="82d34-128">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="82d34-129">TCP **://** \<_system-address> _**:**\<*port>\*</span><span class="sxs-lookup"><span data-stu-id="82d34-129">TCP **://**\<_system-address>_**:**\<*port>\*</span></span>  
  
     <span data-ttu-id="82d34-130">dove \<*system-address>\* è una stringa che identifica in maniera univoca il computer di destinazione e \<*port>\* è il numero di porta usato dall'endpoint del mirroring dell'istanza del server partner.</span><span class="sxs-lookup"><span data-stu-id="82d34-130">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="82d34-131">Per altre informazioni, vedere [Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="82d34-131">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="82d34-132">Ad esempio, sull'istanza del server principale l'istruzione ALTER DATABASE seguente imposta il server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="82d34-132">For example, on the principal server instance, the following ALTER DATABASE statement sets the witness.</span></span> <span data-ttu-id="82d34-133">Il nome del database è **AdventureWorks**, l'indirizzo del sistema è DBSERVER3, ovvero il nome del server di controllo del mirroring, e la porta usata dall'endpoint del mirroring del database del server di controllo del mirroring è `7022`:</span><span class="sxs-lookup"><span data-stu-id="82d34-133">The database name is **AdventureWorks**, the system address is DBSERVER3-the name of the witness system, and the port used by the database mirroring endpoint of the witness is `7022`:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
      SET WITNESS = 'TCP://DBSERVER3:7022'  
    ```  
  
## <a name="example"></a><span data-ttu-id="82d34-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="82d34-134">Example</span></span>  
 <span data-ttu-id="82d34-135">Nell'esempio seguente viene creato un server di controllo del mirroring dei dati.</span><span class="sxs-lookup"><span data-stu-id="82d34-135">The following example establishes a data mirroring witness.</span></span> <span data-ttu-id="82d34-136">Sull'istanza del server di controllo (istanza predefinita in `WITNESSHOST4`):</span><span class="sxs-lookup"><span data-stu-id="82d34-136">On the witness server instance (default instance on `WITNESSHOST4`):</span></span>  
  
1.  <span data-ttu-id="82d34-137">Creare un endpoint per questa istanza del server solo per il ruolo WITNESS utilizzando la porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="82d34-137">Create an endpoint for this server instance for the WITNESS role only using port `7022`.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    ```  
  
2.  <span data-ttu-id="82d34-138">Creare un account di accesso per l'account utente di dominio delle istanze dei partner, se diverso. Ad esempio, supporre che il server di controllo del mirroring sia in esecuzione come `SOMEDOMAIN\witnessuser`, ma che i partner siano in esecuzione come `MYDOMAIN\dbousername`.</span><span class="sxs-lookup"><span data-stu-id="82d34-138">Create a login for domain user account of partner instances, if different; for example, assume that the witness is running as `SOMEDOMAIN\witnessuser`, but the partners are running as `MYDOMAIN\dbousername`.</span></span> <span data-ttu-id="82d34-139">Creare un account di accesso per i partner, come segue:</span><span class="sxs-lookup"><span data-stu-id="82d34-139">Create a login for the partners, as follows:</span></span>  
  
    ```  
    --Create a login for the partner server instances,  
    --which are both running as MYDOMAIN\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [MYDOMAIN\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [MYDOMAIN\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="82d34-140">Su ciascuna delle istanze del server partner creare un account di accesso per l'istanza del server di controllo:</span><span class="sxs-lookup"><span data-stu-id="82d34-140">On each of the partner server instances, create a login for the witness server instance:</span></span>  
  
    ```  
    --Create a login for the witness server instance,  
    --which is running as SOMEDOMAIN\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [SOMEDOMAIN\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [SOMEDOMAIN\witnessuser];  
    GO  
    ```  
  
4.  <span data-ttu-id="82d34-141">Sul server principale impostare il server di controllo del mirroring, che si trova in `WITNESSHOST4`:</span><span class="sxs-lookup"><span data-stu-id="82d34-141">On the principal server, set the witness (which is on `WITNESSHOST4`):</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4:7022'  
    GO  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="82d34-142">L'indirizzo di rete del server indica l'istanza del server di destinazione attraverso il numero di porta, che esegue il mapping dell'endpoint di mirroring dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="82d34-142">The server network address indicates the target server instance by the port number, which maps to the mirroring endpoint of the instance.</span></span>  
  
 <span data-ttu-id="82d34-143">Per un esempio completo che illustri le impostazioni relative alla sicurezza e ai partner, nonché l'aggiunta di un server di controllo del mirroring, vedere [Impostazione del mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="82d34-143">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82d34-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82d34-144">See Also</span></span>  
 <span data-ttu-id="82d34-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="82d34-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="82d34-146">[Concessione dell'accesso alla rete a un endpoint per il mirroring del database utilizzando l'autenticazione di Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="82d34-146">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="82d34-147">[Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="82d34-147">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="82d34-148">[Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="82d34-148">[Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span></span>  
 <span data-ttu-id="82d34-149">[Rimuovere il server di controllo del mirroring da una sessione di mirroring del database &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="82d34-149">[Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="82d34-150">Server di controllo del mirroring del database</span><span class="sxs-lookup"><span data-stu-id="82d34-150">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
