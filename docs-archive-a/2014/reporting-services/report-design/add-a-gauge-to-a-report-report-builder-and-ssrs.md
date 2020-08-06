---
title: Aggiungere un misuratore a un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 45da4fef-2b02-40e1-977c-f8f80d87155e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7125080d95e9c7b882df8d715cce5c6cf8aa6344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722567"
---
# <a name="add-a-gauge-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="cafa9-102">Aggiungere un misuratore a un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="cafa9-102">Add a Gauge to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cafa9-103">Se si desidera riepilogare i dati in formato visivo, è possibile utilizzare un'area dati Misuratore.</span><span class="sxs-lookup"><span data-stu-id="cafa9-103">When you want to summarize data in a visual format, you can use a Gauge data region.</span></span> <span data-ttu-id="cafa9-104">Dopo aver aggiunto tale area dati all'area di progettazione, è possibile trascinare i campi del set di dati del report in un riquadro dei dati nel misuratore.</span><span class="sxs-lookup"><span data-stu-id="cafa9-104">After you add a Gauge data region to the design surface, you can drag report dataset fields to a data pane on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-gauge-to-your-report"></a><span data-ttu-id="cafa9-105">Per aggiungere un misuratore al report</span><span class="sxs-lookup"><span data-stu-id="cafa9-105">To add a gauge to your report</span></span>  
  
1.  <span data-ttu-id="cafa9-106">Creare un report o aprirne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="cafa9-106">Create a report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="cafa9-107">Nella scheda Inserisci fare doppio clic su misuratore.</span><span class="sxs-lookup"><span data-stu-id="cafa9-107">On the Insert tab, double-click Gauge.</span></span> <span data-ttu-id="cafa9-108">Verrà visualizzata la finestra di dialogo **Seleziona tipo di misuratore** .</span><span class="sxs-lookup"><span data-stu-id="cafa9-108">The **Select Gauge Type** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="cafa9-109">Selezionare il tipo di misuratore da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="cafa9-109">Select the type of gauge you want to add.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="cafa9-110">A differenza del grafico, il misuratore è solo di due tipi: lineare e radiale.</span><span class="sxs-lookup"><span data-stu-id="cafa9-110">Unlike Chart, Gauge has only two types: linear and radial.</span></span> <span data-ttu-id="cafa9-111">I misuratori disponibili nella finestra di dialogo **Seleziona tipo di misuratore** rappresentano i modelli per questi due tipi di misuratore.</span><span class="sxs-lookup"><span data-stu-id="cafa9-111">The available gauges in the **Select a Gauge Type** dialog box are templates for these two types of gauges.</span></span> <span data-ttu-id="cafa9-112">Per questo motivo, dopo aver aggiunto il misuratore al report non è possibile modificarne il tipo.</span><span class="sxs-lookup"><span data-stu-id="cafa9-112">For this reason, you cannot change the gauge type after you add the gauge to your report.</span></span> <span data-ttu-id="cafa9-113">Per farlo, è necessario eliminare il misuratore e aggiungerlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="cafa9-113">You must delete and re-add a gauge to change its type.</span></span>  
  
     <span data-ttu-id="cafa9-114">Se al report non sono associati un'origine dati e un set di dati, viene visualizzata la finestra di dialogo **Proprietà origine dati** che consente di eseguire in modo guidato la procedura per creare entrambi.</span><span class="sxs-lookup"><span data-stu-id="cafa9-114">If the report has no data source and dataset the **Data Source Properties** dialog box opens and takes you through the steps to create both.</span></span> <span data-ttu-id="cafa9-115">Per ulteriori informazioni, vedere [aggiungere e verificare una connessione dati o un'origine dati &#40;Generatore report e SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cafa9-115">For more information see, [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="cafa9-116">Se il report ha un'origine dati, ma non un set di dati, viene visualizzata la finestra di dialogo **Proprietà origine dati** in cui sono descritti i passaggi necessari per la creazione.</span><span class="sxs-lookup"><span data-stu-id="cafa9-116">If the report has a data source, but no dataset the **Dataset Properties** dialog box opens and takes you through the steps to create one.</span></span> <span data-ttu-id="cafa9-117">Per altre informazioni, vedere [Creare un set di dati condiviso o un set di dati incorporato &#40;Generatore report e SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cafa9-117">For more information, see [Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span></span>  
  
4.  <span data-ttu-id="cafa9-118">Fare clic sul misuratore per visualizzare il riquadro dei dati.</span><span class="sxs-lookup"><span data-stu-id="cafa9-118">Click the gauge to display the data pane.</span></span> <span data-ttu-id="cafa9-119">Per impostazione predefinita, un misuratore dispone di un solo indicatore di misura corrispondente a un unico valore.</span><span class="sxs-lookup"><span data-stu-id="cafa9-119">By default, a gauge has one pointer corresponding to one value.</span></span> <span data-ttu-id="cafa9-120">È tuttavia possibile aggiungere altri indicatori di misura.</span><span class="sxs-lookup"><span data-stu-id="cafa9-120">You can add additional pointers.</span></span>  
  
5.  <span data-ttu-id="cafa9-121">Aggiungere un campo del set di dati all'area di rilascio del campo dati.</span><span class="sxs-lookup"><span data-stu-id="cafa9-121">Add one field from the dataset to the data field drop-zone.</span></span> <span data-ttu-id="cafa9-122">È possibile aggiungere un campo soltanto.</span><span class="sxs-lookup"><span data-stu-id="cafa9-122">You can add only one field.</span></span> <span data-ttu-id="cafa9-123">Se si desidera visualizzare più campi, è necessario aggiungere indicatori di misura aggiuntivi, uno per ogni campo.</span><span class="sxs-lookup"><span data-stu-id="cafa9-123">If you want to display multiple fields, you must add additional pointers, one for each field.</span></span>  
  
     <span data-ttu-id="cafa9-124">Fare clic con il pulsante destro del mouse sulla scala del misuratore e scegliere **Proprietà scala**.</span><span class="sxs-lookup"><span data-stu-id="cafa9-124">Right-click the gauge scale, and select **Scale Properties**.</span></span> <span data-ttu-id="cafa9-125">Digitare un valore per le opzioni **Minimo** e **Massimo** della scala.</span><span class="sxs-lookup"><span data-stu-id="cafa9-125">Type a value for the **Minimum** and **Maximum** of the scale.</span></span> <span data-ttu-id="cafa9-126">Per altre informazioni, vedere [Impostare un valore minimo o massimo su un misuratore &#40;Generatore report e SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cafa9-126">For more information, see [Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafa9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cafa9-127">See Also</span></span>  
 <span data-ttu-id="cafa9-128">[Aree dati annidate &#40;Generatore report e SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cafa9-128">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="cafa9-129">Misuratori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cafa9-129">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
