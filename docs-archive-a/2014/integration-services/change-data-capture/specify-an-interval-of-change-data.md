---
title: Definire un intervallo dei dati delle modifiche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],specifying interval
ms.assetid: 17899078-8ba3-4f40-8769-e9837dc3ec60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 70b9c14d609f2db69ee5751eca18acb5262a07a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626832"
---
# <a name="specify-an-interval-of-change-data"></a><span data-ttu-id="07f39-102">Definizione di un intervallo dei dati delle modifiche</span><span class="sxs-lookup"><span data-stu-id="07f39-102">Specify an Interval of Change Data</span></span>
  <span data-ttu-id="07f39-103">Nel flusso di controllo di un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che esegue un carico incrementale dei dati delle modifiche, la prima attività consiste nel calcolare gli endpoint dell'intervallo di modifiche.</span><span class="sxs-lookup"><span data-stu-id="07f39-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="07f39-104">Tali endpoint sono valori `datetime` e verranno archiviati in variabili del pacchetto per l'utilizzo successivo nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="07f39-104">These endpoints are `datetime` values and will be stored in package variables for use later in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07f39-105">Per una descrizione del processo complessivo di progettazione del flusso di controllo, vedere [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="07f39-105">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="set-up-package-variables-for-the-endpoints"></a><span data-ttu-id="07f39-106">Configurare le variabili del pacchetto per gli endpoint</span><span class="sxs-lookup"><span data-stu-id="07f39-106">Set Up Package Variables for the Endpoints</span></span>  
 <span data-ttu-id="07f39-107">Prima di configurare l'attività Esegui SQL per il calcolo degli endpoint, è necessario definire le variabili del pacchetto in cui verranno archiviati gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="07f39-107">Before configuring the Execute SQL task to calculate the endpoints, the package variables that will store the endpoints have to be defined.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="07f39-108">Per configurare le variabili del pacchetto</span><span class="sxs-lookup"><span data-stu-id="07f39-108">To set up package variables</span></span>  
  
1.  <span data-ttu-id="07f39-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire un nuovo progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07f39-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="07f39-110">Nella finestra **Variabili** creare le variabili seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f39-110">In the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="07f39-111">Creare una variabile con il tipo di dati `datetime` per memorizzare il punto iniziale per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="07f39-111">Create a variable with the `datetime` data type to hold the starting point for the interval.</span></span>  
  
         <span data-ttu-id="07f39-112">In questo esempio viene utilizzato il nome di variabile ExtractStartTime.</span><span class="sxs-lookup"><span data-stu-id="07f39-112">This example uses the variable name, ExtractStartTime.</span></span>  
  
    2.  <span data-ttu-id="07f39-113">Creare un'altra variabile con il tipo di dati `datetime` per memorizzare il punto finale per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="07f39-113">Create another variable with the `datetime` data type to hold the ending point for the interval.</span></span>  
  
         <span data-ttu-id="07f39-114">In questo esempio viene utilizzato il nome di variabile ExtractEndTime.</span><span class="sxs-lookup"><span data-stu-id="07f39-114">This example uses the variable name, ExtractEndTime.</span></span>  
  
 <span data-ttu-id="07f39-115">Se si calcolano gli endpoint in un pacchetto master che esegue più pacchetti figlio, è possibile utilizzare le configurazioni Variabile pacchetto padre per passare i valori di tali variabili a ciascun pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="07f39-115">If you calculate the endpoints in a master package that executes multiple child packages, you can use Parent Package Variable configurations to pass the values of these variables to each child package.</span></span> <span data-ttu-id="07f39-116">Per altre informazioni, vedere [Attività Esegui pacchetto](../control-flow/execute-package-task.md) e [Utilizzare i valori di variabili e parametri in un pacchetto figlio](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="07f39-116">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
## <a name="calculate-a-starting-point-and-an-ending-point-for-change-data"></a><span data-ttu-id="07f39-117">Calcolare un punto iniziale e un punto finale per i dati delle modifiche</span><span class="sxs-lookup"><span data-stu-id="07f39-117">Calculate a Starting Point and an Ending Point for Change Data</span></span>  
 <span data-ttu-id="07f39-118">Dopo avere configurato le variabili del pacchetto per gli endpoint dell'intervallo, è possibile calcolare i valori effettivi per tali endpoint ed eseguirne il mapping alle variabili del pacchetto corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="07f39-118">After you set up the package variables for the interval endpoints, you can calculate the actual values for those endpoints and map those values to the corresponding package variables.</span></span> <span data-ttu-id="07f39-119">Poiché gli endpoint sono valori `datetime`, sarà necessario utilizzare funzioni in grado di calcolare o utilizzare valori `datetime`.</span><span class="sxs-lookup"><span data-stu-id="07f39-119">Because those endpoints are `datetime` values, you will have to use functions that can calculate or work with `datetime` values.</span></span> <span data-ttu-id="07f39-120">Sia il linguaggio delle espressioni [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che Transact-SQL dispongono di funzioni che utilizzano valori `datetime`:</span><span class="sxs-lookup"><span data-stu-id="07f39-120">Both the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language and Transact-SQL have functions that work with `datetime` values:</span></span>  
  
 <span data-ttu-id="07f39-121">Funzioni nel linguaggio delle espressioni [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che utilizzano valori `datetime`</span><span class="sxs-lookup"><span data-stu-id="07f39-121">Functions in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language that work with `datetime` values</span></span>  
 -   [<span data-ttu-id="07f39-122">DATEADD &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="07f39-122">DATEADD &#40;SSIS Expression&#41;</span></span>](../expressions/dateadd-ssis-expression.md)  
  
-   [<span data-ttu-id="07f39-123">DATEDIFF &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="07f39-123">DATEDIFF &#40;SSIS Expression&#41;</span></span>](../expressions/datediff-ssis-expression.md)  
  
-   [<span data-ttu-id="07f39-124">DATEPART &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="07f39-124">DATEPART &#40;SSIS Expression&#41;</span></span>](../expressions/datepart-ssis-expression.md)  
  
-   [<span data-ttu-id="07f39-125">DAY &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="07f39-125">DAY &#40;SSIS Expression&#41;</span></span>](../expressions/day-ssis-expression.md)  
  
-   [<span data-ttu-id="07f39-126">GETDATE &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="07f39-126">GETDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getdate-ssis-expression.md)  
  
-   [<span data-ttu-id="07f39-127">GETUTCDATE &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="07f39-127">GETUTCDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getutcdate-ssis-expression.md)  
  
-   [<span data-ttu-id="07f39-128">MONTH &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="07f39-128">MONTH &#40;SSIS Expression&#41;</span></span>](../expressions/month-ssis-expression.md)  
  
-   [<span data-ttu-id="07f39-129">YEAR &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="07f39-129">YEAR &#40;SSIS Expression&#41;</span></span>](../expressions/year-ssis-expression.md)  
  
 <span data-ttu-id="07f39-130">Funzioni in Transact-SQL che utilizzano valori `datetime`</span><span class="sxs-lookup"><span data-stu-id="07f39-130">Functions in Transact-SQL that work with `datetime` values</span></span>  
 <span data-ttu-id="07f39-131">[Funzioni e tipi di dati di data e ora &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="07f39-131">[Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
 <span data-ttu-id="07f39-132">Prima di utilizzare una di queste funzioni `datetime` per calcolare gli endpoint, è necessario determinare se l'intervallo è fisso e si verifica regolarmente.</span><span class="sxs-lookup"><span data-stu-id="07f39-132">Before you use any one of these `datetime` functions to calculate the endpoints, you have to determine whether the interval is fixed and occurs on a regular schedule.</span></span> <span data-ttu-id="07f39-133">In genere, le modifiche verificatesi nelle tabelle di origine vengono applicate alle tabelle di destinazione a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="07f39-133">Typically, you want to apply changes that have occurred in source tables to destination tables on a regular schedule.</span></span> <span data-ttu-id="07f39-134">Potrebbe essere necessario, ad esempio, applicare le modifiche su base oraria, giornaliera o settimanale.</span><span class="sxs-lookup"><span data-stu-id="07f39-134">For example, you might want to apply those changes on an hourly, daily, or weekly basis.</span></span>  
  
 <span data-ttu-id="07f39-135">Dopo avere determinato se l'intervallo di modifiche è fisso o più casuale, è possibile calcolare gli endpoint:</span><span class="sxs-lookup"><span data-stu-id="07f39-135">After you understand whether your change interval is fixed or is more random, you can calculate the endpoints:</span></span>  
  
-   <span data-ttu-id="07f39-136">**Calcolo della data e dell'ora di inizio**.</span><span class="sxs-lookup"><span data-stu-id="07f39-136">**Calculating the starting date and time**.</span></span> <span data-ttu-id="07f39-137">Utilizzare la data e l'ora di fine del caricamento precedente come data e ora di inizio correnti.</span><span class="sxs-lookup"><span data-stu-id="07f39-137">You use the ending date and time from the previous load as the current starting date and time.</span></span> <span data-ttu-id="07f39-138">Se si utilizza un intervallo fisso per i caricamenti incrementali, è possibile calcolare questo valore utilizzando le funzioni `datetime` di Transact-SQL o del linguaggio delle espressioni [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07f39-138">If you use a fixed interval for incremental loads, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span> <span data-ttu-id="07f39-139">In caso contrario, potrebbe essere necessario impostare la persistenza degli endpoint tra le esecuzioni e utilizzare un'attività Esegui SQL o un'attività Script per caricare l'endpoint precedente.</span><span class="sxs-lookup"><span data-stu-id="07f39-139">Otherwise, you might have to persist the endpoints between executions, and use an Execute SQL task or a Script task to load the previous endpoint.</span></span>  
  
-   <span data-ttu-id="07f39-140">**Calcolo della data e dell'ora di fine**.</span><span class="sxs-lookup"><span data-stu-id="07f39-140">**Calculating the ending date and time**.</span></span> <span data-ttu-id="07f39-141">Se si utilizza un intervallo fisso per i carichi incrementali, calcolare la data e l'ora di fine correnti come offset della data e dell'ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="07f39-141">If you use a fixed interval for incremental loads, calculate the current ending date and time as an offset from the starting date and time.</span></span> <span data-ttu-id="07f39-142">Anche in questo caso, è possibile calcolare questo valore utilizzando le `datetime` funzioni di Transact-SQL o del [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] linguaggio delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="07f39-142">Again, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span>  
  
 <span data-ttu-id="07f39-143">Nella procedura seguente l'intervallo di modifiche è un intervallo fisso e si presuppone che il pacchetto del caricamento incrementale venga eseguito ogni giorno senza eccezione.</span><span class="sxs-lookup"><span data-stu-id="07f39-143">In the following procedure, the change interval uses a fixed interval and assumes that the incremental load package is run daily without exception.</span></span> <span data-ttu-id="07f39-144">In caso contrario, i dati delle modifiche per gli intervalli in cui non viene eseguito il caricamento andranno perduti.</span><span class="sxs-lookup"><span data-stu-id="07f39-144">Otherwise, change data for missed intervals would be lost.</span></span> <span data-ttu-id="07f39-145">Il punto iniziale per l'intervallo è costituito dalla mezzanotte del giorno precedente a ieri, ovvero tra le 24 e le 48 ore precedenti.</span><span class="sxs-lookup"><span data-stu-id="07f39-145">The starting point for the interval is midnight the day before yesterday, that is, between 24 and 48 hours ago.</span></span> <span data-ttu-id="07f39-146">Il punto finale per l'intervallo è costituito dalla mezzanotte di ieri, ovvero la notte precedente, tra le 0 e le 24 ore precedenti.</span><span class="sxs-lookup"><span data-stu-id="07f39-146">The ending point for the interval is midnight yesterday, that is, the previous night, between 0 and 24 hours ago.</span></span>  
  
#### <a name="to-calculate-the-starting-point-and-ending-point-for-the-capture-interval"></a><span data-ttu-id="07f39-147">Per calcolare il punto iniziale e il punto finale per l'intervallo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="07f39-147">To calculate the starting point and ending point for the capture interval</span></span>  
  
1.  <span data-ttu-id="07f39-148">Nella scheda **Flusso di controllo** di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] aggiungere un'attività Esegui SQL al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="07f39-148">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add an Execute SQL Task to the package.</span></span>  
  
2.  <span data-ttu-id="07f39-149">Nella pagina **Generale**in **Editor attività Esegui SQL** selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f39-149">Open the **Execute SQL Task Editor**, and on the **General** page of the editor, select the following options:</span></span>  
  
    1.  <span data-ttu-id="07f39-150">Per **ResultSet**, selezionare **Riga singola**.</span><span class="sxs-lookup"><span data-stu-id="07f39-150">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="07f39-151">Configurare una connessione valida al database di origine.</span><span class="sxs-lookup"><span data-stu-id="07f39-151">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="07f39-152">Per **SQLSourceType**, selezionare **Input diretto**.</span><span class="sxs-lookup"><span data-stu-id="07f39-152">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="07f39-153">Per **SQLStatement**immettere l'istruzione SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="07f39-153">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        SELECT DATEADD(dd,0, DATEDIFF(dd,0,GETDATE()-1)) AS ExtractStartTime,  
          DATEADD(dd,0, DATEDIFF(dd,0,GETDATE())) AS ExtractEndTime  
  
        ```  
  
3.  <span data-ttu-id="07f39-154">Nella pagina **Set dei risultati** di **Editor attività Esegui SQL**eseguire il mapping tra il risultato di ExtractStartTime e la variabile del pacchetto ExtractStartTime e tra il risultato di ExtractEndTime e la variabile del pacchetto ExtractEndTime.</span><span class="sxs-lookup"><span data-stu-id="07f39-154">On the **Result Set** page of the **Execute SQL Task Editor**, map the ExtractStartTime result to the ExtractStartTime package variable, and map the ExtractEndTime result to the ExtractEndTime package variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="07f39-155">Quando si usa un'espressione per impostare il valore di una variabile in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], l'espressione viene valutata ogni volta che si accede al valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="07f39-155">When you use an expression to set the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, the expression is evaluated every time that the value of the variable is accessed.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="07f39-156">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="07f39-156">Next Step</span></span>  
 <span data-ttu-id="07f39-157">Dopo avere calcolato il punto iniziale e il punto finale per un intervallo di modifiche, il passaggio successivo consiste nel determinare se i dati delle modifiche sono pronti.</span><span class="sxs-lookup"><span data-stu-id="07f39-157">After you calculate the starting point and ending point for a range of changes, the next step is to determine whether the change data is ready.</span></span>  
  
 <span data-ttu-id="07f39-158">**Argomento successivo:** [Determinare se i dati delle modifiche sono pronti](determine-whether-the-change-data-is-ready.md)</span><span class="sxs-lookup"><span data-stu-id="07f39-158">**Next topic:** [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f39-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07f39-159">See Also</span></span>  
 <span data-ttu-id="07f39-160">[Utilizzo di variabili nei pacchetti](../use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="07f39-160">[Use Variables in Packages](../use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="07f39-161">[Espressioni di Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="07f39-161">[Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="07f39-162">[Attività Esegui SQL](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="07f39-162">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="07f39-163">Attività Script</span><span class="sxs-lookup"><span data-stu-id="07f39-163">Script Task</span></span>](../control-flow/script-task.md)  
  
  
