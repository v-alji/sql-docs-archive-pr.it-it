---
title: Gestire i file di log DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- logging
- log files
- dqs log files
ms.assetid: 4fccfd24-aede-4882-be69-ec1e82682e16
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ca85772b8cc8aca41b75ad05d028bc444f280378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636893"
---
# <a name="manage-dqs-log-files"></a><span data-ttu-id="96da8-102">Gestire i file di log DQS</span><span class="sxs-lookup"><span data-stu-id="96da8-102">Manage DQS Log Files</span></span>
  <span data-ttu-id="96da8-103">I file di log di[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) consentono di diagnosticare e risolvere i problemi con il [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]e il [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96da8-103">[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) log files help you in diagnosing and troubleshooting issue with [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="96da8-104">Vengono generati file di log separati per il [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]e il [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96da8-104">Separate log files are generated for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
 <span data-ttu-id="96da8-105">È possibile utilizzare il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] per configurare l'impostazione di gravità del log per le funzionalità e i moduli del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96da8-105">You can use [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] to configure the log severity setting for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] features and modules.</span></span> <span data-ttu-id="96da8-106">Inoltre, è possibile configurare anche altre impostazioni (avanzate) per i file di log DQS modificando manualmente le impostazioni di configurazione del log DQS nel database DQS_MAIN e in un file XML nel computer del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96da8-106">Additionally, you can also configure some other (advanced) settings for the DQS log files by manually changing the DQS log configuration settings in the DQS_MAIN database and an XML file on the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] computer.</span></span>  
  
##  <a name="data-quality-server-log-file"></a><a name="DQSServer"></a><span data-ttu-id="96da8-107">File di log del server Data Quality</span><span class="sxs-lookup"><span data-stu-id="96da8-107">Data Quality Server Log File</span></span>  
 <span data-ttu-id="96da8-108">Il file di log del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , DQServerLog.DQS_MAIN.log, include i log delle attività eseguite nel [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96da8-108">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, DQServerLog.DQS_MAIN.log, includes logs of activities that are run on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="96da8-109">Se è stata installata l'istanza predefinita di SQL Server, il file DQServerLog.DQS_MAIN.log è disponibile in C:\Programmi\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span><span class="sxs-lookup"><span data-stu-id="96da8-109">If you installed the default instance of SQL Server, the DQServerLog.DQS_MAIN.log file is available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span></span> <span data-ttu-id="96da8-110">Il file di log del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] contiene le informazioni seguenti, ognuna delimitata da una pipe (|):</span><span class="sxs-lookup"><span data-stu-id="96da8-110">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file contains the following pieces of information, each delimited by a pipe (|):</span></span>  
  
-   <span data-ttu-id="96da8-111">Date e Time</span><span class="sxs-lookup"><span data-stu-id="96da8-111">Date and time</span></span>  
  
-   <span data-ttu-id="96da8-112">Nome del thread</span><span class="sxs-lookup"><span data-stu-id="96da8-112">Thread name</span></span>  
  
-   <span data-ttu-id="96da8-113">ID del thread</span><span class="sxs-lookup"><span data-stu-id="96da8-113">Thread ID</span></span>  
  
-   <span data-ttu-id="96da8-114">Gravità del log (ERRORE IRREVERSIBILE, ERRORE, AVVISO, INFORMAZIONI e DEBUG)</span><span class="sxs-lookup"><span data-stu-id="96da8-114">Log severity (FATAL, ERROR, WARN, INFO, and DEBUG)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="96da8-115">DEBUG corrisponde a Dettagliato.</span><span class="sxs-lookup"><span data-stu-id="96da8-115">The DEBUG logging severity is same as Verbose.</span></span>  
  
-   <span data-ttu-id="96da8-116">UID (ID interno dell'infrastruttura DQS)</span><span class="sxs-lookup"><span data-stu-id="96da8-116">UID (internal DQS infrastructure ID)</span></span>  
  
-   <span data-ttu-id="96da8-117">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="96da8-117">Namespace</span></span>  
  
-   <span data-ttu-id="96da8-118">Classe e metodo</span><span class="sxs-lookup"><span data-stu-id="96da8-118">Class and method</span></span>  
  
-   <span data-ttu-id="96da8-119">Message</span><span class="sxs-lookup"><span data-stu-id="96da8-119">Message</span></span>  
  
 <span data-ttu-id="96da8-120">Oltre a questi valori, nel file di log vengono visualizzate anche informazioni sulla versione dell'applicazione, il nome del computer, il nome dell'utente e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="96da8-120">Along with these, the log file also displays information about the application version, computer name, user name, and operating system.</span></span>  
  
 <span data-ttu-id="96da8-121">Una voce di esempio nel file di log del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="96da8-121">A sample entry in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file looks like the following:</span></span>  
  
```  
23-08-2013 01:45:29|[]|4|INFO|PUID|InfInfoModuleStarting|Microsoft.Ssdqs.Core.Startup.ServerInit|Starting DQS ServerInit: version [12.0.0.0], machine name [DQS-TEST], user name [NT Service\MSSQLSERVER], operating system [Microsoft Windows NT 6.1.7600.0]...  
```  
  
 <span data-ttu-id="96da8-122">Il file DQServerLog.DQS_MAIN.log è un file mobile e quando il file di log esistente supera il limite delle dimensioni dei file mobili specificate nelle impostazioni di configurazione di log del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] viene creato un nuovo file di log.</span><span class="sxs-lookup"><span data-stu-id="96da8-122">The DQServerLog.DQS_MAIN.log file is a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="96da8-123">Per ulteriori informazioni, vedere [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="96da8-123">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="data-quality-client-log-file"></a><a name="DQSClient"></a><span data-ttu-id="96da8-124">Data Quality Client file di log</span><span class="sxs-lookup"><span data-stu-id="96da8-124">Data Quality Client Log File</span></span>  
 <span data-ttu-id="96da8-125">Il file di log del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , DQClientLog.log, include i log lato client.</span><span class="sxs-lookup"><span data-stu-id="96da8-125">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file, DQClientLog.log, includes the client side logs.</span></span> <span data-ttu-id="96da8-126">Il file di log del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] è disponibile in %APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="96da8-126">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="96da8-127">Il file di log del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] contiene un set di informazioni simili a quelle del file di log del server, ma per il lato client.</span><span class="sxs-lookup"><span data-stu-id="96da8-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file contains similar set of information as in the server log file, but for the client side.</span></span>  
  
 <span data-ttu-id="96da8-128">Analogamente al file di log del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , anche il file di log del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] è un file mobile e quando il file di log esistente supera il limite delle dimensioni dei file mobili specificate nelle impostazioni di configurazione di log del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] viene creato un nuovo file di log.</span><span class="sxs-lookup"><span data-stu-id="96da8-128">As with the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is also a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log configuration settings.</span></span> <span data-ttu-id="96da8-129">Per ulteriori informazioni, vedere [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="96da8-129">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="dqs-cleansing-component-log-file"></a><a name="DQSCleansing"></a><span data-ttu-id="96da8-130">File di log del componente di pulizia DQS</span><span class="sxs-lookup"><span data-stu-id="96da8-130">DQS Cleansing Component Log File</span></span>  
 <span data-ttu-id="96da8-131">Il file di log del [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] , DQSSSISLog.log, include i log delle attività eseguite utilizzando il [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96da8-131">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file, DQSSSISLog.log, includes logs of activities performed using the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="96da8-132">Il file di log del componente [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] è disponibile in %APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="96da8-132">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] component log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="96da8-133">Il file di log di [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] contiene un set di informazioni simili a quelle del file di log del server, ma per [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96da8-133">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file contains similar set of information as in the server log file, but for the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
##  <a name="related-tasks"></a><a name="RT"></a> <span data-ttu-id="96da8-134">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="96da8-134">Related Tasks</span></span>  
  
|<span data-ttu-id="96da8-135">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="96da8-135">Task Description</span></span>|<span data-ttu-id="96da8-136">Argomento</span><span class="sxs-lookup"><span data-stu-id="96da8-136">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="96da8-137">Descrive come configurare le impostazioni di gravità del log per file di log DQS utilizzando il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96da8-137">Describes how to configure log severity settings for DQS log files using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>|[<span data-ttu-id="96da8-138">Configurare livelli di gravità per i file di log DQS</span><span class="sxs-lookup"><span data-stu-id="96da8-138">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)|  
|<span data-ttu-id="96da8-139">Descrive come configurare manualmente le impostazioni avanzate per i file di log DQS.</span><span class="sxs-lookup"><span data-stu-id="96da8-139">Describes how to manually configure advanced settings for DQS log files.</span></span>|[<span data-ttu-id="96da8-140">Configurare le impostazioni avanzate per i file di log DQS</span><span class="sxs-lookup"><span data-stu-id="96da8-140">Configure Advanced Settings for DQS Log Files</span></span>](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)|  
  
## <a name="see-also"></a><span data-ttu-id="96da8-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96da8-141">See Also</span></span>  
 [<span data-ttu-id="96da8-142">amministrazione dqs</span><span class="sxs-lookup"><span data-stu-id="96da8-142">DQS Administration</span></span>](../../2014/data-quality-services/dqs-administration.md)  
  
  
