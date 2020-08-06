---
title: Visualizzare comandi replicati e altre informazioni nel database di distribuzione (programmazione Transact-SQL della replica) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_browsereplcmds
- transactional replication, monitoring
- distribution databases [SQL Server replication], viewing replicated commands
- viewing replicated commands
ms.assetid: 9c20acec-8fab-4483-b9c1-dfe3768f85dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fb5850277d685f2ecf6471fa4bf9814579b2843e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725487"
---
# <a name="view-replicated-commands-and-other-information-in-the-distribution-database-replication-transact-sql-programming"></a><span data-ttu-id="06d21-102">Visualizzare comandi replicati e altre informazioni nel database di distribuzione (programmazione Transact-SQL della replica)</span><span class="sxs-lookup"><span data-stu-id="06d21-102">View Replicated Commands and Other Information in the Distribution Database (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="06d21-103">Durante l'utilizzo della replica transazionale, i comandi della transazione vengono archiviati nel database di distribuzione finché non vengono propagati a tutti i Sottoscrittori dall'agente di distribuzione o un agente di distribuzione nel Sottoscrittore non esegue il pull delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="06d21-103">When using transactional replication, transaction commands are stored in the distribution database until the Distribution Agent propagates them to all Subscribers or a Distribution Agent at the Subscriber pulls the changes.</span></span> <span data-ttu-id="06d21-104">È possibile visualizzare tali comandi in sospeso nel database di distribuzione a livello di programmazione, utilizzando le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="06d21-104">These pending commands in the distribution database can be viewed programmatically using replication stored procedures.</span></span> <span data-ttu-id="06d21-105">Per altre informazioni, vedere [Stored procedure per la replica &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06d21-105">For more information, see [Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-from-all-transactional-publications-in-the-distribution-database"></a><span data-ttu-id="06d21-106">Per visualizzare comandi replicati da tutte le pubblicazioni transazionali nel database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="06d21-106">To view replicated commands from all transactional publications in the distribution database</span></span>  
  
1.  <span data-ttu-id="06d21-107">Nel database di distribuzione del server di distribuzione eseguire [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06d21-107">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-in-the-distribution-database-from-a-specific-article-or-from-a-specific-database-published-using-transactional-replication"></a><span data-ttu-id="06d21-108">Per visualizzare comandi replicati nel database di distribuzione da un articolo specifico o da un database specifico pubblicato tramite la replica transazionale</span><span class="sxs-lookup"><span data-stu-id="06d21-108">To view replicated commands in the distribution database from a specific article or from a specific database published using transactional replication</span></span>  
  
1.  <span data-ttu-id="06d21-109">(Facoltativo) Nel database di pubblicazione del server di pubblicazione eseguire [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06d21-109">(Optional) At the Publisher on the publication database, execute [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span></span> <span data-ttu-id="06d21-110">Specificare \*\* \@ pubblicazioni\*\* e \*\* \@ articoli\*\*.</span><span class="sxs-lookup"><span data-stu-id="06d21-110">Specify **\@publication** and **\@article**.</span></span> <span data-ttu-id="06d21-111">Tenere presente il valore di **article id** nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="06d21-111">Note the value of **article id** in the result set.</span></span>  
  
2.  <span data-ttu-id="06d21-112">Nel database di distribuzione del server di distribuzione eseguire [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06d21-112">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span> <span data-ttu-id="06d21-113">Opzionale Specificare l'ID articolo del passaggio 2 per \*\* \@ article_id\*\*.</span><span class="sxs-lookup"><span data-stu-id="06d21-113">(Optional) Specify the article ID from step 2 for **\@article_id**.</span></span> <span data-ttu-id="06d21-114">Opzionale Specificare l'ID del database di pubblicazione per \*\* \@ publisher_database_id\*\*, che può essere ottenuto dalla colonna **database_id** nella vista del catalogo [sys. databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="06d21-114">(Optional) Specify the ID of the publication database for **\@publisher_database_id**, which can be obtained from the **database_id** column in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d21-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06d21-115">See Also</span></span>  
 [<span data-ttu-id="06d21-116">Monitorare la replica a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="06d21-116">Programmatically Monitor Replication</span></span>](../monitoring-replication.md)  
  
  
