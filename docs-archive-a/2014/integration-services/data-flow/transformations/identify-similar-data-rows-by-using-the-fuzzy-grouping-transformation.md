---
title: Identificare righe di dati simili tramite la trasformazione Raggruppamento fuzzy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Fuzzy Grouping transformation
- match similar data [Integration Services]
- similar data rows [Integration Services]
- fuzzy matches
ms.assetid: ffcb41a6-e23d-49ea-8c32-ac980e3dc495
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4e6d49548c211b38a35d6f5f7efc3d50fec93588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636316"
---
# <a name="identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation"></a><span data-ttu-id="7c2c3-102">Identificazione di righe di dati simili tramite la trasformazione Raggruppamento fuzzy</span><span class="sxs-lookup"><span data-stu-id="7c2c3-102">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>
  <span data-ttu-id="7c2c3-103">È possibile aggiungere e configurare una trasformazione Raggruppamento fuzzy solo se il pacchetto include già almeno un'attività Flusso di dati e un'origine.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-103">To add and configure a Fuzzy Grouping transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-implement-fuzzy-grouping-transformation-in-a-data-flow"></a><span data-ttu-id="7c2c3-104">Per implementare una trasformazione Raggruppamento fuzzy in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="7c2c3-104">To implement Fuzzy Grouping transformation in a data flow</span></span>  
  
1.  <span data-ttu-id="7c2c3-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="7c2c3-106">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="7c2c3-107">Fare clic sulla scheda **Flusso di dati** , quindi da **Casella degli strumenti**trascinare la trasformazione Raggruppamento fuzzy sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Fuzzy Grouping transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="7c2c3-108">Connettere la trasformazione Raggruppamento fuzzy al flusso di dati trascinando il connettore dall'origine dati o da una trasformazione precedente alla trasformazione Raggruppamento fuzzy.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-108">Connect the Fuzzy Grouping transformation to the data flow by dragging the connector from the data source or a previous transformation to the Fuzzy Grouping transformation.</span></span>  
  
5.  <span data-ttu-id="7c2c3-109">Fare doppio clic sulla trasformazione Raggruppamento fuzzy.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-109">Double-click the Fuzzy Grouping transformation.</span></span>  
  
6.  <span data-ttu-id="7c2c3-110">Nella scheda **Gestione connessione** della finestra di dialogo **Editor trasformazione Raggruppamento fuzzy** selezionare una gestione connessione OLE DB che consenta la connessione a un database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c2c3-110">In the **Fuzzy Grouping Transformation Editor** dialog box, on the **Connection Manager** tab, select an OLE DB connection manager that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7c2c3-111">La trasformazione richiede una connessione a un database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per creare tabelle e indici temporanei.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-111">The transformation requires a connection to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database to create temporary tables and indexes.</span></span>  
  
7.  <span data-ttu-id="7c2c3-112">Fare clic sulla scheda **Colonne** e, nell'elenco **Colonne di input disponibili** , selezionare la casella di controllo corrispondente alla colonna di input da usare per identificare righe simili nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-112">Click the **Columns** tab and, in the **Available Input Columns** list, select the check box of the input columns to use to identify similar rows in the dataset.</span></span>  
  
8.  <span data-ttu-id="7c2c3-113">Per identificare le colonne di input da passare direttamente all'output della trasformazione, selezionare le caselle di controllo nella colonna **Pass-through** .</span><span class="sxs-lookup"><span data-stu-id="7c2c3-113">Select the check box in the **Pass Through** column to identify the input columns to pass through to the transformation output.</span></span> <span data-ttu-id="7c2c3-114">Le colonne pass-through non vengono coinvolte nel processo di identificazione delle righe duplicate.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-114">Pass-through columns are not included in the process of identification of duplicate rows.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7c2c3-115">Le colonne di input utilizzate per il raggruppamento vengono automaticamente selezionate come colonne pass-through e non possono essere deselezionate mentre sono in uso per il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-115">Input columns that are used for grouping are automatically selected as pass-through columns, and they cannot be unselected while used for grouping.</span></span>  
  
9. <span data-ttu-id="7c2c3-116">Facoltativamente, aggiornare i nomi delle colonne di output nella colonna **Alias di output** .</span><span class="sxs-lookup"><span data-stu-id="7c2c3-116">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="7c2c3-117">Facoltativamente, aggiornare i nomi delle colonne elaborate nella colonna **Alias di output gruppo** .</span><span class="sxs-lookup"><span data-stu-id="7c2c3-117">Optionally, update the names of cleaned columns in the **Group OutputAlias** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7c2c3-118">I nomi predefiniti delle colonne vengono ottenuti aggiungendo il suffisso "_clean" ai nomi delle colonne di input.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-118">The default names of columns are the names of the input columns with a "_clean" suffix.</span></span>  
  
11. <span data-ttu-id="7c2c3-119">Facoltativamente, digitare nella colonna **Tipo di corrispondenza** il tipo di corrispondenza da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-119">Optionally, update the type of match to use in the **Match Type** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7c2c3-120">È necessario utilizzare la corrispondenza fuzzy almeno per una colonna.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-120">At least one column must use fuzzy matching.</span></span>  
  
12. <span data-ttu-id="7c2c3-121">Specificare le colonne con livello di somiglianza minimo nella colonna **Somiglianza minima** .</span><span class="sxs-lookup"><span data-stu-id="7c2c3-121">Specify the minimum similarity level columns in the **Minimum Similarity** column.</span></span> <span data-ttu-id="7c2c3-122">Il valore deve essere compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-122">The value must be between 0 and 1.</span></span> <span data-ttu-id="7c2c3-123">Più il valore è vicino a 1, più i valori nelle colonne di input dovranno essere simili per formare un gruppo.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-123">The closer the value is to 1, the more similar the values in the input columns must be to form a group.</span></span> <span data-ttu-id="7c2c3-124">Una somiglianza minima pari a 1 indica una corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-124">A minimum similarity of 1 indicates an exact match.</span></span>  
  
13. <span data-ttu-id="7c2c3-125">Facoltativamente, aggiornare i nomi delle colonne con somiglianza nella colonna **Alias di output somiglianza** .</span><span class="sxs-lookup"><span data-stu-id="7c2c3-125">Optionally, update the names of similarity columns in the **Similarity Output Alias** column.</span></span>  
  
14. <span data-ttu-id="7c2c3-126">Per specificare la modalità di gestione dei numeri nei valori dei dati, aggiornare i valori nella colonna **Numerali** .</span><span class="sxs-lookup"><span data-stu-id="7c2c3-126">To specify the handling of numbers in data values, update the values in the **Numerals** column.</span></span>  
  
15. <span data-ttu-id="7c2c3-127">Per specificare la modalità con cui la trasformazione deve confrontare i dati stringa contenuti in una colonna, modificare la selezione predefinita delle opzioni di confronto nella colonna **Flag di confronto** .</span><span class="sxs-lookup"><span data-stu-id="7c2c3-127">To specify how the transformation compares the string data in a column, modify the default selection of comparison options in the **Comparison Flags** column.</span></span>  
  
16. <span data-ttu-id="7c2c3-128">Fare clic sulla scheda **Avanzate** per modificare i nomi delle colonne che la trasformazione aggiunge all'output per l'identificatore di riga univoco (_key_in), l'identificatore di riga duplicato (_key_out) e il valore di somiglianza (_score).</span><span class="sxs-lookup"><span data-stu-id="7c2c3-128">Click the **Advanced** tab to modify the names of the columns that the transformation adds to the output for the unique row identifier (_key_in), the duplicate row identifier (_key_out), and the similarity value (_score).</span></span>  
  
17. <span data-ttu-id="7c2c3-129">Facoltativamente, regolare la soglia di somiglianza spostando il dispositivo di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-129">Optionally, adjust the similarity threshold by moving the slider bar.</span></span>  
  
18. <span data-ttu-id="7c2c3-130">Facoltativamente, deselezionare le caselle di controllo in Delimitatori token per ignorare i delimitatori presenti nei dati.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-130">Optionally, clear the token delimiter check boxes to ignore delimiters in the data.</span></span>  
  
19. <span data-ttu-id="7c2c3-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c2c3-131">Click **OK**.</span></span>  
  
20. <span data-ttu-id="7c2c3-132">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="7c2c3-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c2c3-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c2c3-133">See Also</span></span>  
 <span data-ttu-id="7c2c3-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="7c2c3-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span></span>  
 <span data-ttu-id="7c2c3-135">[Trasformazioni di Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="7c2c3-135">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="7c2c3-136">[Percorsi in Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="7c2c3-136">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="7c2c3-137">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="7c2c3-137">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
