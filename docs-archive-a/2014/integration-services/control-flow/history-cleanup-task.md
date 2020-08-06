---
title: Attività Pulizia contenuto cronologia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.historycleanuptask.f1
helpviewer_keywords:
- history tables [SQL Server]
- History Cleanup task [Integration Services]
ms.assetid: 5defc5b9-dfd3-4859-a7fe-ac8c2b5480f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84bc697b7fb18269fc581cea51e111aebc82c15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623438"
---
# <a name="history-cleanup-task"></a><span data-ttu-id="ac773-102">Attività Pulizia contenuto cronologia</span><span class="sxs-lookup"><span data-stu-id="ac773-102">History Cleanup Task</span></span>
  <span data-ttu-id="ac773-103">L'attività Pulizia contenuto cronologia elimina le voci contenute nelle tabelle di cronologia seguenti del database msdb di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac773-103">The History Cleanup task deletes entries in the following history tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
-   <span data-ttu-id="ac773-104">backupfile</span><span class="sxs-lookup"><span data-stu-id="ac773-104">backupfile</span></span>  
  
-   <span data-ttu-id="ac773-105">backupfilegroup</span><span class="sxs-lookup"><span data-stu-id="ac773-105">backupfilegroup</span></span>  
  
-   <span data-ttu-id="ac773-106">backupmediafamily</span><span class="sxs-lookup"><span data-stu-id="ac773-106">backupmediafamily</span></span>  
  
-   <span data-ttu-id="ac773-107">backupmediaset</span><span class="sxs-lookup"><span data-stu-id="ac773-107">backupmediaset</span></span>  
  
-   <span data-ttu-id="ac773-108">backupset</span><span class="sxs-lookup"><span data-stu-id="ac773-108">backupset</span></span>  
  
-   <span data-ttu-id="ac773-109">restorefile</span><span class="sxs-lookup"><span data-stu-id="ac773-109">restorefile</span></span>  
  
-   <span data-ttu-id="ac773-110">restorefilegroup</span><span class="sxs-lookup"><span data-stu-id="ac773-110">restorefilegroup</span></span>  
  
-   <span data-ttu-id="ac773-111">restorehistory</span><span class="sxs-lookup"><span data-stu-id="ac773-111">restorehistory</span></span>  
  
 <span data-ttu-id="ac773-112">Tramite l'attività Pulizia contenuto cronologia, un pacchetto può eliminare i dati cronologici relativi alle attività di backup e ripristino, ai processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e ai piani di manutenzione del database.</span><span class="sxs-lookup"><span data-stu-id="ac773-112">By using the History Cleanup task, a package can delete historical data related to backup and restore activities, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, and database maintenance plans.</span></span>  
  
 <span data-ttu-id="ac773-113">Questa attività incapsula la stored procedure di sistema sp_delete_backuphistory, a cui passa la data specificata come argomento.</span><span class="sxs-lookup"><span data-stu-id="ac773-113">This task encapsulates the sp_delete_backuphistory system stored procedure and passes the specified date to the procedure as an argument.</span></span> <span data-ttu-id="ac773-114">Per altre informazioni, vedere [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac773-114">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
## <a name="configuration-of-the-history-cleanup-task"></a><span data-ttu-id="ac773-115">Configurazione dell'attività Pulizia contenuto cronologia</span><span class="sxs-lookup"><span data-stu-id="ac773-115">Configuration of the History Cleanup Task</span></span>  
 <span data-ttu-id="ac773-116">L'attività include una proprietà che consente di specificare la data meno recente dei dati da mantenere nelle tabelle della cronologia.</span><span class="sxs-lookup"><span data-stu-id="ac773-116">The task includes a property for specifying the oldest date of data retained in the history tables.</span></span> <span data-ttu-id="ac773-117">È possibile indicare tale data specificando il numero di giorni, settimane, mesi o anni dalla data corrente, affinché l'intervallo venga convertito automaticamente in data dall'attività.</span><span class="sxs-lookup"><span data-stu-id="ac773-117">You can indicate the date by number of days, weeks, months, or years from the current day, and the task automatically translates the interval to a date.</span></span>  
  
 <span data-ttu-id="ac773-118">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac773-118">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="ac773-119">Questa attività è disponibile nella sezione **Attività di manutenzione** della **casella degli strumenti** di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac773-119">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="ac773-120">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="ac773-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="ac773-121">Attività Pulizia contenuto cronologia &#40;Piano di manutenzione&#41;</span><span class="sxs-lookup"><span data-stu-id="ac773-121">History Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/history-cleanup-task-maintenance-plan.md)  
  
 <span data-ttu-id="ac773-122">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="ac773-122">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="ac773-123">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="ac773-123">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac773-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac773-124">See Also</span></span>  
 <span data-ttu-id="ac773-125">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="ac773-125">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="ac773-126">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="ac773-126">Control Flow</span></span>](control-flow.md)  
  
  
