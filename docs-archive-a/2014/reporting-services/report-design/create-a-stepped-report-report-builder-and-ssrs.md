---
title: Creare un report con rientri (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5933c4f0-c713-4ecb-b521-ff46c9c63fff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d845993ac1462cef2d39638101e5c7b9fc314b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627128"
---
# <a name="create-a-stepped-report-report-builder-and-ssrs"></a><span data-ttu-id="fbd05-102">Creazione di un report con rientri (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="fbd05-102">Create a Stepped Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fbd05-103">In un report con rientri le righe di dettaglio oppure i gruppi figlio vengono visualizzati rientrati sotto un gruppo padre della stessa colonna, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fbd05-103">A stepped report shows detail rows or child groups indented under a parent group in the same column, as shown in the example below:</span></span>  
  
 <span data-ttu-id="fbd05-104">![Rendering di un report con rientri](../media/steppedreportrendered.gif "Rendering di un report con rientri")</span><span class="sxs-lookup"><span data-stu-id="fbd05-104">![Rendered stepped report](../media/steppedreportrendered.gif "Rendered stepped report")</span></span>  
  
 <span data-ttu-id="fbd05-105">Nei tradizionali report tabella il gruppo padre viene inserito in una colonna adiacente del report.</span><span class="sxs-lookup"><span data-stu-id="fbd05-105">Traditional table reports place the parent group in an adjacent column on the report.</span></span> <span data-ttu-id="fbd05-106">La nuova area dati Tablix consente di aggiungere un gruppo e righe di dettaglio o gruppi figlio alla stessa colonna.</span><span class="sxs-lookup"><span data-stu-id="fbd05-106">The new tablix data region enables you to add a group and detail rows or child groups to the same column.</span></span> <span data-ttu-id="fbd05-107">Per differenziare le righe di gruppo dalle righe di dettaglio o da quelle di gruppi figlio, è possibile applicare una formattazione, ad esempio il colore del carattere, o applicare il rientro alle righe di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="fbd05-107">To differentiate the group rows from the detail or child group rows, you can apply formatting such as font color, or you can indent the detail rows.</span></span>  
  
 <span data-ttu-id="fbd05-108">Le procedure in questo argomento illustrano come creare manualmente un report avanzato, ma è anche possibile utilizzare la procedura guidata Nuova tabella/Matrice.</span><span class="sxs-lookup"><span data-stu-id="fbd05-108">The procedures in this topic show you how to manually create a stepped report, but you can also use the New Table and Matrix Wizard.</span></span> <span data-ttu-id="fbd05-109">Fornisce il layout per report con rientri, semplificandone la creazione.</span><span class="sxs-lookup"><span data-stu-id="fbd05-109">It provides the layout for stepped reports, making it easy to create them.</span></span> <span data-ttu-id="fbd05-110">Dopo avere completato la procedura guidata, il report può essere ulteriormente migliorato.</span><span class="sxs-lookup"><span data-stu-id="fbd05-110">After you complete the wizard, you can further enhance the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbd05-111">La procedura guidata è disponibile unicamente in Generatore report.</span><span class="sxs-lookup"><span data-stu-id="fbd05-111">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-stepped-report"></a><span data-ttu-id="fbd05-112">Per creare un report con rientri</span><span class="sxs-lookup"><span data-stu-id="fbd05-112">To create a stepped report</span></span>  
  
1.  <span data-ttu-id="fbd05-113">Creare un report tabella.</span><span class="sxs-lookup"><span data-stu-id="fbd05-113">Create a table report.</span></span> <span data-ttu-id="fbd05-114">Inserire ad esempio un'area dati Tablix e aggiungere campi alla riga di dati.</span><span class="sxs-lookup"><span data-stu-id="fbd05-114">For example, insert a tablix data region and add fields to the Data row.</span></span>  
  
2.  <span data-ttu-id="fbd05-115">Aggiungere un gruppo padre al report.</span><span class="sxs-lookup"><span data-stu-id="fbd05-115">Add a parent group to your report.</span></span>  
  
    1.  <span data-ttu-id="fbd05-116">Fare clic in un punto qualsiasi della tabella per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="fbd05-116">Click anywhere in the table to select it.</span></span> <span data-ttu-id="fbd05-117">Nel riquadro di raggruppamento viene visualizzato il gruppo Dettagli presente nel riquadro Gruppi di righe.</span><span class="sxs-lookup"><span data-stu-id="fbd05-117">The Grouping pane displays the Details group in the Row Groups pane.</span></span>  
  
    2.  <span data-ttu-id="fbd05-118">Nel riquadro di raggruppamento fare clic con il pulsante destro del mouse sul gruppo Dettagli, scegliere **Aggiungi gruppo**e quindi fare clic su **Gruppo padre**.</span><span class="sxs-lookup"><span data-stu-id="fbd05-118">In the Grouping Pane, right-click the Details Group, point to **Add Group**, and then click **Parent Group**.</span></span>  
  
    3.  <span data-ttu-id="fbd05-119">Nella finestra di dialogo **Gruppo Tablix** specificare un nome per il gruppo e digitare o selezionare un'espressione di raggruppamento nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="fbd05-119">In the **Tablix Group** dialog box, provide a name for the group and type or select a group expression from the drop-down list.</span></span> <span data-ttu-id="fbd05-120">Nell'elenco a discesa vengono visualizzate le espressioni di campo semplici disponibili nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="fbd05-120">The drop-down list displays the simple field expressions that are available in the Report Data pane.</span></span> <span data-ttu-id="fbd05-121">Ad esempio [PostalCode] è un'espressione di campo semplice per il campo PostalCode in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="fbd05-121">For example, [PostalCode] is a simple field expression for the PostalCode field in a dataset.</span></span>  
  
    4.  <span data-ttu-id="fbd05-122">Selezionare **Aggiungi intestazione gruppo**.</span><span class="sxs-lookup"><span data-stu-id="fbd05-122">Select **Add group header**.</span></span> <span data-ttu-id="fbd05-123">Questa opzione consente di aggiungere una riga statica sopra il gruppo per l'etichetta e i totali relativi al gruppo stesso.</span><span class="sxs-lookup"><span data-stu-id="fbd05-123">This option adds a static row above the group for the group label and group totals.</span></span> <span data-ttu-id="fbd05-124">Allo stesso modo è possibile selezionare **Aggiungi piè di pagina gruppo** per aggiungere una riga statica sotto il gruppo.</span><span class="sxs-lookup"><span data-stu-id="fbd05-124">Likewise, you can select **Add group footer** to add a static row below the group.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="fbd05-125">A questo punto è disponibile un report tabella di base.</span><span class="sxs-lookup"><span data-stu-id="fbd05-125">You now have a basic tabular report.</span></span> <span data-ttu-id="fbd05-126">Quando si esegue il rendering di tale report, verranno visualizzate una colonna con il valore dell'istanza del gruppo e una o più colonne con i dati di dettaglio raggruppati.</span><span class="sxs-lookup"><span data-stu-id="fbd05-126">When it is rendered, you see one column with the group instance value, and one or more columns with grouped detail data.</span></span> <span data-ttu-id="fbd05-127">Nella figura seguente viene illustrato il possibile aspetto dell'area dati nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="fbd05-127">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="fbd05-128">![Area dati della tabella con gruppo](../media/tabledataregionwithgroup.gif "Area dati della tabella con gruppo")</span><span class="sxs-lookup"><span data-stu-id="fbd05-128">![Table data region with group](../media/tabledataregionwithgroup.gif "Table data region with group")</span></span>  
  
     <span data-ttu-id="fbd05-129">Nelle figura seguente viene illustrato il possibile aspetto dell'area dati di cui è stato eseguito il rendering quando viene visualizzato il report.</span><span class="sxs-lookup"><span data-stu-id="fbd05-129">The following figure shows how the rendered data region might look when you view the report.</span></span>  
  
     <span data-ttu-id="fbd05-130">![Rendering di un report raggruppato](../media/tablereportrendered.gif "Rendering di un report raggruppato")</span><span class="sxs-lookup"><span data-stu-id="fbd05-130">![Rendered grouped report](../media/tablereportrendered.gif "Rendered grouped report")</span></span>  
  
3.  <span data-ttu-id="fbd05-131">Per un report con rientri, non è necessario utilizzare la prima colonna in cui viene visualizzata l'istanza del gruppo,</span><span class="sxs-lookup"><span data-stu-id="fbd05-131">For a stepped report, you do not need the first column that shows the group instance.</span></span> <span data-ttu-id="fbd05-132">ma è necessario copiare il valore della cella dell'intestazione di gruppo, eliminare la colonna di gruppo e incollare il valore nella prima casella di testo della riga di intestazione di gruppo.</span><span class="sxs-lookup"><span data-stu-id="fbd05-132">Instead, copy the value in the group header cell, delete the group column, and paste in the first text box in the group header row.</span></span> <span data-ttu-id="fbd05-133">Per rimuovere la colonna di gruppo, fare clic con il pulsante destro del mouse sulla colonna o la cella di gruppo e quindi scegliere **Elimina colonne**.</span><span class="sxs-lookup"><span data-stu-id="fbd05-133">To remove the group column, right-click the group column or cell, and click **Delete Columns**.</span></span> <span data-ttu-id="fbd05-134">Nella figura seguente viene illustrato il possibile aspetto dell'area dati nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="fbd05-134">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="fbd05-135">![Area dati con riga di intestazione di gruppo](../media/tabledataregiongroupheader.gif "Area dati con riga di intestazione di gruppo")</span><span class="sxs-lookup"><span data-stu-id="fbd05-135">![Data region with group header row](../media/tabledataregiongroupheader.gif "Data region with group header row")</span></span>  
  
4.  <span data-ttu-id="fbd05-136">Per applicare il rientro alle righe di dettaglio sotto la riga di intestazione di gruppo nella stessa colonna, modificare il riempimento della cella dei dati di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="fbd05-136">To indent the detail rows under the group header row in the same column, change the padding of the detail data cell.</span></span>  
  
    1.  <span data-ttu-id="fbd05-137">Selezionare la cella con il campo di dettaglio per cui si desidera impostare il rientro.</span><span class="sxs-lookup"><span data-stu-id="fbd05-137">Select the cell with the detail field that you want to indent.</span></span> <span data-ttu-id="fbd05-138">Le proprietà relative alla casella di testo per tale cella verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="fbd05-138">The text box properties for that cell appear in the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="fbd05-139">In **Allineamento**nel riquadro Proprietà espandere le proprietà relative a **Riempimento**.</span><span class="sxs-lookup"><span data-stu-id="fbd05-139">In the Properties pane, under **Alignment**, expand the properties for **Padding**.</span></span>  
  
    3.  <span data-ttu-id="fbd05-140">Per **Left**Digitare un nuovo valore di riempimento, ad esempio `.5in` .</span><span class="sxs-lookup"><span data-stu-id="fbd05-140">For **Left**, type a new padding value, such as `.5in`.</span></span> <span data-ttu-id="fbd05-141">Il riempimento consente di applicare il rientro al testo presente nella cella in base al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="fbd05-141">Padding indents the text in the cell by the value you specify.</span></span> <span data-ttu-id="fbd05-142">Il valore predefinito è 2 punti.</span><span class="sxs-lookup"><span data-stu-id="fbd05-142">The default padding is 2 points.</span></span> <span data-ttu-id="fbd05-143">Il valore valido per le proprietà relative a Riempimento è zero (0) oppure un numero positivo, seguito da un identificatore di dimensione.</span><span class="sxs-lookup"><span data-stu-id="fbd05-143">Valid values for the Padding properties are zero or a positive number, followed by a size designator.</span></span>  
  
         <span data-ttu-id="fbd05-144">Di seguito vengono riportati gli identificatori di dimensione:</span><span class="sxs-lookup"><span data-stu-id="fbd05-144">Size designators are:</span></span>  
  
        |||  
        |-|-|  
        |`in`|<span data-ttu-id="fbd05-145">Pollici (1 pollice = 2,54 centimetri)</span><span class="sxs-lookup"><span data-stu-id="fbd05-145">Inches (1 inch = 2.54 centimeters)</span></span>|  
        |`cm`|<span data-ttu-id="fbd05-146">Centimetri</span><span class="sxs-lookup"><span data-stu-id="fbd05-146">Centimeters</span></span>|  
        |`mm`|<span data-ttu-id="fbd05-147">Millimetri</span><span class="sxs-lookup"><span data-stu-id="fbd05-147">Millimeters</span></span>|  
        |`pt`|<span data-ttu-id="fbd05-148">Punti (1 punto = 1/72 pollice)</span><span class="sxs-lookup"><span data-stu-id="fbd05-148">Points (1 point = 1/72 inch)</span></span>|  
        |`pc`|<span data-ttu-id="fbd05-149">Pica (1 pica = 12 punti)</span><span class="sxs-lookup"><span data-stu-id="fbd05-149">Picas (1 pica = 12 points)</span></span>|  
  
     <span data-ttu-id="fbd05-150">L'aspetto dell'area dati sarà simile a quello riportato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fbd05-150">Your data region will look similar to the following example.</span></span>  
  
     <span data-ttu-id="fbd05-151">![Area dati per un report con rientri](../media/steppedreportdataregion.gif "Area dati per un report con rientri")</span><span class="sxs-lookup"><span data-stu-id="fbd05-151">![Data region for stepped report](../media/steppedreportdataregion.gif "Data region for stepped report")</span></span>  
  
     <span data-ttu-id="fbd05-152">**Area dati per layout di report con rientri**</span><span class="sxs-lookup"><span data-stu-id="fbd05-152">**Data Region for Stepped Report Layout**</span></span>  
  
     <span data-ttu-id="fbd05-153">Nella scheda **Home** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="fbd05-153">On the **Home** tab Click **Run**.</span></span> <span data-ttu-id="fbd05-154">Nel report verrà visualizzato il gruppo con i livelli rientrati per i valori del gruppo figlio.</span><span class="sxs-lookup"><span data-stu-id="fbd05-154">The report displays the group with indented levels for the child group values.</span></span>  
  
### <a name="to-create-a-stepped-report-with-multiple-groups"></a><span data-ttu-id="fbd05-155">Per creare un report con rientri con più gruppi</span><span class="sxs-lookup"><span data-stu-id="fbd05-155">To create a stepped report with multiple groups</span></span>  
  
1.  <span data-ttu-id="fbd05-156">Creare un report come descritto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="fbd05-156">Create a report as described in the previous procedure.</span></span>  
  
2.  <span data-ttu-id="fbd05-157">Aggiungere altri gruppi al report.</span><span class="sxs-lookup"><span data-stu-id="fbd05-157">Add additional groups to your report.</span></span>  
  
    1.  <span data-ttu-id="fbd05-158">Nel riquadro Gruppi di righe fare clic con il pulsante destro del mouse sul gruppo, scegliere **Aggiungi gruppo**e quindi il tipo di gruppo da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="fbd05-158">In the Row Groups pane, right-click the group, click **Add Group**, and then choose the type of group you want to add.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="fbd05-159">È possibile aggiungere gruppi a un'area dati in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="fbd05-159">There are several ways to add groups to a data region.</span></span> <span data-ttu-id="fbd05-160">Per ulteriori informazioni, vedere [aggiungere o eliminare un gruppo in un'area dati &#40;Generatore report e SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fbd05-160">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
    2.  <span data-ttu-id="fbd05-161">Nella finestra di dialogo **Gruppo Tablix** digitare un nome.</span><span class="sxs-lookup"><span data-stu-id="fbd05-161">In the **Tablix Group** dialog box, type a name.</span></span>  
  
    3.  <span data-ttu-id="fbd05-162">In **Espressione di raggruppamento**digitare un'espressione o selezionare un campo del set di dati in base al quale eseguire il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="fbd05-162">In **Group expression**, type an expression or select a dataset field to group on.</span></span> <span data-ttu-id="fbd05-163">Per creare un'espressione, fare clic sul pulsante Espressione (**fx**) per aprire la finestra di dialogo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="fbd05-163">To create an expression, click the expression (**fx**) button to open the **Expression** dialog box.</span></span>  
  
    4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
3.  <span data-ttu-id="fbd05-164">Modificare il riempimento per la cella in cui vengono visualizzati i dati del gruppo.</span><span class="sxs-lookup"><span data-stu-id="fbd05-164">Change the padding for the cell that displays the group data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd05-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbd05-165">See Also</span></span>  
 <span data-ttu-id="fbd05-166">[Intestazioni di pagina e piè di pagina &#40;Generatore report e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fbd05-166">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fbd05-167">[Formattazione degli elementi del report &#40;Generatore report e SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fbd05-167">[Formatting Report Items &#40;Report Builder and SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fbd05-168">[Area dati Tablix &#40;Generatore report e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fbd05-168">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fbd05-169">[Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fbd05-169">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fbd05-170">[Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fbd05-170">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fbd05-171">[Elenca &#40;Generatore report e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fbd05-171">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="fbd05-172">Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fbd05-172">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
