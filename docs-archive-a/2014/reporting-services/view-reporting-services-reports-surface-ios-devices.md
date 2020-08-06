---
title: Visualizzare Reporting Services report sui dispositivi Microsoft Surface e Apple iOS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- iPad
- Safari
- SSRS
- Report Viewer [Reporting Services]
- iOS
ms.assetid: 2124bcf5-d60a-475f-a4ae-de6df44d2860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db52ed500559969ae52eb9477caa6b410889c1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635415"
---
# <a name="view-reporting-services-reports-on-microsoft-surface-devices-and--apple-ios-devices"></a><span data-ttu-id="8a656-102">Visualizzare i report Reporting Services su dispositivi Microsoft Surface e Apple iOS</span><span class="sxs-lookup"><span data-stu-id="8a656-102">View Reporting Services Reports on Microsoft Surface Devices and  Apple iOS Devices</span></span>
  <span data-ttu-id="8a656-103">In questo articolo vengono descritti i flussi di lavoro e le funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] supportati per i dispositivi di Microsoft Surface e i dispositivi con Apple iOS 6 e Apple Safari come l'iPad.</span><span class="sxs-lookup"><span data-stu-id="8a656-103">This article describes the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features and workflows supported for Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari such as the iPad.</span></span>

## <a name="view-and-interact-with-reports"></a><span data-ttu-id="8a656-104">Visualizzare e interagire con i report</span><span class="sxs-lookup"><span data-stu-id="8a656-104">View and Interact With Reports</span></span>
 <span data-ttu-id="8a656-105">A partire da [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] supporta la visualizzazione e l'interattività di base con i report nei dispositivi di Microsoft Surface e nei dispositivi con Apple iOS 6 e il browser Apple Safari come l'iPad.</span><span class="sxs-lookup"><span data-stu-id="8a656-105">Starting with [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] supports viewing and basic interactivity with reports on Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari browser such as the iPad.</span></span> <span data-ttu-id="8a656-106">Inoltre, è possibile pubblicare i report utilizzando i dispositivi di Microsoft Surface.</span><span class="sxs-lookup"><span data-stu-id="8a656-106">You can also publish reports using Microsoft Surface devices.</span></span>

 <span data-ttu-id="8a656-107">![Desktop iPad](media/videothumbnail.jpg "Desktop IPad") Guarda una dimostrazione della visualizzazione dei report in un iPad.</span><span class="sxs-lookup"><span data-stu-id="8a656-107">![IPad Desktop](media/videothumbnail.jpg "IPad Desktop") Watch a demonstration of viewing reports on an iPad.</span></span>

 <span data-ttu-id="8a656-108">I report di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] possono essere visualizzati anche in un dispositivo Windows Phone 8.</span><span class="sxs-lookup"><span data-stu-id="8a656-108">You can also view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports on a Windows Phone 8 device.</span></span>

 <span data-ttu-id="8a656-109">Per utilizzare le funzionalità descritte in questo argomento, installare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a656-109">To utilize the features described in this topic, install one of the following:</span></span>

-   <span data-ttu-id="8a656-110">Per un server di report in modalità nativa, installare [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="8a656-110">For a native mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later.</span></span>

     [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)]<span data-ttu-id="8a656-111">è disponibile per il download dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=35575).</span><span class="sxs-lookup"><span data-stu-id="8a656-111">is available for download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=35575).</span></span>

-   <span data-ttu-id="8a656-112">Per un server di report in modalità SharePoint, installare [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] o versioni successive del componente aggiuntivo [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] per prodotti SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a656-112">For a SharePoint mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>

 <span data-ttu-id="8a656-113">**Per visualizzare un report e interagire con il report su un dispositivo iPad o Microsoft Surface**</span><span class="sxs-lookup"><span data-stu-id="8a656-113">**To view and interact with a report on an iPad device or Microsoft Surface device**</span></span>

1.  <span data-ttu-id="8a656-114">Verificare che sia possibile connettersi al server di report oppure al sito di SharePoint in cui si trova il report.</span><span class="sxs-lookup"><span data-stu-id="8a656-114">Make sure that you can connect to the report server or SharePoint site where the report resides.</span></span>

2.  <span data-ttu-id="8a656-115">Aprire il report effettuando una delle operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8a656-115">Open the report by doing one of the following.</span></span>

    -   <span data-ttu-id="8a656-116">**Avvio dalla posta elettronica:** in un messaggio di posta elettronica creato da una sottoscrizione di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , toccare l'URL del report.</span><span class="sxs-lookup"><span data-stu-id="8a656-116">**Start from e-mail:** From an e-mail that is created by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] subscription, tap the URL of the report.</span></span> <span data-ttu-id="8a656-117">Il report verrà aperto nel browser.</span><span class="sxs-lookup"><span data-stu-id="8a656-117">The report will open in the browser.</span></span>

    -   <span data-ttu-id="8a656-118">**Avvio dal server di report:** passare alla directory nel server di report [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , quindi toccare il nome del report per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="8a656-118">**Start from Report Server:** Browse the directory on the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server, and then tap the report name to open the report.</span></span>

    -   <span data-ttu-id="8a656-119">**Avvio da una raccolta documenti di SharePoint:** selezionare una raccolta documenti di SharePoint in cui sono contenuti i report di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , quindi toccare il nome del report.</span><span class="sxs-lookup"><span data-stu-id="8a656-119">**Start from a SharePoint document library:** Browse to a SharePoint document library that contains [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports, and then tap the report name.</span></span> <span data-ttu-id="8a656-120">È possibile visualizzare e interagire con il report.</span><span class="sxs-lookup"><span data-stu-id="8a656-120">You can view and interact with the report.</span></span>

        > [!IMPORTANT]
        >  <span data-ttu-id="8a656-121"> Per l'iPad, verificare che la proprietà relativa all'esplorazione privata per Safari sia disabilitata **.**</span><span class="sxs-lookup"><span data-stu-id="8a656-121">For the iPad, ensure that the **Private Browsing** property for Safari is turned off.</span></span>

    -   <span data-ttu-id="8a656-122">**Web part di SharePoint:** se la Web part è stata aggiunta a una pagina di SharePoint, è possibile visualizzare i report di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8a656-122">**SharePoint web part:** If the web part has been added to a SharePoint page, you can view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports.</span></span>

3.  <span data-ttu-id="8a656-123">Sul dispositivo Microsoft Surface è inoltre possibile aprire il report utilizzando Gestione report.</span><span class="sxs-lookup"><span data-stu-id="8a656-123">On your Microsoft Surface device, you can also open the report by using Report Manager.</span></span> <span data-ttu-id="8a656-124">Sfogliare la directory in Gestione report di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , quindi toccare il nome del report per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="8a656-124">Browse the directory in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager, and then tap the report name to open the report.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="8a656-125">La visualizzazione dei report in Gestione report non è supportata su un iPad.</span><span class="sxs-lookup"><span data-stu-id="8a656-125">Viewing reports in Report Manager is not supported on an iPad.</span></span>

4.  <span data-ttu-id="8a656-126">Scorrere e fare zoom avanti effettuando le operazioni seguenti</span><span class="sxs-lookup"><span data-stu-id="8a656-126">Scroll and zoom by doing the following.</span></span>

    -   <span data-ttu-id="8a656-127">Per scorrere il report, trascinare il dito sullo schermo (verso l'alto, verso il basso, a sinistra o a destra).</span><span class="sxs-lookup"><span data-stu-id="8a656-127">To scroll the report, drag your finger across the screen (up, down, left or right).</span></span> <span data-ttu-id="8a656-128">Si tratta del gesto di spostamento rapido con un dito.</span><span class="sxs-lookup"><span data-stu-id="8a656-128">This is the swipe gesture.</span></span>

    -   <span data-ttu-id="8a656-129">Per fare zoom avanti, posizionare due dita sullo schermo e allontanarle.</span><span class="sxs-lookup"><span data-stu-id="8a656-129">To zoom in, place two fingers on the screen and separate the fingers.</span></span> <span data-ttu-id="8a656-130">Per fare zoom indietro, posizionare due dita sullo schermo e spostarle insieme.</span><span class="sxs-lookup"><span data-stu-id="8a656-130">To zoom out, place two fingers on the screen and move the fingers together.</span></span> <span data-ttu-id="8a656-131">Si tratta del movimento zoom indietro.</span><span class="sxs-lookup"><span data-stu-id="8a656-131">This is the pinch gesture.</span></span>

5.  <span data-ttu-id="8a656-132">Esplorare e interagire con il report effettuando le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8a656-132">Navigate and interact with the report by doing the following.</span></span>

    -   <span data-ttu-id="8a656-133">Comprimere ed espandere gli elementi del report, nonché le righe e le colonne associate ai gruppi, toccando il segno più (+) per comprimere e il segno meno (-) per espandere.</span><span class="sxs-lookup"><span data-stu-id="8a656-133">Collapse and expand report items, and rows and columns that are associated with groups, by taping the plus (+) sign to collapse and the minus (-) sign to expand.</span></span>

    -   <span data-ttu-id="8a656-134">Toccare il pulsante di ordinamento per passare dall'ordine crescente a quello decrescente e viceversa per le righe di una tabella o per le righe e le colonne di una matrice.</span><span class="sxs-lookup"><span data-stu-id="8a656-134">Toggle between ascending and descending order for rows in a table or for rows and columns in a matrix, by tapping the sort button.</span></span> <span data-ttu-id="8a656-135">Il pulsante di ordinamento in genere si trova nell'intestazione della colonna.</span><span class="sxs-lookup"><span data-stu-id="8a656-135">The sort button is usually located in the column header.</span></span>

    -   <span data-ttu-id="8a656-136">Espandere e comprimere il riquadro dei parametri, toccando il pulsante freccia nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="8a656-136">Expand and collapse the parameter pane, by tapping the arrow button near the top of the report.</span></span>

    -   <span data-ttu-id="8a656-137">Selezionare un valore di parametro toccando la casella o il controllo accanto al parametro.</span><span class="sxs-lookup"><span data-stu-id="8a656-137">Select a parameter value by tapping the box or control next to the parameter.</span></span> <span data-ttu-id="8a656-138">Toccare **Visualizza report** per applicare il valore del parametro al report.</span><span class="sxs-lookup"><span data-stu-id="8a656-138">Tap **View Report** to apply the parameter value to the report.</span></span>

    -   <span data-ttu-id="8a656-139">Per eseguire ricerche nel contenuto del report toccare la casella accanto a **Trova**, digitando un termine di ricerca e toccando **Trova**.</span><span class="sxs-lookup"><span data-stu-id="8a656-139">Search the report content by taping the box next to **Find**, typing a search term, and then taping **Find**.</span></span>

    -   <span data-ttu-id="8a656-140">Esplorare le pagine del report toccando i pulsanti di navigazione o la casella di testo accanto ai pulsanti e digitando il numero di pagina.</span><span class="sxs-lookup"><span data-stu-id="8a656-140">Navigate the report pages by tapping the navigation buttons, or tapping the text box next to the buttons and typing the page number.</span></span>

    -   <span data-ttu-id="8a656-141">Passare agli URL toccando i collegamenti ipertestuali aggiunti agli elementi del report, ad esempio caselle di testo, immagini, grafici e misuratori.</span><span class="sxs-lookup"><span data-stu-id="8a656-141">Navigate to URLs by taping hyperlinks that have been added to report items such as text boxes, images, charts, and gauges.</span></span>

    -   <span data-ttu-id="8a656-142">Esportare il report toccando l'icona di **Menu a discesa Esporta** e, successivamente, un formato di file.</span><span class="sxs-lookup"><span data-stu-id="8a656-142">Export the report by tapping the icon for the **Export drop down menu** and then tapping a file format.</span></span>

        -   <span data-ttu-id="8a656-143">Se si Visualizza il report in un dispositivo di Microsoft Surface, è possibile esportare il report in uno dei formati seguenti.</span><span class="sxs-lookup"><span data-stu-id="8a656-143">If you're viewing the report on a Microsoft Surface device, you can export the report to one of the following formats.</span></span>

            -   <span data-ttu-id="8a656-144">File XML con dati del report</span><span class="sxs-lookup"><span data-stu-id="8a656-144">XML file with report data</span></span>

            -   <span data-ttu-id="8a656-145">CSV (delimitato da virgole)</span><span class="sxs-lookup"><span data-stu-id="8a656-145">CSV (comma delimited)</span></span>

            -   <span data-ttu-id="8a656-146">PDF</span><span class="sxs-lookup"><span data-stu-id="8a656-146">PDF</span></span>

            -   <span data-ttu-id="8a656-147">MHTML (archivio Web)</span><span class="sxs-lookup"><span data-stu-id="8a656-147">MHTML (web archive)</span></span>

            -   <span data-ttu-id="8a656-148">Excel</span><span class="sxs-lookup"><span data-stu-id="8a656-148">Excel</span></span>

            -   <span data-ttu-id="8a656-149">TIFF</span><span class="sxs-lookup"><span data-stu-id="8a656-149">TIFF</span></span>

            -   <span data-ttu-id="8a656-150">Word</span><span class="sxs-lookup"><span data-stu-id="8a656-150">Word</span></span>

        -   <span data-ttu-id="8a656-151">Se si Visualizza il report in un iPad, è possibile esportare il report come file TIFF o PDF.</span><span class="sxs-lookup"><span data-stu-id="8a656-151">If you're viewing the report on an iPad, you can export the report as a TIFF or PDF file.</span></span>

## <a name="authentication"></a><span data-ttu-id="8a656-152">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="8a656-152">Authentication</span></span>
 <span data-ttu-id="8a656-153">L'autenticazione RSWindowsNTLM e l'autenticazione RSWindowsBasic possono essere utilizzate con [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in modalità nativa e con iPad.</span><span class="sxs-lookup"><span data-stu-id="8a656-153">RSWindowsNTLM authentication and RSWindowsBasic authentication work with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode and the iPad.</span></span>

 <span data-ttu-id="8a656-154">In genere, è consigliabile non utilizzare RSWindowsBasic in ambienti non https, poiché questo tipo di autenticazione non offre riservatezza per le credenziali trasmesse.</span><span class="sxs-lookup"><span data-stu-id="8a656-154">In general, it is recommended that RSWindowsBasic is not used in non-https environments because this type of authentication provides no confidentiality for the transmitted credentials.</span></span>

 <span data-ttu-id="8a656-155">Per ulteriori informazioni sui tipi di autenticazione RSWindowsNTLM e RSWindowsBasic, vedere [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="8a656-155">For more information about RSWindowsNTLM and RSWindowsBasic authentication, see [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span></span>

## <a name="uploading-reports"></a><span data-ttu-id="8a656-156">Caricamento di report</span><span class="sxs-lookup"><span data-stu-id="8a656-156">Uploading Reports</span></span>
 <span data-ttu-id="8a656-157">È possibile pubblicare i report da un dispositivo di Microsoft Surface utilizzando uno dei metodi seguenti, se si dispone delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="8a656-157">You can publish reports from a Microsoft Surface device using one of the following methods, if you have the appropriate permissions.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="8a656-158">Questi metodi non sono supportati sull'iPad.</span><span class="sxs-lookup"><span data-stu-id="8a656-158">These methods are not supported on the iPad.</span></span>

-   <span data-ttu-id="8a656-159">Caricare un file di definizione del report (con estensione rdl) in una raccolta documenti di SharePoint aprendo e toccando **Carica documento**.</span><span class="sxs-lookup"><span data-stu-id="8a656-159">Upload a report definition file (.rdl) to a SharePoint document library by opening the library and tapping **Upload Document**.</span></span>

-   <span data-ttu-id="8a656-160">Caricare un file di definizione del report nel database del server di report aprendo Gestione report e toccando **Carica file**.</span><span class="sxs-lookup"><span data-stu-id="8a656-160">Upload a report definition file to the report server database by opening Report Manager and tapping **Upload File**.</span></span>

## <a name="additional-information"></a><span data-ttu-id="8a656-161">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8a656-161">Additional Information</span></span>
 <span data-ttu-id="8a656-162">Per ulteriori informazioni su [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e sui browser supportati, vedere:</span><span class="sxs-lookup"><span data-stu-id="8a656-162">For more information on [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and supported browsers, see:</span></span>

-   [<span data-ttu-id="8a656-163">Pianificazione del supporto per Reporting Services e Power View browser &#40;Reporting Services 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="8a656-163">Planning for Reporting Services and Power View Browser Support &#40;Reporting Services 2014&#41;</span></span>](../../2014/reporting-services/browser-support-for-reporting-services-and-power-view.md)

 <span data-ttu-id="8a656-164">Per ulteriori informazioni su Microsoft Business Intelligence e sui dispositivi mobili, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a656-164">For more information on Microsoft Business Intelligence and Mobile devices, see the following:</span></span>

-   <span data-ttu-id="8a656-165">[Panoramica dei dispositivi mobili e di SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161351(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="8a656-165">[Overview of mobile devices and SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161351(v=office.15).aspx).</span></span>

-   <span data-ttu-id="8a656-166">[Browser per dispositivi mobili supportati in SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161353(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="8a656-166">[Supported mobile device browsers in SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161353(v=office.15).aspx).</span></span>

-   <span data-ttu-id="8a656-167">[Visualizzazione di report e scorecard in dispositivi Apple iPad (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) ( https://technet.microsoft.com/library/hh697482.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8a656-167">[Viewing reports and scorecards on Apple iPad devices (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) (https://technet.microsoft.com/library/hh697482.aspx).</span></span>

-   <span data-ttu-id="8a656-168">[Visualizzazione di Reporting Services report in un iPad (video)](https://technet.microsoft.com/sqlserver/jj873792.aspx) ( https://technet.microsoft.com/sqlserver/jj873792.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8a656-168">[Viewing Reporting Services Reports on an iPad (video)](https://technet.microsoft.com/sqlserver/jj873792.aspx) (https://technet.microsoft.com/sqlserver/jj873792.aspx).</span></span>

-   [<span data-ttu-id="8a656-169">Visualizzazione dei report di Reporting Services in un dispositivo di Microsoft Surface RT (video)</span><span class="sxs-lookup"><span data-stu-id="8a656-169">Viewing Reporting Services Reports on a Microsoft Surface RT Device (video)</span></span>](https://technet.microsoft.com/sqlserver/dn146017)


