---
title: Visualizzare e leggere il log di diagnostica dell'istanza del cluster di failover| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 68074bd5-be9d-4487-a320-5b51ef8e2b2d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 774dc4ec4a02c72420d004909cb7e6ee1b31f3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628263"
---
# <a name="view-and-read-failover-cluster-instance-diagnostics-log"></a><span data-ttu-id="a07e5-102">Visualizzazione e lettura del log di diagnostica dell'istanza del cluster di failover</span><span class="sxs-lookup"><span data-stu-id="a07e5-102">View and Read Failover Cluster Instance Diagnostics Log</span></span>
  <span data-ttu-id="a07e5-103">Tutti gli errori critici e gli eventi di avviso relativi alla DLL risorse SQL Server vengono scritti nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="a07e5-103">All critical errors and warning events for the SQL Server Resource DLL are written to the Windows event log.</span></span> <span data-ttu-id="a07e5-104">Un log in esecuzione relativo a informazioni di diagnostica specifiche di SQL Server viene acquisito dalla stored procedure di sistema [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) e viene scritto nei file di log di diagnostica del cluster di failover di SQL Server, noti anche come log *SQLDIAG*.</span><span class="sxs-lookup"><span data-stu-id="a07e5-104">A running log of the diagnostic information specific to SQL Server is captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) system stored procedure and is written to the SQL Server failover cluster diagnostics (also known as the *SQLDIAG* logs) log files.</span></span>  
  
-   <span data-ttu-id="a07e5-105">**Prima di iniziare:**  [Indicazioni](#Recommendations), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="a07e5-105">**Before you begin:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="a07e5-106">**Per visualizzare il log di diagnostica usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="a07e5-106">**To View the Diagnostic Log, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="a07e5-107">**Per configurare le impostazioni del log di diagnostica usando:** [Transact-SQL](#TsqlConfigure)</span><span class="sxs-lookup"><span data-stu-id="a07e5-107">**To Configure Diagnostic Log settings, using:** [Transact-SQL](#TsqlConfigure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a07e5-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a07e5-108">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a07e5-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="a07e5-109">Recommendations</span></span>  
 <span data-ttu-id="a07e5-110">Per impostazione predefinita, l'utilità SQLdiag è archiviata in una cartella LOG locale della directory dell'istanza di SQL Server, ad esempio,' C\programmi\microsoft Files\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\LOG ' del nodo proprietario dell'istanza del cluster di failover (FCI) AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="a07e5-110">By default, the SQLDIAG are stored under a local LOG folder of the SQL Server instance directory, for example, 'C\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\LOG' of the owning node of the AlwaysOn Failover Cluster Instance (FCI).</span></span> <span data-ttu-id="a07e5-111">La dimensione di ogni file di log SQLDIAG è pari a 100 MB.</span><span class="sxs-lookup"><span data-stu-id="a07e5-111">The size of each SQLDIAG log file is fixed at 100 MB.</span></span> <span data-ttu-id="a07e5-112">Successivamente, tali file di log vengono archiviati nel computer prima di essere riciclati per i nuovi log.</span><span class="sxs-lookup"><span data-stu-id="a07e5-112">Ten such log files are stored on the computer before they are recycled for new logs.</span></span>  
  
 <span data-ttu-id="a07e5-113">Nei log viene utilizzato il formato di file degli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="a07e5-113">The logs use the extended events file format.</span></span> <span data-ttu-id="a07e5-114">La funzione di sistema **sys.fn_xe_file_target_read_file** può essere usata per leggere i file creati dagli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="a07e5-114">The **sys.fn_xe_file_target_read_file** system function can be used to read the files that are created by Extended Events.</span></span> <span data-ttu-id="a07e5-115">Viene restituito un evento per riga in formato XML.</span><span class="sxs-lookup"><span data-stu-id="a07e5-115">One event, in XML format, is returned per row.</span></span> <span data-ttu-id="a07e5-116">Eseguire una query sulla vista di sistema per analizzare i dati XML come set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a07e5-116">Query the system view to parse the XML data as a result-set.</span></span> <span data-ttu-id="a07e5-117">Per altre informazioni, vedere [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a07e5-117">For more information, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a07e5-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a07e5-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a07e5-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a07e5-119">Permissions</span></span>  
 <span data-ttu-id="a07e5-120">L'autorizzazione VIEW SERVER STATE è necessaria per eseguire **fn_xe_file_target_read_file**.</span><span class="sxs-lookup"><span data-stu-id="a07e5-120">VIEW SERVER STATE permission is needed to run **fn_xe_file_target_read_file**.</span></span>  
  
 <span data-ttu-id="a07e5-121">Aprire SQL Server Management Studio come amministratore.</span><span class="sxs-lookup"><span data-stu-id="a07e5-121">Open SQL Server Management Studio as Administrator</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a07e5-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a07e5-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a07e5-123">**Per visualizzare i file di log di diagnostica:**</span><span class="sxs-lookup"><span data-stu-id="a07e5-123">**To view the Diagnostic log files:**</span></span>  
  
1.  <span data-ttu-id="a07e5-124">Scegliere **Apri** dal menu **File**, selezionare **File**, quindi scegliere il file di log di diagnostica che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="a07e5-124">From the **File** menu, select **Open**, **File**, and choose the diagnostic log file you want to view.</span></span>  
  
2.  <span data-ttu-id="a07e5-125">Gli eventi vengono visualizzati come righe nel riquadro destro e per impostazione predefinita **name**e **timestamp** sono le uniche due colonne visualizzate.</span><span class="sxs-lookup"><span data-stu-id="a07e5-125">The events are displayed as rows in the right pane, and by default **name**, and **timestamp** are the only two columns displayed.</span></span>  
  
     <span data-ttu-id="a07e5-126">Viene inoltre attivato il menu **ExtendedEvents** .</span><span class="sxs-lookup"><span data-stu-id="a07e5-126">This also activates the **ExtendedEvents** menu.</span></span>  
  
3.  <span data-ttu-id="a07e5-127">Per visualizzare più colonne, passare al menu **ExtendedEvents** e selezionare **Scegli colonne**.</span><span class="sxs-lookup"><span data-stu-id="a07e5-127">To see more columns, go the **ExtendedEvents** menu, and select **Choose Columns**.</span></span>  
  
     <span data-ttu-id="a07e5-128">Verrà visualizzata una finestra di dialogo con le colonne disponibili in cui è possibile selezionare le colonne da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="a07e5-128">A dialog box opens with the available columns allowing you to select the columns for display.</span></span>  
  
4.  <span data-ttu-id="a07e5-129">È possibile filtrare e ordinare i dati degli eventi utilizzando il menu **ExtendedEvents** e selezionando l'opzione **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="a07e5-129">You can filter, and sort the event data using the **ExtendedEvents** menu and selecting the **Filter** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a07e5-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a07e5-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="a07e5-131">**Per visualizzare i file di log di diagnostica:**</span><span class="sxs-lookup"><span data-stu-id="a07e5-131">**To view the Diagnostic log files:**</span></span>  
  
 <span data-ttu-id="a07e5-132">Per visualizzare tutte le voci di log nel file di log SQLDIAG, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="a07e5-132">To view all the log items in the SQLDIAG log file, use the following query:</span></span>  
  
```  
SELECT  
xml_data.value('(event/@name)[1]','varchar(max)') AS 'Name'  
,xml_data.value('(event/@package)[1]','varchar(max)') AS 'Package'  
,xml_data.value('(event/@timestamp)[1]','datetime') AS 'Time'  
,xml_data.value('(event/data[@name=''state'']/value)[1]','int') AS 'State'  
,xml_data.value('(event/data[@name=''state_desc'']/text)[1]','varchar(max)') AS 'State Description'  
,xml_data.value('(event/data[@name=''failure_condition_level'']/value)[1]','int') AS 'Failure Conditions'  
,xml_data.value('(event/data[@name=''node_name'']/value)[1]','varchar(max)') AS 'Node_Name'  
,xml_data.value('(event/data[@name=''instancename'']/value)[1]','varchar(max)') AS 'Instance Name'  
,xml_data.value('(event/data[@name=''creation time'']/value)[1]','datetime') AS 'Creation Time'  
,xml_data.value('(event/data[@name=''component'']/value)[1]','varchar(max)') AS 'Component'  
,xml_data.value('(event/data[@name=''data'']/value)[1]','varchar(max)') AS 'Data'  
,xml_data.value('(event/data[@name=''info'']/value)[1]','varchar(max)') AS 'Info'  
FROM  
 ( SELECT object_name AS 'event'  
  ,CONVERT(xml,event_data) AS 'xml_data'  
  FROM sys.fn_xe_file_target_read_file('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log\SQLNODE1_MSSQLSERVER_SQLDIAG_0_129936003752530000.xel',NULL,NULL,NULL)   
)   
AS XEventData  
ORDER BY Time;  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="a07e5-133">È possibile filtrare i risultati in base a stati o componenti specifici utilizzando la clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="a07e5-133">You can filter the results for specific components or state using the WHERE clause.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlConfigure"></a> <span data-ttu-id="a07e5-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a07e5-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="a07e5-135">**Per configurare le proprietà del log di diagnostica**</span><span class="sxs-lookup"><span data-stu-id="a07e5-135">**To configure the Diagnostic Log Properties**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a07e5-136">Per un esempio di questa procedura, vedere [Esempio (Transact-SQL)](#TsqlExample)più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a07e5-136">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
 <span data-ttu-id="a07e5-137">Utilizzando l'istruzione DDL (Data Definition Language), `ALTER SERVER CONFIGURATION` è possibile avviare o arrestare la registrazione dei dati di diagnostica acquisiti dalla [sp_server_diagnostics &#40;procedura&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) e impostare i parametri di configurazione dei log SQLDIAG, ad esempio il numero di rollover dei file di log, le dimensioni del file di log e il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="a07e5-137">Using the Data Definition Language (DDL) statement, `ALTER SERVER CONFIGURATION`, you can start or stop logging diagnostic data captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) procedure, and set SQLDIAG log configuration parameters such as the log file rollover count, log file size, and file location.</span></span> <span data-ttu-id="a07e5-138">Per dettagli sulla sintassi, vedere [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span><span class="sxs-lookup"><span data-stu-id="a07e5-138">For syntax details, see [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="ConfigTsqlExample"></a> <span data-ttu-id="a07e5-139">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a07e5-139">Examples (Transact-SQL)</span></span>  
  
####  <a name="setting-diagnostic-log-options"></a><a name="TsqlExample"></a> <span data-ttu-id="a07e5-140">Setting diagnostic log options</span><span class="sxs-lookup"><span data-stu-id="a07e5-140">Setting diagnostic log options</span></span>  
 <span data-ttu-id="a07e5-141">Negli esempi inclusi in questa sezione viene illustrato come impostare i valori per l'opzione del log di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a07e5-141">The examples in this section show how to set the values for the diagnostic log option.</span></span>  
  
##### <a name="a-starting-diagnostic-logging"></a><span data-ttu-id="a07e5-142">R.</span><span class="sxs-lookup"><span data-stu-id="a07e5-142">A.</span></span> <span data-ttu-id="a07e5-143">Avvio della registrazione dei dati di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a07e5-143">Starting diagnostic logging</span></span>  
 <span data-ttu-id="a07e5-144">Nell'esempio seguente viene avviata la registrazione dei dati di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a07e5-144">The following example starts the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG ON;  
```  
  
##### <a name="b-stopping-diagnostic-logging"></a><span data-ttu-id="a07e5-145">B.</span><span class="sxs-lookup"><span data-stu-id="a07e5-145">B.</span></span> <span data-ttu-id="a07e5-146">Arresto della registrazione dei dati di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a07e5-146">Stopping diagnostic logging</span></span>  
 <span data-ttu-id="a07e5-147">Nell'esempio seguente viene arrestata la registrazione dei dati di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a07e5-147">The following example stops the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG OFF;  
```  
  
##### <a name="c-specifying-the-location-of-the-diagnostic-logs"></a><span data-ttu-id="a07e5-148">C.</span><span class="sxs-lookup"><span data-stu-id="a07e5-148">C.</span></span> <span data-ttu-id="a07e5-149">Definizione della posizione dei log di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a07e5-149">Specifying the location of the diagnostic logs</span></span>  
 <span data-ttu-id="a07e5-150">Nell'esempio seguente viene impostata la posizione dei log di diagnostica sul percorso di file specificato.</span><span class="sxs-lookup"><span data-stu-id="a07e5-150">The following example sets the location of the diagnostic logs to the specified file path.</span></span>  
  
```  
ALTER SERVER CONFIGURATION  
SET DIAGNOSTICS LOG PATH = 'C:\logs';  
```  
  
##### <a name="d-specifying-the-maximum-size-of-each-diagnostic-log"></a><span data-ttu-id="a07e5-151">D.</span><span class="sxs-lookup"><span data-stu-id="a07e5-151">D.</span></span> <span data-ttu-id="a07e5-152">Definizione della dimensione massima di ogni log di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a07e5-152">Specifying the maximum size of each diagnostic log</span></span>  
 <span data-ttu-id="a07e5-153">Nell'esempio seguente viene impostata su 10 megabyte la dimensione massima di ogni log di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a07e5-153">The following example set the maximum size of each diagnostic log to 10 megabytes.</span></span>  
  
```  
ALTER SERVER CONFIGURATION   
SET DIAGNOSTICS LOG MAX_SIZE = 10 MB;  
```  
  
## <a name="see-also"></a><span data-ttu-id="a07e5-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a07e5-154">See Also</span></span>  
 [<span data-ttu-id="a07e5-155">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="a07e5-155">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
  
  
