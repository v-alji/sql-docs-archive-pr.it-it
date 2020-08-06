---
title: Aggiungere o eliminare un indicatore (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8b1aac1-53ef-47a4-afc0-8fa866c6c480
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 186ed4f5b6cf7cb239dc7c33a11089c11bccae14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719601"
---
# <a name="add-or-delete-an-indicator-report-builder-and-ssrs"></a><span data-ttu-id="0a5f3-102">Aggiungere o eliminare un indicatore (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="0a5f3-102">Add or Delete an Indicator (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0a5f3-103">Gli indicatori sono piccoli misuratori sui quali è possibile leggere immediatamente lo stato di un singolo valore di dati.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-103">Indicators are minimal gauges that convey the state of a single data value at a glance.</span></span> <span data-ttu-id="0a5f3-104">Per altre informazioni in merito, vedere [Indicatori &#40;Generatore report e SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a5f3-104">For more information about them, see [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="0a5f3-105">Gli indicatori sono posizionati comunemente nelle celle di una tabella o di una matrice, ma possono essere utilizzati anche separatamente, affiancati ai misuratori o incorporati nei misuratori.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-105">Indicators are commonly placed in cells in a table or matrix, but you can also use indicators by themselves, side-by-side with gauges, or embedded in gauges.</span></span>  
  
 <span data-ttu-id="0a5f3-106">Quando si aggiunge un indicatore per la prima volta, viene configurato per impostazione predefinita in modo da utilizzare le percentuali come unità di misura.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-106">When you first add an indicator, it is by default configured to use percentages as measurement units.</span></span> <span data-ttu-id="0a5f3-107">Gli intervalli delle percentuali sono distribuiti uniformemente tra i membri del set di indicatori e l'ambito di valori mostrati dall'indicatore rappresenta l'elemento padre dell'indicatore, ad esempio una tabella o una matrice.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-107">The percentage ranges are evenly distributed across members of the indicator set, and the scope of values shown by the indicator is the parent of the indicator such as a table or matrix.</span></span>  
  
 <span data-ttu-id="0a5f3-108">È possibile aggiornare i valori e gli stati di indicatori.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-108">You can update the values and states of indicators.</span></span> <span data-ttu-id="0a5f3-109">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a5f3-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="0a5f3-110">Modificare le icone degli indicatori e dei set di indicatori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0a5f3-110">Change Indicator Icons and Indicator Sets &#40;Report Builder and SSRS&#41;</span></span>](change-indicator-icons-and-indicator-sets-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="0a5f3-111">Impostare e configurare le unità di misura &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0a5f3-111">Set and Configure Measurement Units &#40;Report Builder and SSRS&#41;</span></span>](set-and-configure-measurement-units-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="0a5f3-112">Impostare l'ambito di sincronizzazione &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0a5f3-112">Set Synchronization Scope &#40;Report Builder and SSRS&#41;</span></span>](set-synchronization-scope-report-builder-and-ssrs.md)  
  
 <span data-ttu-id="0a5f3-113">Poiché un indicatore viene posizionato nel pannello del misuratore, è necessario selezionare l'indicatore anziché il pannello quando si vuole configurare l'indicatore tramite la finestra di dialogo **Proprietà indicatori** o il riquadro **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="0a5f3-113">Because an indicator is positioned inside the gauge panel, you need to select the indicator instead of the panel when you want to configure the indicator by using the **Indicators Properties** dialog box or the **Properties** pane.</span></span> <span data-ttu-id="0a5f3-114">Nell'immagine seguente viene mostrato un indicatore selezionato nel relativo pannello del misuratore.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-114">The following picture shows a selected indicator in its gauge panel.</span></span>  
  
 <span data-ttu-id="0a5f3-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span><span class="sxs-lookup"><span data-stu-id="0a5f3-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a5f3-116">A seconda della larghezza della colonna e della lunghezza dei valori di dati, il testo nella tabella o nelle celle della matrice potrebbe essere sottoposto a wrapping ed essere quindi visualizzato su più righe.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-116">Depending on column width and the length of data values, the text in table or matrix cells might wrap and display text on multiple lines.</span></span> <span data-ttu-id="0a5f3-117">In tal caso, l'icona dell'indicatore potrebbe essere adattata e assumere una forma diversa</span><span class="sxs-lookup"><span data-stu-id="0a5f3-117">When this occurs, the indicator icon might be stretched and change shape.</span></span> <span data-ttu-id="0a5f3-118">rendendola così meno leggibile.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-118">This can make the indicator icon less readable.</span></span> <span data-ttu-id="0a5f3-119">Posizionare l'indicatore in un rettangolo per assicurarsi che l'icona non sia mai adattata.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-119">Place the indicator inside a rectangle to ensure that the icon is never stretched.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="0a5f3-120">Per aggiungere un indicatore a una tabella o a una matrice</span><span class="sxs-lookup"><span data-stu-id="0a5f3-120">To add an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="0a5f3-121">Aprire un report esistente o crearne uno nuovo contenente una tabella e una matrice con i dati che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-121">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="0a5f3-122">Per altre informazioni, vedere [Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) o [Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a5f3-122">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="0a5f3-123">Inserire una colonna nella tabella o nella matrice.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-123">Insert a column in your table or matrix.</span></span> <span data-ttu-id="0a5f3-124">Per altre informazioni, vedere [Inserire o eliminare una colonna &#40;Generatore report e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a5f3-124">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="0a5f3-125">Facoltativamente, nella scheda **Inserisci** fare clic su **Rettangolo**e quindi fare clic su una cella nella nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-125">Optionally, on the **Insert** tab, click **Rectangle**, and then click a cell in the new column.</span></span>  
  
4.  <span data-ttu-id="0a5f3-126">Nella scheda **Inserisci** fare clic su **Indicatore**e quindi fare clic su una cella nella nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-126">On the **Insert** tab, click **Indicator**, and then click a cell in the new column.</span></span>  
  
     <span data-ttu-id="0a5f3-127">Se è stato aggiunto un rettangolo a una cella, fare clic su quella cella.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-127">If you added a rectangle to a cell, click that cell.</span></span>  
  
5.  <span data-ttu-id="0a5f3-128">Nel riquadro sinistro della finestra di dialogo **Seleziona tipo indicatore** fare clic sul tipo di indicatore desiderato e quindi sul set di indicatori.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-128">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
6.  <span data-ttu-id="0a5f3-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-129">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="0a5f3-130">Fare clic sull'indicatore.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-130">Click the indicator.</span></span> <span data-ttu-id="0a5f3-131">Viene visualizzato il riquadro **Dati del misuratore** .</span><span class="sxs-lookup"><span data-stu-id="0a5f3-131">The **Gauge Data** pane opens.</span></span>  
  
8.  <span data-ttu-id="0a5f3-132">Nell'area **Valori** , nell'elenco a discesa **(valore non specificato)** , fare clic sul campo di cui si vuole visualizzare i valori come un indicatore.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-132">In the **Values** area, in the **(Unspecified)** drop-down list, click the field whose values you want to display as an indicator.</span></span>  
  
     <span data-ttu-id="0a5f3-133">L'indicatore è configurato per utilizzare valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-133">The indicator is configured to use default values.</span></span> <span data-ttu-id="0a5f3-134">Per impostazione predefinita, gli indicatori vengono configurati per utilizzare le percentuali come unità di misura e gli intervalli di percentuale sono distribuiti uniformemente tra i membri dell'indicatore; il valore mostrato dall'indicatore utilizza l'ambito del gruppo più vicino.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-134">By default, indicators are configured use percentages as measurement units and the percentage ranges are evenly distributed across the members of the indicator and the value that the indicator conveys uses the scope of the nearest group.</span></span>  
  
### <a name="to-delete-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="0a5f3-135">Per eliminare un indicatore in una tabella o in una matrice</span><span class="sxs-lookup"><span data-stu-id="0a5f3-135">To delete an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="0a5f3-136">Fare clic con il pulsante destro del mouse sull'indicatore da eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-136">Right-click the indicator to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a5f3-137">È probabile che un indicatore sia posizionato in un pannello del misuratore che contiene altri indicatori o misuratori.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-137">An indicator might be positioned inside a gauge panel that contains other indicators or gauges.</span></span> <span data-ttu-id="0a5f3-138">Se i pannelli del misuratore contengono più elementi, assicurarsi di fare clic sull'indicatore da eliminare e non sul pannello del misuratore.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-138">If the gauge panels contain multiple items, be sure to click the indicator to delete it, not the gauge panel.</span></span> <span data-ttu-id="0a5f3-139">Se si fa clic e quindi si elimina il pannello del misuratore, verranno eliminati i pannelli del misuratore e tutti gli elementi in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-139">If you click and then delete the gauge panel, the gauge panels and all the items in it are deleted.</span></span>  
  
2.  <span data-ttu-id="0a5f3-140">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0a5f3-140">Click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a5f3-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a5f3-141">See Also</span></span>  
 [<span data-ttu-id="0a5f3-142">Indicatori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0a5f3-142">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
