---
title: Failover su un database secondario per il log shipping (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server]
- secondary data files [SQL Server], manual fail over
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: edfe5d59-4287-49c1-96c9-dd56212027bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 164e2809e4eff5a14ef54124df7c7ca9077793ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718665"
---
# <a name="fail-over-to-a-log-shipping-secondary-sql-server"></a><span data-ttu-id="debc6-102">Failover su un database secondario per il log shipping (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="debc6-102">Fail Over to a Log Shipping Secondary (SQL Server)</span></span>
  <span data-ttu-id="debc6-103">L'esecuzione del failover in un database secondario per il log shipping è utile in caso di errore o di manutenzione dell'istanza del server primario.</span><span class="sxs-lookup"><span data-stu-id="debc6-103">Failing over to a log shipping secondary is useful if the primary server instance fails or requires maintenance.</span></span>  
  
## <a name="preparing-for-a-controlled-failover"></a><span data-ttu-id="debc6-104">Preparazione di un failover controllato</span><span class="sxs-lookup"><span data-stu-id="debc6-104">Preparing for a Controlled Failover</span></span>  
 <span data-ttu-id="debc6-105">I database primario e secondario non sono in genere sincronizzati, in quanto il database primario continua a essere aggiornato dopo l'ultimo processo di backup.</span><span class="sxs-lookup"><span data-stu-id="debc6-105">Typically, the primary and secondary databases are unsynchronized, because the primary database continues to be updated after its latest backup job.</span></span> <span data-ttu-id="debc6-106">In alcuni casi, inoltre, i backup del log delle transazioni recenti non sono stati copiati nelle istanze del server secondario oppure è possibile che alcuni backup del log copiati non siano stati ancora applicati al database secondario.</span><span class="sxs-lookup"><span data-stu-id="debc6-106">Also, in some cases, recent transaction log backups have not been copied to the secondary server instances, or some copied log backups might still not have been applied to the secondary database.</span></span> <span data-ttu-id="debc6-107">Se possibile, è consigliabile iniziare con la sincronizzazione di tutti i database secondari con il database primario.</span><span class="sxs-lookup"><span data-stu-id="debc6-107">We recommend that you begin by synchronizing all of the secondary databases with the primary database, if possible.</span></span>  
  
 <span data-ttu-id="debc6-108">Per informazioni sui processi per il log shipping, vedere [Informazioni sul log shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="debc6-108">For information about log shipping jobs, see [About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span></span>  
  
## <a name="failing-over"></a><span data-ttu-id="debc6-109">Esecuzione del failover</span><span class="sxs-lookup"><span data-stu-id="debc6-109">Failing Over</span></span>  
 <span data-ttu-id="debc6-110">Per eseguire il failover su un database secondario, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="debc6-110">To fail over to a secondary database:</span></span>  
  
1.  <span data-ttu-id="debc6-111">Copiare i file di backup non ancora copiati dalla condivisione di backup alla cartella di destinazione della copia in ogni server secondario.</span><span class="sxs-lookup"><span data-stu-id="debc6-111">Copy any uncopied backup files from the backup share to the copy destination folder of each secondary server.</span></span>  
  
2.  <span data-ttu-id="debc6-112">Applicare in sequenza i backup del log delle transazioni non ancora applicati a ogni database secondario.</span><span class="sxs-lookup"><span data-stu-id="debc6-112">Apply any unapplied transaction log backups in sequence to each secondary database.</span></span> <span data-ttu-id="debc6-113">Per altre informazioni, vedere [Applicazione dei backup di log delle transazioni &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="debc6-113">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="debc6-114">Se il database primario è accessibile, eseguire il backup del log delle transazioni attivo e applicarlo ai database secondari.</span><span class="sxs-lookup"><span data-stu-id="debc6-114">If the primary database is accessible, back up the active transaction log and apply the log backup to the secondary databases.</span></span>  
  
     <span data-ttu-id="debc6-115">Se l'istanza del server primario originale non è danneggiata, eseguire il backup della parte finale del log delle transazioni del database primario tramite WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="debc6-115">If the original primary server instance is not damaged, back up the tail of the transaction log of the primary database using WITH NORECOVERY.</span></span> <span data-ttu-id="debc6-116">In questo modo il database resta nella stato di ripristino e pertanto non disponibile agli utenti.</span><span class="sxs-lookup"><span data-stu-id="debc6-116">This leaves the database in the restoring state and therefore unavailable to users.</span></span> <span data-ttu-id="debc6-117">Infine è possibile eseguirne il rollforward applicando i backup del log delle transazioni del database primario da sostituire.</span><span class="sxs-lookup"><span data-stu-id="debc6-117">Eventually you will be able to roll this database forward by applying transaction log backups from the replacement primary database.</span></span>  
  
     <span data-ttu-id="debc6-118">Per altre informazioni, vedere [Backup di log delle transazioni &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="debc6-118">For more information, see [Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="debc6-119">Dopo la sincronizzazione dei server secondari, è possibile eseguire il failover su qualsiasi server recuperando il relativo database secondario e reindirizzando i client a quell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="debc6-119">After the secondary servers are synchronized, you can fail over to whichever one you prefer by recovering its secondary database and redirecting clients to that server instance.</span></span> <span data-ttu-id="debc6-120">L'operazione di recupero consente di rendere consistente il database e di portarlo online.</span><span class="sxs-lookup"><span data-stu-id="debc6-120">Recovering puts the database into a consistent state and brings it online.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="debc6-121">Quando si rende disponibile un database secondario, è necessario assicurarsi che i relativi metadati siano coerenti con quelli del database primario originale.</span><span class="sxs-lookup"><span data-stu-id="debc6-121">When you make a secondary database available, you should ensure that its metadata is consistent with the metadata of the original primary database.</span></span> <span data-ttu-id="debc6-122">Per altre informazioni, vedere [Gestione dei metadati quando si rende disponibile un database in un'altra istanza del server &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="debc6-122">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
5.  <span data-ttu-id="debc6-123">Dopo il recupero di un database secondario, è possibile riconfigurarlo affinché funga da database primario per altri database secondari.</span><span class="sxs-lookup"><span data-stu-id="debc6-123">After you have recovered a secondary database, you can reconfigure it to act as a primary database for other secondary databases.</span></span>  
  
     <span data-ttu-id="debc6-124">Se non è disponibile un altro database secondario, vedere [Configurare il log shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="debc6-124">If no other secondary database is available, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="debc6-125">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="debc6-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="debc6-126">Modificare i ruoli tra i server primario e secondario per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="debc6-126">Change Roles Between Primary and Secondary Log Shipping Servers &#40;SQL Server&#41;</span></span>](change-roles-between-primary-and-secondary-log-shipping-servers-sql-server.md)  
  
-   [<span data-ttu-id="debc6-127">Gestione di account di accesso e di processi dopo un cambio di ruolo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="debc6-127">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="debc6-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="debc6-128">See Also</span></span>  
 <span data-ttu-id="debc6-129">[Tabelle e stored procedure relative al log shipping](log-shipping-tables-and-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="debc6-129">[Log Shipping Tables and Stored Procedures](log-shipping-tables-and-stored-procedures.md) </span></span>  
 <span data-ttu-id="debc6-130">[Informazioni sul log shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="debc6-130">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="debc6-131">Backup della parte finale del log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="debc6-131">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/tail-log-backups-sql-server.md)  
  
  
