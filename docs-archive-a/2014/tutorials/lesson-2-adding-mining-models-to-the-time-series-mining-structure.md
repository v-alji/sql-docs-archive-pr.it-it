---
title: 'Lezione 2: aggiunta di modelli di data mining alla struttura di data mining Time Series | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75c2a74b-21ce-44fb-a26b-68be4c685c12
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ae0bb91fafb53c0c077a4e0d82558b550d0e6070
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623682"
---
# <a name="lesson-2-adding-mining-models-to-the-time-series-mining-structure"></a><span data-ttu-id="418c7-102">Lezione 2: Aggiunta di modelli di data mining alla struttura di data mining Time Series</span><span class="sxs-lookup"><span data-stu-id="418c7-102">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>
  <span data-ttu-id="418c7-103">In questa lezione verrà aggiunto un nuovo modello di data mining alla struttura di data mining appena creata nella [lezione 1: creazione di un modello di data mining Time Series e di una struttura di data mining](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="418c7-103">In this lesson, you will add a new mining model to the mining structure that you just created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md).</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="418c7-104">Istruzione ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="418c7-104">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="418c7-105">Per aggiungere un nuovo modello di data mining a una struttura di data mining esistente, utilizzare l'istruzione [ALTER mining structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="418c7-105">In order to add a new mining model to an existing mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="418c7-106">Il codice nell'istruzione può essere suddiviso nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="418c7-106">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="418c7-107">Identificazione della struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="418c7-107">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="418c7-108">Denominazione del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="418c7-108">Naming the mining model</span></span>  
  
-   <span data-ttu-id="418c7-109">Definizione della colonna chiave</span><span class="sxs-lookup"><span data-stu-id="418c7-109">Defining the key column</span></span>  
  
-   <span data-ttu-id="418c7-110">Definizione delle colonne stimabili</span><span class="sxs-lookup"><span data-stu-id="418c7-110">Defining the predictable columns</span></span>  
  
-   <span data-ttu-id="418c7-111">Specifica delle modifiche a livello di algoritmo e parametri</span><span class="sxs-lookup"><span data-stu-id="418c7-111">Specifying the algorithm and any parameter changes</span></span>  
  
 <span data-ttu-id="418c7-112">Di seguito è riportato un esempio generico dell'istruzione ALTER MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="418c7-112">The following is a generic example of the ALTER MINING STRUCTURE statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
   ([<key columns>],  
    <mining model columns>  
   )  
USING <algorithm name>([<algorithm parameters>])  
[WITH DRILLTHROUGH]  
```  
  
 <span data-ttu-id="418c7-113">La prima riga del codice identifica la struttura di data mining esistente a cui verranno aggiunti i modelli di data mining:</span><span class="sxs-lookup"><span data-stu-id="418c7-113">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="418c7-114">La riga successiva del codice indica il nome del modello di data mining che verrà aggiunto alla struttura di data mining:</span><span class="sxs-lookup"><span data-stu-id="418c7-114">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="418c7-115">Per informazioni sulla denominazione di un oggetto in DMX, vedere [identificatori &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="418c7-115">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="418c7-116">Le successive righe del codice definiscono le colonne della struttura di data mining che verranno utilizzate dal modello di data mining:</span><span class="sxs-lookup"><span data-stu-id="418c7-116">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key columns>],  
<mining model columns>  
```  
  
 <span data-ttu-id="418c7-117">È possibile utilizzare solo colonne già esistenti nella struttura di data mining e la prima colonna nell'elenco deve essere la colonna chiave dalla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="418c7-117">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="418c7-118">Le righe successive del codice definiscono l'algoritmo di data mining che genera il modello di data mining e i parametri che è possibile impostare nell'algoritmo, oltre a specificare se è possibile eseguire il drill-down dal modello di data mining per visualizzare dati dettagliati nei case di training:</span><span class="sxs-lookup"><span data-stu-id="418c7-118">The next lines of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm, and specify whether you can drill down from the mining model into view detailed data in the training cases:</span></span>  
  
```  
USING <algorithm name>([<algorithm parameters>])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="418c7-119">Per ulteriori informazioni sui parametri dell'algoritmo che è possibile modificare, vedere [riferimento tecnico per l'algoritmo Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="418c7-119">For more information about the algorithm parameters that you can adjust, see [Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="418c7-120">Per specificare che una colonna nel modello di data mining deve essere utilizzata per la stima, è possibile utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="418c7-120">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="418c7-121">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="418c7-121">Lesson Tasks</span></span>  
 <span data-ttu-id="418c7-122">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="418c7-122">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="418c7-123">Aggiunta di un nuovo modello di data mining Time Series alla struttura</span><span class="sxs-lookup"><span data-stu-id="418c7-123">Add a new time series mining model to the structure.</span></span>  
  
-   <span data-ttu-id="418c7-124">Modifica dei parametri dell'algoritmo per utilizzare un metodo differente di analisi e stima</span><span class="sxs-lookup"><span data-stu-id="418c7-124">Change the algorithm parameters to use a different method of analysis and prediction</span></span>  
  
## <a name="adding-an-arima-time-series-model-to-the-structure"></a><span data-ttu-id="418c7-125">Aggiunta di un modello Time Series ARIMA alla struttura</span><span class="sxs-lookup"><span data-stu-id="418c7-125">Adding an ARIMA Time Series Model to the Structure</span></span>  
 <span data-ttu-id="418c7-126">Il primo passaggio consiste nell'aggiunta di un nuovo modello di data mining di previsione alla struttura esistente.</span><span class="sxs-lookup"><span data-stu-id="418c7-126">The first step is to add a new forecasting mining model to the existing structure.</span></span> <span data-ttu-id="418c7-127">Per impostazione predefinita, l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series crea modelli di data mining Time Series tramite due algoritmi, ARIMA e ARTXP, e combinando i risultati.</span><span class="sxs-lookup"><span data-stu-id="418c7-127">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm creates time series mining models by using two algorithms, ARIMA and ARTXP, and blending the results.</span></span> <span data-ttu-id="418c7-128">È tuttavia possibile specificare un solo algoritmo da utilizzare o l'esatta combinazione di algoritmi.</span><span class="sxs-lookup"><span data-stu-id="418c7-128">However, you can specify a single algorithm to use, or you can specify the exact blend of algorithms.</span></span> <span data-ttu-id="418c7-129">In questo passaggio si aggiungerà un nuovo modello che utilizza solo l'algoritmo ARIMA.</span><span class="sxs-lookup"><span data-stu-id="418c7-129">In this step, you will add a new model that uses only the ARIMA algorithm.</span></span> <span data-ttu-id="418c7-130">L'algoritmo ARIMA è ottimizzato per le stime a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="418c7-130">This algorithm is optimized for long-term prediction.</span></span>  
  
#### <a name="to-add-an-arima-time-series-mining-model"></a><span data-ttu-id="418c7-131">Per aggiungere un modello di data mining Time Series ARIMA</span><span class="sxs-lookup"><span data-stu-id="418c7-131">To add an ARIMA time series mining model</span></span>  
  
1.  <span data-ttu-id="418c7-132">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX** per aprire l'editor di query e una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="418c7-132">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="418c7-133">Copiare l'esempio generico dell'istruzione ALTER MINING STRUCTURE nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="418c7-133">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="418c7-134">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="418c7-134">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="418c7-135">con:</span><span class="sxs-lookup"><span data-stu-id="418c7-135">with:</span></span>  
  
    ```  
    [Forecasting_MIXED_Structure]  
    ```  
  
4.  <span data-ttu-id="418c7-136">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="418c7-136">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="418c7-137">con:</span><span class="sxs-lookup"><span data-stu-id="418c7-137">with:</span></span>  
  
    ```  
    Forecasting_ARIMA  
    ```  
  
5.  <span data-ttu-id="418c7-138">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="418c7-138">Replace the following:</span></span>  
  
    ```  
    <key columns>,  
    ```  
  
     <span data-ttu-id="418c7-139">con:</span><span class="sxs-lookup"><span data-stu-id="418c7-139">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]  
    ```  
  
     <span data-ttu-id="418c7-140">Si noti che non è necessario ripetere le informazioni sul tipo di data o sul tipo di contenuto fornite nell'istruzione CREATE MINING MODEL, perché queste informazioni sono già memorizzate nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="418c7-140">Note that you do not need to repeat any of the date type or content type information that you provided in the CREATE MINING MODEL statement, because this information is already stored in the mining structure.</span></span>  
  
6.  <span data-ttu-id="418c7-141">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="418c7-141">Replace the following:</span></span>  
  
    ```  
    <mining model columns>  
    ```  
  
     <span data-ttu-id="418c7-142">con:</span><span class="sxs-lookup"><span data-stu-id="418c7-142">with:</span></span>  
  
    ```  
    ([Quantity] PREDICT,  
    [Amount] PREDICT  
    )  
    ```  
  
7.  <span data-ttu-id="418c7-143">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="418c7-143">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([<algorithm parameters>])   
    [WITH DRILLTHROUGH]  
    ```  
  
     <span data-ttu-id="418c7-144">con:</span><span class="sxs-lookup"><span data-stu-id="418c7-144">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="418c7-145">L'istruzione risultante dovrebbe essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="418c7-145">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARIMA]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
8.  <span data-ttu-id="418c7-146">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="418c7-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
9. <span data-ttu-id="418c7-147">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Forecasting_ARIMA.dmx` .</span><span class="sxs-lookup"><span data-stu-id="418c7-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARIMA.dmx`.</span></span>  
  
10. <span data-ttu-id="418c7-148">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="418c7-148">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-artxp-time-series-model-to-the-structure"></a><span data-ttu-id="418c7-149">Aggiunta di un modello Time Series ARTXP alla struttura</span><span class="sxs-lookup"><span data-stu-id="418c7-149">Adding an ARTXP Time Series Model to the Structure</span></span>  
 <span data-ttu-id="418c7-150">L'algoritmo ARTXP era l'algoritmo Time Series predefinito in SQL Server 2005 ed è ottimizzato per le stime a breve termine.</span><span class="sxs-lookup"><span data-stu-id="418c7-150">The ARTXP algorithm was the default time series algorithm in SQL Server 2005 and is optimized for short-term prediction.</span></span> <span data-ttu-id="418c7-151">Per confrontare le stime tramite tutti e tre gli algoritmi Time Series, si aggiungerà un ulteriore modello basato sull'algoritmo ARTXP.</span><span class="sxs-lookup"><span data-stu-id="418c7-151">To compare predictions by using all three time series algorithms, you will add one more model that is based on the ARTXP algorithm.</span></span>  
  
#### <a name="to-add-an-artxp-time-series-mining-model"></a><span data-ttu-id="418c7-152">Per aggiungere un modello di data mining Time Series ARTXP</span><span class="sxs-lookup"><span data-stu-id="418c7-152">To add an ARTXP time series mining model</span></span>  
  
1.  <span data-ttu-id="418c7-153">Copiare il codice seguente in una finestra di query vuota.</span><span class="sxs-lookup"><span data-stu-id="418c7-153">Copy the following code into a blank query window.</span></span>  
  
     <span data-ttu-id="418c7-154">Si noti che non è necessario modificare alcun elemento, ad eccezione del nome del nuovo modello di data mining e del valore del parametro FORECAST_METHOD.</span><span class="sxs-lookup"><span data-stu-id="418c7-154">Note that you do not need to change anything except the name of the new mining model, and the value of the FORECAST_METHOD parameter.</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARTXP]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARTXP')  
    WITH DRILLTHROUGH  
    ```  
  
2.  <span data-ttu-id="418c7-155">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="418c7-155">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
3.  <span data-ttu-id="418c7-156">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Forecasting_ARTXP.dmx` .</span><span class="sxs-lookup"><span data-stu-id="418c7-156">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARTXP.dmx`.</span></span>  
  
4.  <span data-ttu-id="418c7-157">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="418c7-157">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="418c7-158">Nella lezione successiva verranno elaborati tutti i modelli e la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="418c7-158">In the next lesson, you will process all of the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="418c7-159">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="418c7-159">Next Lesson</span></span>  
 [<span data-ttu-id="418c7-160">Lezione 3: Elaborazione di strutture e modelli Time Series</span><span class="sxs-lookup"><span data-stu-id="418c7-160">Lesson 3: Processing the Time Series Structure and Models</span></span>](../../2014/tutorials/lesson-3-processing-the-time-series-structure-and-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="418c7-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="418c7-161">See Also</span></span>  
 <span data-ttu-id="418c7-162">[Algoritmo Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="418c7-162">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 [<span data-ttu-id="418c7-163">Riferimento tecnico per l'algoritmo Microsoft Time Series</span><span class="sxs-lookup"><span data-stu-id="418c7-163">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
