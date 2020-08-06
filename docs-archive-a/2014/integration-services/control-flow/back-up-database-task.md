---
title: Attività Backup database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.backupdatabasetask.f1
helpviewer_keywords:
- database backups [Integration Services]
- Back Up Database task [Integration Services]
- backing up databases [Integration Services]
- transaction log backups [Integration Services]
- backing up transaction logs [Integration Services]
ms.assetid: b8839d71-13b7-41f2-a434-cb95020e79d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b0980d89cc915121414dd7d3c89be6f4d72eb715
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626210"
---
# <a name="back-up-database-task"></a><span data-ttu-id="89fb3-102">Attività Backup database</span><span class="sxs-lookup"><span data-stu-id="89fb3-102">Back Up Database Task</span></span>
  <span data-ttu-id="89fb3-103">L'attività Backup database consente di eseguire diversi tipi di backup dei database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89fb3-103">The Back Up Database task performs different types of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database backups.</span></span> <span data-ttu-id="89fb3-104">Per altre informazioni, vedere [Backup e ripristino di database SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="89fb3-104">For more information, see [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="89fb3-105">Tramite l'attività Backup database un pacchetto può eseguire il backup di uno o più database.</span><span class="sxs-lookup"><span data-stu-id="89fb3-105">By using the Back Up Database task, a package can back up a single database or multiple databases.</span></span> <span data-ttu-id="89fb3-106">Se si utilizza l'attività per eseguire il backup di un singolo database, sarà possibile scegliere il componente di cui eseguire il backup, ovvero il database o i relativi file e filegroup.</span><span class="sxs-lookup"><span data-stu-id="89fb3-106">If the task backs up only a single database, you can choose the backup component: the database, or its files and filegroups.</span></span>  
  
## <a name="supported-recover-models-and-backup-types"></a><span data-ttu-id="89fb3-107">Modelli di recupero e tipi di backup supportati</span><span class="sxs-lookup"><span data-stu-id="89fb3-107">Supported Recover Models and Backup Types</span></span>  
 <span data-ttu-id="89fb3-108">Nella tabella seguente sono elencati i modelli di recupero e i tipi di backup supportati dall'attività Backup database.</span><span class="sxs-lookup"><span data-stu-id="89fb3-108">The following table lists the recovery models and backup types that the Back Up Database task supports.</span></span>  
  
|<span data-ttu-id="89fb3-109">modello di recupero</span><span class="sxs-lookup"><span data-stu-id="89fb3-109">Recovery model</span></span>|<span data-ttu-id="89fb3-110">Database</span><span class="sxs-lookup"><span data-stu-id="89fb3-110">Database</span></span>|<span data-ttu-id="89fb3-111">Differenziale del database</span><span class="sxs-lookup"><span data-stu-id="89fb3-111">Database differential</span></span>|<span data-ttu-id="89fb3-112">Log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="89fb3-112">Transaction log</span></span>|<span data-ttu-id="89fb3-113">File o differenziale del file</span><span class="sxs-lookup"><span data-stu-id="89fb3-113">File or file differential</span></span>|  
|--------------------|--------------|---------------------------|---------------------|-------------------------------|  
|<span data-ttu-id="89fb3-114">Semplice</span><span class="sxs-lookup"><span data-stu-id="89fb3-114">Simple</span></span>|<span data-ttu-id="89fb3-115">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="89fb3-115">Required</span></span>|<span data-ttu-id="89fb3-116">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="89fb3-116">Optional</span></span>|<span data-ttu-id="89fb3-117">Non supportate</span><span class="sxs-lookup"><span data-stu-id="89fb3-117">Not supported</span></span>|<span data-ttu-id="89fb3-118">Non supportate</span><span class="sxs-lookup"><span data-stu-id="89fb3-118">Not supported</span></span>|  
|<span data-ttu-id="89fb3-119">Full</span><span class="sxs-lookup"><span data-stu-id="89fb3-119">Full</span></span>|<span data-ttu-id="89fb3-120">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="89fb3-120">Required</span></span>|<span data-ttu-id="89fb3-121">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="89fb3-121">Optional</span></span>|<span data-ttu-id="89fb3-122">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="89fb3-122">Required</span></span>|<span data-ttu-id="89fb3-123">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="89fb3-123">Optional</span></span>|  
|<span data-ttu-id="89fb3-124">Registrazione minima delle operazioni bulk</span><span class="sxs-lookup"><span data-stu-id="89fb3-124">Bulk-logged</span></span>|<span data-ttu-id="89fb3-125">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="89fb3-125">Required</span></span>|<span data-ttu-id="89fb3-126">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="89fb3-126">Optional</span></span>|<span data-ttu-id="89fb3-127">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="89fb3-127">Required</span></span>|<span data-ttu-id="89fb3-128">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="89fb3-128">Optional</span></span>|  
  
 <span data-ttu-id="89fb3-129">L'attività Backup database incapsula l'istruzione Transact-SQL BACKUP.</span><span class="sxs-lookup"><span data-stu-id="89fb3-129">The Back Up Database task encapsulates a Transact-SQL BACKUP statement.</span></span> <span data-ttu-id="89fb3-130">Per altre informazioni, vedere [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="89fb3-130">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
## <a name="configuration-of-the-back-up-database-task"></a><span data-ttu-id="89fb3-131">Configurazione dell'attività Backup database</span><span class="sxs-lookup"><span data-stu-id="89fb3-131">Configuration of the Back Up Database Task</span></span>  
 <span data-ttu-id="89fb3-132">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89fb3-132">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="89fb3-133">Questa attività è disponibile nella sezione **Attività di manutenzione** della **casella degli strumenti** di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89fb3-133">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="89fb3-134">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="89fb3-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="89fb3-135">Attività Backup database &#40;Piano di manutenzione&#41;</span><span class="sxs-lookup"><span data-stu-id="89fb3-135">Back Up Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/options-in-the-back-up-database-task-for-maintenance-plan.md)  
  
 <span data-ttu-id="89fb3-136">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="89fb3-136">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="89fb3-137">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="89fb3-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
