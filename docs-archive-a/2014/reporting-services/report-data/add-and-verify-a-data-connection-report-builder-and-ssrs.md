---
title: Aggiungere e verificare una connessione dati o un'origine dati (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1d3b2573-e29d-480d-9dde-d26379c86618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d86b3e6598c12545f0e24ef1d162eeb1131bd15d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623851"
---
# <a name="add-and-verify-a-data-connection-or-data-source-report-builder-and-ssrs"></a><span data-ttu-id="c1a36-102">Aggiungere e verificare una connessione dati o un'origine dati (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c1a36-102">Add and Verify a Data Connection or Data Source (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c1a36-103">In Generatore report è possibile aggiungere un'origine dati condivisa dal server di report o creare un'origine dati incorporata per il report in uso.</span><span class="sxs-lookup"><span data-stu-id="c1a36-103">In Report Builder, you can add a shared data source from the report server or create an embedded data source for your report.</span></span> <span data-ttu-id="c1a36-104">In Progettazione report è possibile creare un'origine dati condivisa o un'origine dati incorporata e distribuirla a un server di report.</span><span class="sxs-lookup"><span data-stu-id="c1a36-104">In Report Designer, you can create a shared data source or an embedded data source and deploy it to a report server.</span></span>  
  
 <span data-ttu-id="c1a36-105">Per aggiungere un'origine dati condivisa al report, accedere a un server di report e selezionare un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="c1a36-105">To add a shared data source to your report, browse to a report server and select a shared data source.</span></span> <span data-ttu-id="c1a36-106">L'origine dati condivisa del report punta alla definizione dell'origine dati condivisa nel server di report.</span><span class="sxs-lookup"><span data-stu-id="c1a36-106">The shared data source in your report points to the shared data source definition on the report server.</span></span>  
  
 <span data-ttu-id="c1a36-107">Per creare un'origine dati incorporata, l'utente deve disporre delle informazioni di connessione all'origine esterna di dati oltre a dover conoscere le autorizzazioni necessarie per l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="c1a36-107">To create an embedded data source, you must have connection information to the external source of data and you must know which permissions you need to access the data.</span></span> <span data-ttu-id="c1a36-108">Queste informazioni provengono solitamente dal proprietario dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c1a36-108">This information usually comes from the owner of the data source.</span></span> <span data-ttu-id="c1a36-109">Per verificare che le credenziali specificate siano sufficienti si può testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="c1a36-109">You can test the connection to verify that the credentials that are specified are sufficient.</span></span>  
  
 <span data-ttu-id="c1a36-110">Per altre informazioni, vedere [Connessioni dati, origini dati e stringhe di connessione in Generatore report](../data-connections-data-sources-and-connection-strings-in-report-builder.md) e [Specifica di credenziali in Generatore report](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-110">For more information, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) and [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-reference-to-a-shared-data-source"></a><span data-ttu-id="c1a36-111">Per creare un riferimento a un'origine dati condivisa</span><span class="sxs-lookup"><span data-stu-id="c1a36-111">To create a reference to a shared data source</span></span>  
  
1.  <span data-ttu-id="c1a36-112">Nel riquadro dei dati del report della barra degli strumenti fare clic su **Nuova** , quindi su **Origine dati**.</span><span class="sxs-lookup"><span data-stu-id="c1a36-112">On the toolbar in the Report Data pane, click **New,** and then click **Data Source**.</span></span> <span data-ttu-id="c1a36-113">Verrà visualizzata la finestra di dialogo **Proprietà origine dati** .</span><span class="sxs-lookup"><span data-stu-id="c1a36-113">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c1a36-114">Nella casella di testo **Nome** digitare un nome per l'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="c1a36-114">In the **Name** text box, type a name for the data source.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1a36-115">Questo nome viene salvato nella definizione del report locale</span><span class="sxs-lookup"><span data-stu-id="c1a36-115">This name is saved in the local report definition.</span></span> <span data-ttu-id="c1a36-116">e non viene utilizzato per denominare l'origine dati condivisa nel server di report.</span><span class="sxs-lookup"><span data-stu-id="c1a36-116">This name is not the name of the shared data source on the report server.</span></span>  
  
3.  <span data-ttu-id="c1a36-117">Selezionare **Usa una connessione condivisa o un modello di report**.</span><span class="sxs-lookup"><span data-stu-id="c1a36-117">Select **Use a shared connection or report model**.</span></span> <span data-ttu-id="c1a36-118">Verrà visualizzato l'elenco delle origini dati condivise e dei modelli di report utilizzati di recente.</span><span class="sxs-lookup"><span data-stu-id="c1a36-118">The list of recently used shared data sources and report models appears.</span></span> <span data-ttu-id="c1a36-119">Per selezionarne una da un server di report fare clic su **Sfoglia** e scegliere la cartella nel server di report in cui sono disponibili le origini dati condivise.</span><span class="sxs-lookup"><span data-stu-id="c1a36-119">To select one from a report server, click **Browse** and browse to the folder on the report server where shared data sources are available.</span></span>  
  
4.  <span data-ttu-id="c1a36-120">Selezionare l'origine dati condivisa e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="c1a36-120">Select the shared data source and then click **Open**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="c1a36-121">L'origine dati verrà visualizzata nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="c1a36-121">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="c1a36-122">Per creare un'origine dati incorporata</span><span class="sxs-lookup"><span data-stu-id="c1a36-122">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="c1a36-123">Sulla barra degli strumenti nel riquadro dei dati del report fare clic su **nuovo**e quindi su **origine dati**.</span><span class="sxs-lookup"><span data-stu-id="c1a36-123">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span> <span data-ttu-id="c1a36-124">Verrà visualizzata la finestra di dialogo **Proprietà origine dati** .</span><span class="sxs-lookup"><span data-stu-id="c1a36-124">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c1a36-125">Nella casella di testo **Nome** digitare un nome per l'origine dati oppure accettare quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="c1a36-125">In the **Name** text box, type a name for the data source or accept the default.</span></span>  
  
3.  <span data-ttu-id="c1a36-126">Verificare che l'opzione **Usa una connessione incorporata nel report** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="c1a36-126">Verify that **Use a connection embedded in my report** is selected.</span></span>  
  
    1.  <span data-ttu-id="c1a36-127">Dall'elenco a discesa **Seleziona tipo di connessione** selezionare un tipo di origine dati, ad esempio **Microsoft SQL Server** o **OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="c1a36-127">From the **Select connection type** drop-down list, select a data source type; for example, **Microsoft SQL Server** or **OLE DB**.</span></span>  
  
    2.  <span data-ttu-id="c1a36-128">Specificare una stringa di connessione utilizzando una delle alternative seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1a36-128">Specify a connection string by using one of the following alternatives:</span></span>  
  
    -   <span data-ttu-id="c1a36-129">Digitare la stringa di connessione direttamente nella casella di testo **Stringa di connessione** .</span><span class="sxs-lookup"><span data-stu-id="c1a36-129">Type the connection string directly in the **Connection string** text box.</span></span> <span data-ttu-id="c1a36-130">Per esempi di stringhe di connessione, vedere [Connessioni dati, origini dati e stringhe di connessione in Generatore report](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-130">For a list of example connection strings, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
    -   <span data-ttu-id="c1a36-131">Fare clic sul pulsante relativo all'espressione (**fx)** ) per creare un'espressione che restituisca una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="c1a36-131">Click the expression (**fx)** button to create an expression that evaluates to a connection string.</span></span> <span data-ttu-id="c1a36-132">Nella finestra di dialogo **Espressione** digitare l'espressione nel riquadro relativo.</span><span class="sxs-lookup"><span data-stu-id="c1a36-132">In the **Expression** dialog box, type the expression in the Expression pane.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    -   <span data-ttu-id="c1a36-133">Fare clic su **Compila** per aprire la finestra di dialogo **Proprietà connessione** per il tipo di origine dati scelto nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="c1a36-133">Click **Build** to open the **Connection Properties** dialog box for the data source type that you chose in step 2.</span></span>  
  
         <span data-ttu-id="c1a36-134">Nei campi della finestra di dialogo **Proprietà connessione** inserire le informazioni appropriate per il tipo di origine dati.</span><span class="sxs-lookup"><span data-stu-id="c1a36-134">Fill in the fields in the **Connection Properties** dialog box as appropriate for the data source type.</span></span> <span data-ttu-id="c1a36-135">Le proprietà della connessione includono il tipo e il nome dell'origine dati e le credenziali da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c1a36-135">Connection properties include the type of data source, the name of the data source, and the credentials to use.</span></span> <span data-ttu-id="c1a36-136">Dopo avere specificato i valori in questa finestra di dialogo, fare clic su **Test connessione** per verificare che l'origine dati sia disponibile e che le credenziali specificate siano corrette.</span><span class="sxs-lookup"><span data-stu-id="c1a36-136">After you specify values in this dialog box, click **Test Connection** to verify that the data source is available and that the credentials you specified are correct.</span></span>  
  
4.  <span data-ttu-id="c1a36-137">Fare clic su **Credenziali**.</span><span class="sxs-lookup"><span data-stu-id="c1a36-137">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="c1a36-138">Specificare le credenziali da utilizzare per questa origine dati.</span><span class="sxs-lookup"><span data-stu-id="c1a36-138">Specify the credentials to use for this data source.</span></span> <span data-ttu-id="c1a36-139">Il tipo di credenziali supportato viene determinato dal proprietario dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c1a36-139">The owner of the data source chooses the type of credentials that are supported.</span></span> <span data-ttu-id="c1a36-140">In alcuni casi, il proprietario dell'origine dati gestisce un'origine dati condivisa su un server di report e configura l'origine dati con le credenziali che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c1a36-140">In some cases, the owner of the data source maintains a shared data source on a report server and configures the data source with credentials that you can use.</span></span> <span data-ttu-id="c1a36-141">Per queste informazioni, rivolgersi al proprietario dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c1a36-141">Contact the data source owner for this information.</span></span> <span data-ttu-id="c1a36-142">Per altre informazioni, vedere [Specifica di credenziali in Generatore report](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-142">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="c1a36-143">L'origine dati verrà visualizzata nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="c1a36-143">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-verify-a-data-connection"></a><span data-ttu-id="c1a36-144">Per verificare una connessione dati</span><span class="sxs-lookup"><span data-stu-id="c1a36-144">To verify a data connection</span></span>  
  
1.  <span data-ttu-id="c1a36-145">Sulla barra degli strumenti del riquadro dei dati del report fare doppio clic sull'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c1a36-145">On the toolbar in the Report Data pane, double-click the data source.</span></span> <span data-ttu-id="c1a36-146">Verrà visualizzata la finestra di dialogo **Proprietà origine dati** .</span><span class="sxs-lookup"><span data-stu-id="c1a36-146">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c1a36-147">Fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="c1a36-147">Click **Test Connection**.</span></span>  
  
3.  <span data-ttu-id="c1a36-148">Se la connessione riesce, verrà visualizzato il messaggio seguente: "Creazione connessione completata".</span><span class="sxs-lookup"><span data-stu-id="c1a36-148">If the connection is successful, the following message appears: "Connection created successfully".</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="c1a36-149">In caso contrario, verrà visualizzato il messaggio: "Impossibile connettersi all'origine dati".</span><span class="sxs-lookup"><span data-stu-id="c1a36-149">If the connection is not successful, the following message appears: "Unable to connect to the data source."</span></span>  
  
5.  <span data-ttu-id="c1a36-150">Fare clic su **Dettagli**e utilizzare le informazioni per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="c1a36-150">Click **Details**, and use the information to correct the issue.</span></span>  
  
     <span data-ttu-id="c1a36-151">Per altre informazioni, vedere [Specifica di credenziali in Generatore report](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-151">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1a36-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1a36-152">See Also</span></span>  
 <span data-ttu-id="c1a36-153">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c1a36-153">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="c1a36-154">[Set di set di impostazioni e set di impostazioni di set di report incorporati &#40;Generatore report e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c1a36-154">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c1a36-155">[Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c1a36-155">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c1a36-156">Connessioni dati, origini dati e stringhe di connessione in Generatore report</span><span class="sxs-lookup"><span data-stu-id="c1a36-156">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
