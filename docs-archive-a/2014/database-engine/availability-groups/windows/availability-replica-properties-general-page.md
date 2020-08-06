---
title: Proprietà replica di disponibilità (Pagina Generale) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilityreplicaproperties.general.f1
ms.assetid: 8318fefb-e045-4fab-8507-e1951fc7cec6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 313314baf009cdfb6109e63e9b65e369ac314f60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725007"
---
# <a name="availability-replica-properties-general-page"></a><span data-ttu-id="9bd03-102">Proprietà replica di disponibilità (Pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="9bd03-102">Availability Replica Properties (General Page)</span></span>
  <span data-ttu-id="9bd03-103">Usare questa finestra di dialogo per visualizzare le proprietà di una replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="9bd03-103">Use this dialog box to viewthe properties of an availability replica.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="9bd03-104">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="9bd03-104">Task List</span></span>  
 <span data-ttu-id="9bd03-105">**Per visualizzare le proprietà della replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="9bd03-105">**To view availability replica properties**</span></span>  
  
-   [<span data-ttu-id="9bd03-106">Visualizzazione delle proprietà della replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9bd03-106">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="9bd03-107">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9bd03-107">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="9bd03-108">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="9bd03-108">UI element list</span></span>  
 <span data-ttu-id="9bd03-109">**Nome del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="9bd03-109">**Availability group name**</span></span>  
 <span data-ttu-id="9bd03-110">Nome del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="9bd03-110">Name of the availability group.</span></span> <span data-ttu-id="9bd03-111">Si tratta di un nome specificato dall'utente che deve essere univoco all'interno del cluster di failover di Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="9bd03-111">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
 <span data-ttu-id="9bd03-112">**Istanza del server**</span><span class="sxs-lookup"><span data-stu-id="9bd03-112">**Server instance**</span></span>  
 <span data-ttu-id="9bd03-113">Nome del server dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che ospita la replica corrente e, per un'istanza non predefinita, il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="9bd03-113">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="9bd03-114">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="9bd03-114">**Role**</span></span>  
 <span data-ttu-id="9bd03-115">**Server/istanza primaria**</span><span class="sxs-lookup"><span data-stu-id="9bd03-115">**Primary**</span></span>  
 <span data-ttu-id="9bd03-116">Attualmente la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="9bd03-116">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="9bd03-117">**Server/istanza secondaria**</span><span class="sxs-lookup"><span data-stu-id="9bd03-117">**Secondary**</span></span>  
 <span data-ttu-id="9bd03-118">Attualmente una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="9bd03-118">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="9bd03-119">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="9bd03-119">**Resolving**</span></span>  
 <span data-ttu-id="9bd03-120">È in corso la risoluzione del ruolo della replica nel ruolo primario o secondario.</span><span class="sxs-lookup"><span data-stu-id="9bd03-120">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="9bd03-121">**Modalità di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="9bd03-121">**Availability mode**</span></span>  
 <span data-ttu-id="9bd03-122">Modalità di disponibilità della replica. I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="9bd03-122">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="9bd03-123">**Commit asincrono**</span><span class="sxs-lookup"><span data-stu-id="9bd03-123">**Asynchronous commit**</span></span>  
 <span data-ttu-id="9bd03-124">La replica primaria può eseguire il commit delle transazioni senza attendere che la replica secondaria salvi il log su disco.</span><span class="sxs-lookup"><span data-stu-id="9bd03-124">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="9bd03-125">**Commit sincrono**</span><span class="sxs-lookup"><span data-stu-id="9bd03-125">**Synchronous commit**</span></span>  
 <span data-ttu-id="9bd03-126">La replica primaria attende che la replica secondaria salvi la transazione su disco prima di eseguirne il commit.</span><span class="sxs-lookup"><span data-stu-id="9bd03-126">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="9bd03-127">Per ulteriori informazioni, vedere [modalità di disponibilità (gruppi di disponibilità AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9bd03-127">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="9bd03-128">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="9bd03-128">**Failover mode**</span></span>  
 <span data-ttu-id="9bd03-129">Modalità di failover della replica. I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="9bd03-129">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="9bd03-130">**Automatico**</span><span class="sxs-lookup"><span data-stu-id="9bd03-130">**Automatic**</span></span>  
 <span data-ttu-id="9bd03-131">Failover automatico.</span><span class="sxs-lookup"><span data-stu-id="9bd03-131">Automatic failover.</span></span> <span data-ttu-id="9bd03-132">La replica è una destinazione per i failover automatici.</span><span class="sxs-lookup"><span data-stu-id="9bd03-132">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="9bd03-133">Questa opzione è supportata solo se la modalità di disponibilità è impostata sul commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="9bd03-133">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="9bd03-134">**Manuale**</span><span class="sxs-lookup"><span data-stu-id="9bd03-134">**Manual**</span></span>  
 <span data-ttu-id="9bd03-135">Failover manuale.</span><span class="sxs-lookup"><span data-stu-id="9bd03-135">Manual failover.</span></span> <span data-ttu-id="9bd03-136">Il failover della replica può essere eseguito solo manualmente dall'amministratore di database.</span><span class="sxs-lookup"><span data-stu-id="9bd03-136">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="9bd03-137">**Connessioni nel ruolo primario**</span><span class="sxs-lookup"><span data-stu-id="9bd03-137">**Connections in primary role**</span></span>  
 <span data-ttu-id="9bd03-138">Tipo di connessioni client supportate quando la replica detiene il ruolo primario.</span><span class="sxs-lookup"><span data-stu-id="9bd03-138">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="9bd03-139">**Consenti tutte le connessioni**</span><span class="sxs-lookup"><span data-stu-id="9bd03-139">**Allow all connections**</span></span>  
 <span data-ttu-id="9bd03-140">Sono consentite tutte le connessioni ai database nella replica primaria.</span><span class="sxs-lookup"><span data-stu-id="9bd03-140">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="9bd03-141">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9bd03-141">This is the default setting.</span></span>  
  
 <span data-ttu-id="9bd03-142">**Consenti connessioni in lettura/scrittura**</span><span class="sxs-lookup"><span data-stu-id="9bd03-142">**Allow read/write connections**</span></span>  
 <span data-ttu-id="9bd03-143">Non sono consentite le connessioni in cui la proprietà di connessione Finalità dell'applicazione è impostata su **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="9bd03-143">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="9bd03-144">Se la proprietà Finalità dell'applicazione è impostata su **ReadWrite** o se tale proprietà non è impostata, la connessione è consentita.</span><span class="sxs-lookup"><span data-stu-id="9bd03-144">When the Application Intent property is set to **ReadWrite** or the application intent connection property is not set, the connection is allowed.</span></span>  
  
 <span data-ttu-id="9bd03-145">**Secondario leggibile**</span><span class="sxs-lookup"><span data-stu-id="9bd03-145">**Readable Secondary**</span></span>  
 <span data-ttu-id="9bd03-146">Specifica se una replica di disponibilità che esegue il ruolo secondario, ovvero una replica secondaria, può accettare connessioni dai client. I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="9bd03-146">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="9bd03-147">**No**</span><span class="sxs-lookup"><span data-stu-id="9bd03-147">**No**</span></span>  
 <span data-ttu-id="9bd03-148">Non sono consentite connessioni dirette ai database secondari di questa replica.</span><span class="sxs-lookup"><span data-stu-id="9bd03-148">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="9bd03-149">I database non sono disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="9bd03-149">They are not available for read access.</span></span> <span data-ttu-id="9bd03-150">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9bd03-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="9bd03-151">**Solo con finalità di lettura**</span><span class="sxs-lookup"><span data-stu-id="9bd03-151">**Read-intent only**</span></span>  
 <span data-ttu-id="9bd03-152">Sono consentite solo connessioni dirette di sola lettura ai database secondari di questa replica.</span><span class="sxs-lookup"><span data-stu-id="9bd03-152">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="9bd03-153">Il database o i database secondari sono tutti disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="9bd03-153">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="9bd03-154">**Sì**</span><span class="sxs-lookup"><span data-stu-id="9bd03-154">**Yes**</span></span>  
 <span data-ttu-id="9bd03-155">Sono consentite tutte le connessioni ai database secondari di questa replica, ma solo per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="9bd03-155">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="9bd03-156">Il database o i database secondari sono tutti disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="9bd03-156">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="9bd03-157">Per ulteriori informazioni, vedere [repliche secondarie attive: repliche secondarie leggibili (gruppi di disponibilità AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9bd03-157">For more information, see [Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="9bd03-158">**Timeout sessione (secondi)**</span><span class="sxs-lookup"><span data-stu-id="9bd03-158">**Session timeout (seconds)**</span></span>  
 <span data-ttu-id="9bd03-159">Periodo di timeout in secondi.</span><span class="sxs-lookup"><span data-stu-id="9bd03-159">The time-out period, in seconds.</span></span> <span data-ttu-id="9bd03-160">Il periodo di timeout è il tempo di attesa massimo rispettato dalla replica per la ricezione di un messaggio da un'altra replica, prima di considerare la connessione tra la replica primaria e secondaria non riuscita.</span><span class="sxs-lookup"><span data-stu-id="9bd03-160">The time-out period is the maximum time that the replica waits to receive a message from another replica before considering connection between the primary and secondary replica have failed.</span></span> <span data-ttu-id="9bd03-161">Il timeout della sessione rileva se le repliche secondarie sono connesse alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="9bd03-161">Session timeout detects whether secondaries are connected the primary replica.</span></span> <span data-ttu-id="9bd03-162">Se viene rilevata una connessione non riuscita con una replica secondaria, la replica primaria considera la replica secondaria come NOT_SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="9bd03-162">On detecting a failed connection with a secondary replica, the primary replica considers the secondary replica to be NOT_SYNCHRONIZED.</span></span> <span data-ttu-id="9bd03-163">Se viene rilevata una connessione non riuscita con una replica primaria, una replica secondaria tenta di riconnettersi.</span><span class="sxs-lookup"><span data-stu-id="9bd03-163">On detecting a failed connection with the primary replica, a secondary replica simply attempts to reconnect.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bd03-164">I timeout della sessione non provocano failover automatici.</span><span class="sxs-lookup"><span data-stu-id="9bd03-164">Session timeouts do not cause automatic failovers.</span></span>  
  
 <span data-ttu-id="9bd03-165">**URL endpoint**</span><span class="sxs-lookup"><span data-stu-id="9bd03-165">**Endpoint URL**</span></span>  
 <span data-ttu-id="9bd03-166">Rappresentazione di stringa dell'endpoint del mirroring di database specificato dall'utente usato dalle connessioni tra repliche primarie e secondarie per la sincronizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="9bd03-166">String representation of the user-specified database mirroring endpoint that is used by connections between primary and secondary replicas for data synchronization.</span></span> <span data-ttu-id="9bd03-167">Per informazioni sulla sintassi degli URL dell'endpoint, vedere [Specificare l'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="9bd03-167">For information about the syntax of endpoint URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd03-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bd03-168">See Also</span></span>  
 [<span data-ttu-id="9bd03-169">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9bd03-169">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
