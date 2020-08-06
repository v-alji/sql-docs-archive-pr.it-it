---
title: Precaricare la cache (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- cache [Reporting Services]
- preloading cache
ms.assetid: 152a1051-8aa5-4c01-bc85-f8be8971b0cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b60b74f7ab5c0c843b848c09ee574fd59a99c682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716087"
---
# <a name="preload-the-cache-report-manager"></a><span data-ttu-id="45c88-102">Precaricare la cache (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="45c88-102">Preload the Cache (Report Manager)</span></span>
  <span data-ttu-id="45c88-103">Per precaricare la cache per un set di dati condiviso, è possibile creare un piano di aggiornamento della cache per il set di dati stesso.</span><span class="sxs-lookup"><span data-stu-id="45c88-103">You can preload the cache for a shared dataset by creating a cache refresh plan for the shared dataset.</span></span>  
  
 <span data-ttu-id="45c88-104">Di seguito vengono indicate le due modalità di precaricamento della cache.</span><span class="sxs-lookup"><span data-stu-id="45c88-104">You can preload the cache for a report in two ways:</span></span>  
  
1.  <span data-ttu-id="45c88-105">Creazione di un piano di aggiornamento della cache per il report</span><span class="sxs-lookup"><span data-stu-id="45c88-105">Create a cache refresh plan for the report.</span></span> <span data-ttu-id="45c88-106">Questo è il metodo preferito.</span><span class="sxs-lookup"><span data-stu-id="45c88-106">This is the preferred method.</span></span>  
  
2.  <span data-ttu-id="45c88-107">Utilizzo di una sottoscrizione guidata dai dati per il precaricamento della cache con istanze di report con parametri.</span><span class="sxs-lookup"><span data-stu-id="45c88-107">Use a data-driven subscription to preload the cache with instances of parameterized reports.</span></span> <span data-ttu-id="45c88-108">Questo metodo consente di precaricare la cache solo in versioni di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] precedenti a [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45c88-108">This was the only way to preload the cache in versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] earlier than [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="45c88-109">Per altre informazioni, vedere [Memorizzazione dei report nella cache &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="45c88-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
 <span data-ttu-id="45c88-110">Per memorizzare nella cache un report o un set di dati condiviso, è necessario che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="45c88-110">The following conditions must be met before you can cache a report or a shared dataset:</span></span>  
  
-   <span data-ttu-id="45c88-111">Il set di dati condiviso o il report deve essere abilitato per la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="45c88-111">The shared dataset or the report must have caching enabled.</span></span>  
  
-   <span data-ttu-id="45c88-112">Le origini dati condivise per il set di dati condiviso o il report devono essere configurate per l'utilizzo di credenziali archiviate o di nessuna credenziale.</span><span class="sxs-lookup"><span data-stu-id="45c88-112">The shared data sources for the shared dataset or the report must be configured to use stored credentials or no credentials.</span></span>  
  
-   <span data-ttu-id="45c88-113">È necessario che il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="45c88-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service must be running.</span></span>  
  
### <a name="to-preload-the-cache-by-creating-a-cache-refresh-plan"></a><span data-ttu-id="45c88-114">Per precaricare la cache creando un piano di aggiornamento della cache</span><span class="sxs-lookup"><span data-stu-id="45c88-114">To preload the cache by creating a cache refresh plan</span></span>  
  
1.  <span data-ttu-id="45c88-115">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="45c88-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="45c88-116">In Gestione report passare alla pagina **Contenuto** e quindi passare all'elemento che si vuole memorizzare nella cache.</span><span class="sxs-lookup"><span data-stu-id="45c88-116">In Report Manager, navigate to the **Contents** page, and then navigate to the item that you want to cache.</span></span>  
  
3.  <span data-ttu-id="45c88-117">Posizionarsi sull'elemento e quindi fare clic sull'elenco a discesa e selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="45c88-117">Hover over the item, click the drop-down list, and then click **Manage**.</span></span>  
  
4.  <span data-ttu-id="45c88-118">Fare clic sulla scheda **Opzioni di aggiornamento cache** .</span><span class="sxs-lookup"><span data-stu-id="45c88-118">Click the **Cache Refresh Options** tab.</span></span>  
  
5.  <span data-ttu-id="45c88-119">Sulla barra degli strumenti fare clic su **Nuovo piano di aggiornamento della cache**.</span><span class="sxs-lookup"><span data-stu-id="45c88-119">On the toolbar, click **New Cache Refresh Plan**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="45c88-120">Se per l'elemento la memorizzazione nella cache non è abilitata, verrà richiesto di abilitarla.</span><span class="sxs-lookup"><span data-stu-id="45c88-120">If the item does not have caching enabled, you will be prompted to enable caching.</span></span> <span data-ttu-id="45c88-121">Per abilitare la memorizzazione nella cache, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="45c88-121">To enable caching, click **OK**.</span></span>  
  
     <span data-ttu-id="45c88-122">Verrà visualizzata la pagina Piano di aggiornamento della cache.</span><span class="sxs-lookup"><span data-stu-id="45c88-122">The Cache Refresh Plan page opens.</span></span>  
  
6.  <span data-ttu-id="45c88-123">Se si desidera, digitare una descrizione per il piano di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="45c88-123">Optionally type a description for the refresh plan.</span></span>  
  
7.  <span data-ttu-id="45c88-124">Per una pianificazione condivisa, fare clic su **Pianificazione condivisa**e quindi selezionare il nome della pianificazione da usare.</span><span class="sxs-lookup"><span data-stu-id="45c88-124">For a shared schedule, click **Shared schedule**, and then select the name of the schedule to use.</span></span>  
  
     <span data-ttu-id="45c88-125">Per una pianificazione personalizzata, fare clic su **Pianificazione specifica dell'elemento**e quindi fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="45c88-125">For a custom schedule, click **Item-specific schedule**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="45c88-126">Configurare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="45c88-126">Configure the schedule</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-preload-the-cache-with-a-user-specific-report-by-using-a-data-driven-subscription"></a><span data-ttu-id="45c88-127">Per precaricare la cache con un report specifico dell'utente tramite una sottoscrizione guidata dai dati</span><span class="sxs-lookup"><span data-stu-id="45c88-127">To preload the cache with a user-specific report by using a data-driven subscription</span></span>  
  
1.  <span data-ttu-id="45c88-128">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="45c88-128">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="45c88-129">In Gestione report passare alla pagina **Contenuto** e quindi al report per il quale si vuole creare una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="45c88-129">In Report Manager, navigate to the **Contents** page, and then navigate to the report you want to create a subscription for.</span></span>  
  
3.  <span data-ttu-id="45c88-130">Fare clic sul report e quindi sulla scheda **Sottoscrizioni** e su **Nuova sottoscrizione guidata dai dati**.</span><span class="sxs-lookup"><span data-stu-id="45c88-130">Click the report, click the **Subscriptions** tab, and then click **New Data-Driven Subscription**.</span></span>  
  
4.  <span data-ttu-id="45c88-131">Se lo si desidera, digitare una descrizione per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="45c88-131">Optionally type a description for the subscription.</span></span>  
  
5.  <span data-ttu-id="45c88-132">Selezionare **Provider recapito Null** dall'elenco **Specificare la modalità di notifica ai destinatari**.</span><span class="sxs-lookup"><span data-stu-id="45c88-132">From the **Specify how recipients are notified** list, select **Null Delivery Provider**.</span></span>  
  
6.  <span data-ttu-id="45c88-133">Per configurare un'origine dati, specificare un tipo di origine dati e quindi fare clic su **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="45c88-133">Specify a data source type and then click **Next** to configure the data source.</span></span>  
  
7.  <span data-ttu-id="45c88-134">Specificare il tipo di connessione, la stringa di connessione e le credenziali per l'accesso all'origine dei dati che contiene i dati relativi ai sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="45c88-134">Specify the connection type, connection string, and credentials for accessing the data source that contains subscriber data.</span></span> <span data-ttu-id="45c88-135">Nell'esempio seguente viene illustrata una stringa di connessione utilizzata per la connessione al database Subscribers di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="45c88-135">The following example illustrates a connection string used to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database called Subscribers:</span></span>  
  
    ```  
    data source=<servername>; initial catalog=Subscribers  
    ```  
  
8.  <span data-ttu-id="45c88-136">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="45c88-136">Click **Next**.</span></span>  
  
9. <span data-ttu-id="45c88-137">Specificare la query o il comando per il recupero dei dati relativi ai sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="45c88-137">Specify the query or command that retrieves subscriber data.</span></span> <span data-ttu-id="45c88-138">Se lo si desidera, aumentare il periodo di timeout per le query che richiedono un'elaborazione prolungata.</span><span class="sxs-lookup"><span data-stu-id="45c88-138">Optionally increase the time-out period for queries that take a long time to process.</span></span> <span data-ttu-id="45c88-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="45c88-139">For example:</span></span>  
  
    ```  
    Select * from UserInfo  
    ```  
  
10. <span data-ttu-id="45c88-140">Fare clic su **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="45c88-140">Click **Validate**.</span></span> <span data-ttu-id="45c88-141">È necessario convalidare la query prima di proseguire.</span><span class="sxs-lookup"><span data-stu-id="45c88-141">The query must be validated before you continue.</span></span> <span data-ttu-id="45c88-142">Quando viene visualizzato il messaggio **Query convalidata** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="45c88-142">When the **Query validated successfully** message appears, click **Next**.</span></span>  
  
11. <span data-ttu-id="45c88-143">Poiché non è possibile configurare le impostazioni dell'estensione per il recapito per il provider recapito Null, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="45c88-143">Because you cannot configure delivery extension settings for the null delivery provider, click **Next**.</span></span>  
  
12. <span data-ttu-id="45c88-144">Specificare i valori dei parametri del report per la sottoscrizione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="45c88-144">Specify report parameter values for the subscription, and click **Next**.</span></span>  
  
13. <span data-ttu-id="45c88-145">Specificare quando viene elaborata la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="45c88-145">Specify when the subscription is processed.</span></span> <span data-ttu-id="45c88-146">Non fare clic su **Quando i dati del report vengono aggiornati nel server di report**.</span><span class="sxs-lookup"><span data-stu-id="45c88-146">Do not choose **When the report data is updated on the report server**.</span></span> <span data-ttu-id="45c88-147">Questa impostazione è solo per gli snapshot.</span><span class="sxs-lookup"><span data-stu-id="45c88-147">That setting is for snapshots only.</span></span> <span data-ttu-id="45c88-148">Se si vuole usare una pianificazione preesistente, selezionare **In base a una pianificazione condivisa**.</span><span class="sxs-lookup"><span data-stu-id="45c88-148">If want to use a pre-existing schedule, select **On a shared schedule**.</span></span>  
  
     <span data-ttu-id="45c88-149">In alternativa, per creare una pianificazione personalizzata fare clic su **In base a una pianificazione creata per questa sottoscrizione** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="45c88-149">Or, to create a custom schedule, click **On a schedule created for this subscription** and then click **Next**.</span></span> <span data-ttu-id="45c88-150">Configurare la pianificazione e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="45c88-150">Configure the schedule and then click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="45c88-151">Perché i sottoscrittori possano ricevere il report più recente, è necessario che la pianificazione configurata dall'utente sia coerente con la pianificazione di recapito del report che è stata definita per i sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="45c88-151">In order for the subscribers to receive the newest report, the schedule that you configure should be consistent with the report delivery schedule that you have defined for the subscribers.</span></span> <span data-ttu-id="45c88-152">Per altre informazioni, vedere [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="45c88-152">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
14. <span data-ttu-id="45c88-153">Configurare le opzioni di esecuzione del report come segue.</span><span class="sxs-lookup"><span data-stu-id="45c88-153">Configure the Execution options for the report as follows.</span></span> <span data-ttu-id="45c88-154">Nella pagina del report fare clic sulla scheda **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="45c88-154">On the report page, click the **Properties** tab.</span></span>  
  
15. <span data-ttu-id="45c88-155">Nel riquadro a sinistra fare clic sulla scheda **Esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="45c88-155">In the left frame, click the **Execution** tab.</span></span>  
  
16. <span data-ttu-id="45c88-156">Nella pagina scegliere **Esegui il rendering del report con i dati più recenti**.</span><span class="sxs-lookup"><span data-stu-id="45c88-156">On the page, select **Render this report with the most recent data**.</span></span>  
  
17. <span data-ttu-id="45c88-157">Selezionare una delle due opzioni della cache e configurare la scadenza come segue:</span><span class="sxs-lookup"><span data-stu-id="45c88-157">Choose one of the following two cache options and configure the expiration as follows:</span></span>  
  
    -   <span data-ttu-id="45c88-158">Per impostare la scadenza della copia memorizzata nella cache dopo un determinato periodo di tempo, fare clic su **Memorizza nella cache una copia temporanea del report. La copia del report scadrà dopo il numero di minuti seguente.**</span><span class="sxs-lookup"><span data-stu-id="45c88-158">To make the cached copy expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes.**</span></span> <span data-ttu-id="45c88-159">Digitare il numero di minuti alla scadenza del report.</span><span class="sxs-lookup"><span data-stu-id="45c88-159">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="45c88-160">Per impostare la scadenza della copia memorizzata nella cache in base a una pianificazione, fare clic su **Memorizza nella cache una copia temporanea del report. La scadenza della copia è determinata dalla pianificazione seguente.**</span><span class="sxs-lookup"><span data-stu-id="45c88-160">To make the cached copy expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="45c88-161">Per impostare una pianificazione per la scadenza del report, fare clic su **Configura**oppure selezionare una pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="45c88-161">Click **Configure**, or select a shared schedule to set a schedule for report expiration.</span></span>  
  
18. <span data-ttu-id="45c88-162">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="45c88-162">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c88-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45c88-163">See Also</span></span>  
 <span data-ttu-id="45c88-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="45c88-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="45c88-165">[Creare una sottoscrizione guidata dai dati &#40;esercitazione su SSRS&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="45c88-165">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="45c88-166">[Prestazioni, snapshot, memorizzazione nella cache &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="45c88-166">[Performance, Snapshots, Caching &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span></span>  
 <span data-ttu-id="45c88-167">[Impostare le proprietà di elaborazione dei report](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="45c88-167">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="45c88-168">Memorizzazione dei report nella cache &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="45c88-168">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
