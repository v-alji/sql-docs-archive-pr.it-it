---
title: Definizione di una vista origine dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af00938a-5a06-4fae-b2fc-f3fb0ca3cea5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d59c5fbe5fd4a07596745447567a72499ddabd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623557"
---
# <a name="defining-a-data-source-view"></a><span data-ttu-id="dc228-102">Definizione di una vista origine dati</span><span class="sxs-lookup"><span data-stu-id="dc228-102">Defining a Data Source View</span></span>
  <span data-ttu-id="dc228-103">Dopo aver definito le origini dati che si utilizzeranno in un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , il passaggio successivo consiste in genere nella definizione di una vista origine dati per il progetto.</span><span class="sxs-lookup"><span data-stu-id="dc228-103">After you define the data sources that you will use in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, the next step is generally to define a data source view for the project.</span></span> <span data-ttu-id="dc228-104">Una vista origine dati è una vista singola unificata dei metadati delle tabelle e delle viste specificate definite dall'origine dati nel progetto.</span><span class="sxs-lookup"><span data-stu-id="dc228-104">A data source view is a single, unified view of the metadata from the specified tables and views that the data source defines in the project.</span></span> <span data-ttu-id="dc228-105">L'archiviazione dei metadati nella vista origine dati consente di lavorare con i metadati durante lo sviluppo senza una connessione aperta con un'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="dc228-105">Storing the metadata in the data source view enables you to work with the metadata during development without an open connection to any underlying data source.</span></span> <span data-ttu-id="dc228-106">Per altre informazioni, vedere [Viste origine dati in modelli multidimensionali](multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="dc228-106">For more information, see [Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="dc228-107">Nell'attività che segue si definirà una vista origine dati che include cinque tabelle dell'origine dati **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="dc228-107">In the following task, you define a data source view that includes five tables from the **AdventureWorksDW2012** data source.</span></span>  
  
### <a name="to-define-a-new-data-source-view"></a><span data-ttu-id="dc228-108">Per definire una nuova vista origine dati</span><span class="sxs-lookup"><span data-stu-id="dc228-108">To define a new data source view</span></span>  
  
1.  <span data-ttu-id="dc228-109">In Esplora soluzioni (a destra della finestra di Microsoft Visual Studio) fare clic con il pulsante destro del mouse su **Viste origine dati**, quindi scegliere **Nuova vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="dc228-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Source Views**, and then click **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="dc228-110">Nella pagina **Creazione guidata vista origine dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dc228-110">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span> <span data-ttu-id="dc228-111">Viene visualizzata la pagina **Selezione origine dati** .</span><span class="sxs-lookup"><span data-stu-id="dc228-111">The **Select a Data Source** page appears.</span></span>  
  
3.  <span data-ttu-id="dc228-112">In **Origine dati relazionali**è selezionata l'origine dati **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="dc228-112">Under **Relational data sources**, the **Adventure Works DW 2012** data source is selected.</span></span> <span data-ttu-id="dc228-113">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dc228-113">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc228-114">Per creare una vista origine dati basata su più origini dati, definire innanzitutto una vista origine dati basata su una singola origine dati</span><span class="sxs-lookup"><span data-stu-id="dc228-114">To create a data source view that is based on multiple data sources, first define a data source view that is based on a single data source.</span></span> <span data-ttu-id="dc228-115">che viene chiamata origine dati primaria.</span><span class="sxs-lookup"><span data-stu-id="dc228-115">This data source is then called the primary data source.</span></span> <span data-ttu-id="dc228-116">Successivamente, è possibile aggiungere tabelle e viste di un'origine dati secondaria.</span><span class="sxs-lookup"><span data-stu-id="dc228-116">You can then add tables and views from a secondary data source.</span></span> <span data-ttu-id="dc228-117">Quando si progettano dimensioni contenenti attributi basati su tabelle correlate in più origini dati, potrebbe essere necessario definire un'origine dati di [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] come origine dati primaria allo scopo di usare le funzionalità del motore delle query distribuite.</span><span class="sxs-lookup"><span data-stu-id="dc228-117">When designing dimensions that contain attributes based on related tables in multiple data sources, you might need to define a [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] data source as the primary data source to use its distributed query engine capabilities.</span></span>  
  
4.  <span data-ttu-id="dc228-118">Nella pagina **Selezione tabelle e viste** selezionare le tabelle e le viste nell'elenco di oggetti disponibili nell'origine dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="dc228-118">On the **Select Tables and Views** page, select tables and views from the list of objects that are available from the selected data source.</span></span> <span data-ttu-id="dc228-119">Questo elenco può essere filtrato in modo da agevolare la selezione di tabelle e viste.</span><span class="sxs-lookup"><span data-stu-id="dc228-119">You can filter this list to help you select tables and views.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc228-120">Fare clic sul pulsante di ingrandimento nell'angolo superiore destro in modo da visualizzare la finestra a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="dc228-120">Click the maximize button in the upper-right corner so that the window covers the full screen.</span></span> <span data-ttu-id="dc228-121">In questo modo risulterà più semplice visualizzare l'elenco completo di oggetti disponibili.</span><span class="sxs-lookup"><span data-stu-id="dc228-121">This makes it easier to see the complete list of available objects.</span></span>  
  
     <span data-ttu-id="dc228-122">Nell'elenco **Oggetti disponibili** selezionare gli oggetti seguenti.</span><span class="sxs-lookup"><span data-stu-id="dc228-122">In the **Available objects** list, select the following objects.</span></span> <span data-ttu-id="dc228-123">Per selezionare più tabelle, fare clic su ognuna di esse tenendo premuto CTRL:</span><span class="sxs-lookup"><span data-stu-id="dc228-123">You can select multiple tables by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="dc228-124">**DimCustomer (dbo)**</span><span class="sxs-lookup"><span data-stu-id="dc228-124">**DimCustomer (dbo)**</span></span>  
  
    -   <span data-ttu-id="dc228-125">**DimDate (dbo)**</span><span class="sxs-lookup"><span data-stu-id="dc228-125">**DimDate (dbo)**</span></span>  
  
    -   <span data-ttu-id="dc228-126">**DimGeography (dbo)**</span><span class="sxs-lookup"><span data-stu-id="dc228-126">**DimGeography (dbo)**</span></span>  
  
    -   <span data-ttu-id="dc228-127">**DimProduct (dbo)**</span><span class="sxs-lookup"><span data-stu-id="dc228-127">**DimProduct (dbo)**</span></span>  
  
    -   <span data-ttu-id="dc228-128">**FactInternetSales (dbo)**</span><span class="sxs-lookup"><span data-stu-id="dc228-128">**FactInternetSales (dbo)**</span></span>  
  
5.  <span data-ttu-id="dc228-129">Fare clic su questo pulsante **>** per aggiungere le tabelle selezionate all'elenco **oggetti inclusi** .</span><span class="sxs-lookup"><span data-stu-id="dc228-129">Click **>** to add the selected tables to the **Included objects** list.</span></span>  
  
6.  <span data-ttu-id="dc228-130">Fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="dc228-130">Click **Next.**</span></span>  
  
7.  <span data-ttu-id="dc228-131">Nel campo Nome assicurarsi che sia visualizzato **Adventure Works DW 2012** , quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="dc228-131">In the Name field, make sure **Adventure Works DW 2012** displays, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="dc228-132">La vista origine dati **Adventure Works DW 2012** viene visualizzata nella cartella **Viste origine dati** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="dc228-132">The **Adventure Works DW 2012** data source view appears in the **Data Source Views** folder in Solution Explorer.</span></span> <span data-ttu-id="dc228-133">Il contenuto della vista origine dati verrà inoltre visualizzato in Progettazione vista origine dati in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc228-133">The content of the data source view is also displayed in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="dc228-134">Questa finestra di progettazione contiene i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="dc228-134">This designer contains the following elements:</span></span>  
  
    -   <span data-ttu-id="dc228-135">Un riquadro **Diagramma** in cui sono rappresentate graficamente le tabelle e le relative relazioni.</span><span class="sxs-lookup"><span data-stu-id="dc228-135">A **Diagram** pane in which the tables and their relationships are represented graphically.</span></span>  
  
    -   <span data-ttu-id="dc228-136">Un riquadro **Tabelle** in cui le tabelle e i relativi elementi di schema sono visualizzati in una visualizzazione albero.</span><span class="sxs-lookup"><span data-stu-id="dc228-136">A **Tables** pane in which the tables and their schema elements are displayed in a tree view.</span></span>  
  
    -   <span data-ttu-id="dc228-137">Un riquadro **Libreria diagrammi** in cui è possibile creare diagrammi secondari che consentono di visualizzare subset della vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="dc228-137">A **Diagram Organizer** pane in which you can create subdiagrams so that you can view subsets of the data source view.</span></span>  
  
    -   <span data-ttu-id="dc228-138">Una barra degli strumenti specifica di Progettazione vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="dc228-138">A toolbar that is specific to Data Source View Designer.</span></span>  
  
8.  <span data-ttu-id="dc228-139">Per ingrandire l'ambiente di sviluppo di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , fare clic sul pulsante **Ingrandisci** .</span><span class="sxs-lookup"><span data-stu-id="dc228-139">To maximize the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment, click the **Maximize** button.</span></span>  
  
9. <span data-ttu-id="dc228-140">Per visualizzare le tabelle nel riquadro **Diagramma** al 50%, fare clic sull'icona **Zoom** sulla barra degli strumenti di Progettazione vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="dc228-140">To view the tables in the **Diagram** pane at 50 percent, click the **Zoom** icon on the Data Source View Designer toolbar.</span></span> <span data-ttu-id="dc228-141">In questo modo i dettagli delle colonne di ogni tabella verranno nascosti.</span><span class="sxs-lookup"><span data-stu-id="dc228-141">This will hide the column details of each table.</span></span>  
  
10. <span data-ttu-id="dc228-142">Per nascondere Esplora soluzioni, fare clic sul pulsante **Nascondi automaticamente** , ovvero l'icona con la puntina sulla barra del titolo.</span><span class="sxs-lookup"><span data-stu-id="dc228-142">To hide Solution Explorer, click the **Auto Hide** button, which is the pushpin icon on the title bar.</span></span> <span data-ttu-id="dc228-143">Per visualizzare nuovamente Esplora soluzioni, posizionare il puntatore sulla scheda corrispondente sul lato destro dell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dc228-143">To view Solution Explorer again, position your pointer over the Solution Explorer tab along the right side of the development environment.</span></span> <span data-ttu-id="dc228-144">Per scoprire Esplora soluzioni, fare di nuovo clic sul pulsante **Nascondi automaticamente** .</span><span class="sxs-lookup"><span data-stu-id="dc228-144">To unhide Solution Explorer, click the **Auto Hide** button again.</span></span>  
  
11. <span data-ttu-id="dc228-145">Se le finestre non sono nascoste per impostazione predefinita, fare clic su **Nascondi automaticamente** sulla barra del titolo delle finestre Proprietà ed Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="dc228-145">If the windows are not hidden by default, click **Auto Hide** on the title bar of the Properties and Solution Explorer windows.</span></span>  
  
     <span data-ttu-id="dc228-146">A questo punto è possibile visualizzare tutte le tabelle e le relative relazioni nel riquadro **Diagramma** .</span><span class="sxs-lookup"><span data-stu-id="dc228-146">You can now view all the tables and their relationships in the **Diagram** pane.</span></span> <span data-ttu-id="dc228-147">Si noti che tra la tabella FactInternetSales e la tabella DimDate esistono tre relazioni.</span><span class="sxs-lookup"><span data-stu-id="dc228-147">Notice that there are three relationships between the FactInternetSales table and the DimDate table.</span></span> <span data-ttu-id="dc228-148">A ogni vendita sono associate tre date: data di ordine, di scadenza e di spedizione.</span><span class="sxs-lookup"><span data-stu-id="dc228-148">Each sale has three dates associated with the sale: an order date, a due date, and a ship date.</span></span> <span data-ttu-id="dc228-149">Per visualizzare i dettagli di una relazione, fare doppio clic sulla relativa freccia nel riquadro **Diagramma** .</span><span class="sxs-lookup"><span data-stu-id="dc228-149">To view the details of any relationship, double-click the relationship arrow in the **Diagram** pane.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dc228-150">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="dc228-150">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dc228-151">Modifica dei nomi predefiniti delle tabelle</span><span class="sxs-lookup"><span data-stu-id="dc228-151">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc228-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc228-152">See Also</span></span>  
 [<span data-ttu-id="dc228-153">Viste origine dati in modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="dc228-153">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
