---
title: 'Lezione 1: creazione della struttura di data mining Market basket | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a817c8d1-aff4-42b4-b194-ad9cc1c60f35
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a6a6e123e525512a72d70bcc8ca2eba549d1347e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719098"
---
# <a name="lesson-1-creating-the-market-basket-mining-structure"></a><span data-ttu-id="7b37d-102">Lezione 1: Creazione della struttura di data mining Market Basket</span><span class="sxs-lookup"><span data-stu-id="7b37d-102">Lesson 1: Creating the Market Basket Mining Structure</span></span>
  <span data-ttu-id="7b37d-103">In questa lezione verrà creata una struttura di data mining che consente di stimare quali prodotti di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] un cliente tende ad acquistare contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="7b37d-103">In this lesson, you will create a mining structure that allows you to predict what [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] products a customer tends to purchase at the same time.</span></span> <span data-ttu-id="7b37d-104">Se non si ha familiarità con le strutture di data mining e il relativo ruolo in data mining, vedere strutture di data mining [&#40;Analysis Services di data mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="7b37d-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="7b37d-105">La struttura di data mining Association che verrà creata in questa lezione supporta l'aggiunta di modelli di data mining basati sull' [algoritmo Microsoft Association](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="7b37d-105">The association mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span></span> <span data-ttu-id="7b37d-106">Nelle lezioni successive si utilizzeranno i modelli di data mining per stimare il tipo di prodotti che un cliente tende ad acquistare contemporaneamente, ovvero per un'analisi di mercato sugli acquisti.</span><span class="sxs-lookup"><span data-stu-id="7b37d-106">In later lessons, you will use the mining models to predict the type of products a customer tends to purchase at the same time, which is called a market basket analysis.</span></span> <span data-ttu-id="7b37d-107">Ad esempio, è possibile individuare la tendenza ad acquistare contemporaneamente mountain bike, pneumatici per bicicletta e caschi.</span><span class="sxs-lookup"><span data-stu-id="7b37d-107">For example, you may find that customers tend to buy mountain bikes, bike tires, and helmets at the same time.</span></span>  
  
 <span data-ttu-id="7b37d-108">In questa lezione, la struttura di data mining viene definita utilizzando le tabelle nidificate.</span><span class="sxs-lookup"><span data-stu-id="7b37d-108">In this lesson, the mining structure is defined by using nested tables.</span></span> <span data-ttu-id="7b37d-109">L'utilizzo delle tabelle nidificate è determinato dal fatto che il dominio dei dati che verrà definito dalla struttura è contenuto in due diverse tabelle di origine.</span><span class="sxs-lookup"><span data-stu-id="7b37d-109">Nested tables are used because the data domain that will be defined by the structure is contained within two different source tables.</span></span> <span data-ttu-id="7b37d-110">Per ulteriori informazioni sulle tabelle nidificate, vedere [tabelle nidificate &#40;Analysis Services-&#41;di data mining ](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="7b37d-110">For more information on nested tables, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="7b37d-111">Istruzione CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="7b37d-111">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="7b37d-112">Per creare una struttura di data mining contenente una tabella nidificata, utilizzare l'istruzione [create mining structure &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="7b37d-112">In order to create a mining structure containing a nested table, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="7b37d-113">Il codice nell'istruzione può essere suddiviso nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b37d-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="7b37d-114">Denominazione della struttura</span><span class="sxs-lookup"><span data-stu-id="7b37d-114">Naming the structure</span></span>  
  
-   <span data-ttu-id="7b37d-115">Definizione della colonna chiave</span><span class="sxs-lookup"><span data-stu-id="7b37d-115">Defining the key column</span></span>  
  
-   <span data-ttu-id="7b37d-116">Definizione delle colonne di data mining</span><span class="sxs-lookup"><span data-stu-id="7b37d-116">Defining the mining columns</span></span>  
  
-   <span data-ttu-id="7b37d-117">Definizione delle colonne della tabella nidificata</span><span class="sxs-lookup"><span data-stu-id="7b37d-117">Defining the nested table columns</span></span>  
  
 <span data-ttu-id="7b37d-118">Di seguito è riportato un esempio generico dell'istruzione CREATE MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="7b37d-118">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<Mining Structure Name>]  
(  
   <key column>,  
   <mining structure columns>,  
   <table columns>  
   (  <nested key column>,  
      <nested mining structure columns> )  
)  
  
```  
  
 <span data-ttu-id="7b37d-119">La prima riga del codice definisce il nome della struttura:</span><span class="sxs-lookup"><span data-stu-id="7b37d-119">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [Mining Structure Name]  
```  
  
 <span data-ttu-id="7b37d-120">Per informazioni sulla denominazione di un oggetto in DMX, vedere [identificatori &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="7b37d-120">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="7b37d-121">La riga successiva del codice definisce la colonna chiave per la struttura di data mining, che identifica in modo univoco un'entità nei dati di origine:</span><span class="sxs-lookup"><span data-stu-id="7b37d-121">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>  
```  
  
 <span data-ttu-id="7b37d-122">La riga successiva del codice è utilizzata per definire le colonne di data mining che verranno utilizzate dai modelli di data mining associati alla struttura di data mining:</span><span class="sxs-lookup"><span data-stu-id="7b37d-122">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="7b37d-123">Le righe successive del codice definiscono le colonne delle tabelle nidificate:</span><span class="sxs-lookup"><span data-stu-id="7b37d-123">The next lines of the code define the nested table columns:</span></span>  
  
```  
<table columns>  
(  <nested key column>,  
   <nested mining structure columns> )  
```  
  
 <span data-ttu-id="7b37d-124">Per informazioni sui tipi di colonne della struttura di data mining che è possibile definire, vedere [colonne della struttura di data mining](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="7b37d-124">For information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b37d-125">Per impostazione predefinita, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] crea un set di dati di controllo del 30% per ogni struttura di data mining; tuttavia, quando si utilizza DMX per creare una struttura di data mining, è necessario aggiungere manualmente il set di dati di controllo, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="7b37d-125">By default, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates a 30 percent holdout data set for each mining structure; however, when you use DMX to create a mining structure, you must manually add the holdout data set, if desired.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="7b37d-126">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="7b37d-126">Lesson Tasks</span></span>  
 <span data-ttu-id="7b37d-127">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b37d-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="7b37d-128">Creazione di una nuova query vuota</span><span class="sxs-lookup"><span data-stu-id="7b37d-128">Create a new blank query</span></span>  
  
-   <span data-ttu-id="7b37d-129">Modifica della query per creare la struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="7b37d-129">Alter the query to create the mining structure</span></span>  
  
-   <span data-ttu-id="7b37d-130">Eseguire la query</span><span class="sxs-lookup"><span data-stu-id="7b37d-130">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="7b37d-131">Creazione della query</span><span class="sxs-lookup"><span data-stu-id="7b37d-131">Creating the Query</span></span>  
 <span data-ttu-id="7b37d-132">Il primo passaggio consiste nella connessione a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e nella creazione di una nuova query DMX in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b37d-132">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="7b37d-133">Per creare una nuova query DMX in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b37d-133">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="7b37d-134">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b37d-134">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="7b37d-135">Nella finestra di dialogo **Connetti al server** selezionare **Analysis Services**per **tipo di server**.</span><span class="sxs-lookup"><span data-stu-id="7b37d-135">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="7b37d-136">In **nome server**, digitare `LocalHost` o il nome dell'istanza di a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cui si desidera connettersi per questa lezione.</span><span class="sxs-lookup"><span data-stu-id="7b37d-136">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="7b37d-137">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="7b37d-137">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="7b37d-138">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="7b37d-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="7b37d-139">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="7b37d-139">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="7b37d-140">Modifica della query</span><span class="sxs-lookup"><span data-stu-id="7b37d-140">Altering the Query</span></span>  
 <span data-ttu-id="7b37d-141">Il passaggio successivo consiste nella modifica dell'istruzione CREATE MINING STRUCTURE descritta in precedenza per creare la struttura di data mining Market Basket.</span><span class="sxs-lookup"><span data-stu-id="7b37d-141">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Market Basket mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="7b37d-142">Per personalizzare l'istruzione CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="7b37d-142">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="7b37d-143">Nell'editor di query copiare l'esempio generico dell'istruzione CREATE MINING STRUCTURE nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="7b37d-143">In Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="7b37d-144">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7b37d-144">Replace the following:</span></span>  
  
    ```  
    [mining structure name]   
    ```  
  
     <span data-ttu-id="7b37d-145">con:</span><span class="sxs-lookup"><span data-stu-id="7b37d-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
3.  <span data-ttu-id="7b37d-146">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7b37d-146">Replace the following:</span></span>  
  
    ```  
    <key column>  
    ```  
  
     <span data-ttu-id="7b37d-147">con:</span><span class="sxs-lookup"><span data-stu-id="7b37d-147">with:</span></span>  
  
    ```  
    OrderNumber TEXT KEY  
    ```  
  
4.  <span data-ttu-id="7b37d-148">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7b37d-148">Replace the following:</span></span>  
  
    ```  
    <table columns>  
    (  <nested key column>,  
       <nested mining structure columns> )  
    ```  
  
     <span data-ttu-id="7b37d-149">con:</span><span class="sxs-lookup"><span data-stu-id="7b37d-149">with:</span></span>  
  
    ```  
    [Products] TABLE (  
        [Model] TEXT KEY  
    )  
    ```  
  
     <span data-ttu-id="7b37d-150">Il linguaggio TEXT KEY specifica che la colonna Model è la colonna chiave per la tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="7b37d-150">The TEXT KEY language specifies that the Model column is the key column for the nested table.</span></span>  
  
     <span data-ttu-id="7b37d-151">L'istruzione della struttura di data mining completa dovrebbe essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="7b37d-151">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Market Basket] (  
        OrderNumber TEXT KEY,  
        [Products] TABLE (  
            [Model] TEXT KEY  
        )  
    )  
    ```  
  
5.  <span data-ttu-id="7b37d-152">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="7b37d-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="7b37d-153">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Market Basket Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="7b37d-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Market Basket Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="7b37d-154">Esecuzione della query</span><span class="sxs-lookup"><span data-stu-id="7b37d-154">Executing the Query</span></span>  
 <span data-ttu-id="7b37d-155">Il passaggio conclusivo consiste nell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="7b37d-155">The final step is to execute the query.</span></span> <span data-ttu-id="7b37d-156">Dopo la creazione e il salvataggio di una query, per creare la struttura di data mining sul server è necessario che la query (l'istruzione) venga eseguita.</span><span class="sxs-lookup"><span data-stu-id="7b37d-156">After a query is created and saved, it needs to be executed (that is, the statement needs to be run) in order to create the mining structure on the server.</span></span> <span data-ttu-id="7b37d-157">Per ulteriori informazioni sull'esecuzione di query nell'editor di query, vedere [motore di database editor di query &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7b37d-157">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="7b37d-158">Per eseguire la query</span><span class="sxs-lookup"><span data-stu-id="7b37d-158">To execute the query</span></span>  
  
-   <span data-ttu-id="7b37d-159">Nell'editor di query fare clic su **Esegui**sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="7b37d-159">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="7b37d-160">Lo stato della query viene visualizzato nella scheda **messaggi** nella parte inferiore dell'editor di query al termine dell'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="7b37d-160">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="7b37d-161">Dovrebbero essere visualizzati i messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b37d-161">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="7b37d-162">Nel server esiste già una nuova struttura denominata **Market basket** .</span><span class="sxs-lookup"><span data-stu-id="7b37d-162">A new structure named **Market Basket** now exists on the server.</span></span>  
  
 <span data-ttu-id="7b37d-163">Nella lezione successiva verranno aggiunti modelli di data mining alla struttura di data mining Market Basket appena creata.</span><span class="sxs-lookup"><span data-stu-id="7b37d-163">In the next lesson, you will add mining models to the Market Basket mining structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="7b37d-164">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="7b37d-164">Next Lesson</span></span>  
 [<span data-ttu-id="7b37d-165">Lezione 2: Aggiunta di modelli di data mining alla struttura di data mining Market Basket</span><span class="sxs-lookup"><span data-stu-id="7b37d-165">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)  
  
  
