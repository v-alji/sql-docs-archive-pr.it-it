---
title: Abilitazione della registrazione a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SQL Server Integration Services packages, logs
- SSIS packages, logs
- Integration Services packages, logs
- SSIS logging
- log providers [Integration Services]
- logs [Integration Services], enabling
- LoggingMode property
- LogProvider object
- packages [Integration Services], logs
ms.assetid: 3222a1ed-83eb-421c-b299-a53b67bba740
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff7f81aca330960e4e94b0343080a37ded8c1273
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715656"
---
# <a name="enabling-logging-programmatically"></a><span data-ttu-id="317ca-102">Abilitazione della registrazione a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="317ca-102">Enabling Logging Programmatically</span></span>
  <span data-ttu-id="317ca-103">Il motore di runtime include una raccolta di oggetti <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> che consentono l'acquisizione di informazioni specifiche degli eventi durante la convalida e l'esecuzione di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="317ca-103">The run-time engine provides a collection of <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects that enable event-specific information to be captured during package validation and execution.</span></span> <span data-ttu-id="317ca-104">Gli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> sono disponibili per gli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer>, compresi gli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop> e <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="317ca-104"><xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects are available to <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer> objects, including the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>, and <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> objects.</span></span> <span data-ttu-id="317ca-105">La registrazione viene abilitata su singoli contenitori o sull'intero pacchetto.</span><span class="sxs-lookup"><span data-stu-id="317ca-105">Logging is enabled on individual containers, or on the whole package.</span></span>

 <span data-ttu-id="317ca-106">Sono disponibili diversi tipi di provider di log che un contenitore può utilizzare.</span><span class="sxs-lookup"><span data-stu-id="317ca-106">There are several types of log providers that are available for a container to use.</span></span> <span data-ttu-id="317ca-107">In questo modo è possibile creare e archiviare le informazioni del log in modo flessibile in molti formati.</span><span class="sxs-lookup"><span data-stu-id="317ca-107">This provides the flexibility to create and store log information in many formats.</span></span> <span data-ttu-id="317ca-108">Per integrare un oggetto contenitore nella registrazione, sono necessari due passaggi: viene innanzitutto abilitata la registrazione, quindi viene selezionato un provider di log.</span><span class="sxs-lookup"><span data-stu-id="317ca-108">Enlisting a container object in logging is a two-step process: first logging is enabled, and then a log provider is selected.</span></span> <span data-ttu-id="317ca-109">Le proprietà <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> del contenitore vengono utilizzate per specificare gli eventi registrati e per selezionare il provider di log.</span><span class="sxs-lookup"><span data-stu-id="317ca-109">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> properties of the container are used to specify the logged events and to select the log provider.</span></span>

## <a name="enabling-logging"></a><span data-ttu-id="317ca-110">Abilitazione della registrazione</span><span class="sxs-lookup"><span data-stu-id="317ca-110">Enabling Logging</span></span>
 <span data-ttu-id="317ca-111">La proprietà <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A>, disponibile in ogni contenitore in grado di eseguire la registrazione, determina se le informazioni degli eventi del contenitore vengono o meno registrate nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="317ca-111">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property, found in each container that can perform logging, determines whether the container's event information is recorded to the event log.</span></span> <span data-ttu-id="317ca-112">Questa proprietà, a cui viene assegnato un valore della struttura <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode>, è ereditata dall'elemento padre del contenitore per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="317ca-112">This property is assigned a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode> structure, and is inherited from the container's parent by default.</span></span> <span data-ttu-id="317ca-113">Se il contenitore è un pacchetto, pertanto non dispone di elemento padre, la proprietà utilizza l'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, che per impostazione predefinita è `Disabled`.</span><span class="sxs-lookup"><span data-stu-id="317ca-113">If the container is a package, and therefore has no parent, the property uses the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, which defaults to `Disabled`.</span></span>

### <a name="selecting-a-log-provider"></a><span data-ttu-id="317ca-114">Selezione di un provider di log</span><span class="sxs-lookup"><span data-stu-id="317ca-114">Selecting a Log Provider</span></span>
 <span data-ttu-id="317ca-115">Dopo l'impostazione della proprietà <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> su `Enabled`, viene aggiunto un provider di log alla raccolta <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> del contenitore per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="317ca-115">After the <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property is set to `Enabled`, a log provider is added to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection of the container to complete the process.</span></span> <span data-ttu-id="317ca-116">La raccolta <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> è disponibile sull'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> e contiene i provider di log selezionati per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="317ca-116">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection is available on the <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> object, and contains the log providers selected for the container.</span></span> <span data-ttu-id="317ca-117">Il metodo <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> viene chiamato per creare un provider e per aggiungerlo alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="317ca-117">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> method is called to create a provider and add it to the collection.</span></span> <span data-ttu-id="317ca-118">Il metodo restituisce quindi il provider di log aggiunto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="317ca-118">The method then returns the log provider that was added to the collection.</span></span> <span data-ttu-id="317ca-119">Ogni provider include impostazioni di configurazione specifiche e queste proprietà vengono impostate tramite la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="317ca-119">Each provider has configuration settings that are unique to that provider, and these properties are set using the <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> property.</span></span>

 <span data-ttu-id="317ca-120">Nella tabella seguente sono elencati i provider di log disponibili, la relativa descrizione e le informazioni su <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="317ca-120">The following table lists the available log providers, their description, and their <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> information.</span></span>

|<span data-ttu-id="317ca-121">Provider</span><span class="sxs-lookup"><span data-stu-id="317ca-121">Provider</span></span>|<span data-ttu-id="317ca-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="317ca-122">Description</span></span>|<span data-ttu-id="317ca-123">Proprietà ConfigString</span><span class="sxs-lookup"><span data-stu-id="317ca-123">ConfigString property</span></span>|
|--------------|-----------------|---------------------------|
|<span data-ttu-id="317ca-124">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="317ca-124">SQL Server Profiler</span></span>|<span data-ttu-id="317ca-125">Genera tracce SQL che possono essere acquisite e visualizzate in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span><span class="sxs-lookup"><span data-stu-id="317ca-125">Generates SQL traces that may be captured and viewed in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span></span> <span data-ttu-id="317ca-126">L'estensione predefinita dei file per questo provider è trc.</span><span class="sxs-lookup"><span data-stu-id="317ca-126">The default file name extension for this provider is .trc.</span></span>|<span data-ttu-id="317ca-127">Non è richiesta alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="317ca-127">No configuration is required.</span></span>|
|<span data-ttu-id="317ca-128">SQL Server</span><span class="sxs-lookup"><span data-stu-id="317ca-128">SQL Server</span></span>|<span data-ttu-id="317ca-129">Scrive le voci del log eventi nella tabella **sysssislog** in qualsiasi database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="317ca-129">Writes event log entries to the **sysssislog** table in any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>|<span data-ttu-id="317ca-130">Il provider [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] richiede che siano specificati la connessione al database e anche il nome del database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="317ca-130">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider requires that the connection to the database be specified, and also the target database name.</span></span>|
|<span data-ttu-id="317ca-131">File di testo</span><span class="sxs-lookup"><span data-stu-id="317ca-131">Text File</span></span>|<span data-ttu-id="317ca-132">Scrive le voci del log eventi in file di testo ASCII in formato delimitato da virgole (CSV).</span><span class="sxs-lookup"><span data-stu-id="317ca-132">Writes event log entries to ASCII text files in a comma-separated value (CSV) format.</span></span> <span data-ttu-id="317ca-133">L'estensione predefinita dei file per questo provider è log.</span><span class="sxs-lookup"><span data-stu-id="317ca-133">The default file name extension for this provider is .log.</span></span>|<span data-ttu-id="317ca-134">Nome di una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="317ca-134">The name of a file connection manager.</span></span>|
|<span data-ttu-id="317ca-135">Registro eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="317ca-135">Windows Event Log</span></span>|<span data-ttu-id="317ca-136">Registra nel registro eventi standard di Windows nel registro applicazioni del computer locale.</span><span class="sxs-lookup"><span data-stu-id="317ca-136">Logs to standard Windows Event Log on the local computer in the Application log.</span></span>|<span data-ttu-id="317ca-137">Non è richiesta alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="317ca-137">No configuration is required.</span></span>|
|<span data-ttu-id="317ca-138">File XML</span><span class="sxs-lookup"><span data-stu-id="317ca-138">XML File</span></span>|<span data-ttu-id="317ca-139">Scrive le voci del log eventi in un file in formato XML.</span><span class="sxs-lookup"><span data-stu-id="317ca-139">Writes event log entries to XML formatted file.</span></span> <span data-ttu-id="317ca-140">L'estensione predefinita dei file per questo provider è xml.</span><span class="sxs-lookup"><span data-stu-id="317ca-140">The default file name extension for this provider is .xml</span></span>|<span data-ttu-id="317ca-141">Nome di una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="317ca-141">The name of a file connection manager.</span></span>|

 <span data-ttu-id="317ca-142">Gli eventi vengono inclusi o esclusi dal log eventi impostando le proprietà `EventFilterKind` e `EventFilter` del contenitore.</span><span class="sxs-lookup"><span data-stu-id="317ca-142">Events are included in or excluded from the event log by setting the `EventFilterKind` and the `EventFilter` properties of the container.</span></span> <span data-ttu-id="317ca-143">La struttura `EventFilterKind` contiene due valori, `ExclusionFilter` e `InclusionFilter`, che indicano se gli eventi aggiunti a `EventFilter` sono inclusi nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="317ca-143">The `EventFilterKind` structure contains two values, `ExclusionFilter` and `InclusionFilter`, that indicate whether the events that are added to the `EventFilter` are included in the event log.</span></span> <span data-ttu-id="317ca-144">Alla proprietà `EventFilter` viene quindi assegnata una matrice di stringhe che contiene i nomi degli eventi soggetti all'applicazione di filtri.</span><span class="sxs-lookup"><span data-stu-id="317ca-144">The `EventFilter` property is then assigned a string array that contains the names of the events that are the subject of the filtering.</span></span>

 <span data-ttu-id="317ca-145">Nel codice seguente viene abilitata la registrazione su un pacchetto, viene aggiunto il provider di log per i file di testo nella raccolta <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> e viene specificato un elenco di eventi da includere nell'output della registrazione.</span><span class="sxs-lookup"><span data-stu-id="317ca-145">The following code enables logging on a package, adds the log provider for Text files to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection, and specifies a list of events to include in the logging output.</span></span>

## <a name="sample"></a><span data-ttu-id="317ca-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="317ca-146">Sample</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package p = new Package();

      ConnectionManager loggingConnection = p.Connections.Add("FILE");
      loggingConnection.ConnectionString = @"C:\SSISPackageLog.txt";

      LogProvider provider = p.LogProviders.Add("DTS.LogProviderTextFile.2");
      provider.ConfigString = loggingConnection.Name;
      p.LoggingOptions.SelectedLogProviders.Add(provider);
      p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion;
      p.LoggingOptions.EventFilter = new String[] { "OnPreExecute", 
         "OnPostExecute", "OnError", "OnWarning", "OnInformation" };
      p.LoggingMode = DTSLoggingMode.Enabled;

      // Add tasks and other objects to the package.

    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim p As Package = New Package()

    Dim loggingConnection As ConnectionManager = p.Connections.Add("FILE")
    loggingConnection.ConnectionString = "C:\SSISPackageLog.txt"

    Dim provider As LogProvider = p.LogProviders.Add("DTS.LogProviderTextFile.2")
    provider.ConfigString = loggingConnection.Name
    p.LoggingOptions.SelectedLogProviders.Add(provider)
    p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion
    p.LoggingOptions.EventFilter = New String() {"OnPreExecute", _
       "OnPostExecute", "OnError", "OnWarning", "OnInformation"}
    p.LoggingMode = DTSLoggingMode.Enabled

    ' Add tasks and other objects to the package.

  End Sub

End Module
```

<span data-ttu-id="317ca-147">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="317ca-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="317ca-148">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="317ca-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="317ca-149">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="317ca-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="317ca-150">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="317ca-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="317ca-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="317ca-151">See Also</span></span>
 [<span data-ttu-id="317ca-152">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="317ca-152">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)


