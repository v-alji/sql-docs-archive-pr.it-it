---
title: 'Esempio: ripristino offline di un filegroup primario e di un altro filegroup (modello di recupero con connessione completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- offline restores [SQL Server]
- restore sequences [SQL Server], offline
ms.assetid: 7d6c50eb-dc84-4d66-855a-0b5f1bd89737
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f845927fdd74fba476139fccbf9a5fa112d434e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636731"
---
# <a name="example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model"></a><span data-ttu-id="c43c5-102">Esempio: Ripristino offline del filegroup primario e di un altro filegroup (modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="c43c5-102">Example: Offline Restore of Primary and One Other Filegroup (Full Recovery Model)</span></span>
  <span data-ttu-id="c43c5-103">Le informazioni contenute in questo argomento sono rilevanti solo per i database basati sul modello di recupero con registrazione completa che includono più filegroup.</span><span class="sxs-lookup"><span data-stu-id="c43c5-103">This topic is relevant only for databases under the full recovery model that contain multiple filegroups.</span></span>  
  
 <span data-ttu-id="c43c5-104">In questo esempio un database denominato `adb` contiene tre filegroup.</span><span class="sxs-lookup"><span data-stu-id="c43c5-104">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="c43c5-105">I filegroup `A` e `C` sono di lettura/scrittura, mentre il filegroup `B` è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c43c5-105">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="c43c5-106">Il filegroup primario e il filegroup `B` sono danneggiati, mentre i filegroup `A` e `C` sono integri.</span><span class="sxs-lookup"><span data-stu-id="c43c5-106">The primary filegroup and filegroup `B` are damaged, but filegroups `A` and `C` are intact.</span></span> <span data-ttu-id="c43c5-107">Prima dell'emergenza, tutti i filegroup erano online.</span><span class="sxs-lookup"><span data-stu-id="c43c5-107">Before the disaster, all the filegroups were online.</span></span>  
  
 <span data-ttu-id="c43c5-108">L'amministratore del database decide di ripristinare e recuperare il filegroup primario e il filegroup `B`.</span><span class="sxs-lookup"><span data-stu-id="c43c5-108">The database administrator decides to restore and recover the primary filegroup and filegroup `B`.</span></span> <span data-ttu-id="c43c5-109">Dato che il database utilizza il modello di recupero con registrazione completa, prima dell'avvio del ripristino è necessario eseguire un backup della parte finale del log per il database.</span><span class="sxs-lookup"><span data-stu-id="c43c5-109">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="c43c5-110">Non appena il database è online, viene attivata automaticamente la modalità online per i filegroup `A` e `C` .</span><span class="sxs-lookup"><span data-stu-id="c43c5-110">When the database comes on line, Filegroups `A` and `C` are automatically brought online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c43c5-111">La sequenza di ripristino offline prevede un numero di passaggi inferiore rispetto al ripristino online di un file di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c43c5-111">The offline restore sequence has fewer steps than an online restore of a read-only file.</span></span> <span data-ttu-id="c43c5-112">Per un esempio, vedere [Esempio: Ripristino in linea di un file di sola lettura &#40;modello di recupero con registrazione completa&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="c43c5-112">For an example, see [Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span></span> <span data-ttu-id="c43c5-113">L'intero database, tuttavia, rimane in modalità offline per tutta la durata della sequenza.</span><span class="sxs-lookup"><span data-stu-id="c43c5-113">However, the whole database is offline for the duration of the sequence.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="c43c5-114">Backup della parte finale del log</span><span class="sxs-lookup"><span data-stu-id="c43c5-114">Tail-Log Backup</span></span>  
 <span data-ttu-id="c43c5-115">Prima di ripristinare il database, è necessario che l'amministratore del database esegua il backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="c43c5-115">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="c43c5-116">Dato che il database è danneggiato, la creazione di tale backup richiede l'utilizzo dell'opzione NO_TRUNCATE:</span><span class="sxs-lookup"><span data-stu-id="c43c5-116">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup   
   WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="c43c5-117">Il backup della parte finale del log è l'ultimo backup applicato nelle sequenze di ripristino seguenti.</span><span class="sxs-lookup"><span data-stu-id="c43c5-117">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="c43c5-118">Sequenza di ripristino</span><span class="sxs-lookup"><span data-stu-id="c43c5-118">Restore Sequence</span></span>  
 <span data-ttu-id="c43c5-119">Per ripristinare il filegroup primario e il filegroup `B`, l'amministratore del database utilizza una sequenza di ripristino senza l'opzione PARTIAL, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c43c5-119">To restore the primary filegroup and filegroup `B`, the database administrator uses a restore sequence without the PARTIAL option, as follows:</span></span>  
  
```  
RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
WITH NORECOVERY  
RESTORE DATABASE adb FILEGROUP='B' FROM backup2   
WITH NORECOVERY  
RESTORE LOG adb FROM backup3 WITH NORECOVERY  
RESTORE LOG adb FROM backup4 WITH NORECOVERY  
RESTORE LOG adb FROM backup5 WITH NORECOVERY  
RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
```  
  
 <span data-ttu-id="c43c5-120">Per i file non ripristinati viene attivata automaticamente la modalità online.</span><span class="sxs-lookup"><span data-stu-id="c43c5-120">The files that are not restored are automatically brought online.</span></span> <span data-ttu-id="c43c5-121">Tutti i filegroup sono ora online.</span><span class="sxs-lookup"><span data-stu-id="c43c5-121">All the filegroups are now online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c43c5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c43c5-122">See Also</span></span>  
 <span data-ttu-id="c43c5-123">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c43c5-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="c43c5-124">[Ripristini a fasi &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c43c5-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="c43c5-125">[Ripristini di file &#40;modello di recupero con registrazione completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="c43c5-125">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="c43c5-126">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c43c5-126">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="c43c5-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c43c5-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
