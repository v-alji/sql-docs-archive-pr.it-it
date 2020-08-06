---
title: Memorizzare un report nella cache (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- cache [Reporting Services]
- cached reports [Reporting Services]
- schedules [Reporting Services], report expiration
- expiration [Reporting Services]
ms.assetid: 723d1cb0-c2e7-4763-8690-a6a7a8bbbb90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e359e6c7a40b267979137ef2b3a285667a6fdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630315"
---
# <a name="cache-a-report-report-manager"></a><span data-ttu-id="f7a40-102">Memorizzare un report nella cache (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="f7a40-102">Cache a Report (Report Manager)</span></span>
  <span data-ttu-id="f7a40-103">Per ottimizzare le prestazioni, è possibile configurare le proprietà relative alla memorizzazione nella cache per un report.</span><span class="sxs-lookup"><span data-stu-id="f7a40-103">One way to improve performance is to configure caching properties for a report.</span></span> <span data-ttu-id="f7a40-104">Quando un report viene memorizzato nella cache, una copia del report visualizzabile viene salvata per un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="f7a40-104">When a report is cached, a copy of the rendered report is saved for a short period of time.</span></span> <span data-ttu-id="f7a40-105">Il primo utente che richiede il report deve attendere il completamento di tutte le elaborazioni prima di visualizzare il report.</span><span class="sxs-lookup"><span data-stu-id="f7a40-105">The first user who requests the report must wait for all processing to complete before viewing the report.</span></span> <span data-ttu-id="f7a40-106">Gli utenti successivi che richiedono il report all'interno del periodo di memorizzazione nella cache possono visualizzarlo immediatamente perché l'elaborazione è già stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="f7a40-106">Subsequent users who request the report within the caching period can view it right away because processing has already occurred.</span></span>  
  
 <span data-ttu-id="f7a40-107">Sono presenti restrizioni sui tipi di report che è possibile memorizzare nella cache.</span><span class="sxs-lookup"><span data-stu-id="f7a40-107">There are restrictions on the types of reports that you can cache.</span></span> <span data-ttu-id="f7a40-108">Ad esempio, un report non può essere memorizzato nella cache se l'output del report varia in base all'identità utente o se i dati vengono recuperati utilizzando il token di sicurezza dell'utente che richiede il report.</span><span class="sxs-lookup"><span data-stu-id="f7a40-108">For example, a report cannot be cached if report output varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="f7a40-109">Per altre informazioni, vedere [Memorizzazione dei report nella cache &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f7a40-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="f7a40-110">Per pianificare la scadenza di un report memorizzato nella cache</span><span class="sxs-lookup"><span data-stu-id="f7a40-110">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="f7a40-111">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="f7a40-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="f7a40-112">In Gestione report passare alla pagina **Contenuto** .</span><span class="sxs-lookup"><span data-stu-id="f7a40-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="f7a40-113">quindi passare al report per il quale si desidera impostare le proprietà relative alla memorizzazione nella cache, posizionare il puntatore del mouse sull'elemento e fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="f7a40-113">Navigate to the report for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="f7a40-114">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="f7a40-114">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="f7a40-115">Nel riquadro di sinistra fare clic sulla scheda **Opzioni di elaborazione**.</span><span class="sxs-lookup"><span data-stu-id="f7a40-115">In the left frame, click the **Processing Options**.</span></span>  
  
5.  <span data-ttu-id="f7a40-116">Nella pagina scegliere **Eseguire sempre questo report con i dati più recenti**.</span><span class="sxs-lookup"><span data-stu-id="f7a40-116">On the page, select **Always run this report with the most recent data**.</span></span>  
  
6.  <span data-ttu-id="f7a40-117">Selezionare una delle due opzioni cache seguenti e configurare la scadenza come segue:</span><span class="sxs-lookup"><span data-stu-id="f7a40-117">Select one of the following two cache options and configure expiration as follows:</span></span>  
  
    -   <span data-ttu-id="f7a40-118">Per configurare una copia memorizzata nella cache in modo che scada dopo un periodo di tempo specifico, fare clic su **Memorizza nella cache una copia temporanea del report. La copia del report scadrà dopo il numero di minuti seguente**.</span><span class="sxs-lookup"><span data-stu-id="f7a40-118">To configure a cached copy to expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes**.</span></span> <span data-ttu-id="f7a40-119">Digitare il numero di minuti alla scadenza del report.</span><span class="sxs-lookup"><span data-stu-id="f7a40-119">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="f7a40-120">Per configurare una copia memorizzata nella cache affinché scada in base a una pianificazione, fare clic su **Memorizza nella cache una copia temporanea del report. La scadenza della copia è determinata dalla pianificazione seguente.**</span><span class="sxs-lookup"><span data-stu-id="f7a40-120">To configure a cached copy to expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="f7a40-121">Fare clic su **Configura**oppure selezionare una pianificazione condivisa per controllare la scadenza del report.</span><span class="sxs-lookup"><span data-stu-id="f7a40-121">Click **Configure**, or select a shared schedule to control report expiration</span></span>  
  
7.  <span data-ttu-id="f7a40-122">Fare clic su **Apply**.</span><span class="sxs-lookup"><span data-stu-id="f7a40-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a40-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7a40-123">See Also</span></span>  
 <span data-ttu-id="f7a40-124">[Impostare proprietà di elaborazione dei report](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f7a40-124">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="f7a40-125">Memorizzazione dei report nella cache &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f7a40-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
