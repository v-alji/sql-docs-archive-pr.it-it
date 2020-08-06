---
title: 'Lezione 4: Aggiunta di una tabella al report (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ddf2914-bcdd-427d-8cba-0ccb8342f819
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52694168bd60b8e3807db6204f33a89815573093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625223"
---
# <a name="lesson-4-adding-a-table-to-the-report-reporting-services"></a><span data-ttu-id="83ad3-102">Lezione 4: Aggiunta di una tabella al report (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="83ad3-102">Lesson 4: Adding a Table to the Report (Reporting Services)</span></span>
  <span data-ttu-id="83ad3-103">Dopo aver definito il set di dati, è possibile iniziare la progettazione del report.</span><span class="sxs-lookup"><span data-stu-id="83ad3-103">After the dataset is defined, you can start designing the report.</span></span> <span data-ttu-id="83ad3-104">È possibile creare un layout del report trascinando le aree dati, le caselle di testo, le immagini e altri elementi che si desidera includere nel report e rilasciandoli nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="83ad3-104">You create a report layout by dragging and dropping data regions, text boxes, images, and other items that you want to include in your report to the design surface.</span></span>  
  
 <span data-ttu-id="83ad3-105">Le *aree dati*sono elementi che contengono righe ripetute di dati provenienti dai set di dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="83ad3-105">Items that contain repeated rows of data from underlying datasets are called *data regions*.</span></span> <span data-ttu-id="83ad3-106">In un report di base è disponibile una sola area dati, tuttavia è possibile aggiungerne altre, ad esempio se si desidera aggiungere un grafico al report tabulare.</span><span class="sxs-lookup"><span data-stu-id="83ad3-106">A basic report will have only one data region, but you can add more, for example, if you want to add a chart to your tabular report.</span></span> <span data-ttu-id="83ad3-107">Dopo avere aggiunto un'area dati, è possibile aggiungervi dei campi.</span><span class="sxs-lookup"><span data-stu-id="83ad3-107">After you add a data region, you can add fields to the data region.</span></span>  
  
### <a name="to-add-a-table-data-region-and-fields-to-a-report-layout"></a><span data-ttu-id="83ad3-108">Per aggiungere un'area dati tabella e campi a un layout del report</span><span class="sxs-lookup"><span data-stu-id="83ad3-108">To add a Table data region and fields to a report layout</span></span>  
  
1.  <span data-ttu-id="83ad3-109">Nella **casella degli strumenti**fare clic su **Tabella**, fare clic sull'area di progettazione e trascinare il mouse.</span><span class="sxs-lookup"><span data-stu-id="83ad3-109">In the **Toolbox**, click **Table**, and then click on the design surface and drag the mouse.</span></span> <span data-ttu-id="83ad3-110">In Progettazione report verrà disegnata un'area dati tabella composta da tre colonne al centro dell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="83ad3-110">Report Designer draws a table data region with three columns in the center of the design surface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="83ad3-111">È possibile che la **casella degli strumenti** venga visualizzata come scheda sul lato sinistro del riquadro **Dati report** .</span><span class="sxs-lookup"><span data-stu-id="83ad3-111">The **Toolbox** may appear as a tab on the left side of the **Report Data** pane.</span></span> <span data-ttu-id="83ad3-112">Per aprire la **casella degli strumenti**, spostare il puntatore sulla scheda della **casella degli strumenti** . Se la **casella degli strumenti** non è visibile, scegliere **casella degli strumenti**dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="83ad3-112">To open the **Toolbox**, move the pointer over the **Toolbox** tab. If the **Toolbox** is not visible, from the **View** menu, click **Toolbox**.</span></span>  
  
2.  <span data-ttu-id="83ad3-113">Nel riquadro **dei dati del report** espandere il set di dati **AdventureWorksDataSet** per visualizzare i campi.</span><span class="sxs-lookup"><span data-stu-id="83ad3-113">In the **Report Data** pane, expand the **AdventureWorksDataset** dataset to display the fields.</span></span>  
  
3.  <span data-ttu-id="83ad3-114">Trascinare il campo Date dal riquadro **Dati report** alla prima colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="83ad3-114">Drag the Date field from the **Report Data** pane to the first column in the table.</span></span>  
  
     <span data-ttu-id="83ad3-115">Quando si rilascia il campo nella prima colonna, si verificano i due eventi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="83ad3-115">When you drop the field into the first column, two things happen.</span></span> <span data-ttu-id="83ad3-116">Inizialmente nella cella di dati verrà visualizzato il nome del campo, noto come *espressione di campo*, tra parentesi: `[Date]`.</span><span class="sxs-lookup"><span data-stu-id="83ad3-116">First, the data cell will display the field name, known as the *field expression*, in brackets: `[Date]`.</span></span> <span data-ttu-id="83ad3-117">In secondo luogo un valore di intestazione di colonna verrà aggiunto automaticamente alla riga Intestazione, proprio sopra l'espressione di campo.</span><span class="sxs-lookup"><span data-stu-id="83ad3-117">Second, a column header value is automatically added to Header row, just above the field expression.</span></span> <span data-ttu-id="83ad3-118">Per impostazione predefinita, il nome della colonna rappresenta il nome del campo.</span><span class="sxs-lookup"><span data-stu-id="83ad3-118">By default, the column is the name of the field.</span></span> <span data-ttu-id="83ad3-119">È possibile selezionare il testo della riga Intestazione e digitare un nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="83ad3-119">You can select the Header row text and type a new name.</span></span>  
  
4.  <span data-ttu-id="83ad3-120">Trascinare il campo Order dal riquadro **Dati report** alla seconda colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="83ad3-120">Drag the Order field from the **Report Data** pane to the second column in the table.</span></span>  
  
5.  <span data-ttu-id="83ad3-121">Trascinare il campo Product dal riquadro **Dati report** alla terza colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="83ad3-121">Drag the Product field from the **Report Data** pane to the third column in the table.</span></span>  
  
6.  <span data-ttu-id="83ad3-122">Trascinare il campo Qty nel bordo destro della terza colonna fino a quando non si ottiene un cursore verticale e il puntatore del mouse assume l'aspetto del segno più [+].</span><span class="sxs-lookup"><span data-stu-id="83ad3-122">Drag the Qty field to the right edge of the third column until you get a vertical cursor and the mouse pointer has a plus sign [+].</span></span> <span data-ttu-id="83ad3-123">Quando si rilascia il pulsante del mouse, viene creata una quarta colonna per `[Qty]`.</span><span class="sxs-lookup"><span data-stu-id="83ad3-123">When you release the mouse button, a fourth column is created for `[Qty]`.</span></span>  
  
7.  <span data-ttu-id="83ad3-124">Aggiungere il campo LineTotal con la stessa procedura, creando una quinta colonna.</span><span class="sxs-lookup"><span data-stu-id="83ad3-124">Add the LineTotal field in the same way, creating a fifth column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="83ad3-125">L'intestazione di colonna è Totale riga.</span><span class="sxs-lookup"><span data-stu-id="83ad3-125">The column header is Line Total.</span></span> <span data-ttu-id="83ad3-126">Progettazione report crea automaticamente un nome descrittivo per la colonna suddividendo LineTotal in due parole.</span><span class="sxs-lookup"><span data-stu-id="83ad3-126">Report Designer automatically creates a friendly name for the column by splitting LineTotal into two words.</span></span>  
  
     <span data-ttu-id="83ad3-127">Nel diagramma riportato di seguito è illustrata un'area dati della tabella popolata con i campi seguenti: Date, Order, Product, Qty e Line Total.</span><span class="sxs-lookup"><span data-stu-id="83ad3-127">The following diagram shows a table data region that has been populated with these fields: Date, Order, Product, Qty, and Line Total.</span></span>  
  
     <span data-ttu-id="83ad3-128">![Progettazione, tabella con riga di intestazione e riga di dettaglio](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Progettazione, tabella con riga di intestazione e riga di dettaglio")</span><span class="sxs-lookup"><span data-stu-id="83ad3-128">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
## <a name="preview-your-report"></a><span data-ttu-id="83ad3-129">Visualizzazione in anteprima di un report</span><span class="sxs-lookup"><span data-stu-id="83ad3-129">Preview Your Report</span></span>  
 <span data-ttu-id="83ad3-130">Mediante la visualizzazione in anteprima di un report è possibile visualizzare il report visualizzabile senza la necessità di pubblicarlo in un server di report.</span><span class="sxs-lookup"><span data-stu-id="83ad3-130">Previewing a report enables you to view the rendered report without having to first publish it to a report server.</span></span> <span data-ttu-id="83ad3-131">In fase di progettazione può risultare utile visualizzare il report in anteprima con una certa frequenza.</span><span class="sxs-lookup"><span data-stu-id="83ad3-131">You will probably want to preview your report frequently during design time.</span></span> <span data-ttu-id="83ad3-132">Tramite la visualizzazione in anteprima del report verrà inoltre eseguita la convalida nelle connessioni dati e alla progettazione in modo che sia possibile correggere eventuali errori prima di pubblicare il report in un server di report.</span><span class="sxs-lookup"><span data-stu-id="83ad3-132">Previewing the report will also run validation on the design and data connections so you can correct errors and issues before publishing the report to a report server.</span></span>  
  
#### <a name="to-preview-a-report"></a><span data-ttu-id="83ad3-133">Per visualizzare l'anteprima di un report</span><span class="sxs-lookup"><span data-stu-id="83ad3-133">To preview a report</span></span>  
  
-   <span data-ttu-id="83ad3-134">Fare clic sulla scheda **Anteprima** . Progettazione report esegue il report e lo Visualizza nella visualizzazione anteprima.</span><span class="sxs-lookup"><span data-stu-id="83ad3-134">Click the **Preview** tab. Report Designer runs the report and displays it in Preview view.</span></span>  
  
     <span data-ttu-id="83ad3-135">Nel diagramma seguente viene mostrata parte del report in visualizzazione Anteprima.</span><span class="sxs-lookup"><span data-stu-id="83ad3-135">The following diagram shows part of the report in Preview view.</span></span>  
  
     <span data-ttu-id="83ad3-136">![Anteprima, righe di dettaglio di una tabella con 5 colonne](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Anteprima, righe di dettaglio di una tabella con 5 colonne")</span><span class="sxs-lookup"><span data-stu-id="83ad3-136">![Preview, Detail rows of table with 5 columns](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Preview, Detail rows of table with 5 columns")</span></span>  
  
     <span data-ttu-id="83ad3-137">Si noti che per la valuta (nella colonna Line Total) sono presenti sei posizioni dopo il numero decimale e per la data è incluso un timestamp.</span><span class="sxs-lookup"><span data-stu-id="83ad3-137">Notice that the currency (in the Line Total column) has six places after the decimal, and the date has includes a time stamp.</span></span> <span data-ttu-id="83ad3-138">Nella lezione successiva verrà illustrato come correggere questa formattazione.</span><span class="sxs-lookup"><span data-stu-id="83ad3-138">You're going to fix that formatting in the next lesson.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83ad3-139">Per salvare il report, scegliere **Salva tutti** nel menu **File** .</span><span class="sxs-lookup"><span data-stu-id="83ad3-139">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="83ad3-140">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="83ad3-140">Next Steps</span></span>  
 <span data-ttu-id="83ad3-141">È stata aggiunta un'area dati tabella al report, all'area dati sono stati aggiunti campi ed è stato visualizzato in anteprima il report.</span><span class="sxs-lookup"><span data-stu-id="83ad3-141">You have successfully added a Table data region to your report, added fields to the data region, and previewed your report.</span></span> <span data-ttu-id="83ad3-142">Il passaggio successivo consiste nella formattazione delle intestazioni di colonna e dei valori di data e valuta.</span><span class="sxs-lookup"><span data-stu-id="83ad3-142">Next, you will format column headers and date and currency values.</span></span> <span data-ttu-id="83ad3-143">Vedere [Lezione 5: Formattazione di un report &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="83ad3-143">See [Lesson 5: Formatting a Report &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ad3-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83ad3-144">See Also</span></span>  
 <span data-ttu-id="83ad3-145">[Tabelle &#40;Generatore report e SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="83ad3-145">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="83ad3-146">Raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="83ad3-146">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](report-data/dataset-fields-collection-report-builder-and-ssrs.md)  
  
  
