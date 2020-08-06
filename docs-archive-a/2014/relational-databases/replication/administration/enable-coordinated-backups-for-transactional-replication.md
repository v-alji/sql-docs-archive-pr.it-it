---
title: Abilitare backup coordinati per la replica transazionale (programmazione Transact-SQL della replica) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, backup and restore
- sp_replicationdboption
- sync with backup [SQL Server replication]
- coordinated backups [SQL Server replication]
- backups [SQL Server replication], transactional replication
ms.assetid: 73a914ba-8b2d-4f4d-ac1b-db9bac676a30
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77405cd968fa917c3ccc799eb7d168782443eee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725564"
---
# <a name="enable-coordinated-backups-for-transactional-replication-replication-transact-sql-programming"></a><span data-ttu-id="426f2-102">Attivazione di backup coordinati per la replica transazionale (programmazione Transact-SQL della replica)</span><span class="sxs-lookup"><span data-stu-id="426f2-102">Enable Coordinated Backups for Transactional Replication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="426f2-103">Quando si attiva la replica transazionale per un database, è possibile specificare che è necessario eseguire il backup di tutte le transazioni prima del recapito al database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="426f2-103">When enabling a database for transactional replication, you can specify that all transactions must be backed up before being delivered to the distribution database.</span></span> <span data-ttu-id="426f2-104">È inoltre possibile attivare il backup coordinato nel database di distribuzione. In questo modo, il log delle transazioni per il database di pubblicazione viene troncato solo in seguito al backup delle transazioni propagate al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="426f2-104">You can also enable coordinated backup on the distribution database so that the transaction log for the publication database is not truncated until transactions that have been propagated to the Distributor have been backed up.</span></span> <span data-ttu-id="426f2-105">Per altre informazioni, vedere [Strategie per il backup e il ripristino della replica snapshot e della replica transazionale](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="426f2-105">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-database-published-with-transactional-replication"></a><span data-ttu-id="426f2-106">Per attivare i backup coordinati per un database pubblicato con replica transazionale</span><span class="sxs-lookup"><span data-stu-id="426f2-106">To enable coordinated backups for a database published with transactional replication</span></span>  
  
1.  <span data-ttu-id="426f2-107">Nel server di pubblicazione usare la funzione [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) per fare in modo che venga restituita la proprietà **IsSyncWithBackup** del database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="426f2-107">At the Publisher, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the publication database.</span></span> <span data-ttu-id="426f2-108">Se la funzione restituisce **1**, i backup coordinati sono già attivati per il database pubblicato.</span><span class="sxs-lookup"><span data-stu-id="426f2-108">If the function returns **1**, coordinated backups are already enabled for the published database.</span></span>  
  
2.  <span data-ttu-id="426f2-109">Se la funzione nel passaggio 1 restituisce **0**, eseguire [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) nel database di pubblicazione nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="426f2-109">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="426f2-110">Specificare il valore **sync with backup** per **\@optname** e **true** per **\@value**.</span><span class="sxs-lookup"><span data-stu-id="426f2-110">Specify a value of **sync with backup** for **\@optname**, and **true** for **\@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="426f2-111">Se si modifica l'opzione **sync with backup** in **false**, il punto di troncamento del database di pubblicazione viene aggiornato dopo l'esecuzione dell'agente di lettura log o dopo un intervallo, in caso di esecuzione continua dell'agente di lettura log.</span><span class="sxs-lookup"><span data-stu-id="426f2-111">If you change the **sync with backup** option to **false**, the truncation point of the publication database will be updated after the Log Reader Agent runs, or after an interval if the Log Reader Agent is running continuously.</span></span> <span data-ttu-id="426f2-112">L'intervallo massimo è controllato dal parametro dell'agente **-MessageInterval**, la cui impostazione predefinita è pari a 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="426f2-112">The maximum interval is controlled by the **-MessageInterval** agent parameter (which has a default of 30 seconds).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-distribution-database"></a><span data-ttu-id="426f2-113">Per attivare i backup coordinati per un database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="426f2-113">To enable coordinated backups for a distribution database</span></span>  
  
1.  <span data-ttu-id="426f2-114">Nel server di distribuzione usare la funzione [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) per fare in modo che venga restituita la proprietà **IsSyncWithBackup** del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="426f2-114">At the Distributor, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the distribution database.</span></span> <span data-ttu-id="426f2-115">Se la funzione restituisce **1**, i backup coordinati sono già attivati per il database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="426f2-115">If the function returns **1**, coordinated backups are already enabled for the distribution database.</span></span>  
  
2.  <span data-ttu-id="426f2-116">Se la funzione nel passaggio 1 restituisce **0**, eseguire [sp_replicationdboption &#40;Transact-SQL&#41; nel](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) database di pubblicazione nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="426f2-116">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="426f2-117">Specificare il valore **Sync with backup** per \*\* \@ optname\*\* e **true** per \*\* \@ value\*\*.</span><span class="sxs-lookup"><span data-stu-id="426f2-117">Specify a value of **sync with backup** for **\@optname** and **true** for **\@value**.</span></span>  
  
### <a name="to-disable-coordinated-backups"></a><span data-ttu-id="426f2-118">Per disabilitare i backup coordinati</span><span class="sxs-lookup"><span data-stu-id="426f2-118">To disable coordinated backups</span></span>  
  
1.  <span data-ttu-id="426f2-119">Nel database di pubblicazione nel server di pubblicazione o nel database di distribuzione nel server di distribuzione eseguire [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="426f2-119">At either the Publisher on the publication database or at the Distributor on the distribution database, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span></span> <span data-ttu-id="426f2-120">Specificare il valore **Sync with backup** per \*\* \@ optname\*\* e **false** per \*\* \@ value\*\*.</span><span class="sxs-lookup"><span data-stu-id="426f2-120">Specify a value of **sync with backup** for **\@optname** and **false** for **\@value**.</span></span>  
  
  
