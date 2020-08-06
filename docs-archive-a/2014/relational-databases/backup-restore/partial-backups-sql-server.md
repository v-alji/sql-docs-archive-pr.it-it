---
title: Backup parziali (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- partial backups [SQL Server]
- READ_WRITE_FILEGROUPS option
- database backups [SQL Server], about backing up databases
ms.assetid: fe6b6bb1-38d0-46c4-bab8-31df14e8999c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0c03cf2fb4d3af6fe87459e881e26c48cfacc232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635689"
---
# <a name="partial-backups-sql-server"></a><span data-ttu-id="80aff-102">Backup parziali (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80aff-102">Partial Backups (SQL Server)</span></span>
  <span data-ttu-id="80aff-103">Tutti i modelli di recupero di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supportano backup parziali, pertanto questo argomento è attinente per tutti i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80aff-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recovery models support partial backups, so this topic is relevant for all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="80aff-104">I backup parziali sono tuttavia progettati per l'utilizzo con il modello di recupero con registrazione minima e consentono di migliorare la flessibilità per i backup di database di dimensioni molto grandi contenenti uno o più filegroup di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="80aff-104">However, partial backups are designed for use under the simple recovery model to improve flexibility for backing up very large databases that contain one or more read-only filegroups.</span></span>  
  
 <span data-ttu-id="80aff-105">I backup parziali sono utili quando si desidera escludere i filegroup di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="80aff-105">Partial backups are useful whenever you want to exclude read-only filegroups.</span></span> <span data-ttu-id="80aff-106">Un *backup parziale* è simile a un backup completo del database, ma non contiene tutti i filegroup.</span><span class="sxs-lookup"><span data-stu-id="80aff-106">A *partial backup* resembles a full database backup, but a partial backup does not contain all the filegroups.</span></span> <span data-ttu-id="80aff-107">Per un database di lettura/scrittura, un backup parziale contiene invece i dati del filegroup primario, tutti i filegroup di lettura/scrittura e uno o più file di sola lettura specificati facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="80aff-107">Instead, for a read-write database, a partial backup contains the data in the primary filegroup, every read-write filegroup, and, optionally, one or more read-only files.</span></span> <span data-ttu-id="80aff-108">Il backup parziale di un database di sola lettura contiene esclusivamente il filegroup primario.</span><span class="sxs-lookup"><span data-stu-id="80aff-108">A partial backup of a read-only database contains only the primary filegroup.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80aff-109">Se un database di sola lettura diventa di lettura/scrittura dopo un backup parziale, potrebbero essere presenti filegroup secondari di lettura/scrittura non inclusi nel backup parziale.</span><span class="sxs-lookup"><span data-stu-id="80aff-109">If a read-only database is changed to read/write after a partial backup, there might be read/write secondary filegroups that are not in the partial backup.</span></span> <span data-ttu-id="80aff-110">In questo caso, se si tenta di eseguire un backup parziale differenziale, l'operazione non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="80aff-110">In this case, if you try to take a differential partial backup, the backup fails.</span></span> <span data-ttu-id="80aff-111">Prima di poter eseguire un backup parziale differenziale del database, è necessario eseguire un altro backup parziale.</span><span class="sxs-lookup"><span data-stu-id="80aff-111">Before you can take a differential partial backup of the database, you must take another partial backup.</span></span> <span data-ttu-id="80aff-112">Il nuovo backup parziale include tutti i filegroup secondari di lettura/scrittura e può fungere da base per backup parziali differenziali.</span><span class="sxs-lookup"><span data-stu-id="80aff-112">The new partial backup contains every read/write secondary filegroup and can serve as the base for differential partial backups.</span></span>  
  
 <span data-ttu-id="80aff-113">I backup di file relativi a filegroup di sola lettura possono essere combinati con backup parziali.</span><span class="sxs-lookup"><span data-stu-id="80aff-113">File backups of read-only filegroups can be combined with partial backups.</span></span> <span data-ttu-id="80aff-114">Per informazioni sui backup di file, vedere [Backup completi di file &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="80aff-114">For information about file backups, see [Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="80aff-115">Un backup parziale può essere utilizzato come *base differenziale* per backup parziali differenziali.</span><span class="sxs-lookup"><span data-stu-id="80aff-115">A partial backup can serve as the *differential base* for differential partial backups.</span></span> <span data-ttu-id="80aff-116">Per altre informazioni, vedere [Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="80aff-116">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="80aff-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="80aff-117">Related Tasks</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80aff-118">I backup parziali non sono supportati in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] né nella Creazione guidata piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="80aff-118">Partial backups are not supported by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the Maintenance Plan Wizard.</span></span>  
  
 <span data-ttu-id="80aff-119">**Per creare un backup parziale**</span><span class="sxs-lookup"><span data-stu-id="80aff-119">**To create a partial backup**</span></span>  
  
-   <span data-ttu-id="80aff-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; opzione FILEGROUP, se necessario)</span><span class="sxs-lookup"><span data-stu-id="80aff-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; FILEGROUP option, if needed)</span></span>  
  
 <span data-ttu-id="80aff-121">**Per utilizzare un backup parziale in una sequenza di ripristino**</span><span class="sxs-lookup"><span data-stu-id="80aff-121">**To use a partial backup in a restore sequence**</span></span>  
  
-   [<span data-ttu-id="80aff-122">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="80aff-122">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="80aff-123">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="80aff-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="80aff-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80aff-124">See Also</span></span>  
 <span data-ttu-id="80aff-125">[Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="80aff-125">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="80aff-126">[Ripristini di file &#40;modello di recupero con registrazione minima&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="80aff-126">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="80aff-127">Ripristini a fasi &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80aff-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
