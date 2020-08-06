---
title: Ripristinare il database master (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- master database [SQL Server], restoring
ms.assetid: c83d802c-e84e-4458-b3ca-173d9ba32f73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c9cb078b7af60fc5e060bcb144fc9cbaee8ecf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635667"
---
# <a name="restore-the-master-database-transact-sql"></a><span data-ttu-id="0bef7-102">Ripristinare il database master (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0bef7-102">Restore the master Database (Transact-SQL)</span></span>
  <span data-ttu-id="0bef7-103">Questo argomento spiega come ripristinare il database **master** da un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="0bef7-103">This topic explains how to restore the **master** database from a full database backup.</span></span>  
  
### <a name="to-restore-the-master-database"></a><span data-ttu-id="0bef7-104">Per ripristinare il database master</span><span class="sxs-lookup"><span data-stu-id="0bef7-104">To restore the master database</span></span>  
  
1.  <span data-ttu-id="0bef7-105">Avviare l'istanza del server in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="0bef7-105">Start the server instance in single-user mode.</span></span>  
  
     <span data-ttu-id="0bef7-106">Per informazioni su come specificare un parametro di avvio in modalità utente singolo ( **-m**), vedere [Configurare le opzioni di avvio del server &#40;Gestione configurazione SQL Server&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="0bef7-106">For information about how to specify the single-user startup parameter (**-m**), see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
2.  <span data-ttu-id="0bef7-107">Per ripristinare un backup completo del database **master**, usare l'istruzione [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="0bef7-107">To restore a full database backup of **master**, use the following [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="0bef7-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span><span class="sxs-lookup"><span data-stu-id="0bef7-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span></span>  
  
     <span data-ttu-id="0bef7-109">L'opzione REPLACE indica a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] di ripristinare il database specificato anche quando è già presente un database con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="0bef7-109">The REPLACE option instructs [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to restore the specified database even when a database of the same name already exists.</span></span> <span data-ttu-id="0bef7-110">Il database esistente, se presente, viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="0bef7-110">The existing database, if any, is deleted.</span></span> <span data-ttu-id="0bef7-111">In modalità utente singolo è consigliabile immettere l'istruzione RESTORE DATABASE nell' [utilità sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="0bef7-111">In single-user mode, we recommend that you enter the RESTORE DATABASE statement in the [sqlcmd utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="0bef7-112">Per altre informazioni, vedere [Usare l'utilità sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="0bef7-112">For more information, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0bef7-113">Dopo il ripristino del database **master** , l'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] viene arrestata e termina il processo di **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="0bef7-113">After **master** is restored, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] shuts down and terminates the **sqlcmd** process.</span></span> <span data-ttu-id="0bef7-114">Prima di riavviare l'istanza del server, rimuovere il parametro di avvio in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="0bef7-114">Before you restart the server instance, remove the single-user startup parameter.</span></span> <span data-ttu-id="0bef7-115">Per altre informazioni, vedere [Configurazione delle opzioni di avvio del server &#40;Gestione configurazione SQL Server&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="0bef7-115">For more information, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
3.  <span data-ttu-id="0bef7-116">Riavviare l'istanza del server e proseguire con gli altri passaggi di recupero, quali il ripristino di altri database, il collegamento dei database e la correzione delle mancate corrispondenze tra utenti.</span><span class="sxs-lookup"><span data-stu-id="0bef7-116">Restart the server instance and continue other recovery steps such as restoring other databases, attaching databases, and correcting user mismatches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bef7-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="0bef7-117">Example</span></span>  
 <span data-ttu-id="0bef7-118">Nell'esempio seguente viene ripristinato il database `master` nell'istanza predefinita del server.</span><span class="sxs-lookup"><span data-stu-id="0bef7-118">The following example restores the `master` database on the default server instance.</span></span> <span data-ttu-id="0bef7-119">In questo esempio si presuppone che l'istanza del server sia già in esecuzione in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="0bef7-119">The example assumes that the server instance is already running in single-user mode.</span></span> <span data-ttu-id="0bef7-120">Viene avviata l'utilità `sqlcmd` ed eseguita un'istruzione `RESTORE DATABASE` che ripristina un backup completo del database `master` da un dispositivo disco: `Z:\SQLServerBackups\master.bak`.</span><span class="sxs-lookup"><span data-stu-id="0bef7-120">The example starts `sqlcmd` and executes a `RESTORE DATABASE` statement that restores a full database backup of `master` from a disk device: `Z:\SQLServerBackups\master.bak`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bef7-121">Per un'istanza denominata, il comando **sqlcmd** deve specificare l'opzione **-S** _\<ComputerName>_ \\ *\<InstanceName>* .</span><span class="sxs-lookup"><span data-stu-id="0bef7-121">For a named instance, the **sqlcmd** command must specify the **-S**_\<ComputerName>_\\*\<InstanceName>* option.</span></span>  
  
```  
  
      C:\> sqlcmd  
1> RESTORE DATABASE master FROM DISK = 'Z:\SQLServerBackups\master.bak' WITH REPLACE;  
2> GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bef7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bef7-122">See Also</span></span>  
 <span data-ttu-id="0bef7-123">[Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="0bef7-123">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="0bef7-124">[Ripristini di database completi &#40;modello di recupero con registrazione completa&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="0bef7-124">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="0bef7-125">[Risolvere i problemi relativi agli utenti isolati &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0bef7-125">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 <span data-ttu-id="0bef7-126">[Collegamento e scollegamento di un database &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0bef7-126">[Database Detach and Attach &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="0bef7-127">[Ricompilare database di sistema](../databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="0bef7-127">[Rebuild System Databases](../databases/system-databases.md) </span></span>  
 <span data-ttu-id="0bef7-128">[Opzioni di avvio del servizio del motore di database](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span><span class="sxs-lookup"><span data-stu-id="0bef7-128">[Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span></span>  
 <span data-ttu-id="0bef7-129">[Gestione configurazione SQL Server](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0bef7-129">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="0bef7-130">[Backup e ripristino di database di sistema &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0bef7-130">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="0bef7-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0bef7-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="0bef7-132">Avvio di SQL Server in modalità utente singolo</span><span class="sxs-lookup"><span data-stu-id="0bef7-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
