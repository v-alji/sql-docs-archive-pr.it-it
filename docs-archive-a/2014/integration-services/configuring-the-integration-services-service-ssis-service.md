---
title: Configurazione del servizio Integration Services (servizio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- configuration files [Integration Services]
- service [Integration Services], configuring
- default configuration files
ms.assetid: 36d78393-a54c-44b0-8709-7f003f44c27f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70c41377a2c302e1a021c6ade2a9d487579fa64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722983"
---
# <a name="configuring-the-integration-services-service-ssis-service"></a><span data-ttu-id="f2dfa-102">Configurazione del servizio Integration Services (servizio SSIS)</span><span class="sxs-lookup"><span data-stu-id="f2dfa-102">Configuring the Integration Services Service (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="f2dfa-103">In questo argomento viene illustrato il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un servizio Windows per la gestione dei pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2dfa-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] <span data-ttu-id="f2dfa-104">supporta il servizio per la compatibilità con le versioni precedenti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dfa-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="f2dfa-105">A partire da [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], è possibile gestire oggetti come i pacchetti del server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="f2dfa-106">Il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] si basa su un file di configurazione per le relative impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service relies on a configuration file for its settings.</span></span> <span data-ttu-id="f2dfa-107">Per impostazione predefinita, il nome del file di configurazione è MsDtsSrvr.ini.xml e il file si trova nella cartella%programmi%\Microsoft SQL Server\120\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-107">By default, the name for this configuration file is MsDtsSrvr.ini.xml, and the file is located in the folder, %ProgramFiles%\Microsoft SQL Server\120\DTS\Binn.</span></span>  
  
 <span data-ttu-id="f2dfa-108">In genere, non è necessario apportare modifiche a tale file, né modificarne il percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-108">Typically, you do not have to make any changes to this configuration file, nor do you have to change the file's default location.</span></span> <span data-ttu-id="f2dfa-109">Sarà tuttavia necessario modificare il file di configurazione se i pacchetti sono archiviati in un'istanza denominata o remota del [!INCLUDE[ssDE](../includes/ssde-md.md)]o in più istanze del [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dfa-109">However, you will have to modify the configuration file if your packages are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)], or in multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="f2dfa-110">Se si sposta il file di configurazione in un percorso diverso da quello predefinito, sarà necessario modificare la chiave del Registro di sistema tramite cui viene specificato il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-110">Also, if you move the configuration file to a location other than the default location, you will have to modify the Registry key that specifies the file location.</span></span>  
  
## <a name="configuration-file-contents"></a><span data-ttu-id="f2dfa-111">Contenuto del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f2dfa-111">Configuration File Contents</span></span>  
 <span data-ttu-id="f2dfa-112">Durante l'installazione di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]viene creato e installato il file di configurazione per il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ,</span><span class="sxs-lookup"><span data-stu-id="f2dfa-112">When you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the setup process creates and installs the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="f2dfa-113">che contiene le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2dfa-113">This configuration file contains the following settings:</span></span>  
  
-   <span data-ttu-id="f2dfa-114">All'arresto del servizio ai pacchetti viene inviato un comando di arresto.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-114">Packages are sent a stop command when the service stops.</span></span>  
  
-   <span data-ttu-id="f2dfa-115">Le cartelle radice da visualizzare per [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nella finestra Esplora oggetti di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] sono le cartelle MSDB e File System.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-115">The root folders to display for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in Object Explorer of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] are the MSDB and File System folders.</span></span>  
  
-   <span data-ttu-id="f2dfa-116">I pacchetti nel file system [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gestiti dal servizio si trovano in%programmi%\Microsoft SQL Server\120\DTS\Packages.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-116">The packages in the file system that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages are located in %ProgramFiles%\Microsoft SQL Server\120\DTS\Packages.</span></span>  
  
 <span data-ttu-id="f2dfa-117">In questo file di configurazione è inoltre specificato quale database msdb contiene i pacchetti che verranno gestiti dal servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2dfa-117">This configuration file also specifies which msdb database contains the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service will manage.</span></span> <span data-ttu-id="f2dfa-118">Per impostazione predefinita, il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] è configurato per gestire i pacchetti archiviati nel database msdb dell'istanza del [!INCLUDE[ssDE](../includes/ssde-md.md)] installata in contemporanea con [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dfa-118">By default, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed at the same time as [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="f2dfa-119">Se contemporaneamente non viene installata alcuna istanza del [!INCLUDE[ssDE](../includes/ssde-md.md)] , il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] è configurato per gestire i pacchetti contenuti nel database msdb dell'istanza predefinita locale del [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dfa-119">If an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] is not installed at the same time, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the local, default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
### <a name="default-configuration-file-example"></a><span data-ttu-id="f2dfa-120">Esempio di file di configurazione predefinito</span><span class="sxs-lookup"><span data-stu-id="f2dfa-120">Default Configuration File Example</span></span>  
 <span data-ttu-id="f2dfa-121">Nell'esempio seguente è riportato un file di configurazione predefinito in cui sono specificate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2dfa-121">The following example shows a default configuration file that specifies the following settings:</span></span>  
  
-   <span data-ttu-id="f2dfa-122">Arresto dei pacchetti in esecuzione quando viene arrestato il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2dfa-122">Packages stop running when the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service stops.</span></span>  
  
-   <span data-ttu-id="f2dfa-123">Le cartelle radice per l'archiviazione dei pacchetti in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sono le cartelle MSDB e File system.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-123">The root folders for package storage in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are MSDB and File System.</span></span>  
  
-   <span data-ttu-id="f2dfa-124">Il servizio gestisce i pacchetti archiviati nel database msdb dell'istanza predefinita locale di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dfa-124">The service manages packages that are stored in the msdb database of the local, default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f2dfa-125">I pacchetti archiviati nel file system nella cartella Pacchetti sono gestiti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-125">The service manages packages that are stored in the file system in the Packages folder.</span></span>  
  
 <span data-ttu-id="f2dfa-126">**Esempio di un file di configurazione predefinito**</span><span class="sxs-lookup"><span data-stu-id="f2dfa-126">**Example of a Default Configuration File**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>.</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file"></a><span data-ttu-id="f2dfa-127">Modifica del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f2dfa-127">Modification of the Configuration File</span></span>  
 <span data-ttu-id="f2dfa-128">È possibile modificare il file di configurazione in modo da consentire l'esecuzione dei pacchetti anche quando il servizio viene arrestato, visualizzare cartelle radice aggiuntive in Esplora oggetti oppure specificare un'altra cartella o cartelle aggiuntive nel file system da gestire tramite il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2dfa-128">You can modify the configuration file to allow packages to continue running if the service stops, to display additional root folders in Object Explorer, or to specify a different folder or additional folders in the file system to be managed by [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="f2dfa-129">È possibile, ad esempio, creare cartelle radice aggiuntive di tipo `SqlServerFolder` per gestire i pacchetti nei database msdb di istanze aggiuntive del [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dfa-129">For example, you can create additional root folders of type, `SqlServerFolder`, to manage packages in the msdb databases of additional instances of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2dfa-130">Alcuni caratteri non sono validi per i nomi delle cartelle.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-130">Some characters are not valid in folder names.</span></span> <span data-ttu-id="f2dfa-131">I caratteri validi per i nomi delle cartelle sono determinati dalla classe [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]**System.IO.Path** e dal campo **GetInvalidFilenameChars** .</span><span class="sxs-lookup"><span data-stu-id="f2dfa-131">Valid characters for folder names are determined by the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] class **System.IO.Path** and the **GetInvalidFilenameChars** field.</span></span> <span data-ttu-id="f2dfa-132">Il campo **GetInvalidFilenameChars** fornisce una matrice specifica della piattaforma che contiene i caratteri che non è possibile specificare negli argomenti delle stringhe dei percorsi passati ai membri della classe **Path** .</span><span class="sxs-lookup"><span data-stu-id="f2dfa-132">The **GetInvalidFilenameChars** field provides a platform-specific array of characters that cannot be specified in path string arguments passed to members of the **Path** class.</span></span> <span data-ttu-id="f2dfa-133">Il set di caratteri non validi può variare in base al file system.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-133">The set of invalid characters can vary by file system.</span></span> <span data-ttu-id="f2dfa-134">Caratteri non validi sono in genere le virgolette ("), il carattere minore di (<) e la barra verticale (|).</span><span class="sxs-lookup"><span data-stu-id="f2dfa-134">Typically, invalid characters are the quotation mark ("), less than (<) character, and pipe (|) character.</span></span>  
  
 <span data-ttu-id="f2dfa-135">Per gestire i pacchetti archiviati in un'istanza denominata o remota del [!INCLUDE[ssDE](../includes/ssde-md.md)], è tuttavia necessario modificare il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-135">However, you will have to modify the configuration file to manage packages that are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="f2dfa-136">Se non si aggiorna il file di configurazione, non sarà possibile usare **Esplora oggetti** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per visualizzare i pacchetti archiviati nel database msdb nell'istanza denominata o remota.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-136">If you do not update the configuration file, you cannot use **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to view packages that are stored in the msdb database on the named instance or the remote instance.</span></span> <span data-ttu-id="f2dfa-137">Se si tenta di utilizzare **Esplora oggetti** per visualizzare questi pacchetti, verrà visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="f2dfa-137">If you try to use **Object Explorer** to view these packages, you receive the following error message:</span></span>  
  
 `Failed to retrieve data for this request. (Microsoft.SqlServer.SmoEnum)`  
  
 `The SQL Server specified in Integration Services service configuration is not present or is not available. This might occur when there is no default instance of SQL Server on the computer. For more information, see the topic "Configuring the Integration Services Service" in SQL Server 2008 Books Online.`  
  
 `Login Timeout Expired`  
  
 `An error has occurred while establishing a connection to the server. When connecting to SQL Server 2008, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.`  
  
 `Named Pipes Provider: Could not open a connection to SQL Server [2]. (MsDtsSvr).`  
  
 <span data-ttu-id="f2dfa-138">Per modificare il file di configurazione per il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , usare un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-138">To modify the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, you use a text editor.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f2dfa-139">Al termine della modifica del file di configurazione del servizio, è necessario riavviare il servizio in modo che utilizzi la configurazione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-139">After you modify the service configuration file, you must restart the service to use the updated service configuration.</span></span>  
  
### <a name="modified-configuration-file-example"></a><span data-ttu-id="f2dfa-140">Esempio di file di configurazione modificato</span><span class="sxs-lookup"><span data-stu-id="f2dfa-140">Modified Configuration File Example</span></span>  
 <span data-ttu-id="f2dfa-141">Nell'esempio seguente viene illustrato un file di configurazione modificato per [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dfa-141">The following example shows a modified configuration file for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="f2dfa-142">Questo file è per un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] denominata `InstanceName` su un server denominato `ServerName`.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-142">This file is for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] called `InstanceName` on a server named `ServerName`.</span></span>  
  
 <span data-ttu-id="f2dfa-143">**Esempio di un file di configurazione modificato per un'istanza denominata di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f2dfa-143">**Example of a Modified Configuration File for a Named Instance of SQL Server**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>ServerName\InstanceName</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file-location"></a><span data-ttu-id="f2dfa-144">Modifica del percorso del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f2dfa-144">Modification of the Configuration File Location</span></span>  
<span data-ttu-id="f2dfa-145">La chiave del registro di sistema **HKEY_LOCAL_MACHINE \SOFTWARE\MICROSOFT\MICROSOFT SQL Server\120\SSIS\ServiceConfigFile** specifica il percorso e il nome del file di configurazione [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] utilizzato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-145">The Registry key **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\120\SSIS\ServiceConfigFile** specifies the location and name for the configuration file that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service uses.</span></span> <span data-ttu-id="f2dfa-146">Il valore predefinito della chiave del registro di sistema è c:\Programmi\Microsoft **SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-146">The default value of the Registry key is **C:\Program Files\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span></span> <span data-ttu-id="f2dfa-147">È possibile aggiornare il valore della chiave del Registro di sistema per utilizzare un nome e un percorso diversi per il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-147">You can update the value of the Registry key to use a different name and location for the configuration file.</span></span> <span data-ttu-id="f2dfa-148">Si noti che il numero di versione nel percorso (120 per SQL Server [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] ) varia a seconda della versione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-148">Note that the version number in the path (120 for SQL Server  [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)]) will vary depending on the SQL Server version.</span></span> 
  
  
> [!CAUTION]  
>  <span data-ttu-id="f2dfa-149">La modifica non corretta del Registro di sistema può causare seri problemi che potrebbero richiedere la reinstallazione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-149">Incorrectly editing the Registry can cause serious problems that may require you to reinstall your operating system.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="f2dfa-150">non può garantire che i problemi causati dalla modifica non corretta del Registro di sistema possano essere risolti.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-150">cannot guarantee that problems resulting from editing the Registry incorrectly can be resolved.</span></span> <span data-ttu-id="f2dfa-151">Prima di modificare il Registro di sistema, eseguire il backup dei dati importanti.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-151">Before editing the Registry, back up any valuable data.</span></span> <span data-ttu-id="f2dfa-152">Per informazioni sul backup, sul ripristino e sulla modifica del Registro di sistema, vedere l'articolo di [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base relativo alla [descrizione del Registro di sistema di Microsoft Windows](https://support.microsoft.com/kb/256986).</span><span class="sxs-lookup"><span data-stu-id="f2dfa-152">For information about how to back up, restore, and edit the Registry, see the [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base article, [Description of the Microsoft Windows registry](https://support.microsoft.com/kb/256986).</span></span>  
  
 <span data-ttu-id="f2dfa-153">Il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] carica il file di configurazione al momento dell'avvio.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-153">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service loads the configuration file when the service is started.</span></span> <span data-ttu-id="f2dfa-154">Qualsiasi modifica alla voce del Registro di sistema richiede il riavvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="f2dfa-154">Any changes to the Registry entry require that the service be restarted.</span></span>  
  
  
