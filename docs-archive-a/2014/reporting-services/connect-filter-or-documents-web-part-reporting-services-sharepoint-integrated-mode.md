---
title: Connettere la Web part filtro o documenti (Reporting Services in modalità integrata SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Filter Web Part [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
- Documents Web Part [Reporting Services]
ms.assetid: 6a303135-c0ef-44cd-a423-1cea8df3dcf3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5ea7b9f9aba128052ae6ac7f05ef40517eb50e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626041"
---
# <a name="connect-filter-or-documents-web-part-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="f4d41-102">Connettere una web part Filtro o Documenti (Reporting Services in modalità integrata SharePoint)</span><span class="sxs-lookup"><span data-stu-id="f4d41-102">Connect Filter or Documents Web Part (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="f4d41-103">Se si utilizza un prodotto SharePoint, è possibile creare un dashboard o una pagina web part in cui sono incluse una web part di filtro o una web part Documenti e una web part Visualizzatore report.</span><span class="sxs-lookup"><span data-stu-id="f4d41-103">If you are using a SharePoint product, you can create a dashboard or Web Part Page that includes a Filter Web Part or Documents Web part and a Report Viewer Web Part.</span></span> <span data-ttu-id="f4d41-104">Le versioni supportate sono [!INCLUDE[SPF2010](../includes/spf2010-md.md)] o [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4d41-104">Supported versions are [!INCLUDE[SPF2010](../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span></span> <span data-ttu-id="f4d41-105">Sono anche supportate le versioni [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] e [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span><span class="sxs-lookup"><span data-stu-id="f4d41-105">Also supported are [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] or [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span></span> <span data-ttu-id="f4d41-106">Se si connette una web part di filtro, quando l'utente seleziona un valore di filtro in una web part di filtro, tale valore verrà inviato a un report con parametri nella stessa pagina.</span><span class="sxs-lookup"><span data-stu-id="f4d41-106">By connecting a Filter Web Part, users who select filter values in a Filter Web Part can send the value to a parameterized report on the same page.</span></span> <span data-ttu-id="f4d41-107">Se si connette una web part Documenti, quando l'utente fa clic su un report disponibile nella raccolta Documenti, tale report verrà visualizzato in una web part Visualizzatore report adiacente.</span><span class="sxs-lookup"><span data-stu-id="f4d41-107">By connecting a Documents Web Part, users who click on reports in the Documents library can view the report in an adjacent Report Viewer Web Part.</span></span>  
  
 <span data-ttu-id="f4d41-108">La web part di filtro consente di inviare valori a uno o più parametri di un report.</span><span class="sxs-lookup"><span data-stu-id="f4d41-108">The Filter Web Part is used to send values to one or more parameters on a report.</span></span> <span data-ttu-id="f4d41-109">È possibile utilizzare una web part di filtro solo con i report per cui sono definiti parametri compatibili con i valori, il tipo di dati e il formato inviati dalla web part.</span><span class="sxs-lookup"><span data-stu-id="f4d41-109">To use a Filter Web Part, the report must have parameters defined for it that are compatible with the values, data type, and format sent by the Web Part.</span></span>  
  
 <span data-ttu-id="f4d41-110">La web part Documenti è associata alla raccolta Documenti del sito principale.</span><span class="sxs-lookup"><span data-stu-id="f4d41-110">The Documents Web Part is associated with the Documents library of the Home site.</span></span> <span data-ttu-id="f4d41-111">Per visualizzare, aggiungere o rimuovere elementi dalla raccolta Documenti, fare clic su **Visualizza tutto il contenuto del sito**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-111">To view, add, or remove items from the Documents library, click **View All Site Content**.</span></span> <span data-ttu-id="f4d41-112">In Raccolte fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-112">In Libraries, click **Documents**.</span></span> <span data-ttu-id="f4d41-113">Per gestire gli elementi della raccolta Documenti, è possibile usare i menu **Nuovo**, **Carica**e **Azioni** .</span><span class="sxs-lookup"><span data-stu-id="f4d41-113">You can use the **New**, **Upload**, and **Actions** menu to manage the items in the Documents library.</span></span>  
  
### <a name="to-connect-a-filter-web-part"></a><span data-ttu-id="f4d41-114">Per connettere una web part di filtro</span><span class="sxs-lookup"><span data-stu-id="f4d41-114">To connect a Filter Web Part</span></span>  
  
1.  <span data-ttu-id="f4d41-115">Aprire o creare il dashboard o la pagina web part.</span><span class="sxs-lookup"><span data-stu-id="f4d41-115">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="f4d41-116">Scegliere **Modifica pagina** dal menu **Azioni sito**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-116">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="f4d41-117">Fare clic su **Aggiungi web part**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-117">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="f4d41-118">In **tutti i Web part**, nella categoria **varie** selezionare **SQL Server Reporting Services Visualizzatore report**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-118">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="f4d41-119">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-119">Click **Add**.</span></span> <span data-ttu-id="f4d41-120">La web part verrà aggiunta nella parte superiore dell'area.</span><span class="sxs-lookup"><span data-stu-id="f4d41-120">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="f4d41-121">In un'altra area dello stesso dashboard o pagina web part fare clic su **Aggiungi web part**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-121">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
7.  <span data-ttu-id="f4d41-122">Nella sezione **Filtri**di **Tutte le web part** selezionare una web part.</span><span class="sxs-lookup"><span data-stu-id="f4d41-122">In **All Web Parts**, in the **Filters** section, select a Web Part.</span></span>  
  
8.  <span data-ttu-id="f4d41-123">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-123">Click **Add**.</span></span> <span data-ttu-id="f4d41-124">La web part verrà aggiunta nella parte superiore dell'area.</span><span class="sxs-lookup"><span data-stu-id="f4d41-124">The Web Part is added at the top of the zone.</span></span>  
  
9. <span data-ttu-id="f4d41-125">Nell'area che contiene la web part fare clic sul menu **Modifica** della web part, scegliere **Connessioni**, **Send Filter Values To**(Invia valori filtro a), quindi **Visualizzatore report** - *nome report*.</span><span class="sxs-lookup"><span data-stu-id="f4d41-125">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Send Filter Values To**, and then select **Report Viewer** - *report name*.</span></span>  
  
10. <span data-ttu-id="f4d41-126">Archiviare le modifiche e salvare la pagina.</span><span class="sxs-lookup"><span data-stu-id="f4d41-126">Check in your changes and save the page.</span></span>  
  
### <a name="to-connect-a-documents-web-part"></a><span data-ttu-id="f4d41-127">Per connettere una web part Documenti</span><span class="sxs-lookup"><span data-stu-id="f4d41-127">To connect a Documents Web Part</span></span>  
  
1.  <span data-ttu-id="f4d41-128">Aprire o creare il dashboard o la pagina web part.</span><span class="sxs-lookup"><span data-stu-id="f4d41-128">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="f4d41-129">Scegliere **Modifica pagina** dal menu **Azioni sito**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-129">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="f4d41-130">Fare clic su **Aggiungi web part**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-130">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="f4d41-131">Nella sezione **Elenchi e raccolte**di **Tutte le web part** selezionare **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-131">In **All Web Parts**, in the **Lists and Library** section, select **Documents.**</span></span>  
  
5.  <span data-ttu-id="f4d41-132">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-132">Click **Add**.</span></span> <span data-ttu-id="f4d41-133">La web part verrà aggiunta nella parte superiore dell'area.</span><span class="sxs-lookup"><span data-stu-id="f4d41-133">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="f4d41-134">Fare clic sul pulsante **Applica** , disponibile nella parte inferiore del riquadro Strumenti, e quindi scegliere **OK** per chiudere il riquadro.</span><span class="sxs-lookup"><span data-stu-id="f4d41-134">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
7.  <span data-ttu-id="f4d41-135">In un'altra area dello stesso dashboard o pagina web part fare clic su **Aggiungi web part**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-135">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
8.  <span data-ttu-id="f4d41-136">Nella categoria **Varie**di **Tutte le web part** selezionare **Visualizzatore report di SQL Server Reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="f4d41-136">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer.**</span></span>  
  
9. <span data-ttu-id="f4d41-137">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-137">Click **Add**.</span></span> <span data-ttu-id="f4d41-138">La web part verrà aggiunta nella parte superiore dell'area.</span><span class="sxs-lookup"><span data-stu-id="f4d41-138">The Web Part is added at the top of the zone.</span></span>  
  
10. <span data-ttu-id="f4d41-139">Nell'area che contiene la web part fare clic sul menu **Modifica** della web part, scegliere **Connessioni**, **Get report definitions from**(Recupera definizioni report da), quindi **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="f4d41-139">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Get report definitions from**, and then select **Documents**.</span></span>  
  
11. <span data-ttu-id="f4d41-140">Archiviare le modifiche e salvare la pagina.</span><span class="sxs-lookup"><span data-stu-id="f4d41-140">Check in your changes and save the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d41-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4d41-141">See Also</span></span>  
 <span data-ttu-id="f4d41-142">[Aggiungere la Web part Visualizzatore report a una pagina Web &#40;Reporting Services in modalità integrata SharePoint&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="f4d41-142">[Add the Report Viewer Web Part to a Web Page &#40;Reporting Services in SharePoint Integrated Mode&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="f4d41-143">[Web part Visualizzatore report in un sito di SharePoint](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="f4d41-143">[Report Viewer Web Part on a SharePoint Site](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="f4d41-144">Personalizzare la Web part Visualizzatore report</span><span class="sxs-lookup"><span data-stu-id="f4d41-144">Customize the Report Viewer Web Part</span></span>](../../2014/reporting-services/customize-the-report-viewer-web-part.md)  
  
  
