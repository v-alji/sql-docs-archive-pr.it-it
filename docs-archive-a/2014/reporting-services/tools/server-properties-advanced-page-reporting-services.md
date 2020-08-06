---
title: Proprietà server (pagina Avanzate) - Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.advanced.f1
ms.assetid: 07b78a84-a6aa-4502-861d-349720ef790e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1834b1eb458ec718db23ad229a4ed6e04ae826c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629721"
---
# <a name="server-properties-advanced-page---reporting-services"></a><span data-ttu-id="bb573-102">Proprietà server (pagina Avanzate) - Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bb573-102">Server Properties (Advanced Page) - Reporting Services</span></span>
  <span data-ttu-id="bb573-103">Questa pagina consente di impostare le proprietà di sistema nel server di report.</span><span class="sxs-lookup"><span data-stu-id="bb573-103">Use this page to set system properties on the report server.</span></span> <span data-ttu-id="bb573-104">Le proprietà di sistema possono essere impostate in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="bb573-104">There are a number of ways to set system properties.</span></span> <span data-ttu-id="bb573-105">Questo strumento fornisce un'interfaccia utente grafica che consente di impostare le proprietà senza dovere scrivere codice.</span><span class="sxs-lookup"><span data-stu-id="bb573-105">This tool provides a graphical user interface so that you can set properties without having to write code.</span></span>  
  
 <span data-ttu-id="bb573-106">Per aprire questa pagina, avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connettersi a un'istanza del server di report, fare clic con il pulsante destro del mouse sul nome del server di report e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bb573-106">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="bb573-107">Fare clic su **Avanzate** per aprire la pagina.</span><span class="sxs-lookup"><span data-stu-id="bb573-107">Click **Advanced** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bb573-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bb573-108">Options</span></span>  
 <span data-ttu-id="bb573-109">**EnableMyReports**</span><span class="sxs-lookup"><span data-stu-id="bb573-109">**EnableMyReports**</span></span>  
 <span data-ttu-id="bb573-110">Indica se la caratteristica Report personali è abilitata.</span><span class="sxs-lookup"><span data-stu-id="bb573-110">Indicates whether the My Reports feature is enabled.</span></span> <span data-ttu-id="bb573-111">Un valore `true` indica che la caratteristica è abilitata.</span><span class="sxs-lookup"><span data-stu-id="bb573-111">A value of `true` indicates that the feature is enabled.</span></span>  
  
 <span data-ttu-id="bb573-112">**MyReportsRole**</span><span class="sxs-lookup"><span data-stu-id="bb573-112">**MyReportsRole**</span></span>  
 <span data-ttu-id="bb573-113">Nome del ruolo utilizzato durante la creazione dei criteri di sicurezza nelle cartelle Report personali dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bb573-113">The name of the role used when creating security policies on user's My Reports folders.</span></span> <span data-ttu-id="bb573-114">Il valore predefinito è `My Reports Role`.</span><span class="sxs-lookup"><span data-stu-id="bb573-114">The default value is `My Reports Role`.</span></span>  
  
 <span data-ttu-id="bb573-115">**EnableClientPrinting**</span><span class="sxs-lookup"><span data-stu-id="bb573-115">**EnableClientPrinting**</span></span>  
 <span data-ttu-id="bb573-116">Determina se il controllo ActiveX RSClientPrint è disponibile per il download dal server di report.</span><span class="sxs-lookup"><span data-stu-id="bb573-116">Determines whether the RSClientPrint ActiveX control is available for download from the report server.</span></span> <span data-ttu-id="bb573-117">I valori validi sono `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="bb573-117">The valid values are `true` and `false`.</span></span> <span data-ttu-id="bb573-118">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="bb573-118">The default value is `true`.</span></span> <span data-ttu-id="bb573-119">Per altre informazioni sulle impostazioni aggiuntive necessarie per questo controllo, vedere [Abilitare e disabilitare la stampa sul lato client per Reporting Services](../report-server/enable-and-disable-client-side-printing-for-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="bb573-119">For more information about additional settings that are required for this control, see [Enable and Disable Client-Side Printing for Reporting Services](../report-server/enable-and-disable-client-side-printing-for-reporting-services.md).</span></span>  
  
 <span data-ttu-id="bb573-120">**EnableExecutionLogging**</span><span class="sxs-lookup"><span data-stu-id="bb573-120">**EnableExecutionLogging**</span></span>  
 <span data-ttu-id="bb573-121">Indica se la registrazione per l'esecuzione di report è attivata.</span><span class="sxs-lookup"><span data-stu-id="bb573-121">Indicates whether report execution logging is enabled.</span></span> <span data-ttu-id="bb573-122">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="bb573-122">The default value is `true`.</span></span> <span data-ttu-id="bb573-123">Per ulteriori informazioni sul log di esecuzione del server di report, vedere [log di esecuzione del server di report e la vista ExecutionLog3](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="bb573-123">For more information about the report server execution log, see [Report Server Execution Log and the ExecutionLog3 View](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
 <span data-ttu-id="bb573-124">**ExecutionLogDaysKept**</span><span class="sxs-lookup"><span data-stu-id="bb573-124">**ExecutionLogDaysKept**</span></span>  
 <span data-ttu-id="bb573-125">Numero di giorni durante i quali le informazioni sulle esecuzioni dei report vengono conservate nel log di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bb573-125">The number of days to keep report execution information in the execution log.</span></span> <span data-ttu-id="bb573-126">I valori validi per questa proprietà sono i valori compresi tra `-1` e `2`.`147`.`483`.`647`.</span><span class="sxs-lookup"><span data-stu-id="bb573-126">Valid values for this property include `-1` through `2`,`147`,`483`,`647`.</span></span> <span data-ttu-id="bb573-127">Se il valore è `-1` le voci non vengono eliminate dalla tabella del log di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bb573-127">If the value is `-1` entries are not deleted from the Execution Log table.</span></span> <span data-ttu-id="bb573-128">Il valore predefinito è `60`.</span><span class="sxs-lookup"><span data-stu-id="bb573-128">The default value is `60`.</span></span>  
  
 <span data-ttu-id="bb573-129">**SessionTimeout**</span><span class="sxs-lookup"><span data-stu-id="bb573-129">**SessionTimeout**</span></span>  
 <span data-ttu-id="bb573-130">Intervallo, in secondi, durante il quale una sessione rimane attiva.</span><span class="sxs-lookup"><span data-stu-id="bb573-130">The length of time, in seconds, that a session remains active.</span></span> <span data-ttu-id="bb573-131">Il valore predefinito è `600`.</span><span class="sxs-lookup"><span data-stu-id="bb573-131">The default value is `600`.</span></span>  
  
 <span data-ttu-id="bb573-132">**SharePointIntegratedMode**</span><span class="sxs-lookup"><span data-stu-id="bb573-132">**SharePointIntegratedMode**</span></span>  
 <span data-ttu-id="bb573-133">Proprietà di sola lettura che indica la modalità del server.</span><span class="sxs-lookup"><span data-stu-id="bb573-133">This is a read-only property that indicates the server mode.</span></span> <span data-ttu-id="bb573-134">Se il valore è False, il server di report è in esecuzione in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="bb573-134">If this value is False, the report server runs in native mode.</span></span>  
  
 <span data-ttu-id="bb573-135">**SiteName**</span><span class="sxs-lookup"><span data-stu-id="bb573-135">**SiteName**</span></span>  
 <span data-ttu-id="bb573-136">Nome del sito del server di report visualizzato nel titolo della pagina di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="bb573-136">The name of the report server site displayed in the page title of Report Manager.</span></span> <span data-ttu-id="bb573-137">Il valore predefinito è [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb573-137">The default value is [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="bb573-138">Questa proprietà può essere una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="bb573-138">This property can be an empty string.</span></span> <span data-ttu-id="bb573-139">La lunghezza massima è di 8.000 caratteri.</span><span class="sxs-lookup"><span data-stu-id="bb573-139">The maximum length is 8,000 characters.</span></span>  
  
 <span data-ttu-id="bb573-140">**StoredParametersLifetime**</span><span class="sxs-lookup"><span data-stu-id="bb573-140">**StoredParametersLifetime**</span></span>  
 <span data-ttu-id="bb573-141">Specifica il numero massimo di giorni per cui è possibile conservare un parametro archiviato.</span><span class="sxs-lookup"><span data-stu-id="bb573-141">Specifies the maximum number of days that a stored parameter can be stored.</span></span> <span data-ttu-id="bb573-142">I valori validi sono `-1` e i valori compresi tra `+1` e `2,147,483,647`.</span><span class="sxs-lookup"><span data-stu-id="bb573-142">Valid values are `-1`, `+1` through `2,147,483,647`.</span></span> <span data-ttu-id="bb573-143">Il valore predefinito è `180` giorni.</span><span class="sxs-lookup"><span data-stu-id="bb573-143">The default value is `180` days.</span></span>  
  
 <span data-ttu-id="bb573-144">**StoredParametersThreshold**</span><span class="sxs-lookup"><span data-stu-id="bb573-144">**StoredParametersThreshold**</span></span>  
 <span data-ttu-id="bb573-145">Specifica il numero massimo di valori dei parametri che possono essere archiviati nel server di report.</span><span class="sxs-lookup"><span data-stu-id="bb573-145">Specifies the maximum number of parameter values that can be stored by the report server.</span></span> <span data-ttu-id="bb573-146">I valori validi sono `-1` e i valori compresi tra `+1` e `2,147,483,647`.</span><span class="sxs-lookup"><span data-stu-id="bb573-146">Valid values are `-1`, `+1` through `2,147,483,647`.</span></span> <span data-ttu-id="bb573-147">Il valore predefinito è `1500`.</span><span class="sxs-lookup"><span data-stu-id="bb573-147">The default value is `1500`.</span></span>  
  
 <span data-ttu-id="bb573-148">**UseSessionCookies**</span><span class="sxs-lookup"><span data-stu-id="bb573-148">**UseSessionCookies**</span></span>  
 <span data-ttu-id="bb573-149">Indica se il server di report deve utilizzare cookie di sessione per le comunicazioni con i browser dei client.</span><span class="sxs-lookup"><span data-stu-id="bb573-149">Indicates whether the report server should use session cookies when communicating with client browsers.</span></span> <span data-ttu-id="bb573-150">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="bb573-150">The default value is `true`.</span></span>  
  
 <span data-ttu-id="bb573-151">**ExternalImagesTimeout**</span><span class="sxs-lookup"><span data-stu-id="bb573-151">**ExternalImagesTimeout**</span></span>  
 <span data-ttu-id="bb573-152">Determina l'intervallo di tempo entro il quale un file di immagine esterno deve essere recuperato prima del timeout della connessione. Il valore predefinito è `600` secondi.</span><span class="sxs-lookup"><span data-stu-id="bb573-152">Determines the length of time within which an external image file must be retrieved before the connection is timed out. The default is `600` seconds.</span></span>  
  
 <span data-ttu-id="bb573-153">**SnapshotCompression**</span><span class="sxs-lookup"><span data-stu-id="bb573-153">**SnapshotCompression**</span></span>  
 <span data-ttu-id="bb573-154">Definisce come vengono compressi gli snapshot.</span><span class="sxs-lookup"><span data-stu-id="bb573-154">Defines how snapshots are compressed.</span></span> <span data-ttu-id="bb573-155">Il valore predefinito è `SQL`.</span><span class="sxs-lookup"><span data-stu-id="bb573-155">The default value is `SQL`.</span></span> <span data-ttu-id="bb573-156">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb573-156">The valid values are as follows:</span></span>  
  
 <span data-ttu-id="bb573-157">**SQL** = gli snapshot vengono compressi quando vengono archiviati nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb573-157">**SQL =** Snapshots are compressed when stored in the report server database.</span></span> <span data-ttu-id="bb573-158">Questa impostazione corrisponde al comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="bb573-158">This is the current behavior.</span></span>  
  
 <span data-ttu-id="bb573-159">**None** = gli snapshot non vengono compressi.</span><span class="sxs-lookup"><span data-stu-id="bb573-159">**None** = Snapshots are not compressed.</span></span>  
  
 <span data-ttu-id="bb573-160">**All** = gli snapshot vengono compressi per tutte le opzioni di archiviazione, incluso il database del server di report o il file system.</span><span class="sxs-lookup"><span data-stu-id="bb573-160">**All =** Snapshots are compressed for all storage options, which include the report server database or the file system.</span></span>  
  
 <span data-ttu-id="bb573-161">**SystemReportTimeout**</span><span class="sxs-lookup"><span data-stu-id="bb573-161">**SystemReportTimeout**</span></span>  
 <span data-ttu-id="bb573-162">Valore di timeout  predefinito per l'elaborazione dei report, espresso in secondi, per tutti i report gestiti nello spazio dei nomi del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb573-162">The default report processing timeout value, in seconds, for all reports managed in the report server namespace.</span></span> <span data-ttu-id="bb573-163">È possibile eseguire l'override del valore a livello di report.</span><span class="sxs-lookup"><span data-stu-id="bb573-163">This value can be overridden at the report level.</span></span> <span data-ttu-id="bb573-164">Se questa proprietà è impostata, il server di report tenta di arrestare l'elaborazione di un report quando scade il tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="bb573-164">If this property is set, the report server attempts to stop the processing of a report when the specified time has expired.</span></span> <span data-ttu-id="bb573-165">I valori validi sono compresi tra `-1` e `2`.`147`.`483`.`647`.</span><span class="sxs-lookup"><span data-stu-id="bb573-165">Valid values are `-1` through `2`,`147`,`483`,`647`.</span></span> <span data-ttu-id="bb573-166">Se il valore è `-1` durante l'elaborazione non si verifica alcun timeout dei report nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="bb573-166">If the value is `-1`, reports in the namespace do not time out during processing.</span></span> <span data-ttu-id="bb573-167">Il valore predefinito è `1800`.</span><span class="sxs-lookup"><span data-stu-id="bb573-167">The default value is `1800`.</span></span>  
  
 <span data-ttu-id="bb573-168">**SystemSnapshotLimit**</span><span class="sxs-lookup"><span data-stu-id="bb573-168">**SystemSnapshotLimit**</span></span>  
 <span data-ttu-id="bb573-169">Numero massimo di snapshot archiviati per un report.</span><span class="sxs-lookup"><span data-stu-id="bb573-169">The maximum number of snapshots that are stored for a report.</span></span> <span data-ttu-id="bb573-170">I valori validi sono compresi tra `-1` e `2`.`147`.`483`.`647`.</span><span class="sxs-lookup"><span data-stu-id="bb573-170">Valid values are `-1` through `2`,`147`,`483`,`647`.</span></span> <span data-ttu-id="bb573-171">Se il valore è `-1`, non vi sono limiti per gli snapshot.</span><span class="sxs-lookup"><span data-stu-id="bb573-171">If the value is `-1`, there is no snapshot limit.</span></span>  
  
 <span data-ttu-id="bb573-172">**EnableIntegratedSecurity**</span><span class="sxs-lookup"><span data-stu-id="bb573-172">**EnableIntegratedSecurity**</span></span>  
 <span data-ttu-id="bb573-173">Determina se la sicurezza integrata di Windows è supportata per le connessioni alle origini dati dei report.</span><span class="sxs-lookup"><span data-stu-id="bb573-173">Determines whether Windows integrated security is supported for report data source connections.</span></span> <span data-ttu-id="bb573-174">Il valore predefinito è `True`.</span><span class="sxs-lookup"><span data-stu-id="bb573-174">The default is `True`.</span></span> <span data-ttu-id="bb573-175">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb573-175">The valid values are as follows:</span></span>  
  
 <span data-ttu-id="bb573-176">`True` = la sicurezza integrata di Windows è attivata.</span><span class="sxs-lookup"><span data-stu-id="bb573-176">`True` = Windows integrated security is enabled.</span></span>  
  
 <span data-ttu-id="bb573-177">`False` = la sicurezza integrata di Windows non è attivata.</span><span class="sxs-lookup"><span data-stu-id="bb573-177">`False` = Windows integrated security is not enabled.</span></span> <span data-ttu-id="bb573-178">Le origini dati dei report configurate per l'utilizzo della sicurezza integrata di Windows non verranno eseguite.</span><span class="sxs-lookup"><span data-stu-id="bb573-178">Report data sources that are configured to use Windows integrated security will not run.</span></span>  
  
 `EnableLoadReportDefinition`  
 <span data-ttu-id="bb573-179">Selezionare questa opzione per specificare se gli utenti possono eseguire report ad hoc da un report di Generatore report.</span><span class="sxs-lookup"><span data-stu-id="bb573-179">Select this option to specify whether users can perform ad hoc report execution from a Report Builder report.</span></span> <span data-ttu-id="bb573-180">L'impostazione di questa opzione determina il valore della proprietà `EnableLoadReportDefinition` nel server di report.</span><span class="sxs-lookup"><span data-stu-id="bb573-180">Setting this option determines the value of the `EnableLoadReportDefinition` property on the report server.</span></span>  
  
 <span data-ttu-id="bb573-181">Se si deseleziona questa opzione, la proprietà viene impostata su False e nel server di report non sarà possibile generare report click-through per i report che utilizzano un modello di report come origine dati.</span><span class="sxs-lookup"><span data-stu-id="bb573-181">If you clear this option, the property will be set to False and report server will not generate clickthrough reports for reports that use a report model as a data source.</span></span> <span data-ttu-id="bb573-182">Qualsiasi chiamata al metodo LoadReportDefinition verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="bb573-182">Any calls to the LoadReportDefinition method will be blocked.</span></span>  
  
 <span data-ttu-id="bb573-183">La disattivazione di questa opzione consente di attenuare i rischi di attacchi Denial of Service condotti da utenti malintenzionati tramite overload del server di report con richieste LoadReportDefinition.</span><span class="sxs-lookup"><span data-stu-id="bb573-183">Turning off this option mitigates a threat whereby a malicious user launches a denial of service attack by overloading the report server with LoadReportDefinition requests.</span></span>  
  
 <span data-ttu-id="bb573-184">**EnableRemoteErrors**</span><span class="sxs-lookup"><span data-stu-id="bb573-184">**EnableRemoteErrors**</span></span>  
 <span data-ttu-id="bb573-185">Include informazioni esterne sugli errori, ad esempio, informazioni sull'errore relative alle origini dati del report, nei messaggi di errore restituiti agli utenti che richiedono i report dai computer remoti.</span><span class="sxs-lookup"><span data-stu-id="bb573-185">Includes external error information (for example, error information about report data sources) with the error messages that are returned for users who request reports from remote computers.</span></span> <span data-ttu-id="bb573-186">I valori validi sono `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="bb573-186">Valid values are `true` and `false`.</span></span> <span data-ttu-id="bb573-187">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="bb573-187">The default value is `false`.</span></span> <span data-ttu-id="bb573-188">Per altre informazioni, vedere [Abilita errori remoti &#40;Reporting Services&#41;](../report-server/enable-remote-errors-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="bb573-188">For more information, see [Enable Remote Errors &#40;Reporting Services&#41;](../report-server/enable-remote-errors-reporting-services.md).</span></span>  
  
 <span data-ttu-id="bb573-189">**EnableReportDesignClientDownload**</span><span class="sxs-lookup"><span data-stu-id="bb573-189">**EnableReportDesignClientDownload**</span></span>  
 <span data-ttu-id="bb573-190">Specifica se il pacchetto di installazione di Generatore report può essere scaricato dal server di report.</span><span class="sxs-lookup"><span data-stu-id="bb573-190">Specifies whether Report Builder installation package can be downloaded from the report server.</span></span> <span data-ttu-id="bb573-191">Se si deseleziona questa impostazione, l'URL di Generatore report non funziona.</span><span class="sxs-lookup"><span data-stu-id="bb573-191">If you clear this setting, the URL to Report Builder will not work.</span></span> <span data-ttu-id="bb573-192">Per altre informazioni, vedere [Configurare l'accesso a Generatore report](../report-server/configure-report-builder-access.md).</span><span class="sxs-lookup"><span data-stu-id="bb573-192">For more information, see [Configure Report Builder Access](../report-server/configure-report-builder-access.md).</span></span>  
  
 <span data-ttu-id="bb573-193">**EditSessionCacheLimit**</span><span class="sxs-lookup"><span data-stu-id="bb573-193">**EditSessionCacheLimit**</span></span>  
 <span data-ttu-id="bb573-194">Consente di specificare il numero di voci della cache di dati che possono essere attive in una sessione di modifica del report.</span><span class="sxs-lookup"><span data-stu-id="bb573-194">Specifies the number of data cache entries that can be active in a report edit session.</span></span> <span data-ttu-id="bb573-195">Il numero predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="bb573-195">The default number is 5.</span></span>  
  
 <span data-ttu-id="bb573-196">**EditSessionTimeout**</span><span class="sxs-lookup"><span data-stu-id="bb573-196">**EditSessionTimeout**</span></span>  
 <span data-ttu-id="bb573-197">Specifica il numero di secondi prima del timeout di una sessione di modifica del report. Il valore predefinito è 7200 secondi (2 ore).</span><span class="sxs-lookup"><span data-stu-id="bb573-197">Specifies the number of seconds until a report edit session times out. The default value is 7200 seconds (2 hours).</span></span>  
  
 <span data-ttu-id="bb573-198">**EnableTestConnectionDetailedErrors**</span><span class="sxs-lookup"><span data-stu-id="bb573-198">**EnableTestConnectionDetailedErrors**</span></span>  
 <span data-ttu-id="bb573-199">Indica se messaggi di errore dettagliati vengono inviati al computer client quando gli utenti verificano le connessioni all'origine dati utilizzando il server di report.</span><span class="sxs-lookup"><span data-stu-id="bb573-199">Indicates whether detailed error messages are sent to the client computer when users test data source connections using the report server.</span></span> <span data-ttu-id="bb573-200">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="bb573-200">The default value is `true`.</span></span> <span data-ttu-id="bb573-201">Se l'opzione viene impostata su `false`, vengono inviati solo messaggi di errore generici.</span><span class="sxs-lookup"><span data-stu-id="bb573-201">If the option is set to `false`, only generic error messages are sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb573-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb573-202">See Also</span></span>  
 <span data-ttu-id="bb573-203">[Impostazione delle proprietà del server di report &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="bb573-203">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="bb573-204">[Connettersi a un server di report in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="bb573-204">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="bb573-205">[Proprietà Reporting Services](../report-server-web-service/net-framework/reporting-services-properties.md) </span><span class="sxs-lookup"><span data-stu-id="bb573-205">[Reporting Services Properties](../report-server-web-service/net-framework/reporting-services-properties.md) </span></span>  
 <span data-ttu-id="bb573-206">[Guida sensibile al contesto del server di report Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="bb573-206">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="bb573-207">[Proprietà di sistema del server di report](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) </span><span class="sxs-lookup"><span data-stu-id="bb573-207">[Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) </span></span>  
 <span data-ttu-id="bb573-208">[Script per distribuzione e attività amministrative](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="bb573-208">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 [<span data-ttu-id="bb573-209">Abilitare e disabilitare la funzionalità Report personali</span><span class="sxs-lookup"><span data-stu-id="bb573-209">Enable and Disable My Reports</span></span>](../report-server/enable-and-disable-my-reports.md)  
  
  