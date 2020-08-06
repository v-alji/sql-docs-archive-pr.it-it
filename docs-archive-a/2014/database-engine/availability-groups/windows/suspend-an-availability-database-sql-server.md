---
title: Sospendere un database di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.suspenddatamove.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], suspending a database
- Availability Groups [SQL Server], databases
ms.assetid: 86858982-6af1-4e80-9a93-87451f0d7ee9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49afe868a509f84160fc1ad154135e8e67f6900a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724968"
---
# <a name="suspend-an-availability-database-sql-server"></a><span data-ttu-id="42806-102">Sospendere un database di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42806-102">Suspend an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="42806-103">È possibile sospendere un database di disponibilità in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42806-103">You can suspend an availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="42806-104">Si noti che è necessario eseguire un comando di sospensione nell'istanza del server in cui viene ospitato il database da sospendere o riprendere.</span><span class="sxs-lookup"><span data-stu-id="42806-104">Note that a suspend command needs to be issued on the server instance that hosts the database to be suspended or resumed.</span></span>  
  
 <span data-ttu-id="42806-105">L'effetto del comando di sospensione dipende dalla scelta di sospendere un database primario o secondario, come segue:</span><span class="sxs-lookup"><span data-stu-id="42806-105">The effect of a suspend command depends on whether you suspend a secondary database or a primary database, as follows:</span></span>  
  
|<span data-ttu-id="42806-106">Database sospeso</span><span class="sxs-lookup"><span data-stu-id="42806-106">Suspended Database</span></span>|<span data-ttu-id="42806-107">Effetto del comando di sospensione</span><span class="sxs-lookup"><span data-stu-id="42806-107">Effect of Suspend Command</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="42806-108">Database secondario</span><span class="sxs-lookup"><span data-stu-id="42806-108">Secondary database</span></span>|<span data-ttu-id="42806-109">Viene sospeso solo il database secondario locale e il relativo stato di sincronizzazione diventa NOT SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="42806-109">Only the local secondary database is suspended and its synchronization state becomes NOT SYNCHRONIZING.</span></span> <span data-ttu-id="42806-110">Gli altri database secondari non sono influenzati.</span><span class="sxs-lookup"><span data-stu-id="42806-110">Other secondary databases are not affected.</span></span> <span data-ttu-id="42806-111">Nel database sospeso non vengono più eseguite la ricezione e l'applicazione di dati (record di log) e viene persa la sincronizzazione con il database primario.</span><span class="sxs-lookup"><span data-stu-id="42806-111">The suspended database stops receiving and applying data (log records) and begins to fall behind the primary database.</span></span> <span data-ttu-id="42806-112">Le connessioni esistenti nel database secondario leggibile rimangono utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="42806-112">Existing connections on the readable secondary remain usable.</span></span> <span data-ttu-id="42806-113">Non sono consentite nuove connessioni al database sospeso nel database secondario leggibile finché non viene ripreso lo spostamento di dati.</span><span class="sxs-lookup"><span data-stu-id="42806-113">New connections to the suspended database on the readable secondary are not allowed until data movement is resumed.</span></span><br /><br /> <span data-ttu-id="42806-114">Il database primario rimane disponibile.</span><span class="sxs-lookup"><span data-stu-id="42806-114">The primary database remains available.</span></span> <span data-ttu-id="42806-115">Se si sospende ogni database secondario corrispondente, il database primario viene eseguito senza mirroring.</span><span class="sxs-lookup"><span data-stu-id="42806-115">If you suspend each of the corresponding secondary databases, the primary database runs exposed.</span></span><br /><br /> <span data-ttu-id="42806-116">**\*\* Importante \*\*** Durante la fase di sospensione di un database secondario, nella coda di invio del database primario corrispondente verranno accumulati record del log delle transazioni non inviati.</span><span class="sxs-lookup"><span data-stu-id="42806-116">**\*\* Important \*\*** While a secondary database is suspended, the send queue of the corresponding primary database will accumulate unsent transaction log records.</span></span> <span data-ttu-id="42806-117">Tramite le connessioni alla replica secondaria vengono restituiti i dati disponibili quando lo spostamento di dati è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="42806-117">Connections to the secondary replica return data that was available at the time the data movement was suspended.</span></span>|  
|<span data-ttu-id="42806-118">Database primario</span><span class="sxs-lookup"><span data-stu-id="42806-118">Primary database</span></span>|<span data-ttu-id="42806-119">Nel database primario viene arrestato lo spostamento di dati a ogni database secondario connesso.</span><span class="sxs-lookup"><span data-stu-id="42806-119">The primary database stops data movement to every connected secondary database.</span></span> <span data-ttu-id="42806-120">Il database primario rimane in esecuzione, in modalità senza mirroring.</span><span class="sxs-lookup"><span data-stu-id="42806-120">The primary database continues running, in an exposed mode.</span></span> <span data-ttu-id="42806-121">Il database primario rimane disponibile ai client e le connessioni esistenti in un database secondario leggibile rimangono utilizzabili ed è possibile effettuare nuove connessioni.</span><span class="sxs-lookup"><span data-stu-id="42806-121">The primary database remains available to clients, and existing connections on a readable secondary remain usable and new connections can be made.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="42806-122">La sospensione di un database secondario AlwaysOn non incide direttamente sulla disponibilità del database primario.</span><span class="sxs-lookup"><span data-stu-id="42806-122">Suspending an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="42806-123">Tuttavia, la sospensione di un database secondario può avere un impatto sulle funzionalità di ridondanza e failover del database primario.</span><span class="sxs-lookup"><span data-stu-id="42806-123">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database.</span></span> <span data-ttu-id="42806-124">Questo comportamento è diverso rispetto al mirroring del database, in cui lo stato del mirroring risulta sospeso sia sul database mirror che sul database principale.</span><span class="sxs-lookup"><span data-stu-id="42806-124">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database.</span></span> <span data-ttu-id="42806-125">La sospensione di un database primario AlwaysOn comporta la sospensione dello spostamento di dati su tutti i database secondari corrispondenti, mentre le funzionalità di ridondanza e failover cessano per tale database finché il database primario non viene ripreso.</span><span class="sxs-lookup"><span data-stu-id="42806-125">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="42806-126">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="42806-126">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="42806-127">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="42806-127">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="42806-128">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="42806-128">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="42806-129">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="42806-129">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="42806-130">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="42806-130">Security</span></span>](#Security)  
  
-   <span data-ttu-id="42806-131">**Per sospendere un database tramite:**</span><span class="sxs-lookup"><span data-stu-id="42806-131">**To suspend a database, using:**</span></span>  
  
-   [<span data-ttu-id="42806-132">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="42806-132">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="42806-133">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42806-133">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="42806-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="42806-134">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="42806-135">**Completamento:** [Come evitare il riempimento del log delle transazioni](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="42806-135">**Follow up:** [Avoiding a Full Transaction Log](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="42806-136">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="42806-136">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="42806-137">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="42806-137">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="42806-138">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="42806-138">Limitations and Restrictions</span></span>  
 <span data-ttu-id="42806-139">Un comando SUSPEND viene restituito non appena è stato accettato dalla replica che ospita il database di destinazione, ma la sospensione effettiva del database avviene in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="42806-139">A SUSPEND command returns as soon as it has been accepted by the replica that hosts the target database, but actually suspending the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="42806-140">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="42806-140">Prerequisites</span></span>  
 <span data-ttu-id="42806-141">È necessario essere connessi all'istanza del server che ospita il database che si desidera sospendere.</span><span class="sxs-lookup"><span data-stu-id="42806-141">You must be connected to the server instance that hosts the database that you want to suspend.</span></span> <span data-ttu-id="42806-142">Per sospendere un database primario e i database secondari corrispondenti, connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="42806-142">To suspend a primary database and the corresponding secondary databases, connect to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="42806-143">Per sospendere un database secondario lasciando disponibile il database primario, connettersi alla replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="42806-143">To suspend a secondary database while leaving the primary database available, connect to the secondary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="42806-144">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="42806-144">Recommendations</span></span>  
 <span data-ttu-id="42806-145">Durante i colli di bottiglia, potrebbe essere utile sospendere brevemente uno o più database secondari per migliorare temporaneamente le prestazioni sulla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="42806-145">During bottlenecks, suspending one or more secondary databases briefly might be useful to improve performance temporarily on the primary replica.</span></span> <span data-ttu-id="42806-146">Finché un database secondario rimane sospeso, il log delle transazioni del database primario corrispondente non può essere troncato.</span><span class="sxs-lookup"><span data-stu-id="42806-146">As long as a secondary database remains suspended, the transaction log of the corresponding primary database cannot be truncated.</span></span> <span data-ttu-id="42806-147">Per questo motivo, i record del log si accumulano sul database primario.</span><span class="sxs-lookup"><span data-stu-id="42806-147">This causes log records to accumulate on the primary database.</span></span> <span data-ttu-id="42806-148">È pertanto consigliabile riprendere o rimuovere rapidamente un database secondario sospeso.</span><span class="sxs-lookup"><span data-stu-id="42806-148">Therefore, we recommend that you resume, or remove, a suspended secondary database quickly.</span></span> <span data-ttu-id="42806-149">Per altre informazioni, vedere [Completamento: Come evitare il riempimento del log delle transazioni](#FollowUp), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="42806-149">For more information, see [Follow up: Avoiding a Full Transaction Log](#FollowUp), later in this topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="42806-150">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="42806-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="42806-151">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="42806-151">Permissions</span></span>  
 <span data-ttu-id="42806-152">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="42806-152">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="42806-153">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="42806-153">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="42806-154">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="42806-154">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="42806-155">**Per sospendere un database**</span><span class="sxs-lookup"><span data-stu-id="42806-155">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="42806-156">In Esplora oggetti connettersi all'istanza del server che ospita la replica di disponibilità in cui si desidera sospendere un database ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="42806-156">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to suspend a database, and expand the server tree.</span></span> <span data-ttu-id="42806-157">Per altre informazioni, vedere la sessione [Prerequisiti](#Prerequisites)più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="42806-157">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="42806-158">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="42806-158">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="42806-159">Espandere il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="42806-159">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="42806-160">Espandere il nodo **Database di disponibilità** , fare clic con il pulsante destro del mouse sul database e scegliere **Sospendi spostamento dati**.</span><span class="sxs-lookup"><span data-stu-id="42806-160">Expand the **Availability Databases** node, right-click the database, and click **Suspend Data Movement**.</span></span>  
  
5.  <span data-ttu-id="42806-161">Nella finestra di dialogo **Sospendi spostamento dati** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="42806-161">In the **Suspend Data Movement** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="42806-162">In Esplora oggetti il database sospeso viene contrassegnato con l'icona di un indicatore di pausa.</span><span class="sxs-lookup"><span data-stu-id="42806-162">Object Explorer indicates that the database is suspended by changing  the database icon to display a pause indicator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42806-163">Per sospendere database aggiuntivi in questo percorso di replica, ripetere i passaggi 4 e 5 per ogni database.</span><span class="sxs-lookup"><span data-stu-id="42806-163">To suspend additional databases on this replica location, repeat steps 4 and 5  for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="42806-164">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42806-164">Using Transact-SQL</span></span>  
 <span data-ttu-id="42806-165">**Per sospendere un database**</span><span class="sxs-lookup"><span data-stu-id="42806-165">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="42806-166">Connettersi all'istanza del server che ospita la replica di cui si desidera sospendere il database.</span><span class="sxs-lookup"><span data-stu-id="42806-166">Connect to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="42806-167">Per altre informazioni, vedere la sessione [Prerequisiti](#Prerequisites)più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="42806-167">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="42806-168">Sospendere il database usando l'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)seguente:</span><span class="sxs-lookup"><span data-stu-id="42806-168">Suspend the database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="42806-169">ALTER DATABASE *database_name* SET HADR Suspend</span><span class="sxs-lookup"><span data-stu-id="42806-169">ALTER DATABASE *database_name* SET HADR SUSPEND</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="42806-170">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="42806-170">Using PowerShell</span></span>  
 <span data-ttu-id="42806-171">**Per sospendere un database**</span><span class="sxs-lookup"><span data-stu-id="42806-171">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="42806-172">Spostarsi sulla directory (`cd`) dell'istanza del server che ospita la replica di cui si desidera sospendere il database.</span><span class="sxs-lookup"><span data-stu-id="42806-172">Change directory (`cd`) to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="42806-173">Per altre informazioni, vedere la sessione [Prerequisiti](#Prerequisites)più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="42806-173">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="42806-174">Utilizzare il cmdlet `Suspend-SqlAvailabilityDatabase` per sospendere il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="42806-174">Use the `Suspend-SqlAvailabilityDatabase` cmdlet to suspend the availability group.</span></span>  
  
     <span data-ttu-id="42806-175">Ad esempio, il seguente comando sospende la sincronizzazione dati per il database di disponibilità `MyDb3` nel gruppo di disponibilità `MyAg` nell'istanza del server denominata `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="42806-175">For example, the following command suspends data synchronization for the availability database `MyDb3` in the availability group `MyAg` on the server instance named `Computer\Instance`.</span></span>  
  
    ```powershell
    Suspend-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="42806-176">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42806-176">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="42806-177">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="42806-177">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="42806-178">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="42806-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="42806-179">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="42806-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-avoiding-a-full-transaction-log"></a><a name="FollowUp"></a> <span data-ttu-id="42806-180">Completamento: Come evitare il riempimento del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="42806-180">Follow Up: Avoiding a Full Transaction Log</span></span>  
 <span data-ttu-id="42806-181">In genere, quando su un database viene eseguito un checkpoint automatico, il relativo log delle transazioni viene troncato in corrispondenza di tale checkpoint dopo il successivo backup del log.</span><span class="sxs-lookup"><span data-stu-id="42806-181">Normally, when an automatic checkpoint is performed on a database, its transaction log is truncated to that checkpoint after the next log backup.</span></span> <span data-ttu-id="42806-182">Tuttavia, quando un database secondario viene sospeso, tutti i record del log correnti rimangono attivi sul database primario.</span><span class="sxs-lookup"><span data-stu-id="42806-182">However, while a secondary database is suspended, all of the current log records remain active on the primary database.</span></span> <span data-ttu-id="42806-183">Se il log delle transazioni si riempie, perché raggiunge le dimensioni massime o l'istanza del server esaurisce lo spazio, il database non può eseguire ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="42806-183">If the transaction log fills up (either because it reaches its maximum size or the server instance runs out of space), the database cannot perform any more updates.</span></span>  
  
 <span data-ttu-id="42806-184">Per evitare il problema, effettuare una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42806-184">To avoid this problem, you should do one of the following:</span></span>  
  
-   <span data-ttu-id="42806-185">Aggiungere ulteriore spazio di log per il database primario.</span><span class="sxs-lookup"><span data-stu-id="42806-185">Add more log space for the primary database.</span></span>  
  
-   <span data-ttu-id="42806-186">Riprendere il database secondario prima che il log si riempia.</span><span class="sxs-lookup"><span data-stu-id="42806-186">Resume the secondary database before the log fills up.</span></span> <span data-ttu-id="42806-187">Per ulteriori informazioni, vedere [Riprendere un database di disponibilità &#40;SQL Server&#41;](resume-an-availability-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42806-187">For more information, see [Resume an Availability Database &#40;SQL Server&#41;](resume-an-availability-database-sql-server.md).</span></span>  
  
-   <span data-ttu-id="42806-188">Rimuovere il database secondario.</span><span class="sxs-lookup"><span data-stu-id="42806-188">Remove the secondary database.</span></span> <span data-ttu-id="42806-189">Per altre informazioni, vedere [Rimuovere un database secondario da un gruppo di disponibilità &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42806-189">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="42806-190">**Per risolvere i problemi di un log delle transazioni pieno**</span><span class="sxs-lookup"><span data-stu-id="42806-190">**To troubleshoot a full transaction log**</span></span>  
  
-   [<span data-ttu-id="42806-191">Risolvere i problemi relativi a un log delle transazioni completo &#40;Errore di SQL Server 9002&#41;</span><span class="sxs-lookup"><span data-stu-id="42806-191">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../../../relational-databases/logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="42806-192">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="42806-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="42806-193">Riprendere un database di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="42806-193">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="42806-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42806-194">See Also</span></span>  
 <span data-ttu-id="42806-195">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42806-195">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="42806-196">Riprendere un database di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="42806-196">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
