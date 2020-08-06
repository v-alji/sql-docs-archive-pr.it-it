---
title: Eseguire il backup in un set di supporti con mirroring (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 5fc43a5d-dfd6-4c53-a4ef-3c8da23ccc81
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 255a3c190139c029f5211dcab9780b6d07d975a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629442"
---
# <a name="back-up-to-a-mirrored-media-set-transact-sql"></a><span data-ttu-id="f2d56-102">Backup in un set di supporti con mirroring (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f2d56-102">Back Up to a Mirrored Media Set (Transact-SQL)</span></span>
  <span data-ttu-id="f2d56-103">In questo argomento viene descritto come utilizzare l' [!INCLUDE[tsql](../../includes/tsql-md.md)] istruzione [backup](/sql/t-sql/statements/backup-transact-sql) per specificare un set di supporti con mirroring durante l'esecuzione del backup di un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="f2d56-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to specify a mirrored media set when backing up a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="f2d56-104">Nell'istruzione BACKUP specificare il primo mirror nella clausola TO,</span><span class="sxs-lookup"><span data-stu-id="f2d56-104">In your BACKUP statement, specify the first mirror in the TO clause.</span></span> <span data-ttu-id="f2d56-105">quindi specificare ogni mirror nella relativa clausola MIRROR TO.</span><span class="sxs-lookup"><span data-stu-id="f2d56-105">Then, specify each mirror in its own MIRROR TO clause.</span></span> <span data-ttu-id="f2d56-106">È necessario che le clausole TO e MIRROR TO specifichino lo stesso numero e tipo di dispositivo di backup.</span><span class="sxs-lookup"><span data-stu-id="f2d56-106">The TO and MIRROR TO clauses must specify the same number and type of backup devices.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2d56-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2d56-107">Example</span></span>  
 <span data-ttu-id="f2d56-108">Nell'esempio seguente viene creato il set di supporti con mirroring indicato nella figura precedente e viene eseguito il backup del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] su entrambi i mirror.</span><span class="sxs-lookup"><span data-stu-id="f2d56-108">The following example creates the mirrored media set illustrated in the previous illustration and backs up the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to both mirrors.</span></span>  
  
```  
BACKUP DATABASE AdventureWorks2012  
TO TAPE = '\\.\tape0', TAPE = '\\.\tape1'  
MIRROR TO TAPE = '\\.\tape2', TAPE = '\\.\tape3'  
WITH  
    FORMAT,  
    MEDIANAME = 'AdventureWorks2012Set1';  
GO  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="f2d56-109">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="f2d56-109">Related Tasks</span></span>  
 <span data-ttu-id="f2d56-110">**Per eseguire il ripristino da un backup con mirroring**</span><span class="sxs-lookup"><span data-stu-id="f2d56-110">**To restore from a mirrored backup**</span></span>  
  
-   [<span data-ttu-id="f2d56-111">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f2d56-111">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="f2d56-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2d56-112">See Also</span></span>  
 <span data-ttu-id="f2d56-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f2d56-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="f2d56-114">Set di supporti di backup con mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f2d56-114">Mirrored Backup Media Sets &#40;SQL Server&#41;</span></span>](mirrored-backup-media-sets-sql-server.md)  
  
  
