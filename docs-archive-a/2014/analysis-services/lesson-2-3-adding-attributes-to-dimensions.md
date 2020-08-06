---
title: Aggiunta di attributi alle dimensioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80551dad-97ac-40d0-90af-b810780321ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76a04c42cc501fdca3e5ceb6481452052966796b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623534"
---
# <a name="adding-attributes-to-dimensions"></a><span data-ttu-id="29ae7-102">Aggiunta di attributi alle dimensioni</span><span class="sxs-lookup"><span data-stu-id="29ae7-102">Adding Attributes to Dimensions</span></span>
  <span data-ttu-id="29ae7-103">Dopo avere definito le dimensioni, è possibile popolarle con gli attributi che rappresentano ogni elemento dati nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="29ae7-103">Now that you have defined dimensions, you can populate them with attributes that represent each data element in the dimension.</span></span> <span data-ttu-id="29ae7-104">Gli attributi si basano in genere sui campi di una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="29ae7-104">Attributes are commonly based on fields from a data source view.</span></span> <span data-ttu-id="29ae7-105">Quando si aggiungono gli attributi a una dimensione, è possibile includere campi di qualsiasi tabella nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="29ae7-105">When adding attributes to a dimension, you can include fields from any table in the data source view.</span></span>  
  
 <span data-ttu-id="29ae7-106">In questa attività verrà utilizzato Progettazione dimensioni per aggiungere attributi alle dimensioni Customer e Product.</span><span class="sxs-lookup"><span data-stu-id="29ae7-106">In this task, you will use Dimension Designer to add attributes to the Customer and Product dimensions.</span></span> <span data-ttu-id="29ae7-107">La dimensione Customer includerà gli attributi basati sui campi delle tabelle Customer e Geography.</span><span class="sxs-lookup"><span data-stu-id="29ae7-107">The Customer dimension will include attributes based on fields from both the Customer and Geography tables.</span></span>  
  
## <a name="adding-attributes-to-the-customer-dimension"></a><span data-ttu-id="29ae7-108">Aggiunta di attributi alla dimensione Customer</span><span class="sxs-lookup"><span data-stu-id="29ae7-108">Adding Attributes to the Customer Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="29ae7-109">Per aggiungere attributi</span><span class="sxs-lookup"><span data-stu-id="29ae7-109">To add attributes</span></span>  
  
1.  <span data-ttu-id="29ae7-110">Aprire Progettazione dimensioni per la dimensione Customer.</span><span class="sxs-lookup"><span data-stu-id="29ae7-110">Open Dimension Designer for the Customer dimension.</span></span> <span data-ttu-id="29ae7-111">A tale scopo, fare doppio clic sulla dimensione **Customer** nel nodo **Dimensioni** di Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="29ae7-111">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="29ae7-112">Nel riquadro **Attributi** si notino gli attributi Customer Key e Geography Key creati con la Creazione guidata cubo.</span><span class="sxs-lookup"><span data-stu-id="29ae7-112">In the **Attributes** pane, notice the Customer Key and Geography Key attributes that were created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="29ae7-113">Sulla barra degli strumenti della scheda **Struttura dimensione** verificare che l'icona Zoom per la visualizzazione delle tabelle nel riquadro **Vista origine dati** sia impostata su 100%.</span><span class="sxs-lookup"><span data-stu-id="29ae7-113">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="29ae7-114">Trascinare le colonne seguenti dalla tabella **Customer** nel riquadro **Vista origine dati** al riquadro **Attributi** :</span><span class="sxs-lookup"><span data-stu-id="29ae7-114">Drag the following columns from the **Customer** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="29ae7-115">**BirthDate**</span><span class="sxs-lookup"><span data-stu-id="29ae7-115">**BirthDate**</span></span>  
  
    -   <span data-ttu-id="29ae7-116">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="29ae7-116">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="29ae7-117">**Sesso**</span><span class="sxs-lookup"><span data-stu-id="29ae7-117">**Gender**</span></span>  
  
    -   <span data-ttu-id="29ae7-118">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="29ae7-118">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="29ae7-119">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="29ae7-119">**YearlyIncome**</span></span>  
  
    -   <span data-ttu-id="29ae7-120">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="29ae7-120">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="29ae7-121">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="29ae7-121">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="29ae7-122">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="29ae7-122">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="29ae7-123">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="29ae7-123">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="29ae7-124">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="29ae7-124">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="29ae7-125">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="29ae7-125">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="29ae7-126">**Phone**</span><span class="sxs-lookup"><span data-stu-id="29ae7-126">**Phone**</span></span>  
  
    -   <span data-ttu-id="29ae7-127">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="29ae7-127">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="29ae7-128">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="29ae7-128">**CommuteDistance**</span></span>  
  
5.  <span data-ttu-id="29ae7-129">Trascinare le colonne seguenti dalla tabella **Geography** nel riquadro **Vista origine dati** al riquadro **Attributi** :</span><span class="sxs-lookup"><span data-stu-id="29ae7-129">Drag the following columns from the **Geography** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="29ae7-130">**Città**</span><span class="sxs-lookup"><span data-stu-id="29ae7-130">**City**</span></span>  
  
    -   <span data-ttu-id="29ae7-131">**StateProvinceName**</span><span class="sxs-lookup"><span data-stu-id="29ae7-131">**StateProvinceName**</span></span>  
  
    -   <span data-ttu-id="29ae7-132">**EnglishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="29ae7-132">**EnglishCountryRegionName**</span></span>  
  
    -   <span data-ttu-id="29ae7-133">**PostalCode**</span><span class="sxs-lookup"><span data-stu-id="29ae7-133">**PostalCode**</span></span>  
  
6.  <span data-ttu-id="29ae7-134">Scegliere Save All (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="29ae7-134">On the File menu, click **Save All**.</span></span>  
  
## <a name="adding-attributes-to-the-product-dimension"></a><span data-ttu-id="29ae7-135">Aggiunta di attributi alla dimensione Product</span><span class="sxs-lookup"><span data-stu-id="29ae7-135">Adding Attributes to the Product Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="29ae7-136">Per aggiungere attributi</span><span class="sxs-lookup"><span data-stu-id="29ae7-136">To add attributes</span></span>  
  
1.  <span data-ttu-id="29ae7-137">Aprire Progettazione dimensioni per la dimensione Product.</span><span class="sxs-lookup"><span data-stu-id="29ae7-137">Open Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="29ae7-138">Fare doppio clic sulla dimensione **Product** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="29ae7-138">Double-click the **Product** dimension in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="29ae7-139">Nel riquadro **Attributi** si noti l'attributo Product Key creato con la Creazione guidata cubo.</span><span class="sxs-lookup"><span data-stu-id="29ae7-139">In the **Attributes** pane, notice the Product Key attribute that was created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="29ae7-140">Sulla barra degli strumenti della scheda **Struttura dimensione** verificare che l'icona Zoom per la visualizzazione delle tabelle nel riquadro **Vista origine dati** sia impostata su 100%.</span><span class="sxs-lookup"><span data-stu-id="29ae7-140">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="29ae7-141">Trascinare le colonne seguenti dalla tabella **Product** nel riquadro **Vista origine dati** al riquadro **Attributi** :</span><span class="sxs-lookup"><span data-stu-id="29ae7-141">Drag the following columns from the **Product** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="29ae7-142">**StandardCost**</span><span class="sxs-lookup"><span data-stu-id="29ae7-142">**StandardCost**</span></span>  
  
    -   <span data-ttu-id="29ae7-143">**Colore**</span><span class="sxs-lookup"><span data-stu-id="29ae7-143">**Color**</span></span>  
  
    -   <span data-ttu-id="29ae7-144">**SafetyStockLevel**</span><span class="sxs-lookup"><span data-stu-id="29ae7-144">**SafetyStockLevel**</span></span>  
  
    -   <span data-ttu-id="29ae7-145">**ReorderPoint**</span><span class="sxs-lookup"><span data-stu-id="29ae7-145">**ReorderPoint**</span></span>  
  
    -   <span data-ttu-id="29ae7-146">**ListPrice**</span><span class="sxs-lookup"><span data-stu-id="29ae7-146">**ListPrice**</span></span>  
  
    -   <span data-ttu-id="29ae7-147">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="29ae7-147">**Size**</span></span>  
  
    -   <span data-ttu-id="29ae7-148">**SizeRange**</span><span class="sxs-lookup"><span data-stu-id="29ae7-148">**SizeRange**</span></span>  
  
    -   <span data-ttu-id="29ae7-149">**Weight**</span><span class="sxs-lookup"><span data-stu-id="29ae7-149">**Weight**</span></span>  
  
    -   <span data-ttu-id="29ae7-150">**DaysToManufacture**</span><span class="sxs-lookup"><span data-stu-id="29ae7-150">**DaysToManufacture**</span></span>  
  
    -   <span data-ttu-id="29ae7-151">**ProductLine**</span><span class="sxs-lookup"><span data-stu-id="29ae7-151">**ProductLine**</span></span>  
  
    -   <span data-ttu-id="29ae7-152">**DealerPrice**</span><span class="sxs-lookup"><span data-stu-id="29ae7-152">**DealerPrice**</span></span>  
  
    -   <span data-ttu-id="29ae7-153">**Class**</span><span class="sxs-lookup"><span data-stu-id="29ae7-153">**Class**</span></span>  
  
    -   <span data-ttu-id="29ae7-154">**Style**</span><span class="sxs-lookup"><span data-stu-id="29ae7-154">**Style**</span></span>  
  
    -   <span data-ttu-id="29ae7-155">**ModelName**</span><span class="sxs-lookup"><span data-stu-id="29ae7-155">**ModelName**</span></span>  
  
    -   <span data-ttu-id="29ae7-156">**StartDate**</span><span class="sxs-lookup"><span data-stu-id="29ae7-156">**StartDate**</span></span>  
  
    -   <span data-ttu-id="29ae7-157">**EndDate**</span><span class="sxs-lookup"><span data-stu-id="29ae7-157">**EndDate**</span></span>  
  
    -   <span data-ttu-id="29ae7-158">**Status**</span><span class="sxs-lookup"><span data-stu-id="29ae7-158">**Status**</span></span>  
  
5.  <span data-ttu-id="29ae7-159">Scegliere Save All (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="29ae7-159">On the File menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="29ae7-160">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="29ae7-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="29ae7-161">Esame delle proprietà del cubo e delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="29ae7-161">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="29ae7-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29ae7-162">See Also</span></span>  
 [<span data-ttu-id="29ae7-163">Riferimento alle proprietà degli attributo delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="29ae7-163">Dimension Attribute Properties Reference</span></span>](multidimensional-models/dimension-attribute-properties-reference.md)  
  
  
