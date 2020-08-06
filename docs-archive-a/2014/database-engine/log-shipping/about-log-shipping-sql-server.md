---
title: Informazioni sul log shipping (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary servers [SQL Server]
- log shipping [SQL Server], jobs
- copy jobs [SQL Server]
- primary databases [SQL Server]
- log shipping [SQL Server], monitoring
- log shipping [SQL Server], about log shipping
- alert jobs [SQL Server]
- availability [SQL Server]
- jobs [SQL Server], log shipping
- monitor servers [SQL Server]
- restore jobs [SQL Server]
- log shipping [SQL Server]
- backup jobs [SQL Server]
- primary servers [SQL Server]
ms.assetid: 55da6b94-3a4b-4bae-850f-4bf7f6e918ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbf36e0ddd94ec0ab0a40a448e50602decfc0645
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714551"
---
# <a name="about-log-shipping-sql-server"></a><span data-ttu-id="cd476-102">Informazioni sul log shipping (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cd476-102">About Log Shipping (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cd476-103">consente di inviare automaticamente i backup del log delle transazioni da un *database primario* in un'istanza del *server primario* a uno o più *database secondari* in istanze separate del *server secondario* .</span><span class="sxs-lookup"><span data-stu-id="cd476-103">Log shipping allows you to automatically send transaction log backups from a *primary database* on a *primary server* instance to one or more *secondary databases* on separate *secondary server* instances.</span></span> <span data-ttu-id="cd476-104">I backup del log delle transazioni vengono applicati singolarmente a ogni database secondario.</span><span class="sxs-lookup"><span data-stu-id="cd476-104">The transaction log backups are applied to each of the secondary databases individually.</span></span> <span data-ttu-id="cd476-105">Un terzo server facoltativo, noto come *server di monitoraggio*, registra la cronologia e lo stato delle operazioni di backup e di ripristino e genera avvisi nel caso in cui tali operazioni non vengano eseguite come previsto.</span><span class="sxs-lookup"><span data-stu-id="cd476-105">An optional third server instance, known as the *monitor server*, records the history and status of backup and restore operations and, optionally, raises alerts if these operations fail to occur as scheduled.</span></span>  
  
 <span data-ttu-id="cd476-106">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="cd476-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="cd476-107">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="cd476-107">Benefits</span></span>](#Benefits)  
  
-   [<span data-ttu-id="cd476-108">Termini e definizioni</span><span class="sxs-lookup"><span data-stu-id="cd476-108">Terms and Definitions</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="cd476-109">Panoramica del log shipping</span><span class="sxs-lookup"><span data-stu-id="cd476-109">Log Shipping Overview</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="cd476-110">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cd476-110">Interoperability</span></span>](#Interoperability)  
  
-   [<span data-ttu-id="cd476-111">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="cd476-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="cd476-112">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="cd476-112">Benefits</span></span>  
  
-   <span data-ttu-id="cd476-113">Fornisce una soluzione di recupero di emergenza per un solo database primario e uno o più database secondari, ognuno in un'istanza separata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd476-113">Provides a disaster-recovery solution for a single primary database and one or more secondary databases, each on a separate instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="cd476-114">Supporta l'accesso in sola lettura limitato ai database secondari (durante l'intervallo tra processi di ripristino).</span><span class="sxs-lookup"><span data-stu-id="cd476-114">Supports limited read-only access to secondary databases (during the interval between restore jobs).</span></span>  
  
-   <span data-ttu-id="cd476-115">Consente un ritardo specificato dall'utente tra l'esecuzione del backup del log del database primario da parte del server primario e il momento in cui è necessario che i server secondari eseguano il ripristino del backup del log.</span><span class="sxs-lookup"><span data-stu-id="cd476-115">Allows a user-specified delay between when the primary server backs up the log of the primary database and when the secondary servers must restore (apply) the log backup.</span></span> <span data-ttu-id="cd476-116">Un ritardo maggiore può essere utile, ad esempio, se i dati vengono modificati per errore nel database primario.</span><span class="sxs-lookup"><span data-stu-id="cd476-116">A longer delay can be useful, for example, if data is accidentally changed on the primary database.</span></span> <span data-ttu-id="cd476-117">Se la modifica accidentale viene identificata rapidamente, un ritardo può consentire il recupero dei dati precedenti alla modifica da un database secondario prima che la modifica venga estesa anche a questo database.</span><span class="sxs-lookup"><span data-stu-id="cd476-117">If the accidental change is noticed quickly, a delay can let you retrieve still unchanged data from a secondary database before the change is reflected there.</span></span>  
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="cd476-118">Termini e definizioni</span><span class="sxs-lookup"><span data-stu-id="cd476-118">Terms and Definitions</span></span>  
 <span data-ttu-id="cd476-119">server primario</span><span class="sxs-lookup"><span data-stu-id="cd476-119">primary server</span></span>  
 <span data-ttu-id="cd476-120">Istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che costituisce il server di produzione.</span><span class="sxs-lookup"><span data-stu-id="cd476-120">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is your production server.</span></span>  
  
 <span data-ttu-id="cd476-121">database primario</span><span class="sxs-lookup"><span data-stu-id="cd476-121">primary database</span></span>  
 <span data-ttu-id="cd476-122">Il database nel server primario per il quale si desidera eseguire il backup su un altro server.</span><span class="sxs-lookup"><span data-stu-id="cd476-122">The database on the primary server that you want to back up to another server.</span></span> <span data-ttu-id="cd476-123">Tutte le procedure di amministrazione della configurazione per il log shipping tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] vengono eseguite dal database primario.</span><span class="sxs-lookup"><span data-stu-id="cd476-123">All administration of the log shipping configuration through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is performed from the primary database.</span></span>  
  
 <span data-ttu-id="cd476-124">server secondario</span><span class="sxs-lookup"><span data-stu-id="cd476-124">secondary server</span></span>  
 <span data-ttu-id="cd476-125">L'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dove si desidera tenere una copia in modalità warm standby del database primario.</span><span class="sxs-lookup"><span data-stu-id="cd476-125">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where you want to keep a warm standby copy of your primary database.</span></span>  
  
 <span data-ttu-id="cd476-126">database secondario</span><span class="sxs-lookup"><span data-stu-id="cd476-126">secondary database</span></span>  
 <span data-ttu-id="cd476-127">La copia in modalità warm standby del database primario.</span><span class="sxs-lookup"><span data-stu-id="cd476-127">The warm standby copy of the primary database.</span></span> <span data-ttu-id="cd476-128">Il database secondario potrebbe trovarsi nello stato RECOVERING o nello stato STANDBY, in cui rimane disponibile per l'accesso in sola lettura limitato.</span><span class="sxs-lookup"><span data-stu-id="cd476-128">The secondary database may be in either the RECOVERING state or the STANDBY state, which leaves the database available for limited read-only access.</span></span>  
  
 <span data-ttu-id="cd476-129">server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="cd476-129">monitor server</span></span>  
 <span data-ttu-id="cd476-130">Istanza facoltativa di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che tiene traccia di tutti i dettagli del log shipping, tra cui:</span><span class="sxs-lookup"><span data-stu-id="cd476-130">An optional instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that tracks all of the details of log shipping, including:</span></span>  
  
-   <span data-ttu-id="cd476-131">Quando è stato eseguito l'ultimo backup del log delle transazioni nel database primario.</span><span class="sxs-lookup"><span data-stu-id="cd476-131">When the transaction log on the primary database was last backed up.</span></span>  
  
-   <span data-ttu-id="cd476-132">Quando i server secondari hanno eseguito per l'ultima volta la copia e il ripristino dei file di backup.</span><span class="sxs-lookup"><span data-stu-id="cd476-132">When the secondary servers last copied and restored the backup files.</span></span>  
  
-   <span data-ttu-id="cd476-133">Informazioni sugli avvisi di backup non riusciti.</span><span class="sxs-lookup"><span data-stu-id="cd476-133">Information about any backup failure alerts.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd476-134">Una volta configurato il server di monitoraggio, non sarà possibile modificarlo senza prima rimuovere il log shipping.</span><span class="sxs-lookup"><span data-stu-id="cd476-134">Once the monitor server has been configured, it cannot be changed without removing log shipping first.</span></span>  
  
 <span data-ttu-id="cd476-135">processo di backup</span><span class="sxs-lookup"><span data-stu-id="cd476-135">backup job</span></span>  
 <span data-ttu-id="cd476-136">Processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che esegue il backup, registra la cronologia nel server locale e nel server di monitoraggio ed elimina i file di backup e le informazioni sulla cronologia precedenti.</span><span class="sxs-lookup"><span data-stu-id="cd476-136">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that  performs the backup operation, logs history to the local server and the monitor server, and deletes old backup files and history information.</span></span> <span data-ttu-id="cd476-137">Se il log shipping è abilitato, nell'istanza del server primario viene creata la categoria di processi relativa al backup per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="cd476-137">When log shipping is enabled, the job category "Log Shipping Backup" is created on the primary server instance.</span></span>  
  
 <span data-ttu-id="cd476-138">processo di copia</span><span class="sxs-lookup"><span data-stu-id="cd476-138">copy job</span></span>  
 <span data-ttu-id="cd476-139">Processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che copia i file di backup del server primario in una destinazione configurabile del server secondario e registra la cronologia nel server secondario e nel server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="cd476-139">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that copies the backup files from the primary server to a configurable destination on the secondary server and logs history on the secondary server and the monitor server.</span></span> <span data-ttu-id="cd476-140">Se il log shipping è abilitato in un database, la categoria di processi relativa alla copia per il log shipping viene creata in ciascun server secondario in una configurazione per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="cd476-140">When log shipping is enabled on a database, the job category "Log Shipping Copy" is created on each secondary server in a log shipping configuration.</span></span>  
  
 <span data-ttu-id="cd476-141">processo di ripristino</span><span class="sxs-lookup"><span data-stu-id="cd476-141">restore job</span></span>  
 <span data-ttu-id="cd476-142">Processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che ripristina i file di backup copiati nei database secondari.</span><span class="sxs-lookup"><span data-stu-id="cd476-142">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that restores the copied backup files to the secondary databases.</span></span> <span data-ttu-id="cd476-143">Registra la cronologia nel server locale e nel server di monitoraggio ed elimina i file e le informazioni sulla cronologia precedenti.</span><span class="sxs-lookup"><span data-stu-id="cd476-143">It logs history on the local server and the monitor server, and deletes old files and old history information.</span></span> <span data-ttu-id="cd476-144">Se il log shipping è abilitato in un database, la categoria di processi relativa al ripristino per il log shipping viene creata per l'istanza del server secondario.</span><span class="sxs-lookup"><span data-stu-id="cd476-144">When log shipping is enabled on a database, the job category "Log Shipping Restore" is created on the secondary server instance.</span></span>  
  
 <span data-ttu-id="cd476-145">processo gestione avvisi</span><span class="sxs-lookup"><span data-stu-id="cd476-145">alert job</span></span>  
 <span data-ttu-id="cd476-146">Processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che genera avvisi per i database primario e secondario nel caso in cui le operazioni di backup e ripristino non vengano completate entro la soglia stabilita.</span><span class="sxs-lookup"><span data-stu-id="cd476-146">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that raises alerts for primary and secondary databases when a backup or restore operation does not complete successfully within a specified threshold.</span></span> <span data-ttu-id="cd476-147">Se il log shipping è abilitato in un database, la categoria relativa alla gestione degli avvisi per il log shipping viene creata sull'istanza del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="cd476-147">When log shipping is enabled on a database, job category "Log Shipping Alert" is created on the monitor server instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="cd476-148">Per ogni avviso, è necessario specificare un numero.</span><span class="sxs-lookup"><span data-stu-id="cd476-148">For each alert, you need to specify an alert number.</span></span> <span data-ttu-id="cd476-149">Assicurarsi inoltre di configurare l'avviso in modo che un operatore venga notificato quando viene generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="cd476-149">Also, be sure to configure the alert to notify an operator when an alert is raised.</span></span>  
  
##  <a name="log-shipping-overview"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="cd476-150">Panoramica del log shipping</span><span class="sxs-lookup"><span data-stu-id="cd476-150">Log Shipping Overview</span></span>  
 <span data-ttu-id="cd476-151">Il log shipping prevede tre operazioni:</span><span class="sxs-lookup"><span data-stu-id="cd476-151">Log shipping consists of three operations:</span></span>  
  
1.  <span data-ttu-id="cd476-152">Backup del log delle transazioni nell'istanza del server primario.</span><span class="sxs-lookup"><span data-stu-id="cd476-152">Back up the transaction log at the primary server instance.</span></span>  
  
2.  <span data-ttu-id="cd476-153">Copia del file di log delle transazioni nell'istanza del server secondario.</span><span class="sxs-lookup"><span data-stu-id="cd476-153">Copy the transaction log file to the secondary server instance.</span></span>  
  
3.  <span data-ttu-id="cd476-154">Ripristino del backup del log nell'istanza del server secondario.</span><span class="sxs-lookup"><span data-stu-id="cd476-154">Restore the log backup on the secondary server instance.</span></span>  
  
 <span data-ttu-id="cd476-155">È possibile distribuire il log a più istanze del server secondario</span><span class="sxs-lookup"><span data-stu-id="cd476-155">The log can be shipped to multiple secondary server instances.</span></span> <span data-ttu-id="cd476-156">e in questo caso sarà necessario ripetere le operazioni 2 e 3 per ognuna delle istanze.</span><span class="sxs-lookup"><span data-stu-id="cd476-156">In such cases, operations 2 and 3 are duplicated for each secondary server instance.</span></span>  
  
 <span data-ttu-id="cd476-157">Il failover di una configurazione per il log shipping dal server primario al server secondario non viene eseguito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cd476-157">A log shipping configuration does not automatically fail over from the primary server to the secondary server.</span></span> <span data-ttu-id="cd476-158">Se il database primario non è più disponibile, è possibile portare online manualmente uno qualsiasi dei database secondari.</span><span class="sxs-lookup"><span data-stu-id="cd476-158">If the primary database becomes unavailable, any of the secondary databases can be brought online manually.</span></span>  
  
 <span data-ttu-id="cd476-159">È possibile utilizzare un database secondario per la generazione di report.</span><span class="sxs-lookup"><span data-stu-id="cd476-159">You can use a secondary database for reporting purposes.</span></span>  
  
 <span data-ttu-id="cd476-160">È inoltre possibile configurare avvisi per la configurazione per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="cd476-160">In addition, you can configure alerts for your log shipping configuration.</span></span>  
  
### <a name="a-typical-log-shipping-configuration"></a><span data-ttu-id="cd476-161">Configurazione tipica per il log shipping</span><span class="sxs-lookup"><span data-stu-id="cd476-161">A Typical Log Shipping Configuration</span></span>  
 <span data-ttu-id="cd476-162">Nella figura seguente viene illustrata una configurazione per il log shipping con l'istanza del server primario, tre istanze del server secondario e un'istanza del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="cd476-162">The following figure shows a log shipping configuration with the primary server instance, three secondary server instances, and a monitor server instance.</span></span> <span data-ttu-id="cd476-163">Nella figura vengono illustrati i passaggi eseguiti dai processi di backup, copia e ripristino:</span><span class="sxs-lookup"><span data-stu-id="cd476-163">The figure illustrates the steps performed by backup, copy, and restorejobs, as follows:</span></span>  
  
1.  <span data-ttu-id="cd476-164">L'istanza del server primario esegue il processo di backup per eseguire il backup del log delle transazioni nel database primario.</span><span class="sxs-lookup"><span data-stu-id="cd476-164">The primary server instance runs the backup job to back up the transaction log on the primary database.</span></span> <span data-ttu-id="cd476-165">Il backup del log viene quindi inserito in un file di backup del log primario, che viene inviato alla cartella di backup.</span><span class="sxs-lookup"><span data-stu-id="cd476-165">This server instance then places the log backup into a primary log-backup file, which it sends to the backup folder.</span></span>  <span data-ttu-id="cd476-166">In questa figura, la cartella di backup risiede in una directory condivisa, la *condivisione di backup*.</span><span class="sxs-lookup"><span data-stu-id="cd476-166">In this figure, the backup folder is on a shared directory-the *backup share*.</span></span>  
  
2.  <span data-ttu-id="cd476-167">Ognuna delle tre istanze del server secondario esegue un processo di copia per copiare il file di backup del log primario nella propria cartella di destinazione locale.</span><span class="sxs-lookup"><span data-stu-id="cd476-167">Each of the three secondary server instances runs its own copy job to copy the primary log-backup file to its own local destination folder.</span></span>  
  
3.  <span data-ttu-id="cd476-168">Ognuna delle istanze del server secondario esegue un processo di ripristino per ripristinare il backup del log dalla cartella di destinazione locale al database secondario locale.</span><span class="sxs-lookup"><span data-stu-id="cd476-168">Each secondary server instance runs its own restore job to restore the log backup from the local destination folder onto the local secondary database.</span></span>  
  
 <span data-ttu-id="cd476-169">Tramite le istanze dei server primario e secondario vengono inviati la propria cronologia e il proprio stato all'istanza del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="cd476-169">The primary and secondary server instances send their own history and status to the monitor server instance.</span></span>  
  
 <span data-ttu-id="cd476-170">![Configurazione che include processi di backup, copia e ripristino](../media/ls-typical-configuration.gif "Configurazione che include processi di backup, copia e ripristino")</span><span class="sxs-lookup"><span data-stu-id="cd476-170">![Configuration showing backup, copy, & restore jobs](../media/ls-typical-configuration.gif "Configuration showing backup, copy, & restore jobs")</span></span>  
  
##  <a name="interoperability"></a><a name="Interoperability"></a> <span data-ttu-id="cd476-171">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cd476-171">Interoperability</span></span>  
 <span data-ttu-id="cd476-172">Il log shipping può essere utilizzato con le funzionalità o i componenti seguenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cd476-172">Log shipping can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="cd476-173">Prerequisiti per la migrazione dal log shipping a Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-173">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
-   [<span data-ttu-id="cd476-174">Mirroring del database e log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-174">Database Mirroring and Log Shipping &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="cd476-175">Log shipping e replica &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-175">Log Shipping and Replication &#40;SQL Server&#41;</span></span>](log-shipping-and-replication-sql-server.md)  
  
> [!NOTE]  
>  [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] <span data-ttu-id="cd476-176">e il mirroring del database si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="cd476-176">and database mirroring are mutually exclusive.</span></span> <span data-ttu-id="cd476-177">Un database configurato per una di queste funzionalità non può essere configurato per l'altra.</span><span class="sxs-lookup"><span data-stu-id="cd476-177">A database that is configured for one of these features cannot be configured for the other.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cd476-178">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="cd476-178">Related Tasks</span></span>  
  
-   [<span data-ttu-id="cd476-179">Aggiornare il log shipping a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-179">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="cd476-180">Configurare il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-180">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="cd476-181">Aggiungere un database secondario a una configurazione per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-181">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="cd476-182">Rimuovere un database secondario da una configurazione per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-182">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="cd476-183">Rimuovere il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-183">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="cd476-184">Visualizzare il report di log shipping &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-184">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="cd476-185">Monitorare il log shipping &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-185">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="cd476-186">Failover su un database secondario per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-186">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="cd476-187">Failover su un database secondario per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-187">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="cd476-188">Gestione di account di accesso e di processi dopo un cambio di ruolo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-188">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="cd476-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd476-189">See Also</span></span>  
 [<span data-ttu-id="cd476-190">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd476-190">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)  
  
  
