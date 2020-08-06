---
title: Merge Cells in a Data Region (Report Builder and SSRS) (Unire le celle in un'area dati (Generatore report e SSRS)) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 43551300-89b2-4f4e-af09-69084324afaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c69ce8182bda3e0b644893e97b69280a003f5732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719553"
---
# <a name="merge-cells-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="0a128-102">Unire le celle in un'area dati (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="0a128-102">Merge Cells in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0a128-103">È possibile unire celle in un'area dati per combinare più celle, migliorare l'aspetto dell'area dati oppure consentire l'espansione delle etichette per gruppi di colonne e di righe.</span><span class="sxs-lookup"><span data-stu-id="0a128-103">You can merge cells in a data region to combine cells, improve data region appearance, or provide spanning labels for column groups and row groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a128-104">Le celle possono essere unite solo all'interno delle singole aree di un'area dati: angolo, intestazioni di colonna, definizione di gruppo (o intestazioni di riga) e corpo.</span><span class="sxs-lookup"><span data-stu-id="0a128-104">Cells can only be merged within each area of a data region: corner, column headers, group definition (or row headers), and body.</span></span> <span data-ttu-id="0a128-105">Non è possibile unire celle che intersecano i limiti dell'area.</span><span class="sxs-lookup"><span data-stu-id="0a128-105">You cannot merge cells that cross area boundaries.</span></span> <span data-ttu-id="0a128-106">Non è ad esempio possibile unire una cella nell'area dell'angolo dell'area dati con una presente nell'area del gruppo di righe.</span><span class="sxs-lookup"><span data-stu-id="0a128-106">For example, you cannot merge a cell in the data region corner area with a cell in the row group area.</span></span> <span data-ttu-id="0a128-107">Per ulteriori informazioni sulle aree Tablix, vedere la pagina relativa agli [elenchi &#40;Generatore report e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a128-107">For more information about tablix areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-merge-cells-in-a-data-region"></a><span data-ttu-id="0a128-108">Per unire celle in un'area dati</span><span class="sxs-lookup"><span data-stu-id="0a128-108">To merge cells in a data region</span></span>  
  
1.  <span data-ttu-id="0a128-109">Nell'area dati dell'area di progettazione del report fare clic sulla prima cella da unire.</span><span class="sxs-lookup"><span data-stu-id="0a128-109">In the data region on the report design surface, click the first cell to merge.</span></span> <span data-ttu-id="0a128-110">Tenere premuto il pulsante sinistro del mouse, quindi trascinare il cursore in senso orizzontale o verticale per selezionare celle adiacenti.</span><span class="sxs-lookup"><span data-stu-id="0a128-110">Holding the left mouse button down, drag vertically or horizontally to select adjacent cells.</span></span> <span data-ttu-id="0a128-111">Le celle selezionate verranno evidenziate.</span><span class="sxs-lookup"><span data-stu-id="0a128-111">The selected cells are highlighted.</span></span>  
  
2.  <span data-ttu-id="0a128-112">Fare clic con il pulsante destro del mouse sulle celle selezionate e quindi scegliere **Unisci celle**.</span><span class="sxs-lookup"><span data-stu-id="0a128-112">Right-click the selected cells and select **Merge Cells**.</span></span> <span data-ttu-id="0a128-113">Le celle selezionate verranno combinate in un'unica cella.</span><span class="sxs-lookup"><span data-stu-id="0a128-113">The selected cells are combined into a single cell.</span></span>  
  
3.  <span data-ttu-id="0a128-114">Ripetere i passaggi 1 e 2 per unire altre celle adiacenti in un'area dati.</span><span class="sxs-lookup"><span data-stu-id="0a128-114">Repeat steps 1 and 2 to merge other adjacent cells in a data region.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a128-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a128-115">See Also</span></span>  
 <span data-ttu-id="0a128-116">[Area dati Tablix &#40;Generatore report e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0a128-116">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0a128-117">[Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0a128-117">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0a128-118">[Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0a128-118">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0a128-119">[Elenca &#40;Generatore report e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0a128-119">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0a128-120">Elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0a128-120">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
