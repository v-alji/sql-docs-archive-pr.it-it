---
title: Aggiungere un visualizzatore dati a un flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data viewers [Integration Services]
- data flow [Integration Services], data viewers
- adding data viewers
ms.assetid: 5e573274-a170-4132-bfc8-a8ff3a8411e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7abd76417552ec50da736afe024a5ae36ee6a2ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624298"
---
# <a name="add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="509f5-102">Aggiunta di un visualizzatore dati a un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="509f5-102">Add a Data Viewer to a Data Flow</span></span>
  <span data-ttu-id="509f5-103">In questo argomento viene descritta la procedura per l'aggiunta e la configurazione di un visualizzatore dati in un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="509f5-103">This topic describes how to add and configure a data viewer in a data flow.</span></span> <span data-ttu-id="509f5-104">In un visualizzatore dati vengono visualizzati i dati in transito tra due componenti flusso di dati,</span><span class="sxs-lookup"><span data-stu-id="509f5-104">A data viewer displays data that is moving between two data flow components.</span></span> <span data-ttu-id="509f5-105">ad esempio i dati estratti da un'origine dei dati prima che vengano modificati da una trasformazione del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="509f5-105">For example, a data viewer can display the data that is extracted from a data source before a transformation in the data flow modifies the data.</span></span>  
  
 <span data-ttu-id="509f5-106">Un percorso collega i componenti in un flusso di dati connettendo l'output di un componente all'input dell'altro.</span><span class="sxs-lookup"><span data-stu-id="509f5-106">A path connects components in a data flow by connecting the output of one data flow component to the input of another component.</span></span>  
  
 <span data-ttu-id="509f5-107">Per poter aggiungere visualizzatori dati in un pacchetto, è necessario che il pacchetto includa un'attività Flusso di dati e almeno due componenti flusso di dati connessi tra di loro.</span><span class="sxs-lookup"><span data-stu-id="509f5-107">Before you can add data viewers to a package, the package must include a Data Flow task and at least two data flow components that are connected.</span></span>  
  
### <a name="to-add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="509f5-108">Per aggiungere un visualizzatore dati in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="509f5-108">To add a data viewer to a data flow</span></span>  
  
1.  <span data-ttu-id="509f5-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="509f5-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="509f5-110">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="509f5-110">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="509f5-111">Fare clic sulla scheda **Flusso di controllo** se non è già visualizzata.</span><span class="sxs-lookup"><span data-stu-id="509f5-111">Click the **Control Flow** tab, if it is not already active.</span></span>  
  
4.  <span data-ttu-id="509f5-112">Fare clic sull'attività Flusso di dati nel cui flusso di dati si vuole aggiungere un visualizzatore dati e quindi dare clic sulla scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="509f5-112">Click the Data Flow task to whose data flow you want to attach a data viewer and then click the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="509f5-113">Fare clic con il pulsante destro del mouse su un percorso tra due componenti del flusso di dati e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="509f5-113">Right-click a path between two data flow components, and click **Edit**.</span></span>  
  
6.  <span data-ttu-id="509f5-114">Nella pagina **Generale** è possibile visualizzare e modificare le proprietà del percorso.</span><span class="sxs-lookup"><span data-stu-id="509f5-114">On the **General** page, you can view and edit path properties.</span></span> <span data-ttu-id="509f5-115">Ad esempio, nell'elenco a discesa **PathAnnotation** è possibile selezionare l'annotazione visualizzata accanto al percorso.</span><span class="sxs-lookup"><span data-stu-id="509f5-115">For example, from the **PathAnnotation** drop-down list you can select the annotation that appears next to the path.</span></span>  
  
7.  <span data-ttu-id="509f5-116">Nella pagina **Metadati** è possibile visualizzare i metadati delle colonne e copiarli negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="509f5-116">On the **Metadata** page, you can view the column metadata and copy the metadata to the Clipboard.</span></span>  
  
8.  <span data-ttu-id="509f5-117">Nella pagina **Visualizzatore dati** fare clic su **Abilita visualizzatore dati**.</span><span class="sxs-lookup"><span data-stu-id="509f5-117">On the **Data Viewer** page, click **Enable data viewer**.</span></span>  
  
9. <span data-ttu-id="509f5-118">Nell'area Colonne da visualizzare selezionare le colonne che si desidera visualizzare nel visualizzatore dati.</span><span class="sxs-lookup"><span data-stu-id="509f5-118">In the Columns to display area, select the columns you want to display in the data viewer.</span></span> <span data-ttu-id="509f5-119">Per impostazione predefinita, nell'elenco **Colonne visualizzate** sono elencate e selezionate tutte le colonne disponibili.</span><span class="sxs-lookup"><span data-stu-id="509f5-119">By default, all the available columns are selected and listed in the **Displayed Columns** list.</span></span> <span data-ttu-id="509f5-120">Spostare le colonne da non usare nell'elenco **Colonne inutilizzate** selezionandole e facendo clic sulla freccia sinistra.</span><span class="sxs-lookup"><span data-stu-id="509f5-120">Move columns that you do not want to use to the **Unused Column** list by selecting them and then clicking the left arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="509f5-121">I valori nella griglia che rappresentano i tipi di dati DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2 e DT_DBTIMESTAMPOFFSET vengono visualizzati come stringhe formattate ISO 8601. Uno spazio separatore sostituisce il separatore `T`.</span><span class="sxs-lookup"><span data-stu-id="509f5-121">In the grid, values that represent the DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types appear as ISO 8601 formatted strings and a space separator replaces the `T` separator.</span></span> <span data-ttu-id="509f5-122">I valori che rappresentano i tipi di dati DT_DATE e DT_FILETIME includono sette cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="509f5-122">Values that represent the DT_DATE and DT_FILETIME data types include seven digits for fractional seconds.</span></span> <span data-ttu-id="509f5-123">Poiché il tipo di dati DT_FILETIME memorizza solo tre cifre dei secondi frazionari, nella griglia viene visualizzato zero per le quattro cifre rimanenti.</span><span class="sxs-lookup"><span data-stu-id="509f5-123">Because the DT_FILETIME data type stores only three digits of fractional seconds, the grid displays zeros for the remaining four digits.</span></span> <span data-ttu-id="509f5-124">I valori che rappresentano il tipo di dati DT_DBTIMESTAMP includono tre cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="509f5-124">Values that represent the DT_DBTIMESTAMP data type include three digits for fractional seconds.</span></span> <span data-ttu-id="509f5-125">Per i valori che rappresentano i tipi di dati DT_DBTIME2, DT_DBTIMESTAMP2 e DT_DBTIMESTAMPOFFSET, il numero di cifre dei secondi frazionari corrisponde alla scala specificata per il tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="509f5-125">For values that represent the DT_DBTIME2, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types, the number of digits for fractional seconds corresponds to the scale specified for the column's data type.</span></span> <span data-ttu-id="509f5-126">Per altre informazioni sui formati ISO 8601, vedere [Formati di data e ora](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="509f5-126">For more information about ISO 8601 formats, see [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span> <span data-ttu-id="509f5-127">Per altre informazioni sui tipi di dati, vedere [Tipi di dati di Integration Services](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="509f5-127">For more information about data types, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
10. <span data-ttu-id="509f5-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="509f5-128">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509f5-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="509f5-129">See Also</span></span>  
 <span data-ttu-id="509f5-130">[Trasformazioni di Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="509f5-130">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="509f5-131">[Percorsi in Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="509f5-131">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="509f5-132">[Flusso di dati](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="509f5-132">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="509f5-133">Debug di un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="509f5-133">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
  
