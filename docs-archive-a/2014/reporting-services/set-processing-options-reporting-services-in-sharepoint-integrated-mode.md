---
title: Impostare le opzioni di elaborazione (Reporting Services in modalità integrata SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], content management
- snapshots [Reporting Services], creating
ms.assetid: 453b19a1-739a-4b67-aeea-2069b52204e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8c33b205a702d4ab77abf74154232990da9840b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716067"
---
# <a name="set-processing-options-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="e6d50-102">Impostare le opzioni di elaborazione (Reporting Services in modalità integrata SharePoint)</span><span class="sxs-lookup"><span data-stu-id="e6d50-102">Set Processing Options (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="e6d50-103">È possibile impostare le opzioni di elaborazione di un report [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] per determinare il momento in cui deve avvenire l'elaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e6d50-103">You can set processing options on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report to determine when data processing occurs.</span></span> <span data-ttu-id="e6d50-104">È inoltre possibile impostare un valore di timeout per l'elaborazione del report e opzioni che determinano se attivare o meno la cronologia del report per il report corrente.</span><span class="sxs-lookup"><span data-stu-id="e6d50-104">You can also set a time-out value for report processing, and options that determine whether report history is enabled for the current report.</span></span>  
  
-   <span data-ttu-id="e6d50-105">È possibile eseguire un report come snapshot per evitare che venga eseguito in momenti indesiderati, ad esempio durante un backup pianificato.</span><span class="sxs-lookup"><span data-stu-id="e6d50-105">You can run a report as a report snapshot to prevent the report from being run at arbitrary times (for example, during a scheduled backup).</span></span> <span data-ttu-id="e6d50-106">Uno snapshot di report viene in genere creato e in seguito aggiornato in base a una pianificazione, consentendo all'utente di determinare esattamente quando verrà eseguita l'elaborazione del report e dei dati.</span><span class="sxs-lookup"><span data-stu-id="e6d50-106">A report snapshot is usually created and subsequently refreshed on a schedule, allowing you to time exactly when report and data processing will occur.</span></span> <span data-ttu-id="e6d50-107">Se un report si basa su query la cui esecuzione richiede molto tempo oppure su query che utilizzano dati di un'origine dati che non si desidera venga utilizzata in determinati orari, è consigliabile eseguire il report come snapshot.</span><span class="sxs-lookup"><span data-stu-id="e6d50-107">If a report is based on queries that take a long time to run, or on queries that use data from a data source that you prefer no one access during certain hours, you should run the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="e6d50-108">Nel server di report è possibile memorizzare nella cache una copia di un report già elaborato, che verrà utilizzata quando un utente apre il report.</span><span class="sxs-lookup"><span data-stu-id="e6d50-108">A report server can cache a copy of a processed report and return that copy when a user opens the report.</span></span> <span data-ttu-id="e6d50-109">La memorizzazione nella cache è una tecnica per il miglioramento delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="e6d50-109">Caching is a performance-enhancement technique.</span></span> <span data-ttu-id="e6d50-110">che consente di ridurre il tempo necessario per recuperare i report di grandi dimensioni o che vengono aperti di frequente.</span><span class="sxs-lookup"><span data-stu-id="e6d50-110">Caching can shorten the time required to retrieve a report if the report is large or accessed frequently.</span></span>  
  
-   <span data-ttu-id="e6d50-111">La cronologia di un report è costituita dalla raccolta delle copie di un report eseguite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e6d50-111">Report history is a collection of previously run copies of a report.</span></span> <span data-ttu-id="e6d50-112">È pertanto possibile usare la cronologia di un report per mantenere una registrazione dei diversi risultati dell'esecuzione del report ottenuti durante un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="e6d50-112">You can use report history to maintain a record of a report over time.</span></span> <span data-ttu-id="e6d50-113">Non è consigliabile usare la cronologia del report per i report contenenti informazioni riservate e personali.</span><span class="sxs-lookup"><span data-stu-id="e6d50-113">Report history is not intended for reports that contain confidential or personal data.</span></span> <span data-ttu-id="e6d50-114">Per questo motivo, la cronologia del report può essere creata solo per i report che eseguono query su origini dati che utilizzano un unico set di credenziali (credenziali archiviate o credenziali utilizzate per l'esecuzione automatica dei report), che sono disponibili a tutti gli utenti che eseguono il report.</span><span class="sxs-lookup"><span data-stu-id="e6d50-114">For this reason, report history can include only those reports that query a data source using a single set of credentials (either stored credentials or credentials used for unattended report execution) that are available to all users who run a report.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="e6d50-115">con SharePoint utilizza le caratteristiche di gestione contenuto di estrazione e archiviazione di SharePoint per salvare gli aggiornamenti nei tipi di contenuto di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ,</span><span class="sxs-lookup"><span data-stu-id="e6d50-115">integration with SharePoint uses the check out and check in content management features of SharePoint to save updates to [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="e6d50-116">tra cui la creazione di snapshot dei report.</span><span class="sxs-lookup"><span data-stu-id="e6d50-116">This includes the creation of report snapshots.</span></span> <span data-ttu-id="e6d50-117">Pertanto se è stato abilitato il controllo delle versioni su una raccolta documenti, verrà visualizzata la versione del report aggiornata quando viene creato un nuovo snapshot di cronologia del report.</span><span class="sxs-lookup"><span data-stu-id="e6d50-117">Therefore if you have enabled versioning on a document library, you will see the report version updated when a new report history snapshot is created.</span></span> <span data-ttu-id="e6d50-118">Si tratta di un effetto collaterale dell'aggiornamento di snapshot.</span><span class="sxs-lookup"><span data-stu-id="e6d50-118">This is a side-effect of updating snapshots.</span></span> <span data-ttu-id="e6d50-119">L'aggiornamento di uno snapshot determina la modifica della proprietà LastExecution del report con una conseguente modifica della versione del report.</span><span class="sxs-lookup"><span data-stu-id="e6d50-119">When a snapshot is updated it causes the LastExecution property of the report to change and that will cause a change in the version of the report.</span></span>  
  
-   <span data-ttu-id="e6d50-120">È possibile specificare valori di timeout per limitare l'utilizzo delle risorse del sistema.</span><span class="sxs-lookup"><span data-stu-id="e6d50-120">You can specify time-out values to set limits on how system resources are used.</span></span>  
  
||  
|-|  
|<span data-ttu-id="e6d50-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="e6d50-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|  
  
 <span data-ttu-id="e6d50-122">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="e6d50-122">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="e6d50-123">Per impostare le opzioni relative all'aggiornamento dei dati</span><span class="sxs-lookup"><span data-stu-id="e6d50-123">To set data refresh options</span></span>](#bkmk_set_data_refresh)  
  
-   [<span data-ttu-id="e6d50-124">Per impostare le opzioni relative alla memorizzazione dei report nella cache</span><span class="sxs-lookup"><span data-stu-id="e6d50-124">To set report caching options</span></span>](#bkmk_set_report_caching)  
  
-   [<span data-ttu-id="e6d50-125">Per impostare i valori del timeout di elaborazione</span><span class="sxs-lookup"><span data-stu-id="e6d50-125">To set processing time-out values</span></span>](#bkmk_set_processing)  
  
-   [<span data-ttu-id="e6d50-126">Per impostare limiti e opzioni relativi alla cronologia del report</span><span class="sxs-lookup"><span data-stu-id="e6d50-126">To set report history options and limits</span></span>](#bkmk_set_report_history)  
  
-   [<span data-ttu-id="e6d50-127">Impostare il timeout del database</span><span class="sxs-lookup"><span data-stu-id="e6d50-127">Set database timeout</span></span>](#bkmk_set_database_timeout)  
  
##  <a name="to-set-data-refresh-options"></a><a name="bkmk_set_data_refresh"></a><span data-ttu-id="e6d50-128">Per impostare le opzioni di aggiornamento dati</span><span class="sxs-lookup"><span data-stu-id="e6d50-128">To set data refresh options</span></span>  
  
1.  <span data-ttu-id="e6d50-129">Selezionare un report nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e6d50-129">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="e6d50-130">Fare clic sulla freccia in giù e selezionare **Gestisci opzioni elaborazione**.</span><span class="sxs-lookup"><span data-stu-id="e6d50-130">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="e6d50-131">In **Opzioni aggiornamento dati**fare clic su **Usa dati snapshot**.</span><span class="sxs-lookup"><span data-stu-id="e6d50-131">In **Data Refresh Options**, click **Use snapshot data**.</span></span> <span data-ttu-id="e6d50-132">Se viene visualizzato il messaggio "Impossibile eseguire questo report da uno snapshot perché non sono disponibili credenziali archiviate per una o più origini dati", significa che il report non è configurato per l'esecuzione automatica e, prima di impostare questa opzione, sarà necessario modificare le origini dati in modo che utilizzino credenziali archiviate.</span><span class="sxs-lookup"><span data-stu-id="e6d50-132">If you see "This report can not run from a snapshot because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="e6d50-133">In **Opzioni snapshot dati**selezionare **Pianifica elaborazione dati**.</span><span class="sxs-lookup"><span data-stu-id="e6d50-133">In **Data Snapshot Options**, select **Schedule data processing**.</span></span>  
  
5.  <span data-ttu-id="e6d50-134">Se si desidera usare una pianificazione condivisa esistente, fare clic su **In base a una pianificazione condivisa** . In caso contrario, fare clic su **In base a una pianificazione personalizzata**, quindi su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="e6d50-134">Select **On a shared schedule** if you have an existing shared schedule that you want to use, otherwise click **On a custom schedule**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="e6d50-135">Selezionare la frequenza, la pianificazione, nonché le date di inizio e di fine e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6d50-135">Select frequency, schedule, and start and end dates, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="e6d50-136">Se si desidera creare immediatamente i dati dello snapshot da usare con il report, senza attendere l'elaborazione pianificata dei dati, in **Opzioni snapshot dati**selezionare **Crea o aggiorna lo snapshot al salvataggio della pagina** .</span><span class="sxs-lookup"><span data-stu-id="e6d50-136">In **Data Snapshot Options**, select **Create or update the snapshot when this page is saved** if you want to immediately create snapshot data to use with the report, without waiting for the scheduled data processing to occur.</span></span>  
  
##  <a name="to-set-report-caching-options"></a><a name="bkmk_set_report_caching"></a><span data-ttu-id="e6d50-137">Per impostare le opzioni di memorizzazione nella cache del report</span><span class="sxs-lookup"><span data-stu-id="e6d50-137">To set report caching options</span></span>  
  
1.  <span data-ttu-id="e6d50-138">Selezionare un report nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e6d50-138">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="e6d50-139">Fare clic sulla freccia in giù e selezionare **Gestisci opzioni elaborazione**.</span><span class="sxs-lookup"><span data-stu-id="e6d50-139">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="e6d50-140">In **Opzioni aggiornamento dati**fare clic su **Usa dati nella cache**.</span><span class="sxs-lookup"><span data-stu-id="e6d50-140">In **Data Refresh Options**, click **Use cached data**.</span></span> <span data-ttu-id="e6d50-141">Se viene visualizzato il messaggio "Impossibile memorizzare il report nella cache perché le credenziali di una o più origini dati non sono archiviate", significa che il report non è configurato per l'esecuzione automatica e, prima di impostare questa opzione, sarà necessario modificare le origini dati in modo che utilizzino credenziali archiviate.</span><span class="sxs-lookup"><span data-stu-id="e6d50-141">If you see "This report can not be cached because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="e6d50-142">In **Opzioni cache**specificare la modalità di scadenza della cache:</span><span class="sxs-lookup"><span data-stu-id="e6d50-142">In **Cache Options**, specify how the cache will expire:</span></span>  
  
    -   <span data-ttu-id="e6d50-143">Immettere il numero di minuti dopo il quale la cache scadrà.</span><span class="sxs-lookup"><span data-stu-id="e6d50-143">Enter a number of minutes after which the cache will expire.</span></span>  
  
    -   <span data-ttu-id="e6d50-144">Utilizzare una pianificazione per cancellare la cache a orari specifici.</span><span class="sxs-lookup"><span data-stu-id="e6d50-144">Use a shared schedule to clear the cache at times specified in the schedule.</span></span>  
  
    -   <span data-ttu-id="e6d50-145">Creare una pianificazione personalizzata per cancellare la cache all'orario desiderato.</span><span class="sxs-lookup"><span data-stu-id="e6d50-145">Create a custom schedule to clear the cache at a time that you specify.</span></span>  
  
##  <a name="to-set-processing-time-out-values"></a><a name="bkmk_set_processing"></a><span data-ttu-id="e6d50-146">Per impostare i valori di timeout di elaborazione</span><span class="sxs-lookup"><span data-stu-id="e6d50-146">To set processing time-out values</span></span>  
  
1.  <span data-ttu-id="e6d50-147">Selezionare un report nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e6d50-147">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="e6d50-148">Fare clic sulla freccia in giù e selezionare **Gestisci opzioni elaborazione**.</span><span class="sxs-lookup"><span data-stu-id="e6d50-148">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="e6d50-149">Se si desidera usare il valore specificato a livello del server di report, selezionare **Usa impostazione predefinita sito**in **Timeout elaborazione** .</span><span class="sxs-lookup"><span data-stu-id="e6d50-149">In **Processing Time-out**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="e6d50-150">Se invece si desidera sostituire il valore in questione e non impostare alcun timeout o un valore di timeout diverso, selezionare **Nessun timeout per l'elaborazione del report** o **Limite elaborazione report (in secondi)** .</span><span class="sxs-lookup"><span data-stu-id="e6d50-150">Otherwise, select **Do not time out report processing** or **Limit report processing in seconds** if you want to override that value with no time-out or different time-out values.</span></span>  
  
##  <a name="to-set-report-history-options-and-limits"></a><a name="bkmk_set_report_history"></a><span data-ttu-id="e6d50-151">Per impostare limiti e opzioni per la cronologia dei report</span><span class="sxs-lookup"><span data-stu-id="e6d50-151">To set report history options and limits</span></span>  
  
1.  <span data-ttu-id="e6d50-152">Selezionare un report nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e6d50-152">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="e6d50-153">Fare clic sulla freccia in giù e selezionare **Gestisci opzioni elaborazione**.</span><span class="sxs-lookup"><span data-stu-id="e6d50-153">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="e6d50-154">In **Opzioni snapshot cronologia**specificare la modalità e il momento dell'esecuzione e del salvataggio dell'elaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e6d50-154">In **History Snapshot Options**, specify how and when data processing occurs and is saved.</span></span>  
  
4.  <span data-ttu-id="e6d50-155">Se si desidera usare il valore specificato a livello del server di report, selezionare **Usa impostazione predefinita sito**in **Limiti snapshot cronologia** .</span><span class="sxs-lookup"><span data-stu-id="e6d50-155">In **History Snapshot Limits**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="e6d50-156">In caso contrario, selezionare **Numero di snapshot illimitato** oppure **Numero massimo di snapshot** e specificare un valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e6d50-156">Otherwise, select **Do not limit the number of snapshots** or **Limit number of snapshots** to specify a custom value.</span></span>  
  
##  <a name="set-database-timeout"></a><a name="bkmk_set_database_timeout"></a><span data-ttu-id="e6d50-157">Imposta timeout database</span><span class="sxs-lookup"><span data-stu-id="e6d50-157">Set database timeout</span></span>  
  
1.  <span data-ttu-id="e6d50-158">Usare Windows PowerShell per impostare il timeout del database di un server di report di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e6d50-158">Use Windows PowerShell to set the database timeout of a SharePoint report server.</span></span> <span data-ttu-id="e6d50-159">Per altre informazioni, vedere la sezione "Ottenere e impostare le proprietà del database di un'applicazione Reporting Service" dell'argomento [Cmdlet di PowerShell per la modalità SharePoint di Reporting Services](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e6d50-159">For more information, see the "Get and set Properties of the Reporting Service Application Database" section of [PowerShell cmdlets for Reporting Services SharePoint Mode](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d50-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6d50-160">See Also</span></span>  
 <span data-ttu-id="e6d50-161">[Impostare le proprietà di elaborazione dei report](report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e6d50-161">[Set Report Processing Properties](report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="e6d50-162">[Memorizzazione dei report nella cache &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6d50-162">[Caching Reports &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span></span>  
 [<span data-ttu-id="e6d50-163">Impostazione dei valori di timeout per l'elaborazione di report e di set di dati condivisi &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6d50-163">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
  
  
