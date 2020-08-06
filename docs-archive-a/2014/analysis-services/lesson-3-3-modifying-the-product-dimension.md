---
title: Modifica della dimensione Product | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8e3ffecd-7f40-41a8-8735-bc9858a310cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 04c0a778a73371dada92c9ff207a17366a2fbc7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630140"
---
# <a name="modifying-the-product-dimension"></a><span data-ttu-id="afba8-102">Modifica della dimensione Product</span><span class="sxs-lookup"><span data-stu-id="afba8-102">Modifying the Product Dimension</span></span>
  <span data-ttu-id="afba8-103">Nelle attività di questo argomento si utilizzerà un calcolo denominato per fornire nomi più descrittivi per le linee di prodotti, si definirà una gerarchia nella dimensione Product e si specificherà il nome membro (Totale) per la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="afba8-103">In the tasks in this topic, you use a named calculation to provide more descriptive names for the product lines, define a hierarchy in the Product dimension, and specify the (All) member name for the hierarchy.</span></span> <span data-ttu-id="afba8-104">Si raggrupperanno inoltre gli attributi in cartelle di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="afba8-104">You also group attributes into display folders.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="afba8-105">Aggiunta di un calcolo denominato</span><span class="sxs-lookup"><span data-stu-id="afba8-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="afba8-106">È possibile aggiungere un calcolo denominato a una tabella in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="afba8-106">You can add a named calculation to a table in a data source view.</span></span> <span data-ttu-id="afba8-107">Nell'attività seguente verrà creato un calcolo denominato che consente di visualizzare il nome completo della linea di prodotti.</span><span class="sxs-lookup"><span data-stu-id="afba8-107">In the following task, you create a named calculation that displays the full product line name.</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="afba8-108">Per aggiungere un calcolo denominato</span><span class="sxs-lookup"><span data-stu-id="afba8-108">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="afba8-109">Per aprire la vista origine dati **Adventure Works DW 2012** , fare doppio clic su **Adventure Works DW 2012** nella cartella **Viste origine dati** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="afba8-109">To open the **Adventure Works DW 2012** data source view, double-click **Adventure Works DW 2012** in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="afba8-110">Nella parte inferiore del riquadro diagramma fare clic con il pulsante destro del mouse sull'intestazione di tabella **Product** , quindi scegliere **Nuovo calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="afba8-110">In the bottom of the diagram pane, right-click the **Product** table header, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="afba8-111">Nella finestra di dialogo **Crea calcolo denominato** Digitare `ProductLineName` nella casella **nome colonna** .</span><span class="sxs-lookup"><span data-stu-id="afba8-111">In the **Create Named Calculation** dialog box, type `ProductLineName` in the **Column name** box.</span></span>  
  
4.  <span data-ttu-id="afba8-112">Nella casella **Espressione** digitare o copiare e incollare l'istruzione **CASE** seguente:</span><span class="sxs-lookup"><span data-stu-id="afba8-112">In the **Expression** box, type or copy and paste the following **CASE** statement:</span></span>  
  
    ```  
    CASE ProductLine  
       WHEN 'M' THEN 'Mountain'  
       WHEN 'R' THEN 'Road'  
       WHEN 'S' THEN 'Accessory'  
       WHEN 'T' THEN 'Touring'  
       ELSE 'Components'  
    END  
    ```  
  
     <span data-ttu-id="afba8-113">Con questa istruzione **CASE** vengono creati nomi descrittivi per ogni linea di prodotti nel cubo.</span><span class="sxs-lookup"><span data-stu-id="afba8-113">This **CASE** statement creates user-friendly names for each product line in the cube.</span></span>  
  
5.  <span data-ttu-id="afba8-114">Fare clic su **OK** per creare il `ProductLineName` calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="afba8-114">Click **OK** to create the `ProductLineName` named calculation.</span></span> <span data-ttu-id="afba8-115">Potrebbe essere necessario attendere alcuni istanti.</span><span class="sxs-lookup"><span data-stu-id="afba8-115">You might need to wait.</span></span>  
  
6.  <span data-ttu-id="afba8-116">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="afba8-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="modifying-the-namecolumn-property-of-an-attribute"></a><span data-ttu-id="afba8-117">Modifica della proprietà NameColumn di un attributo</span><span class="sxs-lookup"><span data-stu-id="afba8-117">Modifying the NameColumn Property of an Attribute</span></span>  
  
#### <a name="to-modify-the-namecolumn-property-value-of-an-attribute"></a><span data-ttu-id="afba8-118">Per modificare il valore della proprietà NameColumn di un attributo</span><span class="sxs-lookup"><span data-stu-id="afba8-118">To modify the NameColumn property value of an attribute</span></span>  
  
1.  <span data-ttu-id="afba8-119">Passare a Progettazione dimensioni per la dimensione Product.</span><span class="sxs-lookup"><span data-stu-id="afba8-119">Switch to Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="afba8-120">A tale scopo, fare doppio clic sulla dimensione **Product** nel nodo **Dimensioni** di Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="afba8-120">To do this, double-click the **Product** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="afba8-121">Nel riquadro **Attributi** della scheda **Struttura dimensione** selezionare **Product Line**.</span><span class="sxs-lookup"><span data-stu-id="afba8-121">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Line**.</span></span>  
  
3.  <span data-ttu-id="afba8-122">Nella Finestra Proprietà sul lato destro dello schermo fare clic sul campo proprietà **NameColumn** nella parte inferiore della finestra, quindi fare clic sul pulsante Sfoglia (**..**.) per aprire la finestra di dialogo **colonna nome** .</span><span class="sxs-lookup"><span data-stu-id="afba8-122">In the Properties window on the right side of the screen, click the **NameColumn** property field at the bottom of the window, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span> <span data-ttu-id="afba8-123">Per aprire la finestra Proprietà, potrebbe essere necessario fare clic sulla scheda **Proprietà** sul lato destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="afba8-123">(You might need to click the **Properties** tab on the right side of the screen to open the Properties window.</span></span>  
  
4.  <span data-ttu-id="afba8-124">Selezionare `ProductLineName` nella parte inferiore dell'elenco **colonna di origine** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="afba8-124">Select `ProductLineName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="afba8-125">Il campo NameColumn ora contiene il testo **Product.ProductLineName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="afba8-125">The NameColumn field now contains the text, **Product.ProductLineName (WChar)**.</span></span> <span data-ttu-id="afba8-126">I membri della gerarchia dell'attributo **Product Line** ora vengono visualizzati con il nome completo della linea di prodotti anziché con un nome abbreviato.</span><span class="sxs-lookup"><span data-stu-id="afba8-126">The members of the **Product Line** attribute hierarchy now display the full name of the product line instead of an abbreviated product line name.</span></span>  
  
5.  <span data-ttu-id="afba8-127">Nel riquadro **Attributi** della scheda **Struttura dimensione** selezionare **Product Key**.</span><span class="sxs-lookup"><span data-stu-id="afba8-127">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Key**.</span></span>  
  
6.  <span data-ttu-id="afba8-128">Nella Finestra Proprietà fare clic sul campo della proprietà **NameColumn** , quindi fare clic sul pulsante con i puntini di sospensione (**...**) per aprire la finestra di dialogo **colonna nome** .</span><span class="sxs-lookup"><span data-stu-id="afba8-128">In the Properties window, click the **NameColumn** property field, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
7.  <span data-ttu-id="afba8-129">Selezionare **EnglishProductName** nell'elenco **Colonna di origine** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="afba8-129">Select **EnglishProductName** in the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="afba8-130">Il campo NameColumn ora contiene il testo **Product.EnglishProductName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="afba8-130">The NameColumn field now contains the text, **Product.EnglishProductName (WChar)**.</span></span>  
  
8.  <span data-ttu-id="afba8-131">Nella Finestra Proprietà scorrere verso l'alto, fare clic sul campo della proprietà **nome** , quindi digitare `Product Name` .</span><span class="sxs-lookup"><span data-stu-id="afba8-131">In the Properties window, scroll up, click the **Name** property field, and then type `Product Name`.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="afba8-132">Creazione di una gerarchia</span><span class="sxs-lookup"><span data-stu-id="afba8-132">Creating a Hierarchy</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="afba8-133">Per creare una gerarchia</span><span class="sxs-lookup"><span data-stu-id="afba8-133">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="afba8-134">Trascinare l'attributo **Product Line** dal riquadro **Attributi** al riquadro **Gerarchie** .</span><span class="sxs-lookup"><span data-stu-id="afba8-134">Drag the **Product Line** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="afba8-135">Trascinare l'attributo **Model Name** dal riquadro **Attributi** alla cella **\<new level>** nel riquadro **Gerarchie** , sotto il livello **Product Line** .</span><span class="sxs-lookup"><span data-stu-id="afba8-135">Drag the **Model Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Product Line** level.</span></span>  
  
3.  <span data-ttu-id="afba8-136">Trascinare l' `Product Name` attributo dal riquadro **attributi** alla **\<new level>** cella nel riquadro **gerarchie** , sotto il livello del **nome del modello** .</span><span class="sxs-lookup"><span data-stu-id="afba8-136">Drag the `Product Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Model Name** level.</span></span> <span data-ttu-id="afba8-137">L'attributo Product Key è stato rinominato in Product Name nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="afba8-137">(You renamed Product Key to Product Name in the previous section.)</span></span>  
  
4.  <span data-ttu-id="afba8-138">Nel riquadro **gerarchie** della scheda **Struttura dimensione** fare clic con il pulsante destro del mouse sulla barra del titolo della gerarchia **gerarchia** , scegliere **Rinomina**, quindi digitare `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="afba8-138">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Product Model Lines`.</span></span>  
  
     <span data-ttu-id="afba8-139">Il nome della gerarchia è ora `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="afba8-139">The name of the hierarchy is now `Product Model Lines`.</span></span>  
  
5.  <span data-ttu-id="afba8-140">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="afba8-140">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="specifying-folder-names-and-all-member-names"></a><span data-ttu-id="afba8-141">Impostazione dei nomi delle cartelle e dei nomi di membro Totale</span><span class="sxs-lookup"><span data-stu-id="afba8-141">Specifying Folder Names and All Member Names</span></span>  
  
#### <a name="to-specify-the-folder-and-member-names"></a><span data-ttu-id="afba8-142">Per impostare i nomi delle cartelle e dei membri</span><span class="sxs-lookup"><span data-stu-id="afba8-142">To specify the folder and member names</span></span>  
  
1.  <span data-ttu-id="afba8-143">Nel riquadro **Attributi** tenere premuto CTRL e fare clic su ognuno dei seguenti attributi per selezionarli:</span><span class="sxs-lookup"><span data-stu-id="afba8-143">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="afba8-144">**Class**</span><span class="sxs-lookup"><span data-stu-id="afba8-144">**Class**</span></span>  
  
    -   <span data-ttu-id="afba8-145">**Colore**</span><span class="sxs-lookup"><span data-stu-id="afba8-145">**Color**</span></span>  
  
    -   <span data-ttu-id="afba8-146">**Giorni per la produzione**</span><span class="sxs-lookup"><span data-stu-id="afba8-146">**Days To Manufacture**</span></span>  
  
    -   <span data-ttu-id="afba8-147">**Reorder Point**</span><span class="sxs-lookup"><span data-stu-id="afba8-147">**Reorder Point**</span></span>  
  
    -   <span data-ttu-id="afba8-148">**Safety Stock Level**</span><span class="sxs-lookup"><span data-stu-id="afba8-148">**Safety Stock Level**</span></span>  
  
    -   <span data-ttu-id="afba8-149">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="afba8-149">**Size**</span></span>  
  
    -   <span data-ttu-id="afba8-150">**Size Range**</span><span class="sxs-lookup"><span data-stu-id="afba8-150">**Size Range**</span></span>  
  
    -   <span data-ttu-id="afba8-151">**Style**</span><span class="sxs-lookup"><span data-stu-id="afba8-151">**Style**</span></span>  
  
    -   <span data-ttu-id="afba8-152">**Weight**</span><span class="sxs-lookup"><span data-stu-id="afba8-152">**Weight**</span></span>  
  
2.  <span data-ttu-id="afba8-153">Nel campo della proprietà **AttributeHierarchyDisplayFolder** nel finestra Proprietà, digitare `Stocking` .</span><span class="sxs-lookup"><span data-stu-id="afba8-153">In the **AttributeHierarchyDisplayFolder** property field in the Properties window, type `Stocking`.</span></span>  
  
     <span data-ttu-id="afba8-154">Questi attributi sono stati ora raggruppati in un'unica cartella di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="afba8-154">You have now grouped these attributes into a single display folder.</span></span>  
  
3.  <span data-ttu-id="afba8-155">Nel riquadro **Attributi** selezionare i seguenti attributi:</span><span class="sxs-lookup"><span data-stu-id="afba8-155">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="afba8-156">**Dealer Price**</span><span class="sxs-lookup"><span data-stu-id="afba8-156">**Dealer Price**</span></span>  
  
    -   <span data-ttu-id="afba8-157">**List Price**</span><span class="sxs-lookup"><span data-stu-id="afba8-157">**List Price**</span></span>  
  
    -   <span data-ttu-id="afba8-158">**Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="afba8-158">**Standard Cost**</span></span>  
  
4.  <span data-ttu-id="afba8-159">Nella cella della proprietà **AttributeHierarchyDisplayFolder** del finestra Proprietà, digitare `Financial` .</span><span class="sxs-lookup"><span data-stu-id="afba8-159">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `Financial`.</span></span>  
  
     <span data-ttu-id="afba8-160">Questi attributi sono stati ora raggruppati in una seconda cartella di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="afba8-160">You have now grouped these attributes into a second display folder.</span></span>  
  
5.  <span data-ttu-id="afba8-161">Nel riquadro **Attributi** selezionare i seguenti attributi:</span><span class="sxs-lookup"><span data-stu-id="afba8-161">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="afba8-162">**Data di fine**</span><span class="sxs-lookup"><span data-stu-id="afba8-162">**End Date**</span></span>  
  
    -   <span data-ttu-id="afba8-163">**Data inizio**</span><span class="sxs-lookup"><span data-stu-id="afba8-163">**Start Date**</span></span>  
  
    -   <span data-ttu-id="afba8-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="afba8-164">**Status**</span></span>  
  
6.  <span data-ttu-id="afba8-165">Nella cella della proprietà **AttributeHierarchyDisplayFolder** del finestra Proprietà, digitare `History` .</span><span class="sxs-lookup"><span data-stu-id="afba8-165">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `History`.</span></span>  
  
     <span data-ttu-id="afba8-166">Questi attributi sono stati ora raggruppati in una terza cartella di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="afba8-166">You have now grouped these attributes into a third display folder.</span></span>  
  
7.  <span data-ttu-id="afba8-167">Selezionare la `Product Model Lines` gerarchia nel riquadro **gerarchie** , quindi modificare la proprietà **AllMemberName** nel finestra proprietà a `All Products` .</span><span class="sxs-lookup"><span data-stu-id="afba8-167">Select the `Product Model Lines` hierarchy in the **Hierarchies** pane, and then change the **AllMemberName** property in the Properties window to `All Products`.</span></span>  
  
8.  <span data-ttu-id="afba8-168">Fare clic su un'area aperta del riquadro **gerarchie** , quindi modificare la proprietà **AttributeAllMemberName** nella parte superiore del finestra proprietà a `All Products` .</span><span class="sxs-lookup"><span data-stu-id="afba8-168">Click an open area of the **Hierarchies** pane, and then change the **AttributeAllMemberName** property at the top of the Properties window to `All Products`.</span></span>  
  
     <span data-ttu-id="afba8-169">Facendo clic su un'area libera è possibile modificare le proprietà della dimensione Product stessa.</span><span class="sxs-lookup"><span data-stu-id="afba8-169">Clicking an open area lets you modify properties of the Product dimension itself.</span></span> <span data-ttu-id="afba8-170">È inoltre possibile fare clic su **Product** nella parte superiore dell'elenco di attributi nel riquadro **Attributi** .</span><span class="sxs-lookup"><span data-stu-id="afba8-170">You could also click **Product** at the top of the attributes list in the **Attributes** pane.</span></span>  
  
9. <span data-ttu-id="afba8-171">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="afba8-171">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="afba8-172">Definizione di relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="afba8-172">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="afba8-173">Se i dati sottostanti le supportano, è consigliabile definire relazioni tra gli attributi.</span><span class="sxs-lookup"><span data-stu-id="afba8-173">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="afba8-174">La definizione di relazioni tra attributi consente di velocizzare l'elaborazione di dimensioni, partizioni e query.</span><span class="sxs-lookup"><span data-stu-id="afba8-174">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="afba8-175">Per altre informazioni, vedere [Definire relazioni tra attributi](multidimensional-models/attribute-relationships-define.md) e [Relazioni tra attributi](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="afba8-175">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="afba8-176">Per definire relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="afba8-176">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="afba8-177">In **Progettazione dimensioni** per la dimensione Product fare clic sulla scheda **Relazioni tra attributi** .</span><span class="sxs-lookup"><span data-stu-id="afba8-177">In the **Dimension Designer** for the Product dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="afba8-178">Nel diagramma fare clic con il pulsante destro del mouse sull'attributo **Model Name** , quindi scegliere **Nuova relazione tra attributi**.</span><span class="sxs-lookup"><span data-stu-id="afba8-178">In the diagram, right-click the **Model Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="afba8-179">Nella finestra di dialogo **Crea relazione tra attributi** l'opzione **Attributo di origine** è impostata su **Model Name**.</span><span class="sxs-lookup"><span data-stu-id="afba8-179">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Model Name**.</span></span> <span data-ttu-id="afba8-180">Impostare **Attributo correlato** su **Product Line**.</span><span class="sxs-lookup"><span data-stu-id="afba8-180">Set the **Related Attribute** to **Product Line**.</span></span>  
  
     <span data-ttu-id="afba8-181">Nell'elenco **Tipo di relazione** lasciare il tipo di relazione impostato su **Flessibile** perché le relazioni tra i membri potrebbero cambiare nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="afba8-181">In the **Relationship type** list, leave the relationship type set to **Flexible** because relationships between the members might change over time.</span></span> <span data-ttu-id="afba8-182">Ad esempio, un modello di prodotto può essere spostato in una linea di prodotti diversa.</span><span class="sxs-lookup"><span data-stu-id="afba8-182">For example, a product model might eventually be moved to a different product line.</span></span>  
  
4.  <span data-ttu-id="afba8-183">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="afba8-183">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="afba8-184">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="afba8-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="reviewing-product-dimension-changes"></a><span data-ttu-id="afba8-185">Esame delle modifiche alla dimensione Product</span><span class="sxs-lookup"><span data-stu-id="afba8-185">Reviewing Product Dimension Changes</span></span>  
  
#### <a name="to-review-the-product-dimension-changes"></a><span data-ttu-id="afba8-186">Per esaminare le modifiche alla dimensione Product</span><span class="sxs-lookup"><span data-stu-id="afba8-186">To review the Product dimension changes</span></span>  
  
1.  <span data-ttu-id="afba8-187">Scegliere **Distribuisci Analysis Services Tutorial** dal menu [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]Compila **di**.</span><span class="sxs-lookup"><span data-stu-id="afba8-187">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="afba8-188">Dopo la visualizzazione del messaggio **Distribuzione completata** , fare clic sulla scheda **Esplorazione** di **Progettazione dimensioni** per la dimensione **Product** , quindi fare clic sul pulsante Riconnetti sulla barra degli strumenti della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="afba8-188">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the **Product** dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="afba8-189">Verificare che `Product Model Lines` sia selezionato nell'elenco **gerarchia** , quindi espandere `All Products` .</span><span class="sxs-lookup"><span data-stu-id="afba8-189">Verify that `Product Model Lines` is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>  
  
     <span data-ttu-id="afba8-190">Si noti che il nome del membro **totale** viene visualizzato come `All Products` .</span><span class="sxs-lookup"><span data-stu-id="afba8-190">Notice that the name of the **All** member appears as `All Products`.</span></span> <span data-ttu-id="afba8-191">Ciò è dovuto al fatto che la proprietà **AllMemberName** della gerarchia è stata modificata in `All Products` precedenza nella lezione.</span><span class="sxs-lookup"><span data-stu-id="afba8-191">This is because you changed the **AllMemberName** property for the hierarchy to `All Products` earlier in the lesson.</span></span> <span data-ttu-id="afba8-192">Inoltre, i membri del livello **Product Line** hanno ora nomi descrittivi anziché abbreviazioni costituite da una sola lettera.</span><span class="sxs-lookup"><span data-stu-id="afba8-192">Also, the members of the **Product Line** level now have user-friendly names, instead of single-letter abbreviations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="afba8-193">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="afba8-193">Next Task in Lesson</span></span>  
 [<span data-ttu-id="afba8-194">Modifica della dimensione Date</span><span class="sxs-lookup"><span data-stu-id="afba8-194">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="afba8-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afba8-195">See Also</span></span>  
 <span data-ttu-id="afba8-196">[Definire calcoli denominati in una vista origine dati &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="afba8-196">[Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span></span>  
 <span data-ttu-id="afba8-197">[Creazione di gerarchie definite dall'utente](multidimensional-models/user-defined-hierarchies-create.md) </span><span class="sxs-lookup"><span data-stu-id="afba8-197">[Create User-Defined Hierarchies](multidimensional-models/user-defined-hierarchies-create.md) </span></span>  
 [<span data-ttu-id="afba8-198">Configurare il livello &#40;Totale&#41; per le gerarchie di attributi</span><span class="sxs-lookup"><span data-stu-id="afba8-198">Configure the &#40;All&#41; Level for Attribute Hierarchies</span></span>](multidimensional-models/database-dimensions-configure-the-all-level-for-attribute-hierarchies.md)  
  
  
