---
title: Verificare la disponibilità di aggiornamenti o disattivare gli aggiornamenti (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9c69792d-d7c4-453b-ae2f-6d2d071d8606
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 088d41e71d770f746367f2760cff8ff67b15623c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628502"
---
# <a name="check-for-updates-or-turn-updates-off-report-builder-and-ssrs"></a><span data-ttu-id="142d4-102">Verificare o disattivare gli aggiornamenti (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="142d4-102">Check for Updates or Turn Updates Off (Report Builder and SSRS)</span></span>
  <span data-ttu-id="142d4-103">Ogni volta che si apre un report, Generatore report consente di verificare se le istanze pubblicate delle parti del report in tale report sono state aggiornate nel server di report o nel sito di SharePoint integrato con un server di report.</span><span class="sxs-lookup"><span data-stu-id="142d4-103">Every time you open a report, Report Builder checks to see if the published instances of report parts in that report have been updated on the report server or SharePoint site integrated with a report server.</span></span> <span data-ttu-id="142d4-104">Consente di verificare inoltre le modifiche negli elementi dipendenti delle parti di report, ad esempio nel set di dati e nei parametri.</span><span class="sxs-lookup"><span data-stu-id="142d4-104">It also checks for changes in the report parts' dependent items, such as the dataset and parameters.</span></span> <span data-ttu-id="142d4-105">Se qualsiasi parte di report o le relative dipendenze sono state aggiornate sul sito o sul server, in una barra informazioni del report in uso viene visualizzato il numero di parti aggiornate.</span><span class="sxs-lookup"><span data-stu-id="142d4-105">If any report parts or their dependencies have been updated on the site or server, an information bar in your report displays the number of updated parts.</span></span> <span data-ttu-id="142d4-106">È possibile scegliere di visualizzare e accettare, o rifiutare, gli aggiornamenti oppure di ignorare la barra informazioni.</span><span class="sxs-lookup"><span data-stu-id="142d4-106">You can choose to view and accept or reject the updates, or dismiss the information bar.</span></span>  
  
 <span data-ttu-id="142d4-107">Tale barra può inoltre essere disabilitata e non essere quindi informati su eventuali modifiche apportate alle istanze pubblicate di parti di report.</span><span class="sxs-lookup"><span data-stu-id="142d4-107">You can also disable the information bar and not be informed if published instances of report parts have changed.</span></span> <span data-ttu-id="142d4-108">Questa impostazione viene eseguita dall'utente e sarà disabilitata per tutti i report aperti.</span><span class="sxs-lookup"><span data-stu-id="142d4-108">This is a user setting; it will be disabled for all reports that you open.</span></span> <span data-ttu-id="142d4-109">Anche se la barra informazioni è stata disabilitata, è ancora possibile verificare gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="142d4-109">Even if you have disabled the information bar, you can still check for updates.</span></span>  
  
### <a name="to-turn-on-and-off-report-part-updates"></a><span data-ttu-id="142d4-110">Per attivare e disattivare gli aggiornamenti delle parti di report</span><span class="sxs-lookup"><span data-stu-id="142d4-110">To turn on and off report part updates</span></span>  
  
1.  <span data-ttu-id="142d4-111">Fare clic sul pulsante Generatore report, quindi su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="142d4-111">Click the Report Builder button, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="142d4-112">Nella scheda **risorse** della finestra di dialogo **Opzioni** selezionare o deselezionare la casella di controllo **Mostra aggiornamenti per parti del report in report personali** .</span><span class="sxs-lookup"><span data-stu-id="142d4-112">In the **Options** dialog box, on the **Resources** tab, select or clear the **Show updates to report parts in my reports** check box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="142d4-113">Questa impostazione viene eseguita dall'utente</span><span class="sxs-lookup"><span data-stu-id="142d4-113">This is a user setting.</span></span> <span data-ttu-id="142d4-114">e sarà disabilitata per tutti i report aperti.</span><span class="sxs-lookup"><span data-stu-id="142d4-114">It will be disabled for all reports that you open.</span></span>  
  
### <a name="to-check-for-updates"></a><span data-ttu-id="142d4-115">Per verificare gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="142d4-115">To check for updates</span></span>  
  
-   <span data-ttu-id="142d4-116">Fare clic con il pulsante destro del mouse sull'area di progettazione all'esterno del report oppure nel corpo del report, quindi scegliere **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="142d4-116">Right-click the design surface outside the report, or in the report body, and click **Check for Updates**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142d4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="142d4-117">See Also</span></span>  
 <span data-ttu-id="142d4-118">[Parti del report &#40;Generatore report e SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="142d4-118">[Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="142d4-119">[Pubblicare e ripubblicare parti del report &#40;Generatore report e SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="142d4-119">[Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="142d4-120">[Individuare le parti del report e impostare una cartella predefinita &#40;Generatore report e SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="142d4-120">[Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="142d4-121">[Risolvere i problemi relativi alle parti del report &#40;Generatore report e SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="142d4-121">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="142d4-122">Parti del report e set di dati in Generatore report</span><span class="sxs-lookup"><span data-stu-id="142d4-122">Report Parts and Datasets in Report Builder</span></span>](report-data/report-parts-and-datasets-in-report-builder.md)  
  
  
