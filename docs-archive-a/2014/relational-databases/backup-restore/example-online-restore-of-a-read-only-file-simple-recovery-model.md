---
title: 'Esempio: Ripristino online di un file di sola lettura (modello di recupero con registrazione minima) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restore sequences [SQL Server], online
- online restores [SQL Server], simple recovery model
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: 0c691fc6-9865-46a7-b055-8097424492d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d84c920a2cb40866ba106b4d30d8e24c4caea611
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726004"
---
# <a name="example-online-restore-of-a-read-only-file-simple-recovery-model"></a><span data-ttu-id="ddee5-102">Esempio: Ripristino online di un file di sola lettura (modello di recupero con registrazione minima)</span><span class="sxs-lookup"><span data-stu-id="ddee5-102">Example: Online Restore of a Read-Only File (Simple Recovery Model)</span></span>
  <span data-ttu-id="ddee5-103">Le informazioni in questo argomento sono rilevanti per i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che utilizzano il modello di recupero con registrazione minima e che contengono un filegroup di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ddee5-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span> <span data-ttu-id="ddee5-104">Il modello di recupero con registrazione minima consente di ripristinare online un file di sola lettura, se è disponibile un backup del file eseguito dopo la prima conversione del file in file di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ddee5-104">Under the simple recovery model, a read-only file can be restored online if a file backup exists that was taken since the file became read-only for the last time.</span></span>  
  
 <span data-ttu-id="ddee5-105">In questo esempio un database denominato `adb` contiene tre filegroup.</span><span class="sxs-lookup"><span data-stu-id="ddee5-105">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="ddee5-106">Il filegroup `A` è di lettura/scrittura mentre i filegroup `B` e `C` sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ddee5-106">Filegroup `A` is read/write, and filegroups `B` and `C` are read-only.</span></span> <span data-ttu-id="ddee5-107">Inizialmente, tutti i filegroup sono online.</span><span class="sxs-lookup"><span data-stu-id="ddee5-107">Initially, all of the filegroups are online.</span></span> <span data-ttu-id="ddee5-108">È necessario ripristinare il file di sola lettura `B`del filegroup `b1`.</span><span class="sxs-lookup"><span data-stu-id="ddee5-108">A read-only file in filegroup `B`, `b1`, has to be restored.</span></span> <span data-ttu-id="ddee5-109">Per ripristinarlo, l'amministratore del database può utilizzare un backup eseguito dopo che il file è diventato di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ddee5-109">The database administrator can restore it by using a backup that was taken after the file became read-only.</span></span> <span data-ttu-id="ddee5-110">Per tutta la durata del ripristino il filegroup `B` sarà offline, ma il resto del database resterà online.</span><span class="sxs-lookup"><span data-stu-id="ddee5-110">For the duration of the restore, filegroup `B` will be offline, but the remainder of the database will remain online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="ddee5-111">Sequenza di ripristino</span><span class="sxs-lookup"><span data-stu-id="ddee5-111">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ddee5-112">La sintassi di una sequenza di ripristino online è la stessa di una sequenza di ripristino offline.</span><span class="sxs-lookup"><span data-stu-id="ddee5-112">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="ddee5-113">Per ripristinare il file, l'amministratore del database utilizza la sequenza di ripristino seguente:</span><span class="sxs-lookup"><span data-stu-id="ddee5-113">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup   
WITH RECOVERY  
```  
  
 <span data-ttu-id="ddee5-114">Il file è ora online.</span><span class="sxs-lookup"><span data-stu-id="ddee5-114">The file is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="ddee5-115">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="ddee5-115">Additional Examples</span></span>  
  
-   [<span data-ttu-id="ddee5-116">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="ddee5-116">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="ddee5-117">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="ddee5-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="ddee5-118">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="ddee5-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="ddee5-119">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="ddee5-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="ddee5-120">Esempio: Ripristino online di un file di lettura/scrittura &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="ddee5-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="ddee5-121">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="ddee5-121">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="ddee5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddee5-122">See Also</span></span>  
 <span data-ttu-id="ddee5-123">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ddee5-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="ddee5-124">[Ripristini a fasi &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ddee5-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="ddee5-125">[Ripristini di file &#40;modello di recupero con registrazione minima&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="ddee5-125">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="ddee5-126">[Panoramica del ripristino e del recupero &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ddee5-126">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="ddee5-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ddee5-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
