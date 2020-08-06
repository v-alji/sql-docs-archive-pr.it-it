---
title: Sviluppo di una gestione connessione personalizzata | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], connections
- custom connection managers [Integration Services], about custom connection managers
- connection managers [Integration Services], custom
- Integration Services packages, connection managers
- SSIS packages, connection managers
- SQL Server Integration Services packages, connection managers
- custom connection managers [Integration Services]
ms.assetid: bda0b29e-57f5-4879-b04d-1396dc56daa8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19c5a9066db6542742537a41a7f567d1b4b1d23d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726084"
---
# <a name="developing-a-custom-connection-manager"></a><span data-ttu-id="3c847-102">Sviluppo di una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3c847-102">Developing a Custom Connection Manager</span></span>
  <span data-ttu-id="3c847-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] le gestioni connessioni vengono utilizzate per incapsulare le informazioni necessarie per la connessione a un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="3c847-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] uses connection managers to encapsulate the information needed to connect to an external data source.</span></span> <span data-ttu-id="3c847-104">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] è inclusa una varietà di gestioni connessione che supportano connessioni alle origini dati più utilizzate, dai database aziendali a file di testo e fogli di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="3c847-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of connection managers that support connections to the most commonly used data sources, from enterprise databases to text files and Excel worksheets.</span></span> <span data-ttu-id="3c847-105">Se le gestioni connessioni e le origini dati esterne supportate da [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] non soddisfano completamente specifici requisiti, è possibile creare una gestione connessione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3c847-105">If the connection managers and external data sources supported by [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] do not entirely meet your requirements, you can create a custom connection manager.</span></span>  
  
 <span data-ttu-id="3c847-106">Per creare una gestione connessione personalizzata, è necessario creare una classe che eredita dalla classe di base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, applicare l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> alla nuova classe ed eseguire l'override dei metodi e delle proprietà importanti della classe di base, tra cui la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> e il metodo <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="3c847-106">To create a custom connection manager, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3c847-107">La maggior parte delle attività, delle origini e delle destinazioni incluse in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] funziona solo con tipi specifici di gestioni connessioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="3c847-107">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="3c847-108">Prima di sviluppare una gestione connessione personalizzata da utilizzare con attività e componenti predefiniti, controllare se tali componenti restringono l'elenco di gestioni connessioni rendendo disponibili solo quelli di un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="3c847-108">Before developing a custom connection manager for use with built-in tasks and components, check whether those components restrict the list of available connection managers to those of a specific type.</span></span> <span data-ttu-id="3c847-109">Se la soluzione richiede una gestione connessione personalizzata, potrebbe essere necessario sviluppare anche un'attività personalizzata oppure un'origine o una destinazione personalizzata da utilizzare con la gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="3c847-109">If your solution requires a custom connection manager, you might also have to develop a custom task, or a custom source or destination, for use with the connection manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c847-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3c847-110">In This Section</span></span>  
 <span data-ttu-id="3c847-111">In questa sezione viene descritto come creare, configurare e scrivere il codice di una gestione connessione personalizzata e della relativa interfaccia utente personalizzata facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3c847-111">This section describes how to create, configure, and code a custom connection manager and its optional custom user interface.</span></span> <span data-ttu-id="3c847-112">I frammenti di codice illustrati in questa sezione sono tratti dall'esempio di gestione connessione personalizzata SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c847-112">The code snippets shown in this section are drawn from the Sql Server Custom Connection Manager Sample.</span></span>  
  
 [<span data-ttu-id="3c847-113">Creazione di una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3c847-113">Creating a Custom Connection Manager</span></span>](creating-a-custom-connection-manager.md)  
 <span data-ttu-id="3c847-114">Viene descritto come creare le classi per un progetto di gestione connessione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3c847-114">Describes how to create the classes for a custom connection manager project.</span></span>  
  
 [<span data-ttu-id="3c847-115">Scrittura del codice di una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3c847-115">Coding a Custom Connection Manager</span></span>](coding-a-custom-connection-manager.md)  
 <span data-ttu-id="3c847-116">Viene descritto come implementare una gestione connessione personalizzata eseguendo l'override dei metodi e delle proprietà della classe di base.</span><span class="sxs-lookup"><span data-stu-id="3c847-116">Describes how to implement a custom connection manager by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="3c847-117">Sviluppo di un'interfaccia utente per una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3c847-117">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
 <span data-ttu-id="3c847-118">Viene descritto come implementare la classe dell'interfaccia utente e il form utilizzato per configurare la gestione connessione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3c847-118">Describes how to implement the user interface class and the form that is used to configure the custom connection manager.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3c847-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="3c847-119">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="3c847-120">Informazioni comuni per tutti gli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="3c847-120">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="3c847-121">Per informazioni comuni a tutti i tipi di oggetti personalizzati che è possibile creare in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c847-121">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="3c847-122">Sviluppo di oggetti personalizzati per Integration Services</span><span class="sxs-lookup"><span data-stu-id="3c847-122">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="3c847-123">Vengono descritti i passaggi di base per implementare tutti i tipi di oggetti personalizzati in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c847-123">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="3c847-124">Persistenza degli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="3c847-124">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="3c847-125">Viene descritta la persistenza personalizzata e vengono illustrati i casi in cui è necessaria.</span><span class="sxs-lookup"><span data-stu-id="3c847-125">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="3c847-126">Compilazione, distribuzione e debug di oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="3c847-126">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="3c847-127">Vengono descritte le tecniche per la compilazione, la firma, la distribuzione e il debug di oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3c847-127">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="3c847-128">Informazioni su altri oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="3c847-128">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="3c847-129">Per informazioni sugli altri tipi di oggetti personalizzati che è possibile creare in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c847-129">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="3c847-130">Sviluppo di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="3c847-130">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="3c847-131">Viene descritto come programmare attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="3c847-131">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="3c847-132">Sviluppo di un provider di log personalizzato</span><span class="sxs-lookup"><span data-stu-id="3c847-132">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="3c847-133">Viene descritto come programmare provider di log personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3c847-133">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="3c847-134">Sviluppo di un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="3c847-134">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="3c847-135">Viene descritto come programmare enumeratori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3c847-135">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="3c847-136">Sviluppo di un componente flusso di dati personalizzato</span><span class="sxs-lookup"><span data-stu-id="3c847-136">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="3c847-137">Viene descritto come programmare origini, trasformazioni e destinazioni personalizzate del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="3c847-137">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="3c847-138">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="3c847-138">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="3c847-139">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="3c847-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="3c847-140">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="3c847-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="3c847-141">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="3c847-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
