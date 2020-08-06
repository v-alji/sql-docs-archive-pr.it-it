---
title: Mirroring e snapshot del database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- snapshots [SQL Server database snapshots], database mirroring
- database snapshots [SQL Server], database mirroring
ms.assetid: 0bf1be90-7ce4-484c-aaa7-f8a782f57c5f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9df0b74270280bf2315c6a35a80d4b009b75a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626279"
---
# <a name="database-mirroring-and-database-snapshots-sql-server"></a><span data-ttu-id="4c6d2-102">Mirroring e snapshot del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4c6d2-102">Database Mirroring and Database Snapshots (SQL Server)</span></span>
  <span data-ttu-id="4c6d2-103">Per ripartire il carico di lavoro dei report, è possibile avvalersi di un database mirror gestito per scopi di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-103">You can take advantage of a mirror database that you are maintaining for availability purposes to offload reporting.</span></span> <span data-ttu-id="4c6d2-104">Per utilizzare un database mirror per la gestione dei report, creare nel database mirror uno snapshot del database e indirizzare le richieste di connessione client allo snapshot più recente.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-104">To use a mirror database for reporting, you can create a database snapshot on the mirror database and direct client connection requests to the most recent snapshot.</span></span> <span data-ttu-id="4c6d2-105">Uno snapshot del database è uno snapshot statico, in sola lettura e consistente a livello di transazioni del relativo database di origine nello stato in cui quest'ultimo si trovava al momento della creazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-105">A database snapshot is a static, read-only, transaction-consistent snapshot of its source database as it existed at the moment of the snapshot's creation.</span></span> <span data-ttu-id="4c6d2-106">Per creare uno snapshot del database in un database mirror, è necessario che il database si trovi nello stato di mirroring sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-106">To create a database snapshot on a mirror database, the database must be in the synchronized mirroring state.</span></span>  
  
 <span data-ttu-id="4c6d2-107">A differenza del database mirror stesso, uno snapshot del database è accessibile ai client.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-107">Unlike the mirror database itself, a database snapshot is accessible to clients.</span></span> <span data-ttu-id="4c6d2-108">Fino a quando il server mirror comunica con il server principale, è possibile indirizzare i client di report a uno snapshot.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-108">As long as the mirror server is communicating with the principal server, you can direct reporting clients to connect to a snapshot.</span></span> <span data-ttu-id="4c6d2-109">Si noti che poiché uno snapshot del database è statico, i nuovi dati non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-109">Note that because a database snapshot is static, new data is not available.</span></span> <span data-ttu-id="4c6d2-110">Per rendere disponibili agli utenti dati relativamente recenti, è necessario creare periodicamente un nuovo snapshot del database e fare in modo che le applicazioni indirizzino le connessioni client in arrivo allo snapshot più recente.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-110">To make relatively recent data available to your users, you must create a new database snapshot periodically and have applications direct incoming client connections to the newest snapshot.</span></span>  
  
 <span data-ttu-id="4c6d2-111">Un nuovo snapshot del database è quasi vuoto, ma aumenta nel tempo man mano che un numero crescente di pagine del database vengono aggiornate per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-111">A new database snapshot is almost empty, but it grows over time as more and more database pages are updated for the first time.</span></span> <span data-ttu-id="4c6d2-112">Poiché ogni snapshot in un database aumenta in modo incrementale in questo modo, ogni snapshot del database utilizza tante risorse quanto un database normale.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-112">Because every snapshot on a database grows incrementally in this way, each database snapshot consumes as much resources as a normal database.</span></span> <span data-ttu-id="4c6d2-113">A seconda delle configurazioni del server mirror e del server principale, la presenza di un numero eccessivo di snapshot del database in un database mirror può compromettere le prestazioni nel database principale.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-113">Depending on the configurations of the mirror server and principal server, having an excessive number of database snapshots on a mirror database might decrease performance on the principal database.</span></span> <span data-ttu-id="4c6d2-114">È pertanto consigliabile conservare solo gli snapshot relativamente più recenti nei database mirror.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-114">Therefore, we recommend that you keep only a few relatively recent snapshots on your mirror databases.</span></span> <span data-ttu-id="4c6d2-115">In genere, dopo aver creato uno snapshot di sostituzione, è consigliabile reindirizzare le query in arrivo al nuovo snapshot ed eliminare quello meno recente dopo il completamento delle query correnti.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-115">Typically, after you create a replacement snapshot, you should redirect incoming queries to the new snapshot and drop the earlier snapshot after any current queries complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c6d2-116">Per altre informazioni sugli snapshot del database, vedere [Snapshot del database &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c6d2-116">For more information about database snapshots, see [Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span></span>  
  
 <span data-ttu-id="4c6d2-117">In presenza di un cambio di ruolo, il database e i relativi snapshot vengono riavviati, con conseguente disconnessione temporanea degli utenti.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-117">If role switching occurs, the database and its snapshots are restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="4c6d2-118">Gli snapshot del database rimangono quindi nell'istanza del server dove sono stati creati, ovvero il nuovo database principale.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-118">Afterwards, the database snapshots remain on the server instance where they were created, which has become the new principal database.</span></span> <span data-ttu-id="4c6d2-119">Gli utenti possono continuare a utilizzare gli snapshot dopo il failover,</span><span class="sxs-lookup"><span data-stu-id="4c6d2-119">Users can continue to use the snapshots after the failover.</span></span> <span data-ttu-id="4c6d2-120">anche se ciò comporta un carico aggiuntivo per il nuovo server principale.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-120">However, this places an additional load on the new principal server.</span></span> <span data-ttu-id="4c6d2-121">Se è necessario evitare un peggioramento delle prestazioni, è consigliabile creare uno snapshot nel nuovo database mirror quando diventa disponibile, reindirizzare i client al nuovo snapshot ed eliminare tutti gli snapshot del database dal database mirror precedente.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-121">If performance is a concern in your environment, we recommend that you create a snapshot on the new mirror database when it becomes available, redirect clients to the new snapshot, and drop all of the database snapshots from the former mirror database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c6d2-122">Per una soluzione dedicata per la creazione di report che consente una scalabilità orizzontale appropriata, prendere in considerazione la replica.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-122">For a dedicated reporting solution that scales out well, consider replication.</span></span> <span data-ttu-id="4c6d2-123">Per altre informazioni, vedere [Replica di SQL Server](../install-windows/install-sql-server-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4c6d2-123">For more information, see [SQL Server Replication](../install-windows/install-sql-server-replication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c6d2-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c6d2-124">Example</span></span>  
 <span data-ttu-id="4c6d2-125">In questo esempio vengono creati snapshot in un database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-125">This example creates snapshots on a mirrored database.</span></span>  
  
 <span data-ttu-id="4c6d2-126">Si supponga che il database di una sessione di mirroring del database sia [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6d2-126">Assume that the database of a database mirroring session is [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="4c6d2-127">In questo esempio vengono creati tre snapshot del database nella copia mirror del database `AdventureWorks` che risiede nell'unità `F` .</span><span class="sxs-lookup"><span data-stu-id="4c6d2-127">This example creates three database snapshots on the mirror copy of the `AdventureWorks` database, which resides on the `F` drive.</span></span> <span data-ttu-id="4c6d2-128">Gli snapshot sono denominati `AdventureWorks_0600`, `AdventureWorks_1200`e `AdventureWorks_1800` per identificare l'ora approssimativa in cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-128">The snapshots are named `AdventureWorks_0600`, `AdventureWorks_1200`, and `AdventureWorks_1800` to identify their approximate creation times.</span></span>  
  
1.  <span data-ttu-id="4c6d2-129">Creare il primo snapshot del database sul mirror di [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4c6d2-129">Create the first database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_0600  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_0600.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
2.  <span data-ttu-id="4c6d2-130">Creare il secondo snapshot del database sul mirror di [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6d2-130">Create the second database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="4c6d2-131">Gli utenti che utilizzano ancora `AdventureWorks_0600` possono continuare a utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-131">Users who are still using `AdventureWorks_0600` can continue to use it.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1200  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1200.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="4c6d2-132">A questo punto è possibile indirizzare a livello di programmazione le nuove connessioni client allo snapshot più recente.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-132">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
3.  <span data-ttu-id="4c6d2-133">Creare il terzo snapshot sul mirror [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6d2-133">Create the third snapshot on the mirror [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="4c6d2-134">Gli utenti che utilizzano ancora `AdventureWorks_0600` o `AdventureWorks_1200` possono continuare a utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-134">Users who are still using `AdventureWorks_0600` or `AdventureWorks_1200` can continue to use them.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1800  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1800.SNP')  
        AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="4c6d2-135">A questo punto è possibile indirizzare a livello di programmazione le nuove connessioni client allo snapshot più recente.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-135">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4c6d2-136">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4c6d2-136">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4c6d2-137">Creare uno snapshot del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4c6d2-137">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="4c6d2-138">Visualizzazione di uno snapshot del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c6d2-138">View a Database Snapshot &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="4c6d2-139">Eliminare uno snapshot del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4c6d2-139">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md)  

  
## <a name="see-also"></a><span data-ttu-id="4c6d2-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c6d2-140">See Also</span></span>  
 <span data-ttu-id="4c6d2-141">[Snapshot del database &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4c6d2-141">[Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span></span>  
 [<span data-ttu-id="4c6d2-142">Connettere client a una sessione di mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c6d2-142">Connect Clients to a Database Mirroring Session &#40;SQL Server&#41;</span></span>](connect-clients-to-a-database-mirroring-session-sql-server.md)  
  
  
