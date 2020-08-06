---
title: Backup e ripristino di pacchetti (servizio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, backup and restore
- backing up packages [Integration Services]
- packages [Integration Services], backup and restore
- SQL Server Integration Services packages, backup and restore
- restoring packages [Integration Services]
- Integration Services packages, backup and restore
ms.assetid: c67d3b83-a6c8-40de-920f-9236de4ac87f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c4cd6f3856b69485c01e4b38d89e2f7e2ec56f74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636796"
---
# <a name="package-backup-and-restore-ssis-service"></a><span data-ttu-id="7309d-102">Backup e ripristino di pacchetti (servizio SSIS)</span><span class="sxs-lookup"><span data-stu-id="7309d-102">Package Backup and Restore (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="7309d-103">In questo argomento viene illustrato il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un servizio Windows per la gestione dei pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7309d-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="7309d-104">supporta il servizio per la compatibilità con le versioni precedenti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7309d-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="7309d-105">A partire da [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], è possibile gestire oggetti come i pacchetti del server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="7309d-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="7309d-106">I pacchetti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] possono essere salvati nel file system o in msdb, un database di sistema di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7309d-106">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages can be saved to the file system or msdb, a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] system database.</span></span> <span data-ttu-id="7309d-107">È possibile eseguire il backup e il ripristino dei pacchetti salvati in msdb usando le funzionalità di backup e ripristino di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7309d-107">Packages saved to msdb can be backed up and restored using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore features.</span></span>  
  
 <span data-ttu-id="7309d-108">Per altre informazioni sul backup e sul ripristino del database msdb, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7309d-108">For more information about backing up and restoring the msdb database, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7309d-109">Backup e ripristino di database SQL Server</span><span class="sxs-lookup"><span data-stu-id="7309d-109">Back Up and Restore of SQL Server Databases</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
-   [<span data-ttu-id="7309d-110">Backup e ripristino di database di sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7309d-110">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="7309d-111">include l'utilità del prompt dei comandi **dtutil** (dtutil.exec), che può essere usata per gestire i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7309d-111">includes the **dtutil** command-prompt utility (dtutil.exec), which you can use to manage packages.</span></span> <span data-ttu-id="7309d-112">Per altre informazioni, vedere [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="7309d-112">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7309d-113">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="7309d-113">Configuration Files</span></span>  
 <span data-ttu-id="7309d-114">I file di configurazione dei pacchetti vengono archiviati nel file system.</span><span class="sxs-lookup"><span data-stu-id="7309d-114">Any configuration files that the packages include are stored in the file system.</span></span> <span data-ttu-id="7309d-115">Questi file non vengono tuttavia inclusi nel backup del database msdb. Di conseguenza, è necessario assicurarsi che il backup di questi file venga eseguito regolarmente nell'ambito del piano per la sicurezza dei pacchetti salvati in msdb.</span><span class="sxs-lookup"><span data-stu-id="7309d-115">These files are not backed up when you back up the msdb database; therefore, you should make sure that the configuration files are backed up regularly as part of your plan for securing packages saved to msdb.</span></span> <span data-ttu-id="7309d-116">Per includere configurazioni nel backup del database msdb, è consigliabile usare il tipo di configurazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] invece delle configurazioni basate su file.</span><span class="sxs-lookup"><span data-stu-id="7309d-116">To include configurations in the backup of the msdb database, you should consider using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration type instead of file-based configurations.</span></span>  
  
## <a name="packages-stored-in-the-file-system"></a><span data-ttu-id="7309d-117">Pacchetti archiviati nel file system</span><span class="sxs-lookup"><span data-stu-id="7309d-117">Packages Stored in the File System</span></span>  
 <span data-ttu-id="7309d-118">Nel piano per il backup del file system del server deve essere incluso il backup dei pacchetti salvati nel file system.</span><span class="sxs-lookup"><span data-stu-id="7309d-118">The backup of packages that are saved to the file system should be included in the plan for backing up the file system of the server.</span></span> <span data-ttu-id="7309d-119">Nel file di configurazione del servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , il cui nome predefinito è MsDtsSrvr.ini.xml, sono elencate le cartelle del server di cui il servizio esegue il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7309d-119">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service configuration file, which has the default name MsDtsSrvr.ini.xml, lists the folders on the server that the service monitors.</span></span> <span data-ttu-id="7309d-120">Assicurarsi di eseguire il backup di queste cartelle.</span><span class="sxs-lookup"><span data-stu-id="7309d-120">You should make sure these folders are backed up.</span></span> <span data-ttu-id="7309d-121">I pacchetti potrebbero essere archiviati in altre cartelle del server. Assicurarsi di includere nel backup anche queste cartelle.</span><span class="sxs-lookup"><span data-stu-id="7309d-121">Additionally, packages may be stored in other folders on the server and you should make sure to include these folders in the backup.</span></span>  
  
  
