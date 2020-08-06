---
title: Utilizzare SQL Server Profiler per creare un set di raccolta Traccia SQL (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace collector set
ms.assetid: b6941dc0-50f5-475d-82eb-ce7c68117489
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e9c9514fef8069cef615d1480aad1e0acd1582cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636223"
---
# <a name="use-sql-server-profiler-to-create-a-sql-trace-collection-set-sql-server-management-studio"></a><span data-ttu-id="25701-102">Utilizzo di SQL Server Profiler per creare un set di raccolta Traccia SQL (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="25701-102">Use SQL Server Profiler to Create a SQL Trace Collection Set (SQL Server Management Studio)</span></span>
  <span data-ttu-id="25701-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] è possibile sfruttare le funzionalità di traccia sul lato server di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per esportare una definizione della traccia da usare per creare un set di raccolta che usa il tipo di agente di raccolta Traccia SQL generico.</span><span class="sxs-lookup"><span data-stu-id="25701-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] you can exploit the server-side trace capabilities of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to export a trace definition that you can use to create a collection set that uses the Generic SQL Trace collector type.</span></span> <span data-ttu-id="25701-104">Questo processo è costituito da due operazioni:</span><span class="sxs-lookup"><span data-stu-id="25701-104">There are two parts to this process:</span></span>  
  
1.  <span data-ttu-id="25701-105">Creazione ed esportazione di una traccia di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25701-105">Create and export a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace.</span></span>  
  
2.  <span data-ttu-id="25701-106">Creazione di uno script per un nuovo set di raccolta basato su una traccia esportata.</span><span class="sxs-lookup"><span data-stu-id="25701-106">Script a new collection set based on an exported trace.</span></span>  
  
 <span data-ttu-id="25701-107">Lo scenario per le procedure seguenti comporta la raccolta di dati su tutte le stored procedure il cui completamento richiede almeno 80 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="25701-107">The scenario for the following procedures involves collecting data about any stored procedure that requires 80 milliseconds or longer to complete.</span></span> <span data-ttu-id="25701-108">Per completare queste procedure è necessario essere in grado di effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25701-108">In order to complete these procedures you should be able to:</span></span>  
  
-   <span data-ttu-id="25701-109">Utilizzare [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per creare e configurare una traccia.</span><span class="sxs-lookup"><span data-stu-id="25701-109">Use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create and configure a trace.</span></span>  
  
-   <span data-ttu-id="25701-110">Utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per aprire, modificare ed eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="25701-110">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to open, edit, and execute a query.</span></span>  
  
### <a name="create-and-export-a-sql-server-profiler-trace"></a><span data-ttu-id="25701-111">Creazione ed esportazione di una traccia di SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="25701-111">Create and export a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="25701-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25701-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="25701-113">Scegliere **SQL Server Profiler** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="25701-113">(On the **Tools** menu, click **SQL Server Profiler**.)</span></span>  
  
2.  <span data-ttu-id="25701-114">Nella finestra di dialogo **Connetti al server** fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="25701-114">In the **Connect to Server** dialog box, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="25701-115">Per questo scenario, assicurarsi che i valori di durata siano configurati per essere visualizzati in millisecondi (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="25701-115">For this scenario, ensure that duration values are configured to display in milliseconds (the default).</span></span> <span data-ttu-id="25701-116">A questo scopo, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="25701-116">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="25701-117">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="25701-117">On the **Tools** menu, click **Options**.</span></span>  
  
    2.  <span data-ttu-id="25701-118">Nell'area **Opzioni di visualizzazione** assicurarsi che la casella di controllo Mostra i valori nella colonna Durata in microsecondi sia deselezionata.</span><span class="sxs-lookup"><span data-stu-id="25701-118">In the **Display Options** area, ensure that the Show values in Duration column in microseconds check box is cleared.</span></span>  
  
    3.  <span data-ttu-id="25701-119">Fare clic su **OK** per chiudere la finestra di dialogo **Opzioni generali** .</span><span class="sxs-lookup"><span data-stu-id="25701-119">Click **OK** to close the **General Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="25701-120">Scegliere **Nuova traccia** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="25701-120">On the **File** menu, click **New Trace**.</span></span>  
  
5.  <span data-ttu-id="25701-121">Nella finestra di dialogo **Connetti al server** selezionare il server con cui stabilire la connessione, quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="25701-121">In the **Connect to Server** dialog box, select the server that you want to connect to, and then click **Connect**.</span></span>  
  
     <span data-ttu-id="25701-122">Verrà visualizzata la finestra di dialogo **Proprietà traccia** .</span><span class="sxs-lookup"><span data-stu-id="25701-122">The **Trace Properties** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="25701-123">Nella scheda **Generale** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="25701-123">On the **General** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="25701-124">Nella casella **Nome traccia** digitare il nome da usare per la traccia.</span><span class="sxs-lookup"><span data-stu-id="25701-124">In the **Trace name** box, type the name that you want to use for the trace.</span></span> <span data-ttu-id="25701-125">Per questo esempio, il nome della traccia è `SPgt80`.</span><span class="sxs-lookup"><span data-stu-id="25701-125">For this example, the trace name is `SPgt80`.</span></span>  
  
    2.  <span data-ttu-id="25701-126">Nell'elenco **Modello**selezionare il modello da usare per la traccia.</span><span class="sxs-lookup"><span data-stu-id="25701-126">In the **Use the template list**, select the template to use for the trace.</span></span> <span data-ttu-id="25701-127">Per questo esempio, fare clic su **TSQL_SPs**.</span><span class="sxs-lookup"><span data-stu-id="25701-127">For this example, click **TSQL_SPs**.</span></span>  
  
7.  <span data-ttu-id="25701-128">Nella scheda **Selezione eventi** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="25701-128">On the **Events Selection** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="25701-129">Identificare gli eventi da utilizzare per la traccia.</span><span class="sxs-lookup"><span data-stu-id="25701-129">Identify the events to use for the trace.</span></span> <span data-ttu-id="25701-130">Per questo esempio, deselezionare tutte le caselle di controllo nella colonna **Eventi** , tranne **ExistingConnection** e **SP:Completed**.</span><span class="sxs-lookup"><span data-stu-id="25701-130">For this example, clear all check boxes in the **Events** column, except for **ExistingConnection** and **SP:Completed**.</span></span>  
  
    2.  <span data-ttu-id="25701-131">Nell'angolo in basso a destra selezionare la casella di controllo **Mostra tutte le colonne** .</span><span class="sxs-lookup"><span data-stu-id="25701-131">In the lower-right corner, select the **Show all columns** check box.</span></span>  
  
    3.  <span data-ttu-id="25701-132">Fare clic sulla riga **SP:Completed** .</span><span class="sxs-lookup"><span data-stu-id="25701-132">Click the **SP:Completed** row.</span></span>  
  
    4.  <span data-ttu-id="25701-133">Scorrere la riga fino alla colonna **Durata** , quindi selezionare la casella di controllo **Durata** .</span><span class="sxs-lookup"><span data-stu-id="25701-133">Scroll across the row to the **Duration** column, and then select the **Duration** check box.</span></span>  
  
8.  <span data-ttu-id="25701-134">Nell'angolo in basso a destra fare clic su **Filtri colonne** per aprire la finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="25701-134">In the lower-right corner, click **Column Filters** to open the **Edit Filter** dialog box.</span></span> <span data-ttu-id="25701-135">Nella finestra di dialogo **Modifica filtro** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="25701-135">In the **Edit Filter** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="25701-136">Nell'elenco di filtri fare clic su **Durata**.</span><span class="sxs-lookup"><span data-stu-id="25701-136">In the filter list, click **Duration**.</span></span>  
  
    2.  <span data-ttu-id="25701-137">Nella finestra operatore booleano espandere il nodo **maggiore o uguale** a, digitare `80` come valore, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="25701-137">In the Boolean operator window, expand the **Greater than or equal** node, type `80` as the value, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="25701-138">Fare clic su **Esegui** per avviare la traccia.</span><span class="sxs-lookup"><span data-stu-id="25701-138">Click **Run** to start the trace.</span></span>  
  
10. <span data-ttu-id="25701-139">Sulla barra degli strumenti fare clic su **Arresta traccia selezionata** o **Sospendi traccia selezionata**.</span><span class="sxs-lookup"><span data-stu-id="25701-139">On the toolbar, click **Stop Selected Trace** or **Pause Selected Trace**.</span></span>  
  
11. <span data-ttu-id="25701-140">Scegliere **Esporta** dal menu **File**, fare clic su **Crea script per definizione traccia**, quindi su **Per set di raccolta Traccia SQL**.</span><span class="sxs-lookup"><span data-stu-id="25701-140">On the **File** menu, point to **Export**, point to **Script Trace Definition**, and then click **For SQL Trace Collection Set**.</span></span>  
  
12. <span data-ttu-id="25701-141">Nella casella **Nome file** della finestra di dialogo **Salva con nome** digitare il nome da usare per la definizione della traccia, quindi salvarlo nel percorso desiderato.</span><span class="sxs-lookup"><span data-stu-id="25701-141">In the **Save As** dialog box, type the name that you want to use for the trace definition in the **File name** box, and then save it in the location that you want.</span></span> <span data-ttu-id="25701-142">Per questo esempio, il nome del file è identico al nome della traccia, ovvero SPgt80.</span><span class="sxs-lookup"><span data-stu-id="25701-142">For this example, the file name is the same as the trace name (SPgt80).</span></span>  
  
13. <span data-ttu-id="25701-143">Fare clic su **OK** quando si riceve un messaggio indicante che il file è stato salvato correttamente, quindi chiudere [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25701-143">Click **OK** when you receive a message that the file was successfully saved, and then close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="script-a-new-collection-set-from-a-sql-server-profiler-trace"></a><span data-ttu-id="25701-144">Creazione di uno script per un nuovo set di raccolta da una traccia di SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="25701-144">Script a new collection set from a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="25701-145">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Apri** dal menu **File** , quindi fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="25701-145">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, point to **Open,** and then click **File**.</span></span>  
  
2.  <span data-ttu-id="25701-146">Nella finestra di dialogo **Apri file** trovare e aprire il file creato nella procedura precedente (SPgt80).</span><span class="sxs-lookup"><span data-stu-id="25701-146">In the **Open File** dialog box, locate and then open the file that you created in the previous procedure (SPgt80).</span></span>  
  
     <span data-ttu-id="25701-147">Le informazioni sulla traccia salvate in precedenza verranno aperte in una finestra di query e unite in uno script che è possibile eseguire per creare il nuovo set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="25701-147">The trace information that you saved is opened in a Query window and merged into a script that you can run to create the new collection set.</span></span>  
  
3.  <span data-ttu-id="25701-148">Scorrere lo script ed eseguire le sostituzioni seguenti, indicate nel testo di commento dello script:</span><span class="sxs-lookup"><span data-stu-id="25701-148">Scroll through the script and make the following replacements, which are noted in the script comment text:</span></span>  
  
    -   <span data-ttu-id="25701-149">Sostituire **SQLTrace Collection Set Name Here** con il nome che si vuole usare per il set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="25701-149">Replace **SQLTrace Collection Set Name Here** with the name that you want to use for the collection set.</span></span> <span data-ttu-id="25701-150">Per questo esempio, assegnare al set di raccolta il nome `SPROC_CollectionSet`.</span><span class="sxs-lookup"><span data-stu-id="25701-150">For this example, name the collection set `SPROC_CollectionSet`.</span></span>  
  
    -   <span data-ttu-id="25701-151">Sostituire **SQLTrace Collection Item Name Here** con il nome che si vuole usare per l'elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="25701-151">Replace **SQLTrace Collection Item Name Here** with the name that you want to use for the collection item.</span></span> <span data-ttu-id="25701-152">Per questo esempio, assegnare all'elemento della raccolta il nome `SPROC_Collection_Item`.</span><span class="sxs-lookup"><span data-stu-id="25701-152">For this example, name the collection item `SPROC_Collection_Item`.</span></span>  
  
4.  <span data-ttu-id="25701-153">Fare clic su **Esegui** per eseguire la query e creare il set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="25701-153">Click **Execute** to run the query and to create the collection set.</span></span>  
  
5.  <span data-ttu-id="25701-154">In Esplora oggetti verificare che il set di raccolta sia stato creato.</span><span class="sxs-lookup"><span data-stu-id="25701-154">In Object Explorer, verify that the collection set was created.</span></span> <span data-ttu-id="25701-155">A questo scopo, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="25701-155">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="25701-156">Fare clic con il pulsante destro del mouse su **Gestione**, quindi scegliere **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="25701-156">Right-click **Management**, and then click **Refresh**.</span></span>  
  
    2.  <span data-ttu-id="25701-157">Espandere **Gestione**, quindi **Raccolta dati**.</span><span class="sxs-lookup"><span data-stu-id="25701-157">Expand **Management**, and then expand **Data Collection**.</span></span>  
  
     <span data-ttu-id="25701-158">Il `SPROC_CollectionSet` set di raccolta viene visualizzato allo stesso livello del nodo **set di raccolta dati di sistema** .</span><span class="sxs-lookup"><span data-stu-id="25701-158">The `SPROC_CollectionSet` collection set appears at the same level as the **System Data Collection Sets** node.</span></span> <span data-ttu-id="25701-159">Per impostazione predefinita, il set di raccolta è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="25701-159">By default, the collection set is disabled.</span></span>  
  
6.  <span data-ttu-id="25701-160">Utilizzare Esplora oggetti per modificare le proprietà di SPROC_CollectionSet, ad esempio la modalità di raccolta e la pianificazione di caricamento.</span><span class="sxs-lookup"><span data-stu-id="25701-160">Use Object Explorer to edit the properties of SPROC_CollectionSet, such as the collection mode and upload schedule.</span></span> <span data-ttu-id="25701-161">Seguire le stesse procedure utilizzate per i set di raccolta dati di sistema forniti con l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="25701-161">Follow the same procedures that you would for the System Data collection sets that are provided with the data collector.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25701-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="25701-162">Example</span></span>  
 <span data-ttu-id="25701-163">L'esempio di codice seguente rappresenta lo script finale risultante dai passaggi descritti nelle procedure precedenti.</span><span class="sxs-lookup"><span data-stu-id="25701-163">The following code sample is the final script resulting from the steps documented in the preceding procedures.</span></span>  
  
```  
/*************************************************************/  
-- SQL Trace collection set generated from SQL Server Profiler  
-- Date: 11/19/2007  12:55:31 AM  
/*************************************************************/  
  
USE msdb  
GO  
  
BEGIN TRANSACTION  
BEGIN TRY  
  
-- Define collection set  
-- ***  
-- *** Replace 'SqlTrace Collection Set Name Here' in the   
-- *** following script with the name you want  
-- *** to use for the collection set.  
-- ***  
DECLARE @collection_set_id int;  
EXEC [dbo].[sp_syscollector_create_collection_set]  
    @name = N'SPROC_CollectionSet',  
    @schedule_name = N'CollectorSchedule_Every_15min',  
    @collection_mode = 0, -- cached mode needed for Trace collections  
    @logging_level = 0, -- minimum logging  
    @days_until_expiration = 5,  
    @description = N'Collection set generated by SQL Server Profiler',  
    @collection_set_id = @collection_set_id output;  
SELECT @collection_set_id;  
  
-- Define input and output variables for the collection item.  
DECLARE @trace_definition xml;  
DECLARE @collection_item_id int;  
  
-- Define the trace parameters as an XML variable  
SELECT @trace_definition = convert(xml,   
N'<ns:SqlTraceCollector xmlns:ns"DataCollectorType" use_default="0">  
<Events>  
  <EventType name="Sessions">  
    <Event id="17" name="ExistingConnection" columnslist="1,2,14,26,3,35,12" />  
  </EventType>  
  <EventType name="Stored Procedures">  
    <Event id="43" name="SP:Completed" columnslist="1,2,26,34,3,35,12,13,14,22" />  
  </EventType>  
</Events>  
<Filters>  
  <Filter columnid="13" columnname="Duration" logical_operator="AND" comparison_operator="GE" value="80000L" />  
</Filters>  
</ns:SqlTraceCollector>  
');  
  
-- Retrieve the collector type GUID for the trace collector type.  
DECLARE @collector_type_GUID uniqueidentifier;  
SELECT @collector_type_GUID = collector_type_uid FROM [dbo].[syscollector_collector_types] WHERE name = N'Generic SQL Trace Collector Type';  
  
-- Create the trace collection item.  
-- ***  
-- *** Replace 'SqlTrace Collection Item Name Here' in   
-- *** the following script with the name you want to  
-- *** use for the collection item.  
-- ***  
EXEC [dbo].[sp_syscollector_create_collection_item]  
   @collection_set_id = @collection_set_id,  
   @collector_type_uid = @collector_type_GUID,  
   @name = N'SPROC_Collection_Item',  
   @frequency = 900, -- specified the frequency for checking to see if trace is still running  
   @parameters = @trace_definition,  
   @collection_item_id = @collection_item_id output;  
SELECT @collection_item_id;  
  
COMMIT TRANSACTION;  
END TRY  
  
BEGIN CATCH  
ROLLBACK TRANSACTION;  
DECLARE @ErrorMessage nvarchar(4000);  
DECLARE @ErrorSeverity int;  
DECLARE @ErrorState int;  
DECLARE @ErrorNumber int;  
DECLARE @ErrorLine int;  
DECLARE @ErrorProcedure nvarchar(200);  
SELECT @ErrorLine = ERROR_LINE(),  
       @ErrorSeverity = ERROR_SEVERITY(),  
       @ErrorState = ERROR_STATE(),  
       @ErrorNumber = ERROR_NUMBER(),  
       @ErrorMessage = ERROR_MESSAGE(),  
       @ErrorProcedure = ISNULL(ERROR_PROCEDURE(), '-');  
RAISERROR (14684, @ErrorSeverity, 1 , @ErrorNumber, @ErrorSeverity, @ErrorState, @ErrorProcedure, @ErrorLine, @ErrorMessage);  
END CATCH;  
GO  
```  
  
  
