---
title: 'Attività 4 (facoltativo): combinazione, corrispondenza e pubblicazione di un nuovo set di dati | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13a13f03-b307-4555-8e33-6d98c459d994
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ddcec19fa8b957bf77b6ea5269b4d033779bdf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624450"
---
# <a name="task-4-optional-combining-matching-and-publishing-new-set-of-data"></a><span data-ttu-id="eca79-102">Attività 4 (facoltativa): Combinazione, corrispondenza e pubblicazione di un nuovo set di dati</span><span class="sxs-lookup"><span data-stu-id="eca79-102">Task 4 (Optional): Combining, Matching, and Publishing New Set of Data</span></span>
  <span data-ttu-id="eca79-103">Con il tempo, sarà necessario aggiungere ulteriori dati al repository MDS.</span><span class="sxs-lookup"><span data-stu-id="eca79-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="eca79-104">Prima di aggiungere i dati, può essere utile confrontare i nuovi dati con quelli già gestiti in MDS, per assicurarsi che non si stiano aggiungendo dati duplicati o non accurati.</span><span class="sxs-lookup"><span data-stu-id="eca79-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure that you are not adding duplicate or inaccurate data.</span></span> <span data-ttu-id="eca79-105">Nel componente aggiuntivo Master Data Services per Excel è possibile combinare i dati di due fogli di lavoro e confrontarli per identificare e rimuovere i duplicati prima di pubblicare i dati in MDS.</span><span class="sxs-lookup"><span data-stu-id="eca79-105">In the Master Data Services Add-in for Excel, you can combine data from two worksheets and the compare the data to identify and remove duplicates before publishing the data to MDS.</span></span> <span data-ttu-id="eca79-106">Per identificare le corrispondenze nei dati viene utilizzata la funzionalità di corrispondenza di DQS dalla relativa caratteristica del componente aggiuntivo MDS per Excel.</span><span class="sxs-lookup"><span data-stu-id="eca79-106">The matching feature of MDS Excel Add-in uses the DQS matching functionality to identify matches in the data.</span></span> <span data-ttu-id="eca79-107">In questa attività verranno combinati i dati di due fogli di lavoro in uno e, successivamente, verrà eseguita l'attività di individuazione delle corrispondenze per identificare e rimuovere i duplicati prima della pubblicazione in MDS.</span><span class="sxs-lookup"><span data-stu-id="eca79-107">In this task, you will combine data from a two worksheets into one and then perform the matching activity to identify and remove duplicates before publishing to MDS.</span></span> <span data-ttu-id="eca79-108">Per ulteriori informazioni, vedere la pagina relativa alla [corrispondenza Data Quality nell'componente aggiuntivo MDS per Excel](https://msdn.microsoft.com/library/hh548681.aspx) e [combinare i dati](https://msdn.microsoft.com/library/hh548680.aspx) .</span><span class="sxs-lookup"><span data-stu-id="eca79-108">See [Data Quality Matching in the MDS Add-in for Excel](https://msdn.microsoft.com/library/hh548681.aspx) and [Combine Data](https://msdn.microsoft.com/library/hh548680.aspx) topics for more details.</span></span>  
  
1.  <span data-ttu-id="eca79-109">Avviare una nuova istanza di **Excel**.</span><span class="sxs-lookup"><span data-stu-id="eca79-109">Launch new instance of **Excel**.</span></span> <span data-ttu-id="eca79-110">Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **Excel**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eca79-110">Click **Start**, point to **Run**, type **Excel**, and click **OK**.</span></span>  
  
2.  <span data-ttu-id="eca79-111">Passare alla scheda **dati master** facendo clic su **dati master** sulla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="eca79-111">Switch to the **Master Data** tab by clicking **Master Data** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="eca79-112">Fare clic su **Connetti** sulla barra multifunzione nel gruppo **Connetti e carica** per connettersi al **Server MDS**.</span><span class="sxs-lookup"><span data-stu-id="eca79-112">Click **Connect** on the ribbon in the **Connect and Load** group to connect to the **MDS server**.</span></span> <span data-ttu-id="eca79-113">Questa connessione è stata configurata in precedenza nel corso della lezione.</span><span class="sxs-lookup"><span data-stu-id="eca79-113">You have configured this connection earlier in this lesson.</span></span>  
  
     <span data-ttu-id="eca79-114">![Excel - Pulsante Esplora dati master nella scheda Dati master](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Pulsante Esplora dati master nella scheda Dati master")</span><span class="sxs-lookup"><span data-stu-id="eca79-114">![Excel - Show Explorer Button on Master Data Tabl](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Show Explorer Button on Master Data Tabl")</span></span>  
  
4.  <span data-ttu-id="eca79-115">Il riquadro **Esplora dati master** verrà visualizzato a destra.</span><span class="sxs-lookup"><span data-stu-id="eca79-115">You should see the **Master Data Explorer** pane to the right.</span></span> <span data-ttu-id="eca79-116">Se il Esplora dati master non viene visualizzato, fare clic sul pulsante **Mostra Esplora** sulla barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="eca79-116">If you do not see the Master Data Explorer, click **Show Explorer** button on the ribbon.</span></span>  
  
5.  <span data-ttu-id="eca79-117">Nella finestra **Esplora dati master** selezionare **Suppliers** nell'elenco a discesa del **modello**.</span><span class="sxs-lookup"><span data-stu-id="eca79-117">In the **Master Data Explorer** Window, select **Suppliers** in the drop-down list for the **Model**.</span></span> <span data-ttu-id="eca79-118">Si noterà che il modello ha un'entità: **Supplier**.</span><span class="sxs-lookup"><span data-stu-id="eca79-118">You should see that the model has one entity: **Supplier**.</span></span>  
  
     <span data-ttu-id="eca79-119">![Excel - Finestra Esplora dati master](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Finestra Esplora dati master")</span><span class="sxs-lookup"><span data-stu-id="eca79-119">![Excel - Master Data Explorer Window](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Master Data Explorer Window")</span></span>  
  
6.  <span data-ttu-id="eca79-120">Fare doppio clic su **Supplier** nell'elenco di entità per caricare i membri dell'entità nel foglio di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="eca79-120">Double-click **Supplier** in the entity list to load the entity members into the Excel worksheet.</span></span>  
  
7.  <span data-ttu-id="eca79-121">Fare clic su **Sheet2** nella parte inferiore per passare alla scheda **Sheet2** . Se **Sheet2**non è visualizzato, aggiungere un nuovo foglio di foglio.</span><span class="sxs-lookup"><span data-stu-id="eca79-121">Click **Sheet2** at the bottom to switch to the **Sheet2** tab. If you do not see **Sheet2**, add a new worksheet.</span></span>  
  
8.  <span data-ttu-id="eca79-122">Aprire **Suppliers.xls** file (il file di input originale incluso nei file dell'esercitazione) e copiare tutte le righe (tre) dal foglio di **CombineAndCleanse** a **Sheet2**.</span><span class="sxs-lookup"><span data-stu-id="eca79-122">Open **Suppliers.xls** file (the original input file that is included in the tutorial files) and copy all (three) rows from the **CombineAndCleanse** worksheet to **Sheet2**.</span></span>  
  
9. <span data-ttu-id="eca79-123">Tornare alla scheda **Supplier** nel **libro 1-Microsoft Excel** (non l'elenco dei **fornitori puliti e corrispondenti** Excel) connesso a **MDS**.</span><span class="sxs-lookup"><span data-stu-id="eca79-123">Switch back to the **Supplier** sheet in the **Book 1 - Microsoft Excel** (not the **Cleansed and Matched Supplier List** Excel) that is connected to **MDS**.</span></span>  
  
10. <span data-ttu-id="eca79-124">Fare clic su **dati master** sulla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="eca79-124">Click **Master Data** on the menu bar.</span></span>  
  
11. <span data-ttu-id="eca79-125">Fare clic su **combina dati** sulla barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="eca79-125">Click **Combine Data** on the ribbon.</span></span> <span data-ttu-id="eca79-126">Viene visualizzata la finestra di dialogo **combina dati** .</span><span class="sxs-lookup"><span data-stu-id="eca79-126">You will see the **Combine Data** dialog box.</span></span>  
  
12. <span data-ttu-id="eca79-127">Nella finestra di dialogo **combina dati** fare clic sul pulsante accanto alla casella **di testo intervallo da combinare con dati MDS** , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="eca79-127">In the **Combine Data** dialog box, click the button next to **Range to combine with MDS data** text box as shown in the following image.</span></span>  
  
     <span data-ttu-id="eca79-128">![Excel - Finestra di dialogo Combina dati](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Finestra di dialogo Combina dati")</span><span class="sxs-lookup"><span data-stu-id="eca79-128">![Excel - Combine Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Combine Data Dialog Box")</span></span>  
  
13. <span data-ttu-id="eca79-129">A questo punto viene visualizzata la finestra di dialogo ridotta.</span><span class="sxs-lookup"><span data-stu-id="eca79-129">You should see the shrunken dialog box now.</span></span> <span data-ttu-id="eca79-130">A questo punto, fare clic su **Sheet2** per passare alla scheda **Sheet2** con i nuovi dati fornitore con 4 righe (inclusa una riga di intestazione).</span><span class="sxs-lookup"><span data-stu-id="eca79-130">Now, click **Sheet2** to switch to the **Sheet2** tab that has the new supplier data with 4 rows (including one header row).</span></span>  
  
14. <span data-ttu-id="eca79-131">In **Sheet2**, selezionare **tutte le righe che includono la riga di intestazione** (anche se sembrano essere già selezionate).</span><span class="sxs-lookup"><span data-stu-id="eca79-131">In the **Sheet2**, select **all rows including the header row** (even if they seem to be already selected).</span></span> <span data-ttu-id="eca79-132">Si noterà che l' **intervallo da combinare con i dati MDS** viene aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="eca79-132">You should see the **Range to combine with MDS data** is automatically updated.</span></span>  
  
     <span data-ttu-id="eca79-133">![Excel - Finestra di dialogo Combina dati - Ridotta](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Finestra di dialogo Combina dati - Ridotta")</span><span class="sxs-lookup"><span data-stu-id="eca79-133">![Excel - Combine Data Dialog Box - Minimized](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Combine Data Dialog Box - Minimized")</span></span>  
  
15. <span data-ttu-id="eca79-134">Tornare alla scheda **Suppliers** senza chiudere la finestra di dialogo **combina dati** .</span><span class="sxs-lookup"><span data-stu-id="eca79-134">Switch back to the **Suppliers** tab without closing the **Combine Data** dialog box.</span></span>  
  
16. <span data-ttu-id="eca79-135">Fare clic sul **pulsante** accanto alla **casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="eca79-135">Click the **button** next to the **text box**.</span></span> <span data-ttu-id="eca79-136">A questo punto viene visualizzata la finestra di dialogo espansa.</span><span class="sxs-lookup"><span data-stu-id="eca79-136">You should see that the dialog box is expanded now.</span></span> <span data-ttu-id="eca79-137">Si noterà che tutti i mapping tra le colonne dell' **entità** MDS **Supplier** e le colonne di **Excel** vengono popolati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="eca79-137">You should see all the mappings between columns of the **Supplier** MDS **entity** to **Excel** columns are automatically populated.</span></span>  
  
     <span data-ttu-id="eca79-138">![Excel - Finestra di dialogo Combina dati con dati inclusi](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Finestra di dialogo Combina dati con dati inclusi")</span><span class="sxs-lookup"><span data-stu-id="eca79-138">![Excel - Combine Data Dialog Box Filled with Data](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Combine Data Dialog Box Filled with Data")</span></span>  
  
17. <span data-ttu-id="eca79-139">Verificare che sia stato eseguito il mapping della colonna entità **codice** alla colonna **SupplierID** del foglio di codice e che sia stato eseguito il **mapping della colonna** di **entità Cap alla** colonna CAP del foglio di file.</span><span class="sxs-lookup"><span data-stu-id="eca79-139">Ensure that **Code** entity column is mapped to the **SupplierID** column in the worksheet and **Zip Code** entity column is mapped to the **Zip Code** column in the worksheet.</span></span>  
  
18. <span data-ttu-id="eca79-140">Nella finestra di dialogo **combina dati** fare clic su **combina**.</span><span class="sxs-lookup"><span data-stu-id="eca79-140">On the **Combine Data** dialog box, click **Combine**.</span></span>  
  
19. <span data-ttu-id="eca79-141">Verificare che nella parte inferiore del foglio di calcolo sono state aggiunte tre righe di dati e che sono codificate tramite colori.</span><span class="sxs-lookup"><span data-stu-id="eca79-141">Confirm that three data rows are added to the bottom of the worksheet and they should be color coded.</span></span>  
  
     <span data-ttu-id="eca79-142">![Excel - Nuovi elementi dopo la combinazione](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - Nuovi elementi dopo la combinazione")</span><span class="sxs-lookup"><span data-stu-id="eca79-142">![Excel - New Elements after Combining](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - New Elements after Combining")</span></span>  
  
20. <span data-ttu-id="eca79-143">Fare clic su **dati matematici** sulla barra multifunzione per identificare i duplicati.</span><span class="sxs-lookup"><span data-stu-id="eca79-143">Click **Math Data** on the ribbon to identify duplicates.</span></span> <span data-ttu-id="eca79-144">Per questa caratteristica viene utilizzata la funzionalità di corrispondenza di DQS.</span><span class="sxs-lookup"><span data-stu-id="eca79-144">This feature uses the matching functionality of DQS.</span></span>  
  
21. <span data-ttu-id="eca79-145">Nella finestra di dialogo **corrispondenza dati** selezionare **Suppliers** per la **Knowledge Base DQS**.</span><span class="sxs-lookup"><span data-stu-id="eca79-145">In the **Match Data** dialog box, select **Suppliers** for **DQS Knowledge Base**.</span></span>  
  
     <span data-ttu-id="eca79-146">![Excel - Finestra di dialogo Abbina dati](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Finestra di dialogo Abbina dati")</span><span class="sxs-lookup"><span data-stu-id="eca79-146">![Excel - Match Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Match Data Dialog Box")</span></span>  
  
22. <span data-ttu-id="eca79-147">Eseguire il mapping delle colonne del foglio di lavoro ai domini come illustrato nella tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="eca79-147">Map worksheet columns to domains as shown in the following table.</span></span>  
  
    |<span data-ttu-id="eca79-148">Colonna del foglio di lavoro</span><span class="sxs-lookup"><span data-stu-id="eca79-148">Worksheet Column</span></span>|<span data-ttu-id="eca79-149">Dominio</span><span class="sxs-lookup"><span data-stu-id="eca79-149">Domain</span></span>|  
    |----------------------|------------|  
    |<span data-ttu-id="eca79-150">Code (è stato caricato Supplier ID come Code per l'entità Supplier in MDS)</span><span class="sxs-lookup"><span data-stu-id="eca79-150">Code (you uploaded Supplier ID as the Code for the Supplier entity in MDS)</span></span>|<span data-ttu-id="eca79-151">Supplier ID</span><span class="sxs-lookup"><span data-stu-id="eca79-151">Supplier ID</span></span>|  
    |<span data-ttu-id="eca79-152">Name (è stato caricato Supplier Name come Name dell'entità Supplier in MDS)</span><span class="sxs-lookup"><span data-stu-id="eca79-152">Name (you uploaded Supplier Name as the Name for the Supplier entity to MDS)</span></span>|<span data-ttu-id="eca79-153">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="eca79-153">Supplier Name</span></span>|  
    |<span data-ttu-id="eca79-154">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="eca79-154">ContactEmailAddress</span></span>|<span data-ttu-id="eca79-155">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="eca79-155">ContactEmail</span></span>|  
  
23. <span data-ttu-id="eca79-156">Selezionare **prerequisito** per il mapping delle colonne di **codice** .</span><span class="sxs-lookup"><span data-stu-id="eca79-156">Select **Prerequisite** for the **Code** column mapping.</span></span>  
  
24. <span data-ttu-id="eca79-157">Immettere il **70%** come **peso** per **il nome del fornitore** e il **30%** come **peso** per il **messaggio di posta elettronica di contatto** , come illustrato nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="eca79-157">Enter **70%** as the **weight** for **Supplier Name** and **30%** as the **weight** for **Contact Email** as shown in the image.</span></span>  
  
25. <span data-ttu-id="eca79-158">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eca79-158">Click **OK**.</span></span>  
  
26. <span data-ttu-id="eca79-159">Il processo di corrispondenza dovrebbe identificare un duplicato per il fornitore con **codice: S1**.</span><span class="sxs-lookup"><span data-stu-id="eca79-159">The matching process should identify one duplicate for the supplier with **Code: S1**.</span></span>  
  
     <span data-ttu-id="eca79-160">![Excel - Risultati corrispondenti](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Risultati corrispondenti")</span><span class="sxs-lookup"><span data-stu-id="eca79-160">![Excel - Matching Results](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Matching Results")</span></span>  
  
27. <span data-ttu-id="eca79-161">Selezionare la **riga duplicata (arancione)**, fare clic con il pulsante destro del mouse e scegliere **Elimina** per eliminare la riga.</span><span class="sxs-lookup"><span data-stu-id="eca79-161">Select the **duplicate row (orange)**, right-click, and click **Delete** to delete the row.</span></span>  
  
28. <span data-ttu-id="eca79-162">Eliminare la colonna **CLUSTER_ID** perché non è più necessaria.</span><span class="sxs-lookup"><span data-stu-id="eca79-162">Delete the **CLUSTER_ID** column since you don't need it anymore.</span></span>  
  
29. <span data-ttu-id="eca79-163">Fare clic su **pubblica** per pubblicare gli altri due nuovi record con i **codici S66** e **S57** in MDS.</span><span class="sxs-lookup"><span data-stu-id="eca79-163">Click **Publish** to publish the other two new records with **Codes S66** and **S57** to MDS.</span></span>  
  
30. <span data-ttu-id="eca79-164">Nella finestra di dialogo **pubblica e annota** aggiungere un' **annotazione**e fare clic su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="eca79-164">In the **Publish and Annotate** dialog box, add an **annotation**, and click **Publish**.</span></span>  
  
31. <span data-ttu-id="eca79-165">Passa all' **applicazione Web gestione dati master**.</span><span class="sxs-lookup"><span data-stu-id="eca79-165">Switch to the **Master Data Manager Web application**.</span></span>  
  
32. <span data-ttu-id="eca79-166">Nella home page verificare che **Suppliers** sia selezionato per il **modello**, quindi fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="eca79-166">On the home page, ensure that **Suppliers** is selected for the **Model**, and click **Explorer**.</span></span> <span data-ttu-id="eca79-167">Se **Esplora risorse** è già aperto, aggiornare il browser Internet.</span><span class="sxs-lookup"><span data-stu-id="eca79-167">If you already have the **Explorer** open, refresh the internet browser.</span></span>  
  
33. <span data-ttu-id="eca79-168">**Ordinare** l'elenco in base al **codice** e cercare i record con **S57** e **S66** come codici.</span><span class="sxs-lookup"><span data-stu-id="eca79-168">**Sort** the list by **Code** and look for records with **S57** and **S66** as codes.</span></span> <span data-ttu-id="eca79-169">È anche possibile usare il pulsante **filtro** sulla barra degli strumenti per cercare un record specifico nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="eca79-169">You can also use the **Filter** button on the toolbar to search for a specific record in the list.</span></span>  
  
34. <span data-ttu-id="eca79-170">A questo punto, chiudere la finestra **di Book1-Microsoft Excel** senza salvare il file.</span><span class="sxs-lookup"><span data-stu-id="eca79-170">Now, close **Book1 - Microsoft Excel** window without saving the file.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="eca79-171">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="eca79-171">Next Step</span></span>  
 [<span data-ttu-id="eca79-172">Attività 5: Creazione di un attributo basato su dominio di Excel</span><span class="sxs-lookup"><span data-stu-id="eca79-172">Task 5: Creating a Domain-Based Attribute from Excel</span></span>](../../2014/tutorials/task-5-creating-a-domain-based-attribute-from-excel.md)  
  
  
