---
title: 'Lezione 6: Aggiunta di gruppi e totali (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e3d61228-2aa4-42cc-955e-602dbf3406a7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b98798005a984edf00aff469d4c1b09aa2e34d98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637082"
---
# <a name="lesson-6-adding-grouping-and-totals-reporting-services"></a><span data-ttu-id="06eb2-102">Lezione 6: Aggiunta di gruppi e totali (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="06eb2-102">Lesson 6: Adding Grouping and Totals (Reporting Services)</span></span>
  <span data-ttu-id="06eb2-103">È possibile aggiungere gruppi e totali al report per organizzare e riepilogare i dati.</span><span class="sxs-lookup"><span data-stu-id="06eb2-103">Add grouping and totals to your report to organize and summarize your data.</span></span>  
  
 <span data-ttu-id="06eb2-104">Per informazioni sull'aggiunta dei totali in esecuzione ai report, vedere: [aggiunta di totali ai report di Reporting Services (SSRS)](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span><span class="sxs-lookup"><span data-stu-id="06eb2-104">For information about adding running totals to reports, see: [Adding totals to Reporting Services (SSRS) reports](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span></span>  
  
 <span data-ttu-id="06eb2-105">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="06eb2-105">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="06eb2-106">Per raggruppare i dati in un report</span><span class="sxs-lookup"><span data-stu-id="06eb2-106">To group data in a report</span></span>](#bkmk_groupdata)  
  
-   [<span data-ttu-id="06eb2-107">Per aggiungere totali a un report</span><span class="sxs-lookup"><span data-stu-id="06eb2-107">To add totals to a report</span></span>](#bkmk_addtotals)  
  
-   [<span data-ttu-id="06eb2-108">Per aggiungere un totale giornaliero a un report</span><span class="sxs-lookup"><span data-stu-id="06eb2-108">To add a daily total to a report</span></span>](#bkmk_adddailytotal)  
  
-   [<span data-ttu-id="06eb2-109">Per aggiungere un totale complessivo a un report</span><span class="sxs-lookup"><span data-stu-id="06eb2-109">To add a grand total to a report</span></span>](#bkmk_addgrandtotal)  
  
-   [<span data-ttu-id="06eb2-110">Per pubblicare il report nel server di report (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="06eb2-110">To Publish the Report to the Report Server (Optional)</span></span>](#bkmk_publishreport)  
  
##  <a name="to-group-data-in-a-report"></a><a name="bkmk_groupdata"></a><span data-ttu-id="06eb2-111">Per raggruppare i dati in un report</span><span class="sxs-lookup"><span data-stu-id="06eb2-111">To group data in a report</span></span>  
  
1.  <span data-ttu-id="06eb2-112">Fare clic sulla scheda **Progettazione** .</span><span class="sxs-lookup"><span data-stu-id="06eb2-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="06eb2-113">Se il riquadro **gruppi di righe** non è visualizzato, fare clic con il pulsante destro del mouse sull'area di progettazione e scegliere **Visualizza** , quindi fare clic su **raggruppamento**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-113">If you do not see the **Row Groups** pane , right-click the design surface and click **view** and then click **Grouping**.</span></span>  
  
3.  <span data-ttu-id="06eb2-114">Dal riquadro **Dati report** trascinare il campo `Date` nel riquadro **Gruppi di righe**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-114">From the **Report Data** pane, drag the `Date` field to the **Row Groups** pane.</span></span> <span data-ttu-id="06eb2-115">Posizionarlo al di sopra della riga **(Dettagli)**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-115">Place it above the row called **(Details)**.</span></span>  
  
     <span data-ttu-id="06eb2-116">L'handle di riga contiene ora una parentesi quadra per mostrare un gruppo.</span><span class="sxs-lookup"><span data-stu-id="06eb2-116">Note that the row handle now has a bracket in it, to show a group.</span></span> <span data-ttu-id="06eb2-117">La tabella presenta ora due colonne Date, una su ogni lato di una linea verticale tratteggiata.</span><span class="sxs-lookup"><span data-stu-id="06eb2-117">The table now also has two Date columns -- one on either side of a vertical dotted line.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablegroups1design.gif "rs_BasicTableGroups1Design")  
  
4.  <span data-ttu-id="06eb2-118">Dal riquadro **Dati report** trascinare il campo `Order` nel riquadro **Gruppi di righe**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-118">From the **Report Data** pane, drag the `Order` field to the **Row Groups** pane.</span></span> <span data-ttu-id="06eb2-119">Posizionarlo al di sotto di Date e al di sopra di **(Dettagli)**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-119">Place it below Date and above **(Details)**.</span></span>  
  
     <span data-ttu-id="06eb2-120">L'handle di riga contiene ora due parentesi quadre per mostrare due gruppi.</span><span class="sxs-lookup"><span data-stu-id="06eb2-120">Note that the row handle now has two brackets in it, to show two groups.</span></span> <span data-ttu-id="06eb2-121">La tabella include ora `Order` anche due colonne.</span><span class="sxs-lookup"><span data-stu-id="06eb2-121">The table now has two `Order` columns, too.</span></span>  
  
5.  <span data-ttu-id="06eb2-122">Eliminare le colonne Date e Order originali a **destra** della linea doppia.</span><span class="sxs-lookup"><span data-stu-id="06eb2-122">Delete the original Date and Order columns to the **right** of the double line.</span></span> <span data-ttu-id="06eb2-123">Verranno rimossi i singoli valori dei record in modo da visualizzare solo il valore del gruppo.</span><span class="sxs-lookup"><span data-stu-id="06eb2-123">This removes this individual record values so that only the group value is displayed.</span></span> <span data-ttu-id="06eb2-124">Selezionare gli handle delle due colonne, fare clic con il pulsante destro del mouse e scegliere **Elimina colonne**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-124">Select the column handles for the two columns, right-click and click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="06eb2-125">![Selezione colonne da eliminare](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Selezione colonne da eliminare")</span><span class="sxs-lookup"><span data-stu-id="06eb2-125">![Select columns to delete](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Select columns to delete")</span></span>  
  
     <span data-ttu-id="06eb2-126">È possibile formattare nuovamente le intestazioni di colonna e la data.</span><span class="sxs-lookup"><span data-stu-id="06eb2-126">You can format the column headers and date again.</span></span>  
  
6.  <span data-ttu-id="06eb2-127">Per visualizzare un'anteprima del report, passare alla scheda **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="06eb2-127">Switch to the **Preview** tab to preview the report.</span></span> <span data-ttu-id="06eb2-128">Il risultato dovrebbe essere simile a quanto illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="06eb2-128">It should look similar to the following illustration:</span></span>  
  
     <span data-ttu-id="06eb2-129">![Tabella raggruppata per data e quindi per numero di ordine](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Tabella raggruppata per data e quindi per numero di ordine")</span><span class="sxs-lookup"><span data-stu-id="06eb2-129">![Table grouped by date and then order](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Table grouped by date and then order")</span></span>  
  
##  <a name="to-add-totals-to-a-report"></a><a name="bkmk_addtotals"></a><span data-ttu-id="06eb2-130">Per aggiungere totali a un report</span><span class="sxs-lookup"><span data-stu-id="06eb2-130">To add totals to a report</span></span>  
  
1.  <span data-ttu-id="06eb2-131">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="06eb2-131">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="06eb2-132">Fare clic con il pulsante destro del mouse sulla cella dell'area dati contenente il campo `[LineTotal]`e fare clic su **Aggiungi totale**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-132">Right-click the data region cell that contains the field `[LineTotal]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="06eb2-133">Verrà aggiunta una riga con una somma degli importi di tutti gli ordini.</span><span class="sxs-lookup"><span data-stu-id="06eb2-133">This adds a row with a sum of the dollar amount for each order.</span></span>  
  
3.  <span data-ttu-id="06eb2-134">Fare clic con il pulsante destro del mouse sulla cella contenente il campo `[Qty]`e fare clic su **Aggiungi totale**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-134">Right-click the cell that contains the field `[Qty]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="06eb2-135">Verrà aggiunta una somma delle quantità di tutti gli ordini alla riga dei totali.</span><span class="sxs-lookup"><span data-stu-id="06eb2-135">This adds a sum of the quantity for each order to the totals row.</span></span>  
  
4.  <span data-ttu-id="06eb2-136">Nella cella vuota a sinistra di `Sum[Qty]`digitare l'etichetta "**Order Total"**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-136">In the empty cell to the left of `Sum[Qty]`, type the label "**Order Total"**.</span></span>  
  
5.  <span data-ttu-id="06eb2-137">È possibile aggiungere un colore di sfondo alla riga dei totali.</span><span class="sxs-lookup"><span data-stu-id="06eb2-137">You can add a background color to the totals row.</span></span> <span data-ttu-id="06eb2-138">Selezionare le due celle della somma e la cella dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="06eb2-138">Select the two sum cells and the label cell.</span></span>  
  
6.  <span data-ttu-id="06eb2-139">Nel menu **Formato** selezionare **Colore di sfondo**, fare clic su **Grigio chiaro**e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-139">On the **Format** menu, click **Background Color**, click **Light Gray**, and click **OK**.</span></span>  
  
     <span data-ttu-id="06eb2-140">![Visualizzazione Progettazione: tabella di base con totale degli ordini](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Visualizzazione Progettazione: tabella di base con totale degli ordini")</span><span class="sxs-lookup"><span data-stu-id="06eb2-140">![Design view: Basic table with order total](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Design view: Basic table with order total")</span></span>  
  
##  <a name="to-add-a-daily-total-to-a-report"></a><a name="bkmk_adddailytotal"></a><span data-ttu-id="06eb2-141">Per aggiungere un totale giornaliero a un report</span><span class="sxs-lookup"><span data-stu-id="06eb2-141">To add a daily total to a report</span></span>  
  
1.  <span data-ttu-id="06eb2-142">Fare clic con il pulsante destro del mouse sulla cella Order , scegliere **Aggiungi totale**e quindi fare clic su **Dopo**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-142">Right-click the Order cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="06eb2-143">Viene aggiunta una nuova riga contenente le somme della quantità e del dollaro per ogni giorno e l'etichetta "**Total**" nella colonna Order.</span><span class="sxs-lookup"><span data-stu-id="06eb2-143">This adds a new row containing sums of the quantity and dollar amount for each day, and the label "**Total**" in the Order column.</span></span>  
  
2.  <span data-ttu-id="06eb2-144">Digitare la parola **Daily** prima della parola **Total** nella stessa cella in modo da definire la frase **Daily Total**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-144">Type the word **Daily** before the word **Total** in the same cell, so it reads **Daily Total**.</span></span>  
  
3.  <span data-ttu-id="06eb2-145">Selezionare la cella **Daily Total** , le due celle **Sum** e la cella vuota compresa tra di esse.</span><span class="sxs-lookup"><span data-stu-id="06eb2-145">Select the **Daily Total** cell, the two **Sum** cells and the empty cell between them.</span></span>  
  
4.  <span data-ttu-id="06eb2-146">Nel menu **Formato** selezionare **Colore di sfondo**, fare clic su **Arancione**e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-146">On the **Format** menu, click **Background Color**, click **Orange**, and click **OK**.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablesumdaytotaldesign.gif "rs_BasicTableSumDayTotalDesign")  
  
##  <a name="to-add-a-grand-total-to-a-report"></a><a name="bkmk_addgrandtotal"></a><span data-ttu-id="06eb2-147">Per aggiungere un totale complessivo a un report</span><span class="sxs-lookup"><span data-stu-id="06eb2-147">To add a grand total to a report</span></span>  
  
1.  <span data-ttu-id="06eb2-148">Fare clic con il pulsante destro del mouse sulla cella Date, scegliere **Aggiungi totale**e quindi fare clic su **Dopo**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-148">Right-click the Date cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="06eb2-149">Viene aggiunta una nuova riga contenente le somme della quantità e del dollaro per l'intero report e l'etichetta **Total** nella `Date` colonna.</span><span class="sxs-lookup"><span data-stu-id="06eb2-149">This adds a new row containing sums of the quantity and dollar amount for the entire report, and the **Total** label in the `Date` column.</span></span>  
  
2.  <span data-ttu-id="06eb2-150">Digitare la parola **Grand** prima della parola **Total** nella stessa cella in modo da definire la frase **Grand Total**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-150">Type the word **Grand** before the word **Total** in the same cell, so it reads **Grand Total**.</span></span>  
  
3.  <span data-ttu-id="06eb2-151">Selezionare la cella **Grand Total** , le due celle **Sum** e le celle vuote comprese tra di esse.</span><span class="sxs-lookup"><span data-stu-id="06eb2-151">Select the **Grand Total** cell, the two **Sum** cells and the empty cells between them.</span></span>  
  
4.  <span data-ttu-id="06eb2-152">Nel menu **Formato** selezionare **Colore di sfondo**, fare clic su **Azzurro**e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-152">On the **Format** menu, click **Background Color**, click **Light Blue**, and click **OK**.</span></span>  
  
     <span data-ttu-id="06eb2-153">![Visualizzazione Progettazione: totale complessivo in una tabella di base](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Visualizzazione Progettazione: totale complessivo in una tabella di base")</span><span class="sxs-lookup"><span data-stu-id="06eb2-153">![Design view: Grand total in basic table](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Design view: Grand total in basic table")</span></span>  
  
5.  <span data-ttu-id="06eb2-154">Fare clic su Anteprima.</span><span class="sxs-lookup"><span data-stu-id="06eb2-154">Click Preview.</span></span>  
  
     <span data-ttu-id="06eb2-155">L'ultima pagina dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="06eb2-155">The last page should look something like this:</span></span>  
  
     <span data-ttu-id="06eb2-156">![Anteprima: tabella di base con totale complessivo](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Anteprima: tabella di base con totale complessivo")</span><span class="sxs-lookup"><span data-stu-id="06eb2-156">![Preview: Basic table with grand total](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Preview: Basic table with grand total")</span></span>  
  
##  <a name="to-publish-the-report-to-the-report-server-optional"></a><a name="bkmk_publishreport"></a><span data-ttu-id="06eb2-157">Per pubblicare il report nel server di report (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="06eb2-157">To Publish the Report to the Report Server (Optional)</span></span>  
  
1.  <span data-ttu-id="06eb2-158">Un passaggio facoltativo consiste nel pubblicare il report completato nel server di report in modalità nativa in modo che sia possibile visualizzare il report da Gestione report.</span><span class="sxs-lookup"><span data-stu-id="06eb2-158">An optional step is to publish the completed report to the native mode report server so you can view the report from Report Manager.</span></span>  
  
2.  <span data-ttu-id="06eb2-159">Sulla barra degli strumenti fare clic su **Progetto** , quindi scegliere **Proprietà tutorial**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-159">On the toolbar click **Project** and then click **tutorial Properties...**</span></span>  
  
3.  <span data-ttu-id="06eb2-160">In **TargetServerURL** Digitare il nome del server di report, ad esempio **http:// \<servername> /ReportServer**</span><span class="sxs-lookup"><span data-stu-id="06eb2-160">In the **TargetServerURL** type the name of the name of your report server, for example **http://\<servername>/reportserver**</span></span>  
  
4.  <span data-ttu-id="06eb2-161">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-161">Click **OK**</span></span>  
  
5.  <span data-ttu-id="06eb2-162">Sulla barra degli strumenti fare clic su **Compila** , quindi scegliere **Distribuisci Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-162">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>  
  
     <span data-ttu-id="06eb2-163">Se viene visualizzato un messaggio simile al seguente nella finestra di output, la distribuzione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="06eb2-163">If you see a message similar to the following in the output window, it indicates a successful deployment.</span></span>  
  
    > <span data-ttu-id="06eb2-164">------ Compilazione avviata - Progetto: tutorial, Configurazione: Debug ------'Sales Orders.rdl' verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="06eb2-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span></span> <span data-ttu-id="06eb2-165">L'elemento è aggiornato. Compilazione completata--0 errori, 0 avvisi------distribuzione avviata: progetto: esercitazione, configurazione: debug------distribuzione in http:// \<server name> /reportserverDeploying report '/tutorial/Sales Orders '. Distribuzione completata--0 errori, 0 avvisi = = = = = = = = = = = compilazione: 1 riuscite o aggiornate, 0 non riuscite, 0 ignorate = = = = = = = = = = = = = = = = = = = = = = = = = = = =</span><span class="sxs-lookup"><span data-stu-id="06eb2-165">Item is up to date.Build complete -- 0 errors, 0 warnings------ Deploy started: Project: tutorial, Configuration: Debug ------Deploying to http://\<server name>/reportserverDeploying report '/tutorial/Sales Orders'.Deploy complete -- 0 errors, 0 warnings========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==================== Deploy: 1 succeeded, 0 failed, 0 skipped ==========</span></span>  
  
     <span data-ttu-id="06eb2-166">Se viene visualizzato un messaggio di errore simile al seguente, verificare di disporre delle autorizzazione per il server di report e di aver avviato [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="06eb2-166">If you see an error message similar to the following, verify you have permissions on the report server and you have started [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] with administrator privileges.</span></span>  
  
    > <span data-ttu-id="06eb2-167">"Le autorizzazioni concesse all'utente ' XXXXXXXX \\<il nome utente \> ' non sono sufficienti per eseguire questa operazione"</span><span class="sxs-lookup"><span data-stu-id="06eb2-167">"The permissions granted to user 'XXXXXXXX\\<your user name\>' are insufficient for performing this operation"</span></span>  
  
6.  <span data-ttu-id="06eb2-168">Avviare Gestione report con privilegi di amministratore, ad esempio, fare clic con il pulsante destro del mouse sull'icona di Internet Explorer e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-168">Start Report Manager with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>  
  
     <span data-ttu-id="06eb2-169">Selezionare l'URL Gestione report, ad esempio `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="06eb2-169">Browse to the Report Manager URL, for example: `http://<server name>/reports`.</span></span>  
  
7.  <span data-ttu-id="06eb2-170">Selezionare la cartella contenente il report e fare clic sul nome del report `Sales Orders` per visualizzare il report visualizzabile nel browser.</span><span class="sxs-lookup"><span data-stu-id="06eb2-170">Browse to the folder that contains the report and click the name of the report `Sales Orders` to view the rendered report in the browser.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="06eb2-171">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="06eb2-171">Next Steps</span></span>  
 <span data-ttu-id="06eb2-172">Questo passaggio conclude l'esercitazione relativa alla creazione di un report tabella semplice.</span><span class="sxs-lookup"><span data-stu-id="06eb2-172">You have successfully completed the Creating a Basic Table Report tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06eb2-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06eb2-173">See Also</span></span>  
 [<span data-ttu-id="06eb2-174">Filtro, raggruppamento e ordinamento di dati &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="06eb2-174">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
