---
title: Recuperare i dati da un modello di data mining (DMX) (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- retrieving report data
- datasets [Reporting Services], with DMX queries
- datasets [Reporting Services], Analysis Services
- queries [Reporting Services], data mining prediction
ms.assetid: d9cd3624-1594-4707-8887-55437dd7e07c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a59184524967a9bfe772e41890afc3b900cc9e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722572"
---
# <a name="retrieve-data-from-a-data-mining-model-dmx-ssrs"></a><span data-ttu-id="70e06-102">Recuperare i dati da un modello di data mining (DMX) (SSRS)</span><span class="sxs-lookup"><span data-stu-id="70e06-102">Retrieve Data from a Data Mining Model (DMX) (SSRS)</span></span>
  <span data-ttu-id="70e06-103">Per usare dati da un modello di data mining di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in un report, è necessario definire un'origine dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e uno o più set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="70e06-103">To use data from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data mining model in your report, you must define a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source and one or more report datasets.</span></span> <span data-ttu-id="70e06-104">Quando si crea la definizione dell'origine dati, è necessario specificare una stringa di connessione e le credenziali, in modo da poter accedere all'origine dati dal computer client.</span><span class="sxs-lookup"><span data-stu-id="70e06-104">When you create the data source definition, you must specify a connection string and credentials so that you can access the data source from your client computer.</span></span>  
  
 <span data-ttu-id="70e06-105">È possibile creare una definizione di origine dati incorporata per l'utilizzo da un solo report oppure una definizione di origine dati condivisa che può essere utilizzata da più report.</span><span class="sxs-lookup"><span data-stu-id="70e06-105">You can create an embedded data source definition for use by a single report or a shared data source definition that can be used by multiple reports.</span></span> <span data-ttu-id="70e06-106">Le procedure in questo argomento descrivono come creare un'origine dati incorporata.</span><span class="sxs-lookup"><span data-stu-id="70e06-106">The procedures in this topic describe how to create an embedded data source.</span></span> <span data-ttu-id="70e06-107">Per altre informazioni sulle origini dati condivise, vedere [Connessioni dati o origini dati condivise e incorporate &#40;Generatore report e SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) e [Creare, modificare ed eliminare origini dati condivise &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="70e06-107">For more information about shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) and [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
 <span data-ttu-id="70e06-108">Dopo aver creato un'origine dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], è possibile creare uno o più set di dati.</span><span class="sxs-lookup"><span data-stu-id="70e06-108">After you create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you can create one or more datasets.</span></span> <span data-ttu-id="70e06-109">Per ogni set di dati, viene utilizzata una finestra Progettazione query DMX (Data Mining Prediction Expression) che consente di creare una query DMX che specifica la raccolta di campi.</span><span class="sxs-lookup"><span data-stu-id="70e06-109">For each dataset, you use a Data Mining Prediction Expression (DMX) query designer to create a DMX query that specifies the field collection.</span></span> <span data-ttu-id="70e06-110">Per altre informazioni, vedere [Interfaccia utente di Progettazione query DMX di Analysis Services](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="70e06-110">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
 <span data-ttu-id="70e06-111">Una volta creato un set di dati, il relativo nome viene visualizzato nel riquadro dei dati del report sotto forma di nodo dell'origine dati corrispondente.</span><span class="sxs-lookup"><span data-stu-id="70e06-111">After you create a dataset, the name of the dataset appears in the Report Data pane as a node under its data source.</span></span>  
  
 <span data-ttu-id="70e06-112">Dopo aver pubblicato il report, potrebbe essere necessario modificare le credenziali per l'origine dati affinché quando il report viene eseguito nel server di report, le autorizzazioni per il recupero dei dati risultino valide.</span><span class="sxs-lookup"><span data-stu-id="70e06-112">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
### <a name="to-create-an-embedded-microsoft-sql-server-analysis-services-data-source"></a><span data-ttu-id="70e06-113">Per creare un'origine dati incorporata di Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="70e06-113">To create an embedded Microsoft SQL Server Analysis Services data source</span></span>  
  
1.  <span data-ttu-id="70e06-114">Nel riquadro dei dati del report della barra degli strumenti fare clic su **Nuova**, quindi su **Origine dati**.</span><span class="sxs-lookup"><span data-stu-id="70e06-114">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="70e06-115">Nella finestra di dialogo **Proprietà origine dati** digitare un nome nella casella di testo **Nome** o accettare il nome predefinito.</span><span class="sxs-lookup"><span data-stu-id="70e06-115">In the **Data Source Properties** dialog box, type a name in the **Name** text box, or accept the default name.</span></span>  
  
3.  <span data-ttu-id="70e06-116">Verificare che l'opzione **Connessione incorporata** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="70e06-116">Verify that **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="70e06-117">Nell'elenco a discesa **Tipo** selezionare **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="70e06-117">From the **Type** drop-down list, select **Microsoft SQL Server Analysis Services**.</span></span>  
  
5.  <span data-ttu-id="70e06-118">Specificare una stringa di connessione appropriata per l'origine dati di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70e06-118">Specify a connection string that works with your [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
     <span data-ttu-id="70e06-119">Contattare l'amministratore del database per ottenere le informazioni di connessione e le credenziali da utilizzare per connettersi all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="70e06-119">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="70e06-120">La stringa di connessione di esempio seguente specifica il database [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] di esempio nel client locale.</span><span class="sxs-lookup"><span data-stu-id="70e06-120">The following connection string example specifies the sample [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] database on the local client.</span></span>  
  
    ```  
    Data Source=localhost;Initial Catalog=AdventureWorksDW2012  
    ```  
  
6.  <span data-ttu-id="70e06-121">Fare clic su **Credenziali**.</span><span class="sxs-lookup"><span data-stu-id="70e06-121">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="70e06-122">Impostare le credenziali da utilizzare per la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="70e06-122">Set the credentials to use to connect to the data source.</span></span> <span data-ttu-id="70e06-123">Per altre informazioni, vedere [Specificare le credenziali e le informazioni sulla connessione per le origini dati del report](../../integration-services/connection-manager/data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="70e06-123">For more information, see [Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70e06-124">Per testare la connessione all'origine dati, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="70e06-124">To test the data source connection, click **Edit**.</span></span> <span data-ttu-id="70e06-125">Nella finestra di dialogo **Proprietà connessione** fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="70e06-125">In the **Connection Properties** dialog box, click **Test Connection**.</span></span> <span data-ttu-id="70e06-126">Se il test ha esito positivo, verrà visualizzato il messaggio informativo "Test della connessione completato".</span><span class="sxs-lookup"><span data-stu-id="70e06-126">If the test is successful, you will see the information message "Test connection succeeded."</span></span> <span data-ttu-id="70e06-127">Se il test non riesce, verrà visualizzato un messaggio di avviso con ulteriori informazioni sui motivi dell'esito negativo del test.</span><span class="sxs-lookup"><span data-stu-id="70e06-127">If the test fails, you will see a warning message with more information about why the test was not successful.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="70e06-128">L'origine dati verrà visualizzata nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="70e06-128">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-a-dataset-for-a-microsoft-sql-server-analysis-services"></a><span data-ttu-id="70e06-129">Per creare un set di dati per un'origine dati di Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="70e06-129">To create a dataset for a Microsoft SQL Server Analysis Services</span></span>  
  
1.  <span data-ttu-id="70e06-130">Nel riquadro **Dati report** fare clic con il pulsante destro del mouse sul nome dell'origine dati che si connette a un'origine dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e quindi scegliere **Aggiungi set di dati**.</span><span class="sxs-lookup"><span data-stu-id="70e06-130">In the **Report Data** pane, right-click the name of the data source that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="70e06-131">Nella finestra di dialogo **Proprietà set di dati** digitare un nome nella casella di testo **Nome** .</span><span class="sxs-lookup"><span data-stu-id="70e06-131">In the **Dataset Properties** dialog box, type a name in the **Name** text box.</span></span>  
  
3.  <span data-ttu-id="70e06-132">Nella casella **Origine dati**verificare che il nome corrisponda a quello di un'origine dati che si connette a un'origine dati di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70e06-132">In the **Data source box**, verify that the name is the name of a data source that connects to an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
4.  <span data-ttu-id="70e06-133">Fare clic su **Progettazione query** per aprire la finestra Progettazione query con interfaccia grafica e creare una query in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="70e06-133">Click **Query Designer** to open the graphical query designer to build a query interactively.</span></span> <span data-ttu-id="70e06-134">Se la finestra si apre in modalità MDX, fare clic su **Tipo di comando DMX** (![Passa alla visualizzazione linguaggio query DMX](../media/rsqdicon-commandtypedmx.gif "Passaggio alla visualizzazione linguaggio di query DMX")) sulla barra degli strumenti per passare alla finestra Progettazione query relativa alla funzionalità di data mining.</span><span class="sxs-lookup"><span data-stu-id="70e06-134">If the query designer opens in MDX mode, click **Command Type DMX** (![Change to DMX query language view](../media/rsqdicon-commandtypedmx.gif "Change to DMX query language view")) on the toolbar to switch to the data mining query designer.</span></span> <span data-ttu-id="70e06-135">Per altre informazioni, vedere [Interfaccia utente di Progettazione query DMX di Analysis Services](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="70e06-135">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
     <span data-ttu-id="70e06-136">In alternativa, per importare una query DMX esistente da un altro report, fare clic su **Importa**e quindi passare al file RDL contenente la query DMX.</span><span class="sxs-lookup"><span data-stu-id="70e06-136">Alternatively, to import an existing DMX query from another report, click **Import**, and then navigate to the .rdl file with the DMX query.</span></span> <span data-ttu-id="70e06-137">L'importazione di una query da un file con estensione dmx non è supportata.</span><span class="sxs-lookup"><span data-stu-id="70e06-137">Importing a query from an .dmx file is not supported.</span></span>  
  
5.  <span data-ttu-id="70e06-138">Dopo avere creato ed eseguito la query per visualizzare i risultati di esempio, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="70e06-138">After you create and run your query to see sample results, click **OK**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="70e06-139">Il set di dati e la relativa raccolta di campi verranno visualizzati nel riquadro dei dati del report sotto il nodo dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="70e06-139">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e06-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70e06-140">See Also</span></span>  
 <span data-ttu-id="70e06-141">[Tipo di connessione di Analysis Services per DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="70e06-141">[Analysis Services Connection Type for DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) </span></span>  
 <span data-ttu-id="70e06-142">[Connessioni dati, origini dati e stringhe di connessione in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="70e06-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="70e06-143">[Raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="70e06-143">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="70e06-144">Set di dati condivisi e incorporati del report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="70e06-144">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
