---
title: 'Esempio: Ripristino online di un file di sola lettura (modello di recupero con registrazione completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- online restores [SQL Server], full recovery model
- restore sequences [SQL Server], online
ms.assetid: 7ea2d2af-086f-48dc-9636-38dc194c7090
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f493c88d64e6ed22e44f33f1442ae581daa8ed4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726007"
---
# <a name="example-online-restore-of-a-read-only-file-full-recovery-model"></a><span data-ttu-id="5f4b3-102">Esempio: Ripristino online di un file di sola lettura (modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="5f4b3-102">Example: Online Restore of a Read-Only File (Full Recovery Model)</span></span>
  <span data-ttu-id="5f4b3-103">Le informazioni contenute in questo argomento interessano i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] basati sul modello di recupero con registrazione completa che includono più file o filegroup.</span><span class="sxs-lookup"><span data-stu-id="5f4b3-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="5f4b3-104">In questo esempio un database denominato `adb`, che utilizza il modello di recupero con registrazione completa, contiene tre filegroup.</span><span class="sxs-lookup"><span data-stu-id="5f4b3-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="5f4b3-105">Il filegroup `A` è in lettura/scrittura, mentre i filegroup `B` e `C` sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5f4b3-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="5f4b3-106">Inizialmente, tutti i filegroup sono online.</span><span class="sxs-lookup"><span data-stu-id="5f4b3-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="5f4b3-107">È necessario ripristinare il file di sola lettura `b1`nel filegroup `B` del database `adb` .</span><span class="sxs-lookup"><span data-stu-id="5f4b3-107">A read-only file, `b1`, in filegroup `B` of database `adb` has to be restored.</span></span> <span data-ttu-id="5f4b3-108">Dato che è stato eseguito un backup dopo che il file è diventato di sola lettura, i backup del log non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="5f4b3-108">A backup was taken since the file became read-only; therefore, log backups are not required.</span></span> <span data-ttu-id="5f4b3-109">Il filegroup `B` sarà offline per l'intera durata del ripristino, mentre la rimanente parte del database rimarrà online.</span><span class="sxs-lookup"><span data-stu-id="5f4b3-109">Filegroup `B` is offline for the duration of the restore, but the remainder of the database remains online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="5f4b3-110">Sequenza di ripristino</span><span class="sxs-lookup"><span data-stu-id="5f4b3-110">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f4b3-111">La sintassi di una sequenza di ripristino online è la stessa di una sequenza di ripristino offline.</span><span class="sxs-lookup"><span data-stu-id="5f4b3-111">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="5f4b3-112">Per ripristinare il file, l'amministratore del database utilizza la sequenza di ripristino seguente:</span><span class="sxs-lookup"><span data-stu-id="5f4b3-112">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup  
WITH RECOVERY   
```  
  
 <span data-ttu-id="5f4b3-113">Il filegroup B è ora online.</span><span class="sxs-lookup"><span data-stu-id="5f4b3-113">Filegroup B is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="5f4b3-114">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="5f4b3-114">Additional Examples</span></span>  
  
-   [<span data-ttu-id="5f4b3-115">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="5f4b3-115">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5f4b3-116">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="5f4b3-116">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5f4b3-117">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="5f4b3-117">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5f4b3-118">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="5f4b3-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="5f4b3-119">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="5f4b3-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="5f4b3-120">Esempio: Ripristino online di un file di lettura/scrittura &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="5f4b3-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f4b3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f4b3-121">See Also</span></span>  
 <span data-ttu-id="5f4b3-122">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f4b3-122">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="5f4b3-123">[Panoramica del ripristino e del recupero &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f4b3-123">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="5f4b3-124">[Ripristini di file &#40;modello di recupero con registrazione completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="5f4b3-124">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="5f4b3-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5f4b3-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
