---
title: Eseguire processi di manutenzione della replica (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server replication]
ms.assetid: 0dc485a0-5a50-41eb-a29d-f2b2fb920174
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9dc27c65e96a9f956ffa6d3edf9c72ed52f721a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721400"
---
# <a name="run-replication-maintenance-jobs-sql-server-management-studio"></a><span data-ttu-id="0c5bb-102">Esecuzione di processi di manutenzione della replica (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0c5bb-102">Run Replication Maintenance Jobs (SQL Server Management Studio)</span></span>
  <span data-ttu-id="0c5bb-103">Nella replica vengono utilizzati i seguenti processi di manutenzione:</span><span class="sxs-lookup"><span data-stu-id="0c5bb-103">Replication uses the following maintenance jobs:</span></span>  
  
-   <span data-ttu-id="0c5bb-104">**Reinizializzazione delle sottoscrizioni con errori di convalida dei dati**</span><span class="sxs-lookup"><span data-stu-id="0c5bb-104">**Reinitialize subscriptions having data validation failures**</span></span>
-   <span data-ttu-id="0c5bb-105">**Eliminazione del contenuto della cronologia dell'agente: distribuzione**</span><span class="sxs-lookup"><span data-stu-id="0c5bb-105">**Agent history clean up: distribution**</span></span>
-   <span data-ttu-id="0c5bb-106">**Aggiornamento del monitoraggio della replica per la distribuzione.**</span><span class="sxs-lookup"><span data-stu-id="0c5bb-106">**Replication monitoring refresher for distribution.**</span></span>
-   <span data-ttu-id="0c5bb-107">**Controllo degli agenti di replica**</span><span class="sxs-lookup"><span data-stu-id="0c5bb-107">**Replication agents checkup**</span></span>
-   <span data-ttu-id="0c5bb-108">**Eliminazione del contenuto della distribuzione: distribuzione**</span><span class="sxs-lookup"><span data-stu-id="0c5bb-108">**Distribution clean up: distribution**</span></span>
-   <span data-ttu-id="0c5bb-109">**Pulizia dei riferimenti alla sottoscrizione scaduta**</span><span class="sxs-lookup"><span data-stu-id="0c5bb-109">**Expired subscription clean up**</span></span>  
  
 <span data-ttu-id="0c5bb-110">Avviare e arrestare questi processi dalla cartella **Processi** in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] e dalla scheda **Agenti** in Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-110">Start and stop these jobs from the **Jobs** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="0c5bb-111">Per informazioni sull'avvio di Monitoraggio replica, vedere [Avviare Monitoraggio replica](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="0c5bb-111">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span> <span data-ttu-id="0c5bb-112">Visualizzare e modificare le proprietà per ogni processo nella finestra di dialogo **Proprietà processo - \<Job>** , accessibile dalla stessa cartella e dalla stessa scheda.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-112">View and modify properties for each job in the **Job Properties - \<Job>** dialog box, which is available from the same folder and tab.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="0c5bb-113">Per avviare e arrestare un processo di manutenzione della replica in Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c5bb-113">To start or stop a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="0c5bb-114">Connettersi al database di distribuzione in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-114">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="0c5bb-115">Espandere la cartella **SQL Server Agent** e quindi la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="0c5bb-115">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="0c5bb-116">Fare clic con il pulsante destro del mouse su un processo e quindi scegliere **Avvia processo** o **Arresta processo**.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-116">Right-click a job, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="0c5bb-117">Per avviare e arrestare un processo di manutenzione della replica in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="0c5bb-117">To start or stop a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="0c5bb-118">Espandere un gruppo di server di pubblicazione in Monitoraggio replica e quindi selezionare un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-118">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="0c5bb-119">Fare clic sulla scheda **Agenti** .</span><span class="sxs-lookup"><span data-stu-id="0c5bb-119">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="0c5bb-120">Fare clic con il pulsante destro del mouse su un processo e quindi scegliere **Avvia processo** o **Arresta processo**.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-120">Right-click a job in the grid, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="0c5bb-121">Per visualizzare e modificare le proprietà per un processo di manutenzione della replica in Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c5bb-121">To view and modify properties for a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="0c5bb-122">Connettersi al database di distribuzione in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-122">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="0c5bb-123">Espandere la cartella **SQL Server Agent** e quindi la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="0c5bb-123">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="0c5bb-124">Fare clic con il pulsante destro del mouse su un processo e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-124">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0c5bb-125">Nella finestra di dialogo **Proprietà processo - \<Job>** modificare le proprietà, se necessario, e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-125">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="0c5bb-126">Per visualizzare e modificare le proprietà per un processo di manutenzione della replica in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="0c5bb-126">To view and modify properties for a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="0c5bb-127">Espandere un gruppo di server di pubblicazione in Monitoraggio replica e quindi selezionare un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-127">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="0c5bb-128">Fare clic sulla scheda **Agenti** .</span><span class="sxs-lookup"><span data-stu-id="0c5bb-128">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="0c5bb-129">Fare clic con il pulsante destro del mouse su un processo nella griglia e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-129">Right-click a job in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0c5bb-130">Nella finestra di dialogo **Proprietà processo - \<Job>** modificare le proprietà, se necessario, e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c5bb-130">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5bb-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c5bb-131">See Also</span></span>  
 <span data-ttu-id="0c5bb-132">[Avviare e arrestare un agente di replica &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="0c5bb-132">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="0c5bb-133">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0c5bb-133">[View Information and Perform Tasks using Replication Monitor](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="0c5bb-134">Amministrazione dell'agente di replica</span><span class="sxs-lookup"><span data-stu-id="0c5bb-134">Replication Agent Administration</span></span>](../agents/replication-agent-administration.md)  
  
  
