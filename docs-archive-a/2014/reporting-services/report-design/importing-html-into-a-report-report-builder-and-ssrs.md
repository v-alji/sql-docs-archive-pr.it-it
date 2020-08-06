---
title: Importazione di codice HTML in un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dd0410ea-8839-4e8c-9944-8cdfe5465591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f978e67c67556184012db6b809e4f5754f2374c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713855"
---
# <a name="importing-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="3c322-102">Importazione di codice HTML a un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="3c322-102">Importing HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3c322-103">È possibile utilizzare una casella di testo per inserire in un report del testo in formato HTML recuperato da un campo nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="3c322-103">You can use a text box to insert HTML-formatted text that you have retrieved from a field in your dataset into a report.</span></span> <span data-ttu-id="3c322-104">Il testo può provenire da qualsiasi espressione semplice o complessa che restituisce testo HTML correttamente formattato.</span><span class="sxs-lookup"><span data-stu-id="3c322-104">The text can come from any simple or complex expression that evaluates to correctly formatted HTML.</span></span> <span data-ttu-id="3c322-105">Il testo formattato può essere visualizzato in tutti i formati di output supportati, incluso il formato PDF.</span><span class="sxs-lookup"><span data-stu-id="3c322-105">Formatted text can be rendered to all supported output formats, including PDF.</span></span>  
  
 <span data-ttu-id="3c322-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span><span class="sxs-lookup"><span data-stu-id="3c322-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span></span>  
  
 <span data-ttu-id="3c322-107">In questa illustrazione viene mostrato il testo con formattazione HTML nella visualizzazione Progettazione report e lo stesso testo come viene visualizzato all'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="3c322-107">This illustration shows text with HTML formatting in report design view, and the same text as it is rendered when the report is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c322-108">Quando si importa testo che contiene markup HTML, i dati devono sempre essere analizzati prima dalla casella di testo.</span><span class="sxs-lookup"><span data-stu-id="3c322-108">When you import text that contains HTML markup, the data must always be parsed by the text box first.</span></span> <span data-ttu-id="3c322-109">Poiché è supportato solo un subset di tag HTML, il testo HTML mostrato nel report visualizzabile potrebbe differire dal testo HTML originale.</span><span class="sxs-lookup"><span data-stu-id="3c322-109">Because only a subset of HTML tags is supported, the HTML that is shown in the rendered report may differ from your original HTML.</span></span>  
  
 <span data-ttu-id="3c322-110">Per iniziare rapidamente, vedere [Esercitazione: Formattazione di testo &#40;Generatore report&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3c322-110">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="supported-html-tags"></a><span data-ttu-id="3c322-111">Tag HTML supportati</span><span class="sxs-lookup"><span data-stu-id="3c322-111">Supported HTML Tags</span></span>  
 <span data-ttu-id="3c322-112">Di seguito viene mostrato un elenco completo dei tag che vengono visualizzati come testo HTML se definiti come testo segnaposto:</span><span class="sxs-lookup"><span data-stu-id="3c322-112">The following is a complete list of tags that will render as HTML when defined as placeholder text:</span></span>  
  
-   <span data-ttu-id="3c322-113">Elementi di intestazione, stile e blocco: \<H{n}> , \<DIV> , \<SPAN> , \<P> ,\<LI></span><span class="sxs-lookup"><span data-stu-id="3c322-113">Header, style and block elements: \<H{n}>, \<DIV>, \<SPAN>,\<P>, \<LI></span></span>  
  
 <span data-ttu-id="3c322-114">Qualsiasi altro tag del markup HTML verrà ignorato durante l'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="3c322-114">Any other HTML markup tags will be ignored during report processing.</span></span> <span data-ttu-id="3c322-115">Se il codice HTML rappresentato dall'espressione nel testo segnaposto non è formattato in maniera corretta, il segnaposto viene visualizzato come testo normale.</span><span class="sxs-lookup"><span data-stu-id="3c322-115">If the HTML represented by the expression in the placeholder text is not well formed, the placeholder is rendered as plain text.</span></span> <span data-ttu-id="3c322-116">Per tutti i tag HTML non viene rilevata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3c322-116">All HTML tags are case-insensitive.</span></span>  
  
 <span data-ttu-id="3c322-117">Se il testo nella casella di testo contiene un solo blocco di testo, qualsiasi codice HTML presente nel segnaposto che definisce elementi del blocco verrà visualizzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3c322-117">If the text in your text box contains only one block of text, any HTML in the placeholder that defines block elements will render correctly.</span></span> <span data-ttu-id="3c322-118">Se invece nella casella di testo sono presenti più blocchi di testo, i tag HTML vengono ignorati e la struttura del testo viene definita dai blocchi del testo.</span><span class="sxs-lookup"><span data-stu-id="3c322-118">However, if the text box has multiple blocks of text, the HTML tags are ignored and the structure of the text is defined by the blocks of text.</span></span>  
  
 <span data-ttu-id="3c322-119">Se per il testo è definito più di un tag e [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] rileva un conflitto tra il testo HTML e vincoli del report esistenti, solo il tag HTML più interno sarà trattato come HTML.</span><span class="sxs-lookup"><span data-stu-id="3c322-119">If more than one tag is defined for text, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] detects a conflict between the HTML and existing report constraints, only the innermost HTML tag will be treated as HTML.</span></span>  
  
 <span data-ttu-id="3c322-120">Quando si usa l'elenco di gestione dei tag, il tipo di carattere e stile di tutti i punti elenco e dei prefissi dei numeri verrà impostato su Arial black.</span><span class="sxs-lookup"><span data-stu-id="3c322-120">When using the list handling tags, the font and style of all bullets and number prefixes will be fixed to Arial black.</span></span>  
  
 <span data-ttu-id="3c322-121">Per altre informazioni, vedere [Aggiungere codice HTML a un report &#40;Generatore report e SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3c322-121">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="limitations-of-cascading-style-sheet-attributes"></a><span data-ttu-id="3c322-122">Limitazioni degli attributi dei fogli di stile CSS</span><span class="sxs-lookup"><span data-stu-id="3c322-122">Limitations of Cascading Style Sheet Attributes</span></span>  
 <span data-ttu-id="3c322-123">Quando si utilizzano gli attributi dei fogli di stile CSS, viene definito un solo set di tag di base.</span><span class="sxs-lookup"><span data-stu-id="3c322-123">When using cascading style sheet (CSS) attributes, only a basic set of tags are defined.</span></span> <span data-ttu-id="3c322-124">Di seguito viene presentato un elenco degli attributi supportati:</span><span class="sxs-lookup"><span data-stu-id="3c322-124">The following is a list of attributes that are supported:</span></span>  
  
-   <span data-ttu-id="3c322-125">text-align, text-indent</span><span class="sxs-lookup"><span data-stu-id="3c322-125">text-align, text-indent</span></span>  
  
-   <span data-ttu-id="3c322-126">font-family</span><span class="sxs-lookup"><span data-stu-id="3c322-126">font-family</span></span>  
  
-   <span data-ttu-id="3c322-127">font-size</span><span class="sxs-lookup"><span data-stu-id="3c322-127">font-size</span></span>  
  
    -   <span data-ttu-id="3c322-128">Sono supportati solo valori di dimensioni RDL validi, in unità di lunghezza CSS assolute.</span><span class="sxs-lookup"><span data-stu-id="3c322-128">Only valid RDL size values, in absolute CSS length units are supported.</span></span> <span data-ttu-id="3c322-129">Le unità supportate sono: in, cm, mm, pt, pc.</span><span class="sxs-lookup"><span data-stu-id="3c322-129">Supported units are: in, cm, mm, pt, pc.</span></span>  
  
    -   <span data-ttu-id="3c322-130">Le unità di lunghezza CSS relative vengono ignorate e non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="3c322-130">Relative CSS length units are ignored and not supported.</span></span> <span data-ttu-id="3c322-131">Le unità non supportate includono em, ex, px, %, rem.</span><span class="sxs-lookup"><span data-stu-id="3c322-131">Unsupported units include em, ex, px,%,rem.</span></span>  
  
-   <span data-ttu-id="3c322-132">color</span><span class="sxs-lookup"><span data-stu-id="3c322-132">color</span></span>  
  
-   <span data-ttu-id="3c322-133">padding, padding-bottom, padding-top, padding-right, padding-left</span><span class="sxs-lookup"><span data-stu-id="3c322-133">padding, padding-bottom, padding-top, padding-right, padding-left</span></span>  
  
-   <span data-ttu-id="3c322-134">font-weight</span><span class="sxs-lookup"><span data-stu-id="3c322-134">font-weight</span></span>  
  
 <span data-ttu-id="3c322-135">Di seguito sono indicate alcune considerazioni relative all'utilizzo dei fogli di stile CSS:</span><span class="sxs-lookup"><span data-stu-id="3c322-135">Here are some considerations for using CSS:</span></span>  
  
-   <span data-ttu-id="3c322-136">Come accade per il codice HTML non formattato correttamente, i valori CSS in formato non valido vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="3c322-136">Malformed CSS values are ignored in the same way as malformed HTML.</span></span>  
  
-   <span data-ttu-id="3c322-137">Quando nello stesso tag sono presenti sia l'attributo sia gli attributi dello stile CSS, la proprietà CSS ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="3c322-137">When both attribute and CSS style attributes exist in the same tag, the CSS property has a higher precedence.</span></span> <span data-ttu-id="3c322-138">Se, ad esempio, il testo è **\<p style="text-align: right" align="left">** , verrà applicato solo l'attributo text-align e il testo sarà allineato a destra.</span><span class="sxs-lookup"><span data-stu-id="3c322-138">For example, if your text is **\<p style="text-align: right" align="left">**, only the text-align attribute will be applied and the text will be right-aligned.</span></span>  
  
-   <span data-ttu-id="3c322-139">Per gli attributi e gli stili CSS, se una proprietà viene specificata più di una volta, viene applicata solo l'ultima istanza della proprietà.</span><span class="sxs-lookup"><span data-stu-id="3c322-139">For attributes and CSS styles, if a property is specified more than once, only the last instance of the property is applied.</span></span> <span data-ttu-id="3c322-140">Se, ad esempio, il testo è **\<p align="left" align="right">** , il testo verrà allineato a destra.</span><span class="sxs-lookup"><span data-stu-id="3c322-140">For example, if your text is **\<p align="left" align="right">**, the text will be right-aligned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c322-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c322-141">See Also</span></span>  
 [<span data-ttu-id="3c322-142">Rendering in formato HTML &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3c322-142">Rendering to HTML &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/rendering-to-html-report-builder-and-ssrs.md)  
  
  
