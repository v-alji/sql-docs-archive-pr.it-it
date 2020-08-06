---
title: Definizione di una dimensione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 112696db-3838-4b50-91bd-d2ce5fa04ee5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2eb7a695ffc2c0588396a4a9ea655983c26cc719
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623538"
---
# <a name="defining-a-dimension"></a><span data-ttu-id="b9bc7-102">Definizione di una dimensione</span><span class="sxs-lookup"><span data-stu-id="b9bc7-102">Defining a Dimension</span></span>
  <span data-ttu-id="b9bc7-103">Nell'attività seguente si utilizzerà la Creazione guidata dimensione per compilare una dimensione Date.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-103">In the following task, you will use the Dimension Wizard to build a Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9bc7-104">Per questa lezione è necessario aver completato tutte le procedure nella lezione 1.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-104">This lesson requires that you have completed all the procedures in Lesson 1.</span></span>  
  
### <a name="to-define-a-dimension"></a><span data-ttu-id="b9bc7-105">Per definire una dimensione</span><span class="sxs-lookup"><span data-stu-id="b9bc7-105">To define a dimension</span></span>  
  
1.  <span data-ttu-id="b9bc7-106">In Esplora soluzioni, a destra di Microsoft Visual Studio, fare clic con il pulsante destro del mouse su **Dimensioni**e scegliere **Nuova dimensione**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-106">In Solution Explorer (on the right side of Microsoft Visual Studio), right-click **Dimensions**, and then click **New Dimension**.</span></span> <span data-ttu-id="b9bc7-107">Verrà visualizzata la Creazione guidata dimensione.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-107">The Dimension Wizard appears.</span></span>  
  
2.  <span data-ttu-id="b9bc7-108">Nella pagina iniziale di **Creazione guidata dimensione** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-108">On the **Welcome to the Dimension Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="b9bc7-109">Nella pagina **Selezione metodo di creazione** verificare che la pagina **Usa una tabella esistente** sia selezionata e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-109">On the **Select Creation Method** page, verify that the **Use an existing table** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="b9bc7-110">Nella pagina **Impostazione informazioni origine** verificare che sia selezionata la vista origine dati **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="b9bc7-110">On the **Specify Source Information** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="b9bc7-111">Nell'elenco **Tabella principale** selezionare **Data**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-111">In the **Main table** list, select **Date**.</span></span>  
  
6.  <span data-ttu-id="b9bc7-112">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-112">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="b9bc7-113">Nella pagina **Selezione attributi dimensione** selezionare le caselle di controllo accanto agli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9bc7-113">On the **Select Dimension Attributes** page, select the check boxes next to the following attributes:</span></span>  
  
    -   <span data-ttu-id="b9bc7-114">**Date Key**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-114">**Date Key**</span></span>  
  
    -   <span data-ttu-id="b9bc7-115">**Full Date Alternate Key**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-115">**Full Date Alternate Key**</span></span>  
  
    -   <span data-ttu-id="b9bc7-116">**English Month Name**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-116">**English Month Name**</span></span>  
  
    -   <span data-ttu-id="b9bc7-117">**Trimestre di calendario**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-117">**Calendar Quarter**</span></span>  
  
    -   <span data-ttu-id="b9bc7-118">**Anno di calendario**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-118">**Calendar Year**</span></span>  
  
    -   <span data-ttu-id="b9bc7-119">**Calendar Semester**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-119">**Calendar Semester**</span></span>  
  
8.  <span data-ttu-id="b9bc7-120">Modificare l'impostazione della colonna **Tipo attributo** per l'attributo **Full Date Alternate Key** da **Regolare** a **Data**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-120">Change the setting of the **Full Date Alternate Key** attribute's **Attribute Type** column from **Regular** to **Date**.</span></span> <span data-ttu-id="b9bc7-121">A tale scopo, fare clic su **Regolare** nella colonna **Tipo attributo** .</span><span class="sxs-lookup"><span data-stu-id="b9bc7-121">To do this, click **Regular** in the **Attribute Type** column.</span></span> <span data-ttu-id="b9bc7-122">Fare quindi clic sulla freccia per espandere le opzioni.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-122">Then click the arrow to expand the options.</span></span> <span data-ttu-id="b9bc7-123">Quindi, fare clic su **date**  >  **Calendar**  >  **date**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-123">Next, click **Date** > **Calendar** > **Date**.</span></span> <span data-ttu-id="b9bc7-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-124">Click **OK**.</span></span> <span data-ttu-id="b9bc7-125">Ripetere questi passaggi per modificare il tipo di attributo per gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9bc7-125">Repeat these steps to change the attribute type of the attributes as follows:</span></span>  
  
    -   <span data-ttu-id="b9bc7-126">**English Month Name** in **Mese**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-126">**English Month Name** to **Month**</span></span>  
  
    -   <span data-ttu-id="b9bc7-127">**Calendar Quarter** in **Trimestre**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-127">**Calendar Quarter** to **Quarter**</span></span>  
  
    -   <span data-ttu-id="b9bc7-128">**Calendar Year** in **Anno**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-128">**Calendar Year** to **Year**</span></span>  
  
    -   <span data-ttu-id="b9bc7-129">**Calendar Semester** in **Semestre**</span><span class="sxs-lookup"><span data-stu-id="b9bc7-129">**Calendar Semester** to **Half Year**</span></span>  
  
9. <span data-ttu-id="b9bc7-130">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-130">Click **Next**.</span></span>  
  
10. <span data-ttu-id="b9bc7-131">Nel riquadro Anteprima della pagina **Completamento procedura guidata** è possibile visualizzare la dimensione **Date** e i relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-131">On the **Completing the Wizard** page, in the Preview pane, you can see the **Date** dimension and its attributes.</span></span>  
  
11. <span data-ttu-id="b9bc7-132">Fare clic su **Fine** per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-132">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="b9bc7-133">In Esplora soluzioni nel progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial la dimensione Date viene visualizzata nella cartella **Dimensioni** .</span><span class="sxs-lookup"><span data-stu-id="b9bc7-133">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the Date dimension appears in the **Dimensions** folder.</span></span> <span data-ttu-id="b9bc7-134">Al centro dell'ambiente di sviluppo, in Progettazione dimensioni viene visualizzata la dimensione Date.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-134">In the center of the development environment, Dimension Designer displays the Date dimension.</span></span>  
  
12. <span data-ttu-id="b9bc7-135">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="b9bc7-135">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b9bc7-136">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="b9bc7-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b9bc7-137">Definizione di un cubo</span><span class="sxs-lookup"><span data-stu-id="b9bc7-137">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="b9bc7-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9bc7-138">See Also</span></span>  
 <span data-ttu-id="b9bc7-139">[Dimensioni nei modelli multidimensionali](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b9bc7-139">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="b9bc7-140">[Creare una dimensione utilizzando una tabella esistente](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="b9bc7-140">[Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="b9bc7-141">Creare una dimensione utilizzando la Creazione guidata dimensione</span><span class="sxs-lookup"><span data-stu-id="b9bc7-141">Create a Dimension Using the Dimension Wizard</span></span>](multidimensional-models/create-a-dimension-using-the-dimension-wizard.md)  
  
  
