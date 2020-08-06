---
title: Aggiornare e aggiornare i server del gruppo di disponibilità con tempi di inattività e perdita di dati minimi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: f670af56-dbcc-4309-9119-f919dcad8a65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6bac882b93016a430fbcace2d590e6cc087123d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724952"
---
# <a name="upgrade-and-update-of-availability-group-servers-with-minimal-downtime-and-data-loss"></a><span data-ttu-id="d3ed4-102">Aggiornamento dei server dei gruppi di disponibilità con tempi di inattività e perdita dei dati minimi</span><span class="sxs-lookup"><span data-stu-id="d3ed4-102">Upgrade and Update of Availability Group Servers with Minimal Downtime and Data Loss</span></span>
  <span data-ttu-id="d3ed4-103">Quando si aggiornano istanze del server da SQL Server 2012 a un Service Pack o a una versione più recente, è possibile ridurre i tempi di inattività per un gruppo di disponibilità alla durata di un singolo failover manuale eseguendo un aggiornamento in sequenza.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-103">When updating or upgrading server instances from SQL Server 2012 to a service pack or a newer version, you can reduce downtime for an availability group to only a single manual failover by performing a sequential update or upgrade.</span></span> <span data-ttu-id="d3ed4-104">L'aggiornamento in sequenza può essere effettuato sia per passare a versioni successive di SQL Server sia per aggiornare la versione corrente con hotfix o Service Pack.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-104">For upgrading SQL Server versions, it is known as rolling upgrade; for updating the current SQL Server version with hotfixes or service packs, it is known as rolling update.</span></span>  
  
 <span data-ttu-id="d3ed4-105">In questo argomento vengono illustrate esclusivamente le modalità di aggiornamento di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-105">This topic limits the discussion to SQL Server upgrades/updates only.</span></span> <span data-ttu-id="d3ed4-106">Per gli aggiornamenti o gli aggiornamenti relativi al sistema operativo in cui sono in esecuzione le istanze di SQL Server a disponibilità elevata, vedere [migrazione tra cluster di gruppi di disponibilità AlwaysOn per gli aggiornamenti del sistema operativo](https://msdn.microsoft.com/library/jj873730.aspx)</span><span class="sxs-lookup"><span data-stu-id="d3ed4-106">For operating system-related upgrades/updates that the highly-available SQL Server instances are running on, see [Cross-cluster Migration of AlwaysOn Availability Groups for Operating System Upgrades](https://msdn.microsoft.com/library/jj873730.aspx)</span></span>  
  
## <a name="rolling-upgradeupdate-best-practices-for-alwayson-availability-groups"></a><span data-ttu-id="d3ed4-107">Procedure consigliate relative all'aggiornamento in sequenza per i gruppi di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="d3ed4-107">Rolling Upgrade/Update Best Practices for AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="d3ed4-108">Quando si eseguono aggiornamenti dei server, è consigliabile attenersi alle procedure consigliate illustrate di seguito allo scopo di ridurre al minimo i tempi di inattività e la perdita di dati per i gruppi di disponibilità:</span><span class="sxs-lookup"><span data-stu-id="d3ed4-108">The following best practices should be observed when performing server upgrades/updates in order to minimize downtime and data loss for your availability groups:</span></span>  
  
-   <span data-ttu-id="d3ed4-109">Prima di avviare l'aggiornamento in sequenza:</span><span class="sxs-lookup"><span data-stu-id="d3ed4-109">Before starting the rolling upgrade/update,</span></span>  
  
    -   <span data-ttu-id="d3ed4-110">Effettuare un failover manuale di prova su almeno una delle repliche con commit sincrono</span><span class="sxs-lookup"><span data-stu-id="d3ed4-110">Perform a practice manual failover on at least one of your synchronous-commit replicas</span></span>  
  
    -   <span data-ttu-id="d3ed4-111">Proteggere i dati eseguendo un backup completo di ogni database di disponibilità</span><span class="sxs-lookup"><span data-stu-id="d3ed4-111">Protect your data by performing a full database backup on every availability database</span></span>  
  
    -   <span data-ttu-id="d3ed4-112">Eseguire il comando DBCC CHECKDB su ogni database di disponibilità</span><span class="sxs-lookup"><span data-stu-id="d3ed4-112">Run DBCC CHECKDB on every availability database</span></span>  
  
-   <span data-ttu-id="d3ed4-113">Aggiornare sempre prima i nodi di replica secondaria remota, quindi quelli di replica secondaria locale e infine il nodo di replica primaria.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-113">Always upgrade/update the remote secondary replica nodes first, then local secondary replica nodes next, and the primary replica node last.</span></span>  
  
-   <span data-ttu-id="d3ed4-114">Non è possibile eseguire backup su un database in corso di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-114">Backups cannot occur on a database that is in the process of being upgraded.</span></span>  <span data-ttu-id="d3ed4-115">Prima di eseguire l'aggiornamento delle repliche secondarie, configurare la preferenza per i backup automatici in modo che vengano eseguiti solo sulla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-115">Prior to upgrading the secondary replicas, configure the automated backup preference to run backups only on the primary replica.</span></span>  <span data-ttu-id="d3ed4-116">Prima di aggiornare la replica primaria, modificare questa impostazione per l'esecuzione dei backup solo nelle repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-116">Prior to upgrading the primary replica, modify this setting to run backups only on the secondary replicas.</span></span>  
  
-   <span data-ttu-id="d3ed4-117">Per evitare failover accidentali del gruppo di disponibilità durante il processo di aggiornamento, prima di iniziare rimuovere il failover di disponibilità da tutte le repliche con commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-117">To prevent the availability group from unintended failovers during the upgrade/update process, remove availability failover from all synchronous-commit replicas before you begin.</span></span>  
  
-   <span data-ttu-id="d3ed4-118">Non aggiornare il nodo di replica primaria prima di aver effettuato il failover del gruppo di disponibilità a un nodo aggiornato con una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-118">Do not upgrade the primary replica node before failing over the availability group to an upgraded node with a secondary replica first.</span></span> <span data-ttu-id="d3ed4-119">In caso contrario, le applicazioni client potrebbero subire tempi di inattività prolungati durante l'aggiornamento sulla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-119">Otherwise, client applications may suffer extended downtime during the upgrade/update on the primary replica.</span></span>  
  
-   <span data-ttu-id="d3ed4-120">Effettuare sempre il failover del gruppo di disponibilità a un nodo di replica secondaria con commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-120">Always fail over the availability group to a synchronous-commit secondary replica node.</span></span> <span data-ttu-id="d3ed4-121">Se si effettua il failover a una replica secondaria con commit asincrono, si verificheranno perdite di dati nei database e lo spostamento dei dati verrà automaticamente sospeso finché non verrà ripreso manualmente.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-121">If you fail over to an asynchronous-commit secondary replica, the databases will suffer data loss, and data movement is automatically suspended until you manually resume data movement.</span></span>  
  
-   <span data-ttu-id="d3ed4-122">Non aggiornare il nodo di replica primaria prima di aver aggiornato tutti gli altri nodi di replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-122">Do not upgrade/update the primary replica node before upgrading/updating any other secondary replica nodes.</span></span> <span data-ttu-id="d3ed4-123">Tramite una replica primaria aggiornata non è più possibile recapitare log alle repliche secondarie non ancora aggiornate alla stessa versione.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-123">An upgraded primary replica can no longer ship logs to any secondary replica that has not yet been upgraded to the same version.</span></span> <span data-ttu-id="d3ed4-124">Se viene sospeso lo spostamento dei dati in una replica secondaria, il failover automatico per quest'ultima non può essere eseguito e nei database di disponibilità possono verificarsi perdite di dati.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-124">When data movement to a secondary replica is suspended, no automatic failover can occur for that replica, and your availability databases are vulnerable to data loss.</span></span>  
  
-   <span data-ttu-id="d3ed4-125">Prima di effettuare il failover di un gruppo di disponibilità, verificare che lo stato di sincronizzazione della destinazione di failover risulti essere SINCRONIZZATO.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-125">Before failing over an availability group, verify that the synchronization state of the failover target is SYNCHRONIZED.</span></span>  
  
## <a name="rolling-upgradeupdate-process"></a><span data-ttu-id="d3ed4-126">Processo di aggiornamento in sequenza</span><span class="sxs-lookup"><span data-stu-id="d3ed4-126">Rolling Upgrade/Update Process</span></span>  
 <span data-ttu-id="d3ed4-127">Il processo effettivo dipende da fattori quali la topologia di distribuzione dei gruppi di disponibilità e la modalità di commit di ogni replica.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-127">In practice, the exact process will depend on factors such as the deployment topology of your availability groups and the commit mode of each replica.</span></span> <span data-ttu-id="d3ed4-128">Nello scenario più semplice, l'aggiornamento in sequenza è articolato in un processo a più fasi che nella sua forma essenziale prevede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3ed4-128">But in the simplest scenario, a rolling upgrade/update is a multi-stage process that in its simplest form involves the following steps:</span></span>  
  
 <span data-ttu-id="d3ed4-129">![Aggiornamento del gruppo di disponibilità nello scenario di ripristino di emergenza a disponibilità elevata](../../media/alwaysonupgrade-ag-hadr.gif "Aggiornamento del gruppo di disponibilità nello scenario di ripristino di emergenza a disponibilità elevata")</span><span class="sxs-lookup"><span data-stu-id="d3ed4-129">![Availability Group Upgrade in HADR Scenario](../../media/alwaysonupgrade-ag-hadr.gif "Availability Group Upgrade in HADR Scenario")</span></span>  
  
1.  <span data-ttu-id="d3ed4-130">Rimuovere il failover automatico in tutte le repliche con commit sincrono</span><span class="sxs-lookup"><span data-stu-id="d3ed4-130">Remove automatic failover on all synchronous-commit replicas</span></span>  
  
2.  <span data-ttu-id="d3ed4-131">Aggiornare tutte le istanze del server remoto in cui vengono eseguite repliche secondarie con commit asincrono</span><span class="sxs-lookup"><span data-stu-id="d3ed4-131">Upgrade/update all remote server instances running asynchronous-commit secondary replicas</span></span>  
  
3.  <span data-ttu-id="d3ed4-132">Aggiornare tutte le istanze del server locale in cui non è attualmente in esecuzione la replica primaria</span><span class="sxs-lookup"><span data-stu-id="d3ed4-132">Upgrade/update the all local server instances that are not currently running the primary replica</span></span>  
  
4.  <span data-ttu-id="d3ed4-133">Effettuare manualmente il failover del gruppo di disponibilità a una replica secondaria con commit sincrono</span><span class="sxs-lookup"><span data-stu-id="d3ed4-133">Manually fail over the availability group to a synchronous-commit secondary replica</span></span>  
  
5.  <span data-ttu-id="d3ed4-134">Aggiornare l'istanza del server in cui, in precedenza, era ospitata la replica primaria</span><span class="sxs-lookup"><span data-stu-id="d3ed4-134">Upgrade/update the server instance that formerly hosted the primary replica</span></span>  
  
6.  <span data-ttu-id="d3ed4-135">Configurare i partner di failover automatico nel modo desiderato</span><span class="sxs-lookup"><span data-stu-id="d3ed4-135">Configure automatic failover partners as desired</span></span>  
  
 <span data-ttu-id="d3ed4-136">Se necessario, è possibile eseguire un ulteriore failover manuale per ripristinare la configurazione originale del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-136">If necessary, you can perform an extra manual failover to return the availability group to its original configuration.</span></span>  
  
## <a name="availability-group-with-one-remote-secondary-replica"></a><span data-ttu-id="d3ed4-137">Gruppo di disponibilità con una replica secondaria remota</span><span class="sxs-lookup"><span data-stu-id="d3ed4-137">Availability Group with One Remote Secondary Replica</span></span>  
 <span data-ttu-id="d3ed4-138">Se è stato distribuito un gruppo di disponibilità solo a fini di ripristino di emergenza, potrebbe essere necessario effettuarne il failover a una replica secondaria con commit asincrono.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-138">If you have deployed an availability group only for disaster recovery, you may need to fail over the availability group to an asynchronous-commit secondary replica.</span></span> <span data-ttu-id="d3ed4-139">Questo tipo di configurazione è illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="d3ed4-139">Such configuration is illustrated by the following figure:</span></span>  
  
 <span data-ttu-id="d3ed4-140">![Aggiornamento del gruppo di disponibilità nello scenario di ripristino di emergenza](../../media/agupgrade-ag-dr.gif "Aggiornamento del gruppo di disponibilità nello scenario di ripristino di emergenza")</span><span class="sxs-lookup"><span data-stu-id="d3ed4-140">![Availability Group Upgrade in DR Scenario](../../media/agupgrade-ag-dr.gif "Availability Group Upgrade in DR Scenario")</span></span>  
  
 <span data-ttu-id="d3ed4-141">In questo caso, è necessario effettuare il failover del gruppo di disponibilità a una replica secondaria con commit asincrono durante l'aggiornamento in sequenza.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-141">In this situation, you must fail over the availability group to the asynchronous-commit secondary replica during the rolling upgrade/update.</span></span> <span data-ttu-id="d3ed4-142">Per evitare perdite di dati, modificare la modalità di commit impostando il commit sincrono e attendere che venga completata la sincronizzazione della replica secondaria prima di effettuare il failover del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-142">To prevent data loss, change the commit mode to synchronous commit and wait for the secondary replica to be synchronized before you fail over the availability group.</span></span> <span data-ttu-id="d3ed4-143">Il processo di aggiornamento in sequenza può quindi avvenire come segue:</span><span class="sxs-lookup"><span data-stu-id="d3ed4-143">Therefore, the rolling upgrade/update process may look as follows:</span></span>  
  
1.  <span data-ttu-id="d3ed4-144">Aggiornare il server remoto</span><span class="sxs-lookup"><span data-stu-id="d3ed4-144">Upgrade/update the remote server</span></span>  
  
2.  <span data-ttu-id="d3ed4-145">Impostare la modalità di commit sincrono</span><span class="sxs-lookup"><span data-stu-id="d3ed4-145">Change the commit mode to synchronous commit</span></span>  
  
3.  <span data-ttu-id="d3ed4-146">Attendere che lo stato di sincronizzazione sia SINCRONIZZATO</span><span class="sxs-lookup"><span data-stu-id="d3ed4-146">Wait until synchronization state is SYNCHRONIZED</span></span>  
  
4.  <span data-ttu-id="d3ed4-147">Effettuare il failover del gruppo di disponibilità a un sito remoto</span><span class="sxs-lookup"><span data-stu-id="d3ed4-147">Fail over the availability group to the remote site</span></span>  
  
5.  <span data-ttu-id="d3ed4-148">Aggiornare il server locale (sito primario)</span><span class="sxs-lookup"><span data-stu-id="d3ed4-148">Upgrade/update the local (primary site) server</span></span>  
  
6.  <span data-ttu-id="d3ed4-149">Effettuare il failover del gruppo di disponibilità al sito primario</span><span class="sxs-lookup"><span data-stu-id="d3ed4-149">Fail over the availability group to the primary site</span></span>  
  
7.  <span data-ttu-id="d3ed4-150">Impostare la modalità di commit asincrono</span><span class="sxs-lookup"><span data-stu-id="d3ed4-150">Change the commit mode to asynchronous commit</span></span>  
  
 <span data-ttu-id="d3ed4-151">Poiché la modalità di commit sincrono non è consigliata per la sincronizzazione dei dati con un sito remoto, tramite le applicazioni client potrebbe essere rilevato un aumento immediato della latenza del database in seguito alla modifica dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-151">Since the synchronous-commit mode is not a recommended setting for data synchronization to a remote site, client applications may notice an immediate increase in database latency after the setting change.</span></span> <span data-ttu-id="d3ed4-152">Inoltre, l'esecuzione di un failover causerà la rimozione di tutti i messaggi di log non riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-152">Moreover, performing a failover will cause all unacknowledged log messages to be discarded.</span></span> <span data-ttu-id="d3ed4-153">La quantità di messaggi di log rimossi può essere notevole a causa dell'elevata latenza di rete tra i due siti, il che determina un numero elevato di errori delle transazioni con i client.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-153">The amount of discarded log messages can be quite large due to the high network latency between the two sites, causing clients to experience a high volume of transactional failure.</span></span> <span data-ttu-id="d3ed4-154">È possibile ridurre l'impatto per le applicazioni client nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d3ed4-154">You can minimize impact to client applications by doing the following:</span></span>  
  
-   <span data-ttu-id="d3ed4-155">Scegliere con attenzione una finestra di manutenzione nei periodi di minore traffico client</span><span class="sxs-lookup"><span data-stu-id="d3ed4-155">Carefully select a maintenance window during low client traffic</span></span>  
  
-   <span data-ttu-id="d3ed4-156">Durante l'aggiornamento di SQL Server nel sito primario, impostare di nuovo la modalità di commit asincrono, quindi ripristinare il commit sincrono una volta pronti a effettuare nuovamente il failover al sito primario</span><span class="sxs-lookup"><span data-stu-id="d3ed4-156">While upgrading/updating SQL Server on the primary site, change the availability mode back to asynchronous commit, then revert to synchronous commit when you are ready to fail over to the primary site again</span></span>  
  
## <a name="availability-group-with-failover-cluster-instance-nodes"></a><span data-ttu-id="d3ed4-157">Gruppo di disponibilità con nodi di istanze del cluster di failover</span><span class="sxs-lookup"><span data-stu-id="d3ed4-157">Availability Group with Failover Cluster Instance Nodes</span></span>  
 <span data-ttu-id="d3ed4-158">Se in un gruppo di disponibilità sono contenuti nodi di istanze del cluster di failover, è consigliabile aggiornare i nodi inattivi prima di quelli attivi.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-158">If an availability group contains failover cluster instance (FCI) nodes, you should upgrade/update the inactive nodes before you upgrade/update the active nodes.</span></span> <span data-ttu-id="d3ed4-159">Nella figura seguente è illustrato uno scenario comune di gruppi di disponibilità con istanze del cluster di failover per la disponibilità elevata locale e il commit asincrono tra le istanze stesse ai fini del ripristino di emergenza remoto ed è indicata la relativa sequenza di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-159">The figure below illustrates a common availability group scenario with FCIs for local high availability and asynchronous commit between the FCIs for remote disaster recovery, and the upgrade sequence.</span></span>  
  
 <span data-ttu-id="d3ed4-160">![Aggiornamento del gruppo di disponibilità con istanze del cluster di failover](../../media/agupgrade-ag-fci-dr.gif "Aggiornamento del gruppo di disponibilità con istanze del cluster di failover")</span><span class="sxs-lookup"><span data-stu-id="d3ed4-160">![Availability Group Upgrade with FCIs](../../media/agupgrade-ag-fci-dr.gif "Availability Group Upgrade with FCIs")</span></span>  
  
1.  <span data-ttu-id="d3ed4-161">Aggiornare REMOTE2</span><span class="sxs-lookup"><span data-stu-id="d3ed4-161">Upgrade/update REMOTE2</span></span>  
  
2.  <span data-ttu-id="d3ed4-162">Effettuare il failover dell'istanza FCI2 a REMOTE2</span><span class="sxs-lookup"><span data-stu-id="d3ed4-162">Fail over FCI2 to REMOTE2</span></span>  
  
3.  <span data-ttu-id="d3ed4-163">Aggiornare REMOTE1</span><span class="sxs-lookup"><span data-stu-id="d3ed4-163">Upgrade/update REMOTE1</span></span>  
  
4.  <span data-ttu-id="d3ed4-164">Aggiornare PRIMARY2</span><span class="sxs-lookup"><span data-stu-id="d3ed4-164">Upgrade/update PRIMARY2</span></span>  
  
5.  <span data-ttu-id="d3ed4-165">Effettuare il failover dell'istanza FCI1 a PRIMARY2</span><span class="sxs-lookup"><span data-stu-id="d3ed4-165">Fail over FCI1 to PRIMARY2</span></span>  
  
6.  <span data-ttu-id="d3ed4-166">Aggiornare PRIMARY1</span><span class="sxs-lookup"><span data-stu-id="d3ed4-166">Upgrade/update PRIMARY1</span></span>  
  
## <a name="upgradeupdate-sql-server-instances-with-multiple-availability-groups"></a><span data-ttu-id="d3ed4-167">Aggiornare le istanze di SQL Server con più gruppi di disponibilità</span><span class="sxs-lookup"><span data-stu-id="d3ed4-167">Upgrade/Update SQL Server Instances with Multiple Availability Groups</span></span>  
 <span data-ttu-id="d3ed4-168">Se si eseguono più gruppi di disponibilità con repliche primarie su nodi server distinti (configurazione Attiva/Attiva), il percorso di aggiornamento prevede più passaggi di failover allo scopo di preservare la disponibilità elevata durante il processo.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-168">If you are running multiple availability groups with primary replicas on separate server nodes (an Active/Active configuration), the upgrade/update path involves more failover steps to preserve high availability in the process.</span></span> <span data-ttu-id="d3ed4-169">Si supponga di disporre di tre gruppi di disponibilità in tre nodi server come illustrato nella tabella seguente e che tutte le repliche secondarie vengano eseguite in modalità di commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-169">Suppose you are running three availability groups on three server nodes as shown in the following table, and all secondary replicas are running in synchronous-commit mode.</span></span>  
  
|<span data-ttu-id="d3ed4-170">Gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="d3ed4-170">Availability Group</span></span>|<span data-ttu-id="d3ed4-171">Nodo1</span><span class="sxs-lookup"><span data-stu-id="d3ed4-171">Node1</span></span>|<span data-ttu-id="d3ed4-172">Nodo2</span><span class="sxs-lookup"><span data-stu-id="d3ed4-172">Node2</span></span>|<span data-ttu-id="d3ed4-173">Nodo3</span><span class="sxs-lookup"><span data-stu-id="d3ed4-173">Node3</span></span>|  
|------------------------|-----------|-----------|-----------|  
|<span data-ttu-id="d3ed4-174">AG1</span><span class="sxs-lookup"><span data-stu-id="d3ed4-174">AG1</span></span>|<span data-ttu-id="d3ed4-175">Primaria</span><span class="sxs-lookup"><span data-stu-id="d3ed4-175">Primary</span></span>|||  
|<span data-ttu-id="d3ed4-176">AG2</span><span class="sxs-lookup"><span data-stu-id="d3ed4-176">AG2</span></span>||<span data-ttu-id="d3ed4-177">Primaria</span><span class="sxs-lookup"><span data-stu-id="d3ed4-177">Primary</span></span>||  
|<span data-ttu-id="d3ed4-178">AG3</span><span class="sxs-lookup"><span data-stu-id="d3ed4-178">AG3</span></span>|||<span data-ttu-id="d3ed4-179">Primaria</span><span class="sxs-lookup"><span data-stu-id="d3ed4-179">Primary</span></span>|  
  
 <span data-ttu-id="d3ed4-180">In determinate situazioni potrebbe essere opportuno eseguire un aggiornamento in sequenza con bilanciamento del carico articolato come segue:</span><span class="sxs-lookup"><span data-stu-id="d3ed4-180">It may be appropriate in your situation to perform a load-balanced rolling upgrade/update in the following sequence:</span></span>  
  
1.  <span data-ttu-id="d3ed4-181">Effettuare il failover di AG2 a Nodo3 (per liberare Nodo2)</span><span class="sxs-lookup"><span data-stu-id="d3ed4-181">Fail over AG2 to Node3 (to free up Node2)</span></span>  
  
2.  <span data-ttu-id="d3ed4-182">Aggiornare Nodo2</span><span class="sxs-lookup"><span data-stu-id="d3ed4-182">Upgrade/update Node2</span></span>  
  
3.  <span data-ttu-id="d3ed4-183">Effettuare il failover di AG1 a Nodo2 (per liberare Nodo1)</span><span class="sxs-lookup"><span data-stu-id="d3ed4-183">Fail over AG1 to Node2 (to free up Node1)</span></span>  
  
4.  <span data-ttu-id="d3ed4-184">Aggiornare Nodo1</span><span class="sxs-lookup"><span data-stu-id="d3ed4-184">Upgrade/update Node1</span></span>  
  
5.  <span data-ttu-id="d3ed4-185">Effettuare il failover di AG2 e AG3 a Nodo1 (per liberare Nodo3)</span><span class="sxs-lookup"><span data-stu-id="d3ed4-185">Fail over both AG2 and AG3 to Node1 (to free up Node3)</span></span>  
  
6.  <span data-ttu-id="d3ed4-186">Aggiornare Nodo3</span><span class="sxs-lookup"><span data-stu-id="d3ed4-186">Upgrade/update Node3</span></span>  
  
7.  <span data-ttu-id="d3ed4-187">Effettuare il failover di AG3 a Nodo3</span><span class="sxs-lookup"><span data-stu-id="d3ed4-187">Fail over AG3 to Node3</span></span>  
  
 <span data-ttu-id="d3ed4-188">Questa sequenza di aggiornamento implica un tempo di inattività medio inferiore alla durata di due failover per ciascun gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-188">This upgrade/update sequence has an average downtime of less than two failovers per availability group.</span></span> <span data-ttu-id="d3ed4-189">La configurazione risultante è illustrata nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-189">The resulting configuration is shown in the table below.</span></span>  
  
|<span data-ttu-id="d3ed4-190">Gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="d3ed4-190">Availability Group</span></span>|<span data-ttu-id="d3ed4-191">Nodo1</span><span class="sxs-lookup"><span data-stu-id="d3ed4-191">Node1</span></span>|<span data-ttu-id="d3ed4-192">Nodo2</span><span class="sxs-lookup"><span data-stu-id="d3ed4-192">Node2</span></span>|<span data-ttu-id="d3ed4-193">Nodo3</span><span class="sxs-lookup"><span data-stu-id="d3ed4-193">Node3</span></span>|  
|------------------------|-----------|-----------|-----------|  
|<span data-ttu-id="d3ed4-194">AG1</span><span class="sxs-lookup"><span data-stu-id="d3ed4-194">AG1</span></span>||<span data-ttu-id="d3ed4-195">Primaria</span><span class="sxs-lookup"><span data-stu-id="d3ed4-195">Primary</span></span>||  
|<span data-ttu-id="d3ed4-196">AG2</span><span class="sxs-lookup"><span data-stu-id="d3ed4-196">AG2</span></span>|<span data-ttu-id="d3ed4-197">Primaria</span><span class="sxs-lookup"><span data-stu-id="d3ed4-197">Primary</span></span>|||  
|<span data-ttu-id="d3ed4-198">AG3</span><span class="sxs-lookup"><span data-stu-id="d3ed4-198">AG3</span></span>|||<span data-ttu-id="d3ed4-199">Primaria</span><span class="sxs-lookup"><span data-stu-id="d3ed4-199">Primary</span></span>|  
  
 <span data-ttu-id="d3ed4-200">Il percorso di aggiornamento e i tempi di inattività per le applicazioni client possono variare a seconda della specifica implementazione in uso.</span><span class="sxs-lookup"><span data-stu-id="d3ed4-200">Based on your specific implementation, your upgrade/update path may vary, and the downtime that client applications experience may vary as well.</span></span>  
  
  
