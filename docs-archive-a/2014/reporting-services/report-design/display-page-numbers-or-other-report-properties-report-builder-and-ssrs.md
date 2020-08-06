---
title: Visualizzare i numeri di pagina o altre proprietà del report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7d95245-4709-4d04-acb4-59bf71e60d97
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efc3d5d5de11af1fcdfefc52ed12d5057ee12668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628442"
---
# <a name="display-page-numbers-or-other-report-properties-report-builder-and-ssrs"></a><span data-ttu-id="6eaad-102">Visualizzare i numeri di pagina o altre proprietà del report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="6eaad-102">Display Page Numbers or Other Report Properties (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6eaad-103">Aggiungere numeri di pagina, un titolo di report, un nome file e altre proprietà alle intestazioni o ai piè di pagina del report è un'operazione semplice.</span><span class="sxs-lookup"><span data-stu-id="6eaad-103">It's easy to add page numbers, a report title, file name, and other report properties to the page headers or footers of your report.</span></span> <span data-ttu-id="6eaad-104">Queste proprietà sono archiviate come campi nella cartella Campi predefiniti nel riquadro dei dati del report:</span><span class="sxs-lookup"><span data-stu-id="6eaad-104">These properties are stored as fields in the Built-in Fields folder in the Report Data pane:</span></span>  
  
-   <span data-ttu-id="6eaad-105">Ora di esecuzione</span><span class="sxs-lookup"><span data-stu-id="6eaad-105">Execution time</span></span>  
  
-   <span data-ttu-id="6eaad-106">Numero di pagina</span><span class="sxs-lookup"><span data-stu-id="6eaad-106">Page number</span></span>  
  
-   <span data-ttu-id="6eaad-107">Cartella dei report</span><span class="sxs-lookup"><span data-stu-id="6eaad-107">Report folder</span></span>  
  
-   <span data-ttu-id="6eaad-108">Nome del report</span><span class="sxs-lookup"><span data-stu-id="6eaad-108">Report name</span></span>  
  
-   <span data-ttu-id="6eaad-109">URL del server di report</span><span class="sxs-lookup"><span data-stu-id="6eaad-109">Report server URL</span></span>  
  
-   <span data-ttu-id="6eaad-110">Totale pagine</span><span class="sxs-lookup"><span data-stu-id="6eaad-110">Total pages</span></span>  
  
-   <span data-ttu-id="6eaad-111">ID utente</span><span class="sxs-lookup"><span data-stu-id="6eaad-111">User ID</span></span>  
  
-   <span data-ttu-id="6eaad-112">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="6eaad-112">Language</span></span>  
  
 <span data-ttu-id="6eaad-113">Per un numero di pagina, potrebbe essere necessario aggiungere la parola 'Pagina' prima del numero.</span><span class="sxs-lookup"><span data-stu-id="6eaad-113">For a page number, you may want to add the word "Page" before the number.</span></span> <span data-ttu-id="6eaad-114">Inoltre, potrebbe essere necessario indicare anche il numero complessivo di pagine.</span><span class="sxs-lookup"><span data-stu-id="6eaad-114">You may also want to show the total number of pages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6eaad-115">L'aggiunta del numero complessivo di pagine al piè di pagina potrebbe rallentare le prestazioni quando si esegue o si visualizza il report in anteprima.</span><span class="sxs-lookup"><span data-stu-id="6eaad-115">Adding the total number of pages to the footer may slow performance when you run or preview your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-number-or-other-report-properties"></a><span data-ttu-id="6eaad-116">Per aggiungere il numero di pagina o altre proprietà</span><span class="sxs-lookup"><span data-stu-id="6eaad-116">To add a page number or other report properties</span></span>  
  
1.  <span data-ttu-id="6eaad-117">Espandere la cartella Campi predefiniti nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="6eaad-117">In the Report Data pane, expand the Built-in Fields folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6eaad-118">Se il riquadro dei dati del report non viene visualizzato, fare clic su **Dati report**nella scheda Visualizza.</span><span class="sxs-lookup"><span data-stu-id="6eaad-118">If you don't see the Report Data pane, on the View tab, check **Report Data**.</span></span>  
  
2.  <span data-ttu-id="6eaad-119">Trascinare il campo **Numero pagina** dal riquadro dei dati del report nell'intestazione o nel piè di pagina del report.</span><span class="sxs-lookup"><span data-stu-id="6eaad-119">Drag the **Page Number** field from the Report Data pane to the report header or footer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6eaad-120">Il piè di pagina verrà aggiunto automaticamente al report.</span><span class="sxs-lookup"><span data-stu-id="6eaad-120">The page footer is added to the report automatically.</span></span> <span data-ttu-id="6eaad-121">Per aggiungere un'intestazione di pagina, nella scheda **Inserisci** fare clic su **Intestazione**e quindi su **Aggiungi intestazione**.</span><span class="sxs-lookup"><span data-stu-id="6eaad-121">To add a page header, on the **Insert** tab, click **Header**, and then click **Add Header**.</span></span>  
    >   
    >  <span data-ttu-id="6eaad-122">Verrà aggiunta una casella di testo contenente l'espressione semplice [&PageNumber].</span><span class="sxs-lookup"><span data-stu-id="6eaad-122">A text box that contains the simple expression [&PageNumber] is added.</span></span>  
  
### <a name="to-add-the-word-page-before-the-page-number"></a><span data-ttu-id="6eaad-123">Per aggiungere la parola "Pagina" prima del numero di pagina</span><span class="sxs-lookup"><span data-stu-id="6eaad-123">To add the word "Page" before the page number</span></span>  
  
1.  <span data-ttu-id="6eaad-124">Fare clic con il pulsante destro del mouse sulla casella di testo che contiene [&PageNumber], quindi scegliere **Espressioni**.</span><span class="sxs-lookup"><span data-stu-id="6eaad-124">Right-click the text box that contains [&PageNumber] and click **Expressions**.</span></span>  
  
     <span data-ttu-id="6eaad-125">La casella di testo **Imposta espressione per: Valore** contiene l'espressione =Globals!PageNumber.</span><span class="sxs-lookup"><span data-stu-id="6eaad-125">The **Set Expression for: Value** text box contains the expression =Globals!PageNumber.</span></span>  
  
2.  <span data-ttu-id="6eaad-126">Posizionare il cursore dopo il segno = e digitare `"Page " &`.</span><span class="sxs-lookup"><span data-stu-id="6eaad-126">Place the cursor after the = sign and type `"Page " &`.</span></span>  
  
     <span data-ttu-id="6eaad-127">L'espressione cambierà in ="Pagina "&Globals!PageNumber</span><span class="sxs-lookup"><span data-stu-id="6eaad-127">The expression is now  ="Page "&Globals!PageNumber</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-total-number-of-pages-after-the-page-number"></a><span data-ttu-id="6eaad-128">Per aggiungere il numero complessivo di pagine dopo il numero di pagina</span><span class="sxs-lookup"><span data-stu-id="6eaad-128">To add total number of pages after the page number</span></span>  
  
1.  <span data-ttu-id="6eaad-129">Fare clic con il pulsante destro del mouse sulla casella di testo con l'espressione, quindi scegliere **Espressioni**.</span><span class="sxs-lookup"><span data-stu-id="6eaad-129">Right click the text box with the expression and click **Expressions**.</span></span>  
  
2.  <span data-ttu-id="6eaad-130">Digitare **&" di "&** alla fine dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="6eaad-130">Type **&" of "&** at the end of the expression.</span></span>  
  
3.  <span data-ttu-id="6eaad-131">Nel riquadro Categoria espandere **Campi predefiniti** , quindi fare doppio clic **TotalPages**.</span><span class="sxs-lookup"><span data-stu-id="6eaad-131">In the Category pane, expand **Built-in Fields** and double-click **TotalPages**.</span></span>  
  
     <span data-ttu-id="6eaad-132">L'espressione cambierà in ="Page "&Globals!PageNumber &" di "&Globals!TotalPages.</span><span class="sxs-lookup"><span data-stu-id="6eaad-132">The expression is now ="Page "&Globals!PageNumber &" of "&Globals!TotalPages</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6eaad-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6eaad-133">See Also</span></span>  
 <span data-ttu-id="6eaad-134">[Intestazioni di pagina e piè di pagina &#40;Generatore report e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6eaad-134">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6eaad-135">Formattare il testo in una casella di testo &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6eaad-135">Format Text in a Text Box &#40;Report Builder and SSRS&#41;</span></span>](format-text-in-a-text-box-report-builder-and-ssrs.md)  
  
  
