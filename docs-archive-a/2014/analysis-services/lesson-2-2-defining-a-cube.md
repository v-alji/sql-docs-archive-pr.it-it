---
title: Definizione di un cubo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8aa4ac2d-857f-4048-baa0-0f314e207cf6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 354a05840dd2e091f956454858edd5c75c8c4bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623536"
---
# <a name="defining-a-cube"></a><span data-ttu-id="bbf19-102">Definizione di un cubo</span><span class="sxs-lookup"><span data-stu-id="bbf19-102">Defining a Cube</span></span>
  <span data-ttu-id="bbf19-103">La Creazione guidata cubo consente di definire i gruppi di misure e le dimensioni per un cubo.</span><span class="sxs-lookup"><span data-stu-id="bbf19-103">The Cube Wizard helps you define the measure groups and dimensions for a cube.</span></span> <span data-ttu-id="bbf19-104">Nell'attività seguente si utilizzerà la Creazione guidata cubo per compilare un cubo.</span><span class="sxs-lookup"><span data-stu-id="bbf19-104">In the following task, you will use the Cube Wizard to build a cube.</span></span>  
  
### <a name="to-define-a-cube-and-its-properties"></a><span data-ttu-id="bbf19-105">Per definire un cubo e le relative proprietà</span><span class="sxs-lookup"><span data-stu-id="bbf19-105">To define a cube and its properties</span></span>  
  
1.  <span data-ttu-id="bbf19-106">In Esplora soluzioni fare clic con il pulsante destro del mouse su **Cubi**e quindi scegliere **Nuovo cubo**.</span><span class="sxs-lookup"><span data-stu-id="bbf19-106">In Solution Explorer, right-click **Cubes**, and then click **New Cube**.</span></span> <span data-ttu-id="bbf19-107">Verrà visualizzata la Creazione guidata cubo.</span><span class="sxs-lookup"><span data-stu-id="bbf19-107">The Cube Wizard appears.</span></span>  
  
2.  <span data-ttu-id="bbf19-108">Nella pagina **Creazione guidata cubo** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbf19-108">On the **Welcome to the Cube Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="bbf19-109">Nella pagina **Selezione metodo di creazione** verificare che l'opzione **Usa tabelle esistenti** sia selezionata, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbf19-109">On the **Select Creation Method** page, verify that the **Use existing tables** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="bbf19-110">Nella pagina **Selezione tabelle del gruppo di misure** verificare che la vista origine dati **Adventure Works DW 2012** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="bbf19-110">On the **Select Measure Group Tables** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="bbf19-111">Fare clic su **Suggerisci** per visualizzare le tabelle consigliate per la creazione di gruppi di misure.</span><span class="sxs-lookup"><span data-stu-id="bbf19-111">Click **Suggest** to have the cube wizard suggest tables to use to create measure groups.</span></span>  
  
     <span data-ttu-id="bbf19-112">Nel corso della procedura guidata vengono esaminate le tabelle e viene suggerita **InternetSales** come tabella del gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="bbf19-112">The wizard examines the tables and suggests **InternetSales** as a measure group table.</span></span> <span data-ttu-id="bbf19-113">Le tabelle del gruppo di misure, anche dette tabelle dei fatti, contengono le misure a cui si è interessati, ad esempio il numero di unità vendute.</span><span class="sxs-lookup"><span data-stu-id="bbf19-113">Measure group tables, also called fact tables, contain the measures you are interested in, such as the number of units sold.</span></span>  
  
6.  <span data-ttu-id="bbf19-114">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbf19-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="bbf19-115">Nella pagina **Selezione misure** esaminare le misure selezionate nel gruppo di misure **Internet Sales** , quindi deselezionare le caselle di controllo per le misure seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbf19-115">On the **Select Measures** page, review the selected measures in the **Internet Sales** measure group, and then clear the check boxes for the following measures:</span></span>  
  
    -   <span data-ttu-id="bbf19-116">**Promotion Key**</span><span class="sxs-lookup"><span data-stu-id="bbf19-116">**Promotion Key**</span></span>  
  
    -   <span data-ttu-id="bbf19-117">**Currency Key**</span><span class="sxs-lookup"><span data-stu-id="bbf19-117">**Currency Key**</span></span>  
  
    -   <span data-ttu-id="bbf19-118">**Sales Territory Key**</span><span class="sxs-lookup"><span data-stu-id="bbf19-118">**Sales Territory Key**</span></span>  
  
    -   <span data-ttu-id="bbf19-119">**Revision Number**</span><span class="sxs-lookup"><span data-stu-id="bbf19-119">**Revision Number**</span></span>  
  
     <span data-ttu-id="bbf19-120">Per impostazione predefinita, la procedura guidata seleziona come misure tutte le colonne numeriche della tabella dei fatti che non sono collegate a dimensioni.</span><span class="sxs-lookup"><span data-stu-id="bbf19-120">By default, the wizard selects as measures all numeric columns in the fact table that are not linked to dimensions.</span></span> <span data-ttu-id="bbf19-121">Tuttavia, queste quattro colonne non sono effettive misure.</span><span class="sxs-lookup"><span data-stu-id="bbf19-121">However, these four columns are not actual measures.</span></span> <span data-ttu-id="bbf19-122">Le prime tre sono valori chiave che collegano la tabella dei fatti alle tabelle delle dimensioni che non sono utilizzate nella versione iniziale di questo cubo.</span><span class="sxs-lookup"><span data-stu-id="bbf19-122">The first three are key values that link the fact table with dimension tables that are not used in the initial version of this cube.</span></span>  
  
8.  <span data-ttu-id="bbf19-123">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbf19-123">Click **Next**.</span></span>  
  
9. <span data-ttu-id="bbf19-124">Nella pagina **Selezione dimensioni esistenti** assicurarsi che la dimensione **Date** creata in precedenza sia selezionata, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbf19-124">On the **Select Existing Dimensions** page, make sure the **Date** dimension that you created earlier is selected, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="bbf19-125">Nella pagina **Seleziona nuove dimensioni** selezionare le nuove dimensioni da creare.</span><span class="sxs-lookup"><span data-stu-id="bbf19-125">On the **Select New Dimensions** page, select the new dimensions to be created.</span></span> <span data-ttu-id="bbf19-126">A tale scopo, verificare che le caselle di controllo **Customer**, **Geography**e **Product** siano selezionate, quindi deselezionare la casella di controllo **InternetSales** .</span><span class="sxs-lookup"><span data-stu-id="bbf19-126">To do this, verify that the **Customer**, **Geography**, and **Product** check boxes are selected, and then clear the **InternetSales** check box.</span></span>  
  
11. <span data-ttu-id="bbf19-127">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbf19-127">Click **Next**.</span></span>  
  
12. <span data-ttu-id="bbf19-128">Nella pagina **Completamento procedura guidata** modificare il nome del cubo in `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="bbf19-128">On the **Completing the Wizard** page, change the name of the cube to `Analysis Services Tutorial`.</span></span> <span data-ttu-id="bbf19-129">Nel riquadro Anteprima è possibile visualizzare il gruppo di misure **InternetSales** e le relative misure.</span><span class="sxs-lookup"><span data-stu-id="bbf19-129">In the Preview pane, you can see the **InternetSales** measure group and its measures.</span></span> <span data-ttu-id="bbf19-130">È inoltre possibile visualizzare le dimensioni **Date**, **Customer** e **Product** .</span><span class="sxs-lookup"><span data-stu-id="bbf19-130">You can also see the **Date**, **Customer,** and **Product** dimensions.</span></span>  
  
13. <span data-ttu-id="bbf19-131">Fare clic su **Fine** per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="bbf19-131">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="bbf19-132">In Esplora soluzioni, nel progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial viene visualizzato nella cartella **Cubi** e le dimensioni del database Customer e Product vengono visualizzate nella cartella **Dimensions** .</span><span class="sxs-lookup"><span data-stu-id="bbf19-132">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube appears in the **Cubes** folder, and the Customer and Product database dimensions appear in the **Dimensions** folder.</span></span> <span data-ttu-id="bbf19-133">Il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial viene inoltre visualizzato al centro dell'ambiente di sviluppo nella scheda Struttura cubo.</span><span class="sxs-lookup"><span data-stu-id="bbf19-133">Additionally, in the center of the development environment, the Cube Structure tab displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
14. <span data-ttu-id="bbf19-134">Sulla barra degli strumenti della scheda Struttura cubo modificare il livello di **Zoom** portandolo al 50% in modo da poter visualizzare più agevolmente le dimensioni e le tabelle dei fatti del cubo.</span><span class="sxs-lookup"><span data-stu-id="bbf19-134">On the toolbar of the Cube Structure tab, change the **Zoom** level to 50 percent, so that you can more easily see the dimensions and fact tables in the cube.</span></span> <span data-ttu-id="bbf19-135">Si noti che la tabella dei fatti è gialla e le tabelle delle dimensioni sono blu.</span><span class="sxs-lookup"><span data-stu-id="bbf19-135">Notice that the fact table is yellow and the dimension tables are blue.</span></span>  
  
15. <span data-ttu-id="bbf19-136">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="bbf19-136">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="bbf19-137">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="bbf19-137">Next Task in Lesson</span></span>  
 [<span data-ttu-id="bbf19-138">Aggiunta di attributi alle dimensioni</span><span class="sxs-lookup"><span data-stu-id="bbf19-138">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
  
## <a name="see-also"></a><span data-ttu-id="bbf19-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbf19-139">See Also</span></span>  
 <span data-ttu-id="bbf19-140">[Cubi nei modelli multidimensionali](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="bbf19-140">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="bbf19-141">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="bbf19-141">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
