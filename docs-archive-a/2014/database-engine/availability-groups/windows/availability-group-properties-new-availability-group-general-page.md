---
title: Proprietà del gruppo di disponibilità e nuovo gruppo di disponibilità (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.general.f1
ms.assetid: 9af5379f-91b8-4729-9f75-4a80242a30e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 876b9d0948b7cd0d01c21b0ec1d64c51a55fa157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624365"
---
# <a name="availability-group-properties-and-new-availability-group-general-page"></a><span data-ttu-id="67b79-102">Proprietà gruppo di disponibilità e Nuovo gruppo di disponibilità (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="67b79-102">Availability Group Properties and New Availability Group (General Page)</span></span>
  <span data-ttu-id="67b79-103">Questo argomento si applica alla scheda **Generale** della finestra di dialogo **Nuovo gruppo di disponibilità** e della finestra di dialogo **Proprietà gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="67b79-103">This topic applies to the **General** tab of both the **New Availability Group** dialog box and the **Availability Group Properties** dialog box.</span></span>  <span data-ttu-id="67b79-104">Nella finestra di dialogo **Nuovo gruppo di disponibilità** è possibile creare un nuovo gruppo di disponibilità senza usare la [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b79-104">The **New Availability Group** dialog box enables you to create a new availability group without using the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span></span> <span data-ttu-id="67b79-105">Nella finestra di dialogo **Proprietà gruppo di disponibilità** è possibile visualizzare e modificare la configurazione di un gruppo di disponibilità esistente.</span><span class="sxs-lookup"><span data-stu-id="67b79-105">The **Availability Group Properties** dialog box enables you to view and alter the configuration of an existing availability group.</span></span>  
  
 <span data-ttu-id="67b79-106">**Per visualizzare le proprietà del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="67b79-106">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="67b79-107">Visualizzazione delle Proprietà dei gruppi di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="67b79-107">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="67b79-108">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="67b79-108">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="67b79-109">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="67b79-109">UI element list</span></span>  
 <span data-ttu-id="67b79-110">**Nome del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="67b79-110">**Availability group name**</span></span>  
 <span data-ttu-id="67b79-111">Nome del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="67b79-111">Name of the availability group.</span></span> <span data-ttu-id="67b79-112">Si tratta di un nome specificato dall'utente che deve essere univoco all'interno del cluster di failover di Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="67b79-112">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
## <a name="availability-databases"></a><span data-ttu-id="67b79-113">Database di disponibilità</span><span class="sxs-lookup"><span data-stu-id="67b79-113">Availability Databases</span></span>  
 <span data-ttu-id="67b79-114">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="67b79-114">**Database Name**</span></span>  
 <span data-ttu-id="67b79-115">Nome di un database aggiunto al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="67b79-115">Name of a database that has been added to the availability group.</span></span>  
  
 <span data-ttu-id="67b79-116">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="67b79-116">**Add**</span></span>  
 <span data-ttu-id="67b79-117">Fare clic per aggiungere un database al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="67b79-117">Click to add a database to the availability group.</span></span>  
  
 <span data-ttu-id="67b79-118">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="67b79-118">**Remove**</span></span>  
 <span data-ttu-id="67b79-119">Fare clic per rimuovere un database selezionato dal gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="67b79-119">Click to remove a selected database from the availability group.</span></span>  
  
## <a name="availability-replicas"></a><span data-ttu-id="67b79-120">Repliche di disponibilità</span><span class="sxs-lookup"><span data-stu-id="67b79-120">Availability Replicas</span></span>  
 <span data-ttu-id="67b79-121">**Istanza del server**</span><span class="sxs-lookup"><span data-stu-id="67b79-121">**Server instance**</span></span>  
 <span data-ttu-id="67b79-122">Nome del server dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che ospita la replica corrente e, per un'istanza non predefinita, il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="67b79-122">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="67b79-123">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="67b79-123">**Role**</span></span>  
 <span data-ttu-id="67b79-124">**Server/istanza primaria**</span><span class="sxs-lookup"><span data-stu-id="67b79-124">**Primary**</span></span>  
 <span data-ttu-id="67b79-125">Attualmente la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="67b79-125">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="67b79-126">**Server/istanza secondaria**</span><span class="sxs-lookup"><span data-stu-id="67b79-126">**Secondary**</span></span>  
 <span data-ttu-id="67b79-127">Attualmente una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="67b79-127">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="67b79-128">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="67b79-128">**Resolving**</span></span>  
 <span data-ttu-id="67b79-129">È in corso la risoluzione del ruolo della replica nel ruolo primario o secondario.</span><span class="sxs-lookup"><span data-stu-id="67b79-129">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="67b79-130">**Modalità di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="67b79-130">**Availability Mode**</span></span>  
 <span data-ttu-id="67b79-131">Modalità di disponibilità della replica. I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="67b79-131">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="67b79-132">**Commit asincrono**</span><span class="sxs-lookup"><span data-stu-id="67b79-132">**Asynchronous commit**</span></span>  
 <span data-ttu-id="67b79-133">La replica primaria può eseguire il commit delle transazioni senza attendere che la replica secondaria salvi il log su disco.</span><span class="sxs-lookup"><span data-stu-id="67b79-133">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="67b79-134">**Commit sincrono**</span><span class="sxs-lookup"><span data-stu-id="67b79-134">**Synchronous commit**</span></span>  
 <span data-ttu-id="67b79-135">La replica primaria attende che la replica secondaria salvi la transazione su disco prima di eseguirne il commit.</span><span class="sxs-lookup"><span data-stu-id="67b79-135">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="67b79-136">Per ulteriori informazioni, vedere [modalità di disponibilità (gruppi di disponibilità AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="67b79-136">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="67b79-137">**Modalità di failover**</span><span class="sxs-lookup"><span data-stu-id="67b79-137">**Failover Mode**</span></span>  
 <span data-ttu-id="67b79-138">Modalità di failover della replica. I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="67b79-138">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="67b79-139">**Automatico**</span><span class="sxs-lookup"><span data-stu-id="67b79-139">**Automatic**</span></span>  
 <span data-ttu-id="67b79-140">Failover automatico.</span><span class="sxs-lookup"><span data-stu-id="67b79-140">Automatic failover.</span></span> <span data-ttu-id="67b79-141">La replica è una destinazione per i failover automatici.</span><span class="sxs-lookup"><span data-stu-id="67b79-141">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="67b79-142">Questa opzione è supportata solo se la modalità di disponibilità è impostata sul commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="67b79-142">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="67b79-143">**Manuale**</span><span class="sxs-lookup"><span data-stu-id="67b79-143">**Manual**</span></span>  
 <span data-ttu-id="67b79-144">Failover manuale.</span><span class="sxs-lookup"><span data-stu-id="67b79-144">Manual failover.</span></span> <span data-ttu-id="67b79-145">Il failover della replica può essere eseguito solo manualmente dall'amministratore di database.</span><span class="sxs-lookup"><span data-stu-id="67b79-145">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="67b79-146">**Connessioni nel ruolo primario**</span><span class="sxs-lookup"><span data-stu-id="67b79-146">**Connections in Primary Role**</span></span>  
 <span data-ttu-id="67b79-147">Tipo di connessioni client supportate quando la replica detiene il ruolo primario.</span><span class="sxs-lookup"><span data-stu-id="67b79-147">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="67b79-148">**Consenti tutte le connessioni**</span><span class="sxs-lookup"><span data-stu-id="67b79-148">**Allow all connections**</span></span>  
 <span data-ttu-id="67b79-149">Sono consentite tutte le connessioni ai database nella replica primaria.</span><span class="sxs-lookup"><span data-stu-id="67b79-149">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="67b79-150">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="67b79-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="67b79-151">**Consenti connessioni in lettura/scrittura**</span><span class="sxs-lookup"><span data-stu-id="67b79-151">**Allow read/write connections**</span></span>  
 <span data-ttu-id="67b79-152">Non sono consentite le connessioni in cui la proprietà di connessione Finalità dell'applicazione è impostata su **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="67b79-152">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="67b79-153">Se la proprietà Finalità dell'applicazione è impostata su **Lettura/Scrittura** o se tale proprietà non è impostata, la connessione è consentita.</span><span class="sxs-lookup"><span data-stu-id="67b79-153">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="67b79-154">Per altre informazioni sulla proprietà di connessione Finalità dell'applicazione, vedere [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="67b79-154">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="67b79-155">**Secondario leggibile**</span><span class="sxs-lookup"><span data-stu-id="67b79-155">**Readable Secondary**</span></span>  
 <span data-ttu-id="67b79-156">Specifica se una replica di disponibilità che esegue il ruolo secondario, ovvero una replica secondaria, può accettare connessioni dai client. I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="67b79-156">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="67b79-157">**No**</span><span class="sxs-lookup"><span data-stu-id="67b79-157">**No**</span></span>  
 <span data-ttu-id="67b79-158">Non sono consentite connessioni dirette ai database secondari di questa replica.</span><span class="sxs-lookup"><span data-stu-id="67b79-158">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="67b79-159">I database non sono disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="67b79-159">They are not available for read access.</span></span> <span data-ttu-id="67b79-160">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="67b79-160">This is the default setting.</span></span>  
  
 <span data-ttu-id="67b79-161">**Solo con finalità di lettura**</span><span class="sxs-lookup"><span data-stu-id="67b79-161">**Read-intent only**</span></span>  
 <span data-ttu-id="67b79-162">Sono consentite solo connessioni dirette di sola lettura ai database secondari di questa replica.</span><span class="sxs-lookup"><span data-stu-id="67b79-162">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="67b79-163">Il database o i database secondari sono tutti disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="67b79-163">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="67b79-164">**Sì**</span><span class="sxs-lookup"><span data-stu-id="67b79-164">**Yes**</span></span>  
 <span data-ttu-id="67b79-165">Sono consentite tutte le connessioni ai database secondari di questa replica, ma solo per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="67b79-165">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="67b79-166">Il database o i database secondari sono tutti disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="67b79-166">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="67b79-167">**Timeout sessione (secondi)**</span><span class="sxs-lookup"><span data-stu-id="67b79-167">**Session Timeout (seconds)**</span></span>  
 <span data-ttu-id="67b79-168">Numero di secondi per il periodo di timeout della sessione su questa replica.</span><span class="sxs-lookup"><span data-stu-id="67b79-168">The number of seconds for the session-timeout period on this replica.</span></span>  
  
 <span data-ttu-id="67b79-169">**URL endpoint**</span><span class="sxs-lookup"><span data-stu-id="67b79-169">**Endpoint URL**</span></span>  
 <span data-ttu-id="67b79-170">URL dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="67b79-170">The URL of the endpoint.</span></span> <span data-ttu-id="67b79-171">Per informazioni sul formato di questi URL, vedere [Specificare l'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="67b79-171">For information the format of these URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
 <span data-ttu-id="67b79-172">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="67b79-172">**Add**</span></span>  
 <span data-ttu-id="67b79-173">Fare clic per aggiungere una replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="67b79-173">Click to add a secondary replica to the availability group.</span></span>  
  
 <span data-ttu-id="67b79-174">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="67b79-174">**Remove**</span></span>  
 <span data-ttu-id="67b79-175">Fare clic per rimuovere una replica secondaria specificata dal gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="67b79-175">Click to remove a secondary replica from the availability group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b79-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67b79-176">See Also</span></span>  
 [<span data-ttu-id="67b79-177">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="67b79-177">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
