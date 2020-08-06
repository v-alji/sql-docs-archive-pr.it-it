---
title: Modifica di misure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7bd48810-15ce-45ff-862b-372d08606995
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd352cbca1d21f5842e075d9cb8e5e766aa369b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635846"
---
# <a name="modifying-measures"></a><span data-ttu-id="74cb5-102">Modifica delle misure</span><span class="sxs-lookup"><span data-stu-id="74cb5-102">Modifying Measures</span></span>
  <span data-ttu-id="74cb5-103">È possibile usare la proprietà **FormatString** per definire impostazioni di formattazione che controllano la modalità di visualizzazione delle misure agli utenti.</span><span class="sxs-lookup"><span data-stu-id="74cb5-103">You can use the **FormatString** property to define formatting settings that control how measures are displayed to users.</span></span> <span data-ttu-id="74cb5-104">In questa attività vengono impostate le proprietà di formattazione per le misure di valuta e di percentuale nel cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="74cb5-104">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
### <a name="to-modify-the-measures-of-the-cube"></a><span data-ttu-id="74cb5-105">Per modificare le misure del cubo</span><span class="sxs-lookup"><span data-stu-id="74cb5-105">To modify the measures of the cube</span></span>  
  
1.  <span data-ttu-id="74cb5-106">Passare alla scheda **Struttura cubo** di Progettazione cubi per il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial, espandere il gruppo di misure **Internet Sales** nel riquadro **Misure** , fare clic con il pulsante destro del mouse su **Order Quantity**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="74cb5-106">Switch to the **Cube Structure** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, expand the **Internet Sales** measure group in the **Measures** pane, right-click **Order Quantity**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="74cb5-107">Nella finestra Proprietà fare clic sull'icona a forma di puntina da disegno **Nascondi automaticamente** per mantenere aperta la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="74cb5-107">In the Properties window, click the **Auto Hide** pushpin icon to pin the Properties window open.</span></span>  
  
     <span data-ttu-id="74cb5-108">Con la finestra Proprietà aperta risulta più agevole modificare le proprietà per diversi elementi nel cubo.</span><span class="sxs-lookup"><span data-stu-id="74cb5-108">It is easier to change properties for several items in the cube when the Properties window remains open.</span></span>  
  
3.  <span data-ttu-id="74cb5-109">Nella finestra Proprietà fare clic sull'elenco **FormatString** e quindi digitare **#,#**.</span><span class="sxs-lookup"><span data-stu-id="74cb5-109">In the Properties window, click the **FormatString** list, and then type **#,#**.</span></span>  
  
4.  <span data-ttu-id="74cb5-110">Sulla barra degli strumenti della scheda **Struttura cubo** fare clic sull'icona **Mostra griglie delle misure** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="74cb5-110">On the toolbar of the **Cube Structure** tab, click the **Show Measures Grid** icon on the left.</span></span>  
  
     <span data-ttu-id="74cb5-111">Nella visualizzazione griglia è possibile selezionare più misure contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="74cb5-111">The grid view lets you select multiple measures at the same time.</span></span>  
  
5.  <span data-ttu-id="74cb5-112">Selezionare le misure seguenti.</span><span class="sxs-lookup"><span data-stu-id="74cb5-112">Select the following measures.</span></span> <span data-ttu-id="74cb5-113">Per selezionare più misure, fare clic su ognuna di esse tenendo premuto CTRL:</span><span class="sxs-lookup"><span data-stu-id="74cb5-113">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="74cb5-114">**Unit Price**</span><span class="sxs-lookup"><span data-stu-id="74cb5-114">**Unit Price**</span></span>  
  
    -   <span data-ttu-id="74cb5-115">**Extended Amount**</span><span class="sxs-lookup"><span data-stu-id="74cb5-115">**Extended Amount**</span></span>  
  
    -   <span data-ttu-id="74cb5-116">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="74cb5-116">**Discount Amount**</span></span>  
  
    -   <span data-ttu-id="74cb5-117">**Product Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="74cb5-117">**Product Standard Cost**</span></span>  
  
    -   <span data-ttu-id="74cb5-118">**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="74cb5-118">**Total Product Cost**</span></span>  
  
    -   <span data-ttu-id="74cb5-119">**Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="74cb5-119">**Sales Amount**</span></span>  
  
    -   <span data-ttu-id="74cb5-120">**Tax Amt**</span><span class="sxs-lookup"><span data-stu-id="74cb5-120">**Tax Amt**</span></span>  
  
    -   <span data-ttu-id="74cb5-121">**Freight**</span><span class="sxs-lookup"><span data-stu-id="74cb5-121">**Freight**</span></span>  
  
6.  <span data-ttu-id="74cb5-122">Nell'elenco **FormatString** della finestra Proprietà selezionare **Currency**.</span><span class="sxs-lookup"><span data-stu-id="74cb5-122">In the Properties window, in the **FormatString** list, select **Currency**.</span></span>  
  
7.  <span data-ttu-id="74cb5-123">Nell'elenco a discesa nella parte superiore della finestra Proprietà sotto la barra del titolo selezionare la misura **Unit Price Discount Pct**, quindi selezionare **Percent** nell'elenco **FormatString** .</span><span class="sxs-lookup"><span data-stu-id="74cb5-123">In the drop-down list at the top of the Properties window (right below the title bar), select the measure **Unit Price Discount Pct**, and then select **Percent** in the **FormatString** list.</span></span>  
  
8.  <span data-ttu-id="74cb5-124">Nella Finestra Proprietà modificare la proprietà **Name** per la misura **Unit Price Discount Pct** in `Unit Price Discount Percentage` .</span><span class="sxs-lookup"><span data-stu-id="74cb5-124">In the Properties window, change the **Name** property for the **Unit Price Discount Pct** measure to `Unit Price Discount Percentage`.</span></span>  
  
9. <span data-ttu-id="74cb5-125">Nel riquadro **misure** fare clic su **Tax Amt** e modificare il nome della misura in `Tax Amount` .</span><span class="sxs-lookup"><span data-stu-id="74cb5-125">In the **Measures** pane, click **Tax Amt** and change the name of this measure to `Tax Amount`.</span></span>  
  
10. <span data-ttu-id="74cb5-126">Nella finestra Proprietà fare clic sull'icona **Nascondi automaticamente** per nascondere la finestra Proprietà, quindi fare clic su **Mostra albero delle misure** sulla barra degli strumenti della scheda **Struttura cubo** .</span><span class="sxs-lookup"><span data-stu-id="74cb5-126">In the Properties window, click the **Auto Hide** icon to hide the Properties window, and then click **Show Measures Tree** on the toolbar of the **Cube Structure** tab.</span></span>  
  
11. <span data-ttu-id="74cb5-127">Scegliere **Save All** (Salva tutti) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="74cb5-127">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="74cb5-128">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="74cb5-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="74cb5-129">Modifica della dimensione Customer</span><span class="sxs-lookup"><span data-stu-id="74cb5-129">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="74cb5-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74cb5-130">See Also</span></span>  
 <span data-ttu-id="74cb5-131">[Definire le dimensioni del database](multidimensional-models/define-database-dimensions.md) </span><span class="sxs-lookup"><span data-stu-id="74cb5-131">[Define Database Dimensions](multidimensional-models/define-database-dimensions.md) </span></span>  
 [<span data-ttu-id="74cb5-132">Configurare le proprietà delle misure</span><span class="sxs-lookup"><span data-stu-id="74cb5-132">Configure Measure Properties</span></span>](multidimensional-models/configure-measure-properties.md)  
  
  
