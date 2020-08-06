---
title: Amministrare una topologia peer-to-peer (programmazione Transact-SQL della replica) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, peer-to-peer replication
ms.assetid: 4d0fa941-f9ea-4a14-aed9-34df593fc6f2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a73af1c1f3a7196d87f77681ee9d62a3ef248a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626672"
---
# <a name="administer-a-peer-to-peer-topology-replication-transact-sql-programming"></a><span data-ttu-id="ff143-102">Amministrazione di una topologia peer-to-peer (programmazione Transact-SQL della replica)</span><span class="sxs-lookup"><span data-stu-id="ff143-102">Administer a Peer-to-Peer Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="ff143-103">L'amministrazione di una topologia peer-to-peer è simile all'amministrazione di una tipica topologia di replica transazionale, sebbene diverse aree richiedano speciali considerazioni.</span><span class="sxs-lookup"><span data-stu-id="ff143-103">Administering a peer-to-peer topology is similar to administering a typical transactional replication topology, but there are a number of areas with special considerations.</span></span> <span data-ttu-id="ff143-104">La differenza principale nell'amministrazione di una topologia peer-to-peer consiste nella necessità di mettere il sistema in *stato di inattività*in caso di determinate modifiche.</span><span class="sxs-lookup"><span data-stu-id="ff143-104">The principal difference in administering a peer-to-peer topology is that some changes require the system to be *quiesced*.</span></span> <span data-ttu-id="ff143-105">Mettere in stato di inattività un sistema significa arrestare le attività sulle tabelle pubblicate in tutti i nodi e verificare che ogni nodo abbia ricevuto tutte le modifiche dagli altri nodi.</span><span class="sxs-lookup"><span data-stu-id="ff143-105">Quiescing a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="ff143-106">Per altre informazioni, vedere [Come mettere una topologia di replica in stato di inattività &#40;programmazione Transact-SQL della replica&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="ff143-106">For more information, see [Quiesce a Replication Topology &#40;Replication Transact-SQL Programming&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff143-107">In una topologia peer-to-peer il database di distribuzione non può utilizzare una versione precedente di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] rispetto a un Sottoscrittore pull.</span><span class="sxs-lookup"><span data-stu-id="ff143-107">In a peer-to-peer topology, the distributor cannot be using an earlier version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] than a pull subscriber.</span></span>  
  
### <a name="to-add-an-article-to-an-existing-configuration"></a><span data-ttu-id="ff143-108">Per aggiungere un articolo a una configurazione esistente</span><span class="sxs-lookup"><span data-stu-id="ff143-108">To add an article to an existing configuration</span></span>  
  
1.  <span data-ttu-id="ff143-109">Mettere in stato di inattività il sistema.</span><span class="sxs-lookup"><span data-stu-id="ff143-109">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="ff143-110">Arrestare l'agente di distribuzione in ciascun nodo nella topologia.</span><span class="sxs-lookup"><span data-stu-id="ff143-110">Stop the Distribution Agent at each node in the topology.</span></span> <span data-ttu-id="ff143-111">Per altre informazioni, vedere [Concetti di base relativi ai file eseguibili dell’agente di replica](../concepts/replication-agent-executables-concepts.md) o [Avviare e arrestare un agente di replica &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ff143-111">For more information, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="ff143-112">Eseguire l'istruzione CREATE TABLE per aggiungere la tabella nuova a ogni nodo nella topologia.</span><span class="sxs-lookup"><span data-stu-id="ff143-112">Execute the CREATE TABLE statement to add the new table at each node in the topology.</span></span>  
  
4.  <span data-ttu-id="ff143-113">Effettuare manualmente la copia bulk dei dati per la nuova tabella in tutti i nodi utilizzando l' [utilità bcp](../../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ff143-113">Bulk copy the data for the new table manually at all nodes by using the [bcp utility](../../../tools/bcp-utility.md).</span></span>  
  
5.  <span data-ttu-id="ff143-114">Eseguire [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) per creare il nuovo articolo in ogni nodo nella topologia.</span><span class="sxs-lookup"><span data-stu-id="ff143-114">Execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) to create the new article at each node in the topology.</span></span> <span data-ttu-id="ff143-115">Per altre informazioni, vedere [definire un articolo](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="ff143-115">For more information, see [Define an Article](../publish/define-an-article.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff143-116">Dopo l'esecuzione di [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) , la replica aggiunge automaticamente l'articolo alle sottoscrizioni nella topologia.</span><span class="sxs-lookup"><span data-stu-id="ff143-116">After [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) is executed, replication automatically adds the article to the subscriptions in the topology.</span></span>  
  
6.  <span data-ttu-id="ff143-117">Riavviare gli agenti di distribuzione in ciascun nodo nella topologia.</span><span class="sxs-lookup"><span data-stu-id="ff143-117">Restart the Distribution Agents at each node in the topology.</span></span>  
  
### <a name="to-make-schema-changes-to-a-publication-database"></a><span data-ttu-id="ff143-118">Per apportare le modifiche dello schema nel database di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ff143-118">To make schema changes to a publication database</span></span>  
  
1.  <span data-ttu-id="ff143-119">Mettere in stato di inattività il sistema.</span><span class="sxs-lookup"><span data-stu-id="ff143-119">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="ff143-120">Eseguire le istruzioni DLL (Data Definition Language) per modificare lo schema delle tabelle pubblicate.</span><span class="sxs-lookup"><span data-stu-id="ff143-120">Execute the data definition language (DDL) statements to modify the schema of published tables.</span></span> <span data-ttu-id="ff143-121">Per altre informazioni sulle modifiche dello schema supportate, vedere [Modifiche allo schema nei database di pubblicazione](../publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="ff143-121">For more information about supported schema changes, see [Make Schema Changes on Publication Databases](../publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
3.  <span data-ttu-id="ff143-122">Prima di riprendere l'attività nelle tabelle pubblicate, mettere di nuovo il sistema in stato di inattività.</span><span class="sxs-lookup"><span data-stu-id="ff143-122">Before you resume activity on published tables, quiesce the system again.</span></span> <span data-ttu-id="ff143-123">Ciò garantisce che le modifiche dello schema siano ricevute da tutti i nodi prima che venga eseguita la replica di nuove modifiche dei dati.</span><span class="sxs-lookup"><span data-stu-id="ff143-123">This ensures that schema changes have been received by all nodes before any new data changes are replicated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff143-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff143-124">Example</span></span>  
 <span data-ttu-id="ff143-125">Nell'esempio seguente è illustrato come aggiungere un nuovo articolo di tabella a una topologia di replica peer-to-peer esistente con due nodi.</span><span class="sxs-lookup"><span data-stu-id="ff143-125">The following example demonstrates how to add a new table article to an existing peer-to-peer replication topology that has two nodes.</span></span>  
  
 [!code-sql[HowTo#sp_addp2particle_createtables](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createtables)]  
  
 [!code-sql[HowTo#sp_addp2particle_cmdline](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_cmdline)]  
  
 [!code-sql[HowTo#sp_addp2particle_createarticle](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createarticle)]  
  
## <a name="see-also"></a><span data-ttu-id="ff143-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff143-126">See Also</span></span>  
 <span data-ttu-id="ff143-127">[Domande frequenti sull'amministrazione della replica](frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="ff143-127">[Replication Administration FAQ](frequently-asked-questions-for-replication-administrators.md) </span></span>  
 <span data-ttu-id="ff143-128">[Backup e ripristino di database SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="ff143-128">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="ff143-129">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="ff143-129">Peer-to-Peer Transactional Replication</span></span>](../transactional/peer-to-peer-transactional-replication.md)  
  
  
