---
title: Definizione e utilizzo di un'azione drill-through | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3765f865-2b93-44be-b290-28e3815d5ecb
author: minewiskan
ms.author: owend
ms.openlocfilehash: ea19a9721d87936bc88b5401c71ee550a47bc1ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714704"
---
# <a name="defining-and-using-a-drillthrough-action"></a><span data-ttu-id="b6f98-102">Definizione e utilizzo di un'azione drill-through</span><span class="sxs-lookup"><span data-stu-id="b6f98-102">Defining and Using a Drillthrough Action</span></span>
  <span data-ttu-id="b6f98-103">Il dimensionamento dei dati della tabella dei fatti tramite una dimensione dei fatti senza l'applicazione di un filtro appropriato sui dati restituiti dalla query può causare un rallentamento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b6f98-103">Dimensioning fact data by a fact dimension without correctly filtering the data that the query returns can cause slow query performance.</span></span> <span data-ttu-id="b6f98-104">Per evitare questo problema, è possibile definire un'azione drill-through che limita il numero complessivo di righe restituite.</span><span class="sxs-lookup"><span data-stu-id="b6f98-104">To avoid this, you can define a drillthrough action that restricts the total number of rows that are returned.</span></span> <span data-ttu-id="b6f98-105">In questo modo è possibile migliorare in modo significativo le prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="b6f98-105">This will significantly improve query performance.</span></span>  
  
 <span data-ttu-id="b6f98-106">Nelle procedure descritte in questo argomento viene definita un'azione drill-through per restituire informazioni dettagliate sugli ordini relativi alle vendite ai clienti su Internet.</span><span class="sxs-lookup"><span data-stu-id="b6f98-106">In the tasks in this topic, you define a drillthrough action to return order detail information for sales to customers over the Internet.</span></span>  
  
## <a name="defining-the-drillthrough-action-properties"></a><span data-ttu-id="b6f98-107">Definizione delle proprietà di un'azione drill-through</span><span class="sxs-lookup"><span data-stu-id="b6f98-107">Defining the Drillthrough Action Properties</span></span>  
  
1.  <span data-ttu-id="b6f98-108">In Progettazione cubi per il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial fare clic sulla scheda **Azioni** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-108">In Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, click the **Actions** tab.</span></span>  
  
     <span data-ttu-id="b6f98-109">La scheda **Azioni** include diversi riquadri.</span><span class="sxs-lookup"><span data-stu-id="b6f98-109">The **Actions** tab includes several panes.</span></span> <span data-ttu-id="b6f98-110">Sul lato sinistro della scheda si trovano il riquadro **Libreria azioni** e il riquadro **Strumenti di calcolo** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-110">On the left side of the tab are the **Action Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="b6f98-111">Il riquadro a destra di questi due riquadri è il riquadro **Visualizza** , contenente i dettagli dell'azione selezionata nel riquadro **Libreria azioni** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-111">The pane to the right of these two panes is the **Display** pane, which contains the details of the action that is selected in the **Action Organizer** pane.</span></span>  
  
     <span data-ttu-id="b6f98-112">La figura seguente illustra la scheda **Azioni** di Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="b6f98-112">The following image shows the **Actions** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="b6f98-113">![Scheda Azioni di Progettazione cubi](../../2014/tutorials/media/l8-action1.gif "Scheda Azioni di Progettazione cubi")</span><span class="sxs-lookup"><span data-stu-id="b6f98-113">![Actions tab of Cube Designer](../../2014/tutorials/media/l8-action1.gif "Actions tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="b6f98-114">Fare clic sul pulsante **Nuova azione dril-through** sulla barra degli strumenti della scheda **Azioni** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-114">On the toolbar of the **Actions** tab, click the **New Drillthrough Action** button.</span></span>  
  
     <span data-ttu-id="b6f98-115">Nel riquadro di visualizzazione verrà visualizzato un modello Azione vuoto.</span><span class="sxs-lookup"><span data-stu-id="b6f98-115">A blank action template appears in the display pane.</span></span>  
  
     <span data-ttu-id="b6f98-116">![Modello di azione vuota nel riquadro di visualizzazione](../../2014/tutorials/media/l8-action2.gif "Modello di azione vuota nel riquadro di visualizzazione")</span><span class="sxs-lookup"><span data-stu-id="b6f98-116">![Blank Action template in the display pane](../../2014/tutorials/media/l8-action2.gif "Blank Action template in the display pane")</span></span>  
  
3.  <span data-ttu-id="b6f98-117">Nella casella **nome** modificare il nome dell'azione in `Internet Sales Details Drillthrough Action` .</span><span class="sxs-lookup"><span data-stu-id="b6f98-117">In the **Name** box, change the name of this action to `Internet Sales Details Drillthrough Action`.</span></span>  
  
4.  <span data-ttu-id="b6f98-118">Selezionare **Internet Sales** dall'elenco **Membri gruppo di misure**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-118">In the **Measure group members** list, select **Internet Sales**.</span></span>  
  
5.  <span data-ttu-id="b6f98-119">Nella casella **Colonne drill-through** selezionare **Dettagli ordine vendita Internet** nell'elenco **Dimensioni** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-119">In the **Drillthrough Columns** box, select **Internet Sales Order Details** in the **Dimensions** list.</span></span>  
  
6.  <span data-ttu-id="b6f98-120">Nell'elenco **Colonne restituite** selezionare le caselle di controllo **Item Description** e **Order Number** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-120">In the **Return Columns** list, select the **Item Description** and the **Order Number** check boxes, and then click **OK**.</span></span> <span data-ttu-id="b6f98-121">Nella figura seguente viene illustrato l'aspetto che dovrebbe avere assunto il modello Azione a questo punto della procedura.</span><span class="sxs-lookup"><span data-stu-id="b6f98-121">The following image shows the Action template as it should appear at this point in this procedure.</span></span>  
  
     <span data-ttu-id="b6f98-122">![Casella Colonne drill-through](../../2014/tutorials/media/l8-action3.gif "Casella Colonne drill-through")</span><span class="sxs-lookup"><span data-stu-id="b6f98-122">![Drillthrough Columns box](../../2014/tutorials/media/l8-action3.gif "Drillthrough Columns box")</span></span>  
  
7.  <span data-ttu-id="b6f98-123">Espandere la casella **Proprietà aggiuntive** , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="b6f98-123">Expand the **Additional Properties** box, as shown in the following image.</span></span>  
  
     <span data-ttu-id="b6f98-124">![Casella Proprietà aggiuntive](../../2014/tutorials/media/l8-action4.gif "Casella Proprietà aggiuntive")</span><span class="sxs-lookup"><span data-stu-id="b6f98-124">![Additional Properties box](../../2014/tutorials/media/l8-action4.gif "Additional Properties box")</span></span>  
  
8.  <span data-ttu-id="b6f98-125">Nella casella **numero massimo di righe** Digitare `10` .</span><span class="sxs-lookup"><span data-stu-id="b6f98-125">In the **Maximum Rows** box, type `10`.</span></span>  
  
9. <span data-ttu-id="b6f98-126">Nella casella **didascalia** Digitare `Drillthrough to Order Details...` .</span><span class="sxs-lookup"><span data-stu-id="b6f98-126">In the **Caption** box, type `Drillthrough to Order Details...`.</span></span>  
  
     <span data-ttu-id="b6f98-127">Queste impostazioni limitano il numero di righe restituite e specificano la didascalia che viene visualizzata nel menu dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="b6f98-127">These settings limit the number of rows returned and specify the caption that appears in the client application menu.</span></span> <span data-ttu-id="b6f98-128">La figura seguente illustra tali impostazioni all'interno della casella **Proprietà aggiuntive** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-128">The following image shows these settings in the **AdditionalProperties** box.</span></span>  
  
     <span data-ttu-id="b6f98-129">![Casella Proprietà aggiuntive](../../2014/tutorials/media/l8-action5.gif "Casella Proprietà aggiuntive")</span><span class="sxs-lookup"><span data-stu-id="b6f98-129">![Additional Properties box](../../2014/tutorials/media/l8-action5.gif "Additional Properties box")</span></span>  
  
## <a name="using-the-drillthrough-action"></a><span data-ttu-id="b6f98-130">Utilizzo dell'azione drill-through</span><span class="sxs-lookup"><span data-stu-id="b6f98-130">Using the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="b6f98-131">Scegliere **Distribuisci Analysis Services Tutorial** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-131">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="b6f98-132">Una volta completata la distribuzione, selezionare la scheda **Esplorazione** in Progettazione cubi per il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial e fare clic sul pulsante **Riconnetti** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-132">When deployment has successfully completed, click the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="b6f98-133">Avviare Excel.</span><span class="sxs-lookup"><span data-stu-id="b6f98-133">Start Excel.</span></span>  
  
4.  <span data-ttu-id="b6f98-134">Aggiungere la misura **Internet Sales-Sales Amount** all'area Valori.</span><span class="sxs-lookup"><span data-stu-id="b6f98-134">Add the **Internet Sales-Sales Amount** measure to the Values area.</span></span>  
  
5.  <span data-ttu-id="b6f98-135">Aggiungere la gerarchia definita dall'utente **Customer Geography** della cartella **Location** nella dimensione **Customer** all'area **Filtro report** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-135">Add the **Customer Geography** user-defined hierarchy from the **Location** folder in the **Customer** dimension to the **Report Filter** area.</span></span>  
  
6.  <span data-ttu-id="b6f98-136">In **Customer Geography**nella tabella pivot aggiungere un filtro per selezionare un solo cliente.</span><span class="sxs-lookup"><span data-stu-id="b6f98-136">On the PivotTable, in **Customer Geography**, add a filter that selects a single customer.</span></span> <span data-ttu-id="b6f98-137">Espandere **All Customers**, **Australia**, **Queensland**, **Brisbane**e **4000**, selezionare la casella di controllo corrispondente ad **Adam Powell**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-137">Expand **All Customers**, expand **Australia**, expand **Queensland**, expand **Brisbane**, expand **4000**, select the check box for **Adam Powell**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b6f98-138">Il totale dei prodotti venduti da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] ad Adam Powell viene visualizzato nell'area dati.</span><span class="sxs-lookup"><span data-stu-id="b6f98-138">The total sales of products by [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] to Adam Powell are displayed in the data area.</span></span>  
  
7.  <span data-ttu-id="b6f98-139">Fare clic con il pulsante destro del mouse sull'importo delle vendite, scegliere **Additional Actions**(Azioni aggiuntive) e fare clic su **Drillthrough to Order Details**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-139">Right-click on the sales amount, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="b6f98-140">I dettagli degli ordini spediti ad Adam Powell vengono visualizzati nel **visualizzatore dati di esempio**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="b6f98-140">The details of the orders that were shipped to Adam Powell are displayed in the **Data Sample Viewer**, as shown in the following image.</span></span> <span data-ttu-id="b6f98-141">Servirebbero tuttavia alcuni dettagli supplementari, ad esempio la data dell'ordine, la data di scadenza e la data di spedizione.</span><span class="sxs-lookup"><span data-stu-id="b6f98-141">However, some additional details would also be useful, such as the order date, due date, and ship date.</span></span> <span data-ttu-id="b6f98-142">Nella procedura seguente si aggiungeranno tali dettagli supplementari.</span><span class="sxs-lookup"><span data-stu-id="b6f98-142">In the next procedure, you will add these additional details.</span></span>  
  
     <span data-ttu-id="b6f98-143">![Ordini spediti ad Adam Powell](../../2014/tutorials/media/l8-action6.gif "Ordini spediti ad Adam Powell")</span><span class="sxs-lookup"><span data-stu-id="b6f98-143">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action6.gif "Orders shipped to Adam Powell")</span></span>  
  
8.  <span data-ttu-id="b6f98-144">Chiudere Excel.</span><span class="sxs-lookup"><span data-stu-id="b6f98-144">Close Excel/</span></span>  
  
## <a name="modifying-the-drillthrough-action"></a><span data-ttu-id="b6f98-145">Modifica dell'azione drill-through</span><span class="sxs-lookup"><span data-stu-id="b6f98-145">Modifying the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="b6f98-146">Aprire Progettazione dimensioni per la dimensione **Internet Sales Order Details** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-146">Open Dimension Designer for the **Internet Sales Order Details** dimension.</span></span>  
  
     <span data-ttu-id="b6f98-147">Si noti che sono stati definiti solo tre attributi per questa dimensione.</span><span class="sxs-lookup"><span data-stu-id="b6f98-147">Notice that only three attributes have been defined for this dimension.</span></span>  
  
2.  <span data-ttu-id="b6f98-148">Nel riquadro **Vista origine dati** fare clic con il pulsante destro del mouse su un'area aperta e scegliere **Mostra tutte le tabelle**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-148">In the **Data Source View** pane, right-click an open area, and then click **Show All Tables**.</span></span>  
  
3.  <span data-ttu-id="b6f98-149">Scegliere **Layout automatico** dal menu **Formato** e fare clic su **Diagramma**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-149">On the **Format** menu, point to **Autolayout** and then click **Diagram**.</span></span>  
  
4.  <span data-ttu-id="b6f98-150">Individuare la tabella **InternetSales (dbo.FactInternetSales)** facendo clic con il pulsante destro del mouse in un'area aperta del riquadro **Vista origine dati** .</span><span class="sxs-lookup"><span data-stu-id="b6f98-150">Locate the **InternetSales (dbo.FactInternetSales)** table by right-clicking in an open area of the **Data Source View** pane.</span></span> <span data-ttu-id="b6f98-151">Scegliere **Trova tabella** , selezionare **InternetSales** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-151">Then click **Find Table,** click **InternetSales,** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="b6f98-152">Creare nuovi attributi in base alle colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6f98-152">Create new attributes based on the following columns:</span></span>  
  
    -   <span data-ttu-id="b6f98-153">OrderDateKey</span><span class="sxs-lookup"><span data-stu-id="b6f98-153">OrderDateKey</span></span>  
  
    -   <span data-ttu-id="b6f98-154">DueDateKey</span><span class="sxs-lookup"><span data-stu-id="b6f98-154">DueDateKey</span></span>  
  
    -   <span data-ttu-id="b6f98-155">ShipDateKey</span><span class="sxs-lookup"><span data-stu-id="b6f98-155">ShipDateKey</span></span>  
  
6.  <span data-ttu-id="b6f98-156">Modificare la proprietà **Name** dell'attributo **Order Date Key** su `Order Date` then, fare clic sul pulsante Browse per la proprietà **nome colonna** e nella finestra di dialogo **colonna nome** selezionare **date** come tabella di origine e selezionare SimpleDate come colonna di origine.</span><span class="sxs-lookup"><span data-stu-id="b6f98-156">Change the **Name** property for the **Order Date Key** attribute to `Order Date` Then, click the browse button for the **Name Column** property, and in the **Name Column** dialog box, select **Date** as the source table and select SimpleDate as the source column.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="b6f98-157">Modificare la proprietà **Name** dell'attributo **date date Key** in `Due Date` , quindi, usando lo stesso metodo dell'attributo **Order Date Key** , modificare la proprietà **Name Column** di questo attributo in **date. SimpleDate (WCHAR)**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-157">Change the **Name** property for the **Due Date Key** attribute to `Due Date`, and then, by using the same method as the **Order Date Key** attribute, change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
8.  <span data-ttu-id="b6f98-158">Modificare la proprietà **Name** dell'attributo **Ship Date Key** in `Ship Date` , quindi modificare la proprietà **Name Column** di questo attributo in **date. SimpleDate (WCHAR)**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-158">Change the **Name** property for the **Ship Date Key** attribute to `Ship Date`, and then change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
9. <span data-ttu-id="b6f98-159">Passare alla scheda \*\*Azioni[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] di Progettazione cubi per il cubo \*\* Tutorial.</span><span class="sxs-lookup"><span data-stu-id="b6f98-159">Switch to the **Actions** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
10. <span data-ttu-id="b6f98-160">Nella casella **Colonne drill-through** selezionare le caselle di controllo per aggiungere le colonne seguenti all'elenco **Colonne restituite** e fare clic su **OK**:</span><span class="sxs-lookup"><span data-stu-id="b6f98-160">In the **Drillthrough Columns** box, select the check boxes to add the following columns to the **Return Columns** list, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="b6f98-161">Order Date</span><span class="sxs-lookup"><span data-stu-id="b6f98-161">Order Date</span></span>  
  
    -   <span data-ttu-id="b6f98-162">Due Date</span><span class="sxs-lookup"><span data-stu-id="b6f98-162">Due Date</span></span>  
  
    -   <span data-ttu-id="b6f98-163">Ship Date</span><span class="sxs-lookup"><span data-stu-id="b6f98-163">Ship Date</span></span>  
  
     <span data-ttu-id="b6f98-164">Nella figura seguente vengono illustrate tali colonne selezionate.</span><span class="sxs-lookup"><span data-stu-id="b6f98-164">The following image shows these columns selected.</span></span>  
  
     <span data-ttu-id="b6f98-165">![Casella Colonne drill-through](../../2014/tutorials/media/l8-action7.gif "Casella Colonne drill-through")</span><span class="sxs-lookup"><span data-stu-id="b6f98-165">![Drillthrough Columns box](../../2014/tutorials/media/l8-action7.gif "Drillthrough Columns box")</span></span>  
  
## <a name="reviewing-the-modified-drillthrough-action"></a><span data-ttu-id="b6f98-166">Controllo dell'azione drill-through modificata</span><span class="sxs-lookup"><span data-stu-id="b6f98-166">Reviewing the Modified Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="b6f98-167">Scegliere **Distribuisci Analysis Services Tutorial** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-167">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="b6f98-168">Dopo aver completato la distribuzione, passare alla scheda \*\*Esplorazione[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] in Progettazione cubi per il cubo \*\* Tutorial e fare clic sul pulsante **Riconnetti**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-168">When deployment has successfully completed, switch to the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="b6f98-169">Avviare Excel.</span><span class="sxs-lookup"><span data-stu-id="b6f98-169">Start Excel.</span></span>  
  
4.  <span data-ttu-id="b6f98-170">Ricreare la tabella pivot usando **Internet Sales-Sales Amount** nell'area Valori e **Customer Geography** nel Filtro report.</span><span class="sxs-lookup"><span data-stu-id="b6f98-170">Recreate the PivotTable using **Internet Sales-Sales Amount** in the Values area and **Customer Geography** in the Report Filter.</span></span>  
  
     <span data-ttu-id="b6f98-171">Aggiungere un filtro per selezionare da **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, **Adam Powell**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-171">Add a filter that selects from **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, **Adam Powell**.</span></span>  
  
5.  <span data-ttu-id="b6f98-172">Fare clic sulla cella di dati **Internet Sales-Sales Amount** , scegliere **Additional Actions**(Azioni aggiuntive) e fare clic su **Drillthrough to Order Details**.</span><span class="sxs-lookup"><span data-stu-id="b6f98-172">Click the **Internet Sales-Sales Amount** data cell, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="b6f98-173">I dettagli di questi ordini spediti ad Adam Powell vengono visualizzati in un foglio di lavoro temporaneo.</span><span class="sxs-lookup"><span data-stu-id="b6f98-173">The details of these orders shipped to Adam Powell are displayed in a temporary worksheet.</span></span> <span data-ttu-id="b6f98-174">Tali dettagli includono informazioni relative a descrizione articolo, numero ordine, data dell'ordine, data di scadenza e data di spedizione, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="b6f98-174">This includes item description, order number, order date, due date, and ship date information, as shown in the following image.</span></span>  
  
     <span data-ttu-id="b6f98-175">![Ordini spediti ad Adam Powell](../../2014/tutorials/media/l8-action8.gif "Ordini spediti ad Adam Powell")</span><span class="sxs-lookup"><span data-stu-id="b6f98-175">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action8.gif "Orders shipped to Adam Powell")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b6f98-176">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="b6f98-176">Next Lesson</span></span>  
 [<span data-ttu-id="b6f98-177">Lezione 9: Definizione di prospettive e traduzioni</span><span class="sxs-lookup"><span data-stu-id="b6f98-177">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="b6f98-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6f98-178">See Also</span></span>  
 <span data-ttu-id="b6f98-179">[Azioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b6f98-179">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="b6f98-180">[Azioni nei modelli multidimensionali](multidimensional-models/actions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b6f98-180">[Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="b6f98-181">[Relazioni tra dimensioni](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="b6f98-181">[Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 <span data-ttu-id="b6f98-182">[Definizione di una relazione di tipo Fatti](lesson-5-2-defining-a-fact-relationship.md) </span><span class="sxs-lookup"><span data-stu-id="b6f98-182">[Defining a Fact Relationship](lesson-5-2-defining-a-fact-relationship.md) </span></span>  
 [<span data-ttu-id="b6f98-183">Definire una relazione di tipo Fatti e le relative proprietà</span><span class="sxs-lookup"><span data-stu-id="b6f98-183">Define a Fact Relationship and Fact Relationship Properties</span></span>](multidimensional-models/define-a-fact-relationship-and-fact-relationship-properties.md)  
  
  
