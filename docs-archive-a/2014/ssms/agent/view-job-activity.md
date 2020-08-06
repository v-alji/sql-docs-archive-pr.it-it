---
title: Visualizzare l'attività dei processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- viewing job activity
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- displaying job activity
ms.assetid: 5c284e5e-7775-435d-ac49-f3f12a27ddc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 56b159952c83ed243c4c5d8012c76e5a2a248519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725224"
---
# <a name="view-job-activity"></a><span data-ttu-id="ad235-102">Visualizza attività processi</span><span class="sxs-lookup"><span data-stu-id="ad235-102">View Job Activity</span></span>
  <span data-ttu-id="ad235-103">In questo argomento viene illustrato come visualizzare lo stato di runtime dei processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad235-103">This topic describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ad235-104">All'avvio di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent viene creata una nuova sessione e la tabella **sysjobactivity** del database **msdb** viene popolata con tutti i processi definiti esistenti.</span><span class="sxs-lookup"><span data-stu-id="ad235-104">When the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service starts, a new session is created and the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="ad235-105">In questa tabella sono registrati l'attività e lo stato dei processi correnti.</span><span class="sxs-lookup"><span data-stu-id="ad235-105">This table records current job activity and status.</span></span> <span data-ttu-id="ad235-106">Per visualizzare lo stato corrente dei processi è possibile utilizzare Monitoraggio attività processo in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="ad235-106">You can use the Job Activity Monitor in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to view the current state of jobs.</span></span> <span data-ttu-id="ad235-107">Se il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent viene interrotto in modo imprevisto, per verificare quali processi erano in esecuzione al momento dell'interruzione è possibile fare riferimento alla tabella **sysjobactivity** .</span><span class="sxs-lookup"><span data-stu-id="ad235-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service unexpectedly terminates, you can refer to the **sysjobactivity** table to see which jobs were being executed when the service terminated.</span></span>  
  
 <span data-ttu-id="ad235-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ad235-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad235-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ad235-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ad235-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ad235-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ad235-111">**Per visualizzare l'attività del processo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="ad235-111">**To view job activity, using:**</span></span>  
  
     [<span data-ttu-id="ad235-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad235-112">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="ad235-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad235-113">Transact-SQL</span></span>](#TSQL)  
  
## <a name="before-you-begin"></a><span data-ttu-id="ad235-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ad235-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ad235-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ad235-115">Security</span></span>  
 <span data-ttu-id="ad235-116">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="ad235-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="ad235-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad235-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="ad235-118">Per visualizzare l'attività del processo</span><span class="sxs-lookup"><span data-stu-id="ad235-118">To view job activity</span></span>  
  
1.  <span data-ttu-id="ad235-119">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="ad235-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ad235-120">Espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="ad235-120">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="ad235-121">Fare clic con il pulsante destro del mouse su **monitoraggio attività processi** e scegliere **Visualizza attività processi**.</span><span class="sxs-lookup"><span data-stu-id="ad235-121">Right-click **Job Activity Monitor** and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="ad235-122">In **Monitoraggio attività processo**è possibile visualizzare i dettagli relativi a ogni processo definito nel server.</span><span class="sxs-lookup"><span data-stu-id="ad235-122">In the **Job Activity Monitor**, you can view details about each job that is defined for this server.</span></span>  
  
5.  <span data-ttu-id="ad235-123">Fare clic con il pulsante destro del mouse su un processo per avviarlo, arrestarlo, attivarlo o disabilitarlo, aggiornarne lo stato visualizzato in Monitoraggio attività processo, eliminarlo o visualizzarne la cronologia o le proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad235-123">Right-click a job to start it, stop it, enable or disable it, refresh its status as displayed in the Job Activity Monitor, delete it, or view its history or properties.</span></span>  <span data-ttu-id="ad235-124">Per avviare, arrestare, attivare o disabilitare o aggiornare più processi, selezionare più righe in Monitoraggio attività processo e fare clic con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="ad235-124">To start, stop, enable or disable, or refresh multiple jobs, select multiple rows in the Job Activity Monitor, and right-click your selection.</span></span>  
  
6.  <span data-ttu-id="ad235-125">Per aggiornare Monitoraggio attività processo fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="ad235-125">To update the Job Activity Monitor, click **Refresh**.</span></span> <span data-ttu-id="ad235-126">Per visualizzare un numero inferiore di righe, fare clic su **Filtro** e specificare i parametri del filtro.</span><span class="sxs-lookup"><span data-stu-id="ad235-126">To view fewer rows, click **Filter** and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="ad235-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad235-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="ad235-128">Per visualizzare l'attività del processo</span><span class="sxs-lookup"><span data-stu-id="ad235-128">To view job activity</span></span>  
  
1.  <span data-ttu-id="ad235-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad235-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ad235-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ad235-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ad235-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ad235-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- lists activity for all jobs that the current user has permission to view.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobactivity ;  
    GO  
    ```  
  
 <span data-ttu-id="ad235-132">Per ulteriori informazioni, vedere [sp_help_jobactivity &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad235-132">For more information, see [sp_help_jobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span></span>  
  
  
