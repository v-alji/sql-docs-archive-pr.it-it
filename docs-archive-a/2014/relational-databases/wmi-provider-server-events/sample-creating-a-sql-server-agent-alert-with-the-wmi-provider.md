---
title: 'Esempio: creazione di un avviso SQL Server Agent tramite il provider WMI per eventi del server | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SQL Server Agent [WMI]
- WMI Provider for Server Events, samples
- sample applications [WMI]
ms.assetid: d44811c7-cd46-4017-b284-c863ca088e8f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f23a3a8738435dc6a27a230f4521300a3ee2470f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717561"
---
# <a name="sample-creating-a-sql-server-agent-alert-by-using-the-wmi-provider-for-server-events"></a><span data-ttu-id="b85e7-102">Esempio: Creazione di un avviso di SQL Server Agent tramite il provider WMI per eventi del server</span><span class="sxs-lookup"><span data-stu-id="b85e7-102">Sample: Creating a SQL Server Agent Alert by Using the WMI Provider for Server Events</span></span>
  <span data-ttu-id="b85e7-103">Un utilizzo comune del provider di eventi WMI consiste nel creare avvisi di SQL Server Agent in risposta a eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="b85e7-103">One common way to use the WMI Event Provider is to create SQL Server Agent alerts that respond to specific events.</span></span> <span data-ttu-id="b85e7-104">Nell'esempio seguente viene presentato un avviso semplice che salva eventi Deadlock Graph XML in una tabella per l'analisi successiva.</span><span class="sxs-lookup"><span data-stu-id="b85e7-104">The following sample presents a simple alert that saves XML deadlock graph events in a table for later analysis.</span></span> <span data-ttu-id="b85e7-105">SQL Server Agent invia una richiesta WQL, riceve eventi WMI ed esegue un processo in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="b85e7-105">SQL Server Agent submits a WQL request, receives WMI events, and runs a job in response to the event.</span></span> <span data-ttu-id="b85e7-106">Si noti che benché diversi oggetti di Service Broker siano interessati dall'elaborazione del messaggio di notifica, il provider di eventi WMI gestisce i dettagli della creazione e della gestione di tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="b85e7-106">Notice that, although several Service Broker objects are involved in processing the notification message, the WMI Event Provider handles the details of creating and managing these objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b85e7-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b85e7-107">Example</span></span>  
 <span data-ttu-id="b85e7-108">Viene innanzitutto creata una tabella nel database `AdventureWorks` in cui includere l'evento Deadlock Graph.</span><span class="sxs-lookup"><span data-stu-id="b85e7-108">First, a table is created in the `AdventureWorks` database to hold the deadlock graph event.</span></span> <span data-ttu-id="b85e7-109">La tabella è costituita da due colonne: la colonna `AlertTime` contiene la durata di esecuzione dell'avviso, mentre la colonna `DeadlockGraph` contiene il documento XML che include l'evento Deadlock Graph.</span><span class="sxs-lookup"><span data-stu-id="b85e7-109">The table contains two columns: The `AlertTime` column holds the time that the alert runs, and the `DeadlockGraph` column holds the XML document that contains the deadlock graph.</span></span>  
  
 <span data-ttu-id="b85e7-110">Viene quindi creato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="b85e7-110">Then, the alert is created.</span></span> <span data-ttu-id="b85e7-111">Lo script crea innanzitutto il processo eseguito dall'avviso, aggiunge un passaggio del processo al processo e specifica come destinazione del processo l'istanza corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b85e7-111">The script first creates the job that the alert will run, adds a job step to the job, and targets the job to the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b85e7-112">Lo script crea quindi l'avviso.</span><span class="sxs-lookup"><span data-stu-id="b85e7-112">The script then creates the alert.</span></span>  
  
 <span data-ttu-id="b85e7-113">Il passaggio del processo recupera la proprietà **TextData** dell'istanza dell'evento WMI e inserisce tale valore nella colonna **DeadlockGraph** della tabella **DeadlockEvents** .</span><span class="sxs-lookup"><span data-stu-id="b85e7-113">The job step retrieves the **TextData** property of the WMI event instance and inserts that value into the **DeadlockGraph** column of the **DeadlockEvents** table.</span></span> <span data-ttu-id="b85e7-114">Si noti che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] converte in modo implicito la stringa in formato XML.</span><span class="sxs-lookup"><span data-stu-id="b85e7-114">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implicitly converts the string into XML format.</span></span> <span data-ttu-id="b85e7-115">Poiché utilizza il sottosistema [!INCLUDE[tsql](../../includes/tsql-md.md)], il passaggio del processo non specifica un proxy.</span><span class="sxs-lookup"><span data-stu-id="b85e7-115">Because the job step uses the [!INCLUDE[tsql](../../includes/tsql-md.md)] subsystem, the job step does not specify a proxy.</span></span>  
  
 <span data-ttu-id="b85e7-116">L'avviso esegue il processo ogni volta che viene registrato un evento di traccia Deadlock Graph.</span><span class="sxs-lookup"><span data-stu-id="b85e7-116">The alert runs the job whenever a deadlock graph trace event would be logged.</span></span> <span data-ttu-id="b85e7-117">Per un avviso WMI, SQL Server Agent crea una query di notifica utilizzando lo spazio dei nomi e l'istruzione WQL specificati.</span><span class="sxs-lookup"><span data-stu-id="b85e7-117">For a WMI alert, SQL Server Agent creates a notification query using the namespace and WQL statement specified.</span></span> <span data-ttu-id="b85e7-118">Per questo avviso, SQL Server Agent esegue il monitoraggio dell'istanza predefinita nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="b85e7-118">For this alert, SQL Server Agent monitors the default instance on the local computer.</span></span> <span data-ttu-id="b85e7-119">L'istruzione WQL richiede tutti gli eventi `DEADLOCK_GRAPH` nell'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="b85e7-119">The WQL statement requests any `DEADLOCK_GRAPH` event in the default instance.</span></span> <span data-ttu-id="b85e7-120">Per modificare l'istanza monitorata dall'avviso, sostituire il nome dell'istanza per `MSSQLSERVER` in `@wmi_namespace` per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="b85e7-120">To change the instance that the alert monitors, substitute the instance name for `MSSQLSERVER` in the `@wmi_namespace` for the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b85e7-121">Per SQL Server Agent la ricezione di eventi WMI, [!INCLUDE[ssSB](../../includes/sssb-md.md)] è necessario che sia abilitato in **msdb** e [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b85e7-121">For SQL Server Agent to receive WMI events, [!INCLUDE[ssSB](../../includes/sssb-md.md)] must be enabled in **msdb** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
IF OBJECT_ID('DeadlockEvents', 'U') IS NOT NULL  
BEGIN  
    DROP TABLE DeadlockEvents ;  
END ;  
GO  
  
CREATE TABLE DeadlockEvents  
    (AlertTime DATETIME, DeadlockGraph XML) ;  
GO  
-- Add a job for the alert to run.  
  
EXEC  msdb.dbo.sp_add_job @job_name=N'Capture Deadlock Graph',   
    @enabled=1,   
    @description=N'Job for responding to DEADLOCK_GRAPH events' ;  
GO  
  
-- Add a jobstep that inserts the current time and the deadlock graph into  
-- the DeadlockEvents table.  
  
EXEC msdb.dbo.sp_add_jobstep  
    @job_name = N'Capture Deadlock Graph',  
    @step_name=N'Insert graph into LogEvents',  
    @step_id=1,   
    @on_success_action=1,   
    @on_fail_action=2,   
    @subsystem=N'TSQL',   
    @command= N'INSERT INTO DeadlockEvents  
                (AlertTime, DeadlockGraph)  
                VALUES (getdate(), N''$(ESCAPE_SQUOTE(WMI(TextData)))'')',  
    @database_name=N'AdventureWorks' ;  
GO  
  
-- Set the job server for the job to the current instance of SQL Server.  
  
EXEC msdb.dbo.sp_add_jobserver @job_name = N'Capture Deadlock Graph' ;  
GO  
  
-- Add an alert that responds to all DEADLOCK_GRAPH events for  
-- the default instance. To monitor deadlocks for a different instance,  
-- change MSSQLSERVER to the name of the instance.  
  
EXEC msdb.dbo.sp_add_alert @name=N'Respond to DEADLOCK_GRAPH',   
@wmi_namespace=N'\\.\root\Microsoft\SqlServer\ServerEvents\MSSQLSERVER',   
    @wmi_query=N'SELECT * FROM DEADLOCK_GRAPH',   
    @job_name='Capture Deadlock Graph' ;  
GO  
```  
  
## <a name="testing-the-sample"></a><span data-ttu-id="b85e7-122">Test dell'esempio</span><span class="sxs-lookup"><span data-stu-id="b85e7-122">Testing the Sample</span></span>  
 <span data-ttu-id="b85e7-123">Per visualizzare l'esecuzione del processo, provocare un deadlock.</span><span class="sxs-lookup"><span data-stu-id="b85e7-123">To see the job run, provoke a deadlock.</span></span> <span data-ttu-id="b85e7-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] aprire due schede **query SQL** e connettere entrambe le query alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="b85e7-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open two **SQL Query** tabs and connect both queries to the same instance.</span></span> <span data-ttu-id="b85e7-125">Eseguire lo script seguente in una delle schede delle query.</span><span class="sxs-lookup"><span data-stu-id="b85e7-125">Run the following script in one of the query tabs.</span></span> <span data-ttu-id="b85e7-126">Questo script produce un set di risultati e viene terminato.</span><span class="sxs-lookup"><span data-stu-id="b85e7-126">This script produces one result set and finishes.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="b85e7-127">Eseguire lo script seguente nella seconda scheda della query. Questo script produce un set di risultati e quindi si blocca, in attesa di acquisire un blocco su `Production.Product` .</span><span class="sxs-lookup"><span data-stu-id="b85e7-127">Run the following script in the second query tab. This script produces one result set and then blocks, waiting to acquire a lock on `Production.Product`.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="b85e7-128">Eseguire lo script seguente nella prima scheda della query. Questo script si blocca, in attesa di acquisire un blocco su `Production.Location` .</span><span class="sxs-lookup"><span data-stu-id="b85e7-128">Run the following script in the first query tab. This script blocks, waiting to acquire a lock on `Production.Location`.</span></span> <span data-ttu-id="b85e7-129">Dopo un breve timeout, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sceglierà questo script o lo script nell'esempio come vittima del deadlock e terminerà la transazione.</span><span class="sxs-lookup"><span data-stu-id="b85e7-129">After a short time-out, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will choose either this script or the script in the sample as the deadlock victim and end the transaction.</span></span>  
  
```  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="b85e7-130">Dopo avere provocato il deadlock, attendere alcuni momenti prima che SQL Server Agent attivi l'avviso ed esegua il processo.</span><span class="sxs-lookup"><span data-stu-id="b85e7-130">After provoking the deadlock, wait several moments for SQL Server Agent to activate the alert and run the job.</span></span> <span data-ttu-id="b85e7-131">Esaminare il contenuto della tabella `DeadlockEvents` eseguendo lo script seguente:</span><span class="sxs-lookup"><span data-stu-id="b85e7-131">Examine the contents of the `DeadlockEvents` table by running the following script:</span></span>  
  
```  
SELECT * FROM DeadlockEvents ;  
GO  
```  
  
 <span data-ttu-id="b85e7-132">La colonna `DeadlockGraph` deve contenere un documento XML indicante tutte le proprietà dell'evento Deadlock Graph.</span><span class="sxs-lookup"><span data-stu-id="b85e7-132">The `DeadlockGraph` column should contain an XML document that shows all the properties of the deadlock graph event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85e7-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b85e7-133">See Also</span></span>  
 [<span data-ttu-id="b85e7-134">Concetti relativi al provider WMI per eventi del server</span><span class="sxs-lookup"><span data-stu-id="b85e7-134">WMI Provider for Server Events Concepts</span></span>](wmi-provider-for-server-events-concepts.md)  
  
  
