---
title: 'Lezione 3: elaborazione della struttura di data mining Market basket | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095a043f-cf6f-45bb-a021-ae4e1b535c65
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ce2c2e6944d524a38edc331d2cd128ca7cf7d419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711199"
---
# <a name="lesson-3-processing-the-market-basket-mining-structure"></a><span data-ttu-id="59190-102">Lezione 3: Elaborazione della struttura di data mining Market Basket</span><span class="sxs-lookup"><span data-stu-id="59190-102">Lesson 3: Processing the Market Basket Mining Structure</span></span>
  <span data-ttu-id="59190-103">In questa lezione verrà utilizzata l'istruzione [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) e VAssocSeqLineItems e vAssocSeqOrders dal [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database di esempio per elaborare le strutture e i modelli di data mining creati nella [lezione 1: creazione della struttura di data mining Market basket](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) e [lezione 2: aggiunta di modelli di data mining alla struttura di data mining Market basket](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="59190-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement and the vAssocSeqLineItems and vAssocSeqOrders from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) and [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span>  
  
 <span data-ttu-id="59190-104">Quando si elabora una struttura di data mining, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] legge i dati di origine e compila le strutture che supportano i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="59190-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="59190-105">Quando si elabora un modello di data mining, i dati definiti dalla struttura di data mining vengono elaborati tramite l'algoritmo di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="59190-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you chose.</span></span> <span data-ttu-id="59190-106">L'algoritmo ricerca tendenze e schemi e quindi archivia queste informazioni nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="59190-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="59190-107">Il modello di data mining non contiene pertanto i dati di origine effettivi, bensì le informazioni individuate dall'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="59190-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="59190-108">Per ulteriori informazioni sull'elaborazione dei modelli di data mining, vedere [requisiti e considerazioni sull'elaborazione &#40;&#41;di data mining ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="59190-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="59190-109">Una struttura di data mining deve essere rielaborata solo se si modifica una colonna della struttura o i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="59190-109">You only have to reprocess a mining structure if you change a structure column or change the source data.</span></span> <span data-ttu-id="59190-110">Se si aggiunge un modello di data mining a una struttura di data mining già elaborata, è possibile utilizzare l'istruzione `INSERT INTO MINING MODEL` per eseguire il training del nuovo modello di data mining sui dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="59190-110">If you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to train the new mining model on the existing data.</span></span>  
  
 <span data-ttu-id="59190-111">Dato che la struttura di data mining per l'analisi degli acquisti contiene una tabella nidificata, sarà necessario definire le colonne di data mining di cui eseguire il training utilizzando la struttura di tabelle nidificate e utilizzare il comando `SHAPE` per definire le query che eseguono il pull dei dati di training dalle tabelle di origine.</span><span class="sxs-lookup"><span data-stu-id="59190-111">Because the Market Basket mining structure contains a nested table, you will have to define the mining columns to be trained using the nested table structure, and use the `SHAPE` command to define the queries that pull the training data from the source tables.</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="59190-112">Istruzione INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="59190-112">INSERT INTO Statement</span></span>  
 <span data-ttu-id="59190-113">Per eseguire il training della struttura di data mining Market basket e dei modelli di data mining associati, utilizzare l'istruzione [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="59190-113">In order to train the Market Basket mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="59190-114">Il codice nell'istruzione può essere suddiviso nelle parti seguenti.</span><span class="sxs-lookup"><span data-stu-id="59190-114">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="59190-115">Identificazione della struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="59190-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="59190-116">Creazione di un elenco delle colonne nella struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="59190-116">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="59190-117">Definizione dei dati di training mediante il comando `SHAPE`</span><span class="sxs-lookup"><span data-stu-id="59190-117">Defining the training data using `SHAPE`</span></span>  
  
 <span data-ttu-id="59190-118">Di seguito è riportato un esempio generico di istruzione `INSERT INTO`:</span><span class="sxs-lookup"><span data-stu-id="59190-118">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],'<nested SELECT statement>')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="59190-119">La prima riga del codice identifica la struttura di data mining di cui si eseguirà il training:</span><span class="sxs-lookup"><span data-stu-id="59190-119">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="59190-120">Le successive righe del codice specificano le colonne definite dalla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="59190-120">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="59190-121">È necessario che siano elencate tutte le colonne nella struttura di data mining e ogni colonna deve essere associata a una colonna nei dati della query di origine.</span><span class="sxs-lookup"><span data-stu-id="59190-121">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span> <span data-ttu-id="59190-122">È possibile utilizzare `SKIP` per ignorare le colonne presenti nei dati di origine, ma non nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="59190-122">You can use `SKIP` to ignore columns that exist in the source data but do not exist in the mining structure.</span></span> <span data-ttu-id="59190-123">Per ulteriori informazioni sull'utilizzo di `SKIP` , vedere [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span><span class="sxs-lookup"><span data-stu-id="59190-123">For more information about how to use `SKIP`, see [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span></span>  
  
```  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
```  
  
 <span data-ttu-id="59190-124">Le ultime righe del codice definiscono i dati che verranno utilizzati per il training della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="59190-124">The final lines of the code define the data that will be used to train the mining structure.</span></span> <span data-ttu-id="59190-125">Dal momento che i dati di origine sono presenti in due tabelle, si utilizzerà `SHAPE` per correlare le tabelle.</span><span class="sxs-lookup"><span data-stu-id="59190-125">Because the source data is contained within two tables, you will use `SHAPE` to relate the tables.</span></span>  
  
```  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],''<nested SELECT statement>'')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="59190-126">In questa lezione si utilizzerà `OPENQUERY` per definire i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="59190-126">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="59190-127">Per informazioni su altri metodi di definizione di una query sui dati di origine, vedere [&#60;query sui dati di origine&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="59190-127">For information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="59190-128">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="59190-128">Lesson Tasks</span></span>  
 <span data-ttu-id="59190-129">In questa lezione verrà eseguita l'attività seguente:</span><span class="sxs-lookup"><span data-stu-id="59190-129">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="59190-130">Elaborazione della struttura di data mining Market Basket</span><span class="sxs-lookup"><span data-stu-id="59190-130">Process the Market Basket mining structure</span></span>  
  
## <a name="processing-the-market-basket-mining-structure"></a><span data-ttu-id="59190-131">Elaborazione della struttura di data mining Market Basket</span><span class="sxs-lookup"><span data-stu-id="59190-131">Processing the Market Basket Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="59190-132">Per elaborare la struttura di data mining mediante INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="59190-132">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="59190-133">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="59190-133">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="59190-134">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="59190-134">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="59190-135">Copiare l'esempio generico dell'istruzione INSERT INTO nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="59190-135">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="59190-136">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="59190-136">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="59190-137">con:</span><span class="sxs-lookup"><span data-stu-id="59190-137">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="59190-138">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="59190-138">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    [<nested table>]  
    ( SKIP, <skipped column> )  
    ```  
  
     <span data-ttu-id="59190-139">con:</span><span class="sxs-lookup"><span data-stu-id="59190-139">with:</span></span>  
  
    ```  
    [OrderNumber],  
    [Products]   
    (SKIP, [Model])  
    ```  
  
     <span data-ttu-id="59190-140">Nell'istruzione, `Products` si riferisce alla tabella Products definita dall'istruzione SHAPE.</span><span class="sxs-lookup"><span data-stu-id="59190-140">In the statement, `Products` refers to the Products table defined by the SHAPE statement.</span></span> <span data-ttu-id="59190-141">`SKIP` viene utilizzato per ignorare la colonna Model che esiste nei dati di origine come chiave ma non viene utilizzata dalla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="59190-141">`SKIP` is used to ignore the Model column, which exists in the source data as a key, but is not used by the mining structure.</span></span>  
  
5.  <span data-ttu-id="59190-142">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="59190-142">Replace the following:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([<datasource>],'<SELECT statement>') }  
    APPEND  
    (   
      {OPENQUERY([<datasource>],'<nested SELECT statement>')  
    }  
    RELATE [<case key>] TO [<foreign key>]  
    ) AS [<nested table>]  
    ```  
  
     <span data-ttu-id="59190-143">con:</span><span class="sxs-lookup"><span data-stu-id="59190-143">with:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
     <span data-ttu-id="59190-144">La query di origine fa riferimento all' [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] origine dati definita nel [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] progetto di esempio.</span><span class="sxs-lookup"><span data-stu-id="59190-144">The source query references the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample project.</span></span> <span data-ttu-id="59190-145">Utilizza questa origine dei dati per accedere alle viste vAssocSeqLineItems e vAssocSeqOrders</span><span class="sxs-lookup"><span data-stu-id="59190-145">It uses this data source to access the vAssocSeqLineItems and vAssocSeqOrders views.</span></span> <span data-ttu-id="59190-146">contenenti i dati origine che verranno utilizzati per il training del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="59190-146">These views contain the source data that will be used to train the mining model.</span></span> <span data-ttu-id="59190-147">Se il progetto non è stato creato o queste visualizzazioni, vedere [esercitazione di base sul data mining](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="59190-147">If you have not created this project or these views, see [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="59190-148">All'interno del comando `SHAPE` si utilizzerà `OPENQUERY` per definire due query.</span><span class="sxs-lookup"><span data-stu-id="59190-148">Within the `SHAPE` command, you will use `OPENQUERY` to define two queries.</span></span> <span data-ttu-id="59190-149">Nella prima query viene definita la tabella padre, mentre nella seconda viene definita la tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="59190-149">The first query defines the parent table, and the second query defines the nested table.</span></span> <span data-ttu-id="59190-150">Le due tabelle vengono correlate mediante la colonna OrderNumber presente in entrambe.</span><span class="sxs-lookup"><span data-stu-id="59190-150">The two tables are related using the OrderNumber column, which exists in both tables.</span></span>  
  
     <span data-ttu-id="59190-151">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="59190-151">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Market Basket]  
    (  
       [OrderNumber],[Products] (SKIP, [Model])  
    )  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
6.  <span data-ttu-id="59190-152">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="59190-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="59190-153">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Process Market Basket.dmx` .</span><span class="sxs-lookup"><span data-stu-id="59190-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Market Basket.dmx`.</span></span>  
  
8.  <span data-ttu-id="59190-154">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="59190-154">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="59190-155">Una volta terminata l'esecuzione della query, è possibile visualizzare i modelli e i set di elementi trovati, visualizzare le associazioni o filtrare per set di elementi, probabilità o importanza.</span><span class="sxs-lookup"><span data-stu-id="59190-155">After the query has finished running, you can view the patterns and itemsets that were found, view associations, or filter by itemset, probability, or importance.</span></span> <span data-ttu-id="59190-156">Per visualizzare queste informazioni, in fare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] clic con il pulsante destro del mouse sul nome del modello di dati, quindi scegliere **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="59190-156">To view this information, in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click the name of the data model, and then click **Browse**.</span></span>  
  
 <span data-ttu-id="59190-157">Nella lezione successiva verranno create diverse stime basate sui modelli di data mining aggiunti alla struttura Market Basket.</span><span class="sxs-lookup"><span data-stu-id="59190-157">In the next lesson, you will create several predictions based on the mining models that you added to the Market Basket structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="59190-158">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="59190-158">Next Lesson</span></span>  
 [<span data-ttu-id="59190-159">Lezione 4: Esecuzione delle stime relative a Market Basket</span><span class="sxs-lookup"><span data-stu-id="59190-159">Lesson 4: Executing Market Basket Predictions</span></span>](../../2014/tutorials/lesson-4-executing-market-basket-predictions.md)  
  
  
