---
title: Usare il dashboard AlwaysOn (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
- Availability Groups [SQL Server], dashboard
ms.assetid: c9ba2589-139e-42bc-99e1-94546717c64d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4ce0072bcd6642dcb4f3ac63e04c98786bd550e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626299"
---
# <a name="use-the-alwayson-dashboard-sql-server-management-studio"></a><span data-ttu-id="6d099-102">Utilizzare il Dashboard AlwaysOn (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6d099-102">Use the AlwaysOn Dashboard (SQL Server Management Studio)</span></span>
  <span data-ttu-id="6d099-103">Gli amministratori del database utilizzano il dashboard AlwaysOn per ottenere una vista immediata dell'integrità di un gruppo di disponibilità AlwaysOn e delle relative repliche di disponibilità e database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d099-103">Database administrators use the AlwaysOn Dashboard to obtains an at-a-glance view the health of an AlwaysOn availability group and its availability replicas and databases in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="6d099-104">Alcuni degli utilizzi tipici del dashboard AlwaysOn sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d099-104">Some of the typical uses for the AlwaysOn Dashboard are:</span></span>  
  
-   <span data-ttu-id="6d099-105">Scelta di una replica per un failover manuale.</span><span class="sxs-lookup"><span data-stu-id="6d099-105">Choosing a replica for a manual failover.</span></span>  
  
-   <span data-ttu-id="6d099-106">Stima della perdita di dati in caso di failover forzato.</span><span class="sxs-lookup"><span data-stu-id="6d099-106">Estimating data loss if you force failover.</span></span>  
  
-   <span data-ttu-id="6d099-107">Valutazione delle prestazioni della sincronizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="6d099-107">Evaluating data-synchronization performance.</span></span>  
  
-   <span data-ttu-id="6d099-108">Valutazione dell'impatto sulle prestazioni di una replica secondaria con commit sincrono</span><span class="sxs-lookup"><span data-stu-id="6d099-108">Evaluating the performance impact of a synchronous-commit secondary replica</span></span>  
  
 <span data-ttu-id="6d099-109">Il dashboard AlwaysOn fornisce indicatori delle prestazioni e stati dei gruppi di disponibilità principali che facilitano le decisioni operative relative alla disponibilità elevata utilizzando i tipi di informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6d099-109">The AlwaysOn Dashboard provides key availability group states and performance indicators allowing you to easily make high availability operational decisions using the following types of information.</span></span>  
  
-   <span data-ttu-id="6d099-110">Stato di rollup della replica</span><span class="sxs-lookup"><span data-stu-id="6d099-110">Replica roll-up state</span></span>  
  
-   <span data-ttu-id="6d099-111">Modalità e stato di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="6d099-111">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="6d099-112">Perdita di dati stimata</span><span class="sxs-lookup"><span data-stu-id="6d099-112">Estimate Data Loss</span></span>  
  
-   <span data-ttu-id="6d099-113">Tempo di recupero stimato (ripetere aggiornamento)</span><span class="sxs-lookup"><span data-stu-id="6d099-113">Estimated Recovery Time (redo catch up)</span></span>  
  
-   <span data-ttu-id="6d099-114">Dettagli della replica di database</span><span class="sxs-lookup"><span data-stu-id="6d099-114">Database Replica details</span></span>  
  
-   <span data-ttu-id="6d099-115">Modalità e stato di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="6d099-115">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="6d099-116">Tempo per il ripristino del log</span><span class="sxs-lookup"><span data-stu-id="6d099-116">Time to restore log</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6d099-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6d099-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6d099-118">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6d099-118">Prerequisites</span></span>  
 <span data-ttu-id="6d099-119">È necessario essere connessi all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (istanza del server) che ospita la replica primaria o una replica secondaria di un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="6d099-119">You must be connected to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (server instance) that hosts either the primary replica or a secondary replica of an availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6d099-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6d099-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6d099-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6d099-121">Permissions</span></span>  
 <span data-ttu-id="6d099-122">È necessario disporre delle autorizzazioni CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="6d099-122">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="to-start-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="6d099-123">Per avviare il dashboard AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="6d099-123">To start the AlwaysOn Dashboard</span></span>  
  
1.  <span data-ttu-id="6d099-124">In Esplora oggetti connettersi all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in cui si desidera eseguire il dashboard AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="6d099-124">In Object Explorer, connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on which you want to run the AlwaysOn Dashboard.</span></span>  
  
2.  <span data-ttu-id="6d099-125">Espandere il nodo **Disponibilità elevata AlwaysOn** , fare clic con il pulsante destro del mouse sul nodo **Gruppi di disponibilità** , quindi fare clic su **Mostra dashboard**.</span><span class="sxs-lookup"><span data-stu-id="6d099-125">Expand the **AlwaysOn High Availability** node, right-click the **Availability Groups** node, and then click **Show Dashboard**.</span></span>  
  
###  <a name="to-change-alwayson-dashboard-options"></a><a name="DashboardOptions"></a><span data-ttu-id="6d099-126">Per modificare le opzioni del dashboard AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="6d099-126">To Change AlwaysOn Dashboard Options</span></span>  
 <span data-ttu-id="6d099-127">È possibile usare la finestra di dialogo [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Opzioni** per configurare il comportamento del dashboard AlwaysOn di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per l'aggiornamento automatico e l'abilitazione di criteri AlwaysOn definiti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6d099-127">You can use the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Options** dialog box to configure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn Dashboard behavior for automatic refreshing and enabling an auto-defined AlwaysOn policy.</span></span>  
  
1.  <span data-ttu-id="6d099-128">Dal menu **Strumenti** scegliere **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="6d099-128">From the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="6d099-129">Per aggiornare automaticamente il dashboard, nella finestra di dialogo **Opzioni** selezionare **Abilita aggiornamento automatico**, immettere l'intervallo di aggiornamento in secondi, quindi immettere per quante volte si desidera tentare di stabilire la connessione.</span><span class="sxs-lookup"><span data-stu-id="6d099-129">To automatically refresh the dashboard, in the **Options** dialog box, select **Turn on automatic refresh**, enter the refresh interval in seconds, and then enter the number of times you want to retry the connection.</span></span>  
  
3.  <span data-ttu-id="6d099-130">Per abilitare criteri definiti dall'utente, selezionare **Abilita criteri AlwaysOn definiti dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="6d099-130">To enable a user-defined policy, select **Enable user-defined AlwaysOn policy**.</span></span>  
  
##  <a name="availability-group-summary"></a><a name="AvGroupsView"></a><span data-ttu-id="6d099-131">Riepilogo gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="6d099-131">Availability Group Summary</span></span>  
 <span data-ttu-id="6d099-132">Nella schermata del gruppo di disponibilità viene visualizzata una riga di riepilogo per ogni gruppo di disponibilità per il quale l'istanza del server connesso ospita una replica.</span><span class="sxs-lookup"><span data-stu-id="6d099-132">The availability group screen displays a summary line for each availability group for which the connected server instance hosts a replica.</span></span> <span data-ttu-id="6d099-133">In questo riquadro sono visualizzate le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d099-133">This pane displays the following columns.</span></span>  
  
 <span data-ttu-id="6d099-134">**Nome gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="6d099-134">**Availability Group Name**</span></span>  
 <span data-ttu-id="6d099-135">Nome di un gruppo di disponibilità per il quale l'istanza del server connesso ospita una replica.</span><span class="sxs-lookup"><span data-stu-id="6d099-135">The name of an availability group for which the connected server instance hosts a replica.</span></span>  
  
 <span data-ttu-id="6d099-136">**Istanza primaria**</span><span class="sxs-lookup"><span data-stu-id="6d099-136">**Primary Instance**</span></span>  
 <span data-ttu-id="6d099-137">Nome dell'istanza del server che ospita la replica primaria del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="6d099-137">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="6d099-138">**Modalità di failover**</span><span class="sxs-lookup"><span data-stu-id="6d099-138">**Failover Mode**</span></span>  
 <span data-ttu-id="6d099-139">Visualizza la modalità di failover per cui è configurata la replica.</span><span class="sxs-lookup"><span data-stu-id="6d099-139">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="6d099-140">I possibili valori per le modalità di failover sono:</span><span class="sxs-lookup"><span data-stu-id="6d099-140">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="6d099-141">**Automatico**.</span><span class="sxs-lookup"><span data-stu-id="6d099-141">**Automatic**.</span></span> <span data-ttu-id="6d099-142">Indica che una o più repliche sono in modalità di failover automatico.</span><span class="sxs-lookup"><span data-stu-id="6d099-142">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="6d099-143">**Manuale**.</span><span class="sxs-lookup"><span data-stu-id="6d099-143">**Manual**.</span></span> <span data-ttu-id="6d099-144">Indica che non vi sono repliche in modalità di failover automatico.</span><span class="sxs-lookup"><span data-stu-id="6d099-144">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="6d099-145">**Problemi**</span><span class="sxs-lookup"><span data-stu-id="6d099-145">**Issues**</span></span>  
 <span data-ttu-id="6d099-146">Fare clic sul collegamento **Problemi** per aprire la documentazione di risoluzione dei problemi relativa a un determinato problema.</span><span class="sxs-lookup"><span data-stu-id="6d099-146">Click the **Issues** link to open troubleshooting documentation for a given issue.</span></span> <span data-ttu-id="6d099-147">Per un elenco di tutti i problemi relativi ai criteri AlwaysOn, vedere [criteri AlwaysOn per problemi operativi con gruppi di disponibilità AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="6d099-147">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="6d099-148">Fare clic sulle intestazioni di colonna per ordinare le informazioni sul gruppo di disponibilità in base al nome del gruppo di disponibilità, all'istanza primaria, alla modalità di failover o al problema.</span><span class="sxs-lookup"><span data-stu-id="6d099-148">Click the column headings to sort the availability group information by the name of the availability group, primary instance, failover mode, or Issue.</span></span>  
  
##  <a name="availability-group-details"></a><a name="AvGroupDetails"></a><span data-ttu-id="6d099-149">Dettagli del gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="6d099-149">Availability Group Details</span></span>  
 <span data-ttu-id="6d099-150">Le informazioni dettagliate riportate di seguito vengono visualizzate per il gruppo di disponibilità selezionato nello schermata di riepilogo:</span><span class="sxs-lookup"><span data-stu-id="6d099-150">The following detail information is displayed for the availability group that you select from the summary screen:</span></span>  
  
 <span data-ttu-id="6d099-151">**Stato gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="6d099-151">**Availability group state**</span></span>  
 <span data-ttu-id="6d099-152">Visualizza lo stato di integrità del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="6d099-152">Displays the state of health for the availability group.</span></span>  
  
 <span data-ttu-id="6d099-153">**Primary instance**</span><span class="sxs-lookup"><span data-stu-id="6d099-153">**Primary instance**</span></span>  
 <span data-ttu-id="6d099-154">Nome dell'istanza del server che ospita la replica primaria del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="6d099-154">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="6d099-155">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="6d099-155">**Failover mode**</span></span>  
 <span data-ttu-id="6d099-156">Visualizza la modalità di failover per cui è configurata la replica.</span><span class="sxs-lookup"><span data-stu-id="6d099-156">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="6d099-157">I possibili valori per le modalità di failover sono:</span><span class="sxs-lookup"><span data-stu-id="6d099-157">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="6d099-158">**Automatico**.</span><span class="sxs-lookup"><span data-stu-id="6d099-158">**Automatic**.</span></span> <span data-ttu-id="6d099-159">Indica che una o più repliche sono in modalità di failover automatico.</span><span class="sxs-lookup"><span data-stu-id="6d099-159">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="6d099-160">**Manuale**.</span><span class="sxs-lookup"><span data-stu-id="6d099-160">**Manual**.</span></span> <span data-ttu-id="6d099-161">Indica che non vi sono repliche in modalità di failover automatico.</span><span class="sxs-lookup"><span data-stu-id="6d099-161">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="6d099-162">**Stato cluster**</span><span class="sxs-lookup"><span data-stu-id="6d099-162">**Cluster state**</span></span>  
 <span data-ttu-id="6d099-163">Nome e stato del cluster in cui l'istanza del server connesso e del gruppo di disponibilità è un nodo membro.</span><span class="sxs-lookup"><span data-stu-id="6d099-163">Name and state of the cluster where the instance of the connected server and the availability group is a member node.</span></span>  
  
##  <a name="availability-replica-details"></a><a name="AvReplicaDetails"></a> <span data-ttu-id="6d099-164">Dettagli replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="6d099-164">Availability Replica Details</span></span>  
 <span data-ttu-id="6d099-165">Nel riquadro **Replica di disponibilità** vengono visualizzate le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d099-165">The **Availability replica** pane displays the following columns:</span></span>  
  
 <span data-ttu-id="6d099-166">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6d099-166">**Name**</span></span>  
 <span data-ttu-id="6d099-167">Nome dell'istanza del server che ospita la replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="6d099-167">The name of the server instance that hosts the availability replica.</span></span> <span data-ttu-id="6d099-168">Questa colonna viene visualizzata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-168">This column is shown by default.</span></span>  
  
 <span data-ttu-id="6d099-169">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="6d099-169">**Role**</span></span>  
 <span data-ttu-id="6d099-170">Indica il ruolo corrente della replica di disponibilità, ovvero **Primario** o **Secondario**.</span><span class="sxs-lookup"><span data-stu-id="6d099-170">Indicates the current role of the availability replica, either **Primary** or **Secondary**.</span></span> <span data-ttu-id="6d099-171">Per informazioni sui ruoli di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], vedere [Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6d099-171">For information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] roles, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span> <span data-ttu-id="6d099-172">Questa colonna viene visualizzata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-172">This column is shown by default.</span></span>  
  
 <span data-ttu-id="6d099-173">**Modalità di failover**</span><span class="sxs-lookup"><span data-stu-id="6d099-173">**Failover Mode**</span></span>  
 <span data-ttu-id="6d099-174">Visualizza la modalità di failover per cui è configurata la replica.</span><span class="sxs-lookup"><span data-stu-id="6d099-174">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="6d099-175">I possibili valori per le modalità di failover sono:</span><span class="sxs-lookup"><span data-stu-id="6d099-175">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="6d099-176">**Automatico**.</span><span class="sxs-lookup"><span data-stu-id="6d099-176">**Automatic**.</span></span> <span data-ttu-id="6d099-177">Indica che una o più repliche sono in modalità di failover automatico.</span><span class="sxs-lookup"><span data-stu-id="6d099-177">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="6d099-178">**Manuale**.</span><span class="sxs-lookup"><span data-stu-id="6d099-178">**Manual**.</span></span> <span data-ttu-id="6d099-179">Indica che non vi sono repliche in modalità di failover automatico.</span><span class="sxs-lookup"><span data-stu-id="6d099-179">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="6d099-180">**Stato di sincronizzazione**</span><span class="sxs-lookup"><span data-stu-id="6d099-180">**Synchronization State**</span></span>  
 <span data-ttu-id="6d099-181">Indica se una replica secondaria è attualmente sincronizzata con la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-181">Indicates whether a secondary replica is currently synchronized with primary replica.</span></span> <span data-ttu-id="6d099-182">Questa colonna viene visualizzata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-182">This column is shown by default.</span></span> <span data-ttu-id="6d099-183">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="6d099-183">The possible values are:</span></span>  
  
-   <span data-ttu-id="6d099-184">**Non sincronizzato**.</span><span class="sxs-lookup"><span data-stu-id="6d099-184">**Not Synchronized**.</span></span> <span data-ttu-id="6d099-185">Uno o più database nella replica non sono sincronizzati o non ne è ancora stato creato un join al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="6d099-185">One or more databases in the replica are not synchronized or have not yet been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="6d099-186">**Sincronizzazione**in corso.</span><span class="sxs-lookup"><span data-stu-id="6d099-186">**Synchronizing**.</span></span> <span data-ttu-id="6d099-187">Uno o più database nella replica vengono sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="6d099-187">One or more databases in the replica are being synchronized.</span></span>  
  
-   <span data-ttu-id="6d099-188">**Sincronizzazione**completata.</span><span class="sxs-lookup"><span data-stu-id="6d099-188">**Synchronized**.</span></span> <span data-ttu-id="6d099-189">Tutti i database nella replica secondaria sono sincronizzati con i database primari corrispondenti nella replica primaria corrente o nell'ultima replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-189">All databases in the secondary replica are synchronized with the corresponding primary databases on the current primary replica, if any, or on the last primary replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6d099-190">Nella modalità prestazioni, il database non si trova mai nello stato sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="6d099-190">In performance mode, the database is never in the synchronized state.</span></span>  
  
-   <span data-ttu-id="6d099-191">**Valore null**.</span><span class="sxs-lookup"><span data-stu-id="6d099-191">**NULL**.</span></span> <span data-ttu-id="6d099-192">Stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6d099-192">Unknown state.</span></span> <span data-ttu-id="6d099-193">Si ottiene questo valore quando l'istanza del server locale non è in grado di comunicare con il cluster di failover WSFC, ovvero il nodo locale non fa parte del quorum WSFC.</span><span class="sxs-lookup"><span data-stu-id="6d099-193">This value occurs when the local server instance cannot communicate with the WSFC failover cluster (that is the local node is not part of WSFC quorum).</span></span>  
  
 <span data-ttu-id="6d099-194">**Problemi**</span><span class="sxs-lookup"><span data-stu-id="6d099-194">**Issues**</span></span>  
 <span data-ttu-id="6d099-195">Indica il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="6d099-195">Lists the issue name.</span></span> <span data-ttu-id="6d099-196">Questo valore è visualizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-196">This value is shown by default.</span></span> <span data-ttu-id="6d099-197">Per un elenco di tutti i problemi relativi ai criteri AlwaysOn, vedere [criteri AlwaysOn per problemi operativi con gruppi di disponibilità AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="6d099-197">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="6d099-198">**Modalità di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="6d099-198">**Availability Mode**</span></span>  
 <span data-ttu-id="6d099-199">Indica la proprietà della replica impostata separatamente per ogni replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="6d099-199">Indicates the replica property that you set separately for each availability replica.</span></span> <span data-ttu-id="6d099-200">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-200">This value is hidden by default.</span></span> <span data-ttu-id="6d099-201">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="6d099-201">The possible values are:</span></span>  
  
-   <span data-ttu-id="6d099-202">**Asincrono**.</span><span class="sxs-lookup"><span data-stu-id="6d099-202">**Asynchronous**.</span></span> <span data-ttu-id="6d099-203">La replica secondaria non è mai sincronizzata con la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-203">The secondary replica never becomes synchronized with the primary replica.</span></span>  
  
-   <span data-ttu-id="6d099-204">**Sincrono**.</span><span class="sxs-lookup"><span data-stu-id="6d099-204">**Synchronous**.</span></span> <span data-ttu-id="6d099-205">Quando si esegue l'aggiornamento al database primario, un database secondario entra in questo stato e rimane aggiornato finché continua la sincronizzazione dati per il database.</span><span class="sxs-lookup"><span data-stu-id="6d099-205">When catching up to the primary database, a secondary database enters this state, and it remains caught up as long as data synchronization continues for the database.</span></span>  
  
 <span data-ttu-id="6d099-206">**Modalità connessione primaria**</span><span class="sxs-lookup"><span data-stu-id="6d099-206">**Primary Connection Mode**</span></span>  
 <span data-ttu-id="6d099-207">Indica la modalità utilizzata per connettersi alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-207">Indicates the mode that is used to connect to the primary replica.</span></span>  <span data-ttu-id="6d099-208">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-208">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-209">**Modalità connessione secondaria**</span><span class="sxs-lookup"><span data-stu-id="6d099-209">**Secondary Connection Mode**</span></span>  
 <span data-ttu-id="6d099-210">Indica la modalità utilizzata per connettersi alla replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-210">Indicates the mode that is used to connect to the secondary replica.</span></span>  <span data-ttu-id="6d099-211">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-211">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-212">**Stato connessione**</span><span class="sxs-lookup"><span data-stu-id="6d099-212">**Connection State**</span></span>  
 <span data-ttu-id="6d099-213">Indica se una replica secondaria è attualmente connessa alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-213">Indicates whether a secondary replica is currently connected to the primary replica.</span></span> <span data-ttu-id="6d099-214">Questa colonna è nascosta per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-214">This column is hidden by default.</span></span> <span data-ttu-id="6d099-215">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="6d099-215">The possible values are:</span></span>  
  
-   <span data-ttu-id="6d099-216">**Disconnesso**.</span><span class="sxs-lookup"><span data-stu-id="6d099-216">**Disconnected**.</span></span> <span data-ttu-id="6d099-217">Per una replica di disponibilità remota, indica che è disconnessa dalla replica di disponibilità locale.</span><span class="sxs-lookup"><span data-stu-id="6d099-217">For a remote availability replica, indicates that it is disconnected from the local availability replica.</span></span> <span data-ttu-id="6d099-218">La risposta della replica locale allo stato Disconnesso dipende dal relativo ruolo:</span><span class="sxs-lookup"><span data-stu-id="6d099-218">The response of the local replica to the Disconnected state depends on its role, as follows:</span></span>  
  
    -   <span data-ttu-id="6d099-219">Sulla replica primaria, se una replica secondaria è disconnessa, i database secondari sono contrassegnati come **Non sincronizzato** sulla replica primaria e la replica primaria attende che la replica secondaria venga riconnessa.</span><span class="sxs-lookup"><span data-stu-id="6d099-219">On the primary replica, if a secondary replica is disconnected, the secondary databases are marked as **Not Synchronized** on the primary replica, and the primary replica waits for the secondary to reconnect.</span></span>  
  
    -   <span data-ttu-id="6d099-220">Sulla replica secondaria, dopo avere rilevato che è disconnessa, tenta di riconnettersi alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-220">On the secondary replica, upon detecting that it is disconnected, the secondary replica attempts to reconnect to the primary replica.</span></span>  
  
-   <span data-ttu-id="6d099-221">**Connessione interconnessa**.</span><span class="sxs-lookup"><span data-stu-id="6d099-221">**Connected**.</span></span> <span data-ttu-id="6d099-222">Una replica di disponibilità remota attualmente connessa alla replica locale.</span><span class="sxs-lookup"><span data-stu-id="6d099-222">A remote availability replica that is currently connected to the local replica.</span></span>  
  
 <span data-ttu-id="6d099-223">**Stato operativo**</span><span class="sxs-lookup"><span data-stu-id="6d099-223">**Operational State**</span></span>  
 <span data-ttu-id="6d099-224">Indica lo stato operativo corrente della replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-224">Indicates the current operational state of the secondary replica.</span></span> <span data-ttu-id="6d099-225">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-225">This value is hidden by default.</span></span> <span data-ttu-id="6d099-226">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="6d099-226">The possible values are:</span></span>  
  
 <span data-ttu-id="6d099-227">**0**. Failover in sospeso</span><span class="sxs-lookup"><span data-stu-id="6d099-227">**0**. Pending failover</span></span>  
  
 <span data-ttu-id="6d099-228">**1**. In sospeso</span><span class="sxs-lookup"><span data-stu-id="6d099-228">**1**. Pending</span></span>  
  
 <span data-ttu-id="6d099-229">**2**. Online</span><span class="sxs-lookup"><span data-stu-id="6d099-229">**2**. Online</span></span>  
  
 <span data-ttu-id="6d099-230">**3**. Offline</span><span class="sxs-lookup"><span data-stu-id="6d099-230">**3**. Offline</span></span>  
  
 <span data-ttu-id="6d099-231">**4**. Non riuscito</span><span class="sxs-lookup"><span data-stu-id="6d099-231">**4**. Failed</span></span>  
  
 <span data-ttu-id="6d099-232">**5**. Errore, nessun quorum</span><span class="sxs-lookup"><span data-stu-id="6d099-232">**5**. Failed, no quorum</span></span>  
  
 <span data-ttu-id="6d099-233">**Valore null**.</span><span class="sxs-lookup"><span data-stu-id="6d099-233">**NULL**.</span></span> <span data-ttu-id="6d099-234">La replica non è locale.</span><span class="sxs-lookup"><span data-stu-id="6d099-234">Replica is not local</span></span>  
  
 <span data-ttu-id="6d099-235">**Ultimo errore di connessione.**</span><span class="sxs-lookup"><span data-stu-id="6d099-235">**Last Connection Error No.**</span></span>  
 <span data-ttu-id="6d099-236">Numero dell'ultimo errore di connessione.</span><span class="sxs-lookup"><span data-stu-id="6d099-236">Number of the last connection error.</span></span>  <span data-ttu-id="6d099-237">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-237">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-238">**Descrizione ultimo errore di connessione**</span><span class="sxs-lookup"><span data-stu-id="6d099-238">**Last Connection Error Description**</span></span>  
 <span data-ttu-id="6d099-239">Descrizione dell'ultimo errore di connessione.</span><span class="sxs-lookup"><span data-stu-id="6d099-239">Description of the last connection error.</span></span>  <span data-ttu-id="6d099-240">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-240">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-241">**Ora dell'ultimo errore di connessione**</span><span class="sxs-lookup"><span data-stu-id="6d099-241">**Last Connection Error Timestamp**</span></span>  
 <span data-ttu-id="6d099-242">Timestamp dell'ultimo errore di connessione.</span><span class="sxs-lookup"><span data-stu-id="6d099-242">Timestamp of the last connection error.</span></span> <span data-ttu-id="6d099-243">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-243">This value is hidden by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d099-244">Per informazioni sui contatori delle prestazioni per le repliche di disponibilità, vedere [SQL Server, replica di disponibilità](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="6d099-244">For information about performance counters for availability replicas, see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
##  <a name="to-group-availability-group-information"></a><a name="AvDbDetails"></a><span data-ttu-id="6d099-245">Per raggruppare le informazioni sul gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="6d099-245">To Group Availability Group Information</span></span>  
 <span data-ttu-id="6d099-246">Per raggruppare le informazioni, fare clic su **Raggruppa per**, quindi selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d099-246">To group the information, click **Group by**, and select one of the following:</span></span>  
  
-   <span data-ttu-id="6d099-247">**Repliche di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="6d099-247">**Availability replicas**</span></span>  
  
-   <span data-ttu-id="6d099-248">**Database di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="6d099-248">**Availability databases**</span></span>  
  
-   <span data-ttu-id="6d099-249">**Stato di sincronizzazione**</span><span class="sxs-lookup"><span data-stu-id="6d099-249">**Synchronization state**</span></span>  
  
-   <span data-ttu-id="6d099-250">**Conformità del failover**</span><span class="sxs-lookup"><span data-stu-id="6d099-250">**Failover readiness**</span></span>  
  
-   <span data-ttu-id="6d099-251">**Problemi**</span><span class="sxs-lookup"><span data-stu-id="6d099-251">**Issues**</span></span>  
  
 <span data-ttu-id="6d099-252">Nel riquadro in cui sono visualizzate le informazioni raggruppate sono presenti le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d099-252">The pane that displays the grouped information displays the following columns:</span></span>  
  
 <span data-ttu-id="6d099-253">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6d099-253">**Name**</span></span>  
 <span data-ttu-id="6d099-254">Nome del database di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="6d099-254">The name of the availability database.</span></span> <span data-ttu-id="6d099-255">Questo valore è visualizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-255">This value is shown by default.</span></span>  
  
 <span data-ttu-id="6d099-256">**Replica**</span><span class="sxs-lookup"><span data-stu-id="6d099-256">**Replica**</span></span>  
 <span data-ttu-id="6d099-257">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che ospita la replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="6d099-257">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span> <span data-ttu-id="6d099-258">Questo valore è visualizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-258">This value is shown by default.</span></span>  
  
 <span data-ttu-id="6d099-259">**Stato di sincronizzazione**</span><span class="sxs-lookup"><span data-stu-id="6d099-259">**Synchronization State**</span></span>  
 <span data-ttu-id="6d099-260">Indica se il database di disponibilità è attualmente sincronizzato con la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-260">Indicates whether the availability database is currently synchronized with primary replica.</span></span> <span data-ttu-id="6d099-261">Questo valore è visualizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-261">This value is shown by default.</span></span> <span data-ttu-id="6d099-262">I possibili stati di sincronizzazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d099-262">The possible synchronization states are:</span></span>  
  
-   <span data-ttu-id="6d099-263">**Non in sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="6d099-263">**Not synchronizing**.</span></span>  
  
    -   <span data-ttu-id="6d099-264">Per il ruolo primario, indica che il database non è pronto per la sincronizzazione del log delle transazioni con i database secondari corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6d099-264">For the primary role, indicates that the database is not ready to synchronize its transaction log with the corresponding secondary databases.</span></span>  
  
    -   <span data-ttu-id="6d099-265">Per un database secondario, indica che il database non ha ancora avviato la sincronizzazione del log a causa di un problema di connessione, è stato sospeso o si trova in stati di transizione durante l'avvio o un cambio di ruolo.</span><span class="sxs-lookup"><span data-stu-id="6d099-265">For a secondary database, indicates that the database has not started log synchronization because of a connection issue, is being suspended, or is going through transition states during startup or a role switch.</span></span>  
  
-   <span data-ttu-id="6d099-266">**Sincronizzazione**in corso.</span><span class="sxs-lookup"><span data-stu-id="6d099-266">**Synchronizing**.</span></span>  
  
     <span data-ttu-id="6d099-267">Su una replica primaria:</span><span class="sxs-lookup"><span data-stu-id="6d099-267">On a primary replica:</span></span>  
  
    -   <span data-ttu-id="6d099-268">Per un database primario, indica che questo database è pronto ad accettare una richiesta di analisi da un database secondario.</span><span class="sxs-lookup"><span data-stu-id="6d099-268">For a primary database, indicates that this database is ready to accept a scan request from a secondary database.</span></span>  
  
    -   <span data-ttu-id="6d099-269">Su una replica secondaria, indica che è in corso uno spostamento dati attivo per quel database secondario.</span><span class="sxs-lookup"><span data-stu-id="6d099-269">On a secondary replica, indicates that there is active data movement going on for that secondary database.</span></span>  
  
     <span data-ttu-id="6d099-270">Su una replica secondaria, indica che è in corso uno spostamento dati attivo per quella replica.</span><span class="sxs-lookup"><span data-stu-id="6d099-270">On a secondary replica, indicates that there is active data movement going on for that replica.</span></span>  
  
-   <span data-ttu-id="6d099-271">**Sincronizzazione**completata.</span><span class="sxs-lookup"><span data-stu-id="6d099-271">**Synchronized**.</span></span>  
  
     <span data-ttu-id="6d099-272">Per un database primario, indica che almeno un database secondario è sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="6d099-272">For a primary database, indicates that at least one secondary database is synchronized.</span></span>  
  
     <span data-ttu-id="6d099-273">Per un database secondario, indica che il database è sincronizzato con il database primario corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6d099-273">For a secondary database, indicates that the database is synchronized with the corresponding primary database.</span></span>  
  
-   <span data-ttu-id="6d099-274">**Ripristino in corso**.</span><span class="sxs-lookup"><span data-stu-id="6d099-274">**Reverting**.</span></span>  
  
     <span data-ttu-id="6d099-275">Indica la fase del processo di rollback in cui un database secondario ottiene attivamente le pagine dal database primario.</span><span class="sxs-lookup"><span data-stu-id="6d099-275">Indicates the phase in the undo process when a secondary database is actively getting pages from the primary database.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="6d099-276">Quando un database si trova nello stato REVERTING, il failover forzato sulla replica secondaria può lasciare il database in uno stato in cui non può essere avviato.</span><span class="sxs-lookup"><span data-stu-id="6d099-276">When a database is in the REVERTING state, forcing failover to the secondary replica can leave that database in a state in which it cannot be started.</span></span>  
  
-   <span data-ttu-id="6d099-277">**Inizializzazione**.</span><span class="sxs-lookup"><span data-stu-id="6d099-277">**Initializing**.</span></span>  
  
     <span data-ttu-id="6d099-278">Indica la fase di rollback in cui il log delle transazioni necessario a un database secondario per l'intercettazione dell'LSN di rollback viene fornito e finalizzato su una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-278">Indicates the phase of undo when the transaction log required for a secondary database to catch up to the undo LSN is being shipped and hardened on a secondary replica.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="6d099-279">Quando un database si trova nello stato INITIALIZING, il failover forzato sulla replica secondaria lascerà sempre il database in uno stato in cui non può essere avviato.</span><span class="sxs-lookup"><span data-stu-id="6d099-279">When a database is in the INITIALIZING state, forcing failover to the secondary replica will always leave that database in a state in which it cannot be started.</span></span>  
  
 <span data-ttu-id="6d099-280">**Conformità failover**</span><span class="sxs-lookup"><span data-stu-id="6d099-280">**Failover Readiness**</span></span>  
 <span data-ttu-id="6d099-281">Indica per quale replica di disponibilità è possibile eseguire il failover con o senza la potenziale perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="6d099-281">Indicates which availability replica can be failed over with or without potential data loss.</span></span> <span data-ttu-id="6d099-282">Questa colonna viene visualizzata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-282">This column is shown by default.</span></span> <span data-ttu-id="6d099-283">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="6d099-283">The possible values are:</span></span>  
  
-   <span data-ttu-id="6d099-284">**Perdita di dati**</span><span class="sxs-lookup"><span data-stu-id="6d099-284">**Data Loss**</span></span>  
  
-   <span data-ttu-id="6d099-285">**Nessuna perdita di dati**</span><span class="sxs-lookup"><span data-stu-id="6d099-285">**No Data Loss**</span></span>  
  
 <span data-ttu-id="6d099-286">**Problemi**</span><span class="sxs-lookup"><span data-stu-id="6d099-286">**Issues**</span></span>  
 <span data-ttu-id="6d099-287">Indica il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="6d099-287">Lists the issue name.</span></span> <span data-ttu-id="6d099-288">Questa colonna viene visualizzata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-288">This column is shown by default.</span></span> <span data-ttu-id="6d099-289">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="6d099-289">The possible values are:</span></span>  
  
-   <span data-ttu-id="6d099-290">**Avvisi**.</span><span class="sxs-lookup"><span data-stu-id="6d099-290">**Warnings**.</span></span> <span data-ttu-id="6d099-291">Fare clic per visualizzare le soglie e gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="6d099-291">Click to display the thresholds and warnings issues.</span></span>  
  
-   <span data-ttu-id="6d099-292">**Critico**.</span><span class="sxs-lookup"><span data-stu-id="6d099-292">**Critical**.</span></span> <span data-ttu-id="6d099-293">Fare clic per visualizzare i problemi critici.</span><span class="sxs-lookup"><span data-stu-id="6d099-293">Click to display the critical issues.</span></span>  
  
 <span data-ttu-id="6d099-294">Per un elenco di tutti i problemi relativi ai criteri AlwaysOn, vedere [criteri AlwaysOn per problemi operativi con gruppi di disponibilità AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="6d099-294">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="6d099-295">**Sospeso**</span><span class="sxs-lookup"><span data-stu-id="6d099-295">**Suspended**</span></span>  
 <span data-ttu-id="6d099-296">Indica se il database è **Sospeso** o **Ripreso**.</span><span class="sxs-lookup"><span data-stu-id="6d099-296">Indicates whether the database is **Suspended** or has been **Resumed**.</span></span> <span data-ttu-id="6d099-297">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-297">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-298">**Motivo di sospensione**</span><span class="sxs-lookup"><span data-stu-id="6d099-298">**Suspend Reason**</span></span>  
 <span data-ttu-id="6d099-299">Indica il motivo dello stato di sospensione.</span><span class="sxs-lookup"><span data-stu-id="6d099-299">Indicates the reason for the suspended state.</span></span> <span data-ttu-id="6d099-300">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-300">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-301">**Perdita di dati stimata (secondi)**</span><span class="sxs-lookup"><span data-stu-id="6d099-301">**Estimate Data Loss (seconds)**</span></span>  
 <span data-ttu-id="6d099-302">Indica la differenza di orario dell'ultimo record del log delle transazioni nelle repliche primaria e secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-302">Indicates the time difference of the last transaction log record in the primary replica and secondary replica.</span></span> <span data-ttu-id="6d099-303">In caso di errore della replica primaria, andranno persi tutti i record del log delle transazioni entro il tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="6d099-303">If the primary replica fails, all transaction log records within the time window will be lost.</span></span> <span data-ttu-id="6d099-304">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-304">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-305">**Tempo di recupero stimato (secondi)**</span><span class="sxs-lookup"><span data-stu-id="6d099-305">**Estimated Recovery Time (seconds)**</span></span>  
 <span data-ttu-id="6d099-306">Indica il tempo in secondi necessario per ripetere l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="6d099-306">Indicates the time in seconds it takes to redo the catch-up time.</span></span> <span data-ttu-id="6d099-307">Il *tempo di aggiornamento* è il tempo richiesto dalla replica secondaria per l'aggiornamento alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-307">The *catch-up time* is the time it will take for the secondary replica to catch up with the primary replica.</span></span> <span data-ttu-id="6d099-308">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-308">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-309">**Prestazioni di sincronizzazione (secondi)**</span><span class="sxs-lookup"><span data-stu-id="6d099-309">**Synchronization Performance (seconds)**</span></span>  
 <span data-ttu-id="6d099-310">Indica il tempo in secondi necessario per la sincronizzazione tra le repliche primaria e secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-310">Indicates the time in seconds it takes to synchronize between the primary and secondary replicas.</span></span> <span data-ttu-id="6d099-311">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-311">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-312">**Dimensione coda di invio log (KB)**</span><span class="sxs-lookup"><span data-stu-id="6d099-312">**Log Send Queue Size (KB)**</span></span>  
 <span data-ttu-id="6d099-313">Indica il numero di record del log nei file di log del database primario che non sono stati inviati alla replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-313">Indicates the amount of log records in the log files of the primary database that have not been sent to the secondary replica.</span></span> <span data-ttu-id="6d099-314">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-314">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-315">**Velocità di invio log (KB/sec)**</span><span class="sxs-lookup"><span data-stu-id="6d099-315">**Log Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="6d099-316">Indica la velocità in KB al secondo alla quale i record di log vengono inviati alla replica secondaria. Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-316">Indicates the rate in KB per second at which log records are being sent to the secondary replica This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-317">**Dimensione coda di rollforward (KB)**</span><span class="sxs-lookup"><span data-stu-id="6d099-317">**Redo Queue Size (KB)**</span></span>  
 <span data-ttu-id="6d099-318">Indica il numero di record del log nei file di log della replica secondaria di cui non è stato ancora eseguito il rollforward.</span><span class="sxs-lookup"><span data-stu-id="6d099-318">Indicates the amount of log records in the log files of the secondary replica that have not yet been redone.</span></span> <span data-ttu-id="6d099-319">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-319">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-320">**Velocità fase di rollforward (KB/sec)**</span><span class="sxs-lookup"><span data-stu-id="6d099-320">**Redo Rate (KB/sec)**</span></span>  
 <span data-ttu-id="6d099-321">Indica la velocità in KB al secondo alla quale viene eseguito il rollforward dei record di log.</span><span class="sxs-lookup"><span data-stu-id="6d099-321">Indicates the rate in KB per second at which the log records are being redone.</span></span> <span data-ttu-id="6d099-322">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-322">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-323">**Velocità di invio flusso di file (KB/sec)**</span><span class="sxs-lookup"><span data-stu-id="6d099-323">**FileStream Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="6d099-324">Indica la velocità del flusso di file in KB al secondo con cui avviene l'invio delle transazioni alla replica.</span><span class="sxs-lookup"><span data-stu-id="6d099-324">Indicates the rate of the FileStream in KB per second at which transactions are being sent to the replica.</span></span> <span data-ttu-id="6d099-325">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-325">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-326">**LSN di fine log**</span><span class="sxs-lookup"><span data-stu-id="6d099-326">**End of Log LSN**</span></span>  
 <span data-ttu-id="6d099-327">Indica il numero di sequenza del file di log (LSN) effettivo corrispondente all'ultimo record di log nella cache log nelle repliche primarie e secondarie.</span><span class="sxs-lookup"><span data-stu-id="6d099-327">Indicates the actual log sequence number (LSN) that corresponds to the last log record in the log cache on the primary and secondary replicas.</span></span> <span data-ttu-id="6d099-328">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-328">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-329">**LSN recupero**</span><span class="sxs-lookup"><span data-stu-id="6d099-329">**Recovery LSN**</span></span>  
 <span data-ttu-id="6d099-330">Indica la fine del log delle transazioni prima che la replica scriva qualsiasi nuovo record del log dopo il failover o il recupero nella replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-330">Indicates the end of the transaction log before the replica writes any new log records after recovery or failover on the primary replica.</span></span> <span data-ttu-id="6d099-331">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-331">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-332">**LSN troncamento**</span><span class="sxs-lookup"><span data-stu-id="6d099-332">**Truncation LSN**</span></span>  
 <span data-ttu-id="6d099-333">Indica il valore minimo di troncamento del log per la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-333">Indicates the minimum log truncation value for the primary replica.</span></span> <span data-ttu-id="6d099-334">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-334">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-335">**LSN ultimo commit**</span><span class="sxs-lookup"><span data-stu-id="6d099-335">**Last Commit LSN**</span></span>  
 <span data-ttu-id="6d099-336">Indica l'LSN effettivo corrispondente all'ultimo record di commit nel log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="6d099-336">Indicates the actual LSN corresponding to the last commit record in the transaction log.</span></span> <span data-ttu-id="6d099-337">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-337">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-338">**Ora ultimo commit**</span><span class="sxs-lookup"><span data-stu-id="6d099-338">**Last Commit Time**</span></span>  
 <span data-ttu-id="6d099-339">Indica l'ora che corrisponde all'ultimo record di commit.</span><span class="sxs-lookup"><span data-stu-id="6d099-339">Indicates the time corresponding to the last commit record.</span></span> <span data-ttu-id="6d099-340">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-340">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-341">**LSN ultimo invio**</span><span class="sxs-lookup"><span data-stu-id="6d099-341">**Last Sent LSN**</span></span>  
 <span data-ttu-id="6d099-342">Indica il punto fino a cui tutti i blocchi di log sono stati inviati dalla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-342">Indicates the point up to which all log blocks have been sent by the primary replica.</span></span> <span data-ttu-id="6d099-343">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-343">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-344">**Ora ultimo invio**</span><span class="sxs-lookup"><span data-stu-id="6d099-344">**Last Sent Time**</span></span>  
 <span data-ttu-id="6d099-345">Indica l'ora di invio dell'ultimo blocco del log.</span><span class="sxs-lookup"><span data-stu-id="6d099-345">Indicates the time when the last log block was sent.</span></span> <span data-ttu-id="6d099-346">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-346">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-347">**LSN ultima ricezione**</span><span class="sxs-lookup"><span data-stu-id="6d099-347">**Last Received LSN**</span></span>  
 <span data-ttu-id="6d099-348">Indica il punto fino a cui tutti i blocchi di log sono stati ricevuti dalla replica secondaria che ospita il database secondario.</span><span class="sxs-lookup"><span data-stu-id="6d099-348">Indicates the point up to which all log blocks have been received by the secondary replica that hosts the secondary database.</span></span> <span data-ttu-id="6d099-349">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-349">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-350">**Ora ultima ricezione**</span><span class="sxs-lookup"><span data-stu-id="6d099-350">**Last Received Time**</span></span>  
 <span data-ttu-id="6d099-351">Indica l'ora in cui è stato letto l'identificatore del blocco di log nell'ultimo messaggio ricevuto sulla replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-351">Indicates the time when the log block identifier in last message received was read on the secondary replica.</span></span> <span data-ttu-id="6d099-352">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-352">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-353">**LSN ultima finalizzazione**</span><span class="sxs-lookup"><span data-stu-id="6d099-353">**Last Hardened LSN**</span></span>  
 <span data-ttu-id="6d099-354">Indica il punto fino a cui tutti i record di log sono stati scaricati su disco sulla replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-354">Indicates the point up to which all log records have been flushed to disk on the secondary replica.</span></span> <span data-ttu-id="6d099-355">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-355">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-356">**Ora ultima finalizzazione**</span><span class="sxs-lookup"><span data-stu-id="6d099-356">**Last Hardened Time**</span></span>  
 <span data-ttu-id="6d099-357">Indica l'ora di ricezione dell'identificatore del blocco di log per il valore LSN finale sulla replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-357">Indicates the time when the log-block identifier was received for the last hardened LSN on the secondary replica.</span></span> <span data-ttu-id="6d099-358">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-358">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-359">**LSN ultimo rollforward**</span><span class="sxs-lookup"><span data-stu-id="6d099-359">**Last Redone LSN**</span></span>  
 <span data-ttu-id="6d099-360">Indica l'LSN effettivo del record di log di cui è stato eseguito il rollforward per ultimo nella replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="6d099-360">Indicates the actual LSN of the log record that was redone last on the secondary replica.</span></span> <span data-ttu-id="6d099-361">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-361">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="6d099-362">**Ora ultimo rollforward**</span><span class="sxs-lookup"><span data-stu-id="6d099-362">**Last Redone Time**</span></span>  
 <span data-ttu-id="6d099-363">Indica l'ora di rollforward dell'ultimo record del log nel database secondario.</span><span class="sxs-lookup"><span data-stu-id="6d099-363">Indicates the time when the last log record was redone on the secondary database.</span></span> <span data-ttu-id="6d099-364">Questo valore è nascosto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d099-364">This value is hidden by default.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6d099-365">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="6d099-365">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6d099-366">Utilizzare i criteri AlwaysOn per visualizzare l'integrità di un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d099-366">Use AlwaysOn Policies to View the Health of an Availability Group &#40;SQL Server&#41;</span></span>](use-always-on-policies-to-view-the-health-of-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="6d099-367">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d099-367">See Also</span></span>  
 <span data-ttu-id="6d099-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d099-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span></span>  
 [<span data-ttu-id="6d099-369">Monitoraggio di Gruppi di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d099-369">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
