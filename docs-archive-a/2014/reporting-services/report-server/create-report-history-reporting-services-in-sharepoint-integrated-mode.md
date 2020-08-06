---
title: Creare la cronologia dei report (Reporting Services in modalità integrata SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report history [Reporting Services], SharePoint
ms.assetid: e57ec746-05ae-4ff6-8e39-6cde87310daa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 996202580bbacc24080460c2c43218db27294d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630286"
---
# <a name="create-report-history-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="edb75-102">Creare la cronologia dei report (Reporting Services in modalità integrata SharePoint)</span><span class="sxs-lookup"><span data-stu-id="edb75-102">Create Report History (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="edb75-103">La cronologia di un report è una raccolta di snapshot del report creati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="edb75-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="edb75-104">Ogni snapshot è una copia del report nello stato in cui si trovava al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="edb75-104">Each snapshot is a copy of the report as it existed when it was created.</span></span> <span data-ttu-id="edb75-105">e include il layout e i dati del report aggiornati al momento della creazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="edb75-105">It includes the layout and data that was current for the report when the snapshot was created.</span></span> <span data-ttu-id="edb75-106">Le informazioni sul rendering non vengono archiviate con lo snapshot.</span><span class="sxs-lookup"><span data-stu-id="edb75-106">Rendering information is not stored with the snapshot.</span></span> <span data-ttu-id="edb75-107">Gli snapshot della cronologia del report vengono aperti in una pagina HTML nella web part Visualizzatore report.</span><span class="sxs-lookup"><span data-stu-id="edb75-107">When you open a snapshot in report history, it opens in HTML in the Report Viewer Web Part.</span></span> <span data-ttu-id="edb75-108">Dopo il rendering, lo snapshot può essere esportato in altri formati di applicazione.</span><span class="sxs-lookup"><span data-stu-id="edb75-108">After it is rendered, you can export it to other application formats.</span></span>  
  
 <span data-ttu-id="edb75-109">Per creare la cronologia del report, è necessario che il report possa essere eseguito automaticamente, ovvero che il server di report sia in grado di eseguire il report senza l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="edb75-109">To create report history, the report must be able to run unattended (that is, the report server must be able to run the report without user interaction).</span></span> <span data-ttu-id="edb75-110">È necessario disporre dell'autorizzazione Modifica elementi sulla raccolta che contiene il report.</span><span class="sxs-lookup"><span data-stu-id="edb75-110">You must have Edit Items permission on the library that contains the report.</span></span> <span data-ttu-id="edb75-111">Per visualizzare o eliminare la cronologia del report, è necessario disporre dell'autorizzazione Visualizzazione versioni o Eliminazione versioni.</span><span class="sxs-lookup"><span data-stu-id="edb75-111">To view or delete report history, you must have View Versions or Delete Versions permissions.</span></span>  
  
### <a name="to-create-a-snapshot-or-report-history-on-demand"></a><span data-ttu-id="edb75-112">Per creare uno snapshot o una cronologia del report su richiesta</span><span class="sxs-lookup"><span data-stu-id="edb75-112">To create a snapshot or report history on demand</span></span>  
  
1.  <span data-ttu-id="edb75-113">Selezionare il report.</span><span class="sxs-lookup"><span data-stu-id="edb75-113">Point to the report.</span></span>  
  
2.  <span data-ttu-id="edb75-114">Fare clic per visualizzare la freccia in giù e quindi selezionare **Visualizza cronologia report**.</span><span class="sxs-lookup"><span data-stu-id="edb75-114">Click to display the down arrow, and then select **View Report History**.</span></span>  
  
3.  <span data-ttu-id="edb75-115">Fare clic su **Nuovo snapshot**.</span><span class="sxs-lookup"><span data-stu-id="edb75-115">Click **New Snapshot**.</span></span> <span data-ttu-id="edb75-116">Se tale pulsante non è visualizzato, significa che non si dispone delle autorizzazioni necessarie per la creazione di snapshot nella cronologia del report.</span><span class="sxs-lookup"><span data-stu-id="edb75-116">If the button is not visible, it is because you do not have permission to create snapshots in report history.</span></span>  
  
4.  <span data-ttu-id="edb75-117">Per visualizzare lo snapshot appena creato, selezionarlo dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="edb75-117">To view the snapshot you just created, select it from the list.</span></span> <span data-ttu-id="edb75-118">Ogni snapshot è identificato da un timestamp che ne indica la data e l'ora di creazione.</span><span class="sxs-lookup"><span data-stu-id="edb75-118">Each snapshot is identified by a timestamp that shows when the snapshot was created.</span></span> <span data-ttu-id="edb75-119">Non è possibile rinominare lo snapshot, spostarlo in un altro percorso o modificarlo.</span><span class="sxs-lookup"><span data-stu-id="edb75-119">You cannot rename the snapshot, move it to another location, or modify it.</span></span>  
  
### <a name="to-schedule-report-history"></a><span data-ttu-id="edb75-120">Per pianificare la cronologia di un report</span><span class="sxs-lookup"><span data-stu-id="edb75-120">To schedule report history</span></span>  
  
1.  <span data-ttu-id="edb75-121">Selezionare il report.</span><span class="sxs-lookup"><span data-stu-id="edb75-121">Point to the report.</span></span>  
  
2.  <span data-ttu-id="edb75-122">Fare clic per visualizzare la freccia in giù e quindi selezionare **Gestisci opzioni di elaborazione**.</span><span class="sxs-lookup"><span data-stu-id="edb75-122">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="edb75-123">In **Opzioni snapshot cronologia**fare clic su **Crea snapshot della cronologia del report in base a una pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="edb75-123">In **History Snapshot Options**, click **Create report history snapshots on a schedule**.</span></span>  
  
4.  <span data-ttu-id="edb75-124">Se si dispone di una pianificazione condivisa che contiene le informazioni di pianificazione che si desidera usare, fare clic su **In base a una pianificazione condivisa** e selezionare la pianificazione da usare.</span><span class="sxs-lookup"><span data-stu-id="edb75-124">If you have a shared schedule that contains the schedule information you want to use, click **On a shared schedule** and select the schedule you want to use.</span></span> <span data-ttu-id="edb75-125">In caso contrario fare clic su **In base a una pianificazione personalizzata**, quindi su **Configura** per specificare le opzioni relative alla creazione della cronologia del report in base a una pianificazione ricorrente.</span><span class="sxs-lookup"><span data-stu-id="edb75-125">Otherwise, click **On a custom schedule**, and then click **Configure** to specify options to create report history on a recurring schedule.</span></span>  
  
### <a name="to-create-report-history-when-data-is-refreshed-in-a-report"></a><span data-ttu-id="edb75-126">Per creare la cronologia del report quando i dati del report vengono aggiornati</span><span class="sxs-lookup"><span data-stu-id="edb75-126">To create report history when data is refreshed in a report</span></span>  
  
1.  <span data-ttu-id="edb75-127">Selezionare il report.</span><span class="sxs-lookup"><span data-stu-id="edb75-127">Point to the report.</span></span>  
  
2.  <span data-ttu-id="edb75-128">Fare clic per visualizzare la freccia in giù e quindi selezionare **Gestisci opzioni di elaborazione**.</span><span class="sxs-lookup"><span data-stu-id="edb75-128">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="edb75-129">In **Opzioni snapshot cronologia**fare clic su **Archivia tutti gli snapshot di dati del report nella cronologia del report**.</span><span class="sxs-lookup"><span data-stu-id="edb75-129">In **History Snapshot Options**, click **Store all report data snapshots in report history**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb75-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edb75-130">See Also</span></span>  
 [<span data-ttu-id="edb75-131">Impostare le opzioni di elaborazione &#40;Reporting Services in modalità integrata SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="edb75-131">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
  
