---
title: Finestra Thread
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Threads Window [Transact-SQL]
ms.assetid: e153f619-0049-4162-9076-c24a454f3278
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f3460c892c182996a753c2a16076418a6b2008f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714136"
---
# <a name="threads-window"></a><span data-ttu-id="f5f62-102">Finestra Thread</span><span class="sxs-lookup"><span data-stu-id="f5f62-102">Threads Window</span></span>
  <span data-ttu-id="f5f62-103">Nella finestra **Thread** vengono visualizzate informazioni sul thread del [!INCLUDE[ssDE](../../includes/ssde-md.md)] usato dalla sessione dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di cui viene eseguito il debug.</span><span class="sxs-lookup"><span data-stu-id="f5f62-103">The **Threads** window displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] thread that is used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor session that is being debugged.</span></span> <span data-ttu-id="f5f62-104">Per visualizzare le informazioni sul thread, è necessario utilizzare la modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="f5f62-104">You must be in debug mode to display the thread information.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="f5f62-105">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="f5f62-105">Task List</span></span>  
 <span data-ttu-id="f5f62-106">**Per accedere alla finestra Thread**</span><span class="sxs-lookup"><span data-stu-id="f5f62-106">**To access the Threads window**</span></span>  
  
-   <span data-ttu-id="f5f62-107">Scegliere **Finestre** dal menu **Debug**, quindi fare clic su **Thread**.</span><span class="sxs-lookup"><span data-stu-id="f5f62-107">On the **Debug** menu, click **Windows**, and then click **Threads**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="f5f62-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="f5f62-108">Columns</span></span>  
 <span data-ttu-id="f5f62-109">**ID**</span><span class="sxs-lookup"><span data-stu-id="f5f62-109">**ID**</span></span>  
 <span data-ttu-id="f5f62-110">Numero di identificazione univoco assegnato al thread dal debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5f62-110">Is a unique identifying number that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger assigns to the thread.</span></span> <span data-ttu-id="f5f62-111">È possibile ottenere ulteriori informazioni sul thread selezionando una riga nella vista a gestione dinamica sys.dm_os_threads.</span><span class="sxs-lookup"><span data-stu-id="f5f62-111">You can find more information about the thread by selecting a row from the sys.dm_os_threads dynamic management view.</span></span>  
  
 <span data-ttu-id="f5f62-112">Se non è attiva la modalità lightweight pooling, selezionare la riga in cui il valore di os_thread_id corrisponde al valore specificato nella colonna **ID** .</span><span class="sxs-lookup"><span data-stu-id="f5f62-112">If you are not running in lightweight pooling mode, select the row in which the value in os_thread_id matches the value in the **ID** column.</span></span> <span data-ttu-id="f5f62-113">Se è attiva la modalità lightweight pooling, selezionare la riga in cui il valore di fiber_context_address corrisponde al valore specificato nella colonna **ID** .</span><span class="sxs-lookup"><span data-stu-id="f5f62-113">If you are running in lightweight pooling mode, select the row in which the value in fiber_context_address matches the value in the **ID** column.</span></span>  
  
 <span data-ttu-id="f5f62-114">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f5f62-114">**Name**</span></span>  
 <span data-ttu-id="f5f62-115">Consente di visualizzare informazioni sulla sessione del [!INCLUDE[ssDE](../../includes/ssde-md.md)] in formato **NomeComputer/NomeIstanza [SPID]** .</span><span class="sxs-lookup"><span data-stu-id="f5f62-115">Displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] session in the format **ComputerName/InstanceName [SPID]**.</span></span>  
  
 <span data-ttu-id="f5f62-116">**NomeComputer**</span><span class="sxs-lookup"><span data-stu-id="f5f62-116">**ComputerName**</span></span>  
 <span data-ttu-id="f5f62-117">Nome del computer che esegue l'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] a cui è connessa la sessione dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="f5f62-117">The name of the computer that is running the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="f5f62-118">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="f5f62-118">**InstanceName**</span></span>  
 <span data-ttu-id="f5f62-119">Nome dell'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] a cui è connessa la sessione dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="f5f62-119">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="f5f62-120">**[SPID]**</span><span class="sxs-lookup"><span data-stu-id="f5f62-120">**[SPID]**</span></span>  
 <span data-ttu-id="f5f62-121">ID di processo della sessione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che identifica in modo univoco la sessione.</span><span class="sxs-lookup"><span data-stu-id="f5f62-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session process ID that uniquely identifies this session.</span></span> <span data-ttu-id="f5f62-122">È possibile ottenere ulteriori informazioni sulla sessione selezionando la riga nella vista sys.sysprocesses che include lo stesso valore nella colonna spid.</span><span class="sxs-lookup"><span data-stu-id="f5f62-122">You can obtain more information about the session by selecting the row in the sys.sysprocesses view that has the same value in the spid column.</span></span>  
  
 <span data-ttu-id="f5f62-123">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="f5f62-123">**Location**</span></span>  
 <span data-ttu-id="f5f62-124">Consente di visualizzare il nome del file script utilizzato nella sessione dell'editor di query di cui viene eseguito il debug.</span><span class="sxs-lookup"><span data-stu-id="f5f62-124">Displays the name of the script file that is used in the Query Editor session that is being debugged.</span></span>  
  
 <span data-ttu-id="f5f62-125">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="f5f62-125">**Priority**</span></span>  
 <span data-ttu-id="f5f62-126">Il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] non supporta questa caratteristica.</span><span class="sxs-lookup"><span data-stu-id="f5f62-126">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="f5f62-127">**Sospendi**</span><span class="sxs-lookup"><span data-stu-id="f5f62-127">**Suspend**</span></span>  
 <span data-ttu-id="f5f62-128">Il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] non supporta questa caratteristica.</span><span class="sxs-lookup"><span data-stu-id="f5f62-128">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f62-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5f62-129">See Also</span></span>  
 <span data-ttu-id="f5f62-130">[Debugger Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="f5f62-130">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="f5f62-131">[Informazioni del debugger Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="f5f62-131">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="f5f62-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5f62-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span></span>  
 [<span data-ttu-id="f5f62-133">sys.sysprocesses &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f5f62-133">sys.sysprocesses &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysprocesses-transact-sql)  
