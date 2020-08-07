---
title: 'Lezione 3: elaborazione della struttura di data mining Bike Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e748c2cd-339d-4e82-82f1-be2d0fc41b61
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2e3f85016b32884b9a6b809e28d20d9985f97cd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719079"
---
# <a name="lesson-3-processing-the-bike-buyer-mining-structure"></a><span data-ttu-id="54d18-102">Lezione 3: Elaborazione della struttura di data mining Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="54d18-102">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="54d18-103">In questa lezione verrà utilizzata l'istruzione INSERT INTO e la vista vTargetMail del [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database di esempio per elaborare le strutture e i modelli di data mining creati nella [lezione 1: creazione della struttura di data mining Bike Buyer](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) e [lezione 2: aggiunta di modelli di data mining alla struttura di data mining Bike Buyer](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="54d18-103">In this lesson, you will use the INSERT INTO statement and the vTargetMail view from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) and [Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="54d18-104">Quando si elabora una struttura di data mining, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] legge i dati di origine e compila le strutture che supportano i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="54d18-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="54d18-105">Quando si elabora un modello di data mining, i dati definiti dalla struttura di data mining vengono elaborati tramite l'algoritmo di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="54d18-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you choose.</span></span> <span data-ttu-id="54d18-106">L'algoritmo ricerca tendenze e schemi e quindi archivia queste informazioni nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="54d18-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="54d18-107">Il modello di data mining non contiene pertanto i dati di origine effettivi, bensì le informazioni individuate dall'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="54d18-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="54d18-108">Per ulteriori informazioni sull'elaborazione dei modelli di data mining, vedere [requisiti e considerazioni sull'elaborazione &#40;&#41;di data mining ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="54d18-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="54d18-109">Una struttura di data mining deve essere rielaborata solo se si modifica una colonna della struttura o i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="54d18-109">You need to reprocess a mining structure only if you change a structure column or change the source data.</span></span> <span data-ttu-id="54d18-110">Se si aggiunge un modello di data mining a una struttura di data mining già elaborata, è possibile utilizzare l'istruzione INSERT INTO MINING MODEL per eseguire il training del nuovo modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="54d18-110">If you add a mining model to a mining structure that has already been processed, you can use the INSERT INTO MINING MODEL statement to train the new mining model.</span></span>  
  
## <a name="train-structure-template"></a><span data-ttu-id="54d18-111">Training del modello di struttura</span><span class="sxs-lookup"><span data-stu-id="54d18-111">Train Structure Template</span></span>  
 <span data-ttu-id="54d18-112">Per eseguire il training della struttura di data mining e dei modelli di data mining associati, utilizzare l'istruzione [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="54d18-112">In order to train the mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="54d18-113">Il codice nell'istruzione può essere suddiviso nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="54d18-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="54d18-114">Identificazione della struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="54d18-114">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="54d18-115">Creazione di un elenco delle colonne nella struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="54d18-115">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="54d18-116">Definizione dei dati di training</span><span class="sxs-lookup"><span data-stu-id="54d18-116">Defining the training data</span></span>  
  
 <span data-ttu-id="54d18-117">Di seguito è riportato un esempio generico dell'istruzione INSERT INTO:</span><span class="sxs-lookup"><span data-stu-id="54d18-117">The following is a generic example of the INSERT INTO statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="54d18-118">La prima riga del codice identifica la struttura di data mining di cui si eseguirà il training:</span><span class="sxs-lookup"><span data-stu-id="54d18-118">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="54d18-119">La riga successiva del codice specifica le colonne definite dalla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="54d18-119">The next line of the code specifies the columns that are defined by the mining structure.</span></span> <span data-ttu-id="54d18-120">È necessario che siano elencate tutte le colonne nella struttura di data mining e ogni colonna deve essere associata a una colonna nei dati della query di origine.</span><span class="sxs-lookup"><span data-stu-id="54d18-120">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="54d18-121">L'ultima riga del codice definisce i dati che verranno utilizzati per il training della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="54d18-121">The final line of the code defines the data that will be used to train the mining structure:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="54d18-122">In questa lezione si utilizzerà `OPENQUERY` per definire i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="54d18-122">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="54d18-123">Per informazioni su altri metodi di definizione della query di origine, vedere [&#60;query sui dati di origine&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="54d18-123">For information about other methods of defining the source query, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="54d18-124">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="54d18-124">Lesson Tasks</span></span>  
 <span data-ttu-id="54d18-125">In questa lezione verrà eseguita l'attività seguente:</span><span class="sxs-lookup"><span data-stu-id="54d18-125">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="54d18-126">Elaborazione della struttura di data mining Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="54d18-126">Process the Bike Buyer mining structure</span></span>  
  
## <a name="processing-the-predictive-mining-structure"></a><span data-ttu-id="54d18-127">Elaborazione della struttura di data mining predittiva</span><span class="sxs-lookup"><span data-stu-id="54d18-127">Processing the Predictive Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="54d18-128">Per elaborare la struttura di data mining mediante INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="54d18-128">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="54d18-129">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="54d18-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="54d18-130">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="54d18-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="54d18-131">Copiare l'esempio generico dell'istruzione INSERT INTO nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="54d18-131">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="54d18-132">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="54d18-132">Replace the following:</span></span>  
  
    ```  
    [<mining structure name>]   
    ```  
  
     <span data-ttu-id="54d18-133">con:</span><span class="sxs-lookup"><span data-stu-id="54d18-133">with:</span></span>  
  
    ```  
    Bike Buyer  
    ```  
  
4.  <span data-ttu-id="54d18-134">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="54d18-134">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="54d18-135">con:</span><span class="sxs-lookup"><span data-stu-id="54d18-135">with:</span></span>  
  
    ```  
    [Customer Key],  
    [Age],  
    [Bike Buyer],  
    [Commute Distance],  
    [Education],  
    [Gender],  
    [House Owner Flag],  
    [Marital Status],  
    [Number Cars Owned],  
    [Number Children At Home],  
    [Occupation],  
    [Region],  
    [Total Children],  
    [Yearly Income]  
    ```  
  
5.  <span data-ttu-id="54d18-136">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="54d18-136">Replace the following:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="54d18-137">con:</span><span class="sxs-lookup"><span data-stu-id="54d18-137">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
     <span data-ttu-id="54d18-138">L'istruzione OPENQUERY fa riferimento all'origine dati [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] per accedere alla vista vTargetMail</span><span class="sxs-lookup"><span data-stu-id="54d18-138">The OPENQUERY statement references the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source to access the view vTargetMail.</span></span> <span data-ttu-id="54d18-139">in cui sono contenuti i dati di origine che verranno utilizzati per il training dei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="54d18-139">The view contains the source data that will be used to train the mining models.</span></span>  
  
     <span data-ttu-id="54d18-140">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="54d18-140">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key],  
       [Age],  
       [Bike Buyer],  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]     
    )  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
6.  <span data-ttu-id="54d18-141">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="54d18-141">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="54d18-142">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Process Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="54d18-142">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Bike Buyer Structure.dmx`.</span></span>  
  
8.  <span data-ttu-id="54d18-143">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="54d18-143">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="54d18-144">Nella lezione successiva verrà esplorato il contenuto dei modelli di data mining aggiunti alla struttura di data mining in questa lezione.</span><span class="sxs-lookup"><span data-stu-id="54d18-144">In the next lesson, you will explore content in the mining models you added to the mining structure in this lesson.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="54d18-145">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="54d18-145">Next Lesson</span></span>  
 [<span data-ttu-id="54d18-146">Lezione 4: Esplorazione dei modelli di data mining Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="54d18-146">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>](../../2014/tutorials/lesson-4-browsing-the-bike-buyer-mining-models.md)  
  
  
