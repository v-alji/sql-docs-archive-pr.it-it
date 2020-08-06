---
title: Risolvere i problemi relativi a un'operazione di aggiunta file non riuscita (Gruppi di disponibilità AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary databases [SQL Server], Availability Groups
- Availability Groups [SQL Server], troubleshooting
ms.assetid: 31ceaebf-864b-4dd0-9112-0d047b0316ad
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2551080c214f18473caa71a3e17797c34fcc943a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724951"
---
# <a name="troubleshoot-a-failed-add-file-operation-alwayson-availability-groups"></a><span data-ttu-id="a0c0b-102">Risolvere i problemi relativi a una operazione di aggiunta file non riuscita (Gruppi di disponibilità AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="a0c0b-102">Troubleshoot a Failed Add-File Operation (AlwaysOn Availability Groups)</span></span>
  <span data-ttu-id="a0c0b-103">In alcune distribuzioni del gruppo di disponibilità AlwaysOn i percorsi di file nel sistema in cui è ospitata la replica primaria sono diversi da quelli nei sistemi in cui è ospitata una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="a0c0b-103">In some AlwaysOn availability group deployments, file paths differ between the system that hosts the primary replica and systems that host a secondary replica.</span></span> <span data-ttu-id="a0c0b-104">Se il percorso di file di un'operazione di aggiunta di file non esiste in una replica secondaria, tale operazione non verrà completata nel database primario.</span><span class="sxs-lookup"><span data-stu-id="a0c0b-104">If the file path of an add-file operation does not exist on a secondary replica, the add-file operation will succeed on the primary database.</span></span> <span data-ttu-id="a0c0b-105">Tuttavia, l'operazione di aggiunta di file determinerà la sospensione del database secondario.</span><span class="sxs-lookup"><span data-stu-id="a0c0b-105">But the add-file operation will cause the secondary database to be suspended.</span></span> <span data-ttu-id="a0c0b-106">Questa situazione, a sua volta, potrebbe causare l'attivazione dello stato NON IN SINCRONIZZAZIONE della replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="a0c0b-106">This, in turn, causes the secondary replica to enter the NOT SYNCHRONIZING state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0c0b-107">Se possibile, è consigliabile che il percorso del file di un determinato database secondario, inclusa la lettera di unità, sia identico a quello del database primario corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a0c0b-107">We recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span>  
  
## <a name="problem-resolution"></a><span data-ttu-id="a0c0b-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="a0c0b-108">Problem Resolution</span></span>  
 <span data-ttu-id="a0c0b-109">Per risolvere questo problema, il proprietario del database deve completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0c0b-109">To resolve this problem the database owner must complete the following steps:</span></span>  
  
1.  <span data-ttu-id="a0c0b-110">Rimuovere il database secondario dal gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a0c0b-110">Remove the secondary database from the availability group.</span></span> <span data-ttu-id="a0c0b-111">Per altre informazioni, vedere [Rimuovere un database secondario da un gruppo di disponibilità &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a0c0b-111">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="a0c0b-112">Sul database secondario esistente, ripristinare un backup completo del filegroup che contiene il file aggiunto al database secondario, utilizzando WITH NORECOVERY e WITH MOVE (specificando il percorso di file sull'istanza del server che ospita la replica secondaria).</span><span class="sxs-lookup"><span data-stu-id="a0c0b-112">On the existing secondary database, restore a full backup of the filegroup that contains the added file to the secondary database, using WITH NORECOVERY and WITH MOVE (specifying the file path on the server instance that hosts the secondary replica).</span></span> <span data-ttu-id="a0c0b-113">Per altre informazioni, vedere [Ripristinare un database in una nuova posizione &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a0c0b-113">For more information, see [Restore a Database to a New Location &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="a0c0b-114">Eseguire il backup del log delle transazioni che contiene l'operazione di aggiunta file nel database primario e ripristinare manualmente il backup del log nel database secondario con WITH NORECOVERY e WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="a0c0b-114">Back up the transaction log that contains the add-file operation on the primary database, and manually restore the log backup on the secondary database using WITH NORECOVERY and WITH MOVE.</span></span>  
  
4.  <span data-ttu-id="a0c0b-115">Preparare il database secondario per creare di nuovo un join del gruppo di disponibilità, ripristinando, WITH NO RECOVERY, qualsiasi altro backup del log in sospeso dal database primario.</span><span class="sxs-lookup"><span data-stu-id="a0c0b-115">Prepare the secondary database for re-joining the availability group, by restoring, WITH NO RECOVERY, any other outstanding log backups from the primary database.</span></span>  
  
5.  <span data-ttu-id="a0c0b-116">Unire nuovamente in join il database secondario al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a0c0b-116">Rejoin the secondary database to the availability group.</span></span> <span data-ttu-id="a0c0b-117">Per altre informazioni, vedere [Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a0c0b-117">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c0b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0c0b-118">See Also</span></span>  
 <span data-ttu-id="a0c0b-119">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a0c0b-119">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="a0c0b-120">[Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a0c0b-120">[Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="a0c0b-121">[Risolvere i problemi relativi agli utenti isolati &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a0c0b-121">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 [<span data-ttu-id="a0c0b-122">Risolvere i problemi di Gruppi di disponibilità AlwaysOn &#40;di configurazione SQL Server eliminati&#41;</span><span class="sxs-lookup"><span data-stu-id="a0c0b-122">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
  
