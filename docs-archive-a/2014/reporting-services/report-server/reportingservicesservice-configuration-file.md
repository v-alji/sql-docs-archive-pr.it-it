---
title: File di configurazione ReportingServicesService | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- traces [Reporting Services]
- Report Server Windows service, ReportingServicesService configuration file
- ReportingServicesService configuration file
ms.assetid: 40f4a401-cb61-4c42-b1ec-01acdacdacd1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5124631db9635211827dd3b1abbff7116101a61d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629193"
---
# <a name="reportingservicesservice-configuration-file"></a><span data-ttu-id="b5c6e-102">ReportingServicesService - file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b5c6e-102">ReportingServicesService Configuration File</span></span>
  <span data-ttu-id="b5c6e-103">Il file ReportingServicesService.exe.config contiene impostazioni di configurazione della funzionalità di traccia.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-103">The ReportingServicesService.exe.config file includes settings that configure tracing.</span></span>  
  
## <a name="file-location"></a><span data-ttu-id="b5c6e-104">Percorso file</span><span class="sxs-lookup"><span data-stu-id="b5c6e-104">File Location</span></span>  
 <span data-ttu-id="b5c6e-105">Il file si trova nella cartella \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-105">This file is located in the \Reporting Services\Report Server\Bin folder.</span></span>  
  
## <a name="editing-guidelines"></a><span data-ttu-id="b5c6e-106">Linee guida per la modifica</span><span class="sxs-lookup"><span data-stu-id="b5c6e-106">Editing Guidelines</span></span>  
 <span data-ttu-id="b5c6e-107">È possibile modificare questo file per rinominare il file di log oppure per aumentare o ridurre i livelli di traccia.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-107">You can modify this file to rename the log file or to increase or decrease trace levels.</span></span> <span data-ttu-id="b5c6e-108">Non modificare altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-108">Do not modify any of the other settings.</span></span> <span data-ttu-id="b5c6e-109">Per le istruzioni, vedere [Modificare un file di configurazione di Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="b5c6e-109">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="b5c6e-110">Per altre informazioni sui log di traccia, vedere [Log di traccia del servizio del server di report](report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="b5c6e-110">For more information about trace logs, see [Report Server Service Trace Log](report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="b5c6e-111">Configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="b5c6e-111">Example Configuration</span></span>  
 <span data-ttu-id="b5c6e-112">Nell'esempio seguente vengono illustrati i valori predefiniti e le impostazioni contenuti nel file ReportingServicesService.exe.config.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-112">The following example shows the settings and default values found in the ReportingServicesService.exe.config file.</span></span>  
  
```  
<configSections>  
      <section name="RStrace" type="Microsoft.ReportingServices.Diagnostics.RSTraceSectionHandler,Microsoft.ReportingServices.Diagnostics" />  
</configSections>  
<system.diagnostics>  
      <switches>  
          <add name="DefaultTraceSwitch" value="3" />  
      </switches>  
</system.diagnostics>  
<RStrace>  
      <add name="FileName" value="ReportServerService_" />  
      <add name="FileSizeLimitMb" value="32" />  
      <add name="KeepFilesForDays" value="14" />  
      <add name="Prefix" value="tid, time" />  
      <add name="TraceListeners" value="debugwindow, file" />  
      <add name="TraceFileMode" value="unique" />  
      <add name="Components" value="all" />  
</RStrace>  
<runtime>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
             <dependentAssembly>  
                    <assemblyIdentity name="Microsoft.ReportingServices.Interfaces"  
                        publicKeyToken="89845dcd8080cc91"  
                        culture="neutral" />  
                    <bindingRedirect oldVersion="8.0.242.0"  
                                     newVersion="10.0.0.0"/>  
                    <bindingRedirect oldVersion="9.0.242.0"  
                                     newVersion="10.0.0.0"/>  
             </dependentAssembly>  
      </assemblyBinding>  
      <gcServer enabled="true" />  
</runtime>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="b5c6e-113">Impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="b5c6e-113">Configuration Settings</span></span>  
 <span data-ttu-id="b5c6e-114">Nella tabella seguente sono incluse informazioni su impostazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-114">The following table provides information about specific settings.</span></span> <span data-ttu-id="b5c6e-115">Le impostazioni sono elencate nell'ordine in cui vengono visualizzate nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-115">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="b5c6e-116">Impostazione</span><span class="sxs-lookup"><span data-stu-id="b5c6e-116">Setting</span></span>|<span data-ttu-id="b5c6e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5c6e-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5c6e-118">**RStrace**</span><span class="sxs-lookup"><span data-stu-id="b5c6e-118">**RStrace**</span></span>|<span data-ttu-id="b5c6e-119">Specifica gli spazi dei nomi utilizzati per errori e traccia.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-119">Specifies namespaces used for errors and tracing.</span></span>|  
|<span data-ttu-id="b5c6e-120">**DefaultTraceSwitch**</span><span class="sxs-lookup"><span data-stu-id="b5c6e-120">**DefaultTraceSwitch**</span></span>|<span data-ttu-id="b5c6e-121">Specifica il livello delle informazioni da includere nel log di traccia ReportServerService.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-121">Specifies the level of information that is reported to the ReportServerService trace log.</span></span> <span data-ttu-id="b5c6e-122">Ogni livello include anche le informazioni raccolte da tutti i livelli inferiori.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-122">Each level includes the information reported by all lower-numbered levels.</span></span> <span data-ttu-id="b5c6e-123">Non è consigliabile disabilitare la funzionalità di traccia.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-123">Disabling tracing is not recommended.</span></span> <span data-ttu-id="b5c6e-124">I valori validi includono:</span><span class="sxs-lookup"><span data-stu-id="b5c6e-124">Valid values include:</span></span><br /><br /> <span data-ttu-id="b5c6e-125">0= Disabilita la funzionalità di traccia</span><span class="sxs-lookup"><span data-stu-id="b5c6e-125">0= Disables tracing</span></span><br /><br /> <span data-ttu-id="b5c6e-126">1= Eccezioni e riavvii</span><span class="sxs-lookup"><span data-stu-id="b5c6e-126">1= Exceptions and restarts</span></span><br /><br /> <span data-ttu-id="b5c6e-127">2= Eccezioni, riavvii, avvisi</span><span class="sxs-lookup"><span data-stu-id="b5c6e-127">2= Exceptions, restarts, warnings</span></span><br /><br /> <span data-ttu-id="b5c6e-128">3= Eccezioni, riavvii, avvisi, messaggi di stato (valore predefinito)</span><span class="sxs-lookup"><span data-stu-id="b5c6e-128">3= Exceptions, restarts, warnings, status messages (default)</span></span><br /><br /> <span data-ttu-id="b5c6e-129">4= Modalità dettagliata</span><span class="sxs-lookup"><span data-stu-id="b5c6e-129">4= Verbose mode</span></span>|  
|<span data-ttu-id="b5c6e-130">**FileName**</span><span class="sxs-lookup"><span data-stu-id="b5c6e-130">**FileName**</span></span>|<span data-ttu-id="b5c6e-131">Specifica la prima parte del nome file di log.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-131">Specifies the first portion of the log file name.</span></span> <span data-ttu-id="b5c6e-132">Il resto del nome viene completato con il valore specificato da `Prefix`.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-132">The value specified by `Prefix` completes the rest of the name.</span></span> <span data-ttu-id="b5c6e-133">Per impostazione predefinita, il nome è ReportServerService_.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-133">By default, the name is ReportServerService_.</span></span>|  
|<span data-ttu-id="b5c6e-134">**FileSizeLimitMb**</span><span class="sxs-lookup"><span data-stu-id="b5c6e-134">**FileSizeLimitMb**</span></span>|<span data-ttu-id="b5c6e-135">Specifica il limite massimo per le dimensioni del log di traccia.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-135">Specifies an upper limit on trace log size.</span></span> <span data-ttu-id="b5c6e-136">Il file è misurato in megabyte.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-136">The file is measured in megabytes.</span></span> <span data-ttu-id="b5c6e-137">I valori validi sono compresi tra 0 e il valore integer massimo.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-137">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="b5c6e-138">Il valore predefinito è (32).</span><span class="sxs-lookup"><span data-stu-id="b5c6e-138">The default value is 32.</span></span>|  
|<span data-ttu-id="b5c6e-139">**KeepFilesForDays**</span><span class="sxs-lookup"><span data-stu-id="b5c6e-139">**KeepFilesForDays**</span></span>|<span data-ttu-id="b5c6e-140">Specifica dopo quanti giorni un file di log di traccia viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-140">Specifies the number of days after which a trace log file will be deleted.</span></span> <span data-ttu-id="b5c6e-141">I valori validi sono compresi tra 0 e il valore integer massimo.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-141">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="b5c6e-142">Il valore predefinito è 14.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-142">The default value is 14.</span></span>|  
|`Prefix`|<span data-ttu-id="b5c6e-143">Specifica un valore generato che distingue ogni istanza del log dalle altre.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-143">Specifies a generated value that distinguishes one log instance from another.</span></span> <span data-ttu-id="b5c6e-144">Per impostazione predefinita, ai nomi file dei log di traccia vengono aggiunti valori timestamp.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-144">By default, timestamp values are appended to trace log file names.</span></span> <span data-ttu-id="b5c6e-145">Questo valore è impostato su "tid, time".</span><span class="sxs-lookup"><span data-stu-id="b5c6e-145">This value is set to " tid, time ".</span></span> <span data-ttu-id="b5c6e-146">Non modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-146">Do not modify this setting.</span></span>|  
|<span data-ttu-id="b5c6e-147">**TraceListeners**</span><span class="sxs-lookup"><span data-stu-id="b5c6e-147">**TraceListeners**</span></span>|<span data-ttu-id="b5c6e-148">Specifica una destinazione per l'output del contenuto del log di traccia.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-148">Specifies a target for outputting trace log content.</span></span> <span data-ttu-id="b5c6e-149">È possibile specificare più destinazioni, separandole con una virgola.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-149">You can specify multiple targets using a comma to separate each one.</span></span> <span data-ttu-id="b5c6e-150">I valori validi includono:</span><span class="sxs-lookup"><span data-stu-id="b5c6e-150">Valid values include:</span></span><br /><br /> <span data-ttu-id="b5c6e-151">DebugWindow (valore predefinito)</span><span class="sxs-lookup"><span data-stu-id="b5c6e-151">DebugWindow (default)</span></span><br /><br /> <span data-ttu-id="b5c6e-152">File (valore predefinito)</span><span class="sxs-lookup"><span data-stu-id="b5c6e-152">File (default)</span></span><br /><br /> <span data-ttu-id="b5c6e-153">StdOut</span><span class="sxs-lookup"><span data-stu-id="b5c6e-153">StdOut</span></span>|  
|<span data-ttu-id="b5c6e-154">**TraceFileMode**</span><span class="sxs-lookup"><span data-stu-id="b5c6e-154">**TraceFileMode**</span></span>|<span data-ttu-id="b5c6e-155">Specifica se i log di traccia devono contenere dati per un periodo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-155">Specifies whether trace logs contain data for a 24-hour period.</span></span> <span data-ttu-id="b5c6e-156">È consigliabile utilizzare un solo log di traccia al giorno per ogni componente.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-156">You should have one unique trace log for each component on each day.</span></span> <span data-ttu-id="b5c6e-157">Questo valore è impostato su "Unique" (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="b5c6e-157">This value is set to "Unique (default)".</span></span> <span data-ttu-id="b5c6e-158">Non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-158">Do not modify this value.</span></span>|  
|<span data-ttu-id="b5c6e-159">**Componenti**</span><span class="sxs-lookup"><span data-stu-id="b5c6e-159">**Components**</span></span>|<span data-ttu-id="b5c6e-160">Specifica per quali componenti devono essere creati log di traccia.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-160">Specifies the components for which trace logs are created.</span></span> <span data-ttu-id="b5c6e-161">Il valore predefinito è `all`.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-161">The default value is `all`.</span></span> <span data-ttu-id="b5c6e-162">Anche i nomi dei componenti interni sono valori validi per questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-162">Other valid values for this setting include the names of internal components.</span></span> <span data-ttu-id="b5c6e-163">Non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-163">Do not modify this value.</span></span>|  
|<span data-ttu-id="b5c6e-164">**Runtime**</span><span class="sxs-lookup"><span data-stu-id="b5c6e-164">**Runtime**</span></span>|<span data-ttu-id="b5c6e-165">Specifica le impostazioni di configurazione che supportano la compatibilità con la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-165">Specifies configuration settings that support backward compatibility with the previous version.</span></span> <span data-ttu-id="b5c6e-166">Le impostazioni di run-time vengono utilizzate per reindirizzare le richieste relative alla versione precedente di Microsoft.ReportingServices.Interfaces alla nuova versione.</span><span class="sxs-lookup"><span data-stu-id="b5c6e-166">Runtime settings are used to redirect requests that target the previous version of Microsoft.ReportingServices.Interfaces to the new version.</span></span><br /><br /> <span data-ttu-id="b5c6e-167">Tutte le impostazioni di configurazione di questa sezione vengono descritte nella documentazione di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5c6e-167">All of the configuration settings in this section are described in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] product documentation.</span></span> <span data-ttu-id="b5c6e-168">Per ulteriori informazioni, ricercare la voce "Runtime Schema Settings" nel sito Web MSDN o nella documentazione di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5c6e-168">For more information, search for "Runtime Schema Settings" on the MSDN Web site or in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5c6e-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5c6e-169">See Also</span></span>  
 <span data-ttu-id="b5c6e-170">[File di configurazione di Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="b5c6e-170">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="b5c6e-171">Report Server Service Trace Log</span><span class="sxs-lookup"><span data-stu-id="b5c6e-171">Report Server Service Trace Log</span></span>](report-server-service-trace-log.md)  
  
  
