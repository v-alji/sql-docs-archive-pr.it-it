---
title: Implementare una trasformazione Ricerca in modalità Full cache utilizzando la gestione connessione OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Lookup transformation [Integration Services]
ms.assetid: c4150e1b-bdff-4f7a-af4c-3401c34def83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f77a753dd71bc487d57492371906fc48bc114357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636354"
---
# <a name="implement-a-lookup-transformation-in-full-cache-mode-using-the-ole-db-connection-manager"></a><span data-ttu-id="fcab2-102">Implementazione di una trasformazione Ricerca in modalità Full cache utilizzando la gestione connessione OLE DB</span><span class="sxs-lookup"><span data-stu-id="fcab2-102">Implement a Lookup Transformation in Full Cache Mode Using the OLE DB Connection Manager</span></span>
  <span data-ttu-id="fcab2-103">È possibile configurare la trasformazione Ricerca per utilizzare la modalità Full Cache e una gestione connessione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fcab2-103">You can configure the Lookup transformation to use full cache mode and an OLE DB connection manager.</span></span> <span data-ttu-id="fcab2-104">In modalità Full Cache il set di dati di riferimento viene caricato nella cache prima dell'esecuzione della trasformazione Ricerca.</span><span class="sxs-lookup"><span data-stu-id="fcab2-104">In the full cache mode, the reference dataset is loaded into cache before the Lookup transformation runs.</span></span>  
  
 <span data-ttu-id="fcab2-105">La trasformazione Ricerca esegue ricerche creando un join dei dati contenuti nelle colonne di input da un'origine dati connessa con le colonne in un set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="fcab2-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in a reference dataset.</span></span> <span data-ttu-id="fcab2-106">Per altre informazioni, vedere [Trasformazione Ricerca](../data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="fcab2-106">For more information, see [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="fcab2-107">Quando si configura la trasformazione Ricerca per l'utilizzo di una gestione connessione OLE DB, selezionare una tabella, una vista o una query SQL per generare il set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="fcab2-107">When you configure the Lookup transformation to use an OLE DB connection manager, you select a table, view, or SQL query to generate the reference dataset.</span></span>  
  
### <a name="to-implement-a-lookup-transformation-in-full-cache-mode-by-using-ole-db-connection-manager"></a><span data-ttu-id="fcab2-108">Per implementare una trasformazione Ricerca in modalità Full Cache utilizzando la gestione connessione OLE DB</span><span class="sxs-lookup"><span data-stu-id="fcab2-108">To implement a Lookup transformation in full cache mode by using OLE DB connection manager</span></span>  
  
1.  <span data-ttu-id="fcab2-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenente il pacchetto desiderato, quindi fare clic su di esso in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="fcab2-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want, and then double-click the package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="fcab2-110">Nella scheda **Flusso di dati** trascinare la Trasformazione Ricerca dalla **Casella degli strumenti**all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="fcab2-110">On the **Data Flow** tab, from the **Toolbox**, drag the Lookup transformation to the design surface.</span></span>  
  
3.  <span data-ttu-id="fcab2-111">Connettere la trasformazione Ricerca al flusso di dati trascinando un connettore da un'origine o una trasformazione precedente alla trasformazione Ricerca.</span><span class="sxs-lookup"><span data-stu-id="fcab2-111">Connect the Lookup transformation to the data flow by dragging a connector from a source or a previous transformation to the Lookup transformation.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcab2-112">Una trasformazione Ricerca può non essere convalidata se si connette a un file flat che contiene un campo di tipo data vuoto.</span><span class="sxs-lookup"><span data-stu-id="fcab2-112">A Lookup transformation might not validate if that transformation connects to a flat file that contains an empty date field.</span></span> <span data-ttu-id="fcab2-113">La convalida della trasformazione varia a seconda che per la gestione connessione relativa al file flat sia configurato o meno il mantenimento dei valori Null.</span><span class="sxs-lookup"><span data-stu-id="fcab2-113">Whether the transformation validates depends on whether the connection manager for the flat file has been configured to retain null values.</span></span> <span data-ttu-id="fcab2-114">Per assicurarsi che la Trasformazione Ricerca venga convalidata, in **Editor origine file flat**nella **pagina Gestione connessione**selezionare l'opzione **Mantieni i valori Null dell'origine come valori Null nel flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="fcab2-114">To ensure that the Lookup transformation validates, in the **Flat File Source Editor**, on the **Connection Manager Page**, select the **Retain null values from the source as null values in the data flow** option.</span></span>  
  
4.  <span data-ttu-id="fcab2-115">Fare doppio clic sulla trasformazione di origine o precedente per configurare il componente.</span><span class="sxs-lookup"><span data-stu-id="fcab2-115">Double-click the source or previous transformation to configure the component.</span></span>  
  
5.  <span data-ttu-id="fcab2-116">Fare doppio clic su Trasformazione Ricerca, quindi nella pagina **Generale**di **Editor trasformazione Ricerca** selezionare **Full cache**.</span><span class="sxs-lookup"><span data-stu-id="fcab2-116">Double-click the Lookup transformation, and then in the **Lookup Transformation Editor**, on the **General** page, select **Full cache**.</span></span>  
  
6.  <span data-ttu-id="fcab2-117">Nell'area **Tipo di connessione** selezionare **Gestione connessione OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="fcab2-117">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
7.  <span data-ttu-id="fcab2-118">Nell'elenco **Specificare come gestire le righe senza voci corrispondenti** selezionare un'opzione di gestione degli errori per le righe senza voci corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="fcab2-118">In the **Specify how to handle rows with no matching entries** list, select an error handling option for rows without matching entries.</span></span>  
  
8.  <span data-ttu-id="fcab2-119">Nella pagina Connessione, selezionare una gestione connessione dall'elenco **Gestione connessione OLE DB** o fare clic su **Nuova** per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="fcab2-119">On the Connection page, select a connection manager from the **OLE DB connection manager** list or click **New** to create a new connection manager.</span></span> <span data-ttu-id="fcab2-120">Per altre informazioni, vedere [Gestione connessione OLE DB](ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fcab2-120">For more information, see [OLE DB Connection Manager](ole-db-connection-manager.md).</span></span>  
  
9. <span data-ttu-id="fcab2-121">Effettuare una delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="fcab2-121">Do one of the following tasks:</span></span>  
  
    -   <span data-ttu-id="fcab2-122">Fare clic su **Usa una tabella o una vista**, quindi selezionare una tabella o una vista oppure fare clic su **Nuova** per creare una tabella o una vista.</span><span class="sxs-lookup"><span data-stu-id="fcab2-122">Click **Use a table or a view**, and then either select a table or view, or click **New** to create a table or view.</span></span>  
  
         <span data-ttu-id="fcab2-123">-oppure-</span><span class="sxs-lookup"><span data-stu-id="fcab2-123">-or-</span></span>  
  
    -   <span data-ttu-id="fcab2-124">Fare clic su **Usa i risultati di una query SQL**, quindi compilare una query nella finestra **Comando SQL** oppure fare clic su **Compila query** per compilare una query usando gli strumenti grafici disponibili in **Generatore query** .</span><span class="sxs-lookup"><span data-stu-id="fcab2-124">Click **Use results of an SQL query**, and then build a query in the **SQL Command** window, or click **Build Query** to build a query by using the graphical tools that the **Query Builder** provides.</span></span>  
  
         <span data-ttu-id="fcab2-125">-oppure-</span><span class="sxs-lookup"><span data-stu-id="fcab2-125">-or-</span></span>  
  
    -   <span data-ttu-id="fcab2-126">In alternativa fare clic su **Sfoglia** per importare un'istruzione SQL da un file.</span><span class="sxs-lookup"><span data-stu-id="fcab2-126">Alternatively, click **Browse** to import an SQL statement from a file.</span></span>  
  
     <span data-ttu-id="fcab2-127">Per convalidare la query SQL, fare clic su **Analizza query**.</span><span class="sxs-lookup"><span data-stu-id="fcab2-127">To validate the SQL query, click **Parse Query**.</span></span>  
  
     <span data-ttu-id="fcab2-128">Per visualizzare un campione di dati, fare clic su **Anteprima**.</span><span class="sxs-lookup"><span data-stu-id="fcab2-128">To view a sample of the data, click **Preview**.</span></span>  
  
10. <span data-ttu-id="fcab2-129">Fare clic nella pagina **Colonne** e trascinare almeno una colonna dall'elenco **Colonne di input disponibili** a una colonna nell'elenco **Colonne di ricerca disponibili** .</span><span class="sxs-lookup"><span data-stu-id="fcab2-129">Click the **Columns** page, and then from the **Available Input Columns** list, drag at least one column to a column in the **Available Lookup Column** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcab2-130">La trasformazione Ricerca esegue automaticamente il mapping delle colonne con lo stesso nome e lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="fcab2-130">The Lookup transformation automatically maps columns that have the same name and the same data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcab2-131">È possibile eseguire il mapping solo di colonne con tipi di dati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="fcab2-131">Columns must have matching data types to be mapped.</span></span> <span data-ttu-id="fcab2-132">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fcab2-132">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
11. <span data-ttu-id="fcab2-133">Includere colonne di ricerca nell'output effettuando le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="fcab2-133">Include lookup columns in the output by doing the following tasks:</span></span>  
  
    1.  <span data-ttu-id="fcab2-134">Nell'elenco **Colonne di ricerca disponibili** .</span><span class="sxs-lookup"><span data-stu-id="fcab2-134">In the **Available Lookup Columns** list.</span></span> <span data-ttu-id="fcab2-135">selezionare le colonne.</span><span class="sxs-lookup"><span data-stu-id="fcab2-135">select columns.</span></span>  
  
    2.  <span data-ttu-id="fcab2-136">Nell'elenco **Operazione di ricerca** specificare se i valori dalle colonne di ricerca sostituiscono quelli nella colonna di input o vengono scritti in una nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="fcab2-136">In **Lookup Operation** list, specify whether the values from the lookup columns replace values in the input column or are written to a new column.</span></span>  
  
12. <span data-ttu-id="fcab2-137">Per configurare l'output degli errori, fare clic sulla pagina **Output errori** e impostare le opzioni di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="fcab2-137">To configure the error output, click the **Error Output** page and set the error handling options.</span></span> <span data-ttu-id="fcab2-138">Per altre informazioni, vedere [Editor trasformazione Ricerca &#40;pagina Output degli errori&#41;](../lookup-transformation-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="fcab2-138">For more information, see [Lookup Transformation Editor &#40;Error Output Page&#41;](../lookup-transformation-editor-error-output-page.md).</span></span>  
  
13. <span data-ttu-id="fcab2-139">Fare clic su **OK** per salvare le modifiche alla trasformazione Ricerca, quindi eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fcab2-139">Click **OK** to save your changes to the Lookup transformation, and then run the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcab2-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcab2-140">See Also</span></span>  
 <span data-ttu-id="fcab2-141">[Implementare una trasformazione Ricerca in modalità Full Cache tramite la gestione connessione della cache](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fcab2-141">[Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span></span>  
 <span data-ttu-id="fcab2-142">[Implementare una ricerca in modalità No Cache o Partial Cache](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span><span class="sxs-lookup"><span data-stu-id="fcab2-142">[Implement a Lookup in No Cache or Partial Cache Mode](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span></span>  
 [<span data-ttu-id="fcab2-143">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="fcab2-143">Integration Services Transformations</span></span>](../data-flow/transformations/integration-services-transformations.md)  
  
  
