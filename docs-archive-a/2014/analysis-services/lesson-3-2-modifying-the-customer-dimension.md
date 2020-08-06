---
title: Modifica della dimensione Customer | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5b5aed99-1760-4bc7-b248-52ecb0b97ebc
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd5c5c47205a89f8429b0b6f0ba55da266d5e811
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635245"
---
# <a name="modifying-the-customer-dimension"></a><span data-ttu-id="de5b6-102">Modifica della dimensione Customer</span><span class="sxs-lookup"><span data-stu-id="de5b6-102">Modifying the Customer Dimension</span></span>
  <span data-ttu-id="de5b6-103">È possibile migliorare l'usabilità e le funzionalità delle dimensioni di un cubo in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="de5b6-103">There are many different ways that you can increase the usability and functionality of the dimensions in a cube.</span></span> <span data-ttu-id="de5b6-104">Nelle attività di questo argomento verrà modificata la dimensione Customer.</span><span class="sxs-lookup"><span data-stu-id="de5b6-104">In the tasks in this topic, you modify the Customer dimension.</span></span>  
  
## <a name="renaming-attributes"></a><span data-ttu-id="de5b6-105">Ridenominazione di attributi</span><span class="sxs-lookup"><span data-stu-id="de5b6-105">Renaming Attributes</span></span>  
 <span data-ttu-id="de5b6-106">È possibile modificare i nomi degli attributi con la scheda **Struttura dimensione** di Progettazione dimensioni.</span><span class="sxs-lookup"><span data-stu-id="de5b6-106">You can change attribute names with the **Dimension Structure** tab of Dimension Designer.</span></span>  
  
#### <a name="to-rename-an-attribute"></a><span data-ttu-id="de5b6-107">Per rinominare un attributo</span><span class="sxs-lookup"><span data-stu-id="de5b6-107">To rename an attribute</span></span>  
  
1.  <span data-ttu-id="de5b6-108">Passare a **Progettazione dimensioni** per la dimensione Customer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de5b6-108">Switch to **Dimension Designer** for the Customer dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="de5b6-109">A tale scopo, fare doppio clic sulla dimensione **Customer** nel nodo **Dimensioni** di Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="de5b6-109">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="de5b6-110">Nel riquadro **Attributi** fare clic con il pulsante destro del mouse su **English Country Region Name**e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-110">In the **Attributes** pane, right-click **English Country Region Name**, and then click **Rename**.</span></span> <span data-ttu-id="de5b6-111">Modificare il nome dell'attributo in `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-111">Change the name of the attribute to `Country-Region`.</span></span>  
  
3.  <span data-ttu-id="de5b6-112">Modificare i nomi degli attributi seguenti allo stesso modo:</span><span class="sxs-lookup"><span data-stu-id="de5b6-112">Change the names of the following attributes in the same manner:</span></span>  
  
    -   <span data-ttu-id="de5b6-113">Attributo per la **formazione in lingua inglese** -modifica a`Education`</span><span class="sxs-lookup"><span data-stu-id="de5b6-113">**English Education** attribute - change to `Education`</span></span>  
  
    -   <span data-ttu-id="de5b6-114">Attributo **occupation inglese** -modifica in`Occupation`</span><span class="sxs-lookup"><span data-stu-id="de5b6-114">**English Occupation** attribute - change to `Occupation`</span></span>  
  
    -   <span data-ttu-id="de5b6-115">Attributo **nome Provincia di stato** -modifica in`State-Province`</span><span class="sxs-lookup"><span data-stu-id="de5b6-115">**State Province Name** attribute - change to `State-Province`</span></span>  
  
4.  <span data-ttu-id="de5b6-116">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="de5b6-117">Creazione di una gerarchia</span><span class="sxs-lookup"><span data-stu-id="de5b6-117">Creating a Hierarchy</span></span>  
 <span data-ttu-id="de5b6-118">È possibile creare una nuova gerarchia trascinando un attributo dal riquadro **Attributi** al riquadro **Gerarchie** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-118">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="de5b6-119">Per creare una gerarchia</span><span class="sxs-lookup"><span data-stu-id="de5b6-119">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="de5b6-120">Trascinare l' `Country-Region` attributo dal riquadro **attributi** al riquadro **gerarchie** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-120">Drag the `Country-Region` attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="de5b6-121">Trascinare l' `State-Province` attributo dal riquadro **attributi** alla **\<new level>** cella nel riquadro **gerarchie** , sotto il `Country-Region` livello.</span><span class="sxs-lookup"><span data-stu-id="de5b6-121">Drag the `State-Province` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `Country-Region` level.</span></span>  
  
3.  <span data-ttu-id="de5b6-122">Trascinare l'attributo **City** dal riquadro **attributi** alla **\<new level>** cella nel riquadro **gerarchie** , sotto il `State-Province` livello.</span><span class="sxs-lookup"><span data-stu-id="de5b6-122">Drag the **City** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `State-Province` level.</span></span>  
  
4.  <span data-ttu-id="de5b6-123">Nel riquadro **gerarchie** della scheda **Struttura dimensione** fare clic con il pulsante destro del mouse sulla barra del titolo della gerarchia **gerarchia** , scegliere **Rinomina**, quindi digitare `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-123">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, select **Rename**, and then type `Customer Geography`.</span></span>  
  
     <span data-ttu-id="de5b6-124">Il nome della gerarchia è ora `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-124">The name of the hierarchy is now `Customer Geography`.</span></span>  
  
5.  <span data-ttu-id="de5b6-125">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-125">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="de5b6-126">Aggiunta di un calcolo denominato</span><span class="sxs-lookup"><span data-stu-id="de5b6-126">Adding a Named Calculation</span></span>  
 <span data-ttu-id="de5b6-127">È possibile aggiungere un calcolo denominato, ovvero un'espressione SQL rappresentata da una colonna calcolata, a una tabella in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="de5b6-127">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="de5b6-128">L'espressione ha lo stesso aspetto e funziona allo stesso modo di una colonna di una tabella.</span><span class="sxs-lookup"><span data-stu-id="de5b6-128">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="de5b6-129">I calcoli denominati consentono di estendere lo schema relazionale delle tabelle esistenti in una vista origine dati senza modificare la tabella dell'origine dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="de5b6-129">Named calculations let you extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="de5b6-130">Per altre informazioni, vedere [Definire calcoli denominati in una vista origine dati &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="de5b6-130">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="de5b6-131">Per aggiungere un calcolo denominato</span><span class="sxs-lookup"><span data-stu-id="de5b6-131">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="de5b6-132">Per aprire la vista origine dati \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* , fare doppio clic su di essa nella cartella **viste origine dati** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="de5b6-132">Open the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view by double-clicking it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="de5b6-133">Nel riquadro **Tabelle** a sinistra, fare clic con il pulsante destro del mouse su **Customer**e scegliere **Nuovo calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-133">In the **Tables** pane on the left, right-click **Customer**, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="de5b6-134">Nella finestra di dialogo **Crea calcolo denominato** Digitare `FullName` nella casella **nome colonna** , quindi digitare o copiare e incollare l' `CASE` istruzione seguente nella casella **espressione** :</span><span class="sxs-lookup"><span data-stu-id="de5b6-134">In the **Create Named Calculation** dialog box, type `FullName` in the **Column name** box, and then type or copy and paste the following `CASE` statement in the **Expression** box:</span></span>  
  
    ```  
    CASE  
       WHEN MiddleName IS NULL THEN  
       FirstName + ' ' + LastName  
       ELSE  
       FirstName + ' ' + MiddleName + ' ' + LastName  
    END  
    ```  
  
     <span data-ttu-id="de5b6-135">L' `CASE` istruzione concatena le colonne **FirstName**, **MiddleName**e **LastName** in una singola colonna che verrà usata nella dimensione Customer come nome visualizzato per l'attributo **Customer** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-135">The `CASE` statement concatenates the **FirstName**, **MiddleName**, and **LastName** columns into a single column that you will use in the Customer dimension as the displayed name for the **Customer** attribute.</span></span>  
  
4.  <span data-ttu-id="de5b6-136">Fare clic su **OK**e quindi espandere **Customer** nel riquadro **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-136">Click **OK**, and then expand **Customer** in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="de5b6-137">Il `FullName` calcolo denominato viene visualizzato nell'elenco di colonne della tabella Customer, con un'icona che indica che si tratta di un calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="de5b6-137">The `FullName` named calculation appears in the list of columns in the Customer table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="de5b6-138">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-138">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="de5b6-139">Nel riquadro **Tabelle** fare clic con il pulsante destro del mouse su **Customer**e quindi scegliere **Esplora dati**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-139">In the **Tables** pane, right-click **Customer**, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="de5b6-140">Controllare l'ultima colonna della vista **Esplora tabella Customer** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-140">Review the last column in the **Explore Customer Table** view.</span></span>  
  
     <span data-ttu-id="de5b6-141">Si noti che la `FullName` colonna viene visualizzata nella vista origine dati, concatenando correttamente i dati di numerose colonne dell'origine dati sottostante e senza modificare l'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="de5b6-141">Notice that the `FullName` column appears in the data source view, correctly concatenating data from several columns from the underlying data source and without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="de5b6-142">Chiudere la scheda **Esplora tabella Customer** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-142">Close the **Explore Customer Table** tab.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="de5b6-143">Utilizzo del calcolo denominato per i nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="de5b6-143">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="de5b6-144">Dopo aver creato un calcolo denominato nella vista origine dati, è possibile utilizzarlo come proprietà di un attributo.</span><span class="sxs-lookup"><span data-stu-id="de5b6-144">After you have created a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="de5b6-145">Per utilizzare il calcolo denominato per i nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="de5b6-145">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="de5b6-146">Passare a Progettazione dimensioni per la dimensione Customer.</span><span class="sxs-lookup"><span data-stu-id="de5b6-146">Switch to Dimension Designer for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="de5b6-147">Nel riquadro **Attributi** della scheda **Struttura dimensione** fare clic sull'attributo **Customer Key** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-147">In the **Attributes** pane of the **Dimension Structure** tab, click the **Customer Key** attribute.</span></span>  
  
3.  <span data-ttu-id="de5b6-148">Aprire la finestra Proprietà e fare clic sul pulsante **Nascondi automaticamente** sulla barra del titolo in modo che rimanga aperta.</span><span class="sxs-lookup"><span data-stu-id="de5b6-148">Open the Properties window and click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="de5b6-149">Nel campo della proprietà **nome** Digitare `Full Name` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-149">In the **Name** property field, type `Full Name`.</span></span>  
  
5.  <span data-ttu-id="de5b6-150">Fare clic sul campo proprietà **NameColumn** nella parte inferiore, quindi fare clic sul pulsante Sfoglia (**..**.) per aprire la finestra di dialogo **colonna nome** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-150">Click in the **NameColumn** property field at the bottom, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
6.  <span data-ttu-id="de5b6-151">Selezionare `FullName` nella parte inferiore dell'elenco **colonna di origine** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-151">Select `FullName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="de5b6-152">Nella scheda struttura dimensioni trascinare l' `Full Name` attributo dal riquadro **attributi** alla **\<new level>** cella nel riquadro **gerarchie** , sotto il livello **City** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-152">In the Dimensions Structure tab, drag the `Full Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **City** level.</span></span>  
  
8.  <span data-ttu-id="de5b6-153">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-153">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-display-folders"></a><span data-ttu-id="de5b6-154">Definizione di cartelle di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="de5b6-154">Defining Display Folders</span></span>  
 <span data-ttu-id="de5b6-155">È possibile utilizzare cartelle di visualizzazione per raggruppare gerarchie utente e di attributi in strutture di cartelle per migliorare l'usabilità.</span><span class="sxs-lookup"><span data-stu-id="de5b6-155">You can use display folders to group user and attribute hierarchies into folder structures to increase usability.</span></span>  
  
#### <a name="to-define-display-folders"></a><span data-ttu-id="de5b6-156">Per definire cartelle di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="de5b6-156">To define display folders</span></span>  
  
1.  <span data-ttu-id="de5b6-157">Aprire la scheda **Struttura dimensione** per la dimensione Customer.</span><span class="sxs-lookup"><span data-stu-id="de5b6-157">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="de5b6-158">Nel riquadro **Attributi** tenere premuto CTRL e fare clic su ognuno dei seguenti attributi per selezionarli:</span><span class="sxs-lookup"><span data-stu-id="de5b6-158">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="de5b6-159">**Città**</span><span class="sxs-lookup"><span data-stu-id="de5b6-159">**City**</span></span>  
  
    -   `Country-Region`  
  
    -   <span data-ttu-id="de5b6-160">**CAP**</span><span class="sxs-lookup"><span data-stu-id="de5b6-160">**Postal Code**</span></span>  
  
    -   `State-Province`  
  
3.  <span data-ttu-id="de5b6-161">Nella Finestra Proprietà fare clic sul campo della proprietà **AttributeHierarchyDisplayFolder** nella parte superiore (potrebbe essere necessario puntare a tale campo per visualizzare il nome completo), quindi digitare `Location` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-161">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top (you might need to point to it to see the full name), and then type `Location`.</span></span>  
  
4.  <span data-ttu-id="de5b6-162">Nel riquadro **gerarchie** fare clic `Customer Geography` su, quindi nella finestra proprietà a destra selezionare `Location` come valore della proprietà **DisplayFolder** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-162">In the **Hierarchies** pane, click `Customer Geography`, and then in the Properties window on the right, select `Location` as the value of the **DisplayFolder** property.</span></span>  
  
5.  <span data-ttu-id="de5b6-163">Nel riquadro **Attributi** tenere premuto CTRL e fare clic su ognuno dei seguenti attributi per selezionarli:</span><span class="sxs-lookup"><span data-stu-id="de5b6-163">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="de5b6-164">**Commute Distance**</span><span class="sxs-lookup"><span data-stu-id="de5b6-164">**Commute Distance**</span></span>  
  
    -   `Education`  
  
    -   <span data-ttu-id="de5b6-165">**Sesso**</span><span class="sxs-lookup"><span data-stu-id="de5b6-165">**Gender**</span></span>  
  
    -   <span data-ttu-id="de5b6-166">**House Owner Flag**</span><span class="sxs-lookup"><span data-stu-id="de5b6-166">**House Owner Flag**</span></span>  
  
    -   <span data-ttu-id="de5b6-167">**Marital Status**</span><span class="sxs-lookup"><span data-stu-id="de5b6-167">**Marital Status**</span></span>  
  
    -   <span data-ttu-id="de5b6-168">**Number Cars Owned**</span><span class="sxs-lookup"><span data-stu-id="de5b6-168">**Number Cars Owned**</span></span>  
  
    -   <span data-ttu-id="de5b6-169">**Numero di figli a casa**</span><span class="sxs-lookup"><span data-stu-id="de5b6-169">**Number Children At Home**</span></span>  
  
    -   `Occupation`  
  
    -   <span data-ttu-id="de5b6-170">**Total Children**</span><span class="sxs-lookup"><span data-stu-id="de5b6-170">**Total Children**</span></span>  
  
    -   <span data-ttu-id="de5b6-171">**Yearly Income**</span><span class="sxs-lookup"><span data-stu-id="de5b6-171">**Yearly Income**</span></span>  
  
6.  <span data-ttu-id="de5b6-172">Nella Finestra Proprietà fare clic sul campo della proprietà **AttributeHierarchyDisplayFolder** nella parte superiore, quindi digitare `Demographic` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-172">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top, and then type `Demographic`.</span></span>  
  
7.  <span data-ttu-id="de5b6-173">Nel riquadro **Attributi** tenere premuto CTRL e fare clic su ognuno dei seguenti attributi per selezionarli:</span><span class="sxs-lookup"><span data-stu-id="de5b6-173">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="de5b6-174">**Indirizzo di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="de5b6-174">**Email Address**</span></span>  
  
    -   <span data-ttu-id="de5b6-175">**Phone**</span><span class="sxs-lookup"><span data-stu-id="de5b6-175">**Phone**</span></span>  
  
8.  <span data-ttu-id="de5b6-176">Nella Finestra Proprietà fare clic sul campo della proprietà **AttributeHierarchyDisplayFolder** e digitare `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-176">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field and type `Contacts`.</span></span>  
  
9. <span data-ttu-id="de5b6-177">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-177">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns"></a><span data-ttu-id="de5b6-178">Definizione della proprietà KeyColumns composta</span><span class="sxs-lookup"><span data-stu-id="de5b6-178">Defining Composite KeyColumns</span></span>  
 <span data-ttu-id="de5b6-179">La proprietà **KeyColumns** contiene la colonna o le colonne che rappresentano la chiave per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="de5b6-179">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="de5b6-180">In questa lezione verrà creata una chiave composta per la **città** e `State-Province` gli attributi.</span><span class="sxs-lookup"><span data-stu-id="de5b6-180">In this lesson, you create a composite key for the **City** and `State-Province` attributes.</span></span> <span data-ttu-id="de5b6-181">Le chiavi composte possono essere utili quando è necessario identificare in modo univoco un attributo.</span><span class="sxs-lookup"><span data-stu-id="de5b6-181">Composite keys can be helpful when you need to uniquely identify an attribute.</span></span> <span data-ttu-id="de5b6-182">Ad esempio, quando si definiscono le relazioni tra attributi più avanti in questa esercitazione, un attributo **City** deve identificare in modo univoco un `State-Province` attributo.</span><span class="sxs-lookup"><span data-stu-id="de5b6-182">For example, when you define attribute relationships later in this tutorial, a **City** attribute must uniquely identify a `State-Province` attribute.</span></span> <span data-ttu-id="de5b6-183">Tuttavia, è possibile che esistano varie città con lo stesso nome in stati diversi.</span><span class="sxs-lookup"><span data-stu-id="de5b6-183">However, there could be several cities with the same name in different states.</span></span> <span data-ttu-id="de5b6-184">Per questo motivo verrà creata una chiave composta, costituita dalle colonne **StateProvinceName** e **City** per l'attributo **City** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-184">For this reason, you will create a composite key that is composed of the **StateProvinceName** and **City** columns for the **City** attribute.</span></span> <span data-ttu-id="de5b6-185">Per altre informazioni, vedere [Modificare la proprietà KeyColumn di un attributo](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="de5b6-185">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-city-attribute"></a><span data-ttu-id="de5b6-186">Per definire la proprietà KeyColumns composta per l'attributo City</span><span class="sxs-lookup"><span data-stu-id="de5b6-186">To define composite KeyColumns for the City attribute</span></span>  
  
1.  <span data-ttu-id="de5b6-187">Aprire la scheda **Struttura dimensione** per la dimensione Customer.</span><span class="sxs-lookup"><span data-stu-id="de5b6-187">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="de5b6-188">Nel riquadro **Attributi** fare clic sull'attributo **City** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-188">In the **Attributes** pane, click the **City** attribute.</span></span>  
  
3.  <span data-ttu-id="de5b6-189">Nella finestra **Proprietà** fare clic nel campo **KeyColumns** nella parte inferiore e fare clic sul pulsante Sfoglia (**...**).</span><span class="sxs-lookup"><span data-stu-id="de5b6-189">In the **Properties** window, click in the **KeyColumns** field near the bottom, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="de5b6-190">Nella finestra di dialogo **Colonne chiave** , nell'elenco **Colonne disponibili** selezionare la colonna **StateProvinceName**e fare clic sul pulsante **>** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-190">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **StateProvinceName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="de5b6-191">Le colonne **City** e **StateProvinceName** sono ora visualizzate nell'elenco **Colonne chiave** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-191">The **City** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="de5b6-192">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-192">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="de5b6-193">Per impostare la proprietà **NameColumn** dell'attributo **City** , fare clic nel campo **NameColumn** della finestra Proprietà e fare clic sul pulsante Sfoglia (**...**).</span><span class="sxs-lookup"><span data-stu-id="de5b6-193">To set the **NameColumn** property of the **City** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="de5b6-194">Nella finestra di dialogo **Colonna nome** , nell'elenco **Colonna di origine** selezionare **City**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-194">In the **Name Column** dialog box, in the **Source column** list, select **City**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="de5b6-195">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-195">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-state-province-attribute"></a><span data-ttu-id="de5b6-196">Per definire la proprietà KeyColumns composta per l'attributo State-Province</span><span class="sxs-lookup"><span data-stu-id="de5b6-196">To define composite KeyColumns for the State-Province attribute</span></span>  
  
1.  <span data-ttu-id="de5b6-197">Assicurarsi che la scheda **Struttura dimensione** per la dimensione Customer sia aperta.</span><span class="sxs-lookup"><span data-stu-id="de5b6-197">Make sure the **Dimension Structure** tab for the Customer dimension is open.</span></span>  
  
2.  <span data-ttu-id="de5b6-198">Nel riquadro **attributi** fare clic sull' `State-Province` attributo.</span><span class="sxs-lookup"><span data-stu-id="de5b6-198">In the **Attributes** pane, click the `State-Province` attribute.</span></span>  
  
3.  <span data-ttu-id="de5b6-199">Nella finestra **Proprietà** fare clic nel campo **KeyColumns** e quindi sul pulsante Sfoglia (**...**).</span><span class="sxs-lookup"><span data-stu-id="de5b6-199">In the **Properties** window, click in the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="de5b6-200">Nella finestra di dialogo **Colonne chiave** , nell'elenco **Colonne disponibili** selezionare la colonna **EnglishCountryRegionName**e fare clic sul pulsante **>** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-200">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **EnglishCountryRegionName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="de5b6-201">Le colonne **EnglishCountryRegionName** e **StateProvinceName** sono ora visualizzate nell'elenco **Colonne chiave** .</span><span class="sxs-lookup"><span data-stu-id="de5b6-201">The **EnglishCountryRegionName** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="de5b6-202">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-202">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="de5b6-203">Per impostare la proprietà **NameColumn** dell' `State-Province` attributo, fare clic sul campo **NameColumn** nel finestra Proprietà, quindi fare clic sul pulsante Sfoglia (**..**.).</span><span class="sxs-lookup"><span data-stu-id="de5b6-203">To set the **NameColumn** property of the `State-Province` attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="de5b6-204">Nell'elenco **Colonna di origine** della finestra di dialogo **Colonna nome** selezionare **StateProvinceName**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-204">In the **Name Column** dialog box, in the **Source column** list, select **StateProvinceName**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="de5b6-205">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-205">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="de5b6-206">Definizione di relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="de5b6-206">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="de5b6-207">Se i dati sottostanti le supportano, è consigliabile definire relazioni tra gli attributi.</span><span class="sxs-lookup"><span data-stu-id="de5b6-207">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="de5b6-208">La definizione di relazioni tra attributi consente di velocizzare l'elaborazione di dimensioni, partizioni e query.</span><span class="sxs-lookup"><span data-stu-id="de5b6-208">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="de5b6-209">Per altre informazioni, vedere [Definire relazioni tra attributi](multidimensional-models/attribute-relationships-define.md) e [Relazioni tra attributi](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="de5b6-209">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="de5b6-210">Per definire relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="de5b6-210">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="de5b6-211">In **Progettazione dimensioni** per la dimensione Customer fare clic sulla scheda **relazioni tra attributi** . Potrebbe essere necessario attendere.</span><span class="sxs-lookup"><span data-stu-id="de5b6-211">In the **Dimension Designer** for the Customer dimension, click the **Attribute Relationships** tab. You might need to wait.</span></span>  
  
2.  <span data-ttu-id="de5b6-212">Nel diagramma fare clic con il pulsante destro del mouse sull'attributo **City** , quindi scegliere **Nuova relazione tra attributi**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-212">In the diagram, right-click the **City** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="de5b6-213">Nella finestra di dialogo **Crea relazione tra attributi** l'opzione **Attributo di origine** è impostata su **City**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-213">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **City**.</span></span> <span data-ttu-id="de5b6-214">Impostare **attributo correlato** su `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-214">Set the **Related Attribute** to `State-Province`.</span></span>  
  
4.  <span data-ttu-id="de5b6-215">Nell'elenco **Tipo di relazione** impostare il tipo di relazione su **Rigida**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-215">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="de5b6-216">Il tipo di relazione è **Rigida** perché le relazioni tra i membri non cambieranno nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="de5b6-216">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span> <span data-ttu-id="de5b6-217">Ad esempio, è raro che una città diventi parte di uno stato o di una provincia diversa.</span><span class="sxs-lookup"><span data-stu-id="de5b6-217">For example, it would be unusual for a city to become part of a different state or province.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="de5b6-218">Nel diagramma fare clic con il pulsante destro del mouse sull' `State-Province` attributo e quindi scegliere **nuova relazione tra attributi**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-218">In the diagram, right-click the `State-Province` attribute and then select **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="de5b6-219">Nella finestra di dialogo **Crea relazione tra attributi** l' **attributo di origine** è `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-219">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is `State-Province`.</span></span> <span data-ttu-id="de5b6-220">Impostare **attributo correlato** su `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="de5b6-220">Set the **Related Attribute** to `Country-Region`.</span></span>  
  
8.  <span data-ttu-id="de5b6-221">Nell'elenco **Tipo di relazione** impostare il tipo di relazione su **Rigida**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-221">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="de5b6-222">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-222">Click **OK**.</span></span>  
  
10. <span data-ttu-id="de5b6-223">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-223">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-changes-processing-the-objects-and-viewing-the-changes"></a><span data-ttu-id="de5b6-224">Distribuzione delle modifiche, elaborazione degli oggetti e visualizzazione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="de5b6-224">Deploying Changes, Processing the Objects, and Viewing the Changes</span></span>  
 <span data-ttu-id="de5b6-225">Dopo aver modificato gli attributi e le gerarchie, prima di visualizzare le modifiche è necessario distribuirle e rielaborare gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="de5b6-225">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-the-changes-process-the-objects-and-view-the-changes"></a><span data-ttu-id="de5b6-226">Per distribuire le modifiche, elaborare gli oggetti e visualizzare le modifiche</span><span class="sxs-lookup"><span data-stu-id="de5b6-226">To deploy the changes, process the objects, and view the changes</span></span>  
  
1.  <span data-ttu-id="de5b6-227">Scegliere **Distribuisci Analysis Services Tutorial** dal menu [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]Compila **di**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-227">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="de5b6-228">Dopo la visualizzazione del messaggio **Distribuzione completata** , fare clic sulla scheda **Esplorazione** di Progettazione dimensioni per la dimensione Customer e fare clic sul pulsante Riconnetti a sinistra della barra degli strumenti della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="de5b6-228">After you receive the **Deployment Completed Successfully** message, click the **Browser** tab of Dimension Designer for the Customer dimension, and then click the Reconnect button on the left side of the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="de5b6-229">Verificare che `Customer Geography` sia selezionato nell'elenco **gerarchia** , quindi nel riquadro del browser espandere **tutto**, **Australia**, **New South Wales**, quindi espandere **Coffs Harbour**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-229">Verify that `Customer Geography` is selected in the **Hierarchy** list, and then in the browser pane, expand **All**, expand **Australia**, expand **New South Wales**, and then expand **Coffs Harbour**.</span></span>  
  
     <span data-ttu-id="de5b6-230">Verranno visualizzati i clienti della città.</span><span class="sxs-lookup"><span data-stu-id="de5b6-230">The browser displays the customers in the city.</span></span>  
  
4.  <span data-ttu-id="de5b6-231">Passare a **Progettazione cubi** per il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="de5b6-231">Switch to **Cube Designer** for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="de5b6-232">A tale scopo, fare doppio clic sul cubo **Analysis Services Tutorial** nel nodo **Cubi** di **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-232">To do this, double-click the **Analysis Services Tutorial** cube in the **Cubes** node of **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="de5b6-233">Fare clic sulla scheda **Esplorazione** e quindi scegliere il pulsante Riconnetti sulla barra degli strumenti della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="de5b6-233">Click the **Browser** tab, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
6.  <span data-ttu-id="de5b6-234">Nel riquadro **Gruppo di misure** espandere **Customer**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-234">In the **Measure Group** pane, expand **Customer**.</span></span>  
  
     <span data-ttu-id="de5b6-235">Si noti che anziché un lungo elenco di attributi, sotto Customer vengono elencate solo le cartelle di visualizzazione e gli attributi che non presentano valori di cartelle di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="de5b6-235">Notice that instead of a long list of attributes, only the display folders and the attributes that do not have display folder values appear underneath Customer.</span></span>  
  
7.  <span data-ttu-id="de5b6-236">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="de5b6-236">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="de5b6-237">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="de5b6-237">Next Task in Lesson</span></span>  
 [<span data-ttu-id="de5b6-238">Modifica della dimensione Product</span><span class="sxs-lookup"><span data-stu-id="de5b6-238">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="de5b6-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de5b6-239">See Also</span></span>  
 <span data-ttu-id="de5b6-240">[Riferimento alle proprietà degli attributi delle dimensioni](multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="de5b6-240">[Dimension Attribute Properties Reference](multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="de5b6-241">[Rimuovere un attributo da una dimensione](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="de5b6-241">[Remove an Attribute from a Dimension](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span></span>  
 <span data-ttu-id="de5b6-242">[Rinominare un attributo](multidimensional-models/attribute-properties-rename-an-attribute.md) </span><span class="sxs-lookup"><span data-stu-id="de5b6-242">[Rename an Attribute](multidimensional-models/attribute-properties-rename-an-attribute.md) </span></span>  
 [<span data-ttu-id="de5b6-243">Definire calcoli denominati in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="de5b6-243">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
