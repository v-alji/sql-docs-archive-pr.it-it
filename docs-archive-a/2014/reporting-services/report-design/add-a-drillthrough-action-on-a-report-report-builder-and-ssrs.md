---
title: Aggiungere un'azione drill-through a un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 153729c4-d01e-4629-b78f-0cfd5a7f83da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a429380f677a309e4e1437a2e3c5036bb4e8a455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626511"
---
# <a name="add-a-drillthrough-action-on-a-report-report-builder-and-ssrs"></a><span data-ttu-id="c0f9c-102">Aggiungere un'azione drill-through a un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c0f9c-102">Add a Drillthrough Action on a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c0f9c-103">Il report visualizzato quando si fa clic sul collegamento nel report principale è noto come *report drill-through*.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-103">The report that opens when you click the link in the main report is known as a *drillthrough report*.</span></span> <span data-ttu-id="c0f9c-104">Questo collegamento drill-through consente un'azione drill-through.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-104">This drillthrough link enables a drillthrough action.</span></span>  
  
 <span data-ttu-id="c0f9c-105">I report drill-through devono essere pubblicati sullo stesso server di report del report principale, anche se in cartelle diverse.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-105">Drillthrough reports must be published to the same report server as the main report, but they can be in different folders.</span></span> <span data-ttu-id="c0f9c-106">È possibile aggiungere un collegamento drill-through a qualsiasi elemento che dispone di una proprietà **Azione** , ad esempio una casella di testo, un'immagine o punti dati in un grafico.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-106">You can add a drillthrough link to any item that has an **Action** property, such as a text box, an image, or data points on a chart.</span></span>  
  
 <span data-ttu-id="c0f9c-107">Per aggiungere un collegamento drill-through a un report, è necessario prima creare il report drill-through cui collegare il report principale.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-107">To add a drillthrough link to a report, you must first create the drillthrough report that the main report will link to.</span></span> <span data-ttu-id="c0f9c-108">Un report drill-through contiene in genere i dettagli su un elemento presente nel report di riepilogo originale e spesso parametri che consentono di filtrare il report in base ai parametri passati dal report principale.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-108">A drillthrough report commonly contains details about an item that is contained in the original summary report, and often contains parameters that filter the drillthrough report based on parameters passed to it from the main report.</span></span> <span data-ttu-id="c0f9c-109">Per altre informazioni sulla creazione del report drill-through, vedere [Report drill-through &#40;Generatore report e SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c0f9c-109">For more information on creating the drillthrough report, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-drillthrough-action"></a><span data-ttu-id="c0f9c-110">Per aggiungere un'azione drill-through</span><span class="sxs-lookup"><span data-stu-id="c0f9c-110">To add a drillthrough action</span></span>  
  
1.  <span data-ttu-id="c0f9c-111">In visualizzazione Progettazione fare clic con il pulsante destro del mouse sulla casella di testo, sull'immagine o sul grafico cui si vuole aggiungere un collegamento e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-111">In Design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c0f9c-112">Nella finestra di dialogo **Proprietà** dell'elemento fare clic su **Azione**.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-112">In the item's **Properties** dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="c0f9c-113">Selezionare **Vai al report**.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-113">Select **Go to report**.</span></span> <span data-ttu-id="c0f9c-114">Nella finestra di dialogo verranno visualizzate sezioni aggiuntive per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-114">Additional sections appear in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="c0f9c-115">In **Specifica un report**fare clic su **Sfoglia** per individuare il report a cui si vuole passare oppure digitarne il nome.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-115">In **Specify a report**, click **Browse** to locate the report that you want to jump to, or type the name of the report.</span></span> <span data-ttu-id="c0f9c-116">In alternativa, fare clic sul pulsante di espressione (**fx**) per creare un'espressione per il nome del report.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-116">Alternatively, click the expression (**fx**) button to create an expression for the report name.</span></span>  
  
     <span data-ttu-id="c0f9c-117">Il formato del percorso del report drill-through è diverso a seconda che sia attiva la modalità nativa o la modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-117">The format of the path to the drillthrough report differs for native and SharePoint integrated mode.</span></span> <span data-ttu-id="c0f9c-118">Se si utilizza la funzionalità di esplorazione, viene fornito un percorso con il formato corretto.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-118">If you browse to the report, a path of the correct format is provided.</span></span> <span data-ttu-id="c0f9c-119">Per altre informazioni, vedere [Specifica di percorsi di elementi esterni &#40;Generatore report e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c0f9c-119">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="c0f9c-120">Se è necessario specificare parametri per il report drill-through, eseguire la procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-120">If you have to specify parameters for the drillthrough report, follow the next step.</span></span>  
  
5.  <span data-ttu-id="c0f9c-121">In **Utilizzare i parametri seguenti per eseguire il report**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-121">In **Use these parameters to run the report**, click **Add**.</span></span> <span data-ttu-id="c0f9c-122">Alla griglia dei parametri verrà aggiunta una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-122">A new row is added to the parameter grid.</span></span>  
  
    -   <span data-ttu-id="c0f9c-123">Nella casella di testo **Nome** fare clic sull'elenco a discesa o digitare il nome del parametro di report nel report drill-through.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-123">In the **Name** text box, click the drop-down list or type the name of the report parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c0f9c-124">I nomi nell'elenco dei parametri devono corrispondere esattamente ai parametri previsti nel report di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-124">The names in the parameter list must match the expected parameters in the target report exactly.</span></span> <span data-ttu-id="c0f9c-125">I nomi di parametro devono presentare ad esempio la stessa combinazione di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-125">For example, parameter names must match by case.</span></span> <span data-ttu-id="c0f9c-126">Se i nomi non corrispondono o un parametro previsto non è presente nell'elenco, il report drill-through restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-126">If the names do not match, or if an expected parameter is not listed, the drillthrough report fails.</span></span>  
  
    -   <span data-ttu-id="c0f9c-127">In **Valore**digitare o selezionare il valore da passare al parametro nel report drill-through.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-127">In **Value**, type or select the value to pass to the parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c0f9c-128">I valori possono contenere un'espressione che restituisce un valore da passare al parametro del report.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-128">Values can contain an expression that evaluates to a value to pass to the report parameter.</span></span> <span data-ttu-id="c0f9c-129">Le espressioni nell'elenco dei valori includono l'elenco dei campi per il report corrente.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-129">The expressions in the value list include the field list for the current report.</span></span>  
  
     <span data-ttu-id="c0f9c-130">Per informazioni su come nascondere i parametri nei report, vedere [Aggiungere, modificare o eliminare un parametro di report &#40;Generatore report e SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c0f9c-130">For information on how to hide parameters in reports, see [Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="c0f9c-131">(Facoltativo) Per le caselle di testo, è utile indicare all'utente che il testo è un collegamento modificandone il colore e l'effetto nella scheda **Home** della barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-131">(Optional) For text boxes, it is helpful to indicate to the user that the text is a link by changing the color and effect of the text on the **Home** tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="c0f9c-132">Per verificare il collegamento, eseguire il report e fare clic sull'elemento di report su cui è stato impostato il collegamento.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-132">To test the link, run the report and click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f9c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0f9c-133">See Also</span></span>  
 <span data-ttu-id="c0f9c-134">[Finestra di dialogo Proprietà azione &#40;Generatore report e SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c0f9c-134">[Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c0f9c-135">[Formattazione dei punti dati di un grafico &#40;Generatore report e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c0f9c-135">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c0f9c-136">Visualizzazione di descrizioni comandi in una serie &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c0f9c-136">Show ToolTips on a Series &#40;Report Builder and SSRS&#41;</span></span>](show-tooltips-on-a-series-report-builder-and-ssrs.md)  
  
  
