---
title: 'Esempio: Ripristino a fasi di filegroup selezionati (modello di recupero con registrazione minima) | Microsoft Docs'
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
ms.assetid: d7ad026c-5355-4308-9560-0dc843940d4f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8254ac96a269b6fb433759e5a649bf9df1b7feac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725996"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model"></a><span data-ttu-id="f0858-102">Esempio: Ripristino a fasi di filegroup selezionati (modello di recupero con registrazione minima)</span><span class="sxs-lookup"><span data-stu-id="f0858-102">Example: Piecemeal Restore of Only Some Filegroups (Simple Recovery Model)</span></span>
  <span data-ttu-id="f0858-103">Le informazioni in questo argomento sono rilevanti per i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che utilizzano il modello di recupero con registrazione minima e che contengono un filegroup di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="f0858-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span>  
  
 <span data-ttu-id="f0858-104">Con una sequenza di ripristino a fasi, il database viene ripristinato e recuperato in varie fasi a livello di filegroup, partendo dal filegroup primario e da tutti i filegroup secondari in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="f0858-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="f0858-105">In questo esempio, un database denominato `adb`, che utilizza il modello di recupero con registrazione minima, contiene tre filegroup.</span><span class="sxs-lookup"><span data-stu-id="f0858-105">In this example, a database named `adb`, which uses the simple recovery model, contains three filegroups.</span></span> <span data-ttu-id="f0858-106">Il filegroup `A` è in lettura/scrittura, mentre i filegroup `B` e `C` sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="f0858-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="f0858-107">Inizialmente, tutti i filegroup sono online.</span><span class="sxs-lookup"><span data-stu-id="f0858-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="f0858-108">Il filegroup primario e il filegroup `B` del database `adb` risultano danneggiati. L'amministrazione del database decide pertanto di ripristinarli con una sequenza di ripristino a fasi.</span><span class="sxs-lookup"><span data-stu-id="f0858-108">The primary and filegroup `B` of database `adb` appear to be damaged; therefore, the database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="f0858-109">Nel modello di recupero con registrazione minima, tutti i filegroup in lettura/scrittura devono essere ripristinati dallo stesso backup parziale.</span><span class="sxs-lookup"><span data-stu-id="f0858-109">Under the simple recovery model, all read/write filegroups must be restored from the same partial backup.</span></span> <span data-ttu-id="f0858-110">Sebbene sia intatto, il filegroup `A` deve essere ripristinato con il filegroup primario per assicurarne la consistenza. Il database verrà ripristinato fino al punto nel tempo corrispondente alla fine dell'ultimo backup parziale.</span><span class="sxs-lookup"><span data-stu-id="f0858-110">Although filegroup `A` is intact, it must be restored with the primary filegroup to make sure that they are consistent (the database will be restored to the point in time defined by the end of the last partial backup).</span></span> <span data-ttu-id="f0858-111">Il filegroup `C` è intatto, ma è necessario recuperarlo per attivare la modalità online.</span><span class="sxs-lookup"><span data-stu-id="f0858-111">Filegroup `C` is intact, but it must be recovered to bring it online.</span></span> <span data-ttu-id="f0858-112">Nel filegroup `B`, sebbene sia danneggiato, sono inclusi dati meno critici rispetto al filegroup `C`. Il filegroup `B` , pertanto, verrà ripristinato per ultimo.</span><span class="sxs-lookup"><span data-stu-id="f0858-112">Filegroup `B`, although damaged, contains less critical data than Filegroup `C`; therefore, `B` will be restored last.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="f0858-113">Sequenze di ripristino</span><span class="sxs-lookup"><span data-stu-id="f0858-113">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0858-114">La sintassi di una sequenza di ripristino online è la stessa di una sequenza di ripristino offline.</span><span class="sxs-lookup"><span data-stu-id="f0858-114">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="f0858-115">Ripristino parziale del filegroup primario e del filegroup `A` da un backup parziale.</span><span class="sxs-lookup"><span data-stu-id="f0858-115">Partial restore of the primary and filegroup `A` from a partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb READ_WRITE_FILEGROUPS FROM partial_backup   
    WITH PARTIAL, RECOVERY  
    ```  
  
     <span data-ttu-id="f0858-116">A questo punto il filegroup primario e il filegroup `A` sono online.</span><span class="sxs-lookup"><span data-stu-id="f0858-116">At this point the primary filegroup and filegroup `A` are online.</span></span> <span data-ttu-id="f0858-117">I file nei filegroup `B` e `C` sono in attesa di recupero e i filegroup sono offline.</span><span class="sxs-lookup"><span data-stu-id="f0858-117">Files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
2.  <span data-ttu-id="f0858-118">Recupero online del filegroup `C`.</span><span class="sxs-lookup"><span data-stu-id="f0858-118">Online recovery of filegroup `C`.</span></span>  
  
     <span data-ttu-id="f0858-119">Il filegroup `C` è consistente poiché il backup parziale ripristinato in precedenza è stato creato dopo l'impostazione del filegroup `C` in modalità di sola lettura, anche se il ripristino ha portato il database in un momento anteriore nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f0858-119">Filegroup `C` is consistent because the partial backup that was restored above was taken after filegroup `C` became read-only, although the database was taken back in time by the restore.</span></span> <span data-ttu-id="f0858-120">L'amministratore del database recupera il filegroup `C`, senza ripristinarlo, per attivare la modalità online.</span><span class="sxs-lookup"><span data-stu-id="f0858-120">The database administrator recovers the filegroup `C`, without restoring it, to bring it online.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="f0858-121">A questo punto il filegroup primario e i filegroup `A` e `C` sono online.</span><span class="sxs-lookup"><span data-stu-id="f0858-121">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="f0858-122">I file del filegroupB restano in attesa di recupero, con il filegroup offline.</span><span class="sxs-lookup"><span data-stu-id="f0858-122">Files in filegroupB remain recovery pending, with the filegroup offline.</span></span>  
  
3.  <span data-ttu-id="f0858-123">Ripristino online del filegroup `B.`</span><span class="sxs-lookup"><span data-stu-id="f0858-123">Online restore of filegroup `B.`</span></span>  
  
     <span data-ttu-id="f0858-124">I file nel filegroup `B` devono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="f0858-124">Files in filegroup `B` must be restored.</span></span> <span data-ttu-id="f0858-125">L'amministratore del database ripristina il backup del filegroup `B` eseguito dopo l'impostazione del filegroup `B` in modalità di sola lettura e prima del backup parziale.</span><span class="sxs-lookup"><span data-stu-id="f0858-125">The database administrator restores the backup of filegroup `B` taken after filegroup `B` became read-only and before the partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup   
    WITH RECOVERY  
    ```  
  
     <span data-ttu-id="f0858-126">In questa fase tutti i filegroup sono online.</span><span class="sxs-lookup"><span data-stu-id="f0858-126">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="f0858-127">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="f0858-127">Additional Examples</span></span>  
  
-   [<span data-ttu-id="f0858-128">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="f0858-128">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="f0858-129">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="f0858-129">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="f0858-130">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="f0858-130">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="f0858-131">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="f0858-131">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="f0858-132">Esempio: Ripristino online di un file di lettura/scrittura &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="f0858-132">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="f0858-133">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="f0858-133">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="f0858-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0858-134">See Also</span></span>  
 <span data-ttu-id="f0858-135">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f0858-135">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="f0858-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0858-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="f0858-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0858-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="f0858-138">Ripristini a fasi &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0858-138">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
