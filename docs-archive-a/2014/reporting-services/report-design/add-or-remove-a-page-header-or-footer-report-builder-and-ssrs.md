---
title: Aggiungere o rimuovere un'intestazione o un piè di pagina (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 72988623-fee8-4a05-9f72-8fcb8e668576
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b29db3f72323c460360c872a0f60d13a808e3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719590"
---
# <a name="add-or-remove-a-page-header-or-footer-report-builder-and-ssrs"></a><span data-ttu-id="e3372-102">Aggiungere o rimuovere un'intestazione o un piè di pagina (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e3372-102">Add or Remove a Page Header or Footer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e3372-103">È possibile aggiungere testo statico, immagini, linee, rettangoli e bordi a intestazioni di pagina o piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="e3372-103">You can add static text, images, lines, rectangles, and borders to page headers or footers.</span></span> <span data-ttu-id="e3372-104">È possibile posizionare espressioni e immagini con associazioni a dati in una casella di testo se si desiderano dati variabili o calcolati in un'intestazione o in un piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="e3372-104">You can place expressions and data-bound images in a textbox if you want variable or computed data in a header or footer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3372-105">Ogni estensione per il rendering elabora le intestazioni di pagina e i piè di pagina in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="e3372-105">Each rendering extension processes page headers and footers differently.</span></span> <span data-ttu-id="e3372-106">Per altre informazioni, vedere [Intestazioni di pagina e piè di pagina &#40;Generatore report e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) e [Paginazione in Reporting Services &#40;Generatore report e SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e3372-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) and [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-header-or-footer"></a><span data-ttu-id="e3372-107">Per aggiungere un'intestazione di pagina o un piè di pagina</span><span class="sxs-lookup"><span data-stu-id="e3372-107">To add a page header or footer</span></span>  
  
1.  <span data-ttu-id="e3372-108">Aprire un report.</span><span class="sxs-lookup"><span data-stu-id="e3372-108">Open a report.</span></span>  
  
2.  <span data-ttu-id="e3372-109">Nell'area di progettazione fare clic con il pulsante destro del mouse sul report, scegliere **Inserisci**, quindi fare clic su **Intestazione** o **Piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="e3372-109">On the design surface, right-click the report, point to **Insert**, and then click **Header** or **Footer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3372-110">Le opzioni **Intestazione** e **Piè di pagina** vengono visualizzate solo quando un report non include già un'intestazione o un piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="e3372-110">The **Header** and **Footer** options appear only when a header or footer is not already part of the report.</span></span>  
  
### <a name="to-configure-a-page-header-or-footer"></a><span data-ttu-id="e3372-111">Per configurare un'intestazione o un piè di pagina</span><span class="sxs-lookup"><span data-stu-id="e3372-111">To configure a page header or footer</span></span>  
  
1.  <span data-ttu-id="e3372-112">Nell'area di progettazione fare clic con il pulsante destro del mouse sull'intestazione o sul piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="e3372-112">On the design surface, right-click the page header or footer.</span></span>  
  
2.  <span data-ttu-id="e3372-113">Scegliere **Inserisci**, quindi fare clic su uno degli elementi seguenti per aggiungerlo all'are di intestazione o piè di pagina:</span><span class="sxs-lookup"><span data-stu-id="e3372-113">Point to **Insert**, and then click one of the following items to add it to the header or footer area:</span></span>  
  
    -   <span data-ttu-id="e3372-114">**Casella di testo**</span><span class="sxs-lookup"><span data-stu-id="e3372-114">**Textbox**</span></span>  
  
    -   <span data-ttu-id="e3372-115">**Linea**</span><span class="sxs-lookup"><span data-stu-id="e3372-115">**Line**</span></span>  
  
    -   <span data-ttu-id="e3372-116">**Rettangolo**</span><span class="sxs-lookup"><span data-stu-id="e3372-116">**Rectangle**</span></span>  
  
    -   <span data-ttu-id="e3372-117">**Immagine**</span><span class="sxs-lookup"><span data-stu-id="e3372-117">**Image**</span></span>  
  
3.  <span data-ttu-id="e3372-118">Fare clic con il pulsante destro del mouse sull'intestazione pagina, quindi scegliere **Proprietà intestazione** per aggiungere bordi, immagini di sfondo o colori oppure per regolare la larghezza dell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="e3372-118">Right-click the page header, and then click **Header Properties** to add borders, background images, or colors, or to adjust the width of the header.</span></span> <span data-ttu-id="e3372-119">Fare quindi clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3372-119">Then click **OK**.</span></span>  
  
4.  <span data-ttu-id="e3372-120">Fare clic con il pulsante destro del mouse sul piè di pagina, quindi scegliere **Proprietà piè di pagina** per aggiungere bordi, immagini di sfondo o colori oppure per regolare la larghezza del piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="e3372-120">Right-click the page footer, and then click **Footer Properties** to add borders, background images, or colors, or to adjust the width of the footer.</span></span> <span data-ttu-id="e3372-121">Fare quindi clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3372-121">Then click **OK**.</span></span>  
  
### <a name="to-remove-a-page-header-or-footer"></a><span data-ttu-id="e3372-122">Per rimuovere un'intestazione di pagina o un piè di pagina</span><span class="sxs-lookup"><span data-stu-id="e3372-122">To remove a page header or footer</span></span>  
  
1.  <span data-ttu-id="e3372-123">Aprire un report.</span><span class="sxs-lookup"><span data-stu-id="e3372-123">Open a report.</span></span>  
  
2.  <span data-ttu-id="e3372-124">Nell'area di progettazione fare clic con il pulsante destro del mouse sull'intestazione o sul piè di pagina, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e3372-124">On the design surface, right-click the page header or footer, and then click **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3372-125">Quando si rimuove un'intestazione o un piè di pagina, l'elemento viene eliminato dal report.</span><span class="sxs-lookup"><span data-stu-id="e3372-125">When you remove a page header or footer, you delete it from the report.</span></span> <span data-ttu-id="e3372-126">Gli elementi aggiunti in precedenza non verranno visualizzati di nuovo se in seguito si decide di reinserire l'intestazione o il piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="e3372-126">Any items that you previously added to the page header or footer will not reappear if you subsequently add the header or footer again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3372-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3372-127">See Also</span></span>  
 [<span data-ttu-id="e3372-128">Intestazioni di pagina e piè di pagina &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e3372-128">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
