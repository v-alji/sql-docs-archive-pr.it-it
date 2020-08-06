---
title: Backup obsoleto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 307a4ad0-675a-4f97-9a3c-cedd61bdfae5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c6a944b08b15d591a9bbce47a0c0c6a8de3eb54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634983"
---
# <a name="outdated-backup"></a><span data-ttu-id="0ba6c-102">Backup obsoleto</span><span class="sxs-lookup"><span data-stu-id="0ba6c-102">Outdated Backup</span></span>
  <span data-ttu-id="0ba6c-103">Questa regola consente di controllare se per un database siano disponibili backup recenti.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-103">This rule checks that a database has recent backups.</span></span> <span data-ttu-id="0ba6c-104">La pianificazione di backup frequenti è importante per la protezione dei database dalla perdita di dati dovuta a errori diversi.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-104">Scheduling regular backups is important for protecting your databases against data loss from many different failures.</span></span> <span data-ttu-id="0ba6c-105">La frequenza più appropriata per il backup dei dati dipende dal modello di recupero del database, dalle esigenze aziendali relative alla possibile perdita di dati e dalla frequenza con cui viene aggiornato il database.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-105">The appropriate frequency for backing up data depends on the recovery model of the database, on business requirements about potential data loss, and on how frequently the database is updated.</span></span> <span data-ttu-id="0ba6c-106">In un database aggiornato di frequente, l'esposizione alla perdita di dati aumenta piuttosto rapidamente tra i backup.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-106">In a frequently updated database, the work-loss exposure increases fairly quickly between backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="0ba6c-107">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="0ba6c-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="0ba6c-108">È consigliabile eseguire backup sufficientemente frequenti per proteggere i database dalla perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-108">We recommend that you perform backups frequently enough to protect databases against data loss.</span></span>  
  
 <span data-ttu-id="0ba6c-109">Il modello di recupero con registrazione minima e il modello di recupero con registrazione completa richiedono entrambi il backup dei dati.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-109">The simple recovery model and full recovery model both require data backups.</span></span> <span data-ttu-id="0ba6c-110">Per entrambi i modelli, è possibile aggiungere ai backup completi backup differenziali per ridurre in modo efficiente il rischio di perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-110">For either recovery model, you can supplement your full backups with differential backups to efficiently reduce the risk of data loss.</span></span>  
  
 <span data-ttu-id="0ba6c-111">Per un database che utilizza il modello di recupero con registrazione completa, è consigliabile eseguire frequenti backup del log.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-111">For a database that uses the full recovery model, we recommend that you take frequent log backups.</span></span> <span data-ttu-id="0ba6c-112">Per un database di produzione che contiene dati molto importanti, è in genere consigliabile eseguire backup del log ogni quindici minuti.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-112">For a production database that contains very important data, log backups would typically be taken every one to fifteen minutes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ba6c-113">Il metodo consigliato per la pianificazione dei backup è un piano di manutenzione del database.</span><span class="sxs-lookup"><span data-stu-id="0ba6c-113">The recommended method for scheduling backups is a database maintenance plan.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="0ba6c-114">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="0ba6c-114">For More Information</span></span>  
 [<span data-ttu-id="0ba6c-115">Backup e ripristino di database di sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ba6c-115">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="0ba6c-116">Modelli di recupero &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ba6c-116">Recovery Models &#40;SQL Server&#41;</span></span>](../backup-restore/recovery-models-sql-server.md)  
  
 [<span data-ttu-id="0ba6c-117">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ba6c-117">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 [<span data-ttu-id="0ba6c-118">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ba6c-118">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
 [<span data-ttu-id="0ba6c-119">Piani di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0ba6c-119">Maintenance Plans</span></span>](../maintenance-plans/maintenance-plans.md)  
  
 [<span data-ttu-id="0ba6c-120">Backup di log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ba6c-120">Transaction Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/transaction-log-backups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ba6c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ba6c-121">See Also</span></span>  
 [<span data-ttu-id="0ba6c-122">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="0ba6c-122">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
