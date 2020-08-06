---
title: Associare un report o un modello a un'origine dati condivisa (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
ms.assetid: 23cc15f2-2883-48e2-bc6c-fa0ab61a2e21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 596caba042d476173b3c49d1ad18e79d0827fe89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713880"
---
# <a name="bind-a-report-or-model-to-a-shared-data-source-ssrs"></a><span data-ttu-id="5ce72-102">Associare un report o un modello a un'origine dati condivisa (SSRS)</span><span class="sxs-lookup"><span data-stu-id="5ce72-102">Bind a Report or Model to a Shared Data Source (SSRS)</span></span>
  <span data-ttu-id="5ce72-103">In alcune situazioni, ad esempio quando si sposta un report o un modello da un server di test a uno di produzione, potrebbe essere necessario salvare il file nel computer locale e quindi caricarlo in un altro server di report.</span><span class="sxs-lookup"><span data-stu-id="5ce72-103">In some situations, such as when you move a report or model from a test server to a production server, you might want to save the file to your local computer and then upload it to a different report server.</span></span> <span data-ttu-id="5ce72-104">Quando si carica il report o il modello nel nuovo server, è necessario riassociarlo a un'origine dei dati condivisa archiviata nel nuovo server di report.</span><span class="sxs-lookup"><span data-stu-id="5ce72-104">When you upload the report or model to the new server, you need to rebind it to a shared data source that is stored on the new report server.</span></span> <span data-ttu-id="5ce72-105">Se il report o il modello non viene riassociato, non funzionerà correttamente quando vi si accede dal nuovo server di report.</span><span class="sxs-lookup"><span data-stu-id="5ce72-105">If you don't rebind the report or model, it will not work correctly when accessed from the new report server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5ce72-106">Per poter riassociare un report o un modello a un'origine dei dati condivisa, quest'ultima deve esistere già nel server di report o nella raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ce72-106">Before rebinding a report or model to a shared data source, the data source must already exist on the report server or SharePoint library.</span></span> <span data-ttu-id="5ce72-107">Per altre informazioni sulle origini dati, vedere [Creare, modificare ed eliminare origini dati condivise &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5ce72-107">For more information about data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-native-mode"></a><span data-ttu-id="5ce72-108">Per associare un report o un modello a un'origine dei dati condivisa in un server di report in esecuzione in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="5ce72-108">To bind a report or model to a shared data source on a report server running in native mode</span></span>  
  
1.  <span data-ttu-id="5ce72-109">In **Gestione report**fare clic sul nome del report o del modello caricato nel server.</span><span class="sxs-lookup"><span data-stu-id="5ce72-109">In **Report Manager**, click the name of the report or model that you uploaded to the server.</span></span>  
  
     <span data-ttu-id="5ce72-110">Verrà aperta la scheda Proprietà.</span><span class="sxs-lookup"><span data-stu-id="5ce72-110">The Properties tab opens.</span></span>  
  
2.  <span data-ttu-id="5ce72-111">Fare clic su **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="5ce72-111">Click **Data Sources**.</span></span>  
  
3.  <span data-ttu-id="5ce72-112">Fare clic su **Sfoglia**e quindi individuare l'origine dati a cui si vuole associare il report o il modello.</span><span class="sxs-lookup"><span data-stu-id="5ce72-112">Click **Browse**, and then navigate to the data source to which you want to bind the report or model.</span></span>  
  
4.  <span data-ttu-id="5ce72-113">Selezionare l'origine dati e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ce72-113">Select the data source and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="5ce72-114">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="5ce72-114">Click **Apply**.</span></span>  
  
     <span data-ttu-id="5ce72-115">Il report o il modello verrà quindi associato all'origine dei dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="5ce72-115">The report or model is now bound to the data source that you selected.</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-sharepoint-integrated-mode"></a><span data-ttu-id="5ce72-116">Per associare un report o un modello a un'origine dei dati condivisa in un server di report in esecuzione in modalità integrata SharePoint</span><span class="sxs-lookup"><span data-stu-id="5ce72-116">To bind a report or model to a shared data source on a report server running in SharePoint integrated mode</span></span>  
  
1.  <span data-ttu-id="5ce72-117">Se la raccolta non è già aperta, fare clic sul suo nome sulla barra di avvio veloce.</span><span class="sxs-lookup"><span data-stu-id="5ce72-117">If the library is not already open, click its name on the Quick Launch bar.</span></span> <span data-ttu-id="5ce72-118">Se il nome della raccolta non è visualizzato, fare clic su **Visualizza tutto il contenuto del sito**e quindi sul nome della raccolta desiderata.</span><span class="sxs-lookup"><span data-stu-id="5ce72-118">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="5ce72-119">Selezionare il report o il modello e fare clic sulla freccia verso il basso.</span><span class="sxs-lookup"><span data-stu-id="5ce72-119">Point to the report or model and click the down arrow.</span></span>  
  
3.  <span data-ttu-id="5ce72-120">Fare clic su **Gestisci origini dati**.</span><span class="sxs-lookup"><span data-stu-id="5ce72-120">Click **Manage Data Sources**.</span></span>  
  
4.  <span data-ttu-id="5ce72-121">Fare clic su **dataSource1**.</span><span class="sxs-lookup"><span data-stu-id="5ce72-121">Click **dataSource1**.</span></span>  
  
5.  <span data-ttu-id="5ce72-122">Nell'area **Tipo di connessione** verificare che **Origine dati condivisa** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="5ce72-122">In the **Connection Type** area, verify that **Shared data source** is selected.</span></span>  
  
6.  <span data-ttu-id="5ce72-123">Nell'area **Collegamento origine dati** fare clic sul pulsante con i puntini di sospensione (...).</span><span class="sxs-lookup"><span data-stu-id="5ce72-123">In the **Data Source Link** area, click the ellipsis (...) button.</span></span>  
  
7.  <span data-ttu-id="5ce72-124">Individuare l'origine dei dati da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5ce72-124">Locate the data source you want to use.</span></span>  
  
8.  <span data-ttu-id="5ce72-125">Selezionare l'origine dati e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ce72-125">Select the data source and **click OK**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="5ce72-126">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="5ce72-126">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce72-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ce72-127">See Also</span></span>  
 <span data-ttu-id="5ce72-128">[Caricare un file o un report &#40;Gestione report&#41;](../reports/upload-a-file-or-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="5ce72-128">[Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md) </span></span>  
 <span data-ttu-id="5ce72-129">[Caricare documenti in una raccolta di SharePoint &#40;Reporting Services in modalità SharePoint&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="5ce72-129">[Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="5ce72-130">[Creare e gestire origini dati condivise &#40;Reporting Services in modalità integrata SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span><span class="sxs-lookup"><span data-stu-id="5ce72-130">[Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span></span>  
 <span data-ttu-id="5ce72-131">[Creare, eliminare o modificare un'origine dati condivisa &#40;Gestione report&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="5ce72-131">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="5ce72-132">[Connessioni dati, origini dati e stringhe di connessione in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="5ce72-132">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="5ce72-133">Origini dei dati supportate da Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5ce72-133">Data Sources Supported by Reporting Services &#40;SSRS&#41;</span></span>](../create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
