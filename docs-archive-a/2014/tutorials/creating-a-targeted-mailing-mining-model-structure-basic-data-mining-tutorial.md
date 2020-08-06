---
title: Creazione di una struttura del modello di data mining Targeted Mailing (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9c67f29-0c47-4a5a-862b-db0f5213c2c9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 6a27f818b29120e40248044091c78205dad945bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719127"
---
# <a name="creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial"></a><span data-ttu-id="7bd54-102">Creazione di una struttura del modello di data mining Targeted Mailing (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="7bd54-102">Creating a Targeted Mailing Mining Model Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="7bd54-103">Il primo passaggio nella creazione di uno scenario relativo al mailing diretto consiste nell'utilizzo di Creazione guidata modello di data mining in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per creare una nuova struttura e un nuovo modello di data mining basato su un albero delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="7bd54-103">The first step in creating a targeted mailing scenario is to use the Data Mining Wizard in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new mining structure and decision tree mining model.</span></span>  
  
 <span data-ttu-id="7bd54-104">In questa attività verrà configurata una nuova struttura di data mining e verrà aggiunto un modello di data mining iniziale basato sull' [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Decision Trees.</span><span class="sxs-lookup"><span data-stu-id="7bd54-104">In this task you will set up a new mining structure, and add an initial mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="7bd54-105">Per creare la struttura, verranno innanzitutto selezionate le tabelle e le viste, quindi si identificheranno le colonne da utilizzare rispettivamente per il training e per il testing.</span><span class="sxs-lookup"><span data-stu-id="7bd54-105">To create the structure, you will first select tables and views and then identify which columns will be used for training and which for testing.</span></span>  
  
### <a name="to-create-a-mining-structure-for-the-targeted-mailing-scenario"></a><span data-ttu-id="7bd54-106">Per creare una struttura di data mining per lo scenario relativo al mailing diretto</span><span class="sxs-lookup"><span data-stu-id="7bd54-106">To create a mining structure for the targeted mailing scenario</span></span>  
  
1.  <span data-ttu-id="7bd54-107">In Esplora soluzioni fare clic con il pulsante destro del mouse su **strutture di data** mining e scegliere **nuova struttura di data** mining per avviare Creazione guidata modello di data mining</span><span class="sxs-lookup"><span data-stu-id="7bd54-107">In Solution Explorer, right-click **Mining Structures** and select **New Mining Structure** to start the Data Mining Wizard.</span></span>  
  
2.  <span data-ttu-id="7bd54-108">Nella pagina iniziale **Creazione guidata modello di data mining** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7bd54-108">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="7bd54-109">Nella pagina **Selezione metodo di definizione** verificare che sia selezionato **da database relazionale o data warehouse esistente** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7bd54-109">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="7bd54-110">Nella pagina **Crea la struttura di data mining** in **cui data mining tecnica si desidera utilizzare?** selezionare **Microsoft Decision Trees**.</span><span class="sxs-lookup"><span data-stu-id="7bd54-110">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Decision Trees**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7bd54-111">Se viene visualizzato un avviso relativo al mancato rilevamento di algoritmi di data mining, è possibile che le proprietà del progetto non siano state configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="7bd54-111">If you get a warning that no data mining algorithms can be found, the project properties might not be configured correctly.</span></span> <span data-ttu-id="7bd54-112">Questo avviso viene visualizzato quando il progetto tenta di recuperare un elenco di algoritmi di data mining dal server di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e quest'ultimo non viene rilevato.</span><span class="sxs-lookup"><span data-stu-id="7bd54-112">This warning occurs when the project attempts to retrieve a list of data mining algorithms from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and cannot find the server.</span></span> <span data-ttu-id="7bd54-113">Per impostazione predefinita, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] utilizzerà **localhost** come server.</span><span class="sxs-lookup"><span data-stu-id="7bd54-113">By default, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] will use **localhost** as the server.</span></span> <span data-ttu-id="7bd54-114">Se si utilizza un'istanza diversa o un'istanza denominata, è necessario modificare le proprietà del progetto.</span><span class="sxs-lookup"><span data-stu-id="7bd54-114">If you are using a different instance, or a named instance, you must change the project properties.</span></span> <span data-ttu-id="7bd54-115">Per ulteriori informazioni, vedere la pagina relativa alla [creazione di un progetto Analysis Services &#40;esercitazione di base sul Data Mining&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="7bd54-115">For more information, see [Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="7bd54-116">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7bd54-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7bd54-117">Nella pagina **Selezione vista origine dati** , nel riquadro **viste origine dati disponibili** , selezionare **Targeted Mailing**.</span><span class="sxs-lookup"><span data-stu-id="7bd54-117">On the **Select Data Source View** page, in the **Available data source views** pane, select **Targeted Mailing**.</span></span> <span data-ttu-id="7bd54-118">È possibile fare clic su **Sfoglia** per visualizzare le tabelle nella vista origine dati e quindi fare clic su **Chiudi** per tornare alla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="7bd54-118">You can click **Browse** to view the tables in the data source view and then click **Close** to return to the wizard.</span></span>  
  
7.  <span data-ttu-id="7bd54-119">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7bd54-119">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="7bd54-120">Nella pagina **impostazione tipi di tabelle** selezionare la casella di controllo nella colonna **case** per vTargetMail per utilizzarla come tabella del case, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7bd54-120">On the **Specify Table Types** page, select the check box in the **Case** column for vTargetMail to use it as the case table, and then click **Next**.</span></span> <span data-ttu-id="7bd54-121">La tabella ProspectiveBuyer verrà utilizzata in un secondo momento per il testing. Per il momento, ignorarla.</span><span class="sxs-lookup"><span data-stu-id="7bd54-121">You will use the ProspectiveBuyer table later for testing; ignore it for now.</span></span>  
  
9. <span data-ttu-id="7bd54-122">Nella pagina **impostazione dati di training** si identificherà almeno una colonna stimabile, una colonna chiave e una colonna di input per il modello.</span><span class="sxs-lookup"><span data-stu-id="7bd54-122">On the **Specify the Training Data** page, you will identify at least one predictable column, one key column, and one input column for your model.</span></span> <span data-ttu-id="7bd54-123">Selezionare la casella di controllo nella colonna **stimabile** nella riga **BikeBuyer** .</span><span class="sxs-lookup"><span data-stu-id="7bd54-123">Select the check box in the **Predictable** column in the **BikeBuyer** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7bd54-124">Si noti il messaggio di avviso nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="7bd54-124">Notice the warning at the bottom of the window.</span></span> <span data-ttu-id="7bd54-125">Non sarà possibile passare alla pagina successiva fino a quando non si seleziona almeno una colonna di **input** e una colonna **stimabile** .</span><span class="sxs-lookup"><span data-stu-id="7bd54-125">You will not be able to navigate to the next page until you select at least one **Input** and one **Predictable** column.</span></span>  
  
10. <span data-ttu-id="7bd54-126">Fare clic su **Suggerisci** per aprire la finestra di dialogo **Suggerisci colonne correlate** .</span><span class="sxs-lookup"><span data-stu-id="7bd54-126">Click **Suggest** to open the **Suggest Related Columns** dialog box.</span></span>  
  
     <span data-ttu-id="7bd54-127">Il pulsante **Suggerisci** è abilitato ogni volta che è stato selezionato almeno un attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="7bd54-127">The **Suggest** button is enabled whenever at least one predictable attribute has been selected.</span></span> <span data-ttu-id="7bd54-128">Nella finestra di dialogo **Suggerisci colonne correlate** sono elencate le colonne più strettamente correlate alla colonna stimabile e gli attributi vengono ordinati in base alla relativa correlazione con l'attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="7bd54-128">The **Suggest Related Columns** dialog box lists the columns that are most closely related to the predictable column, and orders the attributes by their correlation with the predictable attribute.</span></span> <span data-ttu-id="7bd54-129">Le colonne che presentano una correlazione significativa (confidenza maggiore del 95%) vengono selezionate automaticamente per essere incluse nel modello.</span><span class="sxs-lookup"><span data-stu-id="7bd54-129">Columns with a significant correlation (confidence greater than 95%) are automatically selected to be included in the model.</span></span>  
  
     <span data-ttu-id="7bd54-130">Esaminare i suggerimenti e quindi fare clic su **Annulla** per ignorare i suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="7bd54-130">Review the suggestions, and then click **Cancel** toignore the suggestions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7bd54-131">Se si fa clic su **OK**, tutti i suggerimenti elencati verranno contrassegnati come colonne di input nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="7bd54-131">If you click **OK**, all listed suggestions will be marked as input columns in the wizard.</span></span> <span data-ttu-id="7bd54-132">Se si accetta solo una parte dei suggerimenti, è necessario modificare i valori manualmente.</span><span class="sxs-lookup"><span data-stu-id="7bd54-132">If you agree with only some of the suggestions, you must change the values manually.</span></span>  
  
11. <span data-ttu-id="7bd54-133">Verificare che la casella di controllo nella colonna **chiave** sia selezionata nella riga **CustomerKey** .</span><span class="sxs-lookup"><span data-stu-id="7bd54-133">Verify that the check box in the **Key** column is selected in the **CustomerKey** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7bd54-134">Se la tabella di origine nella vista origine dati indica una chiave, Creazione guidata modello di data mining sceglierà automaticamente tale colonna come chiave per il modello.</span><span class="sxs-lookup"><span data-stu-id="7bd54-134">If the source table from the data source view indicates a key, the Data Mining Wizard automatically chooses that column as a key for the model.</span></span>  
  
12. <span data-ttu-id="7bd54-135">Selezionare le caselle di controllo nella colonna **input** nelle righe seguenti.</span><span class="sxs-lookup"><span data-stu-id="7bd54-135">Select the check boxes in the **Input** column in the following rows.</span></span> <span data-ttu-id="7bd54-136">È possibile selezionare più colonne evidenziando un intervallo di celle e premendo CTRL mentre si seleziona una casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="7bd54-136">You can check multiple columns by highlighting a range of cells and pressing CTRL while selecting a check box.</span></span>  
  
    -   <span data-ttu-id="7bd54-137">**Età**</span><span class="sxs-lookup"><span data-stu-id="7bd54-137">**Age**</span></span>  
  
    -   <span data-ttu-id="7bd54-138">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="7bd54-138">**CommuteDistance**</span></span>  
  
    -   <span data-ttu-id="7bd54-139">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="7bd54-139">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="7bd54-140">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="7bd54-140">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="7bd54-141">**Sesso**</span><span class="sxs-lookup"><span data-stu-id="7bd54-141">**Gender**</span></span>  
  
    -   <span data-ttu-id="7bd54-142">**GeographyKey**</span><span class="sxs-lookup"><span data-stu-id="7bd54-142">**GeographyKey**</span></span>  
  
    -   <span data-ttu-id="7bd54-143">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="7bd54-143">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="7bd54-144">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="7bd54-144">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="7bd54-145">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="7bd54-145">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="7bd54-146">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="7bd54-146">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="7bd54-147">**Area**</span><span class="sxs-lookup"><span data-stu-id="7bd54-147">**Region**</span></span>  
  
    -   <span data-ttu-id="7bd54-148">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="7bd54-148">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="7bd54-149">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="7bd54-149">**YearlyIncome**</span></span>  
  
13. <span data-ttu-id="7bd54-150">Nella colonna all'estrema sinistra della pagina selezionare le caselle di controllo relative alle righe seguenti.</span><span class="sxs-lookup"><span data-stu-id="7bd54-150">On the far left column of the page, select the check boxes in the following rows.</span></span>  
  
    -   <span data-ttu-id="7bd54-151">**AddressLine1**</span><span class="sxs-lookup"><span data-stu-id="7bd54-151">**AddressLine1**</span></span>  
  
    -   <span data-ttu-id="7bd54-152">**AddressLine2**</span><span class="sxs-lookup"><span data-stu-id="7bd54-152">**AddressLine2**</span></span>  
  
    -   <span data-ttu-id="7bd54-153">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="7bd54-153">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="7bd54-154">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="7bd54-154">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="7bd54-155">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="7bd54-155">**FirstName**</span></span>  
  
    -   <span data-ttu-id="7bd54-156">**LastName**</span><span class="sxs-lookup"><span data-stu-id="7bd54-156">**LastName**</span></span>  
  
     <span data-ttu-id="7bd54-157">Assicurarsi che queste righe contengano segni di spunta solo nella colonna sinistra.</span><span class="sxs-lookup"><span data-stu-id="7bd54-157">Ensure that these rows have checks only in the left column.</span></span> <span data-ttu-id="7bd54-158">Le colonne corrispondenti verranno aggiunte alla struttura ma non verranno incluse nel modello.</span><span class="sxs-lookup"><span data-stu-id="7bd54-158">These columns will be added to your structure but will not be included in the model.</span></span> <span data-ttu-id="7bd54-159">Tuttavia, dopo la compilazione del modello, saranno disponibili per il drill-through e il testing.</span><span class="sxs-lookup"><span data-stu-id="7bd54-159">However, after the model is built, they will be available for drillthrough and testing.</span></span> <span data-ttu-id="7bd54-160">Per ulteriori informazioni sul drill-through, vedere [query drill-through &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="7bd54-160">For more information about drillthrough, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
14. <span data-ttu-id="7bd54-161">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7bd54-161">Click **Next**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7bd54-162">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="7bd54-162">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7bd54-163">Impostazione del tipo di dati e del tipo di contenuto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7bd54-163">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="7bd54-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bd54-164">See Also</span></span>  
 <span data-ttu-id="7bd54-165">[Impostazione tipi di tabella &#40;creazione guidata modello di data mining&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="7bd54-165">[Specify Table Types &#40;Data Mining Wizard&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="7bd54-166">[Progettazione modelli di data mining](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7bd54-166">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="7bd54-167">Algoritmo Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="7bd54-167">Microsoft Decision Trees Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)  
  
  
