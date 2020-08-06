---
title: Determinare se i dati delle modifiche sono pronti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],determining readiness
ms.assetid: 04935f35-96cc-4d70-a250-0fd326f8daff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e672440938e366e53ba150f65d7bcd6aed8a58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724039"
---
# <a name="determine-whether-the-change-data-is-ready"></a><span data-ttu-id="40f25-102">Come determinare se i dati delle modifiche sono pronti</span><span class="sxs-lookup"><span data-stu-id="40f25-102">Determine Whether the Change Data Is Ready</span></span>
  <span data-ttu-id="40f25-103">Nel flusso di controllo di un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che esegue un caricamento incrementale dei dati delle modifiche, la seconda attività consiste nel verificare che i dati delle modifiche per l'intervallo selezionato siano pronti.</span><span class="sxs-lookup"><span data-stu-id="40f25-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the second task is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="40f25-104">Questo passaggio è necessario in quanto il processo di acquisizione asincrono potrebbe non avere ancora elaborato tutte le modifiche fino all'endpoint selezionato.</span><span class="sxs-lookup"><span data-stu-id="40f25-104">This step is necessary because the asynchronous capture process might not yet have processed all the changes up to the selected endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40f25-105">La prima attività per il flusso di controllo consiste nel calcolare gli endpoint dell'intervallo di modifiche.</span><span class="sxs-lookup"><span data-stu-id="40f25-105">The first task for the control flow is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="40f25-106">Per altre informazioni su questa attività, vedere [Definizione di un intervallo dei dati delle modifiche](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="40f25-106">For more information about this task, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span> <span data-ttu-id="40f25-107">Per una descrizione del processo complessivo di progettazione del flusso di controllo, vedere [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="40f25-107">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="understanding-the-components-of-the-solution"></a><span data-ttu-id="40f25-108">Informazioni sui componenti della soluzione</span><span class="sxs-lookup"><span data-stu-id="40f25-108">Understanding the Components of the Solution</span></span>  
 <span data-ttu-id="40f25-109">La soluzione descritta in questo argomento usa 4 componenti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="40f25-109">The solution described in this topic uses 4 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components:</span></span>  
  
-   <span data-ttu-id="40f25-110">Un contenitore Ciclo For che valuta ripetutamente l'output di un'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="40f25-110">A For Loop container that repeatedly evaluates the output of an Execute SQL Task.</span></span>  
  
-   <span data-ttu-id="40f25-111">Un'attività Esegui SQL che esegue una query su tabelle speciali gestite dal processo Change Data Capture e che utilizza quindi tali informazioni per determinare se i dati sono pronti.</span><span class="sxs-lookup"><span data-stu-id="40f25-111">An Execute SQL task that queries special tables that the change data capture process maintains and then uses this information to determine whether data is ready.</span></span>  
  
-   <span data-ttu-id="40f25-112">Un componente che implementa un ritardo nell'elaborazione quando i dati non sono pronti.</span><span class="sxs-lookup"><span data-stu-id="40f25-112">A component that implements a delay in processing when the data is not ready.</span></span> <span data-ttu-id="40f25-113">Può trattarsi di un'attività Script o di un'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="40f25-113">This can be either a Script task or an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="40f25-114">Facoltativamente, un componente che segnala un errore o un timeout quando l'attività Esegui SQL restituisce un valore indicante un errore o una condizione di timeout.</span><span class="sxs-lookup"><span data-stu-id="40f25-114">Optionally, a component that reports an error or a timeout when the Execute SQL task returns a value that indicates an error or a timeout condition.</span></span>  
  
 <span data-ttu-id="40f25-115">Tali componenti impostano o leggono i valori di numerose variabili del pacchetto per controllare il flusso di esecuzione all'interno del ciclo e successivamente nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="40f25-115">These components set or read the values of several package variables to control the flow of execution inside the loop and later in the package.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="40f25-116">Per configurare le variabili del pacchetto</span><span class="sxs-lookup"><span data-stu-id="40f25-116">To set up package variables</span></span>  
  
1.  <span data-ttu-id="40f25-117">Nella finestra [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Variabili **di** creare le variabili seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f25-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="40f25-118">Creare una variabile con un tipo di dati integer per memorizzare il valore di stato restituito dall'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="40f25-118">Create a variable with an integer data type to hold the status value returned by the Execute SQL task.</span></span>  
  
         <span data-ttu-id="40f25-119">In questo esempio viene utilizzato il nome di variabile DataReady con un valore iniziale pari a 0.</span><span class="sxs-lookup"><span data-stu-id="40f25-119">This example uses the variable name, DataReady, with an initial value of 0.</span></span>  
  
    2.  <span data-ttu-id="40f25-120">Creare una variabile per memorizzare il periodo di tempo per il ritardo quando i dati non sono pronti.</span><span class="sxs-lookup"><span data-stu-id="40f25-120">Create a variable to hold the period of time to delay when data is not ready.</span></span> <span data-ttu-id="40f25-121">Se si prevede di utilizzare un'attività Script per implementare il ritardo, la variabile deve essere associata a un tipo di dati integer.</span><span class="sxs-lookup"><span data-stu-id="40f25-121">If you plan to use a Script task to implement the delay, the variable should have an integer data type integer.</span></span> <span data-ttu-id="40f25-122">Se si prevede di utilizzare un'attività Esegui SQL con un'istruzione WAITFOR, la variabile deve avere un tipo di dati stringa per accettare valori quali "00.00.10".</span><span class="sxs-lookup"><span data-stu-id="40f25-122">If you plan to use an Execute SQL task with a WAITFOR statement, the variable should have a string data type to accept values such as "00:00:10".</span></span>  
  
         <span data-ttu-id="40f25-123">In questo esempio viene utilizzato il nome di variabile DelaySeconds con un valore iniziale pari a 10.</span><span class="sxs-lookup"><span data-stu-id="40f25-123">This example uses the variable name, DelaySeconds, with an initial value of 10.</span></span>  
  
    3.  <span data-ttu-id="40f25-124">Creare una variabile con un tipo di dati integer per memorizzare l'iterazione corrente del ciclo.</span><span class="sxs-lookup"><span data-stu-id="40f25-124">Create a variable with an integer data type to hold the current iteration of the loop.</span></span>  
  
         <span data-ttu-id="40f25-125">In questo esempio viene utilizzato il nome di variabile TimeoutCount con un valore iniziale pari a 0.</span><span class="sxs-lookup"><span data-stu-id="40f25-125">This example uses the variable name, TimeoutCount, with an initial value of 0.</span></span>  
  
    4.  <span data-ttu-id="40f25-126">Creare una variabile con un tipo di dati integer per specificare il numero di volte in cui il ciclo deve eseguire il test dei dati prima di segnalare una condizione di timeout.</span><span class="sxs-lookup"><span data-stu-id="40f25-126">Create a variable with an integer data type to specify the number of times that the loop should test for data before reporting a timeout condition.</span></span>  
  
         <span data-ttu-id="40f25-127">In questo esempio viene utilizzato il nome di variabile TimeoutCeiling con un valore iniziale pari a 20.</span><span class="sxs-lookup"><span data-stu-id="40f25-127">This example uses the variable name, TimeoutCeiling, with an initial value of 20.</span></span>  
  
    5.  <span data-ttu-id="40f25-128">Creare una variabile con un tipo di dati integer che è possibile utilizzare per indicare il primo caricamento dei dati delle modifiche (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="40f25-128">(Optional) Create a variable with an integer data type that you can use to indicate the first load of change data.</span></span>  
  
         <span data-ttu-id="40f25-129">In questo esempio viene utilizzato il nome di variabile IntervalID e viene verificata solo l'eventuale presenza di un valore pari a 0 per indicare il caricamento iniziale.</span><span class="sxs-lookup"><span data-stu-id="40f25-129">This example uses the variable name, IntervalID, and checks only for a value of 0 to indicate the initial load.</span></span>  
  
## <a name="configuring-a-for-loop-container"></a><span data-ttu-id="40f25-130">Configurazione di un contenitore Ciclo For</span><span class="sxs-lookup"><span data-stu-id="40f25-130">Configuring a For Loop Container</span></span>  
 <span data-ttu-id="40f25-131">Dopo avere impostato le variabili, il contenitore Ciclo For rappresenta il primo componente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="40f25-131">With the variables set, the For Loop container is the first component to be added.</span></span>  
  
#### <a name="to-configure-a-for-loop-container-to-wait-until-change-data-is-ready"></a><span data-ttu-id="40f25-132">Per configurare un contenitore Ciclo For per attendere che i dati delle modifiche siano pronti</span><span class="sxs-lookup"><span data-stu-id="40f25-132">To configure a For Loop container to wait until change data is ready</span></span>  
  
1.  <span data-ttu-id="40f25-133">Nella scheda **Flusso di controllo** di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] aggiungere un contenitore Ciclo For al flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="40f25-133">On the **Control Flow** tab of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a For Loop container to the control flow.</span></span>  
  
2.  <span data-ttu-id="40f25-134">Connettere l'attività Esegui SQL per il calcolo degli endpoint dell'intervallo al contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="40f25-134">Connect the Execute SQL Task that calculates the endpoints of the interval to the For Loop container.</span></span>  
  
3.  <span data-ttu-id="40f25-135">In **Editor ciclo For**selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f25-135">In the **For Loop Editor**, select the following options:</span></span>  
  
    1.  <span data-ttu-id="40f25-136">Per **InitExpression**, immettere `@DataReady = 0`.</span><span class="sxs-lookup"><span data-stu-id="40f25-136">For **InitExpression**, enter `@DataReady = 0`.</span></span>  
  
         <span data-ttu-id="40f25-137">Questa espressione imposta il valore iniziale della variabile del ciclo.</span><span class="sxs-lookup"><span data-stu-id="40f25-137">This expression sets the initial value of the loop variable.</span></span>  
  
    2.  <span data-ttu-id="40f25-138">Per **EvalExpression**, immettere `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="40f25-138">For **EvalExpression**m, enter `@DataReady == 0`.</span></span>  
  
         <span data-ttu-id="40f25-139">Quando questa espressione restituisce **False**, l'esecuzione passa all'esterno del ciclo e viene avviato il caricamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="40f25-139">When this expression evaluates to **False**, execution passes out of the loop and the incremental load starts.</span></span>  
  
## <a name="configuring-the-execute-sql-task-that-queries-for-change-data"></a><span data-ttu-id="40f25-140">Configurazione dell'attività Esegui SQL per l'esecuzione di una query per i dati delle modifiche</span><span class="sxs-lookup"><span data-stu-id="40f25-140">Configuring the Execute SQL Task That Queries for Change Data</span></span>  
 <span data-ttu-id="40f25-141">È necessario aggiungere un'attività Esegui SQL all'interno del contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="40f25-141">Inside the For Loop container, you add an Execute SQL task.</span></span> <span data-ttu-id="40f25-142">Questa attività esegue una query sulle tabelle gestite dal processo Change Data Capture nel database.</span><span class="sxs-lookup"><span data-stu-id="40f25-142">This task queries the tables that the change data capture process maintains in the database.</span></span> <span data-ttu-id="40f25-143">Il risultato della query è un valore di stato che indica se i dati delle modifiche sono pronti.</span><span class="sxs-lookup"><span data-stu-id="40f25-143">The result of this query is a status value that indicates whether the change data is ready.</span></span>  
  
 <span data-ttu-id="40f25-144">Nella tabella seguente la prima colonna indica i valori restituiti dall'attività Esegui SQL tramite la query Transact-SQL di esempio.</span><span class="sxs-lookup"><span data-stu-id="40f25-144">In the following table, the first column shows the values returned from the Execute SQL task by the sample Transact-SQL query.</span></span> <span data-ttu-id="40f25-145">La seconda colonna indica il modo in cui gli altri componenti rispondono a tali valori.</span><span class="sxs-lookup"><span data-stu-id="40f25-145">The second column shows how the other components respond to these values.</span></span>  
  
|<span data-ttu-id="40f25-146">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="40f25-146">Return Value</span></span>|<span data-ttu-id="40f25-147">Significato</span><span class="sxs-lookup"><span data-stu-id="40f25-147">Meaning</span></span>|<span data-ttu-id="40f25-148">Risposta</span><span class="sxs-lookup"><span data-stu-id="40f25-148">Response</span></span>|  
|------------------|-------------|--------------|  
|<span data-ttu-id="40f25-149">0</span><span class="sxs-lookup"><span data-stu-id="40f25-149">0</span></span>|<span data-ttu-id="40f25-150">Indica che i dati delle modifiche non sono pronti.</span><span class="sxs-lookup"><span data-stu-id="40f25-150">Indicates that the change data is not ready.</span></span><br /><br /> <span data-ttu-id="40f25-151">Non è presente alcun record di Change Data Capture successivo al punto finale dell'intervallo selezionato.</span><span class="sxs-lookup"><span data-stu-id="40f25-151">There are no change data capture records later than the ending point of the selected interval.</span></span>|<span data-ttu-id="40f25-152">L'esecuzione continua con il componente che implementa un ritardo.</span><span class="sxs-lookup"><span data-stu-id="40f25-152">Execution continues with the component that implements a delay.</span></span> <span data-ttu-id="40f25-153">Il controllo viene restituito al contenitore Ciclo For, che continua a verificare l'attività Esegui SQL a condizione che il valore restituito sia 0.</span><span class="sxs-lookup"><span data-stu-id="40f25-153">Then control returns to the For Loop container, which continues to check the Execute SQL task as long as the value returned is 0.</span></span>|  
|<span data-ttu-id="40f25-154">1</span><span class="sxs-lookup"><span data-stu-id="40f25-154">1</span></span>|<span data-ttu-id="40f25-155">Potrebbe indicare che i dati delle modifiche non sono stati acquisiti per l'intervallo completo o che sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="40f25-155">Might indicate that the change data has not been captured for the complete interval, or that it has been deleted.</span></span> <span data-ttu-id="40f25-156">Questo caso viene considerato una condizione di errore.</span><span class="sxs-lookup"><span data-stu-id="40f25-156">This is treated as an error condition.</span></span><br /><br /> <span data-ttu-id="40f25-157">Non è presente alcun record di Change Data Capture precedente al punto iniziale dell'intervallo selezionato.</span><span class="sxs-lookup"><span data-stu-id="40f25-157">There are no change data capture records earlier than the starting point of the selected interval</span></span>|<span data-ttu-id="40f25-158">L'esecuzione continua con il componente facoltativo che registra l'errore.</span><span class="sxs-lookup"><span data-stu-id="40f25-158">Execution continues with the optional component that logs the error.</span></span>|  
|<span data-ttu-id="40f25-159">2</span><span class="sxs-lookup"><span data-stu-id="40f25-159">2</span></span>|<span data-ttu-id="40f25-160">Indica che i dati sono pronti.</span><span class="sxs-lookup"><span data-stu-id="40f25-160">Indicates that data is ready.</span></span><br /><br /> <span data-ttu-id="40f25-161">Non è presente alcun record di Change Data Capture che sia precedente al punto iniziale e successivo al punto finale dell'intervallo selezionato.</span><span class="sxs-lookup"><span data-stu-id="40f25-161">There are change data capture records that are both earlier than the starting point and later than the ending point of the selected interval.</span></span>|<span data-ttu-id="40f25-162">L'esecuzione passa all'esterno del contenitore Ciclo For e viene avviato il caricamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="40f25-162">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="40f25-163">3</span><span class="sxs-lookup"><span data-stu-id="40f25-163">3</span></span>|<span data-ttu-id="40f25-164">Indica il caricamento iniziale di tutti i dati delle modifiche disponibili.</span><span class="sxs-lookup"><span data-stu-id="40f25-164">Indicates the initial load of all available change data.</span></span><br /><br /> <span data-ttu-id="40f25-165">La logica condizionale ottiene questo valore da una variabile del pacchetto speciale utilizzata solo a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="40f25-165">The conditional logic obtains this value from a special package variable that is used only for this purpose.</span></span>|<span data-ttu-id="40f25-166">L'esecuzione passa all'esterno del contenitore Ciclo For e viene avviato il caricamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="40f25-166">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="40f25-167">5</span><span class="sxs-lookup"><span data-stu-id="40f25-167">5</span></span>|<span data-ttu-id="40f25-168">Indica che è stato raggiunto il valore di TimeoutCeiling.</span><span class="sxs-lookup"><span data-stu-id="40f25-168">Indicates that the TimeoutCeiling has been reached.</span></span><br /><br /> <span data-ttu-id="40f25-169">Il ciclo ha testato i dati per il numero specificato di volte e i dati non sono ancora disponibili.</span><span class="sxs-lookup"><span data-stu-id="40f25-169">The loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="40f25-170">Senza questo test o uno simile, l'esecuzione del pacchetto potrebbe continuare per un tempo illimitato.</span><span class="sxs-lookup"><span data-stu-id="40f25-170">Without this test or a similar test, the package might run indefinitely.</span></span>|<span data-ttu-id="40f25-171">L'esecuzione prosegue con il componente facoltativo che registra il timeout.</span><span class="sxs-lookup"><span data-stu-id="40f25-171">Execution continues with the optional component that logs the timeout.</span></span>|  
  
#### <a name="to-configure-an-execute-sql-task-to-query-whether-change-data-is-ready"></a><span data-ttu-id="40f25-172">Per configurare un'attività Esegui SQL per l'esecuzione di una query per verificare se i dati sono pronti</span><span class="sxs-lookup"><span data-stu-id="40f25-172">To configure an Execute SQL task to query whether change data is ready</span></span>  
  
1.  <span data-ttu-id="40f25-173">Aggiungere un'attività Esegui SQL all'interno del contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="40f25-173">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="40f25-174">Nella pagina **Generale**in **Editor attività Esegui SQL** selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f25-174">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="40f25-175">Per **ResultSet**, selezionare **Riga singola**.</span><span class="sxs-lookup"><span data-stu-id="40f25-175">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="40f25-176">Configurare una connessione valida al database di origine.</span><span class="sxs-lookup"><span data-stu-id="40f25-176">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="40f25-177">Per **SQLSourceType**, selezionare **Input diretto**.</span><span class="sxs-lookup"><span data-stu-id="40f25-177">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="40f25-178">Per **SQLStatement**immettere l'istruzione SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="40f25-178">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @DataReady int, @TimeoutCount int  
  
        if not exists (select tran_end_time from cdc.lsn_time_mapping  
                where tran_end_time > ?  )  
            select @DataReady = 0  
        else  
            if ? = 0  
                select @DataReady = 3   
        else  
            if not exists (select tran_end_time from cdc.lsn_time_mapping  
                    where tran_end_time <= ? )  
                select @DataReady = 1   
        else  
            select @DataReady = 2  
  
        select @TimeoutCount = ?  
        if (@DataReady = 0)  
            select @TimeoutCount = @TimeoutCount + 1  
        else  
            select @TimeoutCount = 0  
  
        if (@TimeoutCount > ?)  
            select @DataReady = 5  
  
        select @DataReady as DataReady, @TimeoutCount as TimeoutCount  
  
        ```  
  
3.  <span data-ttu-id="40f25-179">Nella pagina **Mapping parametri** di **Editor attività Esegui SQL**creare i mapping seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f25-179">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, make the following mappings:</span></span>  
  
    1.  <span data-ttu-id="40f25-180">Eseguire il mapping tra la variabile ExtractEndTime e il parametro 0.</span><span class="sxs-lookup"><span data-stu-id="40f25-180">Map the ExtractEndTime variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="40f25-181">Mapping tra la variabile IntervalID e il parametro 1.</span><span class="sxs-lookup"><span data-stu-id="40f25-181">Map the IntervalID variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="40f25-182">Eseguire il mapping tra la variabile ExtractStartTime e il parametro 2.</span><span class="sxs-lookup"><span data-stu-id="40f25-182">Map the ExtractStartTime variable to parameter 2.</span></span>  
  
    4.  <span data-ttu-id="40f25-183">Mapping tra la variabile TimeoutCount e il parametro 3.</span><span class="sxs-lookup"><span data-stu-id="40f25-183">Map the TimeoutCount variable to parameter 3.</span></span>  
  
    5.  <span data-ttu-id="40f25-184">Mapping tra la variabile TimeoutCeiling e il parametro 4.</span><span class="sxs-lookup"><span data-stu-id="40f25-184">Map the TimeoutCeiling variable to parameter 4.</span></span>  
  
4.  <span data-ttu-id="40f25-185">Nella pagina **Set dei risultati** di **Editor attività Esegui SQL**eseguire il mapping tra il risultato di DataReady e la variabile DataReady e tra il risultato di TimeoutCount e la variabile TimeoutCount.</span><span class="sxs-lookup"><span data-stu-id="40f25-185">On the **Result Set** page of the **Execute SQL Task Editor**, map the DataReady result to the DataReady variable, and the TimeoutCount result to the TimeoutCount variable.</span></span>  
  
## <a name="waiting-until-the-change-data-is-ready"></a><span data-ttu-id="40f25-186">Attesa che i dati delle modifiche siano pronti</span><span class="sxs-lookup"><span data-stu-id="40f25-186">Waiting Until the Change Data Is Ready</span></span>  
 <span data-ttu-id="40f25-187">È possibile utilizzare uno dei numerosi metodi per implementare un ritardo quando i dati delle modifiche non sono pronti.</span><span class="sxs-lookup"><span data-stu-id="40f25-187">You can use one of several methods to implement a delay when the change data is not ready.</span></span> <span data-ttu-id="40f25-188">Nelle due procedure seguenti viene illustrato come utilizzare un'attività Script o un'attività Esegui SQL per implementare il ritardo.</span><span class="sxs-lookup"><span data-stu-id="40f25-188">The following two procedures illustrate how to use a Script task or an Execute SQL task to implement the delay.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40f25-189">Uno script precompilato è soggetto a un overhead minore rispetto a un'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="40f25-189">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-a-script-task"></a><span data-ttu-id="40f25-190">Per implementare un ritardo tramite un'attività Script</span><span class="sxs-lookup"><span data-stu-id="40f25-190">To implement a delay by using a Script task</span></span>  
  
1.  <span data-ttu-id="40f25-191">Aggiungere un'attività Script all'interno del contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="40f25-191">Inside the For Loop container, add a Script task.</span></span>  
  
2.  <span data-ttu-id="40f25-192">Connettere l'attività Esegui SQL che esegue una query per determinare se i dati delle modifiche sono pronti alla nuova attività Script.</span><span class="sxs-lookup"><span data-stu-id="40f25-192">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
3.  <span data-ttu-id="40f25-193">Per il vincolo di precedenza che connette l'attività Esegui SQL all'attività Script, aprire **Editor vincoli di precedenza** e selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f25-193">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="40f25-194">Per **Operazione valutazione**, selezionare **Espressione e vincolo**.</span><span class="sxs-lookup"><span data-stu-id="40f25-194">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="40f25-195">Per **Valore**, selezionare **Esito positivo**.</span><span class="sxs-lookup"><span data-stu-id="40f25-195">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="40f25-196">Il valore **Esito positivo** del vincolo si riferisce al risultato dell'attività precedente,</span><span class="sxs-lookup"><span data-stu-id="40f25-196">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="40f25-197">in questo caso l'esito positivo dell'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="40f25-197">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="40f25-198">Per **Espressione**, immettere `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span><span class="sxs-lookup"><span data-stu-id="40f25-198">For **Expression**, enter `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span></span>  
  
    4.  <span data-ttu-id="40f25-199">Selezionare **AND logico. Se questa opzione non è già selezionata, tutti i vincoli devono restituire il valore True**.</span><span class="sxs-lookup"><span data-stu-id="40f25-199">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
4.  <span data-ttu-id="40f25-200">Nella pagina **Script**di **Editor attività Script** per **ReadOnlyVariables**selezionare dall'elenco la variabile di tipo integer **User::DelaySeconds** .</span><span class="sxs-lookup"><span data-stu-id="40f25-200">In the **Script Task Editor**, on the **Script** page, for **ReadOnlyVariables**, select the **User::DelaySeconds** integer variable from the list.</span></span>  
  
5.  <span data-ttu-id="40f25-201">Nella pagina **Script**in **Editor attività Script** fare clic su **Modifica script** per aprire l'ambiente di sviluppo dello script.</span><span class="sxs-lookup"><span data-stu-id="40f25-201">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="40f25-202">Nella routine Main immettere una delle righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f25-202">In the Main procedure, enter one of the following lines of code:</span></span>  
  
    -   <span data-ttu-id="40f25-203">Se si utilizza il linguaggio di programmazione C#, immettere la riga di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="40f25-203">If you are programming in C#, enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep((int)Dts.Variables["DelaySeconds"].Value * 1000);  
        ```  
  
         <span data-ttu-id="40f25-204">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="40f25-204">\- or -</span></span>  
  
    -   <span data-ttu-id="40f25-205">Se si utilizza il linguaggio di programmazione [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], immettere la riga di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="40f25-205">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep(Ctype(Dts.Variables("DelaySeconds").Value, Integer) * 1000)  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="40f25-206">Come argomento del metodo `Thread.Sleep` è previsto un argomento specificato in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="40f25-206">The `Thread.Sleep` method expects an argument that is specified in milliseconds.</span></span>  
  
7.  <span data-ttu-id="40f25-207">Lasciare la linea di codice predefinita, che restituisce `DtsExecResult.Success` dall'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="40f25-207">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
8.  <span data-ttu-id="40f25-208">Chiudere l'ambiente di sviluppo dello script ed **Editor attività Script**.</span><span class="sxs-lookup"><span data-stu-id="40f25-208">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-an-execute-sql-task"></a><span data-ttu-id="40f25-209">Per implementare un ritardo tramite un'attività Esegui SQL</span><span class="sxs-lookup"><span data-stu-id="40f25-209">To implement a delay by using an Execute SQL task</span></span>  
  
1.  <span data-ttu-id="40f25-210">Aggiungere un'attività Esegui SQL all'interno del contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="40f25-210">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="40f25-211">Connettere l'attività Esegui SQL che esegue una query per determinare se i dati delle modifiche sono pronti alla nuova attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="40f25-211">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Execute SQL task.</span></span>  
  
3.  <span data-ttu-id="40f25-212">Per il vincolo di precedenza che connette le due attività Esegui SQL, aprire **Editor vincoli di precedenza** e selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f25-212">For the precedence constraint that connects the two Execute SQL tasks, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="40f25-213">Per **Operazione valutazione**, selezionare **Espressione e vincolo**.</span><span class="sxs-lookup"><span data-stu-id="40f25-213">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="40f25-214">Per **Valore**, selezionare **Esito positivo**.</span><span class="sxs-lookup"><span data-stu-id="40f25-214">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="40f25-215">Il valore **Esito positivo** del vincolo si riferisce al risultato dell'attività Esegui SQL precedente.</span><span class="sxs-lookup"><span data-stu-id="40f25-215">The constraint value of **Success** refers to the success of the previous Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="40f25-216">Per **Espressione**, immettere `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="40f25-216">For **Expression**, enter `@DataReady == 0`.</span></span>  
  
    4.  <span data-ttu-id="40f25-217">Selezionare **AND logico. Se questa opzione non è già selezionata, tutti i vincoli devono restituire il valore True**.</span><span class="sxs-lookup"><span data-stu-id="40f25-217">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="40f25-218">Questa opzione richiede che entrambe le condizioni, il vincolo e l'espressione, siano True.</span><span class="sxs-lookup"><span data-stu-id="40f25-218">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
4.  <span data-ttu-id="40f25-219">Nella pagina **Generale**in **Editor attività Esegui SQL** selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f25-219">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="40f25-220">Per **ResultSet**, selezionare **Riga singola**.</span><span class="sxs-lookup"><span data-stu-id="40f25-220">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="40f25-221">Configurare una connessione valida al database di origine.</span><span class="sxs-lookup"><span data-stu-id="40f25-221">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="40f25-222">Per **SQLSourceType**, selezionare **Input diretto**.</span><span class="sxs-lookup"><span data-stu-id="40f25-222">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="40f25-223">Per **SQLStatement**immettere l'istruzione SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="40f25-223">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        WAITFOR DELAY ?  
  
        ```  
  
5.  <span data-ttu-id="40f25-224">Nella pagina **Mapping parametri** dell'editor eseguire il mapping tra la variabile stringa DelaySeconds e il parametro 0.</span><span class="sxs-lookup"><span data-stu-id="40f25-224">On the **Parameter Mapping** page of the editor, map the DelaySeconds string variable to parameter 0.</span></span>  
  
## <a name="handling-an-error-condition"></a><span data-ttu-id="40f25-225">Gestione di una condizione di errore</span><span class="sxs-lookup"><span data-stu-id="40f25-225">Handling an Error Condition</span></span>  
 <span data-ttu-id="40f25-226">Se si desidera, è possibile configurare un componente aggiuntivo nel ciclo per registrare una condizione di errore o di timeout:</span><span class="sxs-lookup"><span data-stu-id="40f25-226">You can optionally configure an additional component inside the loop to log an error or a timeout condition:</span></span>  
  
-   <span data-ttu-id="40f25-227">Questo componente può registrare una condizione di errore quando il valore della variabile DataReady = 1.</span><span class="sxs-lookup"><span data-stu-id="40f25-227">This component can log an error condition when the value of the DataReady variable = 1.</span></span> <span data-ttu-id="40f25-228">Questo valore indica che non sono disponibili dati delle modifiche prima dell'inizio dell'intervallo selezionato.</span><span class="sxs-lookup"><span data-stu-id="40f25-228">This value indicates that there is no available change data before the start of the selected interval.</span></span>  
  
-   <span data-ttu-id="40f25-229">Questo componente può registrare una condizione di timeout anche quando viene raggiunto il valore della variabile TimeoutCeiling.</span><span class="sxs-lookup"><span data-stu-id="40f25-229">This component can also log a timeout condition when the value of the TimeoutCeiling variable is reached.</span></span> <span data-ttu-id="40f25-230">Questo valore indica che il ciclo ha testato i dati per il numero specificato di volte e i dati non sono ancora disponibili.</span><span class="sxs-lookup"><span data-stu-id="40f25-230">This value indicates the loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="40f25-231">Senza questo test o uno simile, l'esecuzione del pacchetto potrebbe continuare per un tempo illimitato.</span><span class="sxs-lookup"><span data-stu-id="40f25-231">Without this test or a similar test, the package might run indefinitely.</span></span>  
  
#### <a name="to-configure-an-optional-script-task-to-log-an-error-condition"></a><span data-ttu-id="40f25-232">Per configurare un'attività Script facoltativa per la registrazione di una condizione di errore</span><span class="sxs-lookup"><span data-stu-id="40f25-232">To configure an optional Script task to log an error condition</span></span>  
  
1.  <span data-ttu-id="40f25-233">Se si desidera segnalare l'errore o il timeout scrivendo un messaggio nel log, configurare la registrazione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="40f25-233">If you want to report the error or timeout by writing a message to the log, configure logging for the package.</span></span> <span data-ttu-id="40f25-234">Per altre informazioni, vedere [Abilitare la registrazione di pacchetti in SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="40f25-234">For more information, see [Enable Package Logging in SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
2.  <span data-ttu-id="40f25-235">Aggiungere un'attività Script all'interno del contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="40f25-235">Inside the For Loop container, add a Script task.</span></span>  
  
3.  <span data-ttu-id="40f25-236">Connettere l'attività Esegui SQL che esegue una query per determinare se i dati delle modifiche sono pronti alla nuova attività Script.</span><span class="sxs-lookup"><span data-stu-id="40f25-236">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
4.  <span data-ttu-id="40f25-237">Per il vincolo di precedenza che connette l'attività Esegui SQL all'attività Script, aprire **Editor vincoli di precedenza** e selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40f25-237">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="40f25-238">Per **Operazione valutazione**, selezionare **Espressione e vincolo**.</span><span class="sxs-lookup"><span data-stu-id="40f25-238">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="40f25-239">Per **Valore**, selezionare **Esito positivo**.</span><span class="sxs-lookup"><span data-stu-id="40f25-239">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="40f25-240">Il valore **Esito positivo** del vincolo si riferisce al risultato dell'attività precedente,</span><span class="sxs-lookup"><span data-stu-id="40f25-240">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="40f25-241">in questo caso l'esito positivo dell'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="40f25-241">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="40f25-242">Per **Espressione**, immettere `@DataReady == 1 || @DataReady == 5`.</span><span class="sxs-lookup"><span data-stu-id="40f25-242">For **Expression**, enter `@DataReady == 1 || @DataReady == 5`.</span></span>  
  
    4.  <span data-ttu-id="40f25-243">Selezionare **AND logico. Se questa opzione non è già selezionata, tutti i vincoli devono restituire il valore True**.</span><span class="sxs-lookup"><span data-stu-id="40f25-243">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="40f25-244">Questa opzione richiede che entrambe le condizioni, il vincolo e l'espressione, siano True.</span><span class="sxs-lookup"><span data-stu-id="40f25-244">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
5.  <span data-ttu-id="40f25-245">Nella pagina **Script**di **Editor attività Script** per **ReadOnlyVariables**selezionare **User::DataReady** e **User::ExtractStartTime** dall'elenco per rendere i valori disponibili per lo script.</span><span class="sxs-lookup"><span data-stu-id="40f25-245">In the **Script Task Editor**, on the **Script** page of the editor, for **ReadOnlyVariables**, select **User::DataReady** and **User::ExtractStartTime** from the list to make their values available to the script.</span></span>  
  
     <span data-ttu-id="40f25-246">Se si desidera includere informazioni da determinate variabili di sistema, ad esempio System::PackageName, nelle informazioni scritte nel log, selezionare anche tali variabili.</span><span class="sxs-lookup"><span data-stu-id="40f25-246">If you want to include information from certain system variables (for example, System::PackageName) in the information that you write to the log, select those variables also.</span></span>  
  
6.  <span data-ttu-id="40f25-247">Nella pagina **Script**in **Editor attività Script** fare clic su **Modifica script** per aprire l'ambiente di sviluppo dello script.</span><span class="sxs-lookup"><span data-stu-id="40f25-247">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
7.  <span data-ttu-id="40f25-248">Nella routine Main immettere il codice per registrare un errore chiamando il metodo `Dts.Log` o per generare un evento chiamando uno dei metodi dell'interfaccia `Dts.Events`.</span><span class="sxs-lookup"><span data-stu-id="40f25-248">In the Main procedure, enter code to log an error by calling the `Dts.Log` method, or to raise an event by calling one of the methods of the `Dts.Events` interface.</span></span> <span data-ttu-id="40f25-249">Informare dell'errore il pacchetto restituendo `Dts.TaskResult = Dts.Results.Failure`.</span><span class="sxs-lookup"><span data-stu-id="40f25-249">Inform the package of the error by returning `Dts.TaskResult = Dts.Results.Failure`.</span></span>  
  
     <span data-ttu-id="40f25-250">Nell'esempio seguente viene illustrato come scrivere un messaggio nel log.</span><span class="sxs-lookup"><span data-stu-id="40f25-250">The following sample shows how to write a message to the log.</span></span> <span data-ttu-id="40f25-251">Per altre informazioni, vedere [Registrazione nell'attività Script](../extending-packages-scripting/task/logging-in-the-script-task.md), [Generazione di eventi nell'attività Script](../extending-packages-scripting/task/raising-events-in-the-script-task.md)e [Risultati restituiti dall'attività Script](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="40f25-251">For more information, see [Logging in the Script Task](../extending-packages-scripting/task/logging-in-the-script-task.md), [Raising Events in the Script Task](../extending-packages-scripting/task/raising-events-in-the-script-task.md), and [Returning Results from the Script Task](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>  
  
    ```  
    ' User variables.  
    Dim dataReady As Integer = _  
      CType(Dts.Variables("DataReady").Value, Integer)  
    Dim extractStartTime As Date = _  
      CType(Dts.Variables("ExtractStartTime").Value, DateTime)  
  
    ' System variables.  
    Dim packageName As String = _  
      Dts.Variables("PackageName").Value.ToString()  
    Dim executionStartTime As Date = _  
      CType(Dts.Variables("StartTime").Value, DateTime)  
  
    Dim eventMessage As New System.Text.StringBuilder()  
  
    If dataReady = 1 OrElse dataReady = 5 Then  
  
      If dataReady = 1 Then  
        eventMessage.AppendLine("Start Time Error")  
      Else  
        eventMessage.AppendLine("Timeout Error")  
      End If  
  
      With eventMessage  
        .Append("The package ")  
        .Append(packageName)  
        .Append(" started at ")  
        .Append(executionStartTime.ToString())  
        .Append(" and ended at ")  
        .AppendLine(DateTime.Now().ToString())  
        If dataReady = 1 Then  
          .Append("The specified ExtractStartTime was ")  
          .AppendLine(extractStartTime.ToString())  
        End If  
      End With  
  
      System.Windows.Forms.MessageBox.Show(eventMessage.ToString())  
  
      Dts.Log(eventMessage.ToString(), 0, Nothing)  
  
      Dts.TaskResult = Dts.Results.Failure  
  
    Else  
  
      Dts.TaskResult = Dts.Results.Success  
  
    End If  
  
    ```  
  
8.  <span data-ttu-id="40f25-252">Chiudere l'ambiente di sviluppo dello script ed **Editor attività Script**.</span><span class="sxs-lookup"><span data-stu-id="40f25-252">Close the script development environment and the **Script Task Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="40f25-253">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="40f25-253">Next Step</span></span>  
 <span data-ttu-id="40f25-254">Dopo avere determinato che i dati delle modifiche sono pronti, il passaggio successivo consiste nel prepararsi a eseguire una query per tali dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="40f25-254">After you determine that change data is ready, the next step is to prepare to query for the change data.</span></span>  
  
 <span data-ttu-id="40f25-255">**Argomento successivo:** [Preparare l'esecuzione di una query per i dati delle modifiche](prepare-to-query-for-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="40f25-255">**Next topic:** [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md)</span></span>  
  
  
