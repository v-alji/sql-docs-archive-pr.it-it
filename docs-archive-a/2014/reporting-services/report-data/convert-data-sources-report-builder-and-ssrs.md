---
title: Convertire un'origine dati da incorporata a condivisa (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
- data sources [Reporting Services], shared
ms.assetid: 0e099c7e-8c03-43eb-9ea3-76e52d9ebbe3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5827bab564b58e7a2b7922f01a33f550a6f523f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625165"
---
# <a name="convert-a-data-source-from-embedded-to-shared-report-builder-and-ssrs"></a><span data-ttu-id="3d76c-102">Convertire un'origine dati da incorporata a condivisa (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="3d76c-102">Convert a Data Source from Embedded to Shared (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3d76c-103">Ogni origine dati nel riquadro dei dati del report è incorporata e specifica del report oppure è condivisa.</span><span class="sxs-lookup"><span data-stu-id="3d76c-103">Each data source in the Report Data pane is embedded and specific to the report or is shared.</span></span> <span data-ttu-id="3d76c-104">In Generatore report un'origine dati condivisa punta a un'origine dati condivisa pubblicata in un server di report o in un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d76c-104">In Report Builder, a shared data source points to a published shared data source on a report server or SharePoint site.</span></span> <span data-ttu-id="3d76c-105">In Progettazione report un'origine dati condivisa punta a un'origine dati condivisa nella cartella **Origini dati condivise** di Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="3d76c-105">In Report Designer, a shared data source points to a shared data source in the **Shared Data Sources** folder in Solution Explorer.</span></span>  
  
 <span data-ttu-id="3d76c-106">Per altre informazioni sulle differenze tra origini dati incorporate e origini dati condivise, vedere [Connessioni dati o origini dati condivise e incorporate &#40;Generatore report e SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3d76c-106">For more information about the differences between embedded and shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="3d76c-107">Per altre informazioni sulla creazione di un'origine dati condivisa, vedere [Creare un'origine dati incorporata o condivisa &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3d76c-107">For more information on how to create a shared data source, see [Create an Embedded or Shared Data Source &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="report-designer"></a><span data-ttu-id="3d76c-108">Progettazione report</span><span class="sxs-lookup"><span data-stu-id="3d76c-108">Report Designer</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="3d76c-109">Per convertire un'origine dati da incorporata a condivisa</span><span class="sxs-lookup"><span data-stu-id="3d76c-109">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="3d76c-110">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sull'origine dati e quindi scegliere **Converti in origine dati condivisa**.</span><span class="sxs-lookup"><span data-stu-id="3d76c-110">In the Report Data pane, right-click the data source, and then click **Convert to Shared Data Source**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3d76c-111">Se il riquadro dei dati del report non è visualizzato, scegliere **Dati report** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="3d76c-111">If the Report Data pane is not visible, on the **View** menu, click **Report Data**.</span></span> <span data-ttu-id="3d76c-112">Se il riquadro è visualizzato come una finestra mobile, è possibile ancorarlo.</span><span class="sxs-lookup"><span data-stu-id="3d76c-112">If the pane opens as a floating window, you can dock it.</span></span> <span data-ttu-id="3d76c-113">Per altre informazioni, vedere [Ancorare il riquadro dei dati del report in Progettazione report &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3d76c-113">For more information, see [Dock the Report Data Pane in Report Designer &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span></span>  
  
     <span data-ttu-id="3d76c-114">Nel riquadro dei dati del report, l'icona dell'origine dati viene modificata nell'icona dell'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="3d76c-114">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span> <span data-ttu-id="3d76c-115">In Esplora soluzioni un'origine dati condivisa con lo stesso nome viene visualizzata nella cartella **Origini dati condivise** .</span><span class="sxs-lookup"><span data-stu-id="3d76c-115">In Solution Explorer, a shared data source with the same name appears under the **Shared Data Source** folder.</span></span>  
  
### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="3d76c-116">Per convertire un'origine dati da condivisa a incorporata</span><span class="sxs-lookup"><span data-stu-id="3d76c-116">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="3d76c-117">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sull'origine dati, aprire la finestra di dialogo **Proprietà origine dati** e quindi fare clic su **Connessione incorporata**.</span><span class="sxs-lookup"><span data-stu-id="3d76c-117">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="3d76c-118">Immettere le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="3d76c-118">Enter the required information.</span></span>  
  
     <span data-ttu-id="3d76c-119">Nel riquadro dei dati del report, l'icona dell'origine dati viene modificata nell'icona dell'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="3d76c-119">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="report-builder"></a><span data-ttu-id="3d76c-120">Generatore report</span><span class="sxs-lookup"><span data-stu-id="3d76c-120">Report Builder</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="3d76c-121">Per convertire un'origine dati da incorporata a condivisa</span><span class="sxs-lookup"><span data-stu-id="3d76c-121">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="3d76c-122">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sull'origine dati per aprire la finestra di dialogo **Proprietà origine dati** e quindi fare clic su **Connessione incorporata**.</span><span class="sxs-lookup"><span data-stu-id="3d76c-122">In the Report Data pane, right-click the data source to open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="3d76c-123">Immettere le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="3d76c-123">Enter the required information.</span></span>  
  
     <span data-ttu-id="3d76c-124">Nel riquadro dei dati del report, l'icona dell'origine dati viene modificata nell'icona dell'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="3d76c-124">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
#### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="3d76c-125">Per convertire un'origine dati da condivisa a incorporata</span><span class="sxs-lookup"><span data-stu-id="3d76c-125">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="3d76c-126">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sull'origine dati, aprire la finestra di dialogo **Proprietà origine dati** e quindi fare clic su **Connessione incorporata**.</span><span class="sxs-lookup"><span data-stu-id="3d76c-126">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="3d76c-127">Immettere le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="3d76c-127">Enter the required information.</span></span>  
  
     <span data-ttu-id="3d76c-128">Nel riquadro dei dati del report, l'icona dell'origine dati viene modificata nell'icona dell'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="3d76c-128">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d76c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d76c-129">See Also</span></span>  
 <span data-ttu-id="3d76c-130">[Gestire origini dati dei report](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="3d76c-130">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="3d76c-131">Connessioni dati, origini dati e stringhe di connessione in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3d76c-131">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
