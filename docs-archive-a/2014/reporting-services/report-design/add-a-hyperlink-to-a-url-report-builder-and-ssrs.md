---
title: Aggiungere un collegamento ipertestuale a un URL (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d3392c0b-7b62-4d27-bc04-2bd0c5487d08
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d3db3fc75feca1393e73e698f44db633f09e8dc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713867"
---
# <a name="add-a-hyperlink-to-a-url-report-builder-and-ssrs"></a><span data-ttu-id="efe12-102">Aggiungere un collegamento ipertestuale a un URL (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="efe12-102">Add a Hyperlink to a URL (Report Builder and SSRS)</span></span>
  <span data-ttu-id="efe12-103">È possibile aggiungere un collegamento ipertestuale a un elemento di report quando si desidera che gli utenti siano in grado di fare clic su un collegamento in un report e aprire una finestra del browser relativa all'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="efe12-103">You can add a hyperlink to a report item when you want your users to be able to click a link in a report and open a browser to the URL that you specify.</span></span> <span data-ttu-id="efe12-104">Un collegamento ipertestuale può essere un URL statico o un'espressione che restituisce un URL.</span><span class="sxs-lookup"><span data-stu-id="efe12-104">A hyperlink can be a static URL or an expression that evaluates to a URL.</span></span> <span data-ttu-id="efe12-105">Se in un database è disponibile un campo contenente URL, sarà possibile usare tale campo nell'espressione per ottenere un elenco dinamico di collegamenti ipertestuali nel report.</span><span class="sxs-lookup"><span data-stu-id="efe12-105">If you have a field in a database that contains URLs, the expression can contain that field, resulting in a dynamic list of hyperlinks in the report.</span></span> <span data-ttu-id="efe12-106">È possibile aggiungere collegamenti ipertestuali a caselle di testo, immagini, grafici e misuratori.</span><span class="sxs-lookup"><span data-stu-id="efe12-106">You can add hyperlinks to text boxes, images, charts, and gauges.</span></span> <span data-ttu-id="efe12-107">È necessario garantire che l'utente acceda all'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="efe12-107">You must ensure that the user has access to the URL that you provide.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="efe12-108">È inoltre possibile specificare URL ai report in qualsiasi server di report per la cui visualizzazione gli utenti dispongono delle autorizzazioni usando richieste di URL inviate al server di report.</span><span class="sxs-lookup"><span data-stu-id="efe12-108">You can also specify URLs to reports on any report server that you and your users have permission to view using URL requests to the report server.</span></span> <span data-ttu-id="efe12-109">È ad esempio possibile specificare un report e nascondere la mappa documento agli utenti quando visualizzano il report per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="efe12-109">For example, you can specify a report and hide the document map for the user when they first view the report.</span></span> <span data-ttu-id="efe12-110">Per altre informazioni, vedere [Accesso con URL &#40;SSRS&#41;](../url-access-ssrs.md) della [Documentazione relativa a Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) inclusa nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efe12-110">For more information, see [URL Access &#40;SSRS&#41;](../url-access-ssrs.md) in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="efe12-111">È possibile aggiungere un collegamento ipertestuale a un URL in qualsiasi elemento che dispone di una proprietà **Azione** , ad esempio una casella di testo, un'immagine o una serie calcolata in un grafico.</span><span class="sxs-lookup"><span data-stu-id="efe12-111">You can add a hyperlink to a URL to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="efe12-112">Quando l'utente fa clic sul tale elemento del report, viene eseguita l'azione definita.</span><span class="sxs-lookup"><span data-stu-id="efe12-112">When the user clicks that report item, the action that you define takes place.</span></span> <span data-ttu-id="efe12-113">Per altre informazioni, vedere [Finestra di dialogo Proprietà azione &#40;Generatore report e SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) e [Specifica di percorsi di elementi esterni &#40;Generatore report e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="efe12-113">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) and [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="efe12-114">Per iniziare rapidamente, vedere [Esercitazione: Formattazione di testo &#40;Generatore report&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="efe12-114">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="efe12-115">I collegamenti associati ai campi del set di dati possono essere esposti ad alterazioni per finalità dannose.</span><span class="sxs-lookup"><span data-stu-id="efe12-115">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="efe12-116">Per altre informazioni, vedere [Garantire la sicurezza di report e risorse](../security/secure-reports-and-resources.md) nella [documentazione online](https://go.microsoft.com/fwlink/?LinkId=154888) di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sul sito msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="efe12-116">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
### <a name="to-add-a-hyperlink"></a><span data-ttu-id="efe12-117">Per aggiungere un collegamento ipertestuale</span><span class="sxs-lookup"><span data-stu-id="efe12-117">To add a hyperlink</span></span>  
  
1.  <span data-ttu-id="efe12-118">Nella visualizzazione Progettazione report fare clic con il pulsante destro del mouse sulla casella di testo, sull'immagine o sul grafico a cui si desidera aggiungere un collegamento, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="efe12-118">In report design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="efe12-119">Nella finestra di dialogo Proprietà fare clic su **Azione**.</span><span class="sxs-lookup"><span data-stu-id="efe12-119">In the Properties dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="efe12-120">Selezionare **Vai a URL**.</span><span class="sxs-lookup"><span data-stu-id="efe12-120">Select **Go to URL**.</span></span> <span data-ttu-id="efe12-121">Nella finestra di dialogo verrà visualizzata una sezione aggiuntiva per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="efe12-121">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="efe12-122">In **Selezionare un URL**digitare o selezionare un URL o un'espressione che restituisca un URL oppure fare clic sulla freccia a discesa e selezionare il nome di un campo contenente un URL.</span><span class="sxs-lookup"><span data-stu-id="efe12-122">In **Select URL**, type or select a URL or an expression that evaluates to a URL, or click the drop-down arrow and click the name of a field that contains a URL.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="efe12-123">(Facoltativo) Il testo non viene formattato automaticamente come collegamento.</span><span class="sxs-lookup"><span data-stu-id="efe12-123">(Optional) The text is not automatically formatted as a link.</span></span> <span data-ttu-id="efe12-124">Per il testo è utile modificare il colore e l'effetto del testo per indicare che si tratta di un collegamento.</span><span class="sxs-lookup"><span data-stu-id="efe12-124">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="efe12-125">È possibile, ad esempio, modificare il colore in blu e sottolineare il testo nella sezione **Carattere** nella scheda Home della barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="efe12-125">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="efe12-126">Per verificare il collegamento,fare clic **Esegui** per visualizzare il report in anteprima, quindi fare clic sull'elemento di report su cui è stato impostato il collegamento.</span><span class="sxs-lookup"><span data-stu-id="efe12-126">To test the link, click **Run** to preview the report, and then click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe12-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efe12-127">See Also</span></span>  
 <span data-ttu-id="efe12-128">[Ordinamento interattivo, mappe documento e collegamenti &#40;Generatore report e SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="efe12-128">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="efe12-129">Creare una mappa documento &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="efe12-129">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
  
  
