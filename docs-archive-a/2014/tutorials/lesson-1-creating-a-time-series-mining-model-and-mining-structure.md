---
title: 'Lezione 1: creazione di un modello di data mining e di una struttura di data mining Time Series | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b201f2b8-9ab5-425b-9ff3-fe321a60a7b7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2513bc3837dd224f6561eb0015ced538ea3add8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625101"
---
# <a name="lesson-1-creating-a-time-series-mining-model-and-mining-structure"></a><span data-ttu-id="bfd96-102">Lezione 1: Creazione di un modello di data mining Time Series e di una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="bfd96-102">Lesson 1: Creating a Time Series Mining Model and Mining Structure</span></span>
  <span data-ttu-id="bfd96-103">In questa lezione verrà creato un modello di data mining che consente di eseguire una stima di valori nel tempo in base a dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="bfd96-103">In this lesson, you will create a mining model that allows you to predict values over time, based on historical data.</span></span> <span data-ttu-id="bfd96-104">Al momento della creazione del modello, la struttura sottostante verrà generata automaticamente e potrà essere utilizzata come base per nuovi modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="bfd96-104">When you create the model, the underlying structure will be generated automatically and can be used as the basis for additional mining models.</span></span>  
  
 <span data-ttu-id="bfd96-105">Questa lezione presuppone che l'utente abbia familiarità con i modelli di previsione e con i requisiti dell'algoritmo Microsoft Time Series.</span><span class="sxs-lookup"><span data-stu-id="bfd96-105">This lesson assumes that you are familiar with forecasting models and with the requirements of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="bfd96-106">Per altre informazioni, vedere [Algoritmo Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="bfd96-106">For more information, see [Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span></span>  
  
## <a name="create-mining-model-statement"></a><span data-ttu-id="bfd96-107">Istruzione CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="bfd96-107">CREATE MINING MODEL Statement</span></span>  
 <span data-ttu-id="bfd96-108">Per creare direttamente un modello di data mining e generare automaticamente la struttura di data mining sottostante, è possibile utilizzare l'istruzione [create mining model &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) .</span><span class="sxs-lookup"><span data-stu-id="bfd96-108">In order to create a mining model directly and automatically generate the underlying mining structure, you use the [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) statement.</span></span> <span data-ttu-id="bfd96-109">Il codice nell'istruzione può essere suddiviso nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfd96-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="bfd96-110">Assegnazione di un nome al modello</span><span class="sxs-lookup"><span data-stu-id="bfd96-110">Naming the model</span></span>  
  
-   <span data-ttu-id="bfd96-111">Definizione del timestamp</span><span class="sxs-lookup"><span data-stu-id="bfd96-111">Defining the time stamp</span></span>  
  
-   <span data-ttu-id="bfd96-112">Definizione della colonna chiave della serie facoltativa</span><span class="sxs-lookup"><span data-stu-id="bfd96-112">Defining the optional series key column</span></span>  
  
-   <span data-ttu-id="bfd96-113">Definizione di uno o più attributi stimabili</span><span class="sxs-lookup"><span data-stu-id="bfd96-113">Defining the predictable attribute or attributes</span></span>  
  
 <span data-ttu-id="bfd96-114">Di seguito è riportato un esempio generico dell'istruzione CREATE MINING MODEL:</span><span class="sxs-lookup"><span data-stu-id="bfd96-114">The following is a generic example of the CREATE MINING MODEL statement:</span></span>  
  
```  
CREATE MINING MODEL [<Mining Structure Name>]  
(  
   <key columns>,  
   <predictable attribute columns>  
)  
USING <algorithm name>([parameter list])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="bfd96-115">La prima riga del codice definisce il nome del modello di data mining:</span><span class="sxs-lookup"><span data-stu-id="bfd96-115">The first line of the code defines the name of the mining model:</span></span>  
  
```  
CREATE MINING MODEL [Mining Model Name]  
```  
  
 <span data-ttu-id="bfd96-116">Il nome della struttura sottostante viene generato automaticamente in Analysis Services aggiungendo il suffisso "_structure" al nome del modello, per assicurare l'utilizzo di un nome univoco derivato dal nome del modello.</span><span class="sxs-lookup"><span data-stu-id="bfd96-116">Analysis Services automatically generates a name for the underlying structure, by appending "_structure" to the model name, which ensures that the structure name is unique from the model name.</span></span> <span data-ttu-id="bfd96-117">Per informazioni sulla denominazione di un oggetto in DMX, vedere [identificatori &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="bfd96-117">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="bfd96-118">La riga successiva definisce la colonna chiave del modello di data mining, che nel caso di un modello Time Series identifica in modo univoco un intervallo temporale nei dati di origine.</span><span class="sxs-lookup"><span data-stu-id="bfd96-118">The next line of the code defines the key column for the mining model, which in the case of a time series model uniquely identifies a time step in the source data.</span></span> <span data-ttu-id="bfd96-119">L'intervallo temporale è identificato dalle parole chiave `KEY TIME` dopo il nome di colonna e i tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="bfd96-119">The time step is identified with the `KEY TIME` keywords after the column name and data types.</span></span> <span data-ttu-id="bfd96-120">Se il modello Time Series dispone di una chiave della serie separata, questa viene identificata tramite la parola chiave `KEY`.</span><span class="sxs-lookup"><span data-stu-id="bfd96-120">If the time series model has a separate series key, it is identified by using the `KEY` keyword.</span></span>  
  
```  
<key columns>  
```  
  
 <span data-ttu-id="bfd96-121">La riga successiva del codice viene utilizzata per definire le colonne del modello di cui verrà eseguita la stima.</span><span class="sxs-lookup"><span data-stu-id="bfd96-121">The next line of the code is used to define the columns in the model that will be predicted.</span></span> <span data-ttu-id="bfd96-122">Un modello di data mining può contenere più attributi stimabili.</span><span class="sxs-lookup"><span data-stu-id="bfd96-122">You can have multiple predictable attributes in a single mining model.</span></span> <span data-ttu-id="bfd96-123">In tal caso, l'algoritmo Microsoft Time Series genererà un'analisi distinta per ogni serie:</span><span class="sxs-lookup"><span data-stu-id="bfd96-123">When there are multiple predictable attributes, the Microsoft Time Series algorithm generates a separate analysis for each series:</span></span>  
  
```  
<predictable attribute columns>  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="bfd96-124">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="bfd96-124">Lesson Tasks</span></span>  
 <span data-ttu-id="bfd96-125">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfd96-125">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="bfd96-126">Creazione di una nuova query vuota</span><span class="sxs-lookup"><span data-stu-id="bfd96-126">Create a new blank query</span></span>  
  
-   <span data-ttu-id="bfd96-127">Modifica della query per creare il modello di data mining</span><span class="sxs-lookup"><span data-stu-id="bfd96-127">Alter the query to create the mining model</span></span>  
  
-   <span data-ttu-id="bfd96-128">Eseguire la query</span><span class="sxs-lookup"><span data-stu-id="bfd96-128">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="bfd96-129">Creazione della query</span><span class="sxs-lookup"><span data-stu-id="bfd96-129">Creating the Query</span></span>  
 <span data-ttu-id="bfd96-130">Il primo passaggio consiste nella connessione a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e nella creazione di una nuova query DMX in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfd96-130">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="bfd96-131">Per creare una nuova query DMX in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bfd96-131">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="bfd96-132">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfd96-132">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="bfd96-133">Nella finestra di dialogo **Connetti al server** selezionare **Analysis Services**per **tipo di server**.</span><span class="sxs-lookup"><span data-stu-id="bfd96-133">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="bfd96-134">In **nome server**, digitare `LocalHost` o il nome dell'istanza di a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cui si desidera connettersi per questa lezione.</span><span class="sxs-lookup"><span data-stu-id="bfd96-134">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="bfd96-135">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="bfd96-135">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="bfd96-136">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="bfd96-136">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="bfd96-137">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="bfd96-137">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="bfd96-138">Modifica della query</span><span class="sxs-lookup"><span data-stu-id="bfd96-138">Altering the Query</span></span>  
 <span data-ttu-id="bfd96-139">Il passaggio successivo consiste nel modificare l'istruzione CREATE MINING MODEL per creare il modello di data mining utilizzato per la previsione, insieme alla struttura di data mining sottostante.</span><span class="sxs-lookup"><span data-stu-id="bfd96-139">The next step is to modify the CREATE MINING MODEL statement to create the mining model used for forecasting, together with its underlying mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-model-statement"></a><span data-ttu-id="bfd96-140">Per personalizzare l'istruzione CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="bfd96-140">To customize the CREATE MINING MODEL statement</span></span>  
  
1.  <span data-ttu-id="bfd96-141">Nell'editor di query copiare l'esempio generico dell'istruzione CREATE MINING MODEL nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="bfd96-141">In Query Editor, copy the generic example of the CREATE MINING MODEL statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="bfd96-142">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bfd96-142">Replace the following:</span></span>  
  
    ```  
    [mining model name]   
    ```  
  
     <span data-ttu-id="bfd96-143">con:</span><span class="sxs-lookup"><span data-stu-id="bfd96-143">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
3.  <span data-ttu-id="bfd96-144">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bfd96-144">Replace the following:</span></span>  
  
    ```  
    <key columns>  
    ```  
  
     <span data-ttu-id="bfd96-145">con:</span><span class="sxs-lookup"><span data-stu-id="bfd96-145">with:</span></span>  
  
    ```  
    [Reporting Date] DATE KEY TIME,  
    [Model Region] TEXT KEY  
    ```  
  
     <span data-ttu-id="bfd96-146">La parola chiave `TIME KEY` indica che la colonna ReportingDate contiene i valori dell'intervallo temporale utilizzati per ordinare i valori.</span><span class="sxs-lookup"><span data-stu-id="bfd96-146">The `TIME KEY` keyword indicates that the ReportingDate column contains the time step values used to order the values.</span></span> <span data-ttu-id="bfd96-147">Gli intervalli temporali possono essere date e ore, numeri interi o qualsiasi tipo di dati ordinati, purché i valori siano univoci e i dati vengano ordinati.</span><span class="sxs-lookup"><span data-stu-id="bfd96-147">Time steps can be dates and times, integers, or any ordered data type, so long as the values are unique and the data is sorted.</span></span>  
  
     <span data-ttu-id="bfd96-148">Le parole chiave `TEXT` e `KEY` indicano che la colonna ModelRegion contiene una chiave della serie aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="bfd96-148">The `TEXT` and `KEY` keywords indicate that the ModelRegion column contains an additional series key.</span></span> <span data-ttu-id="bfd96-149">È consentita solo una chiave della serie e i valori della colonna devono essere distinti.</span><span class="sxs-lookup"><span data-stu-id="bfd96-149">You can have only one series key, and the values in the column must be distinct.</span></span>  
  
4.  <span data-ttu-id="bfd96-150">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bfd96-150">Replace the following:</span></span>  
  
    ```  
    < predictable attribute columns> )  
    ```  
  
     <span data-ttu-id="bfd96-151">con:</span><span class="sxs-lookup"><span data-stu-id="bfd96-151">with:</span></span>  
  
    ```  
    [Quantity] LONG CONTINUOUS PREDICT,  
    [Amount] DOUBLE CONTINUOUS PREDICT  
    )  
    ```  
  
5.  <span data-ttu-id="bfd96-152">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bfd96-152">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([parameter list])  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="bfd96-153">con:</span><span class="sxs-lookup"><span data-stu-id="bfd96-153">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series(AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="bfd96-154">Il parametro `AUTO_DETECT_PERIODICITY` = 0,8 dell'algoritmo indica che si desidera che l'algoritmo rilevi cicli nei dati.</span><span class="sxs-lookup"><span data-stu-id="bfd96-154">The algorithm parameter, `AUTO_DETECT_PERIODICITY` = 0.8, indicates that you want the algorithm to detect cycles in the data.</span></span> <span data-ttu-id="bfd96-155">L'impostazione di questo parametro su un valore prossimo a 1 consente di individuare numerosi modelli, ma può rallentare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="bfd96-155">Setting this value closer to 1 favors the discovery of many patterns but can slow processing.</span></span>  
  
     <span data-ttu-id="bfd96-156">Il parametro `FORECAST_METHOD` dell'algoritmo indica se si desidera che i dati vengano analizzati tramite ARTXP, ARIMA o una combinazione dei due algoritmi.</span><span class="sxs-lookup"><span data-stu-id="bfd96-156">The algorithm parameter, `FORECAST_METHOD`, indicates whether you want the data to be analyzed using ARTXP, ARIMA, or a mixture of both.</span></span>  
  
     <span data-ttu-id="bfd96-157">La parola chiave `WITH DRILLTHROUGH` specifica che si desidera essere in grado di visualizzare statistiche dettagliate nei dati di origine dopo il completamento del modello.</span><span class="sxs-lookup"><span data-stu-id="bfd96-157">The keyword, `WITH DRILLTHROUGH`, specify that you want to be able to view detailed statistics in the source data after the model is complete.</span></span> <span data-ttu-id="bfd96-158">È necessario aggiungere questa clausola se si desidera esplorare il modello tramite il Visualizzatore Microsoft Time Series.</span><span class="sxs-lookup"><span data-stu-id="bfd96-158">You must add this clause if you want to browse the model by using the Microsoft Time Series Viewer.</span></span> <span data-ttu-id="bfd96-159">Tale clausola non è necessaria per l'esecuzione di stime.</span><span class="sxs-lookup"><span data-stu-id="bfd96-159">It is not required for prediction.</span></span>  
  
     <span data-ttu-id="bfd96-160">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="bfd96-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING MODEL [Forecasting_MIXED]  
         (  
        [Reporting Date] DATE KEY TIME,  
        [Model Region] TEXT KEY,  
        [Quantity] LONG CONTINUOUS PREDICT,  
        [Amount] DOUBLE CONTINUOUS PREDICT  
        )  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
  
    ```  
  
6.  <span data-ttu-id="bfd96-161">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="bfd96-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="bfd96-162">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Forecasting_MIXED.dmx` .</span><span class="sxs-lookup"><span data-stu-id="bfd96-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_MIXED.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="bfd96-163">Esecuzione della query</span><span class="sxs-lookup"><span data-stu-id="bfd96-163">Executing the Query</span></span>  
 <span data-ttu-id="bfd96-164">Il passaggio conclusivo consiste nell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="bfd96-164">The final step is to execute the query.</span></span> <span data-ttu-id="bfd96-165">Dopo la creazione e il salvataggio di una query, è necessario eseguirla per creare il modello di data mining e la relativa struttura sul server.</span><span class="sxs-lookup"><span data-stu-id="bfd96-165">After a query is created and saved, it needs to be executed to create the mining model and its mining structure on the server.</span></span> <span data-ttu-id="bfd96-166">Per ulteriori informazioni sull'esecuzione di query nell'editor di query, vedere [motore di database editor di query &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="bfd96-166">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="bfd96-167">Per eseguire la query</span><span class="sxs-lookup"><span data-stu-id="bfd96-167">To execute the query</span></span>  
  
-   <span data-ttu-id="bfd96-168">Nell'editor di query fare clic su **Esegui**sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="bfd96-168">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="bfd96-169">Lo stato della query viene visualizzato nella scheda **messaggi** nella parte inferiore dell'editor di query al termine dell'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="bfd96-169">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="bfd96-170">Dovrebbero essere visualizzati i messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfd96-170">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="bfd96-171">Nel server è presente una nuova struttura denominata **Forecasting_MIXED_Structure** , insieme al modello di data mining correlato **Forecasting_MIXED**.</span><span class="sxs-lookup"><span data-stu-id="bfd96-171">A new structure named **Forecasting_MIXED_Structure** now exists on the server, together with the related mining model **Forecasting_MIXED**.</span></span>  
  
 <span data-ttu-id="bfd96-172">Nella lezione successiva verrà aggiunto un modello di data mining alla struttura di data mining **Forecasting_MIXED** appena creata.</span><span class="sxs-lookup"><span data-stu-id="bfd96-172">In the next lesson, you will add a mining model to the **Forecasting_MIXED** mining structure that you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="bfd96-173">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="bfd96-173">Next Lesson</span></span>  
 [<span data-ttu-id="bfd96-174">Lezione 2: Aggiunta di modelli di data mining alla struttura di data mining Time Series</span><span class="sxs-lookup"><span data-stu-id="bfd96-174">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md)  
  
## <a name="see-also"></a><span data-ttu-id="bfd96-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfd96-175">See Also</span></span>  
 <span data-ttu-id="bfd96-176">[Contenuto del modello di data mining per i modelli Time Series &#40;Analysis Services-Data mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="bfd96-176">[Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="bfd96-177">Riferimento tecnico per l'algoritmo Microsoft Time Series</span><span class="sxs-lookup"><span data-stu-id="bfd96-177">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
