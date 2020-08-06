---
title: Aggiungere un bordo a un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81412f94-2991-4e58-bc05-5ccc0cbf2a75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf4a0c2c117774a0f3b25ca0644796fd067bc971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723483"
---
# <a name="add-a-border-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="825b8-102">Aggiungere un bordo a un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="825b8-102">Add a Border to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="825b8-103">È possibile aggiungere un bordo a un report aggiungendo bordi alle intestazioni, ai piè di pagina e al corpo del report, senza inserire righe o rettangoli.</span><span class="sxs-lookup"><span data-stu-id="825b8-103">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span>  
  
 <span data-ttu-id="825b8-104">Se al report si aggiunge un bordo visualizzato nell'intestazione e nel piè di pagina, non disattivare l'intestazione e il piè di pagina per la prima e l'ultima pagina del report</span><span class="sxs-lookup"><span data-stu-id="825b8-104">If you add a report border that appears on the page header and footer, do not suppress the header and footer on the first and last pages of the report.</span></span> <span data-ttu-id="825b8-105">per evitare che il bordo risulti troncato nella parte superiore o inferiore della prima e dell'ultima pagina del report.</span><span class="sxs-lookup"><span data-stu-id="825b8-105">If you do, the border may appear cut off at the top or bottom of the first and last pages of the report.</span></span> <span data-ttu-id="825b8-106">Per altre informazioni, vedere [Intestazioni di pagina e piè di pagina &#40;Generatore report e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="825b8-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-border-to-a-report"></a><span data-ttu-id="825b8-107">Per aggiungere un bordo a un report</span><span class="sxs-lookup"><span data-stu-id="825b8-107">To add a border to a report</span></span>  
  
1.  <span data-ttu-id="825b8-108">Fare clic con il pulsante destro del mouse nell'intestazione su uno spazio non occupato da elementi, quindi scegliere **Proprietà intestazione**.</span><span class="sxs-lookup"><span data-stu-id="825b8-108">Right-click in the header outside any items in the header, and click **Header Properties**.</span></span> <span data-ttu-id="825b8-109">Nella scheda **Bordo** aggiungere un bordo sinistro, superiore e destro con lo stile desiderato.</span><span class="sxs-lookup"><span data-stu-id="825b8-109">On the **Border** tab, add a left, top, and right border with the style you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="825b8-110">Se non si utilizzano le intestazioni nel report, è possibile posizionare i bordi solo intorno al corpo del report oppure è possibile aggiungere intestazioni dalla scheda **Inserisci** .</span><span class="sxs-lookup"><span data-stu-id="825b8-110">If you do not use headers in your report, you can place borders around just the report body, or you can add headers from the **Insert** tab.</span></span>  
  
2.  <span data-ttu-id="825b8-111">Fare clic con il pulsante destro del mouse nel corpo su uno spazio dell'area di progettazione non occupato da elementi e scegliere **Proprietà corpo**.</span><span class="sxs-lookup"><span data-stu-id="825b8-111">Right-click in the body outside any items on the design surface, and click **Body Properties**.</span></span> <span data-ttu-id="825b8-112">Nella scheda **Bordo** aggiungere un bordo sinistro e destro con lo stile desiderato.</span><span class="sxs-lookup"><span data-stu-id="825b8-112">On the **Border** tab, add a left and right border with the style you want.</span></span>  
  
3.  <span data-ttu-id="825b8-113">Fare clic con il pulsante destro del mouse nel piè di pagina su uno spazio non occupato da elementi, quindi scegliere **Proprietà piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="825b8-113">Right-click in the footer outside any items in the footer, and click **Footer Properties**.</span></span> <span data-ttu-id="825b8-114">Nella scheda **Bordo** aggiungere un bordo sinistro, inferiore e destro con lo stile desiderato.</span><span class="sxs-lookup"><span data-stu-id="825b8-114">On the **Border** tab, add a left, bottom, and right border with the style you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="825b8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="825b8-115">See Also</span></span>  
 [<span data-ttu-id="825b8-116">Rettangoli e linee &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="825b8-116">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
  
  
