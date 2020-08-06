---
title: Preparare l'esecuzione di una query per i dati delle modifiche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],preparing query
ms.assetid: 9ea2db7a-3dca-4bbf-9903-cccd2d494b5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ab732389d5a747c596472f14f5229361dd46275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624291"
---
# <a name="prepare-to-query-for-the-change-data"></a><span data-ttu-id="adabc-102">Preparazione dell'esecuzione di una query per i dati delle modifiche</span><span class="sxs-lookup"><span data-stu-id="adabc-102">Prepare to Query for the Change Data</span></span>
  <span data-ttu-id="adabc-103">Nel flusso di controllo di un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per l'esecuzione di un caricamento incrementale dei dati delle modifiche, la terza e ultima attività consiste nel preparare l'esecuzione di una query per i dati delle modifiche e nell'aggiungere un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="adabc-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to prepare to query for the change data and add a Data Flow task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="adabc-104">La seconda attività per il flusso di controllo consiste nel verificare che i dati delle modifiche per l'intervallo selezionato siano pronti.</span><span class="sxs-lookup"><span data-stu-id="adabc-104">The second task for the control flow is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="adabc-105">Per altre informazioni su questa attività, vedere [Determinare se i dati delle modifiche sono pronti](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="adabc-105">For more information about this task, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span> <span data-ttu-id="adabc-106">Per una descrizione del processo complessivo di progettazione del flusso di controllo, vedere [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="adabc-106">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations"></a><span data-ttu-id="adabc-107">Considerazioni sulla progettazione</span><span class="sxs-lookup"><span data-stu-id="adabc-107">Design Considerations</span></span>  
 <span data-ttu-id="adabc-108">Per recuperare i dati delle modifiche, è necessario chiamare una funzione Transact-SQL con valori di tabella che accetti gli endpoint dell'intervallo come parametri di input e restituisca i dati delle modifiche per l'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="adabc-108">To retrieve the change data, you will call a Transact-SQL table-valued function that accepts the endpoints of the interval as input parameters and returns change data for the specified interval.</span></span> <span data-ttu-id="adabc-109">Un componente di origine nel flusso di dati chiama questa funzione.</span><span class="sxs-lookup"><span data-stu-id="adabc-109">A source component in the data flow calls this function.</span></span> <span data-ttu-id="adabc-110">Per informazioni su questo componente di origine, vedere [Recuperare e comprendere i dati delle modifiche](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="adabc-110">For information about this source component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
 <span data-ttu-id="adabc-111">I componenti di origine [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usati più di frequente, incluse l'origine OLE DB, l'origine ADO e l'origine ADO NET, non possono derivare informazioni sui parametri per una funzione valutata a livello di tabella.</span><span class="sxs-lookup"><span data-stu-id="adabc-111">The most frequently used [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source components, including the OLE DB source, the ADO source, and the ADO NET source, cannot derive parameter information for a table-valued function.</span></span> <span data-ttu-id="adabc-112">La maggior parte delle origini, pertanto, non può chiamare una funzione con parametri direttamente.</span><span class="sxs-lookup"><span data-stu-id="adabc-112">Therefore, most sources cannot call a parameterized function directly.</span></span>  
  
 <span data-ttu-id="adabc-113">Per passare i parametri di input alla funzione, sono disponibili due opzioni di progettazione:</span><span class="sxs-lookup"><span data-stu-id="adabc-113">You have two design options for passing the input parameters to the function:</span></span>  
  
-   <span data-ttu-id="adabc-114">**Assemblare la query con parametri come stringa**.</span><span class="sxs-lookup"><span data-stu-id="adabc-114">**Assemble the parameterized query as a string**.</span></span> <span data-ttu-id="adabc-115">È possibile utilizzare un'attività Script o un'attività Esegui SQL per assemblare una stringa SQL dinamica con valori di parametro specificati a livello di codice nella stringa.</span><span class="sxs-lookup"><span data-stu-id="adabc-115">You can use a Script task or an Execute SQL task to assemble a dynamic SQL string with parameter values hard-coded into the string.</span></span> <span data-ttu-id="adabc-116">È quindi possibile archiviare tale stringa in una variabile del pacchetto e utilizzarla per impostare la proprietà SqlCommand di un componente di origine.</span><span class="sxs-lookup"><span data-stu-id="adabc-116">Then, you can store this string in a package variable and use it to set the SqlCommand property of a source component.</span></span> <span data-ttu-id="adabc-117">Questo approccio ha esito positivo perché il componente di origine non richiede più informazioni sui parametri.</span><span class="sxs-lookup"><span data-stu-id="adabc-117">This approach succeeds because the source component no longer requires parameter information.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="adabc-118">Uno script precompilato è soggetto a un overhead minore rispetto a un'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="adabc-118">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="adabc-119">**Usare un wrapper con parametri**.</span><span class="sxs-lookup"><span data-stu-id="adabc-119">**Use a parameterized wrapper**.</span></span> <span data-ttu-id="adabc-120">In alternativa, è possibile creare una stored procedure con parametri come wrapper che chiama la funzione valutata a livello di tabella con parametri.</span><span class="sxs-lookup"><span data-stu-id="adabc-120">Alternatively, you can create a parameterized stored procedure as a wrapper that calls the parameterized table-valued function.</span></span> <span data-ttu-id="adabc-121">Questo approccio ha esito positivo perché un componente di origine è in grado di derivare correttamente le informazioni sui parametri per una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="adabc-121">This approach succeeds because a source component can successfully derive parameter information for a stored procedure.</span></span>  
  
 <span data-ttu-id="adabc-122">In questo argomento viene utilizzata la prima opzione di progettazione, assemblando una query con parametri come stringa.</span><span class="sxs-lookup"><span data-stu-id="adabc-122">This topic uses the first design option and assembles a parameterized query as a string.</span></span>  
  
## <a name="preparing-the-query"></a><span data-ttu-id="adabc-123">Preparazione della query</span><span class="sxs-lookup"><span data-stu-id="adabc-123">Preparing the Query</span></span>  
 <span data-ttu-id="adabc-124">Prima che sia possibile concatenare i valori dei parametri di input in una singola stringa di query, è necessario configurare le variabili del pacchetto necessarie per la query.</span><span class="sxs-lookup"><span data-stu-id="adabc-124">Before you can concatenate the values of the input parameters into a single query string, you have to set up the package variables that the query needs.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="adabc-125">Per configurare le variabili del pacchetto</span><span class="sxs-lookup"><span data-stu-id="adabc-125">To set up package variables</span></span>  
  
-   <span data-ttu-id="adabc-126">Nella finestra [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Variabili **in** creare una variabile con un tipo di dati stringa per memorizzare la stringa di query restituita dall'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="adabc-126">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create a variable with a string data type to hold the query string returned by the Execute SQL Task.</span></span>  
  
     <span data-ttu-id="adabc-127">In questo esempio viene utilizzato il nome di variabile SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="adabc-127">This example uses the variable name, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="adabc-128">Dopo avere creato la variabile del pacchetto, è possibile utilizzare un'attività Script o un'attività Esegui SQL per concatenare i valori dei parametri di input.</span><span class="sxs-lookup"><span data-stu-id="adabc-128">With the package variable created, you can use either a Script task or Execute SQL task to concatenate the values of the input parameters.</span></span> <span data-ttu-id="adabc-129">Nelle due procedure seguenti viene descritto come configurare tali componenti.</span><span class="sxs-lookup"><span data-stu-id="adabc-129">The following two procedures describe how to configure these components.</span></span>  
  
#### <a name="to-use-a-script-task-to-concatenate-the-query-string"></a><span data-ttu-id="adabc-130">Per utilizzare un'attività Script per concatenare la stringa di query</span><span class="sxs-lookup"><span data-stu-id="adabc-130">To use a Script task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="adabc-131">Nella scheda **Flusso di controllo** aggiungere un'attività Script al pacchetto dopo il contenitore Ciclo For e connettere tale contenitore all'attività.</span><span class="sxs-lookup"><span data-stu-id="adabc-131">On the **Control Flow** tab, add a Script task to the package after the For Loop container and connect the For Loop container to the task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="adabc-132">In questa procedura si presuppone che il pacchetto esegua un caricamento incrementale da una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="adabc-132">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="adabc-133">Se il pacchetto esegue il caricamento da più tabelle e ha un pacchetto padre con più pacchetti figlio, questa attività viene aggiunta come primo componente a ciascun pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="adabc-133">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="adabc-134">Per altre informazioni, vedere [Eseguire un caricamento incrementale di più tabelle](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="adabc-134">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="adabc-135">Nella pagina **Script**in **Editor attività Script** selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="adabc-135">In the **Script Task Editor**, on the **Script** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="adabc-136">Per **ReadOnlyVariables**selezionare **User::DataReady**, **User::ExtractStartTime**e **User::ExtractEndTime** .</span><span class="sxs-lookup"><span data-stu-id="adabc-136">For **ReadOnlyVariables**, select **User::DataReady**, **User::ExtractStartTime**, and **User::ExtractEndTime** from the.</span></span>  
  
    2.  <span data-ttu-id="adabc-137">Per **ReadWriteVariables**selezionare User::SqlDataQuery nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="adabc-137">For **ReadWriteVariables**, select User::SqlDataQuery from the list.</span></span>  
  
3.  <span data-ttu-id="adabc-138">Nella pagina **Script**in **Editor attività Script** fare clic su **Modifica script** per aprire l'ambiente di sviluppo dello script.</span><span class="sxs-lookup"><span data-stu-id="adabc-138">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
4.  <span data-ttu-id="adabc-139">Nella routine Main immettere uno dei segmenti di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="adabc-139">In the Main procedure, enter one of the following code segments:</span></span>  
  
    -   <span data-ttu-id="adabc-140">Se si utilizza il linguaggio di programmazione C#, immettere le righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="adabc-140">If you are programming in C#, enter the following lines of code:</span></span>  
  
        ```  
        int dataReady;  
        System.DateTime extractStartTime;  
        System.DateTime extractEndTime;  
        string sqlDataQuery;  
  
        dataReady = (int)Dts.Variables["DataReady"].Value;  
        extractStartTime = (System.DateTime)Dts.Variables["ExtractStartTime"].Value;  
        extractEndTime = (System.DateTime)Dts.Variables["ExtractEndTime"].Value;  
  
        if (dataReady == 2)  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) + "', '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
        else  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" + ", '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
  
        Dts.Variables["SqlDataQuery"].Value = sqlDataQuery;  
        ```  
  
         <span data-ttu-id="adabc-141">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="adabc-141">\- or -</span></span>  
  
    -   <span data-ttu-id="adabc-142">Se si usa il linguaggio di programmazione [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], immettere le righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="adabc-142">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following lines of code:</span></span>  
  
        ```  
        Dim dataReady As Integer  
        Dim extractStartTime As Date  
        Dim extractEndTime As Date  
        Dim sqlDataQuery As String  
  
        dataReady = CType(Dts.Variables("DataReady").Value, Integer)  
        extractStartTime = CType(Dts.Variables("ExtractStartTime").Value, Date)  
        extractEndTime = CType(Dts.Variables("ExtractEndTime").Value, Date)  
  
        If dataReady = 2 Then  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) & _  
              "', '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        Else  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" & _  
              ", '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        End If  
  
        Dts.Variables("SqlDataQuery").Value = sqlDataQuery  
  
        ```  
  
5.  <span data-ttu-id="adabc-143">Lasciare la linea di codice predefinita, che restituisce `DtsExecResult.Success` dall'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="adabc-143">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
6.  <span data-ttu-id="adabc-144">Chiudere l'ambiente di sviluppo dello script ed **Editor attività Script**.</span><span class="sxs-lookup"><span data-stu-id="adabc-144">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-use-an-execute-sql-task-to-concatenate-the-query-string"></a><span data-ttu-id="adabc-145">Per utilizzare un'attività Esegui SQL per concatenare la stringa di query</span><span class="sxs-lookup"><span data-stu-id="adabc-145">To use an Execute SQL task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="adabc-146">Nella scheda **Flusso di controllo** aggiungere un'attività Esegui SQL al pacchetto dopo il contenitore Ciclo For e connettere tale contenitore all'attività.</span><span class="sxs-lookup"><span data-stu-id="adabc-146">On the **Control Flow** tab, add an Execute SQL task to the package after the For Loop container and connect the For Loop container to this task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="adabc-147">In questa procedura si presuppone che il pacchetto esegua un caricamento incrementale da una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="adabc-147">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="adabc-148">Se il pacchetto esegue il caricamento da più tabelle e ha un pacchetto padre con più pacchetti figlio, questa attività viene aggiunta come primo componente a ciascun pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="adabc-148">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="adabc-149">Per altre informazioni, vedere [Eseguire un caricamento incrementale di più tabelle](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="adabc-149">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="adabc-150">Nella pagina **Generale**in **Editor attività Esegui SQL** selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="adabc-150">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="adabc-151">Per **ResultSet**, selezionare **Riga singola**.</span><span class="sxs-lookup"><span data-stu-id="adabc-151">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="adabc-152">Configurare una connessione valida al database di origine.</span><span class="sxs-lookup"><span data-stu-id="adabc-152">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="adabc-153">Per **SQLSourceType**, selezionare **Input diretto**.</span><span class="sxs-lookup"><span data-stu-id="adabc-153">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="adabc-154">Per **SQLStatement**immettere l'istruzione SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="adabc-154">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @ExtractStartTime datetime,  
        @ExtractEndTime datetime,   
        @DataReady int  
  
        select @DataReady = ?,   
        @ExtractStartTime = ?,   
        @ExtractEndTime = ?  
  
        if @DataReady = 2  
        select N'select * from CDCSample.uf_Customer'  
        + N'('''+ convert(nvarchar(30),@ExtractStartTime,120)  
        + ''', '''  
        + convert(nvarchar(30),@ExtractEndTime,120) + ''') '   
        as SqlDataQuery  
        else  
        select N'select * from CDCSample.uf_Customer'  
        + N'(null, '''  
        + convert(nvarchar(30),@ExtractEndTime,120)  
        + ''') '  
        as SqlDataQuery  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="adabc-155">In questo esempio la clausola `else` genera una query per il caricamento iniziale dei dati delle modifiche passando un valore Null per la data e l'ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="adabc-155">The `else` clause in this sample generates a query for the initial load of change data by passing a null value for the starting date and time.</span></span> <span data-ttu-id="adabc-156">Questo esempio non si applica a uno scenario in cui le modifiche apportate prima dell'attivazione di Change Data Capture devono essere caricate anche nel data warehouse.</span><span class="sxs-lookup"><span data-stu-id="adabc-156">This sample does not address the scenario in which changes that were made before change data capture was enabled also have to be uploaded to the data warehouse.</span></span>  
  
3.  <span data-ttu-id="adabc-157">Nella pagina **Mapping parametri** di **Editor attività Esegui SQL**creare i mapping seguenti:</span><span class="sxs-lookup"><span data-stu-id="adabc-157">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, do the following mapping:</span></span>  
  
    1.  <span data-ttu-id="adabc-158">Eseguire il mapping tra la variabile DataReady e il parametro 0.</span><span class="sxs-lookup"><span data-stu-id="adabc-158">Map the DataReady variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="adabc-159">Eseguire il mapping tra la variabile ExtractStartTime e il parametro 1.</span><span class="sxs-lookup"><span data-stu-id="adabc-159">Map the ExtractStartTime variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="adabc-160">Eseguire il mapping tra la variabile ExtractEndTime e il parametro 2.</span><span class="sxs-lookup"><span data-stu-id="adabc-160">Map the ExtractEndTime variable to parameter 2.</span></span>  
  
4.  <span data-ttu-id="adabc-161">Nella pagina **Set di risultati** di **Editor attività Esegui SQL**eseguire il mapping tra il nome del risultato e la variabile SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="adabc-161">On the **Result Set** page of the **Execute SQL Task Editor**, map the Result Name to the SqlDataQuery variable.</span></span>  
  
     <span data-ttu-id="adabc-162">Il nome del risultato è il nome della singola colonna restituita, ovvero SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="adabc-162">The Result Name is the name of the single column that is returned, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="adabc-163">Nelle procedure precedenti è stata configurata un'attività per la preparazione di una stringa di query con valori stringa specificati a livello di codice per i parametri di input.</span><span class="sxs-lookup"><span data-stu-id="adabc-163">The previous procedures configure a task that prepares a query string with hard-coded string values for the input parameters.</span></span> <span data-ttu-id="adabc-164">Il codice seguente rappresenta un esempio di tale stringa di query:</span><span class="sxs-lookup"><span data-stu-id="adabc-164">The following code is an example of such a query string:</span></span>  
  
 `select * from CDCSample. uf_Customer('2007-06-11 14:21:58', '2007-06-12 14:21:58')`  
  
## <a name="adding-a-data-flow-task"></a><span data-ttu-id="adabc-165">Aggiunta di un'attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="adabc-165">Adding a Data Flow Task</span></span>  
 <span data-ttu-id="adabc-166">L'ultimo passaggio nella progettazione del flusso di controllo per il pacchetto consiste nell'aggiungere un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="adabc-166">The last step in designing the control flow for the package is to add a Data Flow task.</span></span>  
  
#### <a name="to-add-a-data-flow-task-and-complete-the-control-flow"></a><span data-ttu-id="adabc-167">Per aggiungere un'attività Flusso di dati e completare il flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="adabc-167">To add a Data Flow task and complete the control flow</span></span>  
  
-   <span data-ttu-id="adabc-168">Nella scheda **Flusso di controllo** aggiungere un'attività Flusso di dati e connettere l'attività che ha concatenato la stringa di query.</span><span class="sxs-lookup"><span data-stu-id="adabc-168">On the **Control Flow** tab, add a Data Flow task and connect the task that concatenated the query string.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="adabc-169">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="adabc-169">Next Step</span></span>  
 <span data-ttu-id="adabc-170">Dopo avere preparato la stringa di query e avere configurato l'attività Flusso di dati, il passaggio successivo consiste nel creare la funzione valutata a livello di tabella per il recupero dei dati delle modifiche dal database.</span><span class="sxs-lookup"><span data-stu-id="adabc-170">After you prepare the query string and configure the Data Flow task, the next step is create the table-valued function that will retrieve the change data from the database.</span></span>  
  
 <span data-ttu-id="adabc-171">**Argomento successivo:** [Creare la funzione per il recupero dei dati delle modifiche](create-the-function-to-retrieve-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="adabc-171">**Next topic:** [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md)</span></span>  
  
  
