---
title: I file di backup devono trovarsi in dispositivi separati dai file di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7039bebb-1f25-4cf3-81f1-393dfb78da12
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d5eff9cb3139e1e1043f99ba63d11160b1010c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716820"
---
# <a name="backup-files-must-be-on-separate-devices-from-the-database-files"></a><span data-ttu-id="0a4f1-102">Posizionamento dei file di backup in dispositivi separati rispetto ai file di database</span><span class="sxs-lookup"><span data-stu-id="0a4f1-102">Backup Files Must Be on Separate Devices from the Database Files</span></span>
  <span data-ttu-id="0a4f1-103">Questa regola consente di controllare se i file di database si trovano in dispositivi separati rispetto ai file di backup.</span><span class="sxs-lookup"><span data-stu-id="0a4f1-103">This rule checks whether database files are on devices separate from the backup files.</span></span> <span data-ttu-id="0a4f1-104">Se file di database e i file di backup sono archiviati nello stesso dispositivo e si verifica un errore nel dispositivo, il database e i backup non saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="0a4f1-104">If database files and backup files are on the same device and the device fails, the database and backups will be unavailable.</span></span> <span data-ttu-id="0a4f1-105">L'archiviazione dei file di database e di backup in dispositivi distinti, inoltre, consente di ottimizzare le prestazioni di I/O per l'utilizzo del database in un ambiente di produzione e per la scrittura dei backup.</span><span class="sxs-lookup"><span data-stu-id="0a4f1-105">Also, putting the database and backup files on the separate devices optimizes the I/O performance for both the production use of the database and the writing of backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="0a4f1-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="0a4f1-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="0a4f1-107">È consigliabile archiviare il database e i backup in dispositivi di backup distinti.</span><span class="sxs-lookup"><span data-stu-id="0a4f1-107">We strongly recommend that you put the database and backups on separate backup devices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a4f1-108">Questi criteri non sono in grado di rilevare dispositivi fisici separati mediante punti di montaggio.</span><span class="sxs-lookup"><span data-stu-id="0a4f1-108">This policy cannot detect separate physical devices through mount points.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="0a4f1-109">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="0a4f1-109">For More Information</span></span>  
 [<span data-ttu-id="0a4f1-110">Dispositivi di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0a4f1-110">Backup Devices &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/backup-devices-sql-server.md)  
  
 [<span data-ttu-id="0a4f1-111">Backup e ripristino di database SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a4f1-111">Back Up and Restore of SQL Server Databases</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a4f1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a4f1-112">See Also</span></span>  
 [<span data-ttu-id="0a4f1-113">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="0a4f1-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
