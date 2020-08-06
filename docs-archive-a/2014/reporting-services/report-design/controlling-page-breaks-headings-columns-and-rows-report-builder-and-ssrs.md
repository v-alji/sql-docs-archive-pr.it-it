---
title: Controllo di interruzioni di pagina, intestazioni, colonne e righe (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b8fa41f-a727-4f23-8efb-fd9bb0d4cd1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7dae06129ee5dc9962538e8d025dca9966325f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635420"
---
# <a name="controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs"></a><span data-ttu-id="2e2d1-102">Controllo di interruzioni di pagina, intestazioni, colonne e righe (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2e2d1-102">Controlling Page Breaks, Headings, Columns, and Rows (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2e2d1-103">Un'interruzione di pagina consente di suddividere un report in più pagine per la visualizzazione e la stampa.</span><span class="sxs-lookup"><span data-stu-id="2e2d1-103">A page break divides a report into separate pages for viewing and printing.</span></span> <span data-ttu-id="2e2d1-104">Consentono inoltre di adattare il contenuto alle pagine dei report in modo da ottenere una visualizzazione ottimale quando si visualizza l'anteprima di un report o si esporta il report in un altro formato.</span><span class="sxs-lookup"><span data-stu-id="2e2d1-104">Page breaks determine how the content is fitted to a report page for optimal viewing when you preview a report or export it to a different file format.</span></span>  
  
 <span data-ttu-id="2e2d1-105">L'aggiunta di interruzioni di pagina migliora anche le prestazioni dei report di grandi dimensioni in fase di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2e2d1-105">Adding page breaks also improves the performance of large reports when the are processed.</span></span> <span data-ttu-id="2e2d1-106">Il rendering delle pagine viene eseguito in modo progressivo in background</span><span class="sxs-lookup"><span data-stu-id="2e2d1-106">A rendered page is displayed while the rest of the pages are rendered in the background.</span></span> <span data-ttu-id="2e2d1-107">in modo che sia possibile visualizzare immediatamente le pagine iniziali del report mentre si attende che le altre siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="2e2d1-107">This allows you to begin viewing the initial pages of the report while waiting for additional pages to become available.</span></span>  
  
 <span data-ttu-id="2e2d1-108">È possibile aggiungere interruzioni di pagina a elementi del report quali una tabella, una matrice, un elenco, un grafico, un misuratore o un'immagine,</span><span class="sxs-lookup"><span data-stu-id="2e2d1-108">Page breaks can be added to report items such as a table, matrix, list, chart, gauge, or image.</span></span> <span data-ttu-id="2e2d1-109">nonché ai gruppi in una tabella, una matrice o un elenco</span><span class="sxs-lookup"><span data-stu-id="2e2d1-109">You can also add page breaks to groups in a table, matrix, or list.</span></span> <span data-ttu-id="2e2d1-110">Le interruzioni di pagina possono essere aggiunte prima o dopo dei gruppi o tra un gruppo e l'altro.</span><span class="sxs-lookup"><span data-stu-id="2e2d1-110">Page breaks can be added before, after, and between groups.</span></span> <span data-ttu-id="2e2d1-111">Le interruzioni di pagina tra i gruppi non vengono aggiunte al report per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2e2d1-111">Page breaks between groups are not added to the report by default.</span></span>  
  
 <span data-ttu-id="2e2d1-112">Per altre informazioni, vedere [Visualizzare le intestazioni di riga e colonna in più pagine &#40;Generatore report e SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) e [Mantenere visibili le intestazioni durante lo scorrimento di un report &#40;Generatore report e SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2e2d1-112">For more information, see [Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) and [Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e2d1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e2d1-113">See Also</span></span>  
 <span data-ttu-id="2e2d1-114">[Elenca &#40;Generatore report e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e2d1-114">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e2d1-115">[Controllo della visualizzazione dell'area dati Tablix in una pagina del report &#40;Generatore report e SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span><span class="sxs-lookup"><span data-stu-id="2e2d1-115">[Controlling the Tablix Data Region Display on a Report Page &#40;Report Builder and SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span></span>  
 <span data-ttu-id="2e2d1-116">[Riquadro di raggruppamento &#40;Generatore report&#41;](grouping-pane-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="2e2d1-116">[Grouping Pane &#40;Report Builder&#41;](grouping-pane-report-builder.md) </span></span>  
 [<span data-ttu-id="2e2d1-117">Visualizzare intestazioni e piè di pagina con un gruppo &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2e2d1-117">Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;</span></span>](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md)  
  
  
