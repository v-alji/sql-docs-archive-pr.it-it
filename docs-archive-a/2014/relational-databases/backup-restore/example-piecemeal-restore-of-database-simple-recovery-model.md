---
title: 'Esempio: Ripristino a fasi di un database (modello di recupero con registrazione minima) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], simple recovery model
- restore sequences [SQL Server], piecemeal
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: 9834b14a-4e56-4654-b190-c2a38624b6b4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69de84fa2ff3a853eb9926549ad4859d2f1ae38e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720094"
---
# <a name="example-piecemeal-restore-of-database-simple-recovery-model"></a><span data-ttu-id="c3fb7-102">Esempio: Ripristino a fasi di un database (modello di recupero con registrazione minima)</span><span class="sxs-lookup"><span data-stu-id="c3fb7-102">Example: Piecemeal Restore of Database (Simple Recovery Model)</span></span>
  <span data-ttu-id="c3fb7-103">Una sequenza di ripristino a fasi consente di ripristinare e recuperare un database in varie fasi a livello di filegroup, a partire dal filegroup primario e tutti i filegroup secondari di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="c3fb7-104">In questo esempio il database `adb` viene ripristinato in un nuovo computer dopo un'emergenza.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="c3fb7-105">Per il database è in uso il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-105">The database is using the simple recovery model.</span></span> <span data-ttu-id="c3fb7-106">Prima dell'emergenza, tutti i filegroup erano online.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="c3fb7-107">I filegroup `A` e `C` sono di lettura/scrittura, mentre il filegroup `B` è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-107">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="c3fb7-108">Il filegroup `B` è diventato di sola lettura prima del backup parziale più recente, che include il filegroup primario e i filegroup secondari di lettura/scrittura `A` e `C`.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-108">Filegroup `B` became read-only before the most recent partial backup, which contains the primary filegroup and the read/write secondary filegroups, `A` and `C`.</span></span> <span data-ttu-id="c3fb7-109">Dopo che il filegroup `B` è diventato di sola lettura, è stato eseguito un backup di file separato per il filegroup `B` .</span><span class="sxs-lookup"><span data-stu-id="c3fb7-109">After filegroup `B` became read-only, a separate file backup of filegroup `B` was taken.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="c3fb7-110">Sequenze di ripristino</span><span class="sxs-lookup"><span data-stu-id="c3fb7-110">Restore Sequences</span></span>  
  
1.  <span data-ttu-id="c3fb7-111">Eseguire un ripristino parziale del filegroup primario e dei filegroup `A` e `C`.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-111">Partial restore of the primary and filegroups `A` and `C`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A',FILEGROUP='C'   
       FROM partial_backup   
       WITH PARTIAL, RECOVERY;  
  
    ```  
  
     <span data-ttu-id="c3fb7-112">A questo punto il filegroup primario e i filegroup `A` e `C` sono online.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-112">At this point, the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="c3fb7-113">Il recupero di tutti i file nel filegroup `B` è in sospeso e questo filegroup è offline.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-113">All files in filegroup `B` are recovery pending, and the filegroup is offline.</span></span>  
  
2.  <span data-ttu-id="c3fb7-114">Eseguire un ripristino online del filegroup `B`.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-114">Online restore of filegroup `B`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY;  
  
    ```  
  
     <span data-ttu-id="c3fb7-115">In questa fase tutti i filegroup sono online.</span><span class="sxs-lookup"><span data-stu-id="c3fb7-115">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="c3fb7-116">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="c3fb7-116">Additional Examples</span></span>  
  
-   [<span data-ttu-id="c3fb7-117">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="c3fb7-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="c3fb7-118">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="c3fb7-118">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="c3fb7-119">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="c3fb7-119">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="c3fb7-120">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="c3fb7-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="c3fb7-121">Esempio: Ripristino online di un file di lettura/scrittura &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="c3fb7-121">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="c3fb7-122">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="c3fb7-122">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="c3fb7-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3fb7-123">See Also</span></span>  
 <span data-ttu-id="c3fb7-124">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c3fb7-124">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="c3fb7-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3fb7-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="c3fb7-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3fb7-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="c3fb7-127">Ripristini a fasi &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3fb7-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
