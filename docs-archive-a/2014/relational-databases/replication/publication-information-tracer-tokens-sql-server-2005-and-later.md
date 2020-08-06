---
title: Informazioni sulla pubblicazione, token di traccia (pubblicazione transazionale, SQL Server 2005 e versioni successive) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.tracertokens.f1
ms.assetid: a115ba95-17ae-45df-91bd-5a1a35f3745f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af84ab9b9122a55367780976056ce95aa597f62a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721300"
---
# <a name="publication-information-tracer-tokens-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="12077-102">Informazioni sulla pubblicazione, Token di traccia (Pubblicazione transazionale, SQL Server 2005 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="12077-102">Publication Information, Tracer Tokens (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="12077-103"> La scheda **Token di traccia** consente di convalidare le connessioni e di misurare la latenza di un sistema che usa la replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="12077-103">The **Tracer Tokens** tab allows you to validate connections and to measure the latency of a system that uses transactional replication.</span></span> <span data-ttu-id="12077-104">Un token, ovvero una piccola quantità di dati, viene scritto nel log delle transazioni del database di pubblicazione, contrassegnato come se fosse una comune transazione replicata e inviato tramite il sistema in modo da consentire:</span><span class="sxs-lookup"><span data-stu-id="12077-104">A token (a small amount of data) is written to the transaction log of the publication database, marked as though it were a typical replicated transaction, and sent through the system, allowing a calculation of:</span></span>  
  
-   <span data-ttu-id="12077-105">Il calcolo del tempo che trascorre tra l'esecuzione del commit di una transazione nel server di pubblicazione e l'inserimento del comando corrispondente nel database di distribuzione del server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="12077-105">How much time elapses between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span>  
  
-   <span data-ttu-id="12077-106">Il calcolo del tempo che trascorre tra l'inserimento di un comando nel database di distribuzione e l'esecuzione del commit della transazione corrispondente nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="12077-106">How much time elapses between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span>  
  
 <span data-ttu-id="12077-107">I risultati ottenuti da questi calcoli consentono all'utente di rispondere a una serie di domande, incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="12077-107">From these calculations, you can answer a number of questions, including:</span></span>  
  
-   <span data-ttu-id="12077-108">Quali Sottoscrittori hanno richiesto più tempo per ricevere una modifica dal server di pubblicazione?</span><span class="sxs-lookup"><span data-stu-id="12077-108">Which Subscribers take the longest to receive a change from the Publisher?</span></span>  
  
-   <span data-ttu-id="12077-109">Tra i Sottoscrittori destinati a ricevere il token di traccia, quali non lo hanno eventualmente ricevuto?</span><span class="sxs-lookup"><span data-stu-id="12077-109">Of the Subscribers expected to receive the tracer token, which, if any, have not received it?</span></span>  
  
## <a name="options"></a><span data-ttu-id="12077-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="12077-110">Options</span></span>  
 <span data-ttu-id="12077-111">Per modificare la modalità di visualizzazione dei dati nella griglia, fare clic con il pulsante destro del mouse sulla griglia, quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12077-111">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="12077-112">**Ordinamento**: consente di ordinare una o più colonne nella finestra di dialogo **Ordina colonne** .</span><span class="sxs-lookup"><span data-stu-id="12077-112">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="12077-113">**Seleziona colonne da visualizzare**: consente di selezionare le colonne da visualizzare e l'ordine di visualizzazione nella finestra di dialogo **Seleziona colonne** .</span><span class="sxs-lookup"><span data-stu-id="12077-113">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="12077-114">**Filtro**: consente di filtrare le righe nella griglia in base a valori di colonna nella finestra di dialogo **Impostazioni filtro** .</span><span class="sxs-lookup"><span data-stu-id="12077-114">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="12077-115">**Cancella filtro**: consente di cancellare qualsiasi impostazione di filtro per la griglia.</span><span class="sxs-lookup"><span data-stu-id="12077-115">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="12077-116">Le impostazioni di filtro sono specifiche di ogni griglia.</span><span class="sxs-lookup"><span data-stu-id="12077-116">Filter settings are specific to each grid.</span></span> <span data-ttu-id="12077-117">La selezione e l'ordinamento delle colonne vengono applicati a tutte le griglie dello stesso tipo, ad esempio la griglia delle pubblicazioni per ogni server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="12077-117">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="12077-118">**Inserisci utilità di traccia**</span><span class="sxs-lookup"><span data-stu-id="12077-118">**Insert Tracer**</span></span>  
 <span data-ttu-id="12077-119">Fare clic su questo pulsante per inserire un token di traccia nel log delle transazioni del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="12077-119">Click to insert a tracer token in the transaction log at the Publisher.</span></span>  
  
 <span data-ttu-id="12077-120">**Ora di inserimento**</span><span class="sxs-lookup"><span data-stu-id="12077-120">**Time inserted**</span></span>  
 <span data-ttu-id="12077-121">Selezionare l'ora in cui è stato inserito un token di traccia per visualizzare le informazioni sulla latenza a partire da tale ora.</span><span class="sxs-lookup"><span data-stu-id="12077-121">Select a time at which a tracer token was inserted to display latency information from that time.</span></span> <span data-ttu-id="12077-122">Per impostazione predefinita, vengono visualizzate le informazioni a partire dall'ora più recente.</span><span class="sxs-lookup"><span data-stu-id="12077-122">By default, information from the most recent time is displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12077-123">Le informazioni sul token di traccia vengono mantenute per lo stesso periodo di tempo degli altri dati cronologici, ovvero in base all'impostazione del periodo di memorizzazione della cronologia del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="12077-123">Tracer token information is retained for the same time period as other historical data, which is governed by the history retention period of the distribution database.</span></span> <span data-ttu-id="12077-124">Per informazioni sulla modifica delle proprietà del database di distribuzione, vedere [Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="12077-124">For information about changing distribution database properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
 <span data-ttu-id="12077-125">**Sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="12077-125">**Subscription**</span></span>  
 <span data-ttu-id="12077-126">Nome di ogni sottoscrizione della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="12077-126">The name of each subscription to the publication.</span></span>  
  
 <span data-ttu-id="12077-127">**Dal server di pubblicazione al server di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="12077-127">**Publisher to Distributor**</span></span>  
 <span data-ttu-id="12077-128">Tempo trascorso tra l'esecuzione del commit di una transazione nel server di pubblicazione e l'inserimento del comando corrispondente nel database di distribuzione del server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="12077-128">The elapsed time between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span> <span data-ttu-id="12077-129">Il valore **In sospeso** indica che il token non ha ancora raggiunto il server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="12077-129">A value of **Pending** indicates that the token has not yet reached the Distributor.</span></span> <span data-ttu-id="12077-130">Se lo stato In sospeso persiste, assicurarsi che l'agente di lettura log sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="12077-130">If the pending state persists, ensure that the Log Reader Agent is running.</span></span>  
  
 <span data-ttu-id="12077-131">**Dal server di distribuzione al Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="12077-131">**Distributor to Subscriber**</span></span>  
 <span data-ttu-id="12077-132">Tempo trascorso tra l'inserimento di un comando nel database di distribuzione e l'esecuzione del commit della transazione corrispondente nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="12077-132">The elapsed time between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span> <span data-ttu-id="12077-133">Il valore **In sospeso** indica che il token non ha ancora raggiunto il Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="12077-133">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span> <span data-ttu-id="12077-134">Se lo stato In sospeso persiste, assicurarsi che l'agente di distribuzione sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="12077-134">If the pending state persists, ensure that the Distribution Agent is running.</span></span>  
  
 <span data-ttu-id="12077-135">**Latenza totale**</span><span class="sxs-lookup"><span data-stu-id="12077-135">**Total Latency**</span></span>  
 <span data-ttu-id="12077-136">Tempo trascorso tra l'esecuzione del commit di una transazione nel server di pubblicazione e l'esecuzione del commit della transazione corrispondente nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="12077-136">The elapsed time between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="12077-137">Rappresenta la latenza end-to-end del sistema di replica per il Sottoscrittore corrente nel momento specifico.</span><span class="sxs-lookup"><span data-stu-id="12077-137">This represents the end-to-end latency of the replication system for this Subscriber at this time.</span></span> <span data-ttu-id="12077-138">Il valore **In sospeso** indica che il token non ha ancora raggiunto il Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="12077-138">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12077-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12077-139">See Also</span></span>  
 <span data-ttu-id="12077-140">[Avviare e arrestare un agente di replica &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="12077-140">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="12077-141">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="12077-141">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="12077-142">[Misurare la latenza e convalidare le connessioni per la replica transazionale](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="12077-142">[Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span></span>  
 <span data-ttu-id="12077-143">[Monitorare le prestazioni con monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="12077-143">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="12077-144">[Monitoraggio della replica](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="12077-144">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="12077-145">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="12077-145">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
