---
title: 'Esercitazione: Creazione di report drill-through e report principali (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7168c8d3-cef5-4c4a-a0bf-fff1ac5b8b71
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7d30b59a0c5523ed50df06f8587bbd701ae4c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722435"
---
# <a name="tutorial-creating-drillthrough-and-main-reports-report-builder"></a><span data-ttu-id="d94ff-102">Esercitazione: Creazione di report drill-through e report principali (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="d94ff-102">Tutorial: Creating Drillthrough and Main Reports (Report Builder)</span></span>
  <span data-ttu-id="d94ff-103">In questa esercitazione verrà illustrato come creare due tipi di report: un report drill-through e un report principale.</span><span class="sxs-lookup"><span data-stu-id="d94ff-103">This tutorial teaches you how to create two kinds of reports: a drillthrough report and a main report.</span></span> <span data-ttu-id="d94ff-104">I dati di vendita di esempio utilizzati in questi report vengono recuperati da un cubo di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d94ff-104">The sample sales data used in these reports is retrieved from an Analysis Services cube.</span></span> <span data-ttu-id="d94ff-105">Nell'illustrazione seguente vengono mostrati i report creati.</span><span class="sxs-lookup"><span data-stu-id="d94ff-105">The following illustration shows the reports you will create.</span></span>  
  
 <span data-ttu-id="d94ff-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span><span class="sxs-lookup"><span data-stu-id="d94ff-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span></span>  
  
 <span data-ttu-id="d94ff-107">Nella figura seguente viene illustrato il modo in cui il valore del campo, giochi e giocattoli, nel report principale, viene visualizzato nel titolo del report drill-through.</span><span class="sxs-lookup"><span data-stu-id="d94ff-107">The following illustration shows how the field value, Games and Toys, in the main report displays in the drillthrough report's title.</span></span> <span data-ttu-id="d94ff-108">I dati nel report drill-through riguardano la categoria di prodotto Games and Toys.</span><span class="sxs-lookup"><span data-stu-id="d94ff-108">The data in the drillthrough pertains to the Games and Toys product category.</span></span>  
  
 <span data-ttu-id="d94ff-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span><span class="sxs-lookup"><span data-stu-id="d94ff-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="d94ff-110">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="d94ff-110">What You Will Learn</span></span>  
 <span data-ttu-id="d94ff-111">**Nel report drill-through verranno illustrate le procedure per:**</span><span class="sxs-lookup"><span data-stu-id="d94ff-111">**In the drillthrough report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="d94ff-112">Creare un report matrice drill-through e un set di dati da Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="d94ff-112">Create a Drillthrough Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#DMatrixAndDataset)  
  
    1.  [<span data-ttu-id="d94ff-113">Specificare una connessione dati</span><span class="sxs-lookup"><span data-stu-id="d94ff-113">Specify a Data Connection</span></span>](#DConnection)  
  
    2.  [<span data-ttu-id="d94ff-114">Creare una query MDX</span><span class="sxs-lookup"><span data-stu-id="d94ff-114">Create an MDX Query</span></span>](#DMDXQuery)  
  
    3.  [<span data-ttu-id="d94ff-115">Organizzare dati in gruppi</span><span class="sxs-lookup"><span data-stu-id="d94ff-115">Organize Data into Groups Style</span></span>](#DLayout)  
  
    4.  [<span data-ttu-id="d94ff-116">Aggiungere subtotali e totali</span><span class="sxs-lookup"><span data-stu-id="d94ff-116">Add Subtotals and Totals</span></span>](#DTotals)  
  
    5.  [<span data-ttu-id="d94ff-117">Scegliere uno stile</span><span class="sxs-lookup"><span data-stu-id="d94ff-117">Choose a Style</span></span>](#DStyle)  
  
2.  [<span data-ttu-id="d94ff-118">Formattare i dati come valuta</span><span class="sxs-lookup"><span data-stu-id="d94ff-118">Format Data as Currency</span></span>](#DFormat)  
  
3.  [<span data-ttu-id="d94ff-119">Aggiungere colonne per visualizzare i valori delle vendite in grafici sparkline</span><span class="sxs-lookup"><span data-stu-id="d94ff-119">Add columns to Show Sales Values in Sparklines</span></span>](#DSparkline)  
  
4.  [<span data-ttu-id="d94ff-120">Aggiungere un titolo report con nome Product Category</span><span class="sxs-lookup"><span data-stu-id="d94ff-120">Add Report Title with Product Category Name</span></span>](#DReportTitle)  
  
5.  [<span data-ttu-id="d94ff-121">Aggiornare le proprietà dei parametri</span><span class="sxs-lookup"><span data-stu-id="d94ff-121">Update Parameter Properties</span></span>](#DParameter)  
  
6.  [<span data-ttu-id="d94ff-122">Salvare il report in una raccolta di SharePoint</span><span class="sxs-lookup"><span data-stu-id="d94ff-122">Save the Report to a SharePoint Library</span></span>](#DSave)  
  
 <span data-ttu-id="d94ff-123">**Nel report principale verranno illustrate le procedure per:**</span><span class="sxs-lookup"><span data-stu-id="d94ff-123">**In the main report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="d94ff-124">Creare il report di matrice principale e il set di dati da Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="d94ff-124">Create the Main Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#MMatrixAndDataset)  
  
    1.  [<span data-ttu-id="d94ff-125">Specificare una connessione dati</span><span class="sxs-lookup"><span data-stu-id="d94ff-125">Specify a Data Connection</span></span>](#MConnection)  
  
    2.  [<span data-ttu-id="d94ff-126">Creare una query MDX</span><span class="sxs-lookup"><span data-stu-id="d94ff-126">Create an MDX Query</span></span>](#MMDXQuery)  
  
    3.  [<span data-ttu-id="d94ff-127">Organizzare i dati in gruppi</span><span class="sxs-lookup"><span data-stu-id="d94ff-127">Organize Data into Groups</span></span>](#MLayout)  
  
    4.  [<span data-ttu-id="d94ff-128">Aggiungere subtotali e totali</span><span class="sxs-lookup"><span data-stu-id="d94ff-128">Add Subtotals and Totals</span></span>](#MTotals)  
  
    5.  [<span data-ttu-id="d94ff-129">Scegliere uno stile</span><span class="sxs-lookup"><span data-stu-id="d94ff-129">Choose a Style</span></span>](#MStyle)  
  
2.  [<span data-ttu-id="d94ff-130">Rimuovere la riga Totale complessivo</span><span class="sxs-lookup"><span data-stu-id="d94ff-130">Remove the Grand Total Row</span></span>](#MGrandTotal)  
  
3.  [<span data-ttu-id="d94ff-131">Configurare la Casella di testo Azione per il drill-through</span><span class="sxs-lookup"><span data-stu-id="d94ff-131">Configure Text Box Action for Drillthrough</span></span>](#MDrillthrough)  
  
4.  [<span data-ttu-id="d94ff-132">Sostituire i valori numerici con gli indicatori</span><span class="sxs-lookup"><span data-stu-id="d94ff-132">Replace Numeric Values with Indicators</span></span>](#MIndicators)  
  
5.  [<span data-ttu-id="d94ff-133">Aggiornare le proprietà dei parametri</span><span class="sxs-lookup"><span data-stu-id="d94ff-133">Update Parameter Properties</span></span>](#MParameter)  
  
6.  [<span data-ttu-id="d94ff-134">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="d94ff-134">Add a Report Title</span></span>](#MTitle)  
  
7.  [<span data-ttu-id="d94ff-135">Salvare il report in una raccolta di SharePoint</span><span class="sxs-lookup"><span data-stu-id="d94ff-135">Save the Report to a SharePoint Library</span></span>](#MSave)  
  
8.  [<span data-ttu-id="d94ff-136">Eseguire i report principali e drill-through</span><span class="sxs-lookup"><span data-stu-id="d94ff-136">Run the Main and Drillthrough Reports</span></span>](#MRunReports)  
  
 <span data-ttu-id="d94ff-137">Tempo previsto per il completamento di questa esercitazione: 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="d94ff-137">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d94ff-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d94ff-138">Requirements</span></span>  
 <span data-ttu-id="d94ff-139">Questa esercitazione richiede l'accesso al cubo vendite Contoso.</span><span class="sxs-lookup"><span data-stu-id="d94ff-139">This tutorial requires access to the Contoso Sales cube.</span></span> <span data-ttu-id="d94ff-140">Questo requisito si applica sia al drill-through che ai report principali.</span><span class="sxs-lookup"><span data-stu-id="d94ff-140">This requirement applies to both the drillthrough and the main reports.</span></span> <span data-ttu-id="d94ff-141">Per altre informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="d94ff-141">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-drillthrough-report-from-the-table-or-matrix-wizard"></a><a name="DMatrixAndDataset"></a><span data-ttu-id="d94ff-142">1. creare un report drill-through da Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="d94ff-142">1. Create a Drillthrough Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="d94ff-143">Dalla finestra di dialogo Attività iniziali creare un report matrice tramite **Creazione guidata tabella o matrice**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-143">From the Getting Started dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span> <span data-ttu-id="d94ff-144">Nella procedura guidata sono disponibili due modalità: progettazione report e progettazione del set di dati condivisi.</span><span class="sxs-lookup"><span data-stu-id="d94ff-144">There are two modes available in the wizard: report design and shared dataset design.</span></span> <span data-ttu-id="d94ff-145">In questa esercitazione si utilizzerà modalità progettazione report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-145">In this tutorial, you will use the report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="d94ff-146">Per creare un nuovo report</span><span class="sxs-lookup"><span data-stu-id="d94ff-146">To create a new report</span></span>  
  
1.  <span data-ttu-id="d94ff-147">Fare clic sul pulsante **Start**, scegliere **programmi**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Generatore report**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-147">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="d94ff-148">Verrà visualizzata la finestra di dialogo **Attività iniziali**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-148">The **Getting Started** dialog box opens.</span></span> <span data-ttu-id="d94ff-149">Se non viene visualizzato, fare clic sul pulsante **Generatore report** , quindi su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-149">If it does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="d94ff-150">Nel riquadro sinistro verificare che sia selezionata l'opzione **Nuovo report** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-150">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="d94ff-151">Nel riquadro destro verificare che sia selezionata **Creazione guidata tabella o matrice** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-151">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="DConnection"></a><span data-ttu-id="d94ff-152">1a.</span><span class="sxs-lookup"><span data-stu-id="d94ff-152">1a.</span></span> <span data-ttu-id="d94ff-153">Specificare una connessione dati</span><span class="sxs-lookup"><span data-stu-id="d94ff-153">Specify a Data Connection</span></span>  
 <span data-ttu-id="d94ff-154">Una connessione dati contiene le informazioni necessarie per connettersi a un'origine dati esterna, ad esempio cubo di Analysis Services o un database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d94ff-154">A data connection contains the information necessary to connect to an external data source such as an Analysis Services cube or a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="d94ff-155">Per specificare una connessione dati, è possibile utilizzare un'origine dati condivisa dal server di report o creare un'origine dati incorporata che sia utilizzata solo in questo report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-155">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span> <span data-ttu-id="d94ff-156">In questa esercitazione si utilizzerà un'origine dati incorporata.</span><span class="sxs-lookup"><span data-stu-id="d94ff-156">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="d94ff-157">Per altre informazioni sull'uso di un'origine dati condivisa, vedere [Modalità alternative di acquisizione di una connessione dati &#40;Generatore report&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="d94ff-157">To learn more about using a shared data source, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="d94ff-158">Per creare un'origine dati incorporata</span><span class="sxs-lookup"><span data-stu-id="d94ff-158">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="d94ff-159">Nella pagina **Scegliere un set di dati** selezionare **Crea un set di dati**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-159">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="d94ff-160">Verrà visualizzata la pagina **Scegliere una connessione a un'origine dei dati** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-160">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="d94ff-161">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-161">Click **New**.</span></span> <span data-ttu-id="d94ff-162">Verrà visualizzata la finestra di dialogo **Proprietà origine dati** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-162">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="d94ff-163">In **Nome**digitare **Online and Reseller Sales Detail** come nome per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d94ff-163">In **Name**, type **Online and Reseller Sales Detail** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="d94ff-164">In **Seleziona il tipo di connessione**, scegliere **Microsoft SQL Server Analysis Services**, quindi fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-164">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="d94ff-165">In **Origine dati**verificare che l'origine dati sia **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-165">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="d94ff-166">In **Nome server**, digitare il nome di un server nel quale è installata un'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d94ff-166">In **Server name**, type the name of a server where an instance of Analysis Services is installed.</span></span>  
  
7.  <span data-ttu-id="d94ff-167">In **Selezionare o immettere un nome di database**specificare il cubo Contoso.</span><span class="sxs-lookup"><span data-stu-id="d94ff-167">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="d94ff-168">Verificare che **Stringa di connessione** contenga la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="d94ff-168">Verify that **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
     <span data-ttu-id="d94ff-169">`<servername>` è il nome di un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con installato Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d94ff-169">The `<servername>` is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with Analysis Services installed.</span></span>  
  
10. <span data-ttu-id="d94ff-170">Fare clic su **Tipo credenziali**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-170">Click **Credentials type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d94ff-171">A seconda di come vengono configurate le autorizzazioni sull'origine dati, potrebbe essere necessario modificare le opzioni di autenticazione predefinite.</span><span class="sxs-lookup"><span data-stu-id="d94ff-171">Depending on how permissions are configured on the data source, you might need to change the default authentication options.</span></span> <span data-ttu-id="d94ff-172">Per altre informazioni, vedere [Sicurezza &#40;Generatore report&#41;](report-builder/security-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="d94ff-172">For more information, see [Security &#40;Report Builder&#41;](report-builder/security-report-builder.md).</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="d94ff-173">Viene visualizzata la pagina **Scegliere una connessione a un'origine dei dati** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-173">The **Choose a connection to a data source** page appears.</span></span>  
  
12. <span data-ttu-id="d94ff-174">Per verificare che la connessione all'origine dati avvenga correttamente, fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-174">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="d94ff-175">Viene visualizzata la connessione al messaggio **creata correttamente** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-175">The message **Connection created successfully** appears.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="d94ff-176">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-176">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="DMDXQuery"></a><span data-ttu-id="d94ff-177">1b.</span><span class="sxs-lookup"><span data-stu-id="d94ff-177">1b.</span></span> <span data-ttu-id="d94ff-178">Creare una query MDX</span><span class="sxs-lookup"><span data-stu-id="d94ff-178">Create an MDX Query</span></span>  
 <span data-ttu-id="d94ff-179">In un report, è possibile utilizzare un set di dati condiviso che dispone di una query predefinita oppure è possibile creare un set di dati incorporato da utilizzare solo nel report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-179">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="d94ff-180">In questa esercitazione si creerà un set di dati incorporato.</span><span class="sxs-lookup"><span data-stu-id="d94ff-180">In this tutorial, you will create an embedded dataset.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="d94ff-181">Per creare filtri query</span><span class="sxs-lookup"><span data-stu-id="d94ff-181">To create query filters</span></span>  
  
1.  <span data-ttu-id="d94ff-182">Nel riquadro metadati della pagina **Progetta query** fare clic sul pulsante **(...)**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-182">On the **Design a query** page, in the Metadata pane, click the button **(...)**.</span></span>  
  
2.  <span data-ttu-id="d94ff-183">Nella finestra di dialogo **Seleziona cubo** fare clic su Vendite, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-183">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="d94ff-184">Se non si vuole creare manualmente la query MDX, fare clic sull'icona ![Passa alla modalità progettazione](media/rsqdicon-designmode.gif "Passare alla modalità progettazione"), impostare Progettazione query in modalità query, incollare la query MDX completata nella finestra di progettazione query e quindi procedere con il passaggio 6 in [Per creare il set di dati](#DSkip).</span><span class="sxs-lookup"><span data-stu-id="d94ff-184">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 6 in [To create the dataset](#DSkip).</span></span>  
  
    ```  
    SELECT NON EMPTY { [Measures].[Sales Amount], [Measures].[Sales Return Amount] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS * [Product].[Product Subcategory Name].[Product Subcategory Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGS  
    ```  
  
3.  <span data-ttu-id="d94ff-185">Nel riquadro Gruppo di misure, espandere Canale, quindi trascinare Nome canale nella colonna **Gerarchia** del riquadro filtro.</span><span class="sxs-lookup"><span data-stu-id="d94ff-185">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="d94ff-186">Il nome della dimensione Canale viene aggiunto automaticamente alla colonna **Dimensione** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-186">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="d94ff-187">Non modificare le colonne **Dimensione** o **Operatore** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-187">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="d94ff-188">Per aprire l'elenco **Espressione filtro** , fare clic sulla freccia in giù nella colonna **Espressione filtro** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-188">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="d94ff-189">Nell'elenco dell'espressione filtro, espandere **Tutti i canali**, fare clic su **Online**, fare clic su **Rivenditore**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-189">In the filter expression list, expand **All Channel**, click **Online**, click **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d94ff-190">Ora la query include un filtro per includere solo questi canali: Online e Rivenditore.</span><span class="sxs-lookup"><span data-stu-id="d94ff-190">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="d94ff-191">Espandere la dimensione Territorio di vendita, quindi trascinare Gruppo territorio di vendita nella colonna **Gerarchia** , sotto **Nome canale**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-191">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column (below **Channel Name**).</span></span>  
  
7.  <span data-ttu-id="d94ff-192">Aprire l'elenco **Espressione filtro** , espandere **Tutte le aree di vendita**, fare clic su **America del Nord**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-192">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d94ff-193">La query dispone ora di un filtro per includere solo le vendite in America del Nord.</span><span class="sxs-lookup"><span data-stu-id="d94ff-193">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="d94ff-194">Nel riquadro Gruppo di misure espandere Data, quindi trascinare Anno di calendario nella colonna **Gerarchia** del riquadro filtro.</span><span class="sxs-lookup"><span data-stu-id="d94ff-194">In the Measure Group pane, expand Date, and then drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="d94ff-195">Il nome della dimensione Data viene aggiunto automaticamente alla colonna **Dimensione** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-195">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="d94ff-196">Non modificare le colonne **Dimensione** o **Operatore** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-196">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="d94ff-197">Per aprire l'elenco **Espressione filtro** , fare clic sulla freccia in giù nella colonna **Espressione filtro** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-197">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="d94ff-198">Nell'elenco dell'espressione filtro, espandere **Tutte le date**, fare clic su **Anno 2009**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-198">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d94ff-199">La query include ora un filtro per includere solo l'anno solare 2009.</span><span class="sxs-lookup"><span data-stu-id="d94ff-199">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="d94ff-200">Per creare il parametro.</span><span class="sxs-lookup"><span data-stu-id="d94ff-200">To create the parameter</span></span>  
  
1.  <span data-ttu-id="d94ff-201">Espandere la dimensione Prodotto, quindi trascinare il membro Product Category Name nella colonna **Gerarchia** sotto **Anno di calendario**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-201">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Calendar Year**.</span></span>  
  
2.  <span data-ttu-id="d94ff-202">Aprire l 'elenco **Espressione filtro** , fare clic su **Tutti i prodotti**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-202">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d94ff-203">Fare clic sulla casella di controllo **Parametro** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-203">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="d94ff-204">La query ora include il parametro ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="d94ff-204">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d94ff-205">Il parametro contiene i nomi di categorie di prodotto.</span><span class="sxs-lookup"><span data-stu-id="d94ff-205">The parameter contains the names of product categories.</span></span> <span data-ttu-id="d94ff-206">Per visualizzare il report drill-through che viene aperto quando si fa clic sul collegamento drill-through nel report principale, è necessario essere connessi a un server di report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-206">When you click a product category name in the main report, its name is passed to the drillthrough report by using this parameter.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="DSkip"></a><span data-ttu-id="d94ff-207">Per creare il set di dati</span><span class="sxs-lookup"><span data-stu-id="d94ff-207">To create the dataset</span></span>  
  
1.  <span data-ttu-id="d94ff-208">Trascinare Nome canale dalla dimensione Canale al riquadro dei dati.</span><span class="sxs-lookup"><span data-stu-id="d94ff-208">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="d94ff-209">Trascinare Product Category Name dalla dimensione Prodotto al riquadro dei dati, quindi posizionarlo a destra di Nome canale.</span><span class="sxs-lookup"><span data-stu-id="d94ff-209">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="d94ff-210">Trascinare Product Subcategory Name dalla dimensione Prodotto al riquadro dei dati, quindi posizionarlo a destra di Product Category Name.</span><span class="sxs-lookup"><span data-stu-id="d94ff-210">From the Product dimension, drag Product Subcategory Name to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="d94ff-211">Nel riquadro dei metadati espandere **Misure**, quindi espandere Vendite.</span><span class="sxs-lookup"><span data-stu-id="d94ff-211">In the Metadata pane, expand **Measure**, and then expand Sales.</span></span>  
  
5.  <span data-ttu-id="d94ff-212">Trascinare la misura Importo vendite nel riquadro dei dati, quindi posizionarlo a destra di Product Subcategory Name.</span><span class="sxs-lookup"><span data-stu-id="d94ff-212">Drag the Sales Amount measure to the data pane, and then place it to the right of Product Subcategory Name.</span></span>  
  
6.  <span data-ttu-id="d94ff-213">Sulla barra degli strumenti Progettazione query fare clic su **Esegui (!)**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-213">On the query designer toolbar, click **Run (!)**.</span></span>  
  
7.  <span data-ttu-id="d94ff-214">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-214">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="DLayout"></a><span data-ttu-id="d94ff-215">1C.</span><span class="sxs-lookup"><span data-stu-id="d94ff-215">1c.</span></span> <span data-ttu-id="d94ff-216">Organizzare i dati in gruppi</span><span class="sxs-lookup"><span data-stu-id="d94ff-216">Organize Data into Groups</span></span>  
 <span data-ttu-id="d94ff-217">Quando si selezionano dei campi in cui raggruppare i dati, si progetta una matrice con righe e colonne che visualizzano dati dettagliati e dati aggregati.</span><span class="sxs-lookup"><span data-stu-id="d94ff-217">When you select the fields on which to group the data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="d94ff-218">Per organizzare i dati in gruppi</span><span class="sxs-lookup"><span data-stu-id="d94ff-218">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="d94ff-219">Fare clic su **Progettazione**per passare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="d94ff-219">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="d94ff-220">Nella pagina **Disponi campi** trascinare Product_Subcategory_Name in **Gruppi di righe**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-220">On the **Arrange fields** page, drag Product_Subcategory_Name to **Row groups**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d94ff-221">Nei nomi, gli spazi nei nomi vengono sostituiti da caratteri di sottolineatura (_).</span><span class="sxs-lookup"><span data-stu-id="d94ff-221">The spaces in the names are replaced with underscores (_).</span></span> <span data-ttu-id="d94ff-222">Ad esempio Product Category Name è Product_Category_Name.</span><span class="sxs-lookup"><span data-stu-id="d94ff-222">For example Product Category Name is Product_Category_Name.</span></span>  
  
3.  <span data-ttu-id="d94ff-223">Trascinare Channel_Name in **Gruppi di colonne**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-223">Drag Channel_Name to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="d94ff-224">Trascinare Sales_Amount in **Valori**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-224">Drag Sales_Amount to **Values**.</span></span>  
  
     <span data-ttu-id="d94ff-225">Sales_Amount viene aggregato automaticamente dalla funzione Sum, ovvero l'aggregazione predefinita per i campi numerici.</span><span class="sxs-lookup"><span data-stu-id="d94ff-225">Sales_Amount is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="d94ff-226">Il valore è `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="d94ff-226">The value is `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="d94ff-227">È possibile aprire l'elenco a discesa (senza modificare la funzione aggregata) per visualizzare le altre funzioni di aggregazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="d94ff-227">To view the other aggregate functions available, open the drop-down list (do not change the aggregate function).</span></span>  
  
5.  <span data-ttu-id="d94ff-228">Trascinare Sales_Return_Amount in **Valori**, quindi posizionarlo sotto `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="d94ff-228">Drag Sales_Return_Amount to **Values**, and then place it below `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="d94ff-229">I passaggi 4 e 5 consentono di specificare i dati da visualizzare nella matrice.</span><span class="sxs-lookup"><span data-stu-id="d94ff-229">Steps 4 and 5 specify the data to display in the matrix.</span></span>  
  
6.  <span data-ttu-id="d94ff-230">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-230">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="DTotals"></a><span data-ttu-id="d94ff-231">1D.</span><span class="sxs-lookup"><span data-stu-id="d94ff-231">1d.</span></span> <span data-ttu-id="d94ff-232">Aggiungere subtotali e totali</span><span class="sxs-lookup"><span data-stu-id="d94ff-232">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="d94ff-233">Dopo avere creato i gruppi, è possibile aggiungere e formattare delle righe nelle quali visualizzare i valori di aggregazione per i campi.</span><span class="sxs-lookup"><span data-stu-id="d94ff-233">After you create groups, you can add and format rows where the aggregate values for the fields will display.</span></span> <span data-ttu-id="d94ff-234">È anche possibile scegliere se mostrare tutti i dati o lasciare che sia l'utente a espandere e comprimere in modo interattivo i dati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="d94ff-234">You can also choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="d94ff-235">Per aggiungere subtotali e totali</span><span class="sxs-lookup"><span data-stu-id="d94ff-235">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="d94ff-236">Nella pagina **scegliere il layout** , in **Opzioni**, verificare che sia selezionata l'opzione **Mostra subtotali e totali** complessivi.</span><span class="sxs-lookup"><span data-stu-id="d94ff-236">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="d94ff-237">Nel riquadro di anteprima della creazione guidata viene visualizzata una matrice con quattro righe.</span><span class="sxs-lookup"><span data-stu-id="d94ff-237">The wizard Preview pane displays a matrix with four rows.</span></span>  
  
2.  <span data-ttu-id="d94ff-238">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-238">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="DStyle"></a><span data-ttu-id="d94ff-239">1e.</span><span class="sxs-lookup"><span data-stu-id="d94ff-239">1e.</span></span> <span data-ttu-id="d94ff-240">Scegliere uno stile</span><span class="sxs-lookup"><span data-stu-id="d94ff-240">Choose a Style</span></span>  
 <span data-ttu-id="d94ff-241">Uno stile specifica lo stile del carattere, il set di colori e uno stile del bordo.</span><span class="sxs-lookup"><span data-stu-id="d94ff-241">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="d94ff-242">Per specificare uno stile</span><span class="sxs-lookup"><span data-stu-id="d94ff-242">To specify a style</span></span>  
  
1.  <span data-ttu-id="d94ff-243">Nel riquadro Stili della pagina **scegliere uno stile** selezionare Slate.</span><span class="sxs-lookup"><span data-stu-id="d94ff-243">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="d94ff-244">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-244">Click **Finish**.</span></span>  
  
     <span data-ttu-id="d94ff-245">La tabella viene aggiunta all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d94ff-245">The table is added to the design surface.</span></span>  
  
3.  <span data-ttu-id="d94ff-246">Fare clic su **Esegui (!)** per visualizzare un'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-246">To preview the report, click **Run (!)**.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="DFormat"></a><span data-ttu-id="d94ff-247">2. formattare i dati come valuta</span><span class="sxs-lookup"><span data-stu-id="d94ff-247">2. Format Data as Currency</span></span>  
 <span data-ttu-id="d94ff-248">Applicare la formattazione della valuta ai campi dell'importo vendite nel report drill-through.</span><span class="sxs-lookup"><span data-stu-id="d94ff-248">Apply currency formatting to the sales amount fields in the drillthrough report.</span></span>  
  
#### <a name="to-format-data-as-currency"></a><span data-ttu-id="d94ff-249">Per formattare i dati come valuta</span><span class="sxs-lookup"><span data-stu-id="d94ff-249">To format data as currency</span></span>  
  
1.  <span data-ttu-id="d94ff-250">Fare clic su **Progettazione**per passare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="d94ff-250">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="d94ff-251">Per selezionare e formattare contemporaneamente più celle, premere CTRL, quindi selezionare le celle che contengono i dati di vendita numerici.</span><span class="sxs-lookup"><span data-stu-id="d94ff-251">To select and format multiple cells at one time, press the Ctrl key, and then select the cells that contain the numeric sales data.</span></span>  
  
3.  <span data-ttu-id="d94ff-252">Nel gruppo **Numero** della scheda **Home** fare clic su **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-252">On the **Home** tab, in the **Number** group, click **Currency**.</span></span>  
  
##  <a name="3-add-columns-to-show-sales-values-in-sparklines"></a><a name="DSparkline"></a><span data-ttu-id="d94ff-253">3. aggiungere colonne per visualizzare i valori delle vendite nei grafici sparkline</span><span class="sxs-lookup"><span data-stu-id="d94ff-253">3. Add Columns to Show Sales Values in Sparklines</span></span>  
 <span data-ttu-id="d94ff-254">Anziché mostrare vendite e margini di profitto come valori in valuta, il report mostra i valori in un grafico sparkline.</span><span class="sxs-lookup"><span data-stu-id="d94ff-254">Instead of showing sales and sales returns as currency values, the report shows the values in a sparkline.</span></span>  
  
#### <a name="to-add-sparklines-to-columns"></a><span data-ttu-id="d94ff-255">Per aggiungere grafici sparkline alle colonne</span><span class="sxs-lookup"><span data-stu-id="d94ff-255">To add sparklines to columns</span></span>  
  
1.  <span data-ttu-id="d94ff-256">Fare clic su **Progettazione**per passare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="d94ff-256">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="d94ff-257">Nel gruppo Totale della matrice fare clic con il pulsante destro del mouse sulla colonna **Importo vendite** , scegliere **Inserisci colonna**e fare clic su **A destra**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-257">In the Total group of the matrix, right-click the **Sales Amount** column, click **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="d94ff-258">Una colonna vuota viene aggiunta a destra di **Importo vendite**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-258">An empty column is added to the right of **Sales Amount**.</span></span>  
  
3.  <span data-ttu-id="d94ff-259">Sulla barra multifunzione fare clic su **Rettangolo**, quindi fare clic sulla cella vuota a destra della cella `[Sum(Sales_Amount)]` , nel gruppo di righe [Product_Subcategory].</span><span class="sxs-lookup"><span data-stu-id="d94ff-259">On the ribbon, click **Rectangle**, and then click the empty cell to the right of the `[Sum(Sales_Amount)]` cell in the [Product_Subcategory] row group.</span></span>  
  
4.  <span data-ttu-id="d94ff-260">Sulla barra multifunzione, fare clic sull'icona **Grafico sparkline** e fare clic sulla cella dove è stato aggiunto il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="d94ff-260">On the ribbon, click the **Sparkline** icon, and then click the cell where the rectangle was added.</span></span>  
  
5.  <span data-ttu-id="d94ff-261">Nella finestra di dialogo **Seleziona tipo di grafico sparkline** , verificare che sia selezionato il tipo **Colonna** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-261">In the **Select Sparkline Type** dialog box, verify that **Column** type is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="d94ff-262">Fare clic con il pulsante destro del mouse sul grafico sparkline.</span><span class="sxs-lookup"><span data-stu-id="d94ff-262">Right-click the sparkline.</span></span>  
  
8.  <span data-ttu-id="d94ff-263">Nel riquadro Dati grafico fare clic sull'icona **Aggiungi campo** , quindi fare clic su Sales_Amount.</span><span class="sxs-lookup"><span data-stu-id="d94ff-263">In the Chart Data pane, click the **Add field** icon, and then click Sales_Amount.</span></span>  
  
9. <span data-ttu-id="d94ff-264">Fare clic con il pulsante destro del mouse sulla colonna `Sales_Return_Amount` e quindi aggiungere una colonna alla destra.</span><span class="sxs-lookup"><span data-stu-id="d94ff-264">Right-click the `Sales_Return_Amount` column, and then add a column to the right of it.</span></span>  
  
10. <span data-ttu-id="d94ff-265">Ripetere i passaggi da 2 a 6.</span><span class="sxs-lookup"><span data-stu-id="d94ff-265">Repeat steps 2 through 6.</span></span>  
  
11. <span data-ttu-id="d94ff-266">Fare clic con il pulsante destro del mouse sul grafico sparkline.</span><span class="sxs-lookup"><span data-stu-id="d94ff-266">Right-click the sparkline.</span></span>  
  
12. <span data-ttu-id="d94ff-267">Nel riquadro Dati grafico fare clic sull'icona **Aggiungi campo** , quindi fare clic su Sales_Return_Amount.</span><span class="sxs-lookup"><span data-stu-id="d94ff-267">In the Chart Data pane, click the **Add field** icon, and then click Sales_Return_Amount.</span></span>  
  
13. <span data-ttu-id="d94ff-268">Fare clic su **Esegui**per visualizzare un'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-268">To preview the report, click **Run**.</span></span>  
  
##  <a name="4-add-report-title-with-product-category-name"></a><a name="DReportTitle"></a><span data-ttu-id="d94ff-269">4. aggiungere un titolo al report con il nome della categoria di prodotto</span><span class="sxs-lookup"><span data-stu-id="d94ff-269">4. Add Report Title with Product Category Name</span></span>  
 <span data-ttu-id="d94ff-270">Nella parte superiore del report viene visualizzato il titolo del report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-270">A report title appears at the top of the report.</span></span> <span data-ttu-id="d94ff-271">È possibile posizionare il titolo del report in un'apposita intestazione oppure, se il report ne è privo, in una casella di testo nella parte superiore del corpo del report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-271">You can place the report title in a report header or, if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="d94ff-272">In questa esercitazione sarà utilizzata la casella di testo che viene posizionata automaticamente nella parte superiore del corpo del report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-272">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="d94ff-273">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="d94ff-273">To add a report title</span></span>  
  
1.  <span data-ttu-id="d94ff-274">Fare clic su **Progettazione**per passare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="d94ff-274">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="d94ff-275">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-275">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="d94ff-276">Digitare **Vendite e margini per categoria:**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-276">Type **Sales and Returns for Category:**.</span></span>  
  
4.  <span data-ttu-id="d94ff-277">Fare clic con il pulsante destro del mouse, quindi fare clic su **Crea segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-277">Right-click, and then click **Create Placeholder**.</span></span>  
  
5.  <span data-ttu-id="d94ff-278">Fare clic sul pulsante **(fx)** a destra dell'elenco **Valore** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-278">Click the **(fx)** button to the right of the **Value** list.</span></span>  
  
6.  <span data-ttu-id="d94ff-279">Nel riquadro Categoria della finestra di dialogo **Espressione** fare clic su **Set di dati**, quindi nell'elenco **Valori** fare doppio clic su `First(Product_Category_Name)`.</span><span class="sxs-lookup"><span data-stu-id="d94ff-279">In the **Expression** dialog box, in the Category pane, click **Dataset**, and then in the **Values** list double-click `First(Product_Category_Name)`.</span></span>  
  
     <span data-ttu-id="d94ff-280">La casella **Espressione** contiene l'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="d94ff-280">The **Expression** box contains the following expression:</span></span>  
  
    ```  
    =First(Fields!Product_Category_Name.Value, "DataSet1")  
    ```  
  
7.  <span data-ttu-id="d94ff-281">Fare clic su **Esegui**per visualizzare un'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-281">To preview the report, click **Run**.</span></span>  
  
 <span data-ttu-id="d94ff-282">Il titolo del report include il nome della prima categoria di prodotto.</span><span class="sxs-lookup"><span data-stu-id="d94ff-282">The report title includes the name of the first product category.</span></span> <span data-ttu-id="d94ff-283">In un secondo momento, dopo avere eseguito questo report come report drill-through, il nome della categoria di prodotto si modificherà dinamicamente per riflettere il nome della categoria di prodotto selezionata nel report principale.</span><span class="sxs-lookup"><span data-stu-id="d94ff-283">Later, after you run this report as a drillthrough report, the product category name will dynamically change to reflect the name of the product category that was clicked in the main report.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="DParameter"></a><span data-ttu-id="d94ff-284">5. aggiornare le proprietà del parametro</span><span class="sxs-lookup"><span data-stu-id="d94ff-284">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="d94ff-285">Per impostazione predefinita i parametri sono visibili; questa impostazione non è adatta per questo report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-285">By default parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="d94ff-286">È possibile aggiornare le proprietà dei parametri per il report drill-through.</span><span class="sxs-lookup"><span data-stu-id="d94ff-286">You will update the parameter properties for the drillthrough report.</span></span>  
  
#### <a name="to-hide-a-parameter"></a><span data-ttu-id="d94ff-287">Per nascondere un parametro:</span><span class="sxs-lookup"><span data-stu-id="d94ff-287">To hide a parameter</span></span>  
  
1.  <span data-ttu-id="d94ff-288">Nel riquadro Dati report espandere **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-288">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="d94ff-289">Fare clic con il pulsante destro del mouse su \@ ProductProductCategoryName e quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-289">Right-click \@ProductProductCategoryName, and then click **Parameter Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d94ff-290">Il \@ carattere accanto al nome indica che questo è un parametro.</span><span class="sxs-lookup"><span data-stu-id="d94ff-290">The \@ character next to the name indicates that this is a parameter.</span></span>  
  
3.  <span data-ttu-id="d94ff-291">Nella scheda **Generale** fare clic su **Nascondi**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-291">On the **General** tab, click **Hidden**.</span></span>  
  
4.  <span data-ttu-id="d94ff-292">Nella casella **Messaggio di richiesta** , digitare **Categoria prodotto**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-292">In the **Prompt** box, type **Product Category**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d94ff-293">Poiché il parametro è nascosto, questo prompt non viene mai utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d94ff-293">Because the parameter is hidden, this prompt is never used.</span></span>  
  
5.  <span data-ttu-id="d94ff-294">Facoltativamente, fare clic su **Valori disponibili** e **Valori predefiniti** e controllare le opzioni.</span><span class="sxs-lookup"><span data-stu-id="d94ff-294">Optionally, click **Available Values** and **Default Values** and review their options.</span></span> <span data-ttu-id="d94ff-295">Non modificare le opzioni in queste schede.</span><span class="sxs-lookup"><span data-stu-id="d94ff-295">Do not change any options on these tabs.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report-to-a-sharepoint-library"></a><a name="DSave"></a><span data-ttu-id="d94ff-296">6. salvare il report in una raccolta di SharePoint</span><span class="sxs-lookup"><span data-stu-id="d94ff-296">6. Save the Report to a SharePoint Library</span></span>  
 <span data-ttu-id="d94ff-297">È possibile salvare il report in una raccolta di SharePoint, in un server di report o nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="d94ff-297">You can save the report to a SharePoint library, report server, or your computer.</span></span> <span data-ttu-id="d94ff-298">Se il report viene salvato nel computer locale, non saranno disponibili alcune caratteristiche di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , ad esempio le parti del report e i sottoreport.</span><span class="sxs-lookup"><span data-stu-id="d94ff-298">If you save the report to your computer, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span> <span data-ttu-id="d94ff-299">In questa esercitazione verranno illustrate le procedure per il salvataggio del report nella raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d94ff-299">In this tutorial, you will save the report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="d94ff-300">Per salvare il report</span><span class="sxs-lookup"><span data-stu-id="d94ff-300">To save the report</span></span>  
  
1.  <span data-ttu-id="d94ff-301">Dal pulsante Generatore report fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-301">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="d94ff-302">Verrà visualizzata la finestra di dialogo **Salva come report** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-302">The **Save As Report** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d94ff-303">Se si sta salvando di nuovo un report, questo viene automaticamente risalvato nel relativo percorso precedente.</span><span class="sxs-lookup"><span data-stu-id="d94ff-303">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="d94ff-304">Usare l'opzione **Salva con nome** per modificare il percorso.</span><span class="sxs-lookup"><span data-stu-id="d94ff-304">To change the location, use the **Save As** option.</span></span>  
  
2.  <span data-ttu-id="d94ff-305">Per visualizzare un elenco di server di report e di siti di SharePoint usati di recente, fare clic su **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-305">To show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="d94ff-306">Selezionare o digitare il nome del sito di SharePoint per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-306">Select or type the name of the SharePoint site where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="d94ff-307">La sintassi dell'URL della raccolta di SharePoint è la seguente:</span><span class="sxs-lookup"><span data-stu-id="d94ff-307">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
4.  <span data-ttu-id="d94ff-308">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-308">Click **Save**.</span></span>  
  
     <span data-ttu-id="d94ff-309">**Siti e server recenti** elenca le librerie sul sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d94ff-309">**Recent Sites and Servers** lists the libraries on the SharePoint site.</span></span>  
  
5.  <span data-ttu-id="d94ff-310">Passare alla raccolta dove si salverà il report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-310">Navigate to the library where you will save the report.</span></span>  
  
6.  <span data-ttu-id="d94ff-311">Nella casella **Nome** sostituire il nome predefinito con **ResellerVSOnlineDrillthrough**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-311">In the **Name** box, replace the default name with **ResellerVSOnlineDrillthrough**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d94ff-312">Verrà descritta la procedura per salvare il report principale nella stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="d94ff-312">You will save the main report to the same location.</span></span> <span data-ttu-id="d94ff-313">Se si vuole salvare il report principale e report drill-through in librerie o siti diversi, è necessario aggiornare il percorso dell'azione **Vai al report** nel report principale.</span><span class="sxs-lookup"><span data-stu-id="d94ff-313">If you want to save the main and drillthrough reports to different sites or libraries, you must update the path of the **Go to report** action in the main report.</span></span>  
  
7.  <span data-ttu-id="d94ff-314">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-314">Click **Save**.</span></span>  
  
##  <a name="1-create-a-new-report-from-the-table-or-matrix-wizard"></a><a name="MMatrixAndDataset"></a><span data-ttu-id="d94ff-315">1. creare un nuovo report da Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="d94ff-315">1. Create a New Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="d94ff-316">Dalla finestra di dialogo **Attività iniziali** creare un report matrice tramite **Creazione guidata tabella o matrice**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-316">From the **Getting Started** dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="d94ff-317">Per creare un nuovo report</span><span class="sxs-lookup"><span data-stu-id="d94ff-317">To create a new report</span></span>  
  
1.  <span data-ttu-id="d94ff-318">Fare clic sul pulsante **Start**, scegliere **programmi**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Generatore report**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-318">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
2.  <span data-ttu-id="d94ff-319">Nella finestra di dialogo **Attività iniziali** verificare che l'opzione **Nuovo report** sia selezionata e fare clic su **Creazione guidata tabella o matrice**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-319">In the **Getting Started** dialog box, verify that **New Report** is selected, and then click **Table or Matrix Wizard**.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="MConnection"></a><span data-ttu-id="d94ff-320">1a.</span><span class="sxs-lookup"><span data-stu-id="d94ff-320">1a.</span></span> <span data-ttu-id="d94ff-321">Specificare una connessione dati</span><span class="sxs-lookup"><span data-stu-id="d94ff-321">Specify a Data Connection</span></span>  
 <span data-ttu-id="d94ff-322">Verrà aggiunta un'origine dati incorporata al report principale.</span><span class="sxs-lookup"><span data-stu-id="d94ff-322">You will add an embedded data source to the main report.</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="d94ff-323">Per creare un'origine dati incorporata</span><span class="sxs-lookup"><span data-stu-id="d94ff-323">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="d94ff-324">Nella pagina **Scegliere un set di dati** selezionare **Crea un set di dati**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-324">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="d94ff-325">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-325">Click **New**.</span></span>  
  
3.  <span data-ttu-id="d94ff-326">In **Nome**digitare **Online and Reseller Sales Main** come nome per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d94ff-326">In **Name**, type **Online and Reseller Sales Main** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="d94ff-327">In **Seleziona il tipo di connessione**, scegliere **Microsoft SQL Server Analysis Services**, quindi fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-327">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="d94ff-328">In **Origine dati**verificare che l'origine dati sia **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-328">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="d94ff-329">In **nome server**Digitare il nome di un server in cui è installata un'istanza di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d94ff-329">In **Server name**, type the name of a server where an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is installed.</span></span>  
  
7.  <span data-ttu-id="d94ff-330">In **Selezionare o immettere un nome di database**specificare il cubo Contoso.</span><span class="sxs-lookup"><span data-stu-id="d94ff-330">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="d94ff-331">Verificare che la **Stringa di connessione** contenga la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="d94ff-331">Verify that the **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
10. <span data-ttu-id="d94ff-332">Fare clic su **Tipo credenziali**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-332">Click **Credentials type**.</span></span>  
  
     <span data-ttu-id="d94ff-333">A seconda di come vengono configurate le autorizzazioni sull'origine dati, potrebbe essere necessario modificare l'autenticazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d94ff-333">Depending on how permissions are configured on the data source, you might need to change the default authentication.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="d94ff-334">Per verificare che la connessione all'origine dati avvenga correttamente, fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-334">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="d94ff-335">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-335">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="MMDXQuery"></a><span data-ttu-id="d94ff-336">1b.</span><span class="sxs-lookup"><span data-stu-id="d94ff-336">1b.</span></span> <span data-ttu-id="d94ff-337">Creare una query MDX</span><span class="sxs-lookup"><span data-stu-id="d94ff-337">Create an MDX Query</span></span>  
 <span data-ttu-id="d94ff-338">Quindi creare un set di dati incorporato.</span><span class="sxs-lookup"><span data-stu-id="d94ff-338">Next, create an embedded dataset.</span></span> <span data-ttu-id="d94ff-339">A tale scopo, si utilizzerà Progettazione query per creare filtri, parametri, membri calcolati e il set di dati stesso.</span><span class="sxs-lookup"><span data-stu-id="d94ff-339">To do so, you will use the query designer to create filters, parameters, and calculated members as well as the dataset itself.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="d94ff-340">Per creare filtri query</span><span class="sxs-lookup"><span data-stu-id="d94ff-340">To create query filters</span></span>  
  
1.  <span data-ttu-id="d94ff-341">Nella sezione cubo del riquadro metadati della pagina **Progetta query** fare clic sui puntini di sospensione **(...)**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-341">On the **Design a query** page, in the Metadata pane, in the cube section, click the ellipsis **(...)**.</span></span>  
  
2.  <span data-ttu-id="d94ff-342">Nella finestra di dialogo **Seleziona cubo** fare clic su Vendite, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-342">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="d94ff-343">Se non si vuole creare manualmente la query MDX, fare clic sull'icona ![Passa alla modalità progettazione](media/rsqdicon-designmode.gif "Passare alla modalità progettazione"), impostare Progettazione query in modalità query, incollare la query MDX completata nella finestra di progettazione query e quindi procedere con il passaggio 5 in [Per creare il set di dati](#MSkip).</span><span class="sxs-lookup"><span data-stu-id="d94ff-343">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 5 in [To create the dataset](#MSkip).</span></span>  
  
    ```  
    WITH MEMBER [Measures].[Net QTY] AS [Measures].[Sales Quantity] -[Measures].[Sales Return Quantity] MEMBER [Measures].[Net Sales] AS [Measures].[Sales Amount] - [Measures].[Sales Return Amount] SELECT NON EMPTY { [Measures].[Net QTY], [Measures].[Net Sales] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGSQuery text: Code.  
    ```  
  
3.  <span data-ttu-id="d94ff-344">Nel riquadro Gruppo di misure, espandere Canale, quindi trascinare Nome canale nella colonna **Gerarchia** del riquadro filtro.</span><span class="sxs-lookup"><span data-stu-id="d94ff-344">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="d94ff-345">Il nome della dimensione Canale viene aggiunto automaticamente alla colonna **Dimensione** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-345">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="d94ff-346">Non modificare le colonne **Dimensione** o **Operatore** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-346">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="d94ff-347">Per aprire l'elenco **Espressione filtro** , fare clic sulla freccia in giù nella colonna **Espressione filtro** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-347">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="d94ff-348">Nell'elenco dell'espressione filtro, espandere **Tutti i canali**, fare clic su **Online** e **Rivenditore**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-348">In the filter expression list, expand **All Channel**, click **Online** and **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d94ff-349">Ora la query include un filtro per includere solo questi canali: Online e Rivenditore.</span><span class="sxs-lookup"><span data-stu-id="d94ff-349">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="d94ff-350">Espandere la dimensione Sales Territory, quindi trascinare Sales Territory Group nella colonna **gerarchia** , sotto **nome canale**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-350">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column, below **Channel Name**.</span></span>  
  
7.  <span data-ttu-id="d94ff-351">Aprire l'elenco **Espressione filtro** , espandere **Tutte le aree di vendita**, fare clic su **America del Nord**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-351">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d94ff-352">La query dispone ora di un filtro per includere solo le vendite in America del Nord.</span><span class="sxs-lookup"><span data-stu-id="d94ff-352">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="d94ff-353">Nel riquadro Gruppo di misure espandere Data, quindi trascinare Anno di calendario nella colonna **Gerarchia** del riquadro filtro.</span><span class="sxs-lookup"><span data-stu-id="d94ff-353">In the Measure Group pane, expand Date, and drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="d94ff-354">Il nome della dimensione Data viene aggiunto automaticamente alla colonna **Dimensione** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-354">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="d94ff-355">Non modificare le colonne **Dimensione** o **Operatore** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-355">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="d94ff-356">Per aprire l'elenco **Espressione filtro** , fare clic sulla freccia in giù nella colonna **Espressione filtro** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-356">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="d94ff-357">Nell'elenco dell'espressione filtro, espandere **Tutte le date**, fare clic su **Anno 2009**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-357">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d94ff-358">La query include ora un filtro per includere solo l'anno solare 2009.</span><span class="sxs-lookup"><span data-stu-id="d94ff-358">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="d94ff-359">Per creare il parametro.</span><span class="sxs-lookup"><span data-stu-id="d94ff-359">To create the parameter</span></span>  
  
1.  <span data-ttu-id="d94ff-360">Espandere la dimensione Prodotto, quindi trascinare il membro Product Category Name nella colonna **Gerarchia** sotto **Gruppo territorio di vendita**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-360">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Sales Territory Group**.</span></span>  
  
2.  <span data-ttu-id="d94ff-361">Aprire l 'elenco **Espressione filtro** , fare clic su **Tutti i prodotti**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-361">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d94ff-362">Fare clic sulla casella di controllo **Parametro** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-362">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="d94ff-363">La query ora include il parametro ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="d94ff-363">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
#### <a name="to-create-calculated-members"></a><span data-ttu-id="d94ff-364">Per creare membri calcolati</span><span class="sxs-lookup"><span data-stu-id="d94ff-364">To create calculated members</span></span>  
  
1.  <span data-ttu-id="d94ff-365">Posizionare il cursore nel riquadro Membri calcolati, fare clic con il pulsante destro del mouse su **Nuovo membro calcolato**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-365">Place the cursor inside the Calculated Members pane, right-click, and then click **New Calculated Member**.</span></span>  
  
2.  <span data-ttu-id="d94ff-366">Nel riquadro Metadati espandere **misure** , quindi espandere vendite.</span><span class="sxs-lookup"><span data-stu-id="d94ff-366">In the Metadata pane, expand **Measures** and then expand Sales.</span></span>  
  
3.  <span data-ttu-id="d94ff-367">Trascinare la misura Quantità vendite nella casella **Espressione** , digitare il carattere di sottrazione (-), quindi trascinare la misura Quantità margine vendite nella casella **Espressione** dopo il carattere di sottrazione.</span><span class="sxs-lookup"><span data-stu-id="d94ff-367">Drag the Sales Quantity measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Quantity measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="d94ff-368">Nell'esempio di codice seguente viene illustrata l'espressione:</span><span class="sxs-lookup"><span data-stu-id="d94ff-368">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Quantity] - [Measures].[Sales Return Quantity]  
    ```  
  
4.  <span data-ttu-id="d94ff-369">Nella casella Nome digitare **Net QTY**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-369">In the Name box, type **Net QTY**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d94ff-370">Il riquadro Membri calcolati elenca il membro calcolato **Net QTY** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-370">The Calculated Members pane lists the **Net QTY** calculated member.</span></span>  
  
5.  <span data-ttu-id="d94ff-371">Fare clic con il pulsante destro del mouse su **Membri calcolati**, quindi fare clic su **Nuovo membro calcolato**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-371">Right-click **Calculated Members**, and then click **New Calculated Member**.</span></span>  
  
6.  <span data-ttu-id="d94ff-372">Nel riquadro Metadati espandere **Misure**, quindi espandere Vendite.</span><span class="sxs-lookup"><span data-stu-id="d94ff-372">In the Metadata pane, expand **Measures**, and then expand Sales.</span></span>  
  
7.  <span data-ttu-id="d94ff-373">Trascinare la misura Importo vendite nella casella **Espressione** , digitare il carattere di sottrazione (-), quindi trascinare la misura Importo margine vendite nella casella **Espressione** dopo il carattere di sottrazione.</span><span class="sxs-lookup"><span data-stu-id="d94ff-373">Drag the Sales Amount measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Amount measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="d94ff-374">Nell'esempio di codice seguente viene illustrata l'espressione:</span><span class="sxs-lookup"><span data-stu-id="d94ff-374">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Amount] - [Measures].[Sales Return Amount]  
    ```  
  
8.  <span data-ttu-id="d94ff-375">Nella casella **Nome** digitare  **Fatturato netto**, quindi fare clic su **OK**. Nel riquadro Membri calcolati è elencato il membro calcolato di **Fatturato netto** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-375">In the **Name** box, type  **Net Sales**, and then click **OK**.The Calculated Members pane lists the **Net Sales** calculated member.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="MSkip"></a><span data-ttu-id="d94ff-376">Per creare il set di dati</span><span class="sxs-lookup"><span data-stu-id="d94ff-376">To create the dataset</span></span>  
  
1.  <span data-ttu-id="d94ff-377">Trascinare Nome canale dalla dimensione Canale al riquadro dei dati.</span><span class="sxs-lookup"><span data-stu-id="d94ff-377">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="d94ff-378">Trascinare Product Category Name dalla dimensione Prodotto al riquadro dei dati, quindi posizionarlo a destra di Nome canale.</span><span class="sxs-lookup"><span data-stu-id="d94ff-378">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="d94ff-379">Trascinare **da**Membri calcolati `Net QTY` al riquadro dati e posizionarlo alla destra di Product Category Name.</span><span class="sxs-lookup"><span data-stu-id="d94ff-379">From **Calculated Members**, drag `Net QTY` to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="d94ff-380">Trascinare Fatturato netto da Membri calcolati al riquadro dati e posizionarlo a destra di `Net QTY`.</span><span class="sxs-lookup"><span data-stu-id="d94ff-380">From Calculated Members, drag Net Sales to the data pane, and then place it to the right of `Net QTY`.</span></span>  
  
5.  <span data-ttu-id="d94ff-381">Sulla barra degli strumenti Progettazione query fare clic su **Esegui (!)**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-381">On the query designer toolbar, click **Run (!)**.</span></span>  
  
     <span data-ttu-id="d94ff-382">Controllare il set di risultati della query</span><span class="sxs-lookup"><span data-stu-id="d94ff-382">Review the query result set.</span></span>  
  
6.  <span data-ttu-id="d94ff-383">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-383">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="MLayout"></a><span data-ttu-id="d94ff-384">1C.</span><span class="sxs-lookup"><span data-stu-id="d94ff-384">1c.</span></span> <span data-ttu-id="d94ff-385">Organizzare i dati in gruppi</span><span class="sxs-lookup"><span data-stu-id="d94ff-385">Organize Data into Groups</span></span>  
 <span data-ttu-id="d94ff-386">Quando si selezionano dei campi in cui raggruppare i dati, si progetta una matrice con righe e colonne che visualizza dati dettagliati e dati aggregati.</span><span class="sxs-lookup"><span data-stu-id="d94ff-386">When you select the fields on which to group data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="d94ff-387">Per organizzare i dati in gruppi</span><span class="sxs-lookup"><span data-stu-id="d94ff-387">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="d94ff-388">Nella pagina **Disponi campi** trascinare Product_Category_Name in **Gruppi di righe**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-388">On the **Arrange fields** page, drag Product_Category_Name to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="d94ff-389">Trascinare Channel_Name in **Gruppi di colonne**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-389">Drag Channel_Name to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="d94ff-390">Trascinare `Net_QTY` in **Valori**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-390">Drag `Net_QTY` to **Values**.</span></span>  
  
     <span data-ttu-id="d94ff-391">`Net_QTY` viene aggregata automaticamente dalla funzione Sum, l'aggregazione predefinita per i campi numerici.</span><span class="sxs-lookup"><span data-stu-id="d94ff-391">`Net_QTY` is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="d94ff-392">Il valore è `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="d94ff-392">The value is `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="d94ff-393">È possibile aprire l'elenco a discesa per visualizzare le altre funzioni di aggregazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="d94ff-393">To view the other aggregate functions available, open the drop-down list.</span></span> <span data-ttu-id="d94ff-394">Non modificare la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="d94ff-394">Do not change the aggregate function.</span></span>  
  
4.  <span data-ttu-id="d94ff-395">Trascinare `Net_Sales_Return` in **Valori** e posizionarlo sotto `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="d94ff-395">Drag `Net_Sales_Return` to **Values** and then place it below `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="d94ff-396">I passaggi 3 e 4 consentono di specificare i dati da visualizzare nella matrice.</span><span class="sxs-lookup"><span data-stu-id="d94ff-396">Steps 3 and 4 specify the data to display in the matrix.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="MTotals"></a><span data-ttu-id="d94ff-397">1D.</span><span class="sxs-lookup"><span data-stu-id="d94ff-397">1d.</span></span> <span data-ttu-id="d94ff-398">Aggiungere subtotali e totali</span><span class="sxs-lookup"><span data-stu-id="d94ff-398">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="d94ff-399">Nei report è possibile mostrare subtotali e totali complessivi.</span><span class="sxs-lookup"><span data-stu-id="d94ff-399">You can show subtotals and grand totals in reports.</span></span> <span data-ttu-id="d94ff-400">I dati nei report principali sono visualizzati come un indicatore; il totale complessivo verrà rimosso dopo avere completato la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d94ff-400">The data in the main report displays as an indicator; you will remove the grand total after you complete the wizard.</span></span>  
  
#### <a name="to-add-subtotals-and-grand-totals"></a><span data-ttu-id="d94ff-401">Per aggiungere subtotali e totali complessivi</span><span class="sxs-lookup"><span data-stu-id="d94ff-401">To add subtotals and grand totals</span></span>  
  
1.  <span data-ttu-id="d94ff-402">Nella pagina **scegliere il layout** , in **Opzioni**, verificare che sia selezionata l'opzione **Mostra subtotali e totali** complessivi.</span><span class="sxs-lookup"><span data-stu-id="d94ff-402">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="d94ff-403">Nel riquadro di anteprima della creazione guidata viene visualizzata una matrice con quattro righe.</span><span class="sxs-lookup"><span data-stu-id="d94ff-403">The wizard Preview pane displays a matrix with four rows.</span></span>  <span data-ttu-id="d94ff-404">Quando si esegue il report, ogni riga sarà visualizzata nella modalità seguente: La prima riga è il gruppo di colonne, la seconda riga contiene le intestazioni di colonna, la terza riga contiene i dati della categoria di prodotto (`[Sum(Net_ QTY)]` e `[Sum(Net_Sales)]`e la quarta riga contiene i totali.</span><span class="sxs-lookup"><span data-stu-id="d94ff-404">When you run the report, each row will display in the following way: The first row is the column group, the second row contains the column headings, the third row contains the product category data (`[Sum(Net_ QTY)]` and `[Sum(Net_Sales)]`, and the fourth row contains the totals.</span></span>  
  
2.  <span data-ttu-id="d94ff-405">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-405">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="MStyle"></a><span data-ttu-id="d94ff-406">1e.</span><span class="sxs-lookup"><span data-stu-id="d94ff-406">1e.</span></span> <span data-ttu-id="d94ff-407">Scegliere uno stile</span><span class="sxs-lookup"><span data-stu-id="d94ff-407">Choose a Style</span></span>  
 <span data-ttu-id="d94ff-408">Applicare lo stile Ardesia al report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-408">Apply the Slate style to the report.</span></span> <span data-ttu-id="d94ff-409">Si tratta dello stesso stile che utilizza il report drill-through.</span><span class="sxs-lookup"><span data-stu-id="d94ff-409">This is the same style that the drillthrough report uses.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="d94ff-410">Per specificare uno stile</span><span class="sxs-lookup"><span data-stu-id="d94ff-410">To specify a style</span></span>  
  
1.  <span data-ttu-id="d94ff-411">Nel riquadro Stili della pagina **scegliere uno stile** selezionare Slate.</span><span class="sxs-lookup"><span data-stu-id="d94ff-411">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="d94ff-412">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-412">Click **Finish**.</span></span>  
  
3.  <span data-ttu-id="d94ff-413">Fare clic su **Esegui**per visualizzare un'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-413">To preview the report, click **Run**.</span></span>  
  
##  <a name="2-remove-the-grand-total-row"></a><a name="MGrandTotal"></a><span data-ttu-id="d94ff-414">2. rimuovere la riga del totale complessivo</span><span class="sxs-lookup"><span data-stu-id="d94ff-414">2. Remove the Grand Total Row</span></span>  
 <span data-ttu-id="d94ff-415">I valori dei dati vengono mostrati come stati dell'indicatore, includendo i totali del gruppo di colonne.</span><span class="sxs-lookup"><span data-stu-id="d94ff-415">The data values are shown as indictor states, including the column group totals.</span></span> <span data-ttu-id="d94ff-416">Rimuovere la riga che visualizza il totale complessivo.</span><span class="sxs-lookup"><span data-stu-id="d94ff-416">Remove the row that displays the grand total.</span></span>  
  
#### <a name="to-remove-the-grand-total-row"></a><span data-ttu-id="d94ff-417">Per rimuovere la riga Totale complessivo</span><span class="sxs-lookup"><span data-stu-id="d94ff-417">To remove the grand total row</span></span>  
  
1.  <span data-ttu-id="d94ff-418">Fare clic su **Progettazione**per passare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="d94ff-418">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="d94ff-419">Fare clic sulla riga Totale (l'ultima riga della matrice), fare clic con il pulsante destro del mouse, quindi fare clic su **Elimina righe**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-419">Click the Total row (the last row in the matrix), right-click, and then click **Delete Rows**.</span></span>  
  
3.  <span data-ttu-id="d94ff-420">Fare clic su **Esegui**per visualizzare un'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-420">To preview the report, click **Run**.</span></span>  
  
##  <a name="3-configure-text-box-action-for-drillthrough"></a><a name="MDrillthrough"></a><span data-ttu-id="d94ff-421">3. configurare l'azione della casella di testo per il drill-through</span><span class="sxs-lookup"><span data-stu-id="d94ff-421">3. Configure Text Box Action for Drillthrough</span></span>  
 <span data-ttu-id="d94ff-422">Per abilitare il drill-through, specificare un'azione nella casella di testo del report principale.</span><span class="sxs-lookup"><span data-stu-id="d94ff-422">To enable the drillthrough, specify an action on a text box in the main report.</span></span>  
  
#### <a name="to-enable-an-action"></a><span data-ttu-id="d94ff-423">Per abilitare un'azione</span><span class="sxs-lookup"><span data-stu-id="d94ff-423">To enable an action</span></span>  
  
1.  <span data-ttu-id="d94ff-424">Fare clic su **Progettazione**per passare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="d94ff-424">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="d94ff-425">Fare clic con il pulsante destro del mouse sulla cella contenente Product_Category_Name, quindi fare clic su **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-425">Right-click the cell that contains Product_Category_Name, and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="d94ff-426">Fare clic sulla scheda **Azione**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-426">Click the **Action** tab.</span></span>  
  
4.  <span data-ttu-id="d94ff-427">Selezionare **Vai al report.**</span><span class="sxs-lookup"><span data-stu-id="d94ff-427">Select **Go to report.**</span></span>  
  
5.  <span data-ttu-id="d94ff-428">In **Specifica un report**, fare clic su **Sfoglia**, quindi individuare il report drill-through denominato ResellerVSOnlineDrillthrough.</span><span class="sxs-lookup"><span data-stu-id="d94ff-428">In **Specify a report**, click **Browse**, and then locate the drillthrough report named ResellerVSOnlineDrillthrough.</span></span>  
  
6.  <span data-ttu-id="d94ff-429">Per aggiungere un nuovo parametro per l'esecuzione del report drill-through, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-429">To add a parameter to run the drillthrough report, click **Add**.</span></span>  
  
7.  <span data-ttu-id="d94ff-430">Nell'elenco **Nome** selezionare ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="d94ff-430">In the **Name** list, select ProductProductCategoryName.</span></span>  
  
8.  <span data-ttu-id="d94ff-431">In **Valore**digitare `[Product_Category_Name.UniqueName]`.</span><span class="sxs-lookup"><span data-stu-id="d94ff-431">In **Value**, type `[Product_Category_Name.UniqueName]`.</span></span>  
  
     <span data-ttu-id="d94ff-432">Product_Category_Name è un campo nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="d94ff-432">Product_Category_Name is a field in the dataset.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d94ff-433">È necessario includere la proprietà `UniqueName` perché l'azione di drill-through richiede un valore univoco.</span><span class="sxs-lookup"><span data-stu-id="d94ff-433">You must include the `UniqueName` property because the drillthrough action requires a unique value.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-format-the-drillthrough-field"></a><span data-ttu-id="d94ff-434">Per formattare il campo drill-through</span><span class="sxs-lookup"><span data-stu-id="d94ff-434">To format the drillthrough field</span></span>  
  
1.  <span data-ttu-id="d94ff-435">Fare clic con il pulsante destro del mouse sulla cella che contiene `Product_Category_Name`e scegliere **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-435">Right-click the cell that contains the `Product_Category_Name`, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="d94ff-436">Fare clic sulla scheda **Tipo di carattere** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-436">Click the **Font** tab.</span></span>  
  
3.  <span data-ttu-id="d94ff-437">Selezionare **Sottolineato** nell'elenco **Effetti**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-437">In the **Effects** list, select **Underline**.</span></span>  
  
4.  <span data-ttu-id="d94ff-438">Selezionare **Blu** nell'elenco **Colore**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-438">In the **Color** list, select **Blue**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="d94ff-439">Per visualizzare l'anteprima del report, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-439">To preview your report, click **Run**.</span></span>  
  
 <span data-ttu-id="d94ff-440">I nomi della categoria di prodotto sono nel comune formato di collegamento (blu e sottolineato).</span><span class="sxs-lookup"><span data-stu-id="d94ff-440">The product category names are in the common link format (blue and underlined).</span></span>  
  
##  <a name="4-replace-numeric-values-with-indicators"></a><a name="MIndicators"></a><span data-ttu-id="d94ff-441">4. sostituire i valori numerici con gli indicatori</span><span class="sxs-lookup"><span data-stu-id="d94ff-441">4. Replace Numeric Values with Indicators</span></span>  
 <span data-ttu-id="d94ff-442">Utilizzare indicatori per mostrare lo stato di quantità e vendite per i canali Online e Rivenditore.</span><span class="sxs-lookup"><span data-stu-id="d94ff-442">Use indicators to show the state of quantities and sales for Online and Reseller channels.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-qty-values"></a><span data-ttu-id="d94ff-443">Per aggiungere un indicatore per i valori Net QTY</span><span class="sxs-lookup"><span data-stu-id="d94ff-443">To add an indicator for Net QTY values</span></span>  
  
1.  <span data-ttu-id="d94ff-444">Fare clic su **Progettazione**per passare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="d94ff-444">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="d94ff-445">Sulla barra multifunzione, fare clic sull'icona **Rettangolo** , quindi fare clic sulla cella `[Sum(Net QTY)]` del gruppo di righe `[Product_Category_Name]` nel gruppo di colonne `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="d94ff-445">On the ribbon, click the **Rectangle** icon, and then click in the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
3.  <span data-ttu-id="d94ff-446">Sulla barra multifunzione, fare clic sull'icona **Indicatore** , quindi fare clic all'interno del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="d94ff-446">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span> <span data-ttu-id="d94ff-447">Viene visualizzata la finestra di dialogo **Seleziona tipo indicatore** con l'indicatore **Direzionale** selezionato.</span><span class="sxs-lookup"><span data-stu-id="d94ff-447">The **Select Indicator Type** dialog box opens with the **Directional** indicator selected.</span></span>  
  
4.  <span data-ttu-id="d94ff-448">Fare clic sul tipo **3 segnali** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-448">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d94ff-449">Fare clic con il pulsante destro del mouse sull'indicatore e nel riquadro Dati del misuratore, fare clic sulla freccia in giù accanto a **(Non specificato)**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-449">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="d94ff-450">Selezionare `Net_QTY`.</span><span class="sxs-lookup"><span data-stu-id="d94ff-450">Select `Net_QTY`.</span></span>  
  
6.  <span data-ttu-id="d94ff-451">Ripetere i passaggi da 2 a 5 per la cella `[Sum(Net QTY)]` nel gruppo di righe `[Product_Category_Name]` all'interno di **Totale**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-451">Repeat steps 2 through 5 for the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-sales-values"></a><span data-ttu-id="d94ff-452">Per aggiungere un indicatore per i valori Fatturato Netto</span><span class="sxs-lookup"><span data-stu-id="d94ff-452">To add an indicator for Net Sales values</span></span>  
  
1.  <span data-ttu-id="d94ff-453">Sulla barra multifunzione, fare clic sull'icona **Rettangolo** , quindi fare clic all'interno della cella `[Sum(Net_Sales)]` del gruppo di righe `[Product_Category_Name]` nel gruppo di colonne `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="d94ff-453">On the ribbon, click the **Rectangle** icon, and then click inside the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
2.  <span data-ttu-id="d94ff-454">Sulla barra multifunzione, fare clic sull'icona **Indicatore** , quindi fare clic all'interno del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="d94ff-454">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span>  
  
3.  <span data-ttu-id="d94ff-455">Fare clic sul tipo **3 segnali** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-455">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d94ff-456">Fare clic con il pulsante destro del mouse sull'indicatore e nel riquadro Dati del misuratore, fare clic sulla freccia in giù accanto a **(Non specificato)**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-456">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="d94ff-457">Selezionare `Net_Sales`.</span><span class="sxs-lookup"><span data-stu-id="d94ff-457">Select `Net_Sales`.</span></span>  
  
5.  <span data-ttu-id="d94ff-458">Ripetere i passaggi da 1 a 4 per la cella `[Sum(Net_Sales)]` nel gruppo di righe `[Product_Category_Name]` all'interno di **Totale**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-458">Repeat steps 1 through 4 for the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
6.  <span data-ttu-id="d94ff-459">Per visualizzare l'anteprima del report, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-459">To preview your report, click **Run**.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="MParameter"></a><span data-ttu-id="d94ff-460">5. aggiornare le proprietà del parametro</span><span class="sxs-lookup"><span data-stu-id="d94ff-460">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="d94ff-461">Per impostazione predefinita, i parametri sono visibili; questa impostazione non è adatta per questo report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-461">By default, parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="d94ff-462">È possibile aggiornare le proprietà dei parametri per rendere il parametro interno.</span><span class="sxs-lookup"><span data-stu-id="d94ff-462">You will update the parameter properties to make the parameter internal.</span></span>  
  
#### <a name="to-make-the-parameter-internal"></a><span data-ttu-id="d94ff-463">Per rendere interno il parametro</span><span class="sxs-lookup"><span data-stu-id="d94ff-463">To make the parameter internal</span></span>  
  
1.  <span data-ttu-id="d94ff-464">Nel riquadro Dati report espandere **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-464">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="d94ff-465">Fare clic con il pulsante destro del mouse su `@ProductProductCategoryName,` , quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-465">Right-click `@ProductProductCategoryName,` and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="d94ff-466">Nella scheda **Generale** fare clic su **Interno**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-466">On the **General** tab, click **Internal**.</span></span>  
  
4.  <span data-ttu-id="d94ff-467">Facoltativamente, fare clic sulle schede **Valori disponibili** e **Valori predefiniti** e controllare le opzioni.</span><span class="sxs-lookup"><span data-stu-id="d94ff-467">Optionally, click the **Available Values** and **Default Values** tabs and review their options.</span></span> <span data-ttu-id="d94ff-468">Non modificare le opzioni in queste schede.</span><span class="sxs-lookup"><span data-stu-id="d94ff-468">Do not change any options on these tabs.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-add-a-report-title"></a><a name="MTitle"></a><span data-ttu-id="d94ff-469">6. aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="d94ff-469">6. Add a Report Title</span></span>  
 <span data-ttu-id="d94ff-470">Aggiungere un titolo a un report principale</span><span class="sxs-lookup"><span data-stu-id="d94ff-470">Add a title to the main report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="d94ff-471">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="d94ff-471">To add a report title</span></span>  
  
1.  <span data-ttu-id="d94ff-472">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-472">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="d94ff-473">Digitare **2009 Product Category Sales: Categoria Online e Rivenditore**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-473">Type **2009 Product Category Sales: Online and Reseller Category:**.</span></span>  
  
3.  <span data-ttu-id="d94ff-474">Selezionare il testo digitato.</span><span class="sxs-lookup"><span data-stu-id="d94ff-474">Select the text you typed.</span></span>  
  
4.  <span data-ttu-id="d94ff-475">Nel gruppo Carattere della scheda **Home** sulla barra multifunzione, selezionare il tipo di carattere **Times New Roman** , la dimensione **16pt** e gli stili **Grassetto** e **Corsivo** .</span><span class="sxs-lookup"><span data-stu-id="d94ff-475">On the **Home** tab of the ribbon, in the Font group, select the **Times New Roman** font, **16pt** size, and the **Bold** and **Italic** styles.</span></span>  
  
5.  <span data-ttu-id="d94ff-476">Per visualizzare l'anteprima del report, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-476">To preview your report, click **Run**.</span></span>  
  
##  <a name="7-save-the-main-report-to-a-sharepoint-library"></a><a name="MSave"></a><span data-ttu-id="d94ff-477">7. salvare il report principale in una raccolta di SharePoint</span><span class="sxs-lookup"><span data-stu-id="d94ff-477">7. Save the Main Report to a SharePoint Library</span></span>  
 <span data-ttu-id="d94ff-478">Salvare il report principale in una raccolta di SharePoint</span><span class="sxs-lookup"><span data-stu-id="d94ff-478">Save the main report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="d94ff-479">Per salvare il report</span><span class="sxs-lookup"><span data-stu-id="d94ff-479">To save the report</span></span>  
  
1.  <span data-ttu-id="d94ff-480">Fare clic su **Progettazione**per passare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="d94ff-480">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="d94ff-481">Dal pulsante Generatore report fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-481">From the Report Builder button, click **Save**.</span></span>  
  
3.  <span data-ttu-id="d94ff-482">Facoltativamente, fare clic su **Siti e server recenti**per visualizzare un elenco di server di report e di siti di SharePoint usati di recente.</span><span class="sxs-lookup"><span data-stu-id="d94ff-482">Optionally, to show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
4.  <span data-ttu-id="d94ff-483">Selezionare o digitare il nome del sito di SharePoint per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-483">Select or type the name of the SharePoint site where you have permission to save reports.</span></span> <span data-ttu-id="d94ff-484">La sintassi dell'URL della raccolta di SharePoint è la seguente:</span><span class="sxs-lookup"><span data-stu-id="d94ff-484">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
5.  <span data-ttu-id="d94ff-485">Passare alla raccolta dove si salverà il report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-485">Navigate to the library where you want to save the report.</span></span>  
  
6.  <span data-ttu-id="d94ff-486">In **Nome**sostituire il nome predefinito con **ResellerVSOnlineMain**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-486">In **Name**, replace the default name with **ResellerVSOnlineMain**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d94ff-487">Salvare il report principale nello stesso percorso dove era stato salvato il report drill-through.</span><span class="sxs-lookup"><span data-stu-id="d94ff-487">Save the main report to the same location where you saved the drillthrough report.</span></span> <span data-ttu-id="d94ff-488">Per salvare il report principale e il report drill-through in librerie o siti diversi, accertarsi che l'azione **Vai al report** nel report principale indichi il percorso corretto del report drill-through.</span><span class="sxs-lookup"><span data-stu-id="d94ff-488">To save the main and drillthrough reports to different sites or libraries, confirm that the **Go to report** action in the main report, points to the correct location of the drillthrough report.</span></span>  
  
7.  <span data-ttu-id="d94ff-489">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d94ff-489">Click **Save**.</span></span>  
  
##  <a name="8-run-the-main-and-drillthrough-reports"></a><a name="MRunReports"></a><span data-ttu-id="d94ff-490">8. eseguire i report principali e drill-through</span><span class="sxs-lookup"><span data-stu-id="d94ff-490">8. Run the Main and Drillthrough Reports</span></span>  
 <span data-ttu-id="d94ff-491">Eseguire il report principale, quindi fare clic su valori nella colonna della categoria di prodotto per eseguire il report drill-through.</span><span class="sxs-lookup"><span data-stu-id="d94ff-491">Run the main report, and then click values in the product category column to run the drillthrough report.</span></span>  
  
#### <a name="to-run-the-reports"></a><span data-ttu-id="d94ff-492">Per eseguire i report</span><span class="sxs-lookup"><span data-stu-id="d94ff-492">To run the reports</span></span>  
  
1.  <span data-ttu-id="d94ff-493">Aprire la raccolta di SharePoint dove sono salvati i report.</span><span class="sxs-lookup"><span data-stu-id="d94ff-493">Open the SharePoint library where the reports are saved.</span></span>  
  
2.  <span data-ttu-id="d94ff-494">Fare doppio clic su ResellerVSOnlineMain.</span><span class="sxs-lookup"><span data-stu-id="d94ff-494">Double-click ResellerVSOnlineMain.</span></span>  
  
     <span data-ttu-id="d94ff-495">Il report viene eseguito e visualizza le informazioni sulle vendite della categoria di prodotto.</span><span class="sxs-lookup"><span data-stu-id="d94ff-495">The report runs and displays product category sales information.</span></span>  
  
3.  <span data-ttu-id="d94ff-496">Fare clic sul collegamento **Games and Toys** nella colonna che contiene i nomi della categoria di prodotto.</span><span class="sxs-lookup"><span data-stu-id="d94ff-496">Click the **Games and Toys** link in the column that contains product category names.</span></span>  
  
     <span data-ttu-id="d94ff-497">Il report drill-through viene eseguito e visualizza solo i valori per la categoria di prodotto Games and Toys.</span><span class="sxs-lookup"><span data-stu-id="d94ff-497">The drillthrough report runs, displaying only the values for the Games and Toys product category.</span></span>  
  
4.  <span data-ttu-id="d94ff-498">Per tornare al report principale, fare clic sul pulsante Indietro di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d94ff-498">To return to the main report, click the Internet Explorer back button.</span></span>  
  
5.  <span data-ttu-id="d94ff-499">Facoltativamente, esplorare le altre categorie di prodotto facendo clic sui nomi.</span><span class="sxs-lookup"><span data-stu-id="d94ff-499">Optionally, explore other product categories by clicking their names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d94ff-500">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d94ff-500">See Also</span></span>  
 [<span data-ttu-id="d94ff-501">Esercitazioni &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="d94ff-501">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
