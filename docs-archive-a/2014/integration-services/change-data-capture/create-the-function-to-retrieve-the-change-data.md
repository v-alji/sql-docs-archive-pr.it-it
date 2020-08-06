---
title: Creare la funzione per il recupero dei dati delle modifiche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],creating function
ms.assetid: 55dd0946-bd67-4490-9971-12dfb5b9de94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc1d5af0a64225aca4ff54570ad6504d25d62812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724051"
---
# <a name="create-the-function-to-retrieve-the-change-data"></a><span data-ttu-id="7a684-102">Creazione della funzione per il recupero dei dati delle modifiche</span><span class="sxs-lookup"><span data-stu-id="7a684-102">Create the Function to Retrieve the Change Data</span></span>
  <span data-ttu-id="7a684-103">Dopo avere completato il flusso di controllo per un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che esegue un caricamento incrementale dei dati delle modifiche, l'attività successiva consiste nella creazione di una funzione con valori di tabella per il recupero di tali dati.</span><span class="sxs-lookup"><span data-stu-id="7a684-103">After completing the control flow for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the next task is to create a table-valued function that retrieves the change data.</span></span> <span data-ttu-id="7a684-104">Questa funzione deve essere creata solo una volta, prima del primo caricamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="7a684-104">You only have to create this function one time before the first incremental load.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a684-105">La creazione di una funzione per il recupero dei dati delle modifiche rappresenta il secondo passaggio del processo di creazione di un pacchetto che esegue il caricamento incrementale di tali dati.</span><span class="sxs-lookup"><span data-stu-id="7a684-105">The creation of a function to retrieve the change data is the second step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="7a684-106">Per una descrizione del processo completo di creazione del pacchetto, vedere [Change Data Capture &#40;SSIS &#41;](change-data-capture-ssis.md) (Modificare i dati di acquisizione &#40;SSIS &#41;).</span><span class="sxs-lookup"><span data-stu-id="7a684-106">For a description of the overall process for creating this package, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations-for-change-data-capture-functions"></a><span data-ttu-id="7a684-107">Considerazioni sulla progettazione per le funzioni Change Data Capture</span><span class="sxs-lookup"><span data-stu-id="7a684-107">Design Considerations for Change Data Capture Functions</span></span>  
 <span data-ttu-id="7a684-108">Per recuperare i dati delle modifiche, un componente di origine nel flusso di dati del pacchetto chiama una delle funzioni Change Data Capture seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a684-108">To retrieve change data, a source component in the data flow of the package calls one of the following change data capture query functions:</span></span>  
  
-   <span data-ttu-id="7a684-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** Per questa query, la singola riga restituita per ogni aggiornamento contiene lo stato finale di ogni riga modificata.</span><span class="sxs-lookup"><span data-stu-id="7a684-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** For this query, the single row returned for each update contains the final state of each changed row.</span></span> <span data-ttu-id="7a684-110">Nella maggior parte dei casi i dati restituiti da una query sono necessari solo per modifiche totali.</span><span class="sxs-lookup"><span data-stu-id="7a684-110">In most cases, you only need the data returned by a query for net changes.</span></span> <span data-ttu-id="7a684-111">Per altre informazioni, vedere [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a684-111">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
-   <span data-ttu-id="7a684-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** Questa query restituisce tutte le modifiche apportate in ogni riga durante l'intervallo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="7a684-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** This query returns all the changes that have occurred in each row during the capture interval.</span></span> <span data-ttu-id="7a684-113">Per altre informazioni, vedere [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a684-113">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="7a684-114">Il componente di origine passa quindi i risultati restituiti dalla funzione a destinazioni e trasformazioni a valle, che applicano i dati delle modifiche alla destinazione finale.</span><span class="sxs-lookup"><span data-stu-id="7a684-114">The source component then takes the results returned by the function and passes them to downstream transformations and destinations, which apply the change data to the final destination.</span></span>  
  
 <span data-ttu-id="7a684-115">Un componente di origine di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , tuttavia, non è in grado di chiamare direttamente le funzioni di acquisizioni dei dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="7a684-115">However, an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component cannot call these change data capture functions directly.</span></span> <span data-ttu-id="7a684-116">Un componente di origine di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] richiede i metadati sulle colonne restituite dalla query.</span><span class="sxs-lookup"><span data-stu-id="7a684-116">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component requires metadata about the columns that the query returns.</span></span> <span data-ttu-id="7a684-117">Le funzioni Change Data Capture non definiscono le colonne della relativa tabella di output.</span><span class="sxs-lookup"><span data-stu-id="7a684-117">The change data capture functions do not define the columns of their output table.</span></span> <span data-ttu-id="7a684-118">Di conseguenza, le funzioni non restituiscono metadati sufficienti per un componente di origine di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a684-118">Thus, these functions do not return sufficient metadata for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
 <span data-ttu-id="7a684-119">Viene utilizzata invece una funzione wrapper con valori di tabella perché questo tipo di funzione definisce in modo esplicito le colonne della relativa tabella di output nella clausola RETURNS.</span><span class="sxs-lookup"><span data-stu-id="7a684-119">Instead, you use a table-valued wrapper function because this kind of function explicitly defines the columns of its output table in its RETURNS clause.</span></span> <span data-ttu-id="7a684-120">Questa definizione esplicita di colonne fornisce i metadati necessari per un componente di origine di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a684-120">This explicit definition of columns provides the metadata that an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component needs.</span></span> <span data-ttu-id="7a684-121">È necessario creare questa funzione per ogni tabella per cui si desidera recuperare dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="7a684-121">You have to create this function for each table for which you want to retrieve change data.</span></span>  
  
 <span data-ttu-id="7a684-122">Sono disponibili due opzioni per la creazione della funzione wrapper con valori di tabella che chiama la funzione di query Change Data Capture:</span><span class="sxs-lookup"><span data-stu-id="7a684-122">You have two options for creating the table-valued wrapper function that calls the change data capture query function:</span></span>  
  
-   <span data-ttu-id="7a684-123">È possibile chiamare la stored procedure di sistema **sys.sp_cdc_generate_wrapper_function** per creare automaticamente le funzioni con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="7a684-123">You can call the **sys.sp_cdc_generate_wrapper_function** system stored procedure to create the table-valued functions for you.</span></span>  
  
-   <span data-ttu-id="7a684-124">È possibile scrivere una funzione con valori di tabella personalizzata tramite le linee guida e l'esempio presenti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7a684-124">You can write your own table-valued function by using the guidelines and the example in this topic.</span></span>  
  
## <a name="calling-a-stored-procedure-to-create-the-table-valued-function"></a><span data-ttu-id="7a684-125">Chiamata di una stored procedure per la creazione della funzione con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="7a684-125">Calling a Stored Procedure to Create the Table-valued Function</span></span>  
 <span data-ttu-id="7a684-126">Il modo più semplice e rapido per creare le funzioni con valori di tabella necessarie consiste nel chiamare la stored procedure di sistema **sys.sp_cdc_generate_wrapper_function** .</span><span class="sxs-lookup"><span data-stu-id="7a684-126">The quickest and easiest way to create the table-valued functions that you need is to call the **sys.sp_cdc_generate_wrapper_function** system stored procedure.</span></span> <span data-ttu-id="7a684-127">Questa stored procedure genera gli script per creare le funzioni wrapper specificamente progettate per soddisfare le esigenze di un componente di origine di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a684-127">This stored procedure generates scripts to create wrapper functions that are designed specifically to meet the needs of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7a684-128">La stored procedure di sistema **sys.sp_cdc_generate_wrapper_function** non crea direttamente le funzioni wrapper,</span><span class="sxs-lookup"><span data-stu-id="7a684-128">The **sys.sp_cdc_generate_wrapper_function** system stored procedure does not directly create the wrapper functions.</span></span> <span data-ttu-id="7a684-129">ma genera gli script CREATE per le funzioni wrapper.</span><span class="sxs-lookup"><span data-stu-id="7a684-129">Instead, the stored procedure generates the CREATE scripts for the wrapper functions.</span></span> <span data-ttu-id="7a684-130">Lo sviluppatore deve eseguire gli script CREATE generati dalla stored procedure affinché le funzioni wrapper possano essere chiamate da un pacchetto del caricamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="7a684-130">The developer must run the CREATE scripts that the stored procedure generates before an incremental load package can call the wrapper functions.</span></span>  
  
 <span data-ttu-id="7a684-131">Per comprendere il modo in cui utilizzare questa stored procedure di sistema è necessario capire le operazioni eseguite dalla procedura, gli script generati dalla procedura e le funzioni wrapper create dagli script.</span><span class="sxs-lookup"><span data-stu-id="7a684-131">To understand how to use this system stored procedure, you should understand what the procedure does, what scripts the procedure generates, and what wrapper functions the scripts create.</span></span>  
  
### <a name="understanding-and-using-the-stored-procedure"></a><span data-ttu-id="7a684-132">Informazioni sulla stored procedure e relativo utilizzo</span><span class="sxs-lookup"><span data-stu-id="7a684-132">Understanding and Using the Stored Procedure</span></span>  
 <span data-ttu-id="7a684-133">La stored procedure di sistema **sys.sp_cdc_generate_wrapper_function** genera gli script per creare le funzioni wrapper da usare con i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a684-133">The **sys.sp_cdc_generate_wrapper_function** system stored procedure generates scripts to create wrapper functions for use by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="7a684-134">Di seguito vengono riportate le prime righe della definizione della stored procedure:</span><span class="sxs-lookup"><span data-stu-id="7a684-134">Here are the first few lines of the definition of the stored procedure:</span></span>  
  
 `CREATE PROCEDURE sys.sp_cdc_generate_wrapper_function`  
  
 `(`  
  
 `@capture_instance sysname = null`  
  
 `@closed_high_end_point bit = 1,`  
  
 `@column_list = null,`  
  
 `@update_flag_list = null`  
  
 `)`  
  
 <span data-ttu-id="7a684-135">Tutti i parametri per la stored procedure sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="7a684-135">All the parameters for the stored procedure are optional.</span></span> <span data-ttu-id="7a684-136">Se si chiama la stored procedure senza fornire alcun valore per i parametri, la stored procedure crea funzioni wrapper per tutte le istanze di acquisizione a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="7a684-136">If you call the stored procedure without supplying values for any of the parameters, the stored procedure creates wrapper functions for all the capture instances to which you have access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a684-137">Per altre informazioni sulla sintassi di questa stored procedure e sui relativi parametri, vedere [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a684-137">For more information about the syntax of this stored procedure and its parameters, see [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span></span>  
  
 <span data-ttu-id="7a684-138">La stored procedure genera sempre una funzione wrapper per restituire tutte le modifiche da ogni istanza di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="7a684-138">The stored procedure always generates a wrapper function to return all changes from each capture instance.</span></span> <span data-ttu-id="7a684-139">Se il *@supports_net_changes* parametro è stato impostato al momento della creazione dell'istanza di acquisizione, il stored procedure genera anche una funzione wrapper per restituire le modifiche totali da ogni istanza di acquisizione applicabile.</span><span class="sxs-lookup"><span data-stu-id="7a684-139">If the *@supports_net_changes* parameter was set when the capture instance was created, the stored procedure also generates a wrapper function to return net changes from each applicable capture instance.</span></span>  
  
 <span data-ttu-id="7a684-140">La stored procedure restituisce un set di risultati con due colonne:</span><span class="sxs-lookup"><span data-stu-id="7a684-140">The stored procedure returns a result set with two columns:</span></span>  
  
-   <span data-ttu-id="7a684-141">Il nome della funzione wrapper generata dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7a684-141">The name of the wrapper function that the stored procedure has generated.</span></span> <span data-ttu-id="7a684-142">La stored procedure deduce il nome della funzione dal nome dell'istanza di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="7a684-142">This stored procedure derives the function name from the name of the capture instance name.</span></span> <span data-ttu-id="7a684-143">Il nome della funzione è 'fn_all_changes_' seguito dal nome dell'istanza di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="7a684-143">(The function name is 'fn_all_changes_' followed by the capture instance name.</span></span> <span data-ttu-id="7a684-144">Il prefisso utilizzato per la funzione di rilevamento delle modifiche delta, se creato, è 'fn_net_changes_'.</span><span class="sxs-lookup"><span data-stu-id="7a684-144">The prefix used for the net changes function, if it is created, is 'fn_net_changes_'.)</span></span>  
  
-   <span data-ttu-id="7a684-145">L'istruzione CREATE per la funzione wrapper.</span><span class="sxs-lookup"><span data-stu-id="7a684-145">The CREATE statement for the wrapper function.</span></span>  
  
### <a name="understanding-and-using-the-scripts-created-by-the-stored-procedure"></a><span data-ttu-id="7a684-146">Informazioni sugli script creati dalla stored procedure e relativo utilizzo</span><span class="sxs-lookup"><span data-stu-id="7a684-146">Understanding and Using the Scripts Created by the Stored Procedure</span></span>  
 <span data-ttu-id="7a684-147">Uno sviluppatore usa in genere un'istruzione INSERT...EXEC per chiamare la stored procedure **sys.sp_cdc_generate_wrapper_function** e salvare gli script creati dalla stored procedure in una tabella temporanea.</span><span class="sxs-lookup"><span data-stu-id="7a684-147">Typically, a developer would use an INSERT...EXEC statement to call the **sys.sp_cdc_generate_wrapper_function** stored procedure and save the scripts that the stored procedure creates to a temporary table.</span></span> <span data-ttu-id="7a684-148">Ogni script può quindi essere selezionato singolarmente ed eseguito per creare la funzione wrapper corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7a684-148">Each script could then be individually selected and run to create the corresponding wrapper function.</span></span> <span data-ttu-id="7a684-149">Uno sviluppatore può tuttavia utilizzare anche un set di comandi SQL per eseguire tutti gli script CREATE, come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="7a684-149">However, a developer could also use one set of SQL commands to run all the CREATE scripts, as shown in the following sample code:</span></span>  
  
```  
create table #wrapper_functions  
      (function_name sysname, create_stmt nvarchar(max))  
insert into #wrapper_functions  
exec sys.sp_cdc_generate_wrapper_function  
  
declare @stmt nvarchar(max)  
declare #hfunctions cursor local fast_forward for   
      select create_stmt from #wrapper_functions  
open #hfunctions  
fetch #hfunctions into @stmt  
while (@@fetch_status <> -1)  
begin  
      exec sp_executesql @stmt  
      fetch #hfunctions into @stmt  
end  
close #hfunctions  
deallocate #hfunctions  
```  
  
### <a name="understanding-and-using-the-functions-created-by-the-stored-procedure"></a><span data-ttu-id="7a684-150">Informazioni sulle funzioni create dalla stored procedure e relativo utilizzo</span><span class="sxs-lookup"><span data-stu-id="7a684-150">Understanding and Using the Functions Created by the Stored Procedure</span></span>  
 <span data-ttu-id="7a684-151">Per esaminare sistematicamente la sequenza temporale dei dati modificati acquisiti, le funzioni wrapper generate si aspettano che il *@end_time* parametro per un intervallo sia il *@start_time* parametro per l'intervallo successivo.</span><span class="sxs-lookup"><span data-stu-id="7a684-151">To systematically walk the timeline of captured change data, the generated wrapper functions expect that the *@end_time* parameter for one interval will be the *@start_time* parameter for the subsequent interval.</span></span> <span data-ttu-id="7a684-152">Quando viene rispettata questa convenzione, le funzioni wrapper generate possono effettuare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a684-152">When this convention is followed, the generated wrapper functions can do the following tasks:</span></span>  
  
-   <span data-ttu-id="7a684-153">Eseguire il mapping dei valori di data e ora ai valori LSN utilizzati internamente.</span><span class="sxs-lookup"><span data-stu-id="7a684-153">Map the date/time values to the LSN values that are used internally.</span></span>  
  
-   <span data-ttu-id="7a684-154">Verificare che i dati non vengano persi o ripetuti.</span><span class="sxs-lookup"><span data-stu-id="7a684-154">Ensure that no data is lost or repeated.</span></span>  
  
 <span data-ttu-id="7a684-155">Per semplificare l'esecuzione di query su tutte le righe di una tabella delle modifiche, le funzioni wrapper generate supportano inoltre le convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a684-155">To make querying for all rows of a change table simpler, the generated wrapper functions also support the following conventions:</span></span>  
  
-   <span data-ttu-id="7a684-156">Se il parametro @start_time è null, le funzioni wrapper usano il valore LSN minimo nell'istanza di acquisizione come limite inferiore della query.</span><span class="sxs-lookup"><span data-stu-id="7a684-156">If the @start_time parameter is null, the wrapper functions use the lowest LSN value in the capture instance as the lower bound of the query.</span></span>  
  
-   <span data-ttu-id="7a684-157">Se il parametro @end_time è null, le funzioni wrapper usano il valore LSN massimo nell'istanza di acquisizione come limite superiore della query.</span><span class="sxs-lookup"><span data-stu-id="7a684-157">If the @end_time parameter is null, the wrapper functions use the highest LSN value in the capture instance as the upper bound of the query.</span></span>  
  
 <span data-ttu-id="7a684-158">La maggior parte degli utenti dovrebbe essere in grado di usare le funzioni wrapper create dalla stored procedure di sistema **sys.sp_cdc_generate_wrapper_function** senza apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="7a684-158">Most users should be able to use the wrapper functions that the **sys.sp_cdc_generate_wrapper_function** system stored procedure creates without modification.</span></span> <span data-ttu-id="7a684-159">Tuttavia, per personalizzare le funzioni wrapper, è necessario personalizzare gli script CREATE prima di eseguire gli script.</span><span class="sxs-lookup"><span data-stu-id="7a684-159">However, to customize the wrapper functions, you have to customize the CREATE scripts before you run the scripts.</span></span>  
  
 <span data-ttu-id="7a684-160">Quando il pacchetto chiama le funzioni wrapper, il pacchetto deve fornire i valori per tre parametri.</span><span class="sxs-lookup"><span data-stu-id="7a684-160">When your package calls the wrapper functions, the package must supply values for three parameters.</span></span> <span data-ttu-id="7a684-161">Questi tre parametri sono analoghi ai tre parametri utilizzati dalle funzioni Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="7a684-161">These three parameters are like the three parameters that the change data capture functions use.</span></span> <span data-ttu-id="7a684-162">I tre parametri sono:</span><span class="sxs-lookup"><span data-stu-id="7a684-162">These three parameters are as follows:</span></span>  
  
-   <span data-ttu-id="7a684-163">Il valore data/ora di inizio e il valore data/ora di fine per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="7a684-163">The starting date/time value and the ending date/time value for the interval.</span></span> <span data-ttu-id="7a684-164">Mentre le funzioni wrapper utilizzano i valori di data e ora come endpoint per l'intervallo di query, le funzioni Change Data Capture utilizzano due valori LSN come endpoint.</span><span class="sxs-lookup"><span data-stu-id="7a684-164">While the wrapper functions use date/time values as the end points for the query interval, the change data capture functions use two LSN values as the end points.</span></span>  
  
-   <span data-ttu-id="7a684-165">Il filtro di riga.</span><span class="sxs-lookup"><span data-stu-id="7a684-165">The row filter.</span></span> <span data-ttu-id="7a684-166">Sia per le funzioni wrapper che per le funzioni di Change Data Capture, il *@row_filter_option* parametro è lo stesso.</span><span class="sxs-lookup"><span data-stu-id="7a684-166">For both the wrapper functions and the change data capture functions, the *@row_filter_option* parameter is the same.</span></span> <span data-ttu-id="7a684-167">Per altre informazioni, vedere [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) e [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a684-167">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) and [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="7a684-168">Il set di risultati restituito dalle funzioni wrapper include i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a684-168">The result set returned by the wrapper functions includesthe following data:</span></span>  
  
-   <span data-ttu-id="7a684-169">Tutte le colonne di dati di modifica richieste.</span><span class="sxs-lookup"><span data-stu-id="7a684-169">All of the requested columns of change data.</span></span>  
  
-   <span data-ttu-id="7a684-170">Una colonna denominata __CDC_OPERATION che utilizza un campo di uno o due caratteri per identificare l'operazione associata alla riga.</span><span class="sxs-lookup"><span data-stu-id="7a684-170">A column named __CDC_OPERATION that uses a one- or two-character field to identify the operation that is associated with the row.</span></span> <span data-ttu-id="7a684-171">I valori validi per questo campo sono i seguenti: 'I' per inserimento, 'D' per eliminazione, 'UO' per aggiornamento di valori vecchi e 'UN' per aggiornamento di valori nuovi.</span><span class="sxs-lookup"><span data-stu-id="7a684-171">The valid values for this field are as follows: 'I' for insert, 'D' for delete, 'UO' for update old values, and 'UN' for update new values.</span></span>  
  
-   <span data-ttu-id="7a684-172">Aggiornare i flag, quando vengono richiesti, che vengono visualizzati come colonne bit dopo il codice dell'operazione e nell'ordine specificato nel *@update_flag_list* parametro.</span><span class="sxs-lookup"><span data-stu-id="7a684-172">Update flags, when you request them, that appear as bit columns after the operation code and in the order that is specified in the *@update_flag_list* parameter.</span></span> <span data-ttu-id="7a684-173">Per creare il nome di queste colonne, si aggiunge '_uflag' al nome della colonna associato.</span><span class="sxs-lookup"><span data-stu-id="7a684-173">These columns are named by appending '_uflag' to the associated column name.</span></span>  
  
 <span data-ttu-id="7a684-174">Se il pacchetto chiama una funzione wrapper che esegue una query su tutte le modifiche, la funzione wrapper restituisce anche le colonne __CDC_STARTLSN e \__CDC_SEQVAL.</span><span class="sxs-lookup"><span data-stu-id="7a684-174">If your package calls a wrapper function that queries for all changes, the wrapper function also returns the columns, __CDC_STARTLSN and \__CDC_SEQVAL.</span></span> <span data-ttu-id="7a684-175">Queste due colonne diventano rispettivamente la prima e la seconda colonna del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="7a684-175">These two columns become the first and second columns, respectively, of the result set.</span></span> <span data-ttu-id="7a684-176">La funzione wrapper ordina inoltre il set di risultati in base a queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="7a684-176">The wrapper function also sorts the result set based on these two columns.</span></span>  
  
## <a name="writing-your-own-table-value-function"></a><span data-ttu-id="7a684-177">Scrittura della funzione con valori di tabella personalizzata</span><span class="sxs-lookup"><span data-stu-id="7a684-177">Writing Your Own Table-Value Function</span></span>  
 <span data-ttu-id="7a684-178">È anche possibile usare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per scrivere una funzione wrapper con valori di tabella personalizzata che chiama la funzione di query Change Data Capture e archiviare la funzione wrapper con valori di tabella in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a684-178">You can also use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to write your own table-valued wrapper function that calls the change data capture query function, and store the table-valued wrapper function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7a684-179">Per altre informazioni sulla creazione di una funzione Transact-SQL, vedere [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a684-179">For more information about how to create a Transact-SQL function, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
 <span data-ttu-id="7a684-180">Nell'esempio seguente viene definita una funzione con valori di tabella per il recupero delle modifiche da una tabella Customer per l'intervallo di modifiche specificato.</span><span class="sxs-lookup"><span data-stu-id="7a684-180">The following example defines a table-valued function that retrieves changes from a Customer table for the specified change interval.</span></span> <span data-ttu-id="7a684-181">La funzione utilizza le funzioni Change Data Capture per eseguire il mapping tra i valori `datetime` e i valori dei numeri di sequenza del file di log (LSN) binario utilizzati dalle tabelle delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="7a684-181">This function uses change data capture functions to map the `datetime` values to the binary log sequence number (LSN) values that the change tables use internally.</span></span> <span data-ttu-id="7a684-182">Questa funzione gestisce inoltre diverse condizioni speciali:</span><span class="sxs-lookup"><span data-stu-id="7a684-182">This function also handles several special conditions:</span></span>  
  
-   <span data-ttu-id="7a684-183">Quando viene passato un valore Null per l'ora di inizio, questa funzione utilizza il valore disponibile per primo.</span><span class="sxs-lookup"><span data-stu-id="7a684-183">When a null value is passed for the starting time, this function uses the earliest available value.</span></span>  
  
-   <span data-ttu-id="7a684-184">Quando viene passato un valore Null per l'ora di fine, questa funzione utilizza il valore disponibile per ultimo.</span><span class="sxs-lookup"><span data-stu-id="7a684-184">When a null value is passed for the ending time, this function uses the latest available value.</span></span>  
  
-   <span data-ttu-id="7a684-185">Quando il numero LSN iniziale è uguale al numero LSN finale, a indicare in genere che non è presente alcun record per l'intervallo selezionato, la funzione viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="7a684-185">When the starting LSN is equal to the ending LSN, which usually indicates that there are no records for the selected interval, this function exits.</span></span>  
  
### <a name="example-of-a-table-value-function-that-queries-for-change-data"></a><span data-ttu-id="7a684-186">Esempio di una funzione con valori di tabella che esegue query per i dati delle modifiche</span><span class="sxs-lookup"><span data-stu-id="7a684-186">Example of a Table-Value Function that Queries for Change Data</span></span>  
  
```  
CREATE function CDCSample.uf_Customer (  
     @start_time datetime  
    ,@end_time datetime  
)  
returns @Customer table (  
     CustomerID int  
    ,TerritoryID int  
    ,CustomerType nchar(1)  
    ,rowguid uniqueidentifier  
    ,ModifiedDate datetime  
    ,CDC_OPERATION varchar(1)  
) as  
begin  
    declare @from_lsn binary(10), @to_lsn binary(10)  
  
    if (@start_time is null)  
        select @from_lsn = sys.fn_cdc_get_min_lsn('Customer')  
    else  
        select @from_lsn = sys.fn_cdc_increment_lsn(sys.fn_cdc_map_time_to_lsn('largest less than or equal',@start_time))  
  
    if (@end_time is null)  
        select @to_lsn = sys.fn_cdc_get_max_lsn()  
    else  
        select @to_lsn = sys.fn_cdc_map_time_to_lsn('largest less than or equal',@end_time)  
  
    if (@from_lsn = sys.fn_cdc_increment_lsn(@to_lsn))  
        return  
  
    -- Query for change data  
    insert into @Customer  
    select   
        CustomerID,      
        TerritoryID,   
        CustomerType,   
        rowguid,   
        ModifiedDate,   
        case __$operation  
                when 1 then 'D'  
                when 2 then 'I'  
                when 4 then 'U'  
                else null  
         end as CDC_OPERATION  
    from   
        cdc.fn_cdc_get_net_changes_Customer(@from_lsn, @to_lsn, 'all')  
  
    return  
end   
go  
  
```  
  
### <a name="retrieving-additional-metadata-with-the-change-data"></a><span data-ttu-id="7a684-187">Recupero di metadati aggiuntivi con i dati di modifica</span><span class="sxs-lookup"><span data-stu-id="7a684-187">Retrieving Additional Metadata with the Change Data</span></span>  
 <span data-ttu-id="7a684-188">Anche se la funzione con valori di tabella creata dall'utente illustrata in precedenza usa solo la colonna **__$operation**, la funzione **cdc.fn_cdc_get_net_changes_<capture_instance>** restituisce quattro colonne di metadati per ogni riga di modifica.</span><span class="sxs-lookup"><span data-stu-id="7a684-188">Although the user-created table-valued function shown earlier uses only the **__$operation** column, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns four columns of metadata for each change row.</span></span> <span data-ttu-id="7a684-189">Se si desidera utilizzare questi valori nel flusso di dati, è possibile restituirli come colonne aggiuntive dalla funzione wrapper con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="7a684-189">If you want to use these values in your data flow, you can return them as additional columns from the table-valued wrapper function.</span></span>  
  
|<span data-ttu-id="7a684-190">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a684-190">Column name</span></span>|<span data-ttu-id="7a684-191">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a684-191">Data type</span></span>|<span data-ttu-id="7a684-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a684-192">Description</span></span>|  
|-----------------|---------------|-----------------|  
|<span data-ttu-id="7a684-193">**__$start_lsn**</span><span class="sxs-lookup"><span data-stu-id="7a684-193">**__$start_lsn**</span></span>|`binary(10)`|<span data-ttu-id="7a684-194">Valore LSN associato al commit della transazione per la modifica.</span><span class="sxs-lookup"><span data-stu-id="7a684-194">LSN associated with the commit transaction for the change.</span></span><br /><br /> <span data-ttu-id="7a684-195">Tutte le modifiche di cui è stato eseguito il commit nella stessa transazione condividono lo stesso valore LSN di commit.</span><span class="sxs-lookup"><span data-stu-id="7a684-195">All changes committed in the same transaction share the same commit LSN.</span></span> <span data-ttu-id="7a684-196">Se, ad esempio, un'operazione di aggiornamento nella tabella di origine modifica due diverse righe, la tabella delle modifiche conterrà quattro righe, due con i valori precedenti e due con i nuovi valori, ognuna delle quali con lo stesso valore **__$start_lsn** .</span><span class="sxs-lookup"><span data-stu-id="7a684-196">For example, if an update operation on the source table modifies two different rows, the change table will contain four rows (two with the old values and two with the new values), each with the same **__$start_lsn** value.</span></span>|  
|<span data-ttu-id="7a684-197">**__$seqval**</span><span class="sxs-lookup"><span data-stu-id="7a684-197">**__$seqval**</span></span>|`binary(10)`|<span data-ttu-id="7a684-198">Valore di sequenza utilizzato per ordinare le modifiche alle righe in una transazione.</span><span class="sxs-lookup"><span data-stu-id="7a684-198">Sequence value that is used to order the row changes in a transaction.</span></span>|  
|<span data-ttu-id="7a684-199">**__$operation**</span><span class="sxs-lookup"><span data-stu-id="7a684-199">**__$operation**</span></span>|`int`|<span data-ttu-id="7a684-200">Operazione DML (Data Manipulation Language) associata alla modifica.</span><span class="sxs-lookup"><span data-stu-id="7a684-200">The data manipulation language (DML) operation associated with the change.</span></span> <span data-ttu-id="7a684-201">Può essere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a684-201">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="7a684-202">1 = eliminazione</span><span class="sxs-lookup"><span data-stu-id="7a684-202">1 = delete</span></span><br /><br /> <span data-ttu-id="7a684-203">2 = inserimento</span><span class="sxs-lookup"><span data-stu-id="7a684-203">2 = insert</span></span><br /><br /> <span data-ttu-id="7a684-204">3 = aggiornamento (valori precedenti all'operazione di aggiornamento)</span><span class="sxs-lookup"><span data-stu-id="7a684-204">3 = update (Values before the update operation.)</span></span><br /><br /> <span data-ttu-id="7a684-205">4 = aggiornamento (valori successivi all'operazione di aggiornamento)</span><span class="sxs-lookup"><span data-stu-id="7a684-205">4 = update (Values after the update operation.)</span></span>|  
|<span data-ttu-id="7a684-206">**__$update_mask**</span><span class="sxs-lookup"><span data-stu-id="7a684-206">**__$update_mask**</span></span>|`varbinary(128)`|<span data-ttu-id="7a684-207">Maschera di bit basata su numeri ordinali di colonna della tabella delle modifiche che identifica le colonne modificate.</span><span class="sxs-lookup"><span data-stu-id="7a684-207">A bitmask that is based on the column ordinals of the change table identifying those columns that changed.</span></span> <span data-ttu-id="7a684-208">È possibile esaminare questo valore se è necessario determinare le colonne modificate.</span><span class="sxs-lookup"><span data-stu-id="7a684-208">You could examine this value if you had to determine which columns have changed.</span></span>|  
|**\<captured source table columns>**|<span data-ttu-id="7a684-209">variabile</span><span class="sxs-lookup"><span data-stu-id="7a684-209">varies</span></span>|<span data-ttu-id="7a684-210">Le colonne rimanenti restituite dalla funzione sono le colonne della tabella di origine identificate come colonne acquisite durante la creazione dell'istanza di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="7a684-210">The remaining columns returned by the function are the columns from the source table that were identified as captured columns when the capture instance was created.</span></span> <span data-ttu-id="7a684-211">Se in origine non è stata specificata alcuna colonna nell'elenco delle colonne acquisite, verranno restituite tutte le colonne della tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="7a684-211">If no columns were originally specified in the captured column list, all columns in the source table are returned.</span></span>|  
  
 <span data-ttu-id="7a684-212">Per altre informazioni, vedere [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a684-212">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="7a684-213">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7a684-213">Next Step</span></span>  
 <span data-ttu-id="7a684-214">Dopo avere creato la funzione con valori di tabella per l'esecuzione di query per i dati delle modifiche, il passaggio successivo consiste nell'iniziare a progettare il flusso di dati nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7a684-214">After you have created the table-valued function that queries for change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="7a684-215">**Argomento successivo:** [Recuperare e interpretare i dati delle modifiche](retrieve-and-understand-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="7a684-215">**Next topic:** [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md)</span></span>  
  
  
