---
title: 'Lezione 2: aggiungere dati | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 13c3a8cc-b1db-4aba-ad9b-038b7971be8d
author: minewiskan
ms.author: owend
ms.openlocfilehash: c844ea6558949407ca9b8206601ff7fe802ec399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626370"
---
# <a name="lesson-2-add-data"></a><span data-ttu-id="d2649-102">Lezione 2: Aggiungere dati</span><span class="sxs-lookup"><span data-stu-id="d2649-102">Lesson 2: Add Data</span></span>
  <span data-ttu-id="d2649-103">In questa lezione verrà utilizzata l'Importazione guidata tabella in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] per connettersi al database SQL AdventureWorksDW, selezionare i dati, visualizzare un'anteprima, filtrare i dati e quindi importarli nell'area di lavoro del modello.</span><span class="sxs-lookup"><span data-stu-id="d2649-103">In this lesson, you will use the Table Import Wizard in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] to connect to the AdventureWorksDW SQL database, select data, preview, and filter the data, and then import the data into your model workspace.</span></span>  
  
 <span data-ttu-id="d2649-104">Utilizzando l'Importazione guidata tabella è possibile importare dati da diverse origini relazionali, quali Access, SQL, Oracle, Sybase, Informix, DB2, Teradata e così via.</span><span class="sxs-lookup"><span data-stu-id="d2649-104">By using the Table Import Wizard, you can import data from a variety of relational sources: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata, and more.</span></span> <span data-ttu-id="d2649-105">I passaggi per l'importazione dei dati da ognuna di queste origini relazionali sono molto simili a quanto descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="d2649-105">The steps for importing data from each of these relational sources are very similar to what is described below.</span></span> <span data-ttu-id="d2649-106">I dati possono inoltre essere selezionati utilizzando una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d2649-106">Additionally, data can be selected using a stored procedure.</span></span>  
  
 <span data-ttu-id="d2649-107">Per altre informazioni sull'importazione di dati e sui diversi tipi di origine dati da cui è possibile importare, vedere [Origini dati &#40;SSAS tabulare&#41;](data-sources-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d2649-107">To learn more about importing data and the different types of data sources you can import from, see [Data Sources &#40;SSAS Tabular&#41;](data-sources-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="d2649-108">Tempo previsto per il completamento della lezione: **20 minuti**</span><span class="sxs-lookup"><span data-stu-id="d2649-108">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d2649-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d2649-109">Prerequisites</span></span>  
 <span data-ttu-id="d2649-110">Questo argomento fa parte di un'esercitazione sulla creazione di modelli tabulari, con lezioni che è consigliabile completare nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="d2649-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="d2649-111">Prima di eseguire le attività in questa lezione, è necessario aver completato la lezione precedente: [Lezione 1: Creare un nuovo modello di progetto tabulare](lesson-1-create-a-new-tabular-model-project.md).</span><span class="sxs-lookup"><span data-stu-id="d2649-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 1: Create a New Tabular Model Project](lesson-1-create-a-new-tabular-model-project.md).</span></span>  
  
## <a name="create-a-connection"></a><span data-ttu-id="d2649-112">Creare una connessione</span><span class="sxs-lookup"><span data-stu-id="d2649-112">Create a Connection</span></span>  
  
#### <a name="to-create-a-connection-to-a-the-adventureworksdw2012-database"></a><span data-ttu-id="d2649-113">Per creare una connessione al database AdventureWorksDW2012</span><span class="sxs-lookup"><span data-stu-id="d2649-113">To create a connection to a the AdventureWorksDW2012 database</span></span>  
  
1.  <span data-ttu-id="d2649-114">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]fare clic sul menu **Modello** e scegliere **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="d2649-114">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
     <span data-ttu-id="d2649-115">Verrà avviata l'Importazione guidata tabella, che consente di eseguire i passaggi per l'impostazione di una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d2649-115">This launches the Table Import Wizard which guides you through setting up a connection to a data source.</span></span> <span data-ttu-id="d2649-116">Se la voce **Importa da origine dati** è disattivata, fare doppio clic su **Model.bim** in **Esplora soluzioni** per aprire il modello nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d2649-116">If **Import from Data Source** is greyed out, double click **Model.bim** in **Solution Explorer** to open the model in the designer.</span></span>  
  
2.  <span data-ttu-id="d2649-117">Nell' **Importazione guidata tabella**, in **Database relazionali**fare clic su **Microsoft SQL Server**e su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2649-117">In the **Table Import Wizard**, under **Relational Databases**, click **Microsoft SQL Server**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="d2649-118">Nella pagina **connessione a un database di Microsoft SQL Server** , in **nome descrittivo connessione**, digitare `Adventure Works DB from SQL` .</span><span class="sxs-lookup"><span data-stu-id="d2649-118">In the **Connect to a Microsoft SQL Server Database** page, in **Friendly Connection Name**, type `Adventure Works DB from SQL`.</span></span>  
  
4.  <span data-ttu-id="d2649-119">In **Nome server**digitare il nome del server in cui è installato il database AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="d2649-119">In **Server name**, type the name of the server you installed the AdventureWorksDW database.</span></span>  
  
5.  <span data-ttu-id="d2649-120">Nel campo **Nome database** fare clic sulla freccia giù, selezionare **AdventureWorksDW**e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2649-120">In the **Database name** field, click the down arrow and select **AdventureWorksDW**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="d2649-121">Nella pagina **Impostazioni di rappresentazione** specificare le credenziali usate da Analysis Services per la connessione all'origine dati quando vengono importati ed elaborati i dati.</span><span class="sxs-lookup"><span data-stu-id="d2649-121">In the **Impersonation Information** page, you need to specify the credentials Analysis Services will use to connect to the data source when importing and processing data.</span></span> <span data-ttu-id="d2649-122">Verificare che l'opzione **Nome utente e password specifici di Windows** sia selezionata, immettere le credenziali di accesso a Windows in **Nome utente** e **Password**e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d2649-122">Verify **Specific Windows user name and password** is selected, and then in **User Name** and **Password**, enter your Windows logon credentials, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d2649-123">L'utilizzo di un account utente e una password di Windows rappresenta il metodo più sicuro per la connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d2649-123">Using a Windows user account and password provides the most secure method of connecting to a data source.</span></span> <span data-ttu-id="d2649-124">Per altre informazioni, vedere [Rappresentazione &#40;SSAS tabulare&#41;](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d2649-124">For more information, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
7.  <span data-ttu-id="d2649-125">Nella pagina **Scelta della modalità di importazione dei dati** verificare che l'opzione **Seleziona da un elenco di tabelle e viste per scegliere i dati da importare** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="d2649-125">In the **Choose How to Import the Data** page, verify **Select from a list of tables and views to choose the data to import** is selected.</span></span> <span data-ttu-id="d2649-126">Poiché si vuole selezionare da un elenco di tabelle e viste, fare clic su **Avanti** per visualizzare un elenco di tutte le tabelle di origine nel database di origine.</span><span class="sxs-lookup"><span data-stu-id="d2649-126">You want to select from a list of tables and views, so click **Next** to display a list of all the source tables in the source database.</span></span>  
  
8.  <span data-ttu-id="d2649-127">Nella pagina **Selezione tabelle e viste** selezionare le caselle di controllo corrispondenti alle tabelle seguenti: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**e **FactInternetSales**.</span><span class="sxs-lookup"><span data-stu-id="d2649-127">In the **Select Tables and Views** page, select the check box for the following tables: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**, and **FactInternetSales**.</span></span>  
  
9. <span data-ttu-id="d2649-128">Si desidera fornire nomi più comprensibili per le tabelle nel modello.</span><span class="sxs-lookup"><span data-stu-id="d2649-128">We want to give the tables in the model more easily understood names.</span></span> <span data-ttu-id="d2649-129">Fare clic sulla cella nella colonna **Nome descrittivo** per **DimCustomer**.</span><span class="sxs-lookup"><span data-stu-id="d2649-129">Click on the cell in the **Friendly Name** column for **DimCustomer**.</span></span> <span data-ttu-id="d2649-130">Rinominare la tabella rimuovendo "Dim" da DimCustomer.</span><span class="sxs-lookup"><span data-stu-id="d2649-130">Rename the table by removing "Dim" from DimCustomer.</span></span>  
  
10. <span data-ttu-id="d2649-131">Rinominare le altre tabelle:</span><span class="sxs-lookup"><span data-stu-id="d2649-131">Rename the other tables:</span></span>  
  
    |<span data-ttu-id="d2649-132">Nome origine</span><span class="sxs-lookup"><span data-stu-id="d2649-132">Source name</span></span>|<span data-ttu-id="d2649-133">Nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="d2649-133">Friendly Name</span></span>|  
    |-----------------|-------------------|  
    |<span data-ttu-id="d2649-134">DimDate</span><span class="sxs-lookup"><span data-stu-id="d2649-134">DimDate</span></span>|<span data-ttu-id="d2649-135">Data</span><span class="sxs-lookup"><span data-stu-id="d2649-135">Date</span></span>|  
    |<span data-ttu-id="d2649-136">DimGeography</span><span class="sxs-lookup"><span data-stu-id="d2649-136">DimGeography</span></span>|<span data-ttu-id="d2649-137">Area geografica</span><span class="sxs-lookup"><span data-stu-id="d2649-137">Geography</span></span>|  
    |<span data-ttu-id="d2649-138">DimProduct</span><span class="sxs-lookup"><span data-stu-id="d2649-138">DimProduct</span></span>|<span data-ttu-id="d2649-139">Prodotto</span><span class="sxs-lookup"><span data-stu-id="d2649-139">Product</span></span>|  
    |<span data-ttu-id="d2649-140">DimProductCategory</span><span class="sxs-lookup"><span data-stu-id="d2649-140">DimProductCategory</span></span>|<span data-ttu-id="d2649-141">Categoria di prodotto</span><span class="sxs-lookup"><span data-stu-id="d2649-141">Product Category</span></span>|  
    |<span data-ttu-id="d2649-142">DimProductSubcategory</span><span class="sxs-lookup"><span data-stu-id="d2649-142">DimProductSubcategory</span></span>|<span data-ttu-id="d2649-143">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="d2649-143">Product Subcategory</span></span>|  
    |<span data-ttu-id="d2649-144">FactInternetSales</span><span class="sxs-lookup"><span data-stu-id="d2649-144">FactInternetSales</span></span>|<span data-ttu-id="d2649-145">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="d2649-145">Internet Sales</span></span>|  
  
     <span data-ttu-id="d2649-146">**NON** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d2649-146">**DO NOT** click **Finish**.</span></span>  
  
 <span data-ttu-id="d2649-147">Dopo avere stabilito la connessione al database, avere selezionato le tabelle da importare e avere assegnato nomi descrittivi alle tabelle, passare alla sezione successiva per [filtrare i dati della tabella prima dell'importazione](#FilterData).</span><span class="sxs-lookup"><span data-stu-id="d2649-147">Now that you have connected to the database, selected the tables to import, and given the tables friendly names, go to the next section, [Filter the Table Data prior to Importing](#FilterData).</span></span>  
  
##  <a name="filter-the-table-data"></a><a name="FilterData"></a><span data-ttu-id="d2649-148">Filtrare i dati della tabella</span><span class="sxs-lookup"><span data-stu-id="d2649-148">Filter the Table Data</span></span>  
 <span data-ttu-id="d2649-149">La tabella DimCustomer importata dal database contiene un subset dei dati del database SQL Server Adventure Works originale.</span><span class="sxs-lookup"><span data-stu-id="d2649-149">The DimCustomer table that you are importing from the database contains a subset of the data from the original SQL Server Adventure Works database.</span></span> <span data-ttu-id="d2649-150">Verranno filtrate alcune colonne della tabella DimCustomer che non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="d2649-150">You will filter out some of the columns from the DimCustomer table that aren't necessary.</span></span> <span data-ttu-id="d2649-151">Quando possibile, utilizzare filtri per escludere dati che non verranno utilizzati, per risparmiare spazio in memoria utilizzato dal modello.</span><span class="sxs-lookup"><span data-stu-id="d2649-151">When possible, you will want to filter out data that will not be used in order to save in-memory space used by the model.</span></span>  
  
#### <a name="to-filter-the-table-data-prior-to-importing"></a><span data-ttu-id="d2649-152">Per filtrare i dati della tabella prima dell'importazione</span><span class="sxs-lookup"><span data-stu-id="d2649-152">To filter the table data prior to importing</span></span>  
  
1.  <span data-ttu-id="d2649-153">Selezionare la riga per la tabella **Customer** e fare clic su **Visualizza anteprima e applica filtro**.</span><span class="sxs-lookup"><span data-stu-id="d2649-153">Select the row for the **Customer** table, and then click **Preview & Filter**.</span></span> <span data-ttu-id="d2649-154">Verrà visualizzata la finestra **Anteprima tabella selezionata** in cui sono visualizzate tutte le colonne della tabella di origine DimCustomer visualizzata.</span><span class="sxs-lookup"><span data-stu-id="d2649-154">The **Preview Selected Table** window opens with all the columns in the DimCustomer source table displayed.</span></span>  
  
2.  <span data-ttu-id="d2649-155">Deselezionare la casella di controllo nella parte superiore delle colonne seguenti.</span><span class="sxs-lookup"><span data-stu-id="d2649-155">Clear the checkbox at the top of the following columns:</span></span>  
  
    |<span data-ttu-id="d2649-156">Customer</span><span class="sxs-lookup"><span data-stu-id="d2649-156">Customer</span></span>|  
    |--------------|  
    |<span data-ttu-id="d2649-157">**SpanishEducation**</span><span class="sxs-lookup"><span data-stu-id="d2649-157">**SpanishEducation**</span></span>|  
    |<span data-ttu-id="d2649-158">**FrenchEducation**</span><span class="sxs-lookup"><span data-stu-id="d2649-158">**FrenchEducation**</span></span>|  
    |<span data-ttu-id="d2649-159">**SpanishOccupation**</span><span class="sxs-lookup"><span data-stu-id="d2649-159">**SpanishOccupation**</span></span>|  
    |<span data-ttu-id="d2649-160">**FrenchOccupation**</span><span class="sxs-lookup"><span data-stu-id="d2649-160">**FrenchOccupation**</span></span>|  
  
     <span data-ttu-id="d2649-161">Poiché i valori per queste colonne non sono attinenti all'analisi delle vendite Internet, non è necessario importare queste colonne.</span><span class="sxs-lookup"><span data-stu-id="d2649-161">Since the values for these columns are not relevant to Internet sales analysis, there is no need to import these columns.</span></span> <span data-ttu-id="d2649-162">Eliminando le colonne non necessarie, è possibile ridurre le dimensioni del modello.</span><span class="sxs-lookup"><span data-stu-id="d2649-162">Eliminating unnecessary columns will make your model smaller.</span></span>  
  
3.  <span data-ttu-id="d2649-163">Verificare che tutte le altre colonne siano selezionate e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2649-163">Verify that all other columns are checked, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d2649-164">Si noti che le parole **filtri applicati** sono ora visualizzate nella colonna **Dettagli filtro** nella riga **Customer** ; Se si fa clic su tale collegamento, viene visualizzata una descrizione testuale dei filtri appena applicati.</span><span class="sxs-lookup"><span data-stu-id="d2649-164">Notice the words **Applied filters** are now displayed in the **Filter Details** column in the **Customer** row; if you click on that link you'll see a text description of the filters you just applied.</span></span>  
  
4.  <span data-ttu-id="d2649-165">Filtrare le tabelle restanti deselezionando le caselle di controllo per le colonne seguenti in ogni tabella:</span><span class="sxs-lookup"><span data-stu-id="d2649-165">Filter the remaining tables by clearing the checkboxes for the following columns in each table:</span></span>  
  
    |<span data-ttu-id="d2649-166">Data</span><span class="sxs-lookup"><span data-stu-id="d2649-166">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="d2649-167">**DateKey**</span><span class="sxs-lookup"><span data-stu-id="d2649-167">**DateKey**</span></span>|  
    |<span data-ttu-id="d2649-168">**SpanishDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="d2649-168">**SpanishDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="d2649-169">**FrenchDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="d2649-169">**FrenchDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="d2649-170">**SpanishMonthName**</span><span class="sxs-lookup"><span data-stu-id="d2649-170">**SpanishMonthName**</span></span>|  
    |<span data-ttu-id="d2649-171">**FrenchMonthName**</span><span class="sxs-lookup"><span data-stu-id="d2649-171">**FrenchMonthName**</span></span>|  
  
    |<span data-ttu-id="d2649-172">Area geografica</span><span class="sxs-lookup"><span data-stu-id="d2649-172">Geography</span></span>|  
    |---------------|  
    |<span data-ttu-id="d2649-173">**SpanishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="d2649-173">**SpanishCountryRegionName**</span></span>|  
    |<span data-ttu-id="d2649-174">**FrenchCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="d2649-174">**FrenchCountryRegionName**</span></span>|  
    |<span data-ttu-id="d2649-175">**IpAddressLocator**</span><span class="sxs-lookup"><span data-stu-id="d2649-175">**IpAddressLocator**</span></span>|  
  
    |<span data-ttu-id="d2649-176">Prodotto</span><span class="sxs-lookup"><span data-stu-id="d2649-176">Product</span></span>|  
    |-------------|  
    |<span data-ttu-id="d2649-177">**SpanishProductName**</span><span class="sxs-lookup"><span data-stu-id="d2649-177">**SpanishProductName**</span></span>|  
    |<span data-ttu-id="d2649-178">**FrenchProductName**</span><span class="sxs-lookup"><span data-stu-id="d2649-178">**FrenchProductName**</span></span>|  
    |<span data-ttu-id="d2649-179">**FrenchDescription**</span><span class="sxs-lookup"><span data-stu-id="d2649-179">**FrenchDescription**</span></span>|  
    |<span data-ttu-id="d2649-180">**ChineseDescription**</span><span class="sxs-lookup"><span data-stu-id="d2649-180">**ChineseDescription**</span></span>|  
    |<span data-ttu-id="d2649-181">**ArabicDescription**</span><span class="sxs-lookup"><span data-stu-id="d2649-181">**ArabicDescription**</span></span>|  
    |<span data-ttu-id="d2649-182">**HebrewDescription**</span><span class="sxs-lookup"><span data-stu-id="d2649-182">**HebrewDescription**</span></span>|  
    |<span data-ttu-id="d2649-183">**ThaiDescription**</span><span class="sxs-lookup"><span data-stu-id="d2649-183">**ThaiDescription**</span></span>|  
    |<span data-ttu-id="d2649-184">**GermanDescription**</span><span class="sxs-lookup"><span data-stu-id="d2649-184">**GermanDescription**</span></span>|  
    |<span data-ttu-id="d2649-185">**JapaneseDescription**</span><span class="sxs-lookup"><span data-stu-id="d2649-185">**JapaneseDescription**</span></span>|  
    |<span data-ttu-id="d2649-186">**TurkishDescription**</span><span class="sxs-lookup"><span data-stu-id="d2649-186">**TurkishDescription**</span></span>|  
  
    |<span data-ttu-id="d2649-187">Categoria di prodotto</span><span class="sxs-lookup"><span data-stu-id="d2649-187">Product Category</span></span>|  
    |----------------------|  
    |<span data-ttu-id="d2649-188">**SpanishProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="d2649-188">**SpanishProductCategoryName**</span></span>|  
    |<span data-ttu-id="d2649-189">**FrenchProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="d2649-189">**FrenchProductCategoryName**</span></span>|  
  
    |<span data-ttu-id="d2649-190">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="d2649-190">Product Subcategory</span></span>|  
    |-------------------------|  
    |<span data-ttu-id="d2649-191">**SpanishProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="d2649-191">**SpanishProductSubcategoryName**</span></span>|  
    |<span data-ttu-id="d2649-192">**FrenchProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="d2649-192">**FrenchProductSubcategoryName**</span></span>|  
  
    |<span data-ttu-id="d2649-193">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="d2649-193">Internet Sales</span></span>|  
    |--------------------|  
    |<span data-ttu-id="d2649-194">**OrderDateKey**</span><span class="sxs-lookup"><span data-stu-id="d2649-194">**OrderDateKey**</span></span>|  
    |<span data-ttu-id="d2649-195">**DueDateKey**</span><span class="sxs-lookup"><span data-stu-id="d2649-195">**DueDateKey**</span></span>|  
    |<span data-ttu-id="d2649-196">**ShipDateKey**</span><span class="sxs-lookup"><span data-stu-id="d2649-196">**ShipDateKey**</span></span>|  
  
 <span data-ttu-id="d2649-197">Dopo avere visualizzato l'anteprima ed escluso tramite filtro i dati non necessari, è possibile importare i dati.</span><span class="sxs-lookup"><span data-stu-id="d2649-197">Now that you have previewed and filtered out unnecessary data, you can import the data.</span></span> <span data-ttu-id="d2649-198">Passare alla sezione successiva **Importare i dati di tabelle e colonna selezionati**.</span><span class="sxs-lookup"><span data-stu-id="d2649-198">Go to the next section **Import the Selected Tables and Column Data**.</span></span>  
  
##  <a name="import-the-selected-tables-and-column-data"></a><a name="Import"></a><span data-ttu-id="d2649-199">Importa i dati delle tabelle e delle colonne selezionate</span><span class="sxs-lookup"><span data-stu-id="d2649-199">Import the Selected Tables and Column Data</span></span>  
 <span data-ttu-id="d2649-200">È ora possibile importare i dati selezionati.</span><span class="sxs-lookup"><span data-stu-id="d2649-200">You can now import the selected data.</span></span> <span data-ttu-id="d2649-201">La procedura guidata consente di importare i dati delle tabelle e qualsiasi relazione presente tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="d2649-201">The wizard imports the table data along with any relationships between tables.</span></span> <span data-ttu-id="d2649-202">Nel modello verranno create nuove tabelle e colonne utilizzando i nomi descrittivi specificati e i dati esclusi tramite filtro non verranno importati.</span><span class="sxs-lookup"><span data-stu-id="d2649-202">New tables and columns are created in the model using the friendly names you specified, and data that you filtered out will not be imported.</span></span>  
  
#### <a name="to-import-the-selected-tables-and-column-data"></a><span data-ttu-id="d2649-203">Per importare i dati delle tabelle e delle colonne selezionate</span><span class="sxs-lookup"><span data-stu-id="d2649-203">To import the selected tables and column data</span></span>  
  
1.  <span data-ttu-id="d2649-204">Controllare le selezioni.</span><span class="sxs-lookup"><span data-stu-id="d2649-204">Review your selections.</span></span> <span data-ttu-id="d2649-205">Se sono corrette, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d2649-205">If everything looks OK, click **Finish**.</span></span>  
  
     <span data-ttu-id="d2649-206">Durante l'importazione dei dati la procedura guidata visualizza il numero di righe recuperate.</span><span class="sxs-lookup"><span data-stu-id="d2649-206">While importing the data, the wizard displays how many rows have been fetched.</span></span> <span data-ttu-id="d2649-207">Una volta importati tutti i dati, verrà visualizzato un messaggio in cui viene indicato il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d2649-207">When all the data has been imported, a message indicating success is displayed.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="d2649-208">Per vedere le relazioni create automaticamente tra le tabelle importate, fare clic su **Dettagli** nella riga **Preparazione dati**.</span><span class="sxs-lookup"><span data-stu-id="d2649-208">To see the relationships that were automatically created between the imported tables, on the **Data preparation** row, click **Details**.</span></span>  
  
2.  <span data-ttu-id="d2649-209">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="d2649-209">Click **Close**.</span></span>  
  
     <span data-ttu-id="d2649-210">La procedura guidata verrà chiusa e verrà visualizzata la finestra Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="d2649-210">The wizard closes and the model designer is visible.</span></span> <span data-ttu-id="d2649-211">Ogni tabella è stata aggiunta come nuova scheda in Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="d2649-211">Each table has been added as a new tab in the model designer.</span></span>  
  
## <a name="save-the-model-project"></a><span data-ttu-id="d2649-212">Salvare il progetto di modello.</span><span class="sxs-lookup"><span data-stu-id="d2649-212">Save the Model Project</span></span>  
 <span data-ttu-id="d2649-213">È importante salvare frequentemente il progetto di modello.</span><span class="sxs-lookup"><span data-stu-id="d2649-213">It is important to frequently save your model project.</span></span>  
  
#### <a name="to-save-the-model-project"></a><span data-ttu-id="d2649-214">Per salvare il progetto del modello</span><span class="sxs-lookup"><span data-stu-id="d2649-214">To save the model project</span></span>  
  
-   <span data-ttu-id="d2649-215">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]scegliere **Salva tutto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="d2649-215">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **File** menu, and then click **Save All**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d2649-216">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d2649-216">Next Step</span></span>  
 <span data-ttu-id="d2649-217">Per continuare questa esercitazione, passare alla lezione successiva: [Lezione 3: Rinominare colonne](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="d2649-217">To continue this tutorial, go to the next lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
  
