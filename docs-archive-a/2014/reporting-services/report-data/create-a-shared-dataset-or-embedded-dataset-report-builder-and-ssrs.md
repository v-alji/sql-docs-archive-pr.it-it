---
title: Creare un set di dati condiviso o un set di dati incorporato (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d1d7bc71-f0e9-4ce5-b3ad-6fee54388a31
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fca74e1ba7965eeef6ce562e79e378af5bb9e145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712792"
---
# <a name="create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs"></a><span data-ttu-id="72702-102">Creare un set di dati condiviso o un set di dati incorporato (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="72702-102">Create a Shared Dataset or Embedded Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="72702-103">È possibile creare un set di dati incorporato, usato in un report singolo, o un set di dati condiviso da salvare in un server di report, usato in più report.</span><span class="sxs-lookup"><span data-stu-id="72702-103">You can create an embedded dataset for use in a single report or a shared dataset to save to a report server, for use by multiple reports.</span></span> <span data-ttu-id="72702-104">Per creare un set di dati, è necessario disporre di un'origine dati incorporata o condivisa.</span><span class="sxs-lookup"><span data-stu-id="72702-104">To create a dataset, you must have an embedded or shared data source.</span></span>

 <span data-ttu-id="72702-105">Usare Generatore report per effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="72702-105">Use Report Builder to do the following tasks:</span></span>

-   <span data-ttu-id="72702-106">Creare un set di dati condiviso nella visualizzazione di progettazione del set di dati.</span><span class="sxs-lookup"><span data-stu-id="72702-106">Create a shared dataset in Dataset Design View.</span></span> <span data-ttu-id="72702-107">Nei set di dati condivisi devono essere usate origini dati condivise pubblicate.</span><span class="sxs-lookup"><span data-stu-id="72702-107">Shared datasets must use published shared data sources.</span></span>

-   <span data-ttu-id="72702-108">Creare un set di dati incorporato nella visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="72702-108">Create an embedded dataset in Report Design View.</span></span>

-   <span data-ttu-id="72702-109">Salvare il set di dati direttamente nel server di report o nel sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="72702-109">Save the dataset directly to the report server or SharePoint site.</span></span>

 <span data-ttu-id="72702-110">Usare Progettazione report disponibile in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] per effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="72702-110">Use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to do the following tasks:</span></span>

1.  <span data-ttu-id="72702-111">Creare un set di dati condiviso in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="72702-111">Create a shared dataset in Solution Explorer.</span></span> <span data-ttu-id="72702-112">Nei set di dati condivisi devono essere usate origini dati della cartella Origini dati condivise in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="72702-112">Shared datasets must use data sources from the Shared Data Sources folder in Solution Explorer.</span></span>

2.  <span data-ttu-id="72702-113">Creare un set di dati incorporato nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="72702-113">Create an embedded dataset in the Report Data pane.</span></span>

3.  <span data-ttu-id="72702-114">Facoltativamente, distribuire i set di dati condivisi e l'origine dati condivisa con il report.</span><span class="sxs-lookup"><span data-stu-id="72702-114">Optionally deploy the shared datasets and shared data source with the report.</span></span> <span data-ttu-id="72702-115">Per ogni tipo di elemento, usare Proprietà progetto per specificare i percorsi alle cartelle nel server di report o nel sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="72702-115">For each type of item, use Project Properties to specify paths to folders on the report server or SharePoint site.</span></span>

 <span data-ttu-id="72702-116">Per altre informazioni, vedere [Set di dati condivisi e incorporati del report &#40;Generatore report e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="72702-116">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-open-report-builder-and-create-a-shared-dataset"></a><span data-ttu-id="72702-117">Per aprire Generatore report e creare un set di dati condiviso</span><span class="sxs-lookup"><span data-stu-id="72702-117">To open Report Builder and create a shared dataset</span></span>

1.  <span data-ttu-id="72702-118">Aprire Generatore report.</span><span class="sxs-lookup"><span data-stu-id="72702-118">Open Report Builder.</span></span> <span data-ttu-id="72702-119">Viene visualizzato il riquadro **Nuovo report o set di dati** , come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="72702-119">The **New report or dataset pane** opens, as shown in the following figure:</span></span>

     <span data-ttu-id="72702-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span><span class="sxs-lookup"><span data-stu-id="72702-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="72702-121"> Se tale riquadro non viene visualizzato,\ \*\*\** nel pulsante Generatore report fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="72702-121">If the **New report or dataset pane** does not appear, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="72702-122">Nel riquadro sinistro, sotto **Crea un set di dati**, fare clic su **Set di dati condiviso**.</span><span class="sxs-lookup"><span data-stu-id="72702-122">In the left pane, under **Create a dataset**, click **Shared Dataset**.</span></span>

3.  <span data-ttu-id="72702-123">Nel riquadro destro fare clic su **Sfoglia** per selezionare un'origine dati condivisa dal server di report, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="72702-123">In the right pane, click **Browse** to select a shared data source from the report server, and then click **Create**.</span></span> <span data-ttu-id="72702-124">Viene visualizzata la finestra Progettazione query associata all'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="72702-124">The query designer associated with the shared data source opens.</span></span>

4.  <span data-ttu-id="72702-125">In Progettazione query specificare i campi da includere nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="72702-125">In the query designer, specify the fields to include in the dataset.</span></span>

5.  <span data-ttu-id="72702-126">Fare clic su **Esegui** (**!**) per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="72702-126">Click **Run** (**!**) to run the query.</span></span>

6.  <span data-ttu-id="72702-127">Sul pulsante **Generatore report** fare clic su **Salva** o su **Salva con nome** per salvare il set di dati condiviso nel server di report.</span><span class="sxs-lookup"><span data-stu-id="72702-127">On the **Report Builder** button, click **Save** or **Save As** to save the shared dataset to the report server.</span></span>

7.  <span data-ttu-id="72702-128">Per uscire da Generatore report fare clic su **Generatore report**, quindi su **Esci da Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="72702-128">To exit Report Builder, click **Report Builder**, and then click **Exit Report Builder**.</span></span> <span data-ttu-id="72702-129">Per usare report, fare clic su **Generatore report**, quindi su **Nuovo** o **Apri**.</span><span class="sxs-lookup"><span data-stu-id="72702-129">To work with reports, click **Report Builder**, and then click **New** or **Open**.</span></span>

### <a name="to-set-query-parameter-options"></a><span data-ttu-id="72702-130">Per impostare opzioni del parametro query</span><span class="sxs-lookup"><span data-stu-id="72702-130">To set query parameter options</span></span>

1.  <span data-ttu-id="72702-131">Aprire Generatore report.</span><span class="sxs-lookup"><span data-stu-id="72702-131">Open Report Builder.</span></span>

2.  <span data-ttu-id="72702-132">Fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="72702-132">Click **Open**.</span></span>

3.  <span data-ttu-id="72702-133">Selezionare il server di report e scegliere la cartella per l'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="72702-133">Browse to the report server, and select the folder for the shared data source.</span></span>

4.  <span data-ttu-id="72702-134">In **Elementi di tipo**fare clic su Set di dati (\*.rsd) nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="72702-134">In **Items of type**, click Datasets (\*.rsd) in the drop-down list.</span></span>

5.  <span data-ttu-id="72702-135">Selezionare il set di dati condiviso, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="72702-135">Select the shared dataset, and then click **Open**.</span></span> <span data-ttu-id="72702-136">Viene visualizzata la finestra Progettazione query associata.</span><span class="sxs-lookup"><span data-stu-id="72702-136">The associated query designer opens.</span></span>

6.  <span data-ttu-id="72702-137">Sulla barra multifunzione fare clic su **Proprietà set di dati**.</span><span class="sxs-lookup"><span data-stu-id="72702-137">On the Ribbon, click **Dataset Properties**.</span></span>

7.  <span data-ttu-id="72702-138">Fare clic su **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="72702-138">Click **Parameters**.</span></span> <span data-ttu-id="72702-139">In questa pagina impostare un valore predefinito su una costante o un'espressione e contrassegnare il parametro come di sola lettura, che ammette valori Null, o **Ometti dalla query**.</span><span class="sxs-lookup"><span data-stu-id="72702-139">On this page, set a default value to a constant or an expression, mark the parameter as read-only, nullable, or **Omit From Query**.</span></span> <span data-ttu-id="72702-140">Per altre informazioni, vedere [Finestra di dialogo Proprietà set di dati, Parametri &#40;Generatore report&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="72702-140">For more information, see [Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]


### <a name="to-create-a-dataset-from-a-sql-server-relational-database"></a><span data-ttu-id="72702-141">Per creare un set di dati da un database relazionale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="72702-141">To create a dataset from a SQL Server relational database</span></span>

1.  <span data-ttu-id="72702-142">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sul nome dell'origine dati, quindi scegliere **Aggiungi set di dati**.</span><span class="sxs-lookup"><span data-stu-id="72702-142">In the Report Data pane, right-click the name of the data source, and then click **Add Dataset**.</span></span> <span data-ttu-id="72702-143">Viene visualizzata la pagina **Query** della finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="72702-143">The **Query** page of the **Dataset Properties** dialog box opens.</span></span>

2.  <span data-ttu-id="72702-144">In **Nome**digitare un nome per il set di dati oppure accettare quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="72702-144">In **Name**, type a name for the dataset or accept the default name.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="72702-145">Il nome del set di dati viene usato internamente nell'ambito del report.</span><span class="sxs-lookup"><span data-stu-id="72702-145">The dataset name is used internally within the report.</span></span> <span data-ttu-id="72702-146">Per maggiore chiarezza, è consigliabile scegliere per il set di dati un nome che descriva i dati restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="72702-146">For clarity, we recommend that the name of the dataset describe the data that the query returns.</span></span>

3.  <span data-ttu-id="72702-147">In **Origine dati**individuare e selezionare il nome di un'origine dati condivisa o fare clic su **Nuova** per creare una nuova origine dati incorporata.</span><span class="sxs-lookup"><span data-stu-id="72702-147">In **Data source**, browse to and select the name of an existing shared data source, or click **New** to create a new embedded data source.</span></span>

4.  <span data-ttu-id="72702-148">Selezionare un'opzione per **Tipo di query** .</span><span class="sxs-lookup"><span data-stu-id="72702-148">Select a **Query type** option.</span></span> <span data-ttu-id="72702-149">Le opzioni variano a seconda del tipo di origine dati.</span><span class="sxs-lookup"><span data-stu-id="72702-149">Options depend on the data source type.</span></span>

    -   <span data-ttu-id="72702-150">Selezionare **Text** per creare una query basata sul linguaggio di query dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="72702-150">Select **Text** to write a query using the query language of the data source.</span></span>

    -   <span data-ttu-id="72702-151">Selezionare **TableDirect** per restituire tutti i campi di una tabella di un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="72702-151">Select **Table** to return all the fields in a relational database table.</span></span>

    -   <span data-ttu-id="72702-152">Selezionare **StoredProcedure** per eseguire una stored procedure in base al nome.</span><span class="sxs-lookup"><span data-stu-id="72702-152">Select **StoredProcedure** to run a stored procedure by name.</span></span>

5.  <span data-ttu-id="72702-153">In **Query**digitare il nome della query, della stored procedure o della tabella.</span><span class="sxs-lookup"><span data-stu-id="72702-153">In **Query**, type the query, stored procedure, or table name.</span></span> <span data-ttu-id="72702-154">In alternativa, fare clic su **Progettazione query** per aprire la finestra Progettazione query con interfaccia grafica o basata su testo oppure su **Importa** per importare la query da un report esistente.</span><span class="sxs-lookup"><span data-stu-id="72702-154">Alternatively, click **Query Designer** to open the graphical or text-based query designer tool, or **Import** to import the query from an existing report.</span></span>

     <span data-ttu-id="72702-155">In alcuni casi, la raccolta di campi specificata dalla query può essere determinata solo eseguendo la query nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="72702-155">In a few cases, the field collection specified by the query can only be determined by running the query on the data source.</span></span> <span data-ttu-id="72702-156">Una stored procedure, ad esempio, può restituire un set variabile di campi nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="72702-156">For example, a stored procedure may return a variable set of fields in the result set.</span></span> <span data-ttu-id="72702-157">Fare clic su **Aggiorna campi** per eseguire la query nell'origine dati e recuperare i nomi di campo necessari per popolare la raccolta di campi del set di dati nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="72702-157">Click **Refresh Fields** to run the query on the data source and retrieve the field names that are needed to populate the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="72702-158">La raccolta di campi viene visualizzata sotto il nodo del set di dati dopo avere chiuso la finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="72702-158">The field collection appears under the dataset node after you close the **Dataset Properties** dialog box.</span></span>

6.  <span data-ttu-id="72702-159">Nella casella **Timeout**digitare per quanti secondi il server di report deve attendere una risposta dal database.</span><span class="sxs-lookup"><span data-stu-id="72702-159">In **Timeout**, type the number of seconds that the report server waits for a response from the database.</span></span> <span data-ttu-id="72702-160">Il valore predefinito è 0 secondi.</span><span class="sxs-lookup"><span data-stu-id="72702-160">The default value is 0 seconds.</span></span> <span data-ttu-id="72702-161">Quando il valore di timeout è 0 secondi, alla query non viene applicato alcun timeout.</span><span class="sxs-lookup"><span data-stu-id="72702-161">When the time out value is 0 seconds, the query does not time out.</span></span>

7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="72702-162">Il set di dati e la relativa raccolta di campi verranno visualizzati nel riquadro dei dati del report sotto il nodo dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="72702-162">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>

## <a name="see-also"></a><span data-ttu-id="72702-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72702-163">See Also</span></span>
 <span data-ttu-id="72702-164">Set di dati condivisi e set di dati [condivisi &#40;Generatore report e ssrs&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [raccolta campi del set di dati &#40;Generatore report e SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [finestre di progettazione query &#40;](../query-designers-report-builder.md) Generatore report&#41;Generatore report [della Guida per finestre di dialogo, riquadri e procedure guidate](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [aggiungere dati a un report &#40;Generatore report e](report-datasets-ssrs.md) SSRS&#41;[connessioni dati, origini dati e stringhe di connessione in Generatore report](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [set di dati incorporati e condivisi &#40;Generatore report e SSRS&#41;](embedded-and-shared-datasets-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="72702-164">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) [Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](embedded-and-shared-datasets-report-builder-and-ssrs.md)</span></span>


