---
title: Pagina memorizzazione nella cache, set di impostazioni condivisi (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eac372e9-d2a1-48a8-bbe5-09d101df16ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62d899964911a6f2d35e59d49d925ff80013af42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628516"
---
# <a name="caching-page-shared-datasets-report-manager"></a><span data-ttu-id="1154b-102">Pagina Memorizzazione nella cache, set di dati condivisi (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="1154b-102">Caching Page, Shared Datasets (Report Manager)</span></span>
  <span data-ttu-id="1154b-103">La pagina delle proprietà di memorizzazione nella cache consente di impostare le opzioni di cache per un set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="1154b-103">Use the Caching properties page to set the cache options for a shared dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1154b-104">Questa funzionalità non è disponibile in ogni edizione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1154b-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1154b-105">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="1154b-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="1154b-106">Spostamento</span><span class="sxs-lookup"><span data-stu-id="1154b-106">Navigation</span></span>  
 <span data-ttu-id="1154b-107">Utilizzare la procedura riportata di seguito per spostarsi in questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1154b-107">Use the following procedure to navigate to this location in the user interface.</span></span>  
  
### <a name="to-open-the-caching-properties-page-for-a-shared-dataset"></a><span data-ttu-id="1154b-108">Per aprire la pagina delle proprietà per la memorizzazione nella cache per un set di dati condiviso</span><span class="sxs-lookup"><span data-stu-id="1154b-108">To open the Caching properties page for a shared dataset</span></span>  
  
1.  <span data-ttu-id="1154b-109">Aprire Gestione report, quindi individuare il report per il quale si desidera configurare le proprietà del set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="1154b-109">Open Report Manager, and locate the report for which you want to configure shared dataset properties.</span></span>  
  
2.  <span data-ttu-id="1154b-110">Posizionare il puntatore del mouse sul set di dati condiviso, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="1154b-110">Point to the shared dataset, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="1154b-111">Nell'elenco a discesa fare clic su **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="1154b-111">In the drop-down list, click **Manage**.</span></span> <span data-ttu-id="1154b-112">Viene visualizzata la pagina delle proprietà Generale per il report.</span><span class="sxs-lookup"><span data-stu-id="1154b-112">The General properties page for the report opens.</span></span>  
  
4.  <span data-ttu-id="1154b-113">Fare clic sulla scheda **Memorizzazione nella cache** .</span><span class="sxs-lookup"><span data-stu-id="1154b-113">Click the **Caching** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1154b-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1154b-114">Options</span></span>  
 <span data-ttu-id="1154b-115">**Memorizza nella cache set di dati condiviso**</span><span class="sxs-lookup"><span data-stu-id="1154b-115">**Cache shared dataset**</span></span>  
 <span data-ttu-id="1154b-116">Consente di posizionare nella cache una copia temporanea dei dati alla prima apertura da parte di un utente di un report che utilizza questo set di dati.</span><span class="sxs-lookup"><span data-stu-id="1154b-116">Places a temporary copy of the data in a cache when a user first opens a report that uses this shared dataset.</span></span> <span data-ttu-id="1154b-117">Gli utenti che eseguono successivamente il report durante il periodo di memorizzazione nella cache riceveranno la copia dei dati memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="1154b-117">Subsequent users who run the report within the caching period receive the cached copy of the data.</span></span> <span data-ttu-id="1154b-118">La memorizzazione nella cache consente in genere di migliorare le prestazioni in quanto i dati vengono restituiti dalla cache anziché tramite una nuova query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="1154b-118">Caching usually improves performance because the data is returned from the cache instead of running the dataset query again.</span></span>  
  
 <span data-ttu-id="1154b-119">**Memorizza nella cache una copia temporanea del report. La copia del report scadrà dopo il numero di minuti seguente**</span><span class="sxs-lookup"><span data-stu-id="1154b-119">**Expire the cache after a number of minutes**</span></span>  
 <span data-ttu-id="1154b-120">Specificare il numero di minuti per il salvataggio della copia memorizzata nella cache dei dati.</span><span class="sxs-lookup"><span data-stu-id="1154b-120">Specify the number of minutes to save the cached copy of the data.</span></span> <span data-ttu-id="1154b-121">Dopo la scadenza della copia temporanea i dati non vengono più restituiti dalla cache.</span><span class="sxs-lookup"><span data-stu-id="1154b-121">As soon as a temporary copy expires, the data is no longer returned from the cache.</span></span> <span data-ttu-id="1154b-122">Alla successiva apertura di un report che utilizza questo set di dati condiviso da parte di un utente, viene eseguita la query del set di dati e il server di report memorizza nella cache una copia dei dati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="1154b-122">The next time a user opens a report that uses this shared dataset, the dataset query runs and the report server places a copy of the refreshed data back in the cache.</span></span>  
  
 <span data-ttu-id="1154b-123">**Scadenza cache basata sulla pianificazione seguente**</span><span class="sxs-lookup"><span data-stu-id="1154b-123">**Expire the cache on the following schedule**</span></span>  
 <span data-ttu-id="1154b-124">Consente di pianificare l'ora in cui i dati memorizzati nella cache non sono più validi e vengono rimossi dalla stessa.</span><span class="sxs-lookup"><span data-stu-id="1154b-124">Schedule the time when the cached data is no longer valid and is removed from the cache.</span></span> <span data-ttu-id="1154b-125">La pianificazione può essere una pianificazione condivisa o specifica del set di dati condiviso corrente.</span><span class="sxs-lookup"><span data-stu-id="1154b-125">The schedule can be a shared schedule or one that is specific for only the current shared dataset.</span></span>  
  
 <span data-ttu-id="1154b-126">**Pianificazione specifica del set di dati**</span><span class="sxs-lookup"><span data-stu-id="1154b-126">**Dataset-specific schedule**</span></span>  
 <span data-ttu-id="1154b-127">Consente di specificare una pianificazione utilizzata solo per questo set di dati.</span><span class="sxs-lookup"><span data-stu-id="1154b-127">Specify a schedule that is used only by this dataset.</span></span>  
  
 <span data-ttu-id="1154b-128">**Pianificazione condivisa**</span><span class="sxs-lookup"><span data-stu-id="1154b-128">**Shared schedule**</span></span>  
 <span data-ttu-id="1154b-129">Consente di specificare una pianificazione condivisa fra report, sottoscrizioni e altri set di dati condivisi.</span><span class="sxs-lookup"><span data-stu-id="1154b-129">Specify a schedule that is shared among reports, subscriptions, and other shared datasets.</span></span>  
  
 <span data-ttu-id="1154b-130">**Applica**</span><span class="sxs-lookup"><span data-stu-id="1154b-130">**Apply**</span></span>  
 <span data-ttu-id="1154b-131">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1154b-131">Save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1154b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1154b-132">See Also</span></span>  
 <span data-ttu-id="1154b-133">[Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="1154b-133">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="1154b-134">[Guida sensibile al contesto Gestione report](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1154b-134">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="1154b-135">[Memorizzare nella cache i set di impostazioni &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1154b-135">[Cache Shared Datasets &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="1154b-136">Pianificazioni</span><span class="sxs-lookup"><span data-stu-id="1154b-136">Schedules</span></span>](subscriptions/schedules.md)  
  
  
