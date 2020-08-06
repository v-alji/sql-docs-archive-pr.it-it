---
title: 'Passaggio 6: Aggiunta e configurazione delle trasformazioni Ricerca | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c59f723-9707-4407-80ae-f05f483cf65f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96b0a848508c19eb24cf1538244a39fcec57361a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628832"
---
# <a name="step-6-adding-and-configuring-the-lookup-transformations"></a><span data-ttu-id="c2d79-102">Passaggio 6: Aggiunta e configurazione delle trasformazioni Ricerca</span><span class="sxs-lookup"><span data-stu-id="c2d79-102">Step 6: Adding and Configuring the Lookup Transformations</span></span>
  <span data-ttu-id="c2d79-103">Dopo aver configurato l'origine file flat per l'estrazione di dati dal file di origine si definiranno le trasformazioni Ricerca necessarie per ottenere i valori di **CurrencyKey** e **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-103">After you have configured the Flat File source to extract data from the source file, the next task is to define the Lookup transformations needed to obtain the values for the **CurrencyKey** and **DateKey**.</span></span> <span data-ttu-id="c2d79-104">Una trasformazione Ricerca esegue una ricerca tramite l'unione in join dei dati della colonna di input specificata con una colonna di un set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2d79-104">A Lookup transformation performs a lookup by joining data in the specified input column to a column in a reference dataset.</span></span> <span data-ttu-id="c2d79-105">Il set di dati di riferimento può essere una vista o tabella esistente, una nuova tabella o il risultato di un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="c2d79-105">The reference dataset can be an existing table or view, a new table, or the result of an SQL statement.</span></span> <span data-ttu-id="c2d79-106">In questa esercitazione, la trasformazione Ricerca utilizza una gestione connessione OLE DB per connettersi al database che contiene i dati che costituiscono l'origine del set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2d79-106">In this tutorial, the Lookup transformation uses an OLE DB connection manager to connect to the database that contains the data that is the source of the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2d79-107">È anche possibile configurare la trasformazione Ricerca per collegarsi a una cache che contiene il set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2d79-107">You can also configure the Lookup transformation to connect to a cache that contains the reference dataset.</span></span> <span data-ttu-id="c2d79-108">Per altre informazioni, vedere [Trasformazione Ricerca](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c2d79-108">For more information, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="c2d79-109">In questa esercitazione verranno aggiunti al pacchetto e configurati i due componenti di trasformazione Ricerca seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2d79-109">For this tutorial, you will add and configure the following two Lookup transformation components to the package:</span></span>  
  
-   <span data-ttu-id="c2d79-110">Una trasformazione per eseguire la ricerca di valori della colonna **CurrencyKey** della tabella delle dimensioni **DimCurrency** in base alla corrispondenza con i valori della colonna **CurrencyID** del file flat.</span><span class="sxs-lookup"><span data-stu-id="c2d79-110">One transformation to perform a lookup of values from the **CurrencyKey** column of the **DimCurrency** dimension table based on matching **CurrencyID** column values from the flat file.</span></span>  
  
-   <span data-ttu-id="c2d79-111">Una trasformazione per eseguire una ricerca di valori della colonna **DateKey** della tabella delle dimensioni **DimDate** in base alla corrispondenza con i valori della colonna **CurrencyDate** del file flat.</span><span class="sxs-lookup"><span data-stu-id="c2d79-111">One transformation to perform a lookup of values from the **DateKey** column of the **DimDate** dimension table based on matching **CurrencyDate** column values from the flat file.</span></span>  
  
 <span data-ttu-id="c2d79-112">In entrambi i casi nella trasformazione Ricerca verrà utilizzata la gestione connessione OLE DB creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c2d79-112">In both cases, the Lookup transformation will utilize the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-lookup-currency-key-transformation"></a><span data-ttu-id="c2d79-113">Per aggiungere e configurare la trasformazione Lookup Currency Key</span><span class="sxs-lookup"><span data-stu-id="c2d79-113">To add and configure the Lookup Currency Key transformation</span></span>  
  
1.  <span data-ttu-id="c2d79-114">Nella **casella degli strumenti SSIS**espandere **comune**, quindi trascinare **ricerca** sull'area di progettazione della scheda **flusso di dati** . Posizionare la ricerca direttamente sotto l'origine **dati Estrai valuta di esempio** .</span><span class="sxs-lookup"><span data-stu-id="c2d79-114">In the **SSIS Toolbox**, expand **Common**, and then drag **Lookup** onto the design surface of the **Data Flow** tab. Place Lookup directly below the **Extract Sample Currency Data** source.</span></span>  
  
2.  <span data-ttu-id="c2d79-115">Fare clic sull'origine del file flat **Extract Sample Currency Data** e trascinare la freccia verde sulla trasformazione **Ricerca** appena aggiunta per collegare i due componenti.</span><span class="sxs-lookup"><span data-stu-id="c2d79-115">Click the **Extract Sample Currency Data** flat file source and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="c2d79-116">Nell'area di progettazione **Flusso di dati** fare clic su **Ricerca** nella trasformazione **Ricerca** e cambiare il nome in **Lookup Currency Key**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-116">On the **Data Flow** design surface, click **Lookup** in the **Lookup** transformation, and change the name to **Lookup Currency Key**.</span></span>  
  
4.  <span data-ttu-id="c2d79-117">Fare doppio clic sulla trasformazione **Lookup Currency Key** per visualizzare l'Editor trasformazione Ricerca.</span><span class="sxs-lookup"><span data-stu-id="c2d79-117">Double-click the **Lookup CurrencyKey** transformation to display the Lookup Transformation Editor.</span></span>  
  
5.  <span data-ttu-id="c2d79-118">Nella pagina **Generale** effettuare le selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2d79-118">On the **General** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="c2d79-119">Selezionare **Full cache**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-119">Select **Full cache**.</span></span>  
  
    2.  <span data-ttu-id="c2d79-120">Nell'area **Tipo di connessione** selezionare **Gestione connessione OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-120">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
6.  <span data-ttu-id="c2d79-121">Nella pagina **Connessione** effettuare le selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2d79-121">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="c2d79-122">Nella finestra di dialogo **Gestione connessione OLE DB** assicurarsi che sia visualizzato **localhost.AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="c2d79-122">In the **OLE DB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="c2d79-123">Selezionare **Usa i risultati di una query SQL**, quindi digitare o copiare l'istruzione SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="c2d79-123">Select **Use results of an SQL query**, and then type or copy the following SQL statement:</span></span>  
  
        ```  
        select * from (select * from [dbo].[DimCurrency]) as refTable  
        where [refTable].[CurrencyAlternateKey] = 'ARS'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'AUD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'BRL'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CAD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CNY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'DEM'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'EUR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'FRF'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'GBP'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'JPY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'MXN'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'SAR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'USD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'VEB'  
        ```  
  
7.  <span data-ttu-id="c2d79-124">Nella pagina **Colonne** effettuare le selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2d79-124">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="c2d79-125">Nel pannello **Colonne di input disponibili** trascinare **CurrencyID** sul pannello **Colonne di ricerca disponibili** e rilasciarlo su **CurrencyAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-125">In the **Available Input Columns** panel, drag **CurrencyID** to the **Available Lookup Columns** panel and drop it on **CurrencyAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="c2d79-126">Nell'elenco **Colonne di ricerca disponibili** selezionare la casella di controllo a sinistra di **CurrencyKey**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-126">In the **Available Lookup Columns** list, select the check box to the left of **CurrencyKey**.</span></span>  
  
8.  <span data-ttu-id="c2d79-127">Fare clic su **OK** per tornare all'area di progettazione **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="c2d79-127">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
9. <span data-ttu-id="c2d79-128">Fare clic con il pulsante destro del mouse sulla trasformazione Lookup Currency Key e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-128">Right-click the Lookup Currency Key transformation, click **Properties**.</span></span>  
  
10. <span data-ttu-id="c2d79-129">Nella Finestra Proprietà verificare che la `LocaleID` proprietà sia impostata su **inglese (Stati Uniti)** e che la proprietà **DefaultCodePage** sia impostata su **1252**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-129">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
### <a name="to-add-and-configure-the--lookup-datekey-transformation"></a><span data-ttu-id="c2d79-130">Per aggiungere e configurare la trasformazione Lookup DateKey</span><span class="sxs-lookup"><span data-stu-id="c2d79-130">To add and configure the  Lookup DateKey transformation</span></span>  
  
1.  <span data-ttu-id="c2d79-131">Nella **Casella degli strumenti SSIS**trascinare **Ricerca** sull'area di progettazione **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="c2d79-131">In the **SSIS Toolbox**, drag **Lookup** onto the **Data Flow** design surface.</span></span> <span data-ttu-id="c2d79-132">Posizionare Ricerca proprio sotto la trasformazione **Lookup Currency Key** .</span><span class="sxs-lookup"><span data-stu-id="c2d79-132">Place Lookup directly below the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="c2d79-133">Fare clic sulla trasformazione **Lookup Currency Key** e trascinare la freccia verde sulla nuova trasformazione **Ricerca** per collegare i due componenti.</span><span class="sxs-lookup"><span data-stu-id="c2d79-133">Click the **Lookup Currency Key** transformation and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="c2d79-134">Nella finestra di dialogo **Selezione input e output** fare clic su **Output corrispondenza ricerca** nella casella di riepilogo **Output** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-134">In the **Input Output Selection** dialog box, click **Lookup Match Output** in the **Output** list box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="c2d79-135">Nell'area di progettazione **Flusso di dati** fare clic su **Ricerca** nella trasformazione **Ricerca** appena aggiunta e impostare il nome su **Lookup Date Key**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-135">On the **Data Flow** design surface, click **Lookup** in the newly added **Lookup** transformation, and change the name to **Lookup Date Key**.</span></span>  
  
5.  <span data-ttu-id="c2d79-136">Fare doppio clic sulla trasformazione **Lookup Date Key** .</span><span class="sxs-lookup"><span data-stu-id="c2d79-136">Double-click the **Lookup Date Key** transformation.</span></span>  
  
6.  <span data-ttu-id="c2d79-137">Nella pagina **Generale** selezionare **Partial cache**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-137">On the **General** page, select **Partial cache**.</span></span>  
  
7.  <span data-ttu-id="c2d79-138">Nella pagina **Connessione** effettuare le selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2d79-138">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="c2d79-139">Nella finestra di dialogo **Gestione connessione OLE DB** assicurarsi che sia visualizzato **localhost.AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="c2d79-139">In the **OLEDB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="c2d79-140">Nella casella **Usa una tabella o una vista** digitare o selezionare **[dbo].[DimDate]**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-140">In the **Use a table or view** box, type or select **[dbo].[DimDate]**.</span></span>  
  
8.  <span data-ttu-id="c2d79-141">Nella pagina **Colonne** effettuare le selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2d79-141">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="c2d79-142">Nel pannello **Colonne di input disponibili** trascinare **CurrencyDate** sul pannello **Colonne di ricerca disponibili** e rilasciarlo su **FullDateAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-142">In the **Available Input Columns** panel, drag **CurrencyDate** to the **Available Lookup Columns** panel and drop it on **FullDateAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="c2d79-143">Nell'elenco **Colonne di ricerca disponibili** selezionare la casella di controllo a sinistra di **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-143">In the **Available Lookup Columns** list, select the check box to the left of **DateKey**.</span></span>  
  
9. <span data-ttu-id="c2d79-144">Nella pagina **Avanzate** rivedere le opzioni di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="c2d79-144">On the **Advanced** page, review the caching options.</span></span>  
  
10. <span data-ttu-id="c2d79-145">Fare clic su **OK** per tornare all'area di progettazione **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="c2d79-145">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
11. <span data-ttu-id="c2d79-146">Fare clic con il pulsante destro del mouse sulla trasformazione Lookup Date Key e scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="c2d79-146">Right-click the Lookup Date Key transformation and click **Properties.**</span></span>  
  
12. <span data-ttu-id="c2d79-147">Nella Finestra Proprietà verificare che la `LocaleID` proprietà sia impostata su **inglese (Stati Uniti)** e che la proprietà **DefaultCodePage** sia impostata su **1252**.</span><span class="sxs-lookup"><span data-stu-id="c2d79-147">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c2d79-148">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="c2d79-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c2d79-149">Passaggio 7: Aggiunta e configurazione della destinazione OLE DB</span><span class="sxs-lookup"><span data-stu-id="c2d79-149">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
## <a name="see-also"></a><span data-ttu-id="c2d79-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2d79-150">See Also</span></span>  
 [<span data-ttu-id="c2d79-151">Trasformazione Ricerca</span><span class="sxs-lookup"><span data-stu-id="c2d79-151">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
