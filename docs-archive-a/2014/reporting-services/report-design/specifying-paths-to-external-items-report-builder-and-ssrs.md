---
title: Specifica di percorsi di elementi esterni (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4fe513da-f3c5-479c-9fec-8662b91a0d6d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 097a3566f914e7810039ee07bc3d3bf3185d7f06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623770"
---
# <a name="specifying-paths-to-external-items-report-builder-and-ssrs"></a><span data-ttu-id="22d02-102">Specifica di percorsi di elementi esterni (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="22d02-102">Specifying Paths to External Items (Report Builder and SSRS)</span></span>
  <span data-ttu-id="22d02-103">Nelle proprietà degli elementi del report è possibile specificare percorsi che facciano riferimento a elementi esterni al file di definizione del report archiviati in un server di report, ad esempio report drill-through, sottoreport e file di immagini.</span><span class="sxs-lookup"><span data-stu-id="22d02-103">You specify paths in report item properties to reference items such as drillthrough reports, subreports, and image files that are external to the report definition file and are stored on a report server.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="22d02-104">In Generatore report i percorsi degli elementi devono specificare elementi presenti in un server di report.</span><span class="sxs-lookup"><span data-stu-id="22d02-104">In Report Builder, paths to items must specify items on a report server.</span></span> <span data-ttu-id="22d02-105">I percorsi degli elementi di un file system non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="22d02-105">Paths to items on a file system are not supported.</span></span> <span data-ttu-id="22d02-106">È possibile visualizzare in anteprima un report che utilizza questi elementi solo se si è connessi al server di report in cui si trovano gli elementi.</span><span class="sxs-lookup"><span data-stu-id="22d02-106">You can preview a report that uses these items only if you are connected to the report server where the items are located.</span></span>  
  
 <span data-ttu-id="22d02-107">Quando si specifica un percorso di un elemento esterno in una finestra di dialogo relativa ad azioni, sottoreport o immagini, è possibile passare direttamente al server di report e selezionare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="22d02-107">When you specify a path for an external item in a dialog box for actions, subreports, or images, you can browse directly to the report server and select the item.</span></span> <span data-ttu-id="22d02-108">Per specificare un report drill-through o un sottoreport è consigliabile individuare e selezionare l'elemento direttamente dal server di report.</span><span class="sxs-lookup"><span data-stu-id="22d02-108">Browsing to an item and selecting it directly is the recommended way to specify a drillthrough report or subreport.</span></span> <span data-ttu-id="22d02-109">In questo modo, quando si specificano i parametri del report o del sottoreport, i nomi di parametro corretti risulteranno disponibili in un elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="22d02-109">That way the correct parameter names will be available in a drop-down list when you specify report or subreport parameters.</span></span> <span data-ttu-id="22d02-110">Se si modifica il percorso di un elemento in modo che punti a un altro elemento, è necessario aggiornare manualmente i valori e i nomi dei parametri nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="22d02-110">When you change an item path to point to a different item, you must manually update the correct parameter names and values as needed.</span></span>  
  
 <span data-ttu-id="22d02-111">In un server di report configurato in modalità nativa, specificare un nome di report drill-through senza l'estensione di file rdl.</span><span class="sxs-lookup"><span data-stu-id="22d02-111">On a report server configured in native mode, specify a drillthrough report name without the file extension .rdl.</span></span>  
  
 <span data-ttu-id="22d02-112">In un server di report configurato in modalità integrata SharePoint, è necessario includere l'estensione di file rdl.</span><span class="sxs-lookup"><span data-stu-id="22d02-112">On a report server configured in SharePoint integrated mode, you must include the file extension .rdl.</span></span> <span data-ttu-id="22d02-113">Il percorso può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="22d02-113">The path can be one of the following:</span></span>  
  
-   <span data-ttu-id="22d02-114">**Un percorso relativo dell'elemento del report principale,**</span><span class="sxs-lookup"><span data-stu-id="22d02-114">**A relative path to the item from the main report.**</span></span> <span data-ttu-id="22d02-115">ad esempio ../TuttiSottoreport/Sottoreport1.</span><span class="sxs-lookup"><span data-stu-id="22d02-115">For example, ../AllSubreports/Subreport1.</span></span> <span data-ttu-id="22d02-116">In questo esempio i puntini di sospensione **..**</span><span class="sxs-lookup"><span data-stu-id="22d02-116">In this example, the **..**</span></span> <span data-ttu-id="22d02-117">indicano la cartella di livello superiore rispetto a quella in cui si trova il report principale.</span><span class="sxs-lookup"><span data-stu-id="22d02-117">indicates the folder above the folder where the main report is located.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22d02-118">Quando il report viene eseguito in Generatore report, i percorsi relativi non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="22d02-118">Relative paths are not supported when the report is run inside Report Builder.</span></span> <span data-ttu-id="22d02-119">Per visualizzare un report che utilizza percorsi relativi di elementi esterni, salvare il report nel server di report ed eseguirlo da tale server.</span><span class="sxs-lookup"><span data-stu-id="22d02-119">To view a report that uses relative paths to external items, save the report to the report server, and run the report from there</span></span>  
  
-   <span data-ttu-id="22d02-120">**Un percorso completo dell'elemento.**</span><span class="sxs-lookup"><span data-stu-id="22d02-120">**A full path to the item.**</span></span>  
  
    -   <span data-ttu-id="22d02-121">**Nel server di report:** Un percorso completo inizia da **/** la cartella Home,</span><span class="sxs-lookup"><span data-stu-id="22d02-121">**On a report server:** The path starts from **/**, the Home folder.</span></span> <span data-ttu-id="22d02-122">ad esempio /Report/TuttiSottoreport/Sottoreport1.</span><span class="sxs-lookup"><span data-stu-id="22d02-122">For example, /Reports/AllSubreports/Subreport1.</span></span>  
  
    -   <span data-ttu-id="22d02-123">**In un sito di SharePoint** È necessario specificare il nome del report in un'espressione, includendo l'URL completo dell'elemento e l'estensione di file rdl,</span><span class="sxs-lookup"><span data-stu-id="22d02-123">**On a SharePoint site:** You must specify the report name in an expression, with the full URL of the item and the file extension .rdl.</span></span> <span data-ttu-id="22d02-124">Ad esempio: `="http://server/site/library/folder/Report1.rdl"`.</span><span class="sxs-lookup"><span data-stu-id="22d02-124">For example, `="http://server/site/library/folder/Report1.rdl"`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d02-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22d02-125">See Also</span></span>  
 <span data-ttu-id="22d02-126">[Aggiungere un'immagine esterna &#40;Generatore report e SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="22d02-126">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="22d02-127">[Aggiungere un sottoreport e parametri &#40;Generatore report e SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="22d02-127">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="22d02-128">Aggiungere un'azione drill-through a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="22d02-128">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
