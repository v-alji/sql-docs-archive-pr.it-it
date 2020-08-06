---
title: Oggetto Backup Device di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Backup Device
- Backup Device object
ms.assetid: 52e7febf-d5e0-4674-945b-aacc40a9ad6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e3126310ad31dcc153fc79508dbfaccf86f5da78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627208"
---
# <a name="sql-server-backup-device-object"></a><span data-ttu-id="e8148-102">Oggetto Backup Device di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8148-102">SQL Server, Backup Device Object</span></span>
  <span data-ttu-id="e8148-103">L'oggetto **Backup Device** include contatori per il monitoraggio dei dispositivi di backup di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usati per le operazioni di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="e8148-103">The **Backup Device** object provides counters to monitor Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices used for backup and restore operations.</span></span> <span data-ttu-id="e8148-104">Monitorare i dispositivi di backup se si desidera determinare la velocità effettiva oppure lo stato di avanzamento e le prestazioni delle operazioni di backup e ripristino per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8148-104">Monitor backup devices when you want to determine the throughput or the progress and performance of your backup and restore operations on a per device basis.</span></span> <span data-ttu-id="e8148-105">Per monitorare la velocità effettiva di un'operazione di backup o ripristino dell'intero database, usare il contatore **Velocità effettiva backup o ripristino/sec** dell'oggetto **Databases** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8148-105">To monitor the throughput of the entire database backup or restore operation, use the **Backup/Restore Throughput/sec** counter of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Databases** object.</span></span> <span data-ttu-id="e8148-106">Per altre informazioni, vedere [SQL Server, Databases Object](sql-server-databases-object.md).</span><span class="sxs-lookup"><span data-stu-id="e8148-106">For more information, see [SQL Server, Databases Object](sql-server-databases-object.md).</span></span>  
  
 <span data-ttu-id="e8148-107">Nella tabella seguente viene descritto il contatore **Backup Device** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8148-107">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Backup Device** counter.</span></span>  
  
|<span data-ttu-id="e8148-108">Contatore dell'oggetto Backup Device di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8148-108">SQL Server Backup Device counters</span></span>|<span data-ttu-id="e8148-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8148-109">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="e8148-110">**Byte/sec velocità effettiva dispositivo**</span><span class="sxs-lookup"><span data-stu-id="e8148-110">**Device Throughput Bytes/sec**</span></span>|<span data-ttu-id="e8148-111">Velocità effettiva delle operazioni di lettura e scrittura (in byte al secondo) di un dispositivo di backup utilizzato durante il backup o il ripristino dei database.</span><span class="sxs-lookup"><span data-stu-id="e8148-111">Throughput of read and write operations (in bytes per second) for a backup device used when backing up or restoring databases.</span></span> <span data-ttu-id="e8148-112">Il contatore è disponibile solo durante l'esecuzione dell'operazione di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="e8148-112">This counter exists only while the backup or restore operation is executing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8148-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8148-113">See Also</span></span>  
 <span data-ttu-id="e8148-114">[Dispositivi di backup &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e8148-114">[Backup Devices &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="e8148-115">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="e8148-115">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
