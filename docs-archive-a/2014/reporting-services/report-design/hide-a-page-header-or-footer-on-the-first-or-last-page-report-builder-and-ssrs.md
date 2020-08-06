---
title: Nascondere un'intestazione o un piè di pagina nella prima o nell'ultima pagina (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f87ce79b-00d7-4458-a17e-e253a20f720d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60c8789fd098df7347e9cc0f583426478aee06e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711639"
---
# <a name="hide-a-page-header-or-footer-on-the-first-or-last-page-report-builder-and-ssrs"></a><span data-ttu-id="01aa5-102">Nascondere un'intestazione o un piè di pagina nella prima o nell'ultima pagina (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="01aa5-102">Hide a Page Header or Footer on the First or Last Page (Report Builder and SSRS)</span></span>
  <span data-ttu-id="01aa5-103">In un report è possibile includere un'intestazione e un piè di pagina, posizionati rispettivamente nella parte superiore e inferiore di ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="01aa5-103">A report can contain a page header and page footer that run along the top and bottom of each page, respectively.</span></span> <span data-ttu-id="01aa5-104">Dopo aver aggiunto un'intestazione o un piè di pagina, è possibile nasconderlo selettivamente nella prima e nell'ultima pagina di un report.</span><span class="sxs-lookup"><span data-stu-id="01aa5-104">After you a add a header or footer, you can selectively hide it on the first and last pages of a report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-a-page-header-on-the-first-or-last-page"></a><span data-ttu-id="01aa5-105">Per nascondere un'intestazione di pagina nella prima o nell'ultima pagina</span><span class="sxs-lookup"><span data-stu-id="01aa5-105">To hide a page header on the first or last page</span></span>  
  
1.  <span data-ttu-id="01aa5-106">Aprire un report in visualizzazione Progettazione.</span><span class="sxs-lookup"><span data-stu-id="01aa5-106">Open a report in Design view.</span></span>  
  
2.  <span data-ttu-id="01aa5-107">Fare clic con il pulsante destro del mouse sull'intestazione di pagina, quindi scegliere **Proprietà intestazione**.</span><span class="sxs-lookup"><span data-stu-id="01aa5-107">Right-click the page header, and then click **Header Properties**.</span></span> <span data-ttu-id="01aa5-108">Verrà visualizzata la finestra di dialogo **Proprietà intestazione report** .</span><span class="sxs-lookup"><span data-stu-id="01aa5-108">The **Report Header Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="01aa5-109">Verificare che l'opzione **Visualizza intestazione per il report** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="01aa5-109">Verify that **Display header for this report** is not selected.</span></span>  
  
4.  <span data-ttu-id="01aa5-110">Nella sezione **Opzioni di stampa** deselezionare la casella di controllo relativa alle singole opzioni per disattivare la visualizzazione nella prima o nell'ultima pagina del report.</span><span class="sxs-lookup"><span data-stu-id="01aa5-110">In the **Print options** section, clear the check box for each option to hide the display on the first or last page of the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-hide-a-page-footer-on-the-first-or-last-page"></a><span data-ttu-id="01aa5-111">Per nascondere un piè di pagina nella prima o nell'ultima pagina</span><span class="sxs-lookup"><span data-stu-id="01aa5-111">To hide a page footer on the first or last page</span></span>  
  
1.  <span data-ttu-id="01aa5-112">Aprire un report in visualizzazione Progettazione.</span><span class="sxs-lookup"><span data-stu-id="01aa5-112">Open a report in Design view.</span></span>  
  
2.  <span data-ttu-id="01aa5-113">Fare clic con il pulsante destro del mouse sul piè di pagina, quindi scegliere **Proprietà piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="01aa5-113">Right-click the page footer, and then click **Footer Properties**.</span></span> <span data-ttu-id="01aa5-114">Verrà visualizzata la finestra di dialogo **Proprietà piè di pagina report** .</span><span class="sxs-lookup"><span data-stu-id="01aa5-114">The **Report Footer Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="01aa5-115">Verificare che l'opzione **Visualizza piè di pagina per il report** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="01aa5-115">Verify that **Display footer for this report** is not selected.</span></span>  
  
4.  <span data-ttu-id="01aa5-116">Nella sezione **Opzioni di stampa** deselezionare la casella di controllo relativa alle singole opzioni per disattivare la visualizzazione nella prima o nell'ultima pagina del report.</span><span class="sxs-lookup"><span data-stu-id="01aa5-116">In the **Print options** section, clear the check box for each option to hide the display on the first or last page of the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="01aa5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01aa5-117">See Also</span></span>  
 <span data-ttu-id="01aa5-118">[Intestazioni di pagina e piè di pagina &#40;Generatore report e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="01aa5-118">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="01aa5-119">[Paginazione in Reporting Services &#40;Generatore report e SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="01aa5-119">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="01aa5-120">Aggiungere o rimuovere un'intestazione o un piè di pagina &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="01aa5-120">Add or Remove a Page Header or Footer &#40;Report Builder and SSRS&#41;</span></span>](add-or-remove-a-page-header-or-footer-report-builder-and-ssrs.md)  
  
  
