---
title: Aggiungere, spostare o eliminare una tabella, una matrice o un elenco (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b97c470-cde0-4bb1-a46e-5f5f5553feaa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 43941639a41c897a49cd34662b74de26a27e3f07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723464"
---
# <a name="add-move-or-delete-a-table-matrix-or-list-report-builder-and-ssrs"></a><span data-ttu-id="99ee6-102">Aggiunta, spostamento o eliminazione di una tabella, una matrice o un elenco (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="99ee6-102">Add, Move, or Delete a Table, Matrix, or List (Report Builder and SSRS)</span></span>
  <span data-ttu-id="99ee6-103">In un'area dati vengono visualizzati i dati di un set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="99ee6-103">A data region displays data from a report dataset.</span></span> <span data-ttu-id="99ee6-104">Le aree dati includono tabelle, matrici, elenchi, grafici e misuratori.</span><span class="sxs-lookup"><span data-stu-id="99ee6-104">Data regions include table, matrix, list, chart, and gauge.</span></span> <span data-ttu-id="99ee6-105">Per nidificare un'area dati in un'altra, aggiungere separatamente ogni area dati, quindi trascinare l'area dati figlio nell'area dati padre.</span><span class="sxs-lookup"><span data-stu-id="99ee6-105">To nest one data region inside another, add each data region separately, and then drag the child data region onto the parent data region.</span></span>  
  
 <span data-ttu-id="99ee6-106">Per aggiungere un'area dati tabella o matrice al report in modo semplice, eseguire la Creazione guidata tabella o la Creazione guidata matrice.</span><span class="sxs-lookup"><span data-stu-id="99ee6-106">The simplest way to add a table or matrix data region to your report is to run the New Table or New Matrix Wizard.</span></span> <span data-ttu-id="99ee6-107">In queste procedure guidate vengono fornite istruzioni utili per scegliere una connessione a un'origine dati, disporre i campi e selezionare il layout e lo stile.</span><span class="sxs-lookup"><span data-stu-id="99ee6-107">These wizards will guide you through the process of choosing a connection to a data source, arranging fields, and choosing the layout and style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99ee6-108">La procedura guidata è disponibile unicamente in Generatore report.</span><span class="sxs-lookup"><span data-stu-id="99ee6-108">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-table-or-matrix-to-a-report-by-using-the-new-table-or-new-matrix-wizard"></a><span data-ttu-id="99ee6-109">Per aggiungere una tabella o una matrice a un report utilizzando la Creazione guidata tabella o la Creazione guidata matrice</span><span class="sxs-lookup"><span data-stu-id="99ee6-109">To add a table or matrix to a report by using the New Table or New Matrix Wizard</span></span>  
  
1.  <span data-ttu-id="99ee6-110">Nella scheda **Inserisci** fare clic su **Tabella** o **Matrice**e quindi scegliere **Creazione guidata tabella** o **Creazione guidata matrice**.</span><span class="sxs-lookup"><span data-stu-id="99ee6-110">On the **Insert** tab, click **Table** or **Matrix**, and then click **Table Wizard** or **Matrix Wizard**.</span></span>  
  
2.  <span data-ttu-id="99ee6-111">Seguire i **passaggi della procedura guidata per la creazione** di una **nuova matrice** .</span><span class="sxs-lookup"><span data-stu-id="99ee6-111">Follow the steps in the **NewTable** or **New Matrix** wizard.</span></span>  
  
3.  <span data-ttu-id="99ee6-112">Nella scheda **Home** fare clic su **Esegui** per mostrare il report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="99ee6-112">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="99ee6-113">Nella scheda **Esegui** fare clic su **Progettazione** per continuare a utilizzare il report.</span><span class="sxs-lookup"><span data-stu-id="99ee6-113">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-data-region"></a><span data-ttu-id="99ee6-114">Per aggiungere un'area dati</span><span class="sxs-lookup"><span data-stu-id="99ee6-114">To add a data region</span></span>  
  
1.  <span data-ttu-id="99ee6-115">Nel gruppo **Aree dati**sulla **barra multifunzione** fare clic sull'area dati da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="99ee6-115">On the **Ribbon**, in the **Data Regions** group, click the data region to add.</span></span>  
  
2.  <span data-ttu-id="99ee6-116">Fare clic nell'area di progettazione, quindi trascinare il mouse per creare una casella delle dimensioni desiderate per l'area dati.</span><span class="sxs-lookup"><span data-stu-id="99ee6-116">Click the design surface, and then drag to create a box that is the desired size of the data region.</span></span>  
  
3.  <span data-ttu-id="99ee6-117">Trascinare un campo del set di dati del report dal riquadro dei dati del report in una cella dell'area dati.</span><span class="sxs-lookup"><span data-stu-id="99ee6-117">Drag a report dataset field from the Report Data pane onto a data region cell.</span></span> <span data-ttu-id="99ee6-118">L'area dati risulterà associata ai dati del set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="99ee6-118">The data region is now bound to data from the report dataset.</span></span>  
  
### <a name="to-select-a-data-region"></a><span data-ttu-id="99ee6-119">Per selezionare un'area dati</span><span class="sxs-lookup"><span data-stu-id="99ee6-119">To select a data region</span></span>  
  
-   <span data-ttu-id="99ee6-120">Per un'area dati Tablix, fare clic con il pulsante destro del mouse sull'handle d'angolo.</span><span class="sxs-lookup"><span data-stu-id="99ee6-120">For a tablix data region, right-click the corner handle.</span></span> <span data-ttu-id="99ee6-121">Per un'area dati grafico o misuratore, fare clic nell'area dati.</span><span class="sxs-lookup"><span data-stu-id="99ee6-121">For a chart or gauge data region, click in the data region.</span></span>  
  
     <span data-ttu-id="99ee6-122">Verranno visualizzati un handle di selezione e otto handle di ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="99ee6-122">A selection handle and eight resizing handles appear.</span></span>  
  
     <span data-ttu-id="99ee6-123">Per le aree dati annidate, fare clic con il pulsante destro del mouse nell'area dati annidata, scegliere **Seleziona**e quindi selezionare l'elemento del report desiderato.</span><span class="sxs-lookup"><span data-stu-id="99ee6-123">For nested data regions, right-click in the nested data region, click **Select**, and then select the report item you want.</span></span> <span data-ttu-id="99ee6-124">Per verificare quale elemento del report è selezionato, utilizzare il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="99ee6-124">To verify which report item is selected, use the Properties pane.</span></span> <span data-ttu-id="99ee6-125">Il nome dell'elemento selezionato nell'area di progettazione verrà visualizzato sulla barra degli strumenti del riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="99ee6-125">The name of the selected item on the design surface appears in the toolbar of the Properties pane.</span></span>  
  
### <a name="to-move-a-data-region"></a><span data-ttu-id="99ee6-126">Per spostare un'area dati</span><span class="sxs-lookup"><span data-stu-id="99ee6-126">To move a data region</span></span>  
  
-   <span data-ttu-id="99ee6-127">Per spostare un'area dati, fare clic sull'handle di selezione dell'area dati e trascinarlo.</span><span class="sxs-lookup"><span data-stu-id="99ee6-127">To move a data region, click the selection handle of the data region and drag it.</span></span> <span data-ttu-id="99ee6-128">Utilizzare guide di allineamento per allineare l'area dati agli elementi di report esistenti.</span><span class="sxs-lookup"><span data-stu-id="99ee6-128">Use snaplines to align it to existing report items.</span></span>  
  
     <span data-ttu-id="99ee6-129">Se il righello non è visibile, fare clic sulla scheda Visualizza e selezionare l'opzione **Righello** .</span><span class="sxs-lookup"><span data-stu-id="99ee6-129">If the ruler is not visible, click the View tab and select the **Ruler** option.</span></span>  
  
     <span data-ttu-id="99ee6-130">In alternativa, utilizzare i tasti di direzione per spostare l'area dati selezionata nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="99ee6-130">Alternatively, use the arrow keys to move the selected data region on the design surface.</span></span>  
  
### <a name="to-delete-a-data-region"></a><span data-ttu-id="99ee6-131">Per eliminare un'area dati</span><span class="sxs-lookup"><span data-stu-id="99ee6-131">To delete a data region</span></span>  
  
-   <span data-ttu-id="99ee6-132">Selezionare l'area dati, fare clic con il pulsante destro del mouse nell'area dati e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="99ee6-132">Select the data region, right-click in the data region, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ee6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99ee6-133">See Also</span></span>  
 <span data-ttu-id="99ee6-134">[Area dati Tablix &#40;Generatore report e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="99ee6-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="99ee6-135">[Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="99ee6-135">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="99ee6-136">[Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="99ee6-136">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="99ee6-137">[Elenca &#40;Generatore report e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="99ee6-137">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="99ee6-138">Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="99ee6-138">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
