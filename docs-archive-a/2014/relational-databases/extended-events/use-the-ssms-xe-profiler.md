---
title: Usare la sessione system_health | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], system health session
- extended events [SQL Server], system_health session
- system_health session [SQL Server extended events]
- system health session [SQL Server extended events]
ms.assetid: 1e1fad43-d747-4775-ac0d-c50648e56d78
author: yualan
ms.author: alayu
ms.openlocfilehash: 86c3221fb4c0ea0690b369888ac8f2f9f82d6ef9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624158"
---
# <a name="use-the-system_health-session"></a><span data-ttu-id="bb014-102">Utilizzare la sessione system_health</span><span class="sxs-lookup"><span data-stu-id="bb014-102">Use the system_health Session</span></span>
  <span data-ttu-id="bb014-103">La sessione system_health è una sessione di eventi estesi inclusa per impostazione predefinita in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb014-103">The system_health session is an Extended Events session that is included by default with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bb014-104">Questa sessione viene avviata automaticamente all'avvio del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e viene eseguita senza effetti rilevanti sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="bb014-104">This session starts automatically when the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] starts, and runs without any noticeable performance effects.</span></span> <span data-ttu-id="bb014-105">La sessione raccoglie dati del sistema che consentono di semplificare la risoluzione dei problemi relativi alle prestazioni nel [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb014-105">The session collects system data that you can use to help troubleshoot performance issues in the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="bb014-106">È pertanto consigliabile non arrestare o eliminare la sessione.</span><span class="sxs-lookup"><span data-stu-id="bb014-106">Therefore, we recommend that you do not stop or delete the session.</span></span>  
  
 <span data-ttu-id="bb014-107">La sessione raccoglie le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb014-107">The session collects information that includes the following:</span></span>  
  
-   <span data-ttu-id="bb014-108">Sql_text e session_id per qualsiasi sessione in cui si verifica un errore con gravità >=20.</span><span class="sxs-lookup"><span data-stu-id="bb014-108">The sql_text and session_id for any sessions that encounter an error that has a severity >=20.</span></span>  
  
-   <span data-ttu-id="bb014-109">Sql_text e session_id per qualsiasi sessione in cui si verifica un errore relativo alla memoria.</span><span class="sxs-lookup"><span data-stu-id="bb014-109">The sql_text and session_id for any sessions that encounter a memory-related error.</span></span> <span data-ttu-id="bb014-110">ad esempio gli errori 17803, 701, 802, 8645, 8651, 8657 e 8902.</span><span class="sxs-lookup"><span data-stu-id="bb014-110">The errors include 17803, 701, 802, 8645, 8651, 8657 and 8902.</span></span>  
  
-   <span data-ttu-id="bb014-111">Un record di qualsiasi problema dell'utilità di pianificazione relativo alla mancata cessione del controllo.</span><span class="sxs-lookup"><span data-stu-id="bb014-111">A record of any non-yielding scheduler problems.</span></span> <span data-ttu-id="bb014-112">Questi problemi sono inclusi come errori 17883 nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb014-112">(These appear in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log as error 17883.)</span></span>  
  
-   <span data-ttu-id="bb014-113">Qualsiasi deadlock rilevato.</span><span class="sxs-lookup"><span data-stu-id="bb014-113">Any deadlocks that are detected.</span></span>  
  
-   <span data-ttu-id="bb014-114">Callstack, sql_text e session_id per qualsiasi sessione in attesa su latch (o altre risorse interessanti) per un tempo maggiore a 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="bb014-114">The callstack, sql_text, and session_id for any sessions that have waited on latches (or other interesting resources) for > 15 seconds.</span></span>  
  
-   <span data-ttu-id="bb014-115">Callstack, sql_text e session_id per qualsiasi sessione in attesa su blocchi per un tempo maggiore a 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="bb014-115">The callstack, sql_text, and session_id for any sessions that have waited on locks for > 30 seconds.</span></span>  
  
-   <span data-ttu-id="bb014-116">Callstack, sql_text e session_id per qualsiasi sessione rimasta in attesa per molto tempo a causa di attese preemptive.</span><span class="sxs-lookup"><span data-stu-id="bb014-116">The callstack, sql_text, and session_id for any sessions that have waited for a long time for preemptive waits.</span></span> <span data-ttu-id="bb014-117">La durata varia in base al tipo di attesa.</span><span class="sxs-lookup"><span data-stu-id="bb014-117">The duration varies by wait type.</span></span> <span data-ttu-id="bb014-118">In un'attesa preemptive [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in attesa di chiamate API esterne.</span><span class="sxs-lookup"><span data-stu-id="bb014-118">A preemptive wait is where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for external API calls.</span></span>  
  
-   <span data-ttu-id="bb014-119">callstack e session_id per l'allocazione CLR e per errori di allocazione virtuali.</span><span class="sxs-lookup"><span data-stu-id="bb014-119">The callstack and session_id for CLR allocation and virtual allocation failures.</span></span>  
  
-   <span data-ttu-id="bb014-120">Eventi ring_buffer per il broker di memoria, il monitoraggio dell'utilità di pianificazione, la memoria insufficiente del nodo di memoria, la sicurezza e la connettività.</span><span class="sxs-lookup"><span data-stu-id="bb014-120">The ring_buffer events for the memory broker, scheduler monitor, memory node OOM, security, and connectivity.</span></span>  
  
-   <span data-ttu-id="bb014-121">Risultati del componente di sistema da sp_server_diagnostics.</span><span class="sxs-lookup"><span data-stu-id="bb014-121">System component results from sp_server_diagnostics.</span></span>  
  
-   <span data-ttu-id="bb014-122">Integrità dell'istanza raccolta da scheduler_monitor_system_health_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="bb014-122">Instance health collected by scheduler_monitor_system_health_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="bb014-123">Errori di allocazione CLR.</span><span class="sxs-lookup"><span data-stu-id="bb014-123">CLR Allocation failures.</span></span>  
  
-   <span data-ttu-id="bb014-124">Errori di connettività utilizzando connectivity_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="bb014-124">Connectivity errors using connectivity_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="bb014-125">Errori di sicurezza utilizzando security_error_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="bb014-125">Security errors using security_error_ring_buffer_recorded.</span></span>  
  
## <a name="viewing-the-session-data"></a><span data-ttu-id="bb014-126">Visualizzazione dei dati della sessione</span><span class="sxs-lookup"><span data-stu-id="bb014-126">Viewing the Session Data</span></span>  
 <span data-ttu-id="bb014-127">Nella sessione viene utilizzata la destinazione del buffer circolare per archiviare i dati.</span><span class="sxs-lookup"><span data-stu-id="bb014-127">The session uses the ring buffer target to store the data.</span></span> <span data-ttu-id="bb014-128">Per visualizzare i dati della sessione, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="bb014-128">To view the session data, use the following query:</span></span>  
  
```  
SELECT CAST(xet.target_data as xml) FROM sys.dm_xe_session_targets xet  
JOIN sys.dm_xe_sessions xe  
ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'system_health'  
```  
  
 <span data-ttu-id="bb014-129">Per visualizzare i dati sessione dell'evento file, utilizzare l'interfaccia utente degli eventi estesi disponibili in Management Studio.</span><span class="sxs-lookup"><span data-stu-id="bb014-129">To view the session data from the event file, use the Extended Events user interface available in Management Studio.</span></span> <span data-ttu-id="bb014-130">Per ulteriori informazioni, vedere [visualizzare i dati della sessione eventi](../../database-engine/view-event-session-data.md) .</span><span class="sxs-lookup"><span data-stu-id="bb014-130">See [View Event Session Data](../../database-engine/view-event-session-data.md) for more information.</span></span>  
  
## <a name="restoring-the-system_health-session"></a><span data-ttu-id="bb014-131">Ripristino della sessione system_health</span><span class="sxs-lookup"><span data-stu-id="bb014-131">Restoring the system_health Session</span></span>  
 <span data-ttu-id="bb014-132">Se si elimina la sessione system_health, è possibile ripristinarla eseguendo il file **u_tables.sql** nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="bb014-132">If you delete the system_health session, you can restore it by executing the **u_tables.sql** file in Query Editor.</span></span> <span data-ttu-id="bb014-133">Questo file si trova nella cartella seguente, dove C: rappresenta l'unità in cui sono stati installati i file di programma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="bb014-133">This file is located in the following folder, where C: represents the drive where you installed the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] program files:</span></span>  
  
 <span data-ttu-id="bb014-134">C:\Programmi\Microsoft SQL Server\MSSQL12. \<*instanceid*> \MSSQL\Install</span><span class="sxs-lookup"><span data-stu-id="bb014-134">C:\Program Files\Microsoft SQL Server\MSSQL12.\<*instanceid*>\MSSQL\Install</span></span>  
  
 <span data-ttu-id="bb014-135">Tenere presente che dopo aver ripristinato la sessione, è necessario avviarla tramite l'istruzione ALTER EVENT SESSION o tramite il nodo **Eventi estesi** in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="bb014-135">Be aware that after you restore the session, you must start the session by using the ALTER EVENT SESSION statement or by using the **Extended Events** node in Object Explorer.</span></span> <span data-ttu-id="bb014-136">In caso contrario, la sessione verrà avviata al successivo riavvio del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb014-136">Otherwise, the session starts automatically the next time that you restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb014-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb014-137">See Also</span></span>  
 [<span data-ttu-id="bb014-138">Strumenti degli eventi estesi</span><span class="sxs-lookup"><span data-stu-id="bb014-138">Extended Events Tools</span></span>](extended-events-tools.md)  
  
  
