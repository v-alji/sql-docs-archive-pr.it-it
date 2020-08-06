---
title: Stabilire una sessione di mirroring del database tramite l'autenticazione di Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 143c68a5-589f-4e7f-be59-02707e1a430a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3088333fbfd4babd209df07f8880c838ce626d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624934"
---
# <a name="establish-a-database-mirroring-session-using-windows-authentication-transact-sql"></a><span data-ttu-id="98ea4-102">Stabilire una sessione di mirroring del database tramite autenticazione di Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="98ea4-102">Establish a Database Mirroring Session Using Windows Authentication (Transact-SQL)</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="98ea4-103">In alternativa, usare [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ea4-103">Use [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] instead.</span></span>  
  
 <span data-ttu-id="98ea4-104">Dopo la preparazione del database mirror, illustrata in [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md), è possibile stabilire una sessione di mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="98ea4-104">After the mirror database is prepared (see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)), you can establish a database mirroring session.</span></span> <span data-ttu-id="98ea4-105">È necessario che le istanze del server principale, del server mirror e del server di controllo del mirroring siano istanze di server distinte, situate in sistemi host distinti.</span><span class="sxs-lookup"><span data-stu-id="98ea4-105">The principal, mirror, and witness server instances must be separate server instances, which should be on separate host systems.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="98ea4-106">È consigliabile configurare il mirroring del database durante le fasce orarie di minore attività, dato che tale configurazione può influire sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="98ea4-106">We recommend that you configure database mirroring during off-peak hours because configuring mirroring can impact performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98ea4-107">Una determinata istanza del server può prendere parte a più sessioni di mirroring del database simultanee con lo stesso partner o con partner diversi.</span><span class="sxs-lookup"><span data-stu-id="98ea4-107">A given server instance can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="98ea4-108">Una determinata istanza del server può essere partner in alcune sessioni e server di controllo del mirroring in altre.</span><span class="sxs-lookup"><span data-stu-id="98ea4-108">A server instance can be a partner in some sessions and a witness in other sessions.</span></span> <span data-ttu-id="98ea4-109">L'istanza del server mirror deve eseguire la stessa edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come istanza del server principale.</span><span class="sxs-lookup"><span data-stu-id="98ea4-109">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the principal server instance.</span></span> <span data-ttu-id="98ea4-110">Il mirroring del database non è disponibile in ogni edizione di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ea4-110">Database mirroring is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="98ea4-111">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="98ea4-112">È inoltre consigliabile che vengano eseguite in sistemi simili in grado di gestire carichi di lavoro identici.</span><span class="sxs-lookup"><span data-stu-id="98ea4-112">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
### <a name="to-establish-a-database-mirroring-session"></a><span data-ttu-id="98ea4-113">Per stabilire una sessione di mirroring del database</span><span class="sxs-lookup"><span data-stu-id="98ea4-113">To establish a database mirroring session</span></span>  
  
1.  <span data-ttu-id="98ea4-114">Creare il database mirror.</span><span class="sxs-lookup"><span data-stu-id="98ea4-114">Create the mirror database.</span></span> <span data-ttu-id="98ea4-115">Per altre informazioni, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-115">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="98ea4-116">Impostare la sicurezza in ogni istanza del server.</span><span class="sxs-lookup"><span data-stu-id="98ea4-116">Set up security on each server instance.</span></span>  
  
     <span data-ttu-id="98ea4-117">Per ogni istanza del server in una sessione di mirroring del database è necessario un endpoint di mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="98ea4-117">Each server instance in a database mirroring session requires a database mirroring endpoint.</span></span> <span data-ttu-id="98ea4-118">Se l'endpoint non esiste, è necessario crearlo.</span><span class="sxs-lookup"><span data-stu-id="98ea4-118">If the endpoint does not exist, you must create it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="98ea4-119">La forma di autenticazione utilizzata per il mirroring del database da un'istanza del server corrisponde a una proprietà dell'endpoint del mirroring del database dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="98ea4-119">The form of authentication used for database mirroring by a server instance is a property of its database mirroring endpoint.</span></span> <span data-ttu-id="98ea4-120">Per il mirroring del database sono disponibili due tipi di sicurezza del trasporto: autenticazione di Windows o autenticazione basata su certificati.</span><span class="sxs-lookup"><span data-stu-id="98ea4-120">Two types of transport security are available for database mirroring: Windows Authentication or certificate-based authentication.</span></span> <span data-ttu-id="98ea4-121">Per ulteriori informazioni, vedere [sicurezza del trasporto per il mirroring del database e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-121">For more information, see [Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span></span>  
  
     <span data-ttu-id="98ea4-122">Assicurarsi che in ogni server partner server sia disponibile un endpoint per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="98ea4-122">On each partner server, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="98ea4-123">Indipendentemente dal numero di sessioni di mirroring da supportare, nell'istanza del server è consentito un solo endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="98ea4-123">Regardless of the number of mirroring sessions to be supported, the server instance can have only one database mirroring endpoint.</span></span> <span data-ttu-id="98ea4-124">Se si desidera usare questa istanza del server esclusivamente per i partner di sessioni di mirroring del database, è possibile assegnare il ruolo di partner all'endpoint (ROLE **=** PARTNER).</span><span class="sxs-lookup"><span data-stu-id="98ea4-124">If you intend to use this server instance exclusively for partners in database mirroring sessions, you can assign the role of partner to the endpoint (ROLE**=** PARTNER).</span></span> <span data-ttu-id="98ea4-125">Se si desidera utilizzare questo server anche per il server di controllo del mirroring in altre sessioni di mirroring del database, assegnare il ruolo dell'endpoint come ALL.</span><span class="sxs-lookup"><span data-stu-id="98ea4-125">If you intend also to use this server for the witness in other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="98ea4-126">Per eseguire un'istruzione SET PARTNER, l'opzione STATE degli endpoint di entrambi i partner deve essere impostata su STARTED.</span><span class="sxs-lookup"><span data-stu-id="98ea4-126">To execute a SET PARTNER statement, the STATE of the endpoints of both partners must be set to STARTED.</span></span>  
  
     <span data-ttu-id="98ea4-127">Per verificare se un'istanza del server dispone di un endpoint del mirroring del database e per informazioni sul ruolo e sullo stato relativi, in quell'istanza, utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="98ea4-127">To learn whether a server instance has a database mirroring endpoint and to learn its role and state, on that instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="98ea4-128">Non riconfigurare un endpoint del mirroring del database in uso.</span><span class="sxs-lookup"><span data-stu-id="98ea4-128">Do not reconfigure an in-use database mirroring endpoint.</span></span> <span data-ttu-id="98ea4-129">Se un endpoint di mirroring del database è presente e già in uso, è consigliabile utilizzarlo per ogni sessione sull'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="98ea4-129">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="98ea4-130">L'eliminazione di un endpoint in uso può determinare il riavvio dell'endpoint, interrompendo le connessioni delle sessioni esistenti, cosa che ad altre istanze del server potrebbe apparire come un errore.</span><span class="sxs-lookup"><span data-stu-id="98ea4-130">Dropping an in-use endpoint can cause the endpoint to restart, disrupting the connections of the existing sessions, which can appear to be an error to the other server instances.</span></span> <span data-ttu-id="98ea4-131">Questa indicazione è particolarmente importante in modalità a sicurezza elevata con failover automatico, nella quale la riconfigurazione dell'endpoint in un partner potrebbe causare il verificarsi di un failover.</span><span class="sxs-lookup"><span data-stu-id="98ea4-131">This is particularly important in high-safety mode with automatic failover, in which reconfiguring the endpoint on a partner could cause a failover to occur.</span></span> <span data-ttu-id="98ea4-132">Se un server di controllo del mirroring è stato impostato per una sessione, l'eliminazione dell'endpoint del mirroring del database può inoltre determinare la perdita del quorum da parte del server principale della sessione. Se si verifica questa situazione, il database viene portato offline e i suoi utenti vengono disconnessi.</span><span class="sxs-lookup"><span data-stu-id="98ea4-132">Also, if a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="98ea4-133">Per altre informazioni, vedere [Quorum: Impatto di un server di controllo del mirroring sulla disponibilità del database &#40;mirroring del database&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-133">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="98ea4-134">Se un partner manca di un endpoint, vedere [Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-134">If either partner lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
3.  <span data-ttu-id="98ea4-135">Se le istanze del server sono in esecuzione in account utente di dominio diversi, per ciascuna istanza è necessario un account di accesso nel database **master** delle altre.</span><span class="sxs-lookup"><span data-stu-id="98ea4-135">If server instances are running under different domain user accounts, each requires a login in the **master** database of the others.</span></span> <span data-ttu-id="98ea4-136">Se l'account di accesso non esiste, è necessario crearlo.</span><span class="sxs-lookup"><span data-stu-id="98ea4-136">If the login does not exist, you must create it.</span></span> <span data-ttu-id="98ea4-137">Per altre informazioni, vedere [Concessione dell'accesso alla rete a un endpoint per il mirroring del database utilizzando l'autenticazione di Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-137">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
4.  <span data-ttu-id="98ea4-138">Per impostare il server principale come partner sul database mirror, connettersi al server mirror ed eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="98ea4-138">To set the principal server as partner on the mirror database, connect to the mirror server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="98ea4-139">ALTER DATABASE *<database_name>* SET PARTNER **=** _<server_network_address>_</span><span class="sxs-lookup"><span data-stu-id="98ea4-139">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="98ea4-140">dove *<database_name>* è il nome del database di cui eseguire il mirroring (questo nome è lo stesso per entrambi i partner) e *<server_network_address>* è l'indirizzo di rete del server principale.</span><span class="sxs-lookup"><span data-stu-id="98ea4-140">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the principal server.</span></span>  
  
     <span data-ttu-id="98ea4-141">La sintassi per un indirizzo di rete del server presenta la seguente struttura:</span><span class="sxs-lookup"><span data-stu-id="98ea4-141">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="98ea4-142">TCP<strong>://</strong> \<*system-address> \*<strong>:</strong> \<*port> \*</span><span class="sxs-lookup"><span data-stu-id="98ea4-142">TCP<strong>://</strong>\<*system-address>*<strong>:</strong>\<*port>*</span></span>  
  
     <span data-ttu-id="98ea4-143">dove \<*system-address>\* è una stringa che identifica in maniera univoca il computer di destinazione e \<*port>\* è il numero di porta usato dall'endpoint del mirroring dell'istanza del server partner.</span><span class="sxs-lookup"><span data-stu-id="98ea4-143">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="98ea4-144">Per altre informazioni, vedere [Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-144">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="98ea4-145">Ad esempio, sull'istanza del server mirror, l'istruzione ALTER DATABASE seguente imposta il partner come istanza del server principale originale.</span><span class="sxs-lookup"><span data-stu-id="98ea4-145">For example, on the mirror server instance, the following ALTER DATABASE statement sets the partner as the original principal server instance.</span></span> <span data-ttu-id="98ea4-146">Il nome del database è **AdventureWorks**, l'indirizzo del sistema è DBSERVER1, ovvero il nome del sistema partner, e il numero della porta usata dall'endpoint del mirroring del database del partner è 7022:</span><span class="sxs-lookup"><span data-stu-id="98ea4-146">The database name is **AdventureWorks**, the system address is DBSERVER1-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7022:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
       SET PARTNER = 'TCP://DBSERVER1:7022'  
    ```  
  
     <span data-ttu-id="98ea4-147">Questa istruzione prepara il server mirror per creare una sessione quando viene contattato dal server principale.</span><span class="sxs-lookup"><span data-stu-id="98ea4-147">This statement prepares the mirror server to form a session when it is contacted by the principal server.</span></span>  
  
5.  <span data-ttu-id="98ea4-148">Per impostare il server mirror come partner sul database principale, connettersi al server principale ed eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="98ea4-148">To set the mirror server as partner on the principal database, connect to the principal server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="98ea4-149">ALTER DATABASE *<database_name>* SET PARTNER **=** _<server_network_address>_</span><span class="sxs-lookup"><span data-stu-id="98ea4-149">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="98ea4-150">Per ulteriori informazioni, vedere il passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="98ea4-150">For more information, see step 4.</span></span>  
  
     <span data-ttu-id="98ea4-151">Ad esempio, sull'istanza del server principale, l'istruzione ALTER DATABASE seguente imposta il partner come istanza del server mirror originale.</span><span class="sxs-lookup"><span data-stu-id="98ea4-151">For example, on the principal server instance, the following ALTER DATABASE statement sets the partner as the original mirror server instance.</span></span> <span data-ttu-id="98ea4-152">Il nome del database è **AdventureWorks**, l'indirizzo del sistema è DBSERVER2, ovvero il nome del sistema partner, e il numero della porta usata dall'endpoint del mirroring del database del partner è 7025:</span><span class="sxs-lookup"><span data-stu-id="98ea4-152">The database name is **AdventureWorks**, the system address is DBSERVER2-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7025:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks SET PARTNER = 'TCP://DBSERVER2:7022'  
    ```  
  
     <span data-ttu-id="98ea4-153">L'immissione di questa istruzione sul server principale avvia la sessione di mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="98ea4-153">Entering this statement on the principal server begins the database mirroring session.</span></span>  
  
6.  <span data-ttu-id="98ea4-154">Per impostazione predefinita, una sessione è impostata su un livello di protezione delle transazioni completo (SAFETY è impostato su FULL), il che determina l'avvio della sessione in modalità sincrona a sicurezza elevata senza failover automatico.</span><span class="sxs-lookup"><span data-stu-id="98ea4-154">By default a session is set to full transaction safety (SAFETY is set to FULL), which starts the session in synchronous, high-safety mode without automatic failover.</span></span> <span data-ttu-id="98ea4-155">È possibile riconfigurare la sessione per l'esecuzione in modalità a sicurezza elevata con failover automatico o in modalità asincrona a prestazioni elevate, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="98ea4-155">You can reconfigure the session to run in high-safety mode with automatic failover or in asynchronous, high-performance mode, as follows:</span></span>  
  
    -   <span data-ttu-id="98ea4-156">**Modalità a sicurezza elevata con failover automatico**</span><span class="sxs-lookup"><span data-stu-id="98ea4-156">**High-safety mode with automatic failover**</span></span>  
  
         <span data-ttu-id="98ea4-157">Se si desidera che una sessione in modalità a sicurezza elevata supporti il failover automatico, aggiungere un'istanza del server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="98ea4-157">If you want a high-safety mode session to support automatic failover, add a witness server instance.</span></span> <span data-ttu-id="98ea4-158">Per altre informazioni, vedere [Aggiungere un server di controllo del mirroring del database tramite l'autenticazione di Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-158">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
    -   <span data-ttu-id="98ea4-159">**Modalità a prestazioni elevate**</span><span class="sxs-lookup"><span data-stu-id="98ea4-159">**High-performance mode**</span></span>  
  
         <span data-ttu-id="98ea4-160">In alternativa, se si desidera evitare il failover automatico e si preferisce privilegiare le prestazioni rispetto alla disponibilità, disattivare la protezione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="98ea4-160">Alternatively, if you do not want automatic failover and you prefer to emphasize performance over availability, turn off transaction safety.</span></span> <span data-ttu-id="98ea4-161">Per altre informazioni, vedere [Modifica della protezione delle transazioni in una sessione di mirroring del database &#40;SQL Server&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-161">For more information, see [Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="98ea4-162">In modalità a prestazioni elevate, WITNESS deve essere impostato su OFF.</span><span class="sxs-lookup"><span data-stu-id="98ea4-162">In high-performance mode, WITNESS should be set to OFF.</span></span> <span data-ttu-id="98ea4-163">Per altre informazioni, vedere [Quorum: Impatto di un server di controllo del mirroring sulla disponibilità del database &#40;mirroring del database&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-163">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98ea4-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="98ea4-164">Example</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98ea4-165">Nell'esempio seguente viene creata una sessione di mirroring del database tra i partner per un database mirror esistente.</span><span class="sxs-lookup"><span data-stu-id="98ea4-165">The following example establishes a database mirroring session between partners for an existing mirror database.</span></span> <span data-ttu-id="98ea4-166">Per informazioni sulla creazione di un database mirror, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-166">For information on creating a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)=.</span></span>  
  
 <span data-ttu-id="98ea4-167">Nell'esempio viene illustrata la procedura di base per la creazione di una sessione di mirroring del database senza un server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="98ea4-167">The example shows the basic steps for creating a database mirroring session without a witness.</span></span> <span data-ttu-id="98ea4-168">I due partner sono le istanze del server predefinite sui due sistemi di computer (PARTNERHOST1 e PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="98ea4-168">The two partners are the default server instances on two computer systems (PARTNERHOST1 and PARTNERHOST5).</span></span> <span data-ttu-id="98ea4-169">Le due istanze dei partner vengono eseguite tramite lo stesso account utente di dominio di Windows (MYDOMAIN\dbousername).</span><span class="sxs-lookup"><span data-stu-id="98ea4-169">The two partner instances run the same Windows domain user account (MYDOMAIN\dbousername).</span></span>  
  
1.  <span data-ttu-id="98ea4-170">Nell'istanza del server principale (istanza predefinita in PARTNERHOST1) creare un endpoint che supporti tutti i ruoli utilizzando la porta 7022:</span><span class="sxs-lookup"><span data-stu-id="98ea4-170">On the principal server instance (default instance on PARTNERHOST1), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="98ea4-171">Per un esempio di configurazione di un account di accesso, vedere [Concessione dell'accesso alla rete a un endpoint per il mirroring del database utilizzando l'autenticazione di Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-171">For an example of how to setup a login, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
2.  <span data-ttu-id="98ea4-172">Nell'istanza del server mirror (istanza predefinita in PARTNERHOST5) creare un endpoint che supporti tutti i ruoli utilizzando la porta 7022:</span><span class="sxs-lookup"><span data-stu-id="98ea4-172">On the mirror server instance (default instance on PARTNERHOST5), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
3.  <span data-ttu-id="98ea4-173">Nell'istanza del server principale (in PARTNERHOST1), eseguire il backup del database:</span><span class="sxs-lookup"><span data-stu-id="98ea4-173">On the principal server instance (on PARTNERHOST1), back up the database:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdvWorks_dbmirror.bak'   
        WITH FORMAT  
    GO  
    ```  
  
4.  <span data-ttu-id="98ea4-174">Sull'istanza del server mirror (in `PARTNERHOST5`), eseguire il ripristino del database:</span><span class="sxs-lookup"><span data-stu-id="98ea4-174">On the mirror server instance (on `PARTNERHOST5`), restore the database:</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks   
        FROM DISK = 'Z:\AdvWorks_dbmirror.bak'   
        WITH NORECOVERY  
    GO  
    ```  
  
5.  <span data-ttu-id="98ea4-175">Dopo aver creato il backup completo del database, è necessario creare un backup del log sul database principale.</span><span class="sxs-lookup"><span data-stu-id="98ea4-175">After you create the full database backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="98ea4-176">Ad esempio, l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente esegue il backup del log nello stesso file utilizzato dal backup del database precedente:</span><span class="sxs-lookup"><span data-stu-id="98ea4-176">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding database backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="98ea4-177">Prima di avviare il mirroring, è necessario applicare il backup del log richiesto ed eventuali backup del log successivi.</span><span class="sxs-lookup"><span data-stu-id="98ea4-177">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="98ea4-178">Ad esempio, l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente ripristina il primo log da C:\AdventureWorks.bak:</span><span class="sxs-lookup"><span data-stu-id="98ea4-178">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from C:\AdventureWorks.bak:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\ AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="98ea4-179">Nell'istanza del server mirror impostare l'istanza del server in PARTNERHOST1 come partner, rendendola il server principale iniziale:</span><span class="sxs-lookup"><span data-stu-id="98ea4-179">On the mirror server instance, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1:7022'  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="98ea4-180">Per impostazione predefinita, una sessione di mirroring del database viene eseguita in modalità sincrona, che dipende da un livello di sicurezza delle transazioni completo (SAFETY impostato su FULL).</span><span class="sxs-lookup"><span data-stu-id="98ea4-180">default, a database mirroring session runs in synchronous mode, which depends on having full transaction safety (SAFETY is set to FULL).</span></span> <span data-ttu-id="98ea4-181">Per fare in modo che una sessione venga eseguita in modalità asincrona a prestazioni elevate impostare SAFETY su OFF.</span><span class="sxs-lookup"><span data-stu-id="98ea4-181">To cause a session to run in asynchronous, high-performance mode, set SAFETY to OFF.</span></span> <span data-ttu-id="98ea4-182">Per altre informazioni, vedere [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-182">For more information, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
8.  <span data-ttu-id="98ea4-183">Nell'istanza del server principale impostare l'istanza del server in `PARTNERHOST5` come partner, rendendola l'istanza del server mirror iniziale:</span><span class="sxs-lookup"><span data-stu-id="98ea4-183">On the principal server instance, set the server instance on `PARTNERHOST5` as the partner (making it the initial mirror server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5:7022'  
    GO  
    ```  
  
9. <span data-ttu-id="98ea4-184">Facoltativamente, se si desidera utilizzare la modalità a sicurezza elevata con failover automatico, impostare l'istanza del server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="98ea4-184">Optionally, if you intend to use high-safety mode with automatic failover, set up the witness server instance.</span></span> <span data-ttu-id="98ea4-185">Per altre informazioni, vedere [Aggiungere un server di controllo del mirroring del database tramite l'autenticazione di Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-185">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98ea4-186">Per un esempio completo che illustri le impostazioni relative alla sicurezza e ai partner, nonché l'aggiunta di un server di controllo del mirroring, vedere [Impostazione del mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="98ea4-186">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ea4-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98ea4-187">See Also</span></span>  
 <span data-ttu-id="98ea4-188">[Impostazione del mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ea4-188">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="98ea4-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="98ea4-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="98ea4-190">[Concessione dell'accesso alla rete a un endpoint per il mirroring del database utilizzando l'autenticazione di Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="98ea4-190">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="98ea4-191">[Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ea4-191">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="98ea4-192">[Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="98ea4-192">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="98ea4-193">[Mirroring del database e log shipping &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ea4-193">[Database Mirroring and Log Shipping &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="98ea4-194">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ea4-194">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="98ea4-195">[Mirroring e replica del database &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ea4-195">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="98ea4-196">[Impostazione del mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ea4-196">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="98ea4-197">[Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="98ea4-197">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 [<span data-ttu-id="98ea4-198">Database Mirroring Operating Modes</span><span class="sxs-lookup"><span data-stu-id="98ea4-198">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
