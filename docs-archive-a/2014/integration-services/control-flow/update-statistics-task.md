---
title: Attività Aggiorna statistiche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.updatestatisticstask.f1
helpviewer_keywords:
- updating statistics
- Update Statistics task [Integration Services]
ms.assetid: 0247483b-f092-4511-8fa8-3610108bd1bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1507ada1e4fa087901383930fce4996c191fb553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623417"
---
# <a name="update-statistics-task"></a><span data-ttu-id="53196-102">Attività Aggiorna statistiche</span><span class="sxs-lookup"><span data-stu-id="53196-102">Update Statistics Task</span></span>
  <span data-ttu-id="53196-103">L'attività Aggiorna statistiche consente di aggiornare le informazioni sulla distribuzione dei valori di chiave per uno o più gruppi o raccolte di statistiche nella tabella o vista indicizzata specificata.</span><span class="sxs-lookup"><span data-stu-id="53196-103">The Update Statistics task updates information about the distribution of key values for one or more statistics groups (collections) in the specified table or indexed view.</span></span> <span data-ttu-id="53196-104">Per altre informazioni, vedere l'articolo relativo alle [statistiche](../../relational-databases/statistics/statistics.md).</span><span class="sxs-lookup"><span data-stu-id="53196-104">For more information, see [Statistics](../../relational-databases/statistics/statistics.md).</span></span>  
  
 <span data-ttu-id="53196-105">Tramite l'attività Aggiorna statistiche un pacchetto può aggiornare le statistiche per uno o più database.</span><span class="sxs-lookup"><span data-stu-id="53196-105">By using the Update Statistics task, a package can update statistics for a single database or multiple databases.</span></span> <span data-ttu-id="53196-106">Se si utilizza l'attività per aggiornare le statistiche in un singolo database, sarà possibile scegliere le viste e le tabelle di cui aggiornare le statistiche.</span><span class="sxs-lookup"><span data-stu-id="53196-106">If the task updates only the statistics in a single database, you can choose the views or the tables whose statistics the task updates.</span></span> <span data-ttu-id="53196-107">È possibile configurare l'attività in modo da aggiornare tutte le statistiche, solo le statistiche delle colonne oppure solo le statistiche degli indici.</span><span class="sxs-lookup"><span data-stu-id="53196-107">You can configure the update to update all statistics, column statistics only, or index statistics only.</span></span>  
  
 <span data-ttu-id="53196-108">L'attività incapsula un'istruzione UPDATE STATISTICS che include le clausole e gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="53196-108">This task encapsulates an UPDATE STATISTICS statement, including the following arguments and clauses:</span></span>  
  
-   <span data-ttu-id="53196-109">Argomento *table_name* o *view_name* .</span><span class="sxs-lookup"><span data-stu-id="53196-109">The *table_name* or *view_name* argument.</span></span>  
  
-   <span data-ttu-id="53196-110">Se l'aggiornamento interessa tutte le statistiche, è implicita la clausola WITH ALL.</span><span class="sxs-lookup"><span data-stu-id="53196-110">If the update applies to all statistics, the WITH ALL clause is implied.</span></span>  
  
-   <span data-ttu-id="53196-111">Se l'aggiornamento interessa solo le colonne, viene inclusa la clausola WITH COLUMN.</span><span class="sxs-lookup"><span data-stu-id="53196-111">If the update applies only to columns, the WITH COLUMN clause is included.</span></span>  
  
-   <span data-ttu-id="53196-112">Se l'aggiornamento interessa solo gli indici, viene inclusa la clausola WITH INDEX.</span><span class="sxs-lookup"><span data-stu-id="53196-112">If the update applies only to indexes, the WITH INDEX clause is included.</span></span>  
  
 <span data-ttu-id="53196-113">Se l'attività Aggiorna statistiche viene utilizzata per aggiornare statistiche in più database, eseguirà più istruzioni UPDATE STATISTICS, una per ogni tabella o vista.</span><span class="sxs-lookup"><span data-stu-id="53196-113">If the Update Statistics task updates statistics in multiple databases, the task runs multiple UPDATE STATISTICS statements, one for each table or view.</span></span> <span data-ttu-id="53196-114">Tutte le istanze dell'istruzione UPDATE STATISTICS usano la stessa clausola ma valori di *table_name* o *view_name* diversi.</span><span class="sxs-lookup"><span data-stu-id="53196-114">All instances of UPDATE STATISTICS use the same clause, but different *table_name* or *view_name* values.</span></span> <span data-ttu-id="53196-115">Per altre informazioni, vedere [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) e [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53196-115">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) and [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="53196-116">Il tempo richiesto dall'attività per creare l'istruzione Transact-SQL da eseguire è proporzionale al numero delle statistiche da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="53196-116">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of statistics the task updates.</span></span> <span data-ttu-id="53196-117">Se l'attività è configurata per l'aggiornamento delle statistiche in tutte le tabelle e le viste di un database con un numero elevato di indici oppure per l'aggiornamento delle statistiche in più database, la generazione dell'istruzione Transact-SQL potrebbe richiedere una quantità di tempo considerevole.</span><span class="sxs-lookup"><span data-stu-id="53196-117">If the task is configured to update statistics in all the tables and views in a database with a large number of indexes, or to update statistics in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-update-statistics-task"></a><span data-ttu-id="53196-118">Configurazione dell'attività Aggiorna statistiche</span><span class="sxs-lookup"><span data-stu-id="53196-118">Configuration of the Update Statistics Task</span></span>  
 <span data-ttu-id="53196-119">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53196-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="53196-120">Questa attività è disponibile nella sezione **Attività di manutenzione** della **casella degli strumenti** di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53196-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="53196-121">Per informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="53196-121">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="53196-122">Attività Aggiorna statistiche &#40;Piano di manutenzione&#41;</span><span class="sxs-lookup"><span data-stu-id="53196-122">Update Statistics Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/update-statistics-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="53196-123">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="53196-123">Related Tasks</span></span>  
 <span data-ttu-id="53196-124">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="53196-124">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="53196-125">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="53196-125">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="53196-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53196-126">See Also</span></span>  
 <span data-ttu-id="53196-127">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="53196-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="53196-128">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="53196-128">Control Flow</span></span>](control-flow.md)  
  
  
