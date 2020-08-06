---
title: Modifica della dimensione Date | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4689d780-4bf6-4cf8-8fde-eb3f15dd668a
author: minewiskan
ms.author: owend
ms.openlocfilehash: b4978e9fe3acd93ddfdca707d2c2353bf171ba12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630141"
---
# <a name="modifying-the-date-dimension"></a><span data-ttu-id="db8a9-102">Modifica della dimensione Date</span><span class="sxs-lookup"><span data-stu-id="db8a9-102">Modifying the Date Dimension</span></span>
  <span data-ttu-id="db8a9-103">Nelle attività di questo argomento verrà creata una gerarchia definita dell'utente e verranno modificati i nomi dei membri visualizzati per gli attributi Date, Month, Calendar Quarter e Calendar Semester.</span><span class="sxs-lookup"><span data-stu-id="db8a9-103">In the tasks in this topic, you create a user-defined hierarchy and change the member names that are displayed for the Date, Month, Calendar Quarter, and Calendar Semester attributes.</span></span> <span data-ttu-id="db8a9-104">Verranno inoltre definite chiavi composte per gli attributi, verrà controllato l'ordinamento dei membri di dimensione e verranno definite relazioni tra attributi.</span><span class="sxs-lookup"><span data-stu-id="db8a9-104">You also define composite keys for attributes, control the sort order of dimension members, and define attribute relationships.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="db8a9-105">Aggiunta di un calcolo denominato</span><span class="sxs-lookup"><span data-stu-id="db8a9-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="db8a9-106">È possibile aggiungere un calcolo denominato, ovvero un'espressione SQL rappresentata da una colonna calcolata, a una tabella in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="db8a9-106">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="db8a9-107">L'espressione ha lo stesso aspetto e funziona allo stesso modo di una colonna di una tabella.</span><span class="sxs-lookup"><span data-stu-id="db8a9-107">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="db8a9-108">I calcoli denominati consentono di estendere lo schema relazionale delle tabelle esistenti in una vista origine dati senza modificare la tabella dell'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="db8a9-108">Named calculations enable you to extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="db8a9-109">Per altre informazioni, vedere [Definire calcoli denominati in una vista origine dati &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="db8a9-109">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="db8a9-110">Per aggiungere un calcolo denominato</span><span class="sxs-lookup"><span data-stu-id="db8a9-110">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="db8a9-111">Per aprire la vista origine dati **Adventure Works DW 2012** , selezionarla con doppio clic nella cartella **Viste origine dati** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="db8a9-111">To open the **Adventure Works DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="db8a9-112">Nella parte inferiore del riquadro **tabelle** fare clic con il pulsante destro del mouse su `Date` , quindi scegliere **nuovo calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-112">Near the bottom of the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="db8a9-113">Nella finestra di dialogo **Crea calcolo denominato** Digitare `SimpleDate` nella casella **nome colonna** , quindi digitare o copiare e incollare l' `DATENAME` istruzione seguente nella casella **espressione** :</span><span class="sxs-lookup"><span data-stu-id="db8a9-113">In the **Create Named Calculation** dialog box, type `SimpleDate` in the **Column name** box, and then type or copy and paste the following `DATENAME` statement in the **Expression** box:</span></span>  
  
    ```  
    DATENAME(mm, FullDateAlternateKey) + ' ' +  
    DATENAME(dd, FullDateAlternateKey) + ', ' +  
    DATENAME(yy, FullDateAlternateKey)  
    ```  
  
     <span data-ttu-id="db8a9-114">L'istruzione `DATENAME` consente di estrarre i valori per l'anno, il mese e il giorno dalla colonna FullDateAlternateKey.</span><span class="sxs-lookup"><span data-stu-id="db8a9-114">The `DATENAME` statement extracts the year, month, and day values from the FullDateAlternateKey column.</span></span> <span data-ttu-id="db8a9-115">Questa nuova colonna verrà utilizzata come nome visualizzato per l'attributo FullDateAlternateKey.</span><span class="sxs-lookup"><span data-stu-id="db8a9-115">You will use this new column as the displayed name for the FullDateAlternateKey attribute.</span></span>  
  
4.  <span data-ttu-id="db8a9-116">Fare clic su **OK**, quindi espandere `Date` nel riquadro **tabelle** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-116">Click **OK**, and then expand `Date` in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="db8a9-117">Il `SimpleDate` calcolo denominato viene visualizzato nell'elenco di colonne della tabella Date, con un'icona che indica che si tratta di un calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="db8a9-117">The `SimpleDate` named calculation appears in the list of columns in the Date table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="db8a9-118">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-118">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="db8a9-119">Nel riquadro **tabelle** fare clic con il pulsante destro del mouse su `Date` , quindi scegliere **Esplora dati**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-119">In the **Tables** pane, right-click `Date`, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="db8a9-120">Scorrere verso destra per rivedere l'ultima colonna nella vista **Explore Date Table** (Esplora tabella Date).</span><span class="sxs-lookup"><span data-stu-id="db8a9-120">Scroll to the right to review the last column in the **Explore Date Table** view.</span></span>  
  
     <span data-ttu-id="db8a9-121">Si noti che la `SimpleDate` colonna viene visualizzata nella vista origine dati, concatenando correttamente i dati di più colonne dall'origine dati sottostante, senza modificare l'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="db8a9-121">Notice that the `SimpleDate` column appears in the data source view, correctly concatenating data from several columns from the underlying data source, without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="db8a9-122">Chiudere la vista **Explore Date Table** (Esplora tabella Date).</span><span class="sxs-lookup"><span data-stu-id="db8a9-122">Close the **Explore Date Table** view.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="db8a9-123">Utilizzo del calcolo denominato per i nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="db8a9-123">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="db8a9-124">Dopo aver creato un calcolo denominato nella vista origine dati, è possibile utilizzarlo come proprietà di un attributo.</span><span class="sxs-lookup"><span data-stu-id="db8a9-124">After you create a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="db8a9-125">Per utilizzare il calcolo denominato per i nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="db8a9-125">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="db8a9-126">Aprire **Progettazione dimensioni** per la dimensione Date in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db8a9-126">Open **Dimension Designer** for the Date dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="db8a9-127">A tale scopo, fare doppio clic sulla `Date` dimensione nel nodo **dimensioni** del **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-127">To do this, double-click the `Date` dimension in the **Dimensions** node of **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="db8a9-128">Nel riquadro **Attributi** della scheda **Struttura dimensione** fare clic sull'attributo **Date Key** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-128">In the **Attributes** pane of the **Dimension Structure** tab, click the **Date Key** attribute.</span></span>  
  
3.  <span data-ttu-id="db8a9-129">Se la finestra Proprietà non è aperta, aprirla e fare clic sul pulsante **Nascondi automaticamente** sulla barra del titolo in modo che rimanga aperta.</span><span class="sxs-lookup"><span data-stu-id="db8a9-129">If the Properties window is not open, open the Properties window, and then click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="db8a9-130">Fare clic sul campo proprietà **NameColumn** nella parte inferiore della finestra, quindi fare clic sul pulsante con i puntini di sospensione (**...**) per aprire la finestra di dialogo **colonna nome** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-130">Click the **NameColumn** property field near the bottom of the window, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
5.  <span data-ttu-id="db8a9-131">Selezionare `SimpleDate` nella parte inferiore dell'elenco **colonna di origine** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-131">Select `SimpleDate` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="db8a9-132">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-132">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="db8a9-133">Creazione di una gerarchia</span><span class="sxs-lookup"><span data-stu-id="db8a9-133">Creating a Hierarchy</span></span>  
 <span data-ttu-id="db8a9-134">È possibile creare una nuova gerarchia trascinando un attributo dal riquadro **Attributi** al riquadro **Gerarchie** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-134">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="db8a9-135">Per creare una gerarchia</span><span class="sxs-lookup"><span data-stu-id="db8a9-135">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="db8a9-136">Nella scheda **Struttura dimensione** di Progettazione dimensioni per la `Date` dimensione trascinare l'attributo **Calendar Year** dal riquadro **attributi** al riquadro **gerarchie** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-136">In **Dimension Structure** tab of the Dimension Designer for the `Date` dimension, drag the **Calendar Year** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="db8a9-137">Trascinare l'attributo **Calendar Semester** dal riquadro **Attributi** alla cella **\<new level>** del riquadro **Gerarchie** , sotto il livello **Calendar Year** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-137">Drag the **Calendar Semester** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Year** level.</span></span>  
  
3.  <span data-ttu-id="db8a9-138">Trascinare l'attributo **Calendar Quarter** dal riquadro **Attributi** alla cella **\<new level>** del riquadro **Gerarchie** sotto il livello **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-138">Drag the **Calendar Quarter** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Semester** level.</span></span>  
  
4.  <span data-ttu-id="db8a9-139">Trascinare l'attributo **English Month Name** dal riquadro **Attributi** alla cella **\<new level>** del riquadro **Gerarchie** , sotto il livello **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-139">Drag the **English Month Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Quarter** level.</span></span>  
  
5.  <span data-ttu-id="db8a9-140">Trascinare l'attributo **Date Key** dal riquadro **Attributi** alla cella **\<new level>** del riquadro **Gerarchie** , sotto il livello **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-140">Drag the **Date Key** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **English Month Name** level.</span></span>  
  
6.  <span data-ttu-id="db8a9-141">Nel riquadro **gerarchie** fare clic con il pulsante destro del mouse sulla barra del titolo della gerarchia **gerarchia** , scegliere **Rinomina**, quindi digitare `Calendar Date` .</span><span class="sxs-lookup"><span data-stu-id="db8a9-141">In the **Hierarchies** pane, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Calendar Date`.</span></span>  
  
7.  <span data-ttu-id="db8a9-142">Utilizzando il menu di scelta rapida, nella `Calendar Date` gerarchia rinominare il livello **English Month Name** in `Calendar Month` , quindi rinominare il livello di **chiave date** su `Date` .</span><span class="sxs-lookup"><span data-stu-id="db8a9-142">By using the right-click context menu, in the `Calendar Date` hierarchy, rename the **English Month Name** level to `Calendar Month`, and then rename the **Date Key** level to `Date`.</span></span>  
  
8.  <span data-ttu-id="db8a9-143">Eliminare l'attributo **Full Date Alternate Key** dal riquadro **Attributi** , in quanto non verrà usato.</span><span class="sxs-lookup"><span data-stu-id="db8a9-143">Delete the **Full Date Alternate Key** attribute from the **Attributes** pane because you will not be using it.</span></span> <span data-ttu-id="db8a9-144">Fare clic su **OK** nella finestra di conferma **Elimina oggetti** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-144">Click **OK** in the **Delete Objects** confirmation window.</span></span>  
  
9. <span data-ttu-id="db8a9-145">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-145">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="db8a9-146">Definizione di relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="db8a9-146">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="db8a9-147">Se i dati sottostanti le supportano, è consigliabile definire relazioni tra gli attributi.</span><span class="sxs-lookup"><span data-stu-id="db8a9-147">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="db8a9-148">La definizione di relazioni tra attributi consente di velocizzare l'elaborazione di dimensioni, partizioni e query.</span><span class="sxs-lookup"><span data-stu-id="db8a9-148">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="db8a9-149">Per definire relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="db8a9-149">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="db8a9-150">In **Progettazione dimensioni** per la `Date` dimensione fare clic sulla scheda **relazioni tra attributi** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-150">In the **Dimension Designer** for the `Date` dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="db8a9-151">Nel diagramma fare clic con il pulsante destro del mouse sull'attributo **English Month Name** e scegliere **Nuova relazione tra attributi**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-151">In the diagram, right-click the **English Month Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="db8a9-152">Nella finestra di dialogo **Crea relazione tra attributi** l'opzione **Attributo di origine** è impostata su **English Month Name**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-152">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **English Month Name**.</span></span> <span data-ttu-id="db8a9-153">Impostare **Attributo correlato** su **Calendar Quarter**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-153">Set the **Related Attribute** to **Calendar Quarter**.</span></span>  
  
4.  <span data-ttu-id="db8a9-154">Nell'elenco **Tipo di relazione** impostare il tipo di relazione su **Rigida**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-154">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="db8a9-155">Il tipo di relazione è **Rigida** perché le relazioni tra i membri non cambieranno nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="db8a9-155">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span>  
  
5.  <span data-ttu-id="db8a9-156">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-156">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="db8a9-157">Nel diagramma fare clic con il pulsante destro del mouse sull'attributo **Calendar Quarter** e scegliere **Nuova relazione tra attributi**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-157">In the diagram, right-click the **Calendar Quarter** attribute, and then click **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="db8a9-158">Nella finestra di dialogo **Crea relazione tra attributi** l'opzione **Attributo di origine** è impostata su **Calendar Quarter**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-158">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Quarter**.</span></span> <span data-ttu-id="db8a9-159">Impostare **Attributo correlato** su **Calendar Semester**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-159">Set the **Related Attribute** to **Calendar Semester**.</span></span>  
  
8.  <span data-ttu-id="db8a9-160">Nell'elenco **Tipo di relazione** impostare il tipo di relazione su **Rigida**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-160">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="db8a9-161">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-161">Click **OK**.</span></span>  
  
10. <span data-ttu-id="db8a9-162">Nel diagramma fare clic con il pulsante destro del mouse sull'attributo **Calendar Semester** e scegliere **Nuova relazione tra attributi**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-162">In the diagram, right-click the **Calendar Semester** attribute, and then click **New Attribute Relationship**.</span></span>  
  
11. <span data-ttu-id="db8a9-163">Nella finestra di dialogo **Crea relazione tra attributi** l'opzione **Attributo di origine** è impostata su **Calendar Semester**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-163">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Semester**.</span></span> <span data-ttu-id="db8a9-164">Impostare **Attributo correlato** su **Calendar Year**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-164">Set the **Related Attribute** to **Calendar Year**.</span></span>  
  
12. <span data-ttu-id="db8a9-165">Nell'elenco **Tipo di relazione** impostare il tipo di relazione su **Rigida**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-165">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
13. <span data-ttu-id="db8a9-166">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-166">Click **OK**.</span></span>  
  
14. <span data-ttu-id="db8a9-167">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-167">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="providing-unique-dimension-member-names"></a><span data-ttu-id="db8a9-168">Impostazione di nomi univoci per i membri di dimensione</span><span class="sxs-lookup"><span data-stu-id="db8a9-168">Providing Unique Dimension Member Names</span></span>  
 <span data-ttu-id="db8a9-169">In questa attività si creeranno colonne con nomi descrittivi che verranno usate dagli attributi **EnglishMonthName**, **CalendarQuarter**e **CalendarSemester** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-169">In this task, you will create user-friendly name columns that will be used by the **EnglishMonthName**, **CalendarQuarter**, and **CalendarSemester** attributes.</span></span>  
  
#### <a name="to-provide-unique-dimension-member-names"></a><span data-ttu-id="db8a9-170">Per impostare nomi univoci per i membri di dimensione</span><span class="sxs-lookup"><span data-stu-id="db8a9-170">To provide unique dimension member names</span></span>  
  
1.  <span data-ttu-id="db8a9-171">Per passare alla vista origine dati \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* , fare doppio clic su di essa nella cartella **viste origine dati** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="db8a9-171">To switch to the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="db8a9-172">Nel riquadro **tabelle** fare clic con il pulsante destro del mouse su `Date` , quindi scegliere **nuovo calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-172">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="db8a9-173">Nella finestra di dialogo **Crea calcolo denominato** Digitare `MonthName` nella casella **nome colonna** , quindi digitare o copiare e incollare l'istruzione seguente nella casella **espressione** :</span><span class="sxs-lookup"><span data-stu-id="db8a9-173">In the **Create Named Calculation** dialog box, type `MonthName` in the **Column name** box, and then type or copy and paste the following statement in the **Expression** box:</span></span>  
  
    ```  
    EnglishMonthName+' '+ CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="db8a9-174">Questa istruzione consente di concatenare il mese e l'anno per ogni mese della tabella in una nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="db8a9-174">The statement concatenates the month and year for each month in the table into a new column.</span></span>  
  
4.  <span data-ttu-id="db8a9-175">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-175">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="db8a9-176">Nel riquadro **tabelle** fare clic con il pulsante destro del mouse su `Date` , quindi scegliere **nuovo calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-176">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="db8a9-177">Nella finestra di dialogo **Crea calcolo denominato** Digitare `CalendarQuarterDesc` nella casella **nome colonna** , quindi digitare o copiare e incollare lo script SQL seguente nella casella **espressione** :</span><span class="sxs-lookup"><span data-stu-id="db8a9-177">In the **Create Named Calculation** dialog box, type `CalendarQuarterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    'Q' + CONVERT(CHAR (1), CalendarQuarter) +' '+ 'CY ' +  
    CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="db8a9-178">Questo script SQL consente di concatenare il trimestre e l'anno di calendario per ogni trimestre della tabella in una nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="db8a9-178">This SQL script concatenates the calendar quarter and year for each quarter in the table into a new column.</span></span>  
  
7.  <span data-ttu-id="db8a9-179">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-179">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="db8a9-180">Nel riquadro **tabelle** fare clic con il pulsante destro del mouse su `Date` , quindi scegliere **nuovo calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-180">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
9. <span data-ttu-id="db8a9-181">Nella finestra di dialogo **Crea calcolo denominato** Digitare `CalendarSemesterDesc` nella casella **nome colonna** , quindi digitare o copiare e incollare lo script SQL seguente nella casella **espressione** :</span><span class="sxs-lookup"><span data-stu-id="db8a9-181">In the **Create Named Calculation** dialog box, type `CalendarSemesterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    CASE  
    WHEN CalendarSemester = 1 THEN 'H1' + ' ' + 'CY' + ' '   
           + CONVERT(CHAR(4), CalendarYear)  
    ELSE  
    'H2' + ' ' + 'CY' + ' ' + CONVERT(CHAR(4), CalendarYear)  
    END  
    ```  
  
     <span data-ttu-id="db8a9-182">Questo script SQL consente di concatenare il semestre e l'anno di calendario per ogni semestre della tabella in una nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="db8a9-182">This SQL script concatenates the calendar semester and year for each semester in the table into a new column.</span></span>  
  
10. <span data-ttu-id="db8a9-183">Scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="db8a9-183">Click **OK.**</span></span>  
  
11. <span data-ttu-id="db8a9-184">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns-and-setting-the-name-column"></a><span data-ttu-id="db8a9-185">Definizione della proprietà KeyColumns composta e impostazione di NameColumn</span><span class="sxs-lookup"><span data-stu-id="db8a9-185">Defining Composite KeyColumns and Setting the Name Column</span></span>  
 <span data-ttu-id="db8a9-186">La proprietà **KeyColumns** contiene la colonna o le colonne che rappresentano la chiave per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="db8a9-186">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="db8a9-187">In questa attività verrà definita la proprietà **KeyColumns**composta.</span><span class="sxs-lookup"><span data-stu-id="db8a9-187">In this task, you will define composite **KeyColumns**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-english-month-name-attribute"></a><span data-ttu-id="db8a9-188">Per definire la proprietà KeyColumns composta per l'attributo English Month Name</span><span class="sxs-lookup"><span data-stu-id="db8a9-188">To define composite KeyColumns for the English Month Name attribute</span></span>  
  
1.  <span data-ttu-id="db8a9-189">Aprire la scheda **Struttura dimensione** per la dimensione Date.</span><span class="sxs-lookup"><span data-stu-id="db8a9-189">Open the **Dimension Structure** tab for the Date dimension.</span></span>  
  
2.  <span data-ttu-id="db8a9-190">Nel riquadro **Attributi** fare clic sull'attributo **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-190">In the **Attributes** pane, click the **English Month Name** attribute.</span></span>  
  
3.  <span data-ttu-id="db8a9-191">Nella finestra **Proprietà** fare clic nel campo **KeyColumns** e sul pulsante sfoglia (**..**).</span><span class="sxs-lookup"><span data-stu-id="db8a9-191">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="db8a9-192">Nell'elenco **colonne disponibili** della finestra di dialogo **colonne chiave** selezionare la colonna **CalendarYear**, quindi fare clic sul **>** pulsante.</span><span class="sxs-lookup"><span data-stu-id="db8a9-192">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
5.  <span data-ttu-id="db8a9-193">Le colonne **EnglishMonthName** e **CalendarYear** sono ora visualizzate nell'elenco **Colonne chiave** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-193">The **EnglishMonthName** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
6.  <span data-ttu-id="db8a9-194">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-194">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="db8a9-195">Per impostare la proprietà **NameColumn** dell'attributo **EnglishMonthName** , fare clic nel campo **NameColumn** nella finestra Proprietà e fare clic sul pulsante sfoglia (**...**).</span><span class="sxs-lookup"><span data-stu-id="db8a9-195">To set the **NameColumn** property of the **EnglishMonthName** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
8.  <span data-ttu-id="db8a9-196">Nell'elenco **colonna di origine** della finestra di dialogo **colonna nome** selezionare `MonthName` , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-196">In the **Name Column** dialog box, in the **Source Column** list, select `MonthName`, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="db8a9-197">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-197">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-quarter-attribute"></a><span data-ttu-id="db8a9-198">Per definire la proprietà KeyColumns composta per l'attributo Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="db8a9-198">To define composite KeyColumns for the Calendar Quarter attribute</span></span>  
  
1.  <span data-ttu-id="db8a9-199">Nel riquadro **Attributi** fare clic sull'attributo **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-199">In the **Attributes** pane, click the **Calendar Quarter** attribute.</span></span>  
  
2.  <span data-ttu-id="db8a9-200">Nella finestra **Proprietà** fare clic nel campo **KeyColumns** e sul pulsante sfoglia (**..**).</span><span class="sxs-lookup"><span data-stu-id="db8a9-200">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="db8a9-201">Nell'elenco **colonne disponibili** della finestra di dialogo **colonne chiave** selezionare la colonna **CalendarYear**, quindi fare clic sul **>** pulsante.</span><span class="sxs-lookup"><span data-stu-id="db8a9-201">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="db8a9-202">Le colonne **CalendarQuarter** e **CalendarYear** sono ora visualizzate nell'elenco **Colonne chiave** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-202">The **CalendarQuarter** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="db8a9-203">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-203">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="db8a9-204">Per impostare la proprietà **NameColumn** dell'attributo **Calendar Quarter** , fare clic nel campo **NameColumn** nella finestra Proprietà e fare clic sul pulsante sfoglia (**...**).</span><span class="sxs-lookup"><span data-stu-id="db8a9-204">To set the **NameColumn** property of the **Calendar Quarter** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="db8a9-205">Nell'elenco **colonna di origine** della finestra di dialogo **colonna nome** selezionare `CalendarQuarterDesc` , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-205">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarQuarterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="db8a9-206">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-206">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-semester-attribute"></a><span data-ttu-id="db8a9-207">Per definire la proprietà KeyColumns composta per l'attributo Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="db8a9-207">To define composite KeyColumns for the Calendar Semester attribute</span></span>  
  
1.  <span data-ttu-id="db8a9-208">Nel riquadro **Attributi** fare clic sull'attributo **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-208">In the **Attributes** pane, click the **Calendar Semester** attribute.</span></span>  
  
2.  <span data-ttu-id="db8a9-209">Nella finestra **Proprietà** fare clic nel campo **KeyColumns** e sul pulsante sfoglia (**..**).</span><span class="sxs-lookup"><span data-stu-id="db8a9-209">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="db8a9-210">Nell'elenco **Colonne disponibili** della finestra di dialogo **Colonne chiave** selezionare la colonna **CalendarYear**e fare clic sul pulsante **>** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-210">In the **Key Columns** dialog box, in the **Available Columns** list, select the column, **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="db8a9-211">Le colonne **CalendarSemester** e **CalendarYear** sono ora visualizzate nell'elenco **Colonne chiave** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-211">The **CalendarSemester** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="db8a9-212">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-212">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="db8a9-213">Per impostare la proprietà **NameColumn** dell'attributo **Calendar Semester** , fare clic nel campo **NameColumn** nella finestra delle proprietà e fare clic sul pulsante sfoglia (**...**).</span><span class="sxs-lookup"><span data-stu-id="db8a9-213">To set the **NameColumn** property of the **Calendar Semester** attribute, click the **NameColumn** field in the property window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="db8a9-214">Nell'elenco **colonna di origine** della finestra di dialogo **colonna nome** selezionare `CalendarSemesterDesc` , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-214">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarSemesterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="db8a9-215">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-215">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-and-viewing-the-changes"></a><span data-ttu-id="db8a9-216">Distribuzione e visualizzazione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="db8a9-216">Deploying and Viewing the Changes</span></span>  
 <span data-ttu-id="db8a9-217">Dopo aver modificato gli attributi e le gerarchie, prima di visualizzare le modifiche è necessario distribuirle e rielaborare gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="db8a9-217">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-and-view-the-changes"></a><span data-ttu-id="db8a9-218">Per distribuire e visualizzare le modifiche</span><span class="sxs-lookup"><span data-stu-id="db8a9-218">To deploy and view the changes</span></span>  
  
1.  <span data-ttu-id="db8a9-219">Scegliere **Distribuisci Analysis Services Tutorial** dal menu [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]Compila **di**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-219">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="db8a9-220">Dopo aver ricevuto il messaggio **distribuzione completata** , fare clic sulla scheda **esplorazione** di **Progettazione dimensioni** per la `Date` dimensione e quindi fare clic sul pulsante Riconnetti sulla barra degli strumenti della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="db8a9-220">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the `Date` dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="db8a9-221">Selezionare **Calendar Quarter** nell'elenco **Gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-221">Select **Calendar Quarter** from the **Hierarchy** list.</span></span> <span data-ttu-id="db8a9-222">Controllare i membri nella gerarchia dell'attributo **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-222">Review the members in the **Calendar Quarter** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="db8a9-223">Si noti che i nomi dei membri della gerarchia dell'attributo **Calendar Quarter** sono più chiari e semplici da usare in quanto è stato creato un calcolo denominato da usare come nome.</span><span class="sxs-lookup"><span data-stu-id="db8a9-223">Notice that the names of the members of the **Calendar Quarter** attribute hierarchy are clearer and easier to use because you created a named calculation to use as the name.</span></span> <span data-ttu-id="db8a9-224">I membri sono ora disponibili nella gerarchia dell'attributo **Calendar Quarter** per ogni trimestre in ogni anno.</span><span class="sxs-lookup"><span data-stu-id="db8a9-224">Members now exist in the **Calendar Quarter** attribute hierarchy for each quarter in each year.</span></span> <span data-ttu-id="db8a9-225">I membri non sono disposti in ordine cronologico.</span><span class="sxs-lookup"><span data-stu-id="db8a9-225">The members are not sorted in chronological order.</span></span> <span data-ttu-id="db8a9-226">Sono invece ordinati per trimestre e quindi per anno.</span><span class="sxs-lookup"><span data-stu-id="db8a9-226">Instead they are sorted by quarter and then by year.</span></span> <span data-ttu-id="db8a9-227">Nell'attività successiva di questo argomento verrà modificato tale funzionamento in modo da ordinare i membri di questa gerarchia dell'attributo per anno e quindi per trimestre.</span><span class="sxs-lookup"><span data-stu-id="db8a9-227">In the next task in this topic, you will modify this behavior to sort the members of this attribute hierarchy by year and then by quarter.</span></span>  
  
4.  <span data-ttu-id="db8a9-228">Controllare i membri delle gerarchie degli attributi **English Month Name** e **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-228">Review the members of the **English Month Name** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="db8a9-229">È possibile notare che anche i membri di queste gerarchie non sono ordinati cronologicamente.</span><span class="sxs-lookup"><span data-stu-id="db8a9-229">Notice that the members of these hierarchies are also not sorted in chronological order.</span></span> <span data-ttu-id="db8a9-230">Sono invece ordinati rispettivamente per mese o per semestre e quindi per anno.</span><span class="sxs-lookup"><span data-stu-id="db8a9-230">Instead, they are sorted by month or semester, respectively, and then by year.</span></span> <span data-ttu-id="db8a9-231">Nell'attività successiva di questo argomento verrà modificato tale funzionamento in modo da cambiare il tipo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="db8a9-231">In the next task in this topic, you will modify this behavior to change this sort order.</span></span>  
  
## <a name="changing-the-sort-order-by-modifying-composite-key-member-order"></a><span data-ttu-id="db8a9-232">Modifica del tipo di ordinamento tramite la modifica dell'ordine dei membri della chiave composta</span><span class="sxs-lookup"><span data-stu-id="db8a9-232">Changing the Sort Order by Modifying Composite Key Member Order</span></span>  
 <span data-ttu-id="db8a9-233">In questa attività verrà modificato l'ordinamento cambiando l'ordine delle chiavi che costituiscono la chiave composta.</span><span class="sxs-lookup"><span data-stu-id="db8a9-233">In this task, you will change the sort order by changing the order of the keys that make up the composite key.</span></span>  
  
#### <a name="to-modify-the-composite-key-member-order"></a><span data-ttu-id="db8a9-234">Per modificare l'ordine dei membri della chiave composta</span><span class="sxs-lookup"><span data-stu-id="db8a9-234">To modify the composite key member order</span></span>  
  
1.  <span data-ttu-id="db8a9-235">Aprire la scheda **Struttura dimensione** di Progettazione dimensioni per la `Date` dimensione e quindi selezionare **Calendar Semester** nel riquadro **attributi** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-235">Open the **Dimension Structure** tab of Dimension Designer for the `Date` dimension, and then select **Calendar Semester** in the **Attributes** pane.</span></span>  
  
2.  <span data-ttu-id="db8a9-236">Nella finestra Proprietà controllare il valore della proprietà **OrderBy** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-236">In the Properties window, review the value for the **OrderBy** property.</span></span> <span data-ttu-id="db8a9-237">È impostato su **Chiave**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-237">It is set to **Key**.</span></span>  
  
     <span data-ttu-id="db8a9-238">I membri della gerarchia dell'attributo **Calendar Semester** vengono ordinati in base al valore della chiave.</span><span class="sxs-lookup"><span data-stu-id="db8a9-238">The members of the **Calendar Semester** attribute hierarchy are sorted by their key value.</span></span> <span data-ttu-id="db8a9-239">Con una chiave composta, l'ordinamento delle chiavi dei membri si basa innanzitutto sul valore della prima chiave del membro e quindi sul valore della seconda chiave.</span><span class="sxs-lookup"><span data-stu-id="db8a9-239">With a composite key, the ordering of the member keys is based first on the value of the first member key, and then on the value of the second member key.</span></span> <span data-ttu-id="db8a9-240">In altri termini, i membri della gerarchia dell'attributo **Calendar Semester** vengono ordinati prima in base al semestre, poi in base all'anno.</span><span class="sxs-lookup"><span data-stu-id="db8a9-240">In other words, the members of the **Calendar Semester** attribute hierarchy are sorted first by semester and then by year.</span></span>  
  
3.  <span data-ttu-id="db8a9-241">Nella finestra Proprietà fare clic sul pulsante con i puntini di sospensione (**...**) per cambiare il valore della proprietà **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-241">In the Properties window, click the ellipsis browse button (**...**) to change the **KeyColumns** property value.</span></span>  
  
4.  <span data-ttu-id="db8a9-242">Nell'elenco **Colonne chiave** della finestra di dialogo **Colonne chiave** verificare che **CalendarSemester** sia selezionato e fare clic sulla freccia a discesa per invertire l'ordine dei membri di questa chiave composta.</span><span class="sxs-lookup"><span data-stu-id="db8a9-242">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarSemester** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="db8a9-243">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-243">Click **OK**.</span></span>  
  
     <span data-ttu-id="db8a9-244">I membri della gerarchia dell'attributo sono ora ordinati per anno e quindi per semestre.</span><span class="sxs-lookup"><span data-stu-id="db8a9-244">The members of the attribute hierarchy are now sorted first by year and then by semester.</span></span>  
  
5.  <span data-ttu-id="db8a9-245">Selezionare **Calendar Quarter** nel riquadro **Attributi** e fare clic sul pulsante con i puntini di sospensione (**...**) della proprietà **KeyColumns** nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="db8a9-245">Select **Calendar Quarter** in the **Attributes** pane, and then click the ellipsis browse button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
6.  <span data-ttu-id="db8a9-246">Nell'elenco **Colonne chiave** della finestra di dialogo **Colonne chiave** verificare che **CalendarQuarter** sia selezionato e fare clic sulla freccia a discesa per invertire l'ordine dei membri di questa chiave composta.</span><span class="sxs-lookup"><span data-stu-id="db8a9-246">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarQuarter** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="db8a9-247">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-247">Click **OK**.</span></span>  
  
     <span data-ttu-id="db8a9-248">I membri della gerarchia dell'attributo sono ora ordinati per anno e quindi per trimestre.</span><span class="sxs-lookup"><span data-stu-id="db8a9-248">The members of the attribute hierarchy are now sorted first by year and then by quarter.</span></span>  
  
7.  <span data-ttu-id="db8a9-249">Selezionare **English Month Name** nel riquadro **Attributi** e fare clic sul pulsante con i puntini di sospensione (**...**) della proprietà **KeyColumns** nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="db8a9-249">Select **English Month Name** in the **Attributes** pane, and then click the ellipsis button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
8.  <span data-ttu-id="db8a9-250">Nell'elenco **Colonne chiave** della finestra di dialogo **Colonne chiave** verificare che **EnglishMonthName** sia selezionato e fare clic sulla freccia a discesa per invertire l'ordine dei membri di questa chiave composta.</span><span class="sxs-lookup"><span data-stu-id="db8a9-250">In the **Key Columns** list of the **Key Columns** dialog box, verify that **EnglishMonthName** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="db8a9-251">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-251">Click **OK**.</span></span>  
  
     <span data-ttu-id="db8a9-252">I membri della gerarchia dell'attributo sono ora ordinati per anno e quindi per mese.</span><span class="sxs-lookup"><span data-stu-id="db8a9-252">The members of the attribute hierarchy are now sorted first by year and then by month.</span></span>  
  
9. <span data-ttu-id="db8a9-253">Scegliere **Distribuisci Analysis Services Tutorial** dal menu [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]Compila **di**.</span><span class="sxs-lookup"><span data-stu-id="db8a9-253">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span> <span data-ttu-id="db8a9-254">Al termine della distribuzione, fare clic sulla scheda **esplorazione** in Progettazione dimensioni per la `Date` dimensione.</span><span class="sxs-lookup"><span data-stu-id="db8a9-254">When deployment has successfully completed, click the **Browser** tab in Dimension Designer for the `Date` dimension.</span></span>  
  
10. <span data-ttu-id="db8a9-255">Sulla barra degli strumenti della scheda **Esplorazione** fare clic sul pulsante Riconnetti.</span><span class="sxs-lookup"><span data-stu-id="db8a9-255">On the toolbar of the **Browser** tab, click the Reconnect button.</span></span>  
  
11. <span data-ttu-id="db8a9-256">Controllare i membri delle gerarchie degli attributi **Calendar Quarter** e **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-256">Review the members of the **Calendar Quarter** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="db8a9-257">Si noti che i membri di queste gerarchie sono ora ordinati cronologicamente per anno e quindi, rispettivamente, per trimestre o semestre.</span><span class="sxs-lookup"><span data-stu-id="db8a9-257">Notice that the members of these hierarchies are now sorted in chronological order, by year and then by quarter or semester, respectively.</span></span>  
  
12. <span data-ttu-id="db8a9-258">Controllare i membri della gerarchia dell'attributo **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="db8a9-258">Review the members of the **English Month Name** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="db8a9-259">Si noti che i membri della gerarchia dell'attributo sono ora ordinati per anno e quindi alfabeticamente per mese.</span><span class="sxs-lookup"><span data-stu-id="db8a9-259">Notice that the members of the hierarchy are now sorted first by year and then alphabetically by month.</span></span> <span data-ttu-id="db8a9-260">Questo avviene in quanto il tipo di dati per la colonna EnglishCalendarMonth nella vista origine dati è una colonna stringa basata sul tipo di dati nvarchar nel database relazionale sottostante.</span><span class="sxs-lookup"><span data-stu-id="db8a9-260">This is because the data type for the EnglishCalendarMonth column in the data source view is a string column, based on the nvarchar data type in the underlying relational database.</span></span> <span data-ttu-id="db8a9-261">Per informazioni su come consentire l'ordinamento cronologico dei mesi in ogni anno, vedere [Ordinamento dei membri dell'attributo in base a un attributo secondario](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="db8a9-261">For information about how to enable the months to be sorted chronologically within each year, see [Sorting Attribute Members Based on a Secondary Attribute](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="db8a9-262">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="db8a9-262">Next Task in Lesson</span></span>  
 [<span data-ttu-id="db8a9-263">Esplorazione di un cubo distribuito</span><span class="sxs-lookup"><span data-stu-id="db8a9-263">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="db8a9-264">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db8a9-264">See Also</span></span>  
 [<span data-ttu-id="db8a9-265">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="db8a9-265">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
