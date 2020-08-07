---
title: 'Lezione 1: creazione della struttura di data mining Bike Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a73ac60b-660f-458a-bd2f-993fbeba7226
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d6384910858d87a80aa3c8f897bc88e45f4504fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719097"
---
# <a name="lesson-1-creating-the-bike-buyer-mining-structure"></a><span data-ttu-id="f9c29-102">Lezione 1: Creazione della struttura di data mining Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="f9c29-102">Lesson 1: Creating the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="f9c29-103">In questa lezione verrà creata una struttura di data mining che consente di stimare se un potenziale cliente di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] acquisterà una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="f9c29-103">In this lesson, you will create a mining structure that allows you to predict whether a potential customer of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] will purchase a bicycle.</span></span> <span data-ttu-id="f9c29-104">Se non si ha familiarità con le strutture di data mining e il relativo ruolo in data mining, vedere strutture di data mining [&#40;Analysis Services di data mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f9c29-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="f9c29-105">La struttura di data mining Bike Buyer che verrà creata in questa lezione supporta l'aggiunta di modelli di data mining basati sull'algoritmo Microsoft [clustering algoritmo](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)[Microsoft Decision Trees](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="f9c29-105">The Bike Buyer mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)[Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="f9c29-106">Nelle lezioni successive si utilizzeranno i modelli di data mining di clustering per esaminare le diverse modalità di raggruppamento dei clienti e si utilizzeranno modelli di data mining di albero delle decisioni per stimare se un potenziale cliente acquisterà una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="f9c29-106">In later lessons, you will use the clustering mining models to explore the different ways in which customers can be grouped, and will use decision tree mining models to predict whether or not a potential customer will purchase a bicycle.</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="f9c29-107">Istruzione CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="f9c29-107">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="f9c29-108">Per creare una struttura di data mining, è possibile utilizzare l'istruzione [create mining structure &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="f9c29-108">To create a mining structure, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="f9c29-109">Il codice nell'istruzione può essere suddiviso nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9c29-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="f9c29-110">Denominazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="f9c29-110">Naming the structure.</span></span>  
  
-   <span data-ttu-id="f9c29-111">Definizione della colonna chiave.</span><span class="sxs-lookup"><span data-stu-id="f9c29-111">Defining the key column.</span></span>  
  
-   <span data-ttu-id="f9c29-112">Definizione delle colonne di data mining.</span><span class="sxs-lookup"><span data-stu-id="f9c29-112">Defining the mining columns.</span></span>  
  
-   <span data-ttu-id="f9c29-113">Definizione di un set di dati di testing facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f9c29-113">Defining an optional testing data set.</span></span>  
  
 <span data-ttu-id="f9c29-114">Di seguito è riportato un esempio generico dell'istruzione CREATE MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="f9c29-114">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
(  
    <key column>,  
    <mining structure columns>  
)   
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="f9c29-115">La prima riga del codice definisce il nome della struttura:</span><span class="sxs-lookup"><span data-stu-id="f9c29-115">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="f9c29-116">Per informazioni sulla denominazione di un oggetto in DMX (Data Mining Extensions), vedere [identificatori &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="f9c29-116">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="f9c29-117">La riga successiva del codice definisce la colonna chiave per la struttura di data mining, che identifica in modo univoco un'entità nei dati di origine:</span><span class="sxs-lookup"><span data-stu-id="f9c29-117">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>,  
```  
  
 <span data-ttu-id="f9c29-118">In questa struttura di data mining creata, l'identificatore del cliente, `CustomerKey`, definisce un'entità nei dati di origine.</span><span class="sxs-lookup"><span data-stu-id="f9c29-118">In the mining structure you will create, the customer identifier, `CustomerKey`, defines an entity in the source data.</span></span>  
  
 <span data-ttu-id="f9c29-119">La riga successiva del codice è utilizzata per definire le colonne di data mining che verranno utilizzate dai modelli di data mining associati alla struttura di data mining:</span><span class="sxs-lookup"><span data-stu-id="f9c29-119">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="f9c29-120">È possibile usare la funzione DISCRETIZZARE in \<mining structure columns> per discretizzare colonne continue usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f9c29-120">You can use the DISCRETIZE function within \<mining structure columns> to discretize continuous columns by using the following syntax:</span></span>  
  
 `DISCRETIZE(<method>,<number of buckets>)`  
  
 <span data-ttu-id="f9c29-121">Per ulteriori informazioni sulle colonne discretizzazione, vedere [metodi di discretizzazione &#40;&#41;di data mining ](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f9c29-121">For more information about discretizing columns, see [Discretization Methods &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span></span> <span data-ttu-id="f9c29-122">Per ulteriori informazioni sui tipi di colonne della struttura di data mining che è possibile definire, vedere [colonne della struttura di data mining](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="f9c29-122">For more information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
 <span data-ttu-id="f9c29-123">L'ultima riga del codice definisce una partizione facoltativa nella struttura di data mining:</span><span class="sxs-lookup"><span data-stu-id="f9c29-123">The final line of the code defines an optional partition in the mining structure:</span></span>  
  
```  
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="f9c29-124">Specificare alcuni dati da utilizzare per testare i modelli di data mining correlati alla struttura e i rimanenti dati da utilizzare per il training dei modelli.</span><span class="sxs-lookup"><span data-stu-id="f9c29-124">You specify some portion of the data to use for testing mining models that are related to the structure, and the remaining data is used for training the models.</span></span> <span data-ttu-id="f9c29-125">Per impostazione predefinita, in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] viene creato un set di dati di test che contiene il 30% di tutti i dati dei case.</span><span class="sxs-lookup"><span data-stu-id="f9c29-125">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates a test data set that contains 30 percent of all case data.</span></span> <span data-ttu-id="f9c29-126">È necessario aggiungere la specifica che i set di dati di test devono contenere il 30% dei case fino a un massimo di 1000 case.</span><span class="sxs-lookup"><span data-stu-id="f9c29-126">You will add the specification that the test data set should contain 30 percent of the cases up to a maximum of 1000 cases.</span></span> <span data-ttu-id="f9c29-127">Se il 30% dei case è minore di 1000, il set di dati di test conterrà la quantità inferiore.</span><span class="sxs-lookup"><span data-stu-id="f9c29-127">If 30 percent of the cases is less than 1000, the test data set will contain the smaller amount.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="f9c29-128">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="f9c29-128">Lesson Tasks</span></span>  
 <span data-ttu-id="f9c29-129">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9c29-129">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="f9c29-130">Creazione di una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="f9c29-130">Create a new blank query.</span></span>  
  
-   <span data-ttu-id="f9c29-131">Modifica della query per creare la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="f9c29-131">Alter the query to create the mining structure.</span></span>  
  
-   <span data-ttu-id="f9c29-132">Esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="f9c29-132">Execute the query.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="f9c29-133">Creazione della query</span><span class="sxs-lookup"><span data-stu-id="f9c29-133">Creating the Query</span></span>  
 <span data-ttu-id="f9c29-134">Il primo passaggio consiste nella connessione a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e nella creazione di una nuova query DMX in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9c29-134">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="f9c29-135">Per creare una nuova query DMX in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9c29-135">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="f9c29-136">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9c29-136">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="f9c29-137">Nella finestra di dialogo **Connetti al server** selezionare **Analysis Services**per **tipo di server**.</span><span class="sxs-lookup"><span data-stu-id="f9c29-137">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="f9c29-138">In **nome server**Digitare `LocalHost` o digitare il nome dell'istanza di a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cui si desidera connettersi per questa lezione.</span><span class="sxs-lookup"><span data-stu-id="f9c29-138">In **Server name**, type `LocalHost`, or type the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="f9c29-139">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="f9c29-139">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="f9c29-140">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX** per aprire l' **editor di query** e una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="f9c29-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the **Query Editor** and a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="f9c29-141">Modifica della query</span><span class="sxs-lookup"><span data-stu-id="f9c29-141">Altering the Query</span></span>  
 <span data-ttu-id="f9c29-142">Il passaggio successivo consiste nella modifica dell'istruzione CREATE MINING STRUCTURE descritta in precedenza per creare la struttura di data mining Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="f9c29-142">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Bike Buyer mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="f9c29-143">Per personalizzare l'istruzione CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="f9c29-143">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="f9c29-144">Nell'editor di query copiare l'esempio generico dell'istruzione CREATE MINING STRUCTURE nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="f9c29-144">In the Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="f9c29-145">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9c29-145">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]   
    ```  
  
     <span data-ttu-id="f9c29-146">con:</span><span class="sxs-lookup"><span data-stu-id="f9c29-146">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
3.  <span data-ttu-id="f9c29-147">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9c29-147">Replace the following:</span></span>  
  
    ```  
    <key column>   
    ```  
  
     <span data-ttu-id="f9c29-148">con:</span><span class="sxs-lookup"><span data-stu-id="f9c29-148">with:</span></span>  
  
    ```  
    CustomerKey LONG KEY  
    ```  
  
4.  <span data-ttu-id="f9c29-149">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9c29-149">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>   
    ```  
  
     <span data-ttu-id="f9c29-150">con:</span><span class="sxs-lookup"><span data-stu-id="f9c29-150">with:</span></span>  
  
    ```  
    [Age] LONG DISCRETIZED(Automatic,10),  
    [Bike Buyer] LONG DISCRETE,  
    [Commute Distance] TEXT DISCRETE,  
    [Education] TEXT DISCRETE,  
    [Gender] TEXT DISCRETE,  
    [House Owner Flag] TEXT DISCRETE,  
    [Marital Status] TEXT DISCRETE,  
    [Number Cars Owned] LONG DISCRETE,  
    [Number Children At Home] LONG DISCRETE,  
    [Occupation] TEXT DISCRETE,  
    [Region] TEXT DISCRETE,  
    [Total Children]LONG DISCRETE,  
    [Yearly Income] DOUBLE CONTINUOUS  
    ```  
  
5.  <span data-ttu-id="f9c29-151">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9c29-151">Replace the following:</span></span>  
  
    ```  
    WITH HOLDOUT (holdout specifier>)  
    ```  
  
     <span data-ttu-id="f9c29-152">con:</span><span class="sxs-lookup"><span data-stu-id="f9c29-152">with:</span></span>  
  
    ```  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
    ```  
  
     <span data-ttu-id="f9c29-153">L'istruzione della struttura di data mining completa dovrebbe essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="f9c29-153">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key] LONG KEY,  
       [Age]LONG DISCRETIZED(Automatic,10),  
       [Bike Buyer] LONG DISCRETE,  
       [Commute Distance] TEXT DISCRETE,  
       [Education] TEXT DISCRETE,  
       [Gender] TEXT DISCRETE,  
       [House Owner Flag] TEXT DISCRETE,  
       [Marital Status] TEXT DISCRETE,  
       [Number Cars Owned]LONG DISCRETE,  
       [Number Children At Home]LONG DISCRETE,  
       [Occupation] TEXT DISCRETE,  
       [Region] TEXT DISCRETE,  
       [Total Children]LONG DISCRETE,  
       [Yearly Income] DOUBLE CONTINUOUS  
    )  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
  
    ```  
  
6.  <span data-ttu-id="f9c29-154">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="f9c29-154">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="f9c29-155">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="f9c29-155">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Bike Buyer Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="f9c29-156">Esecuzione della query</span><span class="sxs-lookup"><span data-stu-id="f9c29-156">Executing the Query</span></span>  
 <span data-ttu-id="f9c29-157">Il passaggio conclusivo consiste nell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="f9c29-157">The final step is to execute the query.</span></span> <span data-ttu-id="f9c29-158">Dopo la creazione e il salvataggio di una query, è necessario eseguirla.</span><span class="sxs-lookup"><span data-stu-id="f9c29-158">After a query is created and saved, it needs to be executed.</span></span> <span data-ttu-id="f9c29-159">Ovvero, l'istruzione deve essere eseguita per creare la struttura di data mining nel server.</span><span class="sxs-lookup"><span data-stu-id="f9c29-159">That is, the statement needs to be run in order to create the mining structure on the server.</span></span> <span data-ttu-id="f9c29-160">Per ulteriori informazioni sull'esecuzione di query nell'editor di query, vedere [motore di database editor di query &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="f9c29-160">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="f9c29-161">Per eseguire la query</span><span class="sxs-lookup"><span data-stu-id="f9c29-161">To execute the query</span></span>  
  
1.  <span data-ttu-id="f9c29-162">Nell'editor di query fare clic su **Esegui**sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="f9c29-162">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="f9c29-163">Lo stato della query viene visualizzato nella scheda **messaggi** nella parte inferiore dell'editor di query al termine dell'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="f9c29-163">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="f9c29-164">Dovrebbero essere visualizzati i messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9c29-164">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="f9c29-165">Nel server è presente una nuova struttura denominata **Bike Buyer** .</span><span class="sxs-lookup"><span data-stu-id="f9c29-165">A new structure named **Bike Buyer** now exists on the server.</span></span>  
  
 <span data-ttu-id="f9c29-166">Nella lezione successiva verranno aggiunti modelli di data mining alla struttura appena creata.</span><span class="sxs-lookup"><span data-stu-id="f9c29-166">In the next lesson, you will add mining models to the structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="f9c29-167">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="f9c29-167">Next Lesson</span></span>  
 [<span data-ttu-id="f9c29-168">Lezione 2: Aggiunta di modelli di data mining alla struttura di data mining Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="f9c29-168">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md)  
  
  
