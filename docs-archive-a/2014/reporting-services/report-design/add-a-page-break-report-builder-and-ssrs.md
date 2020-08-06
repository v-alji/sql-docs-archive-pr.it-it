---
title: Aggiungere un'interruzione di pagina (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3846cd48-2787-47e9-b13b-7fc45a205f68
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55d6be3ae47827c5a8ff4a5b36e3ff2ce80e1034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623801"
---
# <a name="add-a-page-break-report-builder-and-ssrs"></a><span data-ttu-id="bdd54-102">Aggiungere un'interruzione di pagina (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="bdd54-102">Add a Page Break (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bdd54-103">È possibile aggiungere un'interruzione di pagina a rettangoli, aree dati o gruppi all'interno di aree dati per controllare la quantità di informazioni in ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="bdd54-103">You can add a page break to rectangles, data regions, or groups within data regions to control the amount of information on each page.</span></span> <span data-ttu-id="bdd54-104">Con l'aggiunta di interruzioni di pagina è possibile migliorare le prestazioni dei report pubblicati, perché quando si visualizza il report è necessario elaborare solo gli elementi presenti in ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="bdd54-104">Adding page breaks can improve the performance of published reports because only the items on each page have to be processed as you view the report.</span></span> <span data-ttu-id="bdd54-105">Quando l'intero report è costituito da un'unica pagina, prima che sia possibile visualizzare il report è necessario che tutti gli elementi vengano elaborati.</span><span class="sxs-lookup"><span data-stu-id="bdd54-105">When the whole report is a single page, all items must be processed before you can view the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-break-to-a-data-region"></a><span data-ttu-id="bdd54-106">Per aggiungere un'interruzione di pagina a un'area dati</span><span class="sxs-lookup"><span data-stu-id="bdd54-106">To add a page break to a data region</span></span>  
  
1.  <span data-ttu-id="bdd54-107">Nell'area di progettazione fare clic con il pulsante destro del mouse sull'handle d'angolo dell'area dati, quindi scegliere **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-107">On the design surface, right-click the corner handle of the data region and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="bdd54-108">Nella scheda **Generale** , in **Opzioni di interruzione pagina**, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bdd54-108">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="bdd54-109">**Aggiungi un'interruzione di pagina prima**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-109">**Add a page break before**.</span></span> <span data-ttu-id="bdd54-110">Selezionare questa opzione se si desidera aggiungere un'interruzione di pagina prima della tabella.</span><span class="sxs-lookup"><span data-stu-id="bdd54-110">Select this option when you want to add a page break before the table.</span></span>  
  
    -   <span data-ttu-id="bdd54-111">**Aggiungi un'interruzione di pagina dopo**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-111">**Add a page break after**.</span></span> <span data-ttu-id="bdd54-112">Selezionare questa opzione se si desidera aggiungere un'interruzione di pagina dopo la tabella.</span><span class="sxs-lookup"><span data-stu-id="bdd54-112">Select this option when you want to add a page break after the table.</span></span>  
  
    -   <span data-ttu-id="bdd54-113">**Riduci tabella a una sola pagina se possibile**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-113">**Fit table on one page if possible**.</span></span> <span data-ttu-id="bdd54-114">Selezionare questa opzione se si desidera adattare i dati in un'unica pagina.</span><span class="sxs-lookup"><span data-stu-id="bdd54-114">Select this option when you want the data to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-rectangle"></a><span data-ttu-id="bdd54-115">Per aggiungere un'interruzione di pagina a un rettangolo</span><span class="sxs-lookup"><span data-stu-id="bdd54-115">To add a page break to a rectangle</span></span>  
  
1.  <span data-ttu-id="bdd54-116">Nell'area di progettazione fare clic con il pulsante destro del mouse sul rettangolo in cui si desidera aggiungere un'interruzione di pagina, quindi scegliere **Proprietà rettangolo**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-116">On the design surface, right-click the rectangle where you want to add a page break, and then click **Rectangle Properties**.</span></span>  
  
2.  <span data-ttu-id="bdd54-117">Nella scheda **Generale** , in **Opzioni di interruzione pagina**, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bdd54-117">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="bdd54-118">**Aggiungi un'interruzione di pagina prima**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-118">**Add a page break before**.</span></span> <span data-ttu-id="bdd54-119">Selezionare questa opzione se si desidera aggiungere un'interruzione di pagina prima del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="bdd54-119">Select this option when you want to add a page break before the rectangle.</span></span>  
  
    -   <span data-ttu-id="bdd54-120">**Aggiungi un'interruzione di pagina dopo**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-120">**Add a page break after**.</span></span> <span data-ttu-id="bdd54-121">Selezionare questa opzione se si desidera aggiungere un'interruzione di pagina dopo il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="bdd54-121">Select this option when you want to add a page break after the rectangle.</span></span>  
  
    -   <span data-ttu-id="bdd54-122">**Ometti bordo sull'interruzione di pagina**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-122">**Omit border on page break**.</span></span> <span data-ttu-id="bdd54-123">Selezionare questa opzione se non si desidera aggiungere un bordo sull'interruzione di pagina.</span><span class="sxs-lookup"><span data-stu-id="bdd54-123">Select this option when you do not want a border on the page break.</span></span>  
  
    -   <span data-ttu-id="bdd54-124">**Mantieni contenuto in una singola pagina, se possibile**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-124">**Keep contents together on a single page, if possible**.</span></span> <span data-ttu-id="bdd54-125">Selezionare questa opzione se si desidera che il contenuto del rettangolo occupi una sola pagina.</span><span class="sxs-lookup"><span data-stu-id="bdd54-125">Select this option when you want contents inside the rectangle to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-row-group-in-a-table-matrix-or-list"></a><span data-ttu-id="bdd54-126">Per aggiungere un'interruzione di pagina a un gruppo di righe in una tabella, in una matrice o in un elenco</span><span class="sxs-lookup"><span data-stu-id="bdd54-126">To add a page break to a row group in a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="bdd54-127">Nel riquadro Raggruppamento fare clic con il pulsante destro del mouse sul gruppo di righe, quindi scegliere **Proprietà gruppo**.</span><span class="sxs-lookup"><span data-stu-id="bdd54-127">In the Grouping pane, right-click a row group, and then click **Group Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bdd54-128">Le interruzioni di pagina relative a gruppi di colonne vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="bdd54-128">Page breaks are ignored on column groups.</span></span>  
  
2.  <span data-ttu-id="bdd54-129">Nella scheda **Interruzioni di pagina** selezionare **Tra ogni istanza di un gruppo** per aggiungere un'interruzione di pagina tra ogni istanza di un gruppo nella tabella.</span><span class="sxs-lookup"><span data-stu-id="bdd54-129">On the **Page Breaks** tab, select **Between each instance of a group** to add a page break between each instance of a group in the table.</span></span>  
  
3.  <span data-ttu-id="bdd54-130">Facoltativamente, selezionare **Anche all'inizio di un gruppo** o **Anche alla fine di un gruppo** per specificare che un'interruzione di pagina deve essere aggiunta all'inizio o alla fine di un gruppo nella tabella.</span><span class="sxs-lookup"><span data-stu-id="bdd54-130">Optionally, select **Also at the start of a group** or **Also at the end of a group** to specify that a page break be added when a group starts or ends in the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd54-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdd54-131">See Also</span></span>  
 <span data-ttu-id="bdd54-132">[Paginazione in Reporting Services &#40;Generatore report e SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bdd54-132">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bdd54-133">[Tipi di rendering &#40;Generatore report e SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bdd54-133">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bdd54-134">Intestazioni di pagina e piè di pagina &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bdd54-134">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
