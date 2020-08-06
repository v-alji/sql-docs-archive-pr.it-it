---
title: Avvia SQL Server Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: 22e57ffa-63b0-4de3-b92e-df297dda1226
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05743927420865a9b6341fc050ca999f494d64d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719152"
---
# <a name="start-sql-server-profiler"></a><span data-ttu-id="ad7d8-102">Avviare SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="ad7d8-102">Start SQL Server Profiler</span></span>
  <span data-ttu-id="ad7d8-103">È possibile avviare [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in diversi modi per supportare la raccolta dell'output di traccia in numerosi scenari.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-103">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in several different ways to support gathering trace output in a variety of scenarios.</span></span> <span data-ttu-id="ad7d8-104">[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] può essere avviato dal menu **Start** , dal menu **Strumenti** in Ottimizzazione guidata [!INCLUDE[ssDE](../../includes/ssde-md.md)] e da diverse posizioni all'interno di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad7d8-104">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] include from the **Start** menu, from the **Tools** menu in [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor, and from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ad7d8-105">Quando si avvia [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per la prima volta e si sceglie **Nuova traccia** dal menu **File **, l'applicazione visualizza la finestra di dialogo** Connetti al server[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui è possibile specificare l'istanza di** alla quale si vuole connettersi.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-105">When you first start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and select **New Trace** from the **File** menu, the application displays a **Connect to Server** dialog box where you can specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to which you want to connect.</span></span>  
  
### <a name="to-start-sql-server-profiler-from-the-start-menu"></a><span data-ttu-id="ad7d8-106">Per avviare SQL Server Profiler dal menu Start</span><span class="sxs-lookup"><span data-stu-id="ad7d8-106">To start SQL Server Profiler from the Start menu</span></span>  
  
1.  <span data-ttu-id="ad7d8-107">Scegliere **Tutti i programmi** dal menu **Start**, selezionare [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], scegliere **Strumenti per le prestazioni**e fare clic su **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-107">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and then click **SQL Server Profiler**.</span></span>  
  
### <a name="to-start-sql-server-profiler-in-database-engine-tuning-advisor"></a><span data-ttu-id="ad7d8-108">Per avviare SQL Server Profiler in Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="ad7d8-108">To start SQL Server Profiler in Database Engine Tuning Advisor</span></span>  
  
1.  <span data-ttu-id="ad7d8-109">Selezionare [!INCLUDE[ssDE](../../includes/ssde-md.md)] SQL Server Profiler **dal menu** Tools **di Ottimizzazione guidata**.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-109">On the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
## <a name="starting-sql-server-profiler-in-management-studio"></a><span data-ttu-id="ad7d8-110">Avvio di SQL Server Profiler in Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad7d8-110">Starting SQL Server Profiler in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="ad7d8-111">avvia ogni sessione del profiler nella rispettiva istanza e continua l'esecuzione anche dopo l'arresto di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad7d8-111">starts each profiler session in its own instance and continues to run if you shutdown [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ad7d8-112">È possibile avviare [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] da diverse posizioni all'interno di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], come illustrato nelle procedure riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-112">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as illustrated in the following procedures.</span></span> <span data-ttu-id="ad7d8-113">Quando viene avviato [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , vengono caricati il contesto di connessione, il modello di traccia e il contesto del filtro del punto di avvio.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-113">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] starts it loads the connection context, trace template, and filter context of its launch point.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-tools-menu"></a><span data-ttu-id="ad7d8-114">Per avviare SQL Server Profiler dal menu Strumenti</span><span class="sxs-lookup"><span data-stu-id="ad7d8-114">To start SQL Server Profiler from the Tools menu</span></span>  
  
1.  <span data-ttu-id="ad7d8-115">Dal menu **Strumenti** di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] scegliere **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-115">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-query-editor"></a><span data-ttu-id="ad7d8-116">Per avviare SQL Server Profiler dall'editor di query</span><span class="sxs-lookup"><span data-stu-id="ad7d8-116">To start SQL Server Profiler from the Query Editor</span></span>  
  
1.  <span data-ttu-id="ad7d8-117">Sulla barra dei menu di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-117">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] menu bar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="ad7d8-118">In Editor di query fare clic con il pulsante destro del mouse e scegliere **Traccia query in SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-118">In Query Editor, right-click and then select **Trace Query in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ad7d8-119">Il contesto di connessione è la connessione dell'editor, il modello di traccia è TSQL_SPs e il filtro applicato è SPID = finestra della query SPID.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-119">The connection context is the editor connection, the trace template is TSQL_SPs, and the applied filter is SPID = query window SPID.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-activity-monitor"></a><span data-ttu-id="ad7d8-120">Per avviare SQL Server Profiler da Monitor attività</span><span class="sxs-lookup"><span data-stu-id="ad7d8-120">To start SQL Server Profiler from Activity Monitor</span></span>  
  
1.  <span data-ttu-id="ad7d8-121">In Esplora oggetti fare clic con il pulsante destro del mouse su un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e scegliere **Monitoraggio attività**.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-121">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="ad7d8-122">Nel riquadro **Processi** fare clic con il pulsante destro del mouse sul processo di cui si vuole modificare il profilo e scegliere **Processo di traccia in SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-122">Click the **Processes** pane, right-click the process that you want to profile, and then click **Trace Process in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ad7d8-123">Quando viene selezionato un processo, il contesto di connessione è la connessione Esplora oggetti stabilita all'apertura di Monitor attività.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-123">When a process is selected, the connection context is the Object Explorer connection when Activity Monitor was opened.</span></span> <span data-ttu-id="ad7d8-124">Il modello di traccia è l'impostazione predefinita basata sul tipo di server e lo SPID corrisponde a quello del processo selezionato.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-124">The trace template is the default based on the server type, and the SPID equals the SPID for the selected process.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ad7d8-125">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ad7d8-125">.NET Framework Security</span></span>  
 <span data-ttu-id="ad7d8-126">Nella modalità di autenticazione di Windows l'account utente utilizzato per l'esecuzione di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] deve disporre dell'autorizzazione per la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad7d8-126">In Windows Authentication mode, the user account that runs [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] must have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ad7d8-127">Per eseguire tracce con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], gli utenti devono inoltre possedere l'autorizzazione ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="ad7d8-127">To perform tracing with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], users must also have the ALTER TRACE permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7d8-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad7d8-128">See Also</span></span>  
 <span data-ttu-id="ad7d8-129">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="ad7d8-129">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="ad7d8-130">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad7d8-130">Use SQL Server Management Studio</span></span>](../../database-engine/use-sql-server-management-studio.md)  
  
  
