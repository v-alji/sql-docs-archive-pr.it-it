---
title: Configurare le proprietà di esecuzione per un report (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- reports [Reporting Services], properties
- reports [Reporting Services], execution options
ms.assetid: 73cc8dcc-ef80-40d7-9739-d33bba0eb28a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51cd7b5db225b39f5a061ed750b2ef5cdd265b9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638265"
---
# <a name="configure-execution-properties-for-a-report--report-manager"></a><span data-ttu-id="c6f2c-102">Configurare le proprietà di esecuzione per un report (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="c6f2c-102">Configure Execution Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="c6f2c-103">È possibile impostare le opzioni di elaborazione di un report per specificare il momento in cui i dati vengono recuperati per un report specifico.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-103">You can set report processing options to specify when data is retrieved for a report.</span></span> <span data-ttu-id="c6f2c-104">Questa operazione risulta utile per pianificare l'elaborazione dei dati per un report se l'origine dati esterna viene aggiornata a intervalli stabiliti (ad esempio se un data warehouse viene aggiornato su base giornaliera o settimanale) e si desidera evitare l'overhead dovuto al recupero degli stessi dati ogni volta che un report viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-104">It is useful to schedule data processing for a report if the external data source is refreshed at specific times (for example, a data warehouse that is refreshed daily or weekly) and you want to avoid the overhead of retrieving the same data each time a report is requested.</span></span> <span data-ttu-id="c6f2c-105">La pianificazione dell'elaborazione dei dati è utile anche se si desidera controllare il carico di elaborazione nel server di database esterno o quando si desidera fornire risultati coerenti per più utenti che devono utilizzare set di dati identici.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-105">Scheduling data processing is also useful if you want to control the processing load on the external database server or when you want to provide consistent results for multiple users who must work with identical sets of data.</span></span> <span data-ttu-id="c6f2c-106">Con dati volatili, un report su richiesta può generare risultati diversi anche a differenza di pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-106">With volatile data, an on-demand report can produce different results from one minute to the next.</span></span> <span data-ttu-id="c6f2c-107">Uno snapshot del report, invece, consente di eseguire confronti validi con altri report o strumenti analitici contenenti dati riferiti allo stesso momento nel tempo.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-107">A report snapshot, by contrast, allows you to make valid comparisons against other reports or analytical tools that contain data from the same point in time.</span></span>  
  
 <span data-ttu-id="c6f2c-108">Il termine snapshot del report indica un report che include informazioni sul layout e i risultati di query recuperati in un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-108">A report snapshot is a report that contains layout instructions and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="c6f2c-109">Diversamente dai report su richiesta, per i quali vengono recuperati risultati di query aggiornati quando si seleziona il report, gli snapshot dei report vengono elaborati in base a una pianificazione e quindi salvati nel server di report.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-109">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="c6f2c-110">Quando si seleziona uno snapshot per la visualizzazione, il server di report recupera il report archiviato dal database del server di report e visualizza i dati e il layout del report aggiornati al momento della creazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-110">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
 <span data-ttu-id="c6f2c-111">Gli snapshot dei report non vengono salvati in un formato di rendering specifico,</span><span class="sxs-lookup"><span data-stu-id="c6f2c-111">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="c6f2c-112">ma ne viene eseguito il rendering nel formato di visualizzazione finale, ad esempio HTML, solo quando vengono richiesti da un utente o un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-112">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="c6f2c-113">Il rendering posticipato rende uno snapshot portabile.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-113">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="c6f2c-114">È possibile eseguire il rendering del report nel formato corretto per il dispositivo o il browser da cui proviene la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-114">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
### <a name="to-configure-report-processing-options"></a><span data-ttu-id="c6f2c-115">Per configurare le opzioni relative all'elaborazione dei report</span><span class="sxs-lookup"><span data-stu-id="c6f2c-115">To configure report processing options</span></span>  
  
1.  <span data-ttu-id="c6f2c-116">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c6f2c-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="c6f2c-117">Selezionare e aprire il report per il quale si desidera impostare le opzioni di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-117">Navigate to and open the report for which you want to set processing options.</span></span>  
  
 <span data-ttu-id="c6f2c-118">Passare con il puntatore del mouse sul report, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
1.  <span data-ttu-id="c6f2c-119">Scegliere **Gestisci** dal menu a discesa, quindi selezionare la scheda **Opzioni di elaborazione** .</span><span class="sxs-lookup"><span data-stu-id="c6f2c-119">In the drop-down menu, click **Manage** and then select the **Processing Options** tab.</span></span>  
  
2.  <span data-ttu-id="c6f2c-120">Fare clic su **Esegui il rendering del report da uno snapshot dell'esecuzione del report**, quindi selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6f2c-120">Click **Render this report from an execution snapshot, and then select one of the following options:**</span></span>  
  
    -   <span data-ttu-id="c6f2c-121">Se si desidera creare uno snapshot, selezionare **Usa la pianificazione seguente per creare snapshot dell'esecuzione del report**, quindi definire una pianificazione in base al report oppure selezionare un'opzione dall'elenco **Pianificazione condivisa** .</span><span class="sxs-lookup"><span data-stu-id="c6f2c-121">If you want to create a snapshot, select **Use the following schedule to create report execution snapshots**, and then either define a report-specific schedule or select from the **Shared schedule** list.</span></span>  
  
    -   <span data-ttu-id="c6f2c-122">Se si desidera creare immediatamente uno snapshot, selezionare **Crea uno snapshot del report quando viene scelto il pulsante Applica in questa pagina**.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-122">If you want to create a snapshot immediately, select **Create a report snapshot when you click the Apply button on this page**.</span></span>  
  
3.  <span data-ttu-id="c6f2c-123">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="c6f2c-123">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f2c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6f2c-124">See Also</span></span>  
 <span data-ttu-id="c6f2c-125">[Impostare le proprietà di elaborazione dei report](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c6f2c-125">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="c6f2c-126">[Aprire e chiudere un report &#40;Gestione report&#41;](../reports/open-and-close-a-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c6f2c-126">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) </span></span>  
 <span data-ttu-id="c6f2c-127">[Pagina Contenuto &#40;Gestione report&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c6f2c-127">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="c6f2c-128">[Gestione contenuto del server di report &#40;modalità nativa SSRS&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="c6f2c-128">[Report Server Content Management &#40;SSRS Native Mode&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="c6f2c-129">Pagina delle proprietà Opzioni di elaborazione &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="c6f2c-129">Processing Options Properties Page &#40;Report Manager&#41;</span></span>](../processing-options-properties-page-report-manager.md)  
  
  
