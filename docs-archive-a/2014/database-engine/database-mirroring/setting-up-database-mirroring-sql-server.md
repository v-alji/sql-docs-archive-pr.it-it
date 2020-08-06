---
title: Impostazione del mirroring del database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
ms.assetid: da45efed-55eb-4c71-be34-ac2589dfce8d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7e55e973ffbb888394d13578f21e08a08ae9d03c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629588"
---
# <a name="setting-up-database-mirroring-sql-server"></a><span data-ttu-id="9dce6-102">Impostazione del mirroring del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9dce6-102">Setting Up Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="9dce6-103">In questa sezione vengono illustrati i prerequisiti, le indicazioni e la procedura per l'impostazione del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="9dce6-103">This section describes the prerequisites, recommendations, and steps for setting up database mirroring.</span></span> <span data-ttu-id="9dce6-104">Per un'introduzione al mirroring del database, vedere [Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-104">For an introduction to database mirroring, see [Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9dce6-105">È consigliabile configurare il mirroring del database durante le fasce orarie di minore attività, in quanto la configurazione può influire sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="9dce6-105">We recommend that you configure database mirroring during off-peak hours because configuration can impact performance.</span></span>  
  
 
  
##  <a name="preparing-a-server-instance-to-host-a-mirror-server"></a><a name="PrepareInstances"></a> <span data-ttu-id="9dce6-106">Preparazione di un'istanza del server a ospitare un server mirror</span><span class="sxs-lookup"><span data-stu-id="9dce6-106">Preparing a Server Instance to Host a Mirror Server</span></span>  
 <span data-ttu-id="9dce6-107">Per ogni sessione di mirroring del database:</span><span class="sxs-lookup"><span data-stu-id="9dce6-107">For each database mirroring session:</span></span>  
  
1.  <span data-ttu-id="9dce6-108">È necessario che il server principale, il server mirror e il server di controllo, se presente, siano ospitati in istanze di server distinte, situate in sistemi host distinti.</span><span class="sxs-lookup"><span data-stu-id="9dce6-108">The principal server, mirror server, and witness, if any, must be hosted by separate server instances, which should be on separate host systems.</span></span> <span data-ttu-id="9dce6-109">Per ogni istanza del server è necessario un endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="9dce6-109">Each of the server instances requires a database mirroring endpoint.</span></span> <span data-ttu-id="9dce6-110">Se è necessario creare un endpoint del mirroring di database, assicurarsi che sia accessibile alle altre istanze del server.</span><span class="sxs-lookup"><span data-stu-id="9dce6-110">If you need to create a database mirroring endpoint, ensure that it is accessible to the other server instances.</span></span>  
  
     <span data-ttu-id="9dce6-111">La forma di autenticazione utilizzata per il mirroring del database da un'istanza del server corrisponde a una proprietà dell'endpoint del mirroring del database dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="9dce6-111">The form of authentication used for database mirroring by a server instance is a property of its database mirroring endpoint.</span></span> <span data-ttu-id="9dce6-112">Per il mirroring del database sono disponibili due tipi di sicurezza del trasporto: autenticazione di Windows o autenticazione basata su certificati.</span><span class="sxs-lookup"><span data-stu-id="9dce6-112">Two types of transport security are available for database mirroring: Windows Authentication or certificate-based authentication.</span></span> <span data-ttu-id="9dce6-113">Per ulteriori informazioni, vedere [sicurezza del trasporto per il mirroring del database e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-113">For more information, see [Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span></span>  
  
     <span data-ttu-id="9dce6-114">I requisiti per l'accesso alla rete sono specifici della forma di autenticazione, come segue:</span><span class="sxs-lookup"><span data-stu-id="9dce6-114">The requirements for network access are specific to the form of authentication, as follows:</span></span>  
  
    -   <span data-ttu-id="9dce6-115">**In caso di utilizzo dell'autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="9dce6-115">**If using Windows Authentication**</span></span>  
  
         <span data-ttu-id="9dce6-116">Se le istanze del server sono in esecuzione in account utente di dominio diversi, per ciascuna istanza è necessario un account di accesso nel database **master** delle altre.</span><span class="sxs-lookup"><span data-stu-id="9dce6-116">If server instances are running under different domain user accounts, each requires a login in the **master** database of the others.</span></span> <span data-ttu-id="9dce6-117">Se l'account di accesso non esiste, è necessario crearlo.</span><span class="sxs-lookup"><span data-stu-id="9dce6-117">If the login does not exist, you must create it.</span></span> <span data-ttu-id="9dce6-118">Per altre informazioni, vedere [Concessione dell'accesso alla rete a un endpoint per il mirroring del database utilizzando l'autenticazione di Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-118">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
    -   <span data-ttu-id="9dce6-119">**In caso di utilizzo di certificati**</span><span class="sxs-lookup"><span data-stu-id="9dce6-119">**If using certificates**</span></span>  
  
         <span data-ttu-id="9dce6-120">Per abilitare l'autenticazione del certificato per il mirroring del database in una determinata istanza del server, l'amministratore di sistema deve configurare ogni istanza del server per l'utilizzo dei certificati nelle connessioni in uscita e in ingresso.</span><span class="sxs-lookup"><span data-stu-id="9dce6-120">To enable certificate authentication for database mirroring on a given server instance, the system administrator must configure each server instance to use certificates on both outbound and inbound connections.</span></span> <span data-ttu-id="9dce6-121">Le connessioni in uscita devono essere configurate per prime.</span><span class="sxs-lookup"><span data-stu-id="9dce6-121">Outbound connections must be configured first.</span></span> <span data-ttu-id="9dce6-122">Per ulteriori informazioni, vedere [Utilizzare certificati per un endpoint del mirroring del database &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-122">For more information, see [Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="9dce6-123">Verificare che nel server mirror siano presenti account di accesso per tutti gli utenti del database.</span><span class="sxs-lookup"><span data-stu-id="9dce6-123">Make sure that logins exist on the mirror server for all the database users.</span></span> <span data-ttu-id="9dce6-124">Per ulteriori informazioni, vedere la pagina relativa alla [configurazione degli account di accesso per il mirroring del database o Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](set-up-login-accounts-database-mirroring-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-124">For more information, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](set-up-login-accounts-database-mirroring-always-on-availability.md).</span></span>  
  
3.  <span data-ttu-id="9dce6-125">Sull'istanza del server che ospiterà il database mirror, configurare il resto dell'ambiente richiesto per il database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="9dce6-125">On the server instance that will host the mirror database, set up the rest of the environment that is required for the mirrored database.</span></span> <span data-ttu-id="9dce6-126">Per altre informazioni, vedere [Gestione dei metadati quando si rende disponibile un database in un'altra istanza del server &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-126">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
##  <a name="overview-establishing-a-database-mirroring-session"></a><a name="EstablishUsingWinAuthentication"></a> <span data-ttu-id="9dce6-127">Panoramica: apertura di una sessione di mirroring del database</span><span class="sxs-lookup"><span data-stu-id="9dce6-127">Overview: Establishing a Database Mirroring Session</span></span>  
 <span data-ttu-id="9dce6-128">I passaggi di base per stabilire una sessione di mirroring sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dce6-128">The basic steps for establishing a mirroring session are as follows:</span></span>  
  
1.  <span data-ttu-id="9dce6-129">Creare il database mirror ripristinando i backup seguenti, utilizzando RESTORE WITH NORECOVERY per ogni operazione di ripristino:</span><span class="sxs-lookup"><span data-stu-id="9dce6-129">Create the mirror database by restoring the following backups, using RESTORE WITH NORECOVERY on every restore operation:</span></span>  
  
    1.  <span data-ttu-id="9dce6-130">Ripristinare un backup completo recente del database principale dopo aver verificato che il database principale utilizzava già il modello di recupero con registrazione completa al momento dell'esecuzione del backup.</span><span class="sxs-lookup"><span data-stu-id="9dce6-130">Restore a recent full database backup of the principal database, after making sure that the principal database was already using the full recovery model when the backup was taken.</span></span> <span data-ttu-id="9dce6-131">Il database mirror deve avere lo stesso nome del database principale.</span><span class="sxs-lookup"><span data-stu-id="9dce6-131">The mirror database must have the same name as the principal database.</span></span>  
  
    2.  <span data-ttu-id="9dce6-132">Se sono stati effettuati backup differenziali del database dopo il backup completo ripristinato, ripristinare il backup differenziale più recente.</span><span class="sxs-lookup"><span data-stu-id="9dce6-132">If you have taken any differential backups of the database since the restored full backup, restore your most recent differential backup.</span></span>  
  
    3.  <span data-ttu-id="9dce6-133">Ripristinare tutti i backup del log eseguiti dopo il backup completo o differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="9dce6-133">Restore all the log backups done since the full or differential database backup.</span></span>  
  
     <span data-ttu-id="9dce6-134">Per altre informazioni, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-134">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9dce6-135">Completare i passaggi di installazione rimanenti non appena possibile dopo l'esecuzione del backup del database principale.</span><span class="sxs-lookup"><span data-stu-id="9dce6-135">Complete the remaining setup steps as soon as you can after taking the backup of the principal database.</span></span> <span data-ttu-id="9dce6-136">Prima di poter avviare il mirroring nei partner, è consigliabile creare un backup del log corrente nel database originale e ripristinarlo nel futuro database mirror.</span><span class="sxs-lookup"><span data-stu-id="9dce6-136">Before you can start mirroring on the partners, you should create a current log backup on the original database and restore it to the future mirror database.</span></span>  
  
2.  <span data-ttu-id="9dce6-137">È possibile impostare il mirroring utilizzando [!INCLUDE[tsql](../../includes/tsql-md.md)] o la procedura guidata per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="9dce6-137">You can set up mirroring by using either [!INCLUDE[tsql](../../includes/tsql-md.md)] or the Database Mirroring Wizard.</span></span> <span data-ttu-id="9dce6-138">Per ulteriori informazioni, vedere uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dce6-138">For more information, see one of the following:</span></span>  
  
    -   [<span data-ttu-id="9dce6-139">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-139">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
    -   [<span data-ttu-id="9dce6-140">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-140">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
3.  <span data-ttu-id="9dce6-141">Per impostazione predefinita, una sessione è impostata su un livello di protezione delle transazioni completo (SAFETY è impostato su FULL), il che determina l'avvio della sessione in modalità sincrona a sicurezza elevata senza failover automatico.</span><span class="sxs-lookup"><span data-stu-id="9dce6-141">By default a session is set to full transaction safety (SAFETY is set to FULL), which starts the session in synchronous, high-safety mode without automatic failover.</span></span> <span data-ttu-id="9dce6-142">È possibile riconfigurare la sessione per l'esecuzione in modalità a sicurezza elevata con failover automatico o in modalità asincrona a prestazioni elevate, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9dce6-142">You can reconfigure the session to run in high-safety mode with automatic failover or in asynchronous, high-performance mode, as follows:</span></span>  
  
    -   <span data-ttu-id="9dce6-143">**Modalità a sicurezza elevata con failover automatico**</span><span class="sxs-lookup"><span data-stu-id="9dce6-143">**High-safety mode with automatic failover**</span></span>  
  
         <span data-ttu-id="9dce6-144">Se si desidera che una sessione in modalità a sicurezza elevata supporti il failover automatico, aggiungere un'istanza del server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="9dce6-144">If you want a high-safety mode session to support automatic failover, add a witness server instance.</span></span>  
  
         <span data-ttu-id="9dce6-145">**Per aggiungere un server di controllo del mirroring**</span><span class="sxs-lookup"><span data-stu-id="9dce6-145">**To add a witness**</span></span>  
  
        -   [<span data-ttu-id="9dce6-146">Aggiungere un server di controllo del mirroring del database tramite l'autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-146">Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md)  
  
        -   [<span data-ttu-id="9dce6-147">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-147">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
        > [!NOTE]  
        >  <span data-ttu-id="9dce6-148">Il proprietario del database può disattivare il server di controllo del mirroring di un database in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="9dce6-148">The database owner can turn off the witness for a database at any time.</span></span> <span data-ttu-id="9dce6-149">Un server di controllo del mirroring disattivato è praticamente assente e di conseguenza il failover automatico non può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="9dce6-149">Turning off the witness is equivalent to having no witness, and automatic failover cannot occur.</span></span>  
  
    -   <span data-ttu-id="9dce6-150">**Modalità a prestazioni elevate**</span><span class="sxs-lookup"><span data-stu-id="9dce6-150">**High-performance mode**</span></span>  
  
         <span data-ttu-id="9dce6-151">In alternativa, se si desidera evitare il failover automatico e si preferisce privilegiare le prestazioni rispetto alla disponibilità, disattivare la protezione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="9dce6-151">Alternatively, if you do not want automatic failover and you prefer to emphasize performance over availability, turn off transaction safety.</span></span> <span data-ttu-id="9dce6-152">Per altre informazioni, vedere [Modifica della protezione delle transazioni in una sessione di mirroring del database &#40;SQL Server&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-152">For more information, see [Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9dce6-153">In modalità a prestazioni elevate, WITNESS deve essere impostato su OFF.</span><span class="sxs-lookup"><span data-stu-id="9dce6-153">In high-performance mode, WITNESS needs to be set to OFF.</span></span> <span data-ttu-id="9dce6-154">Per altre informazioni, vedere [Quorum: Impatto di un server di controllo del mirroring sulla disponibilità del database &#40;mirroring del database&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-154">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9dce6-155">Per un esempio dell'uso di [!INCLUDE[tsql](../../includes/tsql-md.md)] per impostare il mirroring del database tramite l'autenticazione di Microsoft Windows, vedere [Esempio: Impostazione del mirroring del database tramite l'autenticazione di Windows &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-155">For an example of using [!INCLUDE[tsql](../../includes/tsql-md.md)] to set up database mirroring using Microsoft Windows Authentication, see [Example: Setting Up Database Mirroring Using Windows Authentication &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md).</span></span>  
>   
>  <span data-ttu-id="9dce6-156">Per un esempio dell'uso di [!INCLUDE[tsql](../../includes/tsql-md.md)] per impostare il mirroring del database tramite la sicurezza basata sui certificati, vedere [Esempio: Configurazione del mirroring del database tramite certificati &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-156">For an example of using [!INCLUDE[tsql](../../includes/tsql-md.md)] to set up database mirroring using certificate-based security, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
 
  
##  <a name="in-this-section"></a><a name="InThisSection"></a> <span data-ttu-id="9dce6-157">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9dce6-157">In This Section</span></span>  
 [<span data-ttu-id="9dce6-158">Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-158">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
 <span data-ttu-id="9dce6-159">Include un riepilogo della procedura di creazione di un database mirror o di preparazione di un database mirror prima di riprendere una sessione sospesa.</span><span class="sxs-lookup"><span data-stu-id="9dce6-159">Summarizes the steps for creating a mirror database or preparing a mirror database before resuming a suspended session.</span></span> <span data-ttu-id="9dce6-160">Include inoltre collegamenti ad altre procedure.</span><span class="sxs-lookup"><span data-stu-id="9dce6-160">Also provides links to how-to topics.</span></span>  
  
 [<span data-ttu-id="9dce6-161">Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-161">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](specify-a-server-network-address-database-mirroring.md)  
 <span data-ttu-id="9dce6-162">Descrive la sintassi di un indirizzo di rete del server, in che modo l'indirizzo identifica l'endpoint del mirroring del database dell'istanza del server e come individuare il nome di dominio completo di un sistema.</span><span class="sxs-lookup"><span data-stu-id="9dce6-162">Describes the syntax of a server network address, how the address identifies the database mirroring endpoint of the server instance, and how to find the fully-qualified domain name of a system.</span></span>  
  
 [<span data-ttu-id="9dce6-163">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-163">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
 <span data-ttu-id="9dce6-164">Viene descritto come utilizzare la Configurazione guidata sicurezza mirroring del database per avviare il mirroring di un database.</span><span class="sxs-lookup"><span data-stu-id="9dce6-164">Describes how to use the Configure Database Mirroring Security Wizard to start database mirroring on a database.</span></span>  
  
 [<span data-ttu-id="9dce6-165">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-165">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
 <span data-ttu-id="9dce6-166">Viene descritta la procedura [!INCLUDE[tsql](../../includes/tsql-md.md)] per l'impostazione del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="9dce6-166">Describes the [!INCLUDE[tsql](../../includes/tsql-md.md)] steps for setting up database mirroring.</span></span>  
  
 [<span data-ttu-id="9dce6-167">Esempio: Configurazione del mirroring del database tramite l'autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-167">Example: Setting Up Database Mirroring Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md)  
 <span data-ttu-id="9dce6-168">Include un esempio di tutte le fasi necessarie per creare una sessione di mirroring del database con un server di controllo del mirroring, utilizzando l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="9dce6-168">Contains an example of all the stages required to create a database mirroring session with a witness, using Windows Authentication.</span></span>  
  
 [<span data-ttu-id="9dce6-169">Esempio: Configurazione del mirroring del database tramite certificati &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-169">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
 <span data-ttu-id="9dce6-170">Include un esempio di tutte le fasi necessarie per creare una sessione di mirroring del database con un server di controllo del mirroring, utilizzando l'autenticazione basata sui certificati.</span><span class="sxs-lookup"><span data-stu-id="9dce6-170">Contains an example of all the stages required to create a database mirroring session with a witness, using certificate-based authentication.</span></span>  
  
 [<span data-ttu-id="9dce6-171">Configurare gli account di accesso per il mirroring del database o Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-171">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](set-up-login-accounts-database-mirroring-always-on-availability.md)  
 <span data-ttu-id="9dce6-172">Descrive la creazione di un account di accesso per un'istanza del server remota che utilizza un account diverso dall'istanza del server locale.</span><span class="sxs-lookup"><span data-stu-id="9dce6-172">Describes creating a login for a remote server instance that is using a different account than the local server instance.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9dce6-173">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="9dce6-173">Related Tasks</span></span>  
 <span data-ttu-id="9dce6-174">**SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-174">**SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="9dce6-175">Avvio della Configurazione guidata sicurezza mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-175">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
-   [<span data-ttu-id="9dce6-176">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-176">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
 <span data-ttu-id="9dce6-177">**Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="9dce6-177">**Transact-SQL**</span></span>  
  
-   [<span data-ttu-id="9dce6-178">Concessione dell'accesso alla rete a un endpoint per il mirroring del database utilizzando l'autenticazione di Windows &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-178">Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;</span></span>](../database-mirroring-allow-network-access-windows-authentication.md)  
  
-   [<span data-ttu-id="9dce6-179">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in uscita &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-179">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="9dce6-180">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-180">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="9dce6-181">Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-181">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="9dce6-182">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-182">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="9dce6-183">Aggiungere un server di controllo del mirroring del database tramite l'autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-183">Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="9dce6-184">Impostazione di un database mirror per l'utilizzo della proprietà Trustworthy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-184">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
 <span data-ttu-id="9dce6-185">**Transact-SQL/SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-185">**Transact-SQL/SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="9dce6-186">Riduzione al minimo del tempo di inattività per i database con mirroring quando si aggiornano le istanze del server</span><span class="sxs-lookup"><span data-stu-id="9dce6-186">Minimize Downtime for Mirrored Databases When Upgrading Server Instances</span></span>](upgrading-mirrored-instances.md)  
  
-   [<span data-ttu-id="9dce6-187">Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-187">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="9dce6-188">Risolvere i problemi relativi alla configurazione del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-188">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="9dce6-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dce6-189">See Also</span></span>  
 <span data-ttu-id="9dce6-190">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9dce6-190">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="9dce6-191">[Mirroring del database: interoperabilità e coesistenza &#40;SQL Server&#41;](database-mirroring-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9dce6-191">[Database Mirroring: Interoperability and Coexistence &#40;SQL Server&#41;](database-mirroring-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="9dce6-192">[Sicurezza del trasporto per il mirroring del database e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="9dce6-192">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 [<span data-ttu-id="9dce6-193">Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;</span><span class="sxs-lookup"><span data-stu-id="9dce6-193">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](specify-a-server-network-address-database-mirroring.md)  
  
  