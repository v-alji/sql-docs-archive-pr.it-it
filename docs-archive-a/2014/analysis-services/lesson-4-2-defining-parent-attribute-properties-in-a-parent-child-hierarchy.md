---
title: Definizione delle proprietà degli attributi padre in una gerarchia padre-figlio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d78fa73-a13b-4e12-bbd0-43e5307f760c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1dfa4340bdc161809cf3821e5cb1f0609399e1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630127"
---
# <a name="defining-parent-attribute-properties-in-a-parent-child-hierarchy"></a><span data-ttu-id="e6803-102">Definizione delle proprietà degli attributi padre in una gerarchia padre-figlio</span><span class="sxs-lookup"><span data-stu-id="e6803-102">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>
  <span data-ttu-id="e6803-103">Una gerarchia padre-figlio è una gerarchia in una dimensione basata su due colonne di tabella.</span><span class="sxs-lookup"><span data-stu-id="e6803-103">A parent-child hierarchy is a hierarchy in a dimension that is based on two table columns.</span></span> <span data-ttu-id="e6803-104">Nell'insieme, queste colonne definiscono le relazioni gerarchiche tra i membri della dimensione.</span><span class="sxs-lookup"><span data-stu-id="e6803-104">Together, these columns define the hierarchical relationships among the members of the dimension.</span></span> <span data-ttu-id="e6803-105">La prima colonna, denominata *colonna chiave membro*, identifica ogni membro della dimensione.</span><span class="sxs-lookup"><span data-stu-id="e6803-105">The first column, called the *member key column*, identifies each dimension member.</span></span> <span data-ttu-id="e6803-106">L'altra colonna, denominata *colonna padre*, identifica l'elemento padre di ogni membro della dimensione.</span><span class="sxs-lookup"><span data-stu-id="e6803-106">The other column, called the *parent column*, identifies the parent of each dimension member.</span></span> <span data-ttu-id="e6803-107">La proprietà **NamingTemplate** di un attributo padre consente di determinare il nome di ogni livello nella gerarchia padre-figlio e la proprietà **MembersWithData** consente di determinare se i dati del membro padre devono essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="e6803-107">The **NamingTemplate** property of a parent attribute determines the name of each level in the parent-child hierarchy, and the **MembersWithData** property determines whether data for parent members should be displayed.</span></span>

 <span data-ttu-id="e6803-108">Per ulteriori informazioni, vedere [gerarchia padre-figlio](multidimensional-models/parent-child-dimension.md), [attributi nelle gerarchie padre-figlio](multidimensional-models/parent-child-dimension-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="e6803-108">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md), [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>

> [!NOTE]
>  <span data-ttu-id="e6803-109">Quando si utilizza la Creazione guidata dimensione per creare una dimensione, vengono riconosciute le tabelle che presentano relazioni padre-figlio e viene definita automaticamente la gerarchia padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="e6803-109">When you use the Dimension Wizard to create a dimension, the wizard recognizes the tables that have parent-child relationships and automatically defines the parent-child hierarchy for you.</span></span>

 <span data-ttu-id="e6803-110">Questo argomento illustra le attività che consentono di creare un modello di denominazione con il quale definire il nome di ogni livello nella gerarchia padre-figlio della dimensione **Employee** .</span><span class="sxs-lookup"><span data-stu-id="e6803-110">In the tasks in this topic, you will create a naming template that defines the name for each level in the parent-child hierarchy in the **Employee** dimension.</span></span> <span data-ttu-id="e6803-111">L'attributo padre verrà quindi configurato per nascondere tutti i dati padre in modo da visualizzare solo le vendite dei membri al livello foglia.</span><span class="sxs-lookup"><span data-stu-id="e6803-111">You will then configure the parent attribute to hide all parent data, so that only the sales for leaf-level members are displayed.</span></span>

## <a name="browsing-the-employee-dimension"></a><span data-ttu-id="e6803-112">Visualizzazione della dimensione Employee</span><span class="sxs-lookup"><span data-stu-id="e6803-112">Browsing the Employee Dimension</span></span>

1.  <span data-ttu-id="e6803-113">In Esplora soluzioni fare doppio clic su **Employee.dim** nella cartella **Dimensioni** per aprire Progettazione dimensioni per la dimensione Employee.</span><span class="sxs-lookup"><span data-stu-id="e6803-113">In Solution Explorer, double-click **Employee.dim** in the **Dimensions** folder to open Dimension Designer for the Employee dimension.</span></span>

2.  <span data-ttu-id="e6803-114">Fare clic sulla scheda **Esplorazione** e verificare che **Employees** sia selezionato nell'elenco **Gerarchia** ed espandere il membro **All Employees** .</span><span class="sxs-lookup"><span data-stu-id="e6803-114">Click the **Browser** tab, verify that **Employees** is selected in the **Hierarchy** list, and then expand the **All Employees** member.</span></span>

     <span data-ttu-id="e6803-115">Si noti che **Ken J. Sánchez** è il responsabile principale in questa gerarchia padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="e6803-115">Notice that **Ken J. Sánchez** is the top-level manager in this parent-child hierarchy.</span></span>

3.  <span data-ttu-id="e6803-116">Selezionare il membro **Ken J. Sánchez** .</span><span class="sxs-lookup"><span data-stu-id="e6803-116">Select the **Ken J. Sánchez** member.</span></span>

     <span data-ttu-id="e6803-117">Si noti che il nome del livello di questo membro è **Livello 02**.</span><span class="sxs-lookup"><span data-stu-id="e6803-117">Notice that the level name for this member is **Level 02**.</span></span> <span data-ttu-id="e6803-118">Il nome del livello viene visualizzato dopo **Livello corrente:** immediatamente sopra il membro **All Employees** . Nell'attività successiva verranno definiti nomi più descrittivi per ogni livello.</span><span class="sxs-lookup"><span data-stu-id="e6803-118">(The level name appears after **Current level:** immediately above the **All Employees** member.) In the next task, you will define more descriptive names for each level.</span></span>

4.  <span data-ttu-id="e6803-119">Espandere **Ken J. Sánchez** per visualizzare i nomi dei dipendenti che fanno riferimento a questo responsabile e selezionare **Brian S. Welcker** per visualizzare il nome di questo livello.</span><span class="sxs-lookup"><span data-stu-id="e6803-119">Expand **Ken J. Sánchez** to view the names of the employees who report to this manager, and then select **Brian S. Welcker** to view the name of this level.</span></span>

     <span data-ttu-id="e6803-120">Si noti che il nome del livello di questo membro è **Livello 03**.</span><span class="sxs-lookup"><span data-stu-id="e6803-120">Notice that the level name for this member is **Level 03**.</span></span>

5.  <span data-ttu-id="e6803-121">In Esplora soluzioni fare doppio clic su **Analysis Services Tutorial.cube** nella cartella **Cubi** per aprire Progettazione cubi per il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="e6803-121">In Solution Explorer, double-click **Analysis Services Tutorial.cube** in the **Cubes** folder to open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>

6.  <span data-ttu-id="e6803-122">Fare clic sulla scheda **Esplorazione** .</span><span class="sxs-lookup"><span data-stu-id="e6803-122">Click the **Browser** tab.</span></span>

7.  <span data-ttu-id="e6803-123">Fare clic sull'icona Excel e selezionare **Abilita** quando richiesto per abilitare le connessioni.</span><span class="sxs-lookup"><span data-stu-id="e6803-123">Click the Excel icon, and then click **Enable** when prompted to enable connections.</span></span>

8.  <span data-ttu-id="e6803-124">Nell'elenco dei campi della tabella pivot espandere **Reseller Sales**.</span><span class="sxs-lookup"><span data-stu-id="e6803-124">In the PivotTable Field List, expand **Reseller Sales**.</span></span> <span data-ttu-id="e6803-125">Trascinare **Reseller Sales-Sales Amount** nell'area Valori.</span><span class="sxs-lookup"><span data-stu-id="e6803-125">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

9. <span data-ttu-id="e6803-126">Nell'elenco di campi della tabella pivot espandere **Employee**e trascinare la gerarchia **Employees** nell'area **Righe** .</span><span class="sxs-lookup"><span data-stu-id="e6803-126">In the PivotTable Field List, expand **Employee**, and then drag the **Employees** hierarchy to the **Rows** area.</span></span>

     <span data-ttu-id="e6803-127">Tutti i membri della gerarchia Employees verranno aggiunti alla colonna A del report di tabella pivot.</span><span class="sxs-lookup"><span data-stu-id="e6803-127">All the members of the Employees hierarchy are added to column A of the PivotTable report.</span></span>

     <span data-ttu-id="e6803-128">Nell'immagine seguente viene illustrata la gerarchia Employees espansa.</span><span class="sxs-lookup"><span data-stu-id="e6803-128">The following image shows the Employees hierarchy expanded.</span></span>

10. <span data-ttu-id="e6803-129">![Gerarchia Employees visualizzata in una tabella pivot](../../2014/tutorials/media/l4-employee-1.gif "Gerarchia Employees visualizzata in una tabella pivot")</span><span class="sxs-lookup"><span data-stu-id="e6803-129">![PivotTable showing Employees hierarchy](../../2014/tutorials/media/l4-employee-1.gif "PivotTable showing Employees hierarchy")</span></span>

     <span data-ttu-id="e6803-130">Si noti che le vendite di ogni responsabile nel Livello 03 vengono visualizzate anche nel Livello 04.</span><span class="sxs-lookup"><span data-stu-id="e6803-130">Notice that the sales made by each manager in Level 03 are also displayed in Level 04.</span></span> <span data-ttu-id="e6803-131">dal momento che ogni responsabile è anche un dipendente di altri responsabili.</span><span class="sxs-lookup"><span data-stu-id="e6803-131">This is because each manager is also an employee of another manager.</span></span> <span data-ttu-id="e6803-132">Nell'attività successiva gli importi delle vendite verranno nascosti.</span><span class="sxs-lookup"><span data-stu-id="e6803-132">In the next task, you will hide these sale amounts.</span></span>

## <a name="modifying-parent-attribute-properties-in-the-employee-dimension"></a><span data-ttu-id="e6803-133">Modifica delle proprietà degli attributi padre della dimensione Employee</span><span class="sxs-lookup"><span data-stu-id="e6803-133">Modifying Parent Attribute Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="e6803-134">Passare a Progettazione dimensioni per la dimensione **Employee** .</span><span class="sxs-lookup"><span data-stu-id="e6803-134">Switch to Dimension Designer for the **Employee** dimension.</span></span>

2.  <span data-ttu-id="e6803-135">Fare clic sulla scheda **Struttura dimensione** e selezionare la gerarchia dell'attributo **Employees** nel riquadro **Attributi** .</span><span class="sxs-lookup"><span data-stu-id="e6803-135">Click the **Dimension Structure** tab, and then select the **Employees** attribute hierarchy in the **Attributes** pane.</span></span>

     <span data-ttu-id="e6803-136">Si noti l'icona particolare dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="e6803-136">Notice the unique icon for this attribute.</span></span> <span data-ttu-id="e6803-137">Tale icona indica che l'attributo rappresenta la chiave del padre in una gerarchia padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="e6803-137">This icon signifies that the attribute is the parent key in a parent-child hierarchy.</span></span> <span data-ttu-id="e6803-138">Si noti anche che nella finestra Proprietà la proprietà **Usage** è definita come **Padre**.</span><span class="sxs-lookup"><span data-stu-id="e6803-138">Notice also, in the Properties window, that the **Usage** property for the attribute is defined as **Parent**.</span></span> <span data-ttu-id="e6803-139">Questa proprietà è stata impostata con la Creazione guidata dimensione durante la progettazione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="e6803-139">This property was set by the Dimension Wizard when the dimension was designed.</span></span> <span data-ttu-id="e6803-140">La procedura guidata ha rilevato automaticamente la relazione padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="e6803-140">The wizard automatically detected the parent-child relationship.</span></span>

3.  <span data-ttu-id="e6803-141">Nella finestra Proprietà fare clic sul pulsante con i puntini di sospensione (**...**) nella cella della proprietà **NamingTemplate** .</span><span class="sxs-lookup"><span data-stu-id="e6803-141">In the Properties window, click the ellipsis button (**...**) in the **NamingTemplate** property cell.</span></span>

     <span data-ttu-id="e6803-142">Nella finestra di dialogo **Modello denominazione livelli** viene definito il modello di denominazione dei livelli che consente di determinare i nomi dei livelli nella gerarchia padre-figlio visualizzati durante l'esplorazione dei cubi.</span><span class="sxs-lookup"><span data-stu-id="e6803-142">In the **Level Naming Template** dialog box, you define the level naming template that determines the level names in the parent-child hierarchy that are displayed to users as they browse cubes.</span></span>

4.  <span data-ttu-id="e6803-143">Nella seconda riga, la **\*** riga digitare \*\*Employee Level \* \*\* nella colonna **Name** , quindi fare clic sulla terza riga.</span><span class="sxs-lookup"><span data-stu-id="e6803-143">In the second row, the **\*** row, type **Employee Level \*** in the **Name** column, and then click the third row.</span></span>

     <span data-ttu-id="e6803-144">Si noti che alla voce **Risultato** ogni livello verrà denominato "Employee Level" seguito da un numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="e6803-144">Notice under **Result** that each level will now be named "Employee Level" followed by a sequentially increasing number.</span></span>

     <span data-ttu-id="e6803-145">La figura seguente illustrale modifiche apportate nella finestra di dialogo **Modello denominazione livelli** .</span><span class="sxs-lookup"><span data-stu-id="e6803-145">The following image shows the changes in the **Level Naming Template** dialog box.</span></span>

     <span data-ttu-id="e6803-146">![Finestra di dialogo Modello denominazione livelli](../../2014/tutorials/media/l4-namingtemplate.gif "Finestra di dialogo Modello denominazione livelli")</span><span class="sxs-lookup"><span data-stu-id="e6803-146">![Level Naming Template dialog box](../../2014/tutorials/media/l4-namingtemplate.gif "Level Naming Template dialog box")</span></span>

5.  <span data-ttu-id="e6803-147">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6803-147">Click **OK**.</span></span>

6.  <span data-ttu-id="e6803-148">Nella cella della proprietà **MembersWithData** della finestra Proprietà dell'attributo **Employees** selezionare **NonLeafDataHidden** per modificare questo valore per l'attributo **Employees** .</span><span class="sxs-lookup"><span data-stu-id="e6803-148">In the Properties window for the **Employees** attribute, in the **MembersWithData** property cell, select **NonLeafDataHidden** to change this value for the **Employees** attribute.</span></span>

     <span data-ttu-id="e6803-149">In questo modo i dati correlati ai membri non a livello foglia nella gerarchia padre-figlio verranno nascosti.</span><span class="sxs-lookup"><span data-stu-id="e6803-149">This will cause data that is related to non-leaf level members in the parent-child hierarchy to be hidden.</span></span>

## <a name="browsing-the-employee-dimension-with-the-modified-attributes"></a><span data-ttu-id="e6803-150">Visualizzazione della dimensione Employee con gli attributi modificati</span><span class="sxs-lookup"><span data-stu-id="e6803-150">Browsing the Employee Dimension with the Modified Attributes</span></span>

1.  <span data-ttu-id="e6803-151">Scegliere **Distribuisci Analysis Services Tutorial** dal menu [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]Compila **di**.</span><span class="sxs-lookup"><span data-stu-id="e6803-151">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="e6803-152">Dopo aver completato la distribuzione, passare a Progettazione cubi per il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial e fare clic sul pulsante **Riconnetti** sulla barra degli strumenti della scheda **Esplorazione** .</span><span class="sxs-lookup"><span data-stu-id="e6803-152">When deployment has successfully completed, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Reconnect** on the toolbar of the **Browser** tab.</span></span>

3.  <span data-ttu-id="e6803-153">Fare clic sull'icona di Excel, quindi su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="e6803-153">Click the Excel icon, and then click **Enable**.</span></span>

4.  <span data-ttu-id="e6803-154">Trascinare **Reseller Sales-Sales Amount** nell'area Valori.</span><span class="sxs-lookup"><span data-stu-id="e6803-154">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

5.  <span data-ttu-id="e6803-155">Trascinare la gerarchia **Employees** nell'area Etichette di riga.</span><span class="sxs-lookup"><span data-stu-id="e6803-155">Drag the **Employees** hierarchy to the Row Labels area.</span></span>

     <span data-ttu-id="e6803-156">Nella figura seguente vengono illustrate le modifiche apportate alla gerarchia Employee.</span><span class="sxs-lookup"><span data-stu-id="e6803-156">The following image shows the changes that you made to the Employees hierarchy.</span></span> <span data-ttu-id="e6803-157">Si noti che tephen Y. Jiang non viene più visualizzato come dipendente di se stesso.</span><span class="sxs-lookup"><span data-stu-id="e6803-157">Notice that Stephen Y. Jiang no longer appears as an employee of himself.</span></span>

     <span data-ttu-id="e6803-158">![Gerarchia Employees modificata](../../2014/tutorials/media/l4-employee-2.png "Gerarchia Employees modificata")</span><span class="sxs-lookup"><span data-stu-id="e6803-158">![Modified Employees hierarchy](../../2014/tutorials/media/l4-employee-2.png "Modified Employees hierarchy")</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="e6803-159">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="e6803-159">Next Task in Lesson</span></span>
 [<span data-ttu-id="e6803-160">Raggruppamento automatico dei membri degli attributi</span><span class="sxs-lookup"><span data-stu-id="e6803-160">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)

## <a name="see-also"></a><span data-ttu-id="e6803-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6803-161">See Also</span></span>
 <span data-ttu-id="e6803-162">Attributi della [gerarchia padre-figlio](multidimensional-models/parent-child-dimension.md) [nelle gerarchie padre-figlio](multidimensional-models/parent-child-dimension-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="e6803-162">[Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>


