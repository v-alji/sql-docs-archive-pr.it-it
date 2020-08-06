---
title: Aggiungere la Web part Visualizzatore report a una pagina Web (Reporting Services in modalità integrata SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], viewing reports
- Web Parts [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
ms.assetid: cac75345-2380-467d-a394-0a2140908a5a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d9b933fad8bc566b3cb0ef04303a85c5f034e620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721102"
---
# <a name="add-the-report-viewer-web-part-to-a-web-page-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="f1136-102">Aggiungere la web part Visualizzatore report a una pagina Web (Reporting Services in modalità integrata SharePoint)</span><span class="sxs-lookup"><span data-stu-id="f1136-102">Add the Report Viewer Web Part to a Web Page (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="f1136-103">È possibile utilizzare la web part Visualizzatore report per visualizzare report eseguiti in un server di report configurato per l'esecuzione in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f1136-103">You can use the Report Viewer Web Part to view reports that run on report server that is configured to run in SharePoint integrated mode.</span></span> <span data-ttu-id="f1136-104">Questa web part può essere utilizzata per visualizzare i file di definizione dei report (con estensione rdl) creati in Generatore report o Progettazione report e caricati in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="f1136-104">You can use the Web Part to display report definition (.rdl) files that you created in Report Builder or Report Designer and uploaded to a library.</span></span>  
  
 <span data-ttu-id="f1136-105">È possibile aggiungere la web part Visualizzatore report a una pagina Web se si desidera incorporare un report nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f1136-105">You can add the Report Viewer Web Part to a Web page if you want to embed a report on that page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1136-106">Sebbene abbiano lo stesso nome, la web part Visualizzatore report installata tramite il componente aggiuntivo di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è diversa dalla web part Visualizzatore report inclusa nel file RSWebParts.cab.</span><span class="sxs-lookup"><span data-stu-id="f1136-106">Although they have identical names, the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in is different from the Report Viewer Web Part that is included in the RSWebParts.cab file.</span></span> <span data-ttu-id="f1136-107">Le istruzioni contenute in questo argomento sono specifiche della web part visualizzatore di report installata attraverso il componente aggiuntivo [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1136-107">The instructions in this topic are specifically for the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
 <span data-ttu-id="f1136-108">Per aggiungere una web part a una pagina Web, è necessario disporre dell'autorizzazione Aggiunta e personalizzazione pagine a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="f1136-108">To add a Web Part to a Web page, you must have the Add and Customize Pages permission at the site level.</span></span> <span data-ttu-id="f1136-109">Se si usano impostazioni di sicurezza predefinite, questa autorizzazione è concessa ai membri del gruppo **Proprietari** che hanno il livello di autorizzazione Controllo completo.</span><span class="sxs-lookup"><span data-stu-id="f1136-109">If you are using default security settings, this permission is granted to members of the **Owners** group who have the Full Control level of permission.</span></span>  
  
### <a name="to-embed-a-report-in-a-web-page"></a><span data-ttu-id="f1136-110">Per incorporare un report in una pagina Web</span><span class="sxs-lookup"><span data-stu-id="f1136-110">To embed a report in a Web page</span></span>  
  
1.  <span data-ttu-id="f1136-111">Aprire o creare il dashboard o la pagina web part.</span><span class="sxs-lookup"><span data-stu-id="f1136-111">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="f1136-112">Nella pagina **Azioni sito**fare clic su **Modifica pagina**.</span><span class="sxs-lookup"><span data-stu-id="f1136-112">On **Site Actions**, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="f1136-113">Fare clic su **Aggiungi web part**.</span><span class="sxs-lookup"><span data-stu-id="f1136-113">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="f1136-114">Nell'elenco delle categorie di web part selezionare la categoria **Varie** e quindi selezionare **Visualizzatore report di SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="f1136-114">In the list of web part categories, select the **Miscellaneous** category, and then select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="f1136-115">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f1136-115">Click **Add**.</span></span> <span data-ttu-id="f1136-116">La web part verrà aggiunta nella parte superiore dell'area.</span><span class="sxs-lookup"><span data-stu-id="f1136-116">The Web Part is added at the top of the zone.</span></span> <span data-ttu-id="f1136-117">È possibile trascinarla in una posizione diversa all'interno dell'area.</span><span class="sxs-lookup"><span data-stu-id="f1136-117">You can drag it to a different location in the zone.</span></span>  
  
6.  <span data-ttu-id="f1136-118">Nel visualizzatore fare clic su **Fare clic qui per aprire il riquadro Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="f1136-118">Within the viewer, click **Click here to open the tool pane**.</span></span>  
  
7.  <span data-ttu-id="f1136-119">Fare clic sul pulsante per la ricerca (**...**) e selezionare un report da una raccolta della raccolta siti corrente.</span><span class="sxs-lookup"><span data-stu-id="f1136-119">Select a report from any library in the current site collection by clicking the browse (**...**) button.</span></span> <span data-ttu-id="f1136-120">In alternativa è possibile digitare l'URL del report.</span><span class="sxs-lookup"><span data-stu-id="f1136-120">You can also type the report URL.</span></span> <span data-ttu-id="f1136-121">Per determinare l'URL di un report, fare clic con il pulsante destro del mouse sul report e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f1136-121">To determine the URL for any report, right-click the report and select **Properties**.</span></span> <span data-ttu-id="f1136-122">Non fare clic sulla freccia verso il basso visualizzata accanto al report. L'URL del report non è indicato nella pagina Visualizza proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="f1136-122">Do not click the down arrow next to the report; the report URL is not indicated in the View Properties page of the item.</span></span> <span data-ttu-id="f1136-123">Se si copia e si incolla l'URL dalla finestra di dialogo **Proprietà** , sostituire con uno spazio tutte le occorrenze del codice "%20" presenti nell'URL. Ad esempio, modificare "Vendite%20azienda" in "Vendite azienda".</span><span class="sxs-lookup"><span data-stu-id="f1136-123">If you copy and paste the URL from the **Properties** dialog box, replace the "%20" URL encoding with a space (for example, "Company%20Sales" should be "Company Sales").</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f1136-124">Ogni web part Visualizzatore report può contenere un solo report.</span><span class="sxs-lookup"><span data-stu-id="f1136-124">Each Report Viewer Web Part contains a single report.</span></span> <span data-ttu-id="f1136-125">L'URL deve essere costituito dal percorso completo di un report presente nel sito di SharePoint corrente oppure in un sito disponibile nella stessa farm o applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="f1136-125">The URL must be the fully qualified path to a report that is on the current SharePoint site, or on a site within the same Web application or farm.</span></span> <span data-ttu-id="f1136-126">L'URL deve corrispondere a una raccolta documenti o a una cartella all'interno della raccolta documenti che contiene il report</span><span class="sxs-lookup"><span data-stu-id="f1136-126">The URL must resolve to a document library or to a folder within a document library that contains the report.</span></span> <span data-ttu-id="f1136-127">e deve includere l'estensione rdl del file.</span><span class="sxs-lookup"><span data-stu-id="f1136-127">The report URL must include the .rdl file extension.</span></span> <span data-ttu-id="f1136-128">Se il report dipende da un file modello o di origine dati condivisa, non sarà necessario specificare tali file nell'URL,</span><span class="sxs-lookup"><span data-stu-id="f1136-128">If the report depends on a model or shared data source files, you do not need to specify those files in the URL.</span></span> <span data-ttu-id="f1136-129">perché il report contiene riferimenti a tutti i file necessari.</span><span class="sxs-lookup"><span data-stu-id="f1136-129">The report contains references to the files it needs.</span></span>  
  
8.  <span data-ttu-id="f1136-130">Quando il riquadro Strumenti è aperto è possibile impostare alcune proprietà per modificare il layout e l'aspetto predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f1136-130">While the tool pane is open, you can set properties to modify the default appearance and layout.</span></span>  
  
9. <span data-ttu-id="f1136-131">Fare clic sul pulsante **Applica** , disponibile nella parte inferiore del riquadro Strumenti, e quindi scegliere **OK** per chiudere il riquadro.</span><span class="sxs-lookup"><span data-stu-id="f1136-131">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1136-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1136-132">See Also</span></span>  
 <span data-ttu-id="f1136-133">[Web part Visualizzatore report in un sito di SharePoint](../report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="f1136-133">[Report Viewer Web Part on a SharePoint Site](../report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 <span data-ttu-id="f1136-134">[Personalizzare la Web part Visualizzatore report](../customize-the-report-viewer-web-part.md) </span><span class="sxs-lookup"><span data-stu-id="f1136-134">[Customize the Report Viewer Web Part](../customize-the-report-viewer-web-part.md) </span></span>  
 <span data-ttu-id="f1136-135">[Concessione di autorizzazioni per elementi del server di report in un sito di SharePoint](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="f1136-135">[Granting Permissions on Report Server Items on a SharePoint Site](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="f1136-136">Installare o disinstallare il componente aggiuntivo Reporting Services per SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="f1136-136">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](../install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
