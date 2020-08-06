---
title: Sviluppo di un'attività personalizzata | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom tasks [Integration Services], about custom tasks
- Task class
- custom tasks [Integration Services]
- SSIS custom tasks
- SSIS custom tasks, about custom tasks
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- tasks [Integration Services], custom
- TaskHost object
ms.assetid: dcbd8615-fa6d-4ddb-b8a5-0b19dddd6239
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d9d3446acff7ced73ab47014bec51708dba225b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635168"
---
# <a name="developing-a-custom-task"></a><span data-ttu-id="169b4-102">Sviluppo di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="169b4-102">Developing a Custom Task</span></span>
  <span data-ttu-id="169b4-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] vengono utilizzate attività per eseguire unità di lavoro a supporto dell'estrazione, della trasformazione e del caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="169b4-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] uses tasks to perform units of work in support of the extraction, transformation, and loading of data.</span></span> <span data-ttu-id="169b4-104">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] è inclusa una varietà di attività per l'esecuzione delle azioni più frequenti, dall'esecuzione di un'istruzione SQL al download di un file da un sito FTP.</span><span class="sxs-lookup"><span data-stu-id="169b4-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of tasks that perform the most frequently used actions, from executing an SQL statement to downloading a file from an FTP site.</span></span> <span data-ttu-id="169b4-105">Se le attività incluse e le azioni supportate non soddisfano completamente specifici requisiti, è possibile creare un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="169b4-105">If the included tasks and supported actions do not completely meet your requirements, you can create a custom task.</span></span>  
  
 <span data-ttu-id="169b4-106">A tale scopo, è necessario creare una classe che eredita dalla classe di base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), applicare l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> alla nuova classe ed eseguire l'override dei metodi e delle proprietà importanti della classe di base, tra cui il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="169b4-106">To create a custom task, you have to create a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="169b4-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="169b4-107">In This Section</span></span>  
 <span data-ttu-id="169b4-108">In questa sezione viene descritto come creare, configurare e scrivere il codice di un'attività personalizzata e della relativa interfaccia utente personalizzata facoltativa.</span><span class="sxs-lookup"><span data-stu-id="169b4-108">This section describes how to create, configure, and code a custom task and its optional custom user interface.</span></span>  
  
 [<span data-ttu-id="169b4-109">Creazione di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="169b4-109">Creating a Custom Task</span></span>](creating-a-custom-task.md)  
 <span data-ttu-id="169b4-110">Viene descritto il primo passaggio, ovvero la creazione dell'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="169b4-110">Describes the first step, which is creating the custom task.</span></span>  
  
 [<span data-ttu-id="169b4-111">Scrittura del codice di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="169b4-111">Coding a Custom Task</span></span>](coding-a-custom-task.md)  
 <span data-ttu-id="169b4-112">Viene descritto come scrivere il codice dei principali metodi di un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="169b4-112">Describes how to code the principal methods of a custom task.</span></span>  
  
 [<span data-ttu-id="169b4-113">Connessione alle origini dati in un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="169b4-113">Connecting to Data Sources in a Custom Task</span></span>](connecting-to-data-sources-in-a-custom-task.md)  
 <span data-ttu-id="169b4-114">Viene descritto come connettere un'attività personalizzata a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="169b4-114">Describes how to connect a custom task to a data source.</span></span>  
  
 [<span data-ttu-id="169b4-115">Generazione e definizione di eventi in un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="169b4-115">Raising and Defining Events in a Custom Task</span></span>](raising-and-defining-events-in-a-custom-task.md)  
 <span data-ttu-id="169b4-116">Viene descritto come generare eventi e definire eventi personalizzati dall'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="169b4-116">Describes how to raise events and define custom events from the custom task.</span></span>  
  
 [<span data-ttu-id="169b4-117">Aggiunta di supporto per il debug in un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="169b4-117">Adding Support for Debugging in a Custom Task</span></span>](adding-support-for-debugging-in-a-custom-task.md)  
 <span data-ttu-id="169b4-118">Viene descritto come creare destinazioni di punti di interruzione nell'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="169b4-118">Describes how to create breakpoint targets in the custom task.</span></span>  
  
 [<span data-ttu-id="169b4-119">Sviluppo di un'interfaccia utente per un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="169b4-119">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
 <span data-ttu-id="169b4-120">Viene descritto come creare un'interfaccia utente visualizzata in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] per configurare le proprietà nell'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="169b4-120">Describes how to create a user interface that shows in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to configure properties on the custom task.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="169b4-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="169b4-121">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="169b4-122">Informazioni comuni per tutti gli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="169b4-122">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="169b4-123">Per informazioni comuni a tutti i tipi di oggetti personalizzati che è possibile creare in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="169b4-123">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="169b4-124">Sviluppo di oggetti personalizzati per Integration Services</span><span class="sxs-lookup"><span data-stu-id="169b4-124">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="169b4-125">Vengono descritti i passaggi di base per implementare tutti i tipi di oggetti personalizzati in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="169b4-125">Describes the basic steps in implementing all kinds of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="169b4-126">Persistenza degli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="169b4-126">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="169b4-127">Viene descritta la persistenza personalizzata e vengono illustrati i casi in cui è necessaria.</span><span class="sxs-lookup"><span data-stu-id="169b4-127">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="169b4-128">Compilazione, distribuzione e debug di oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="169b4-128">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="169b4-129">Vengono descritte le tecniche per la compilazione, la firma, la distribuzione e il debug di oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="169b4-129">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="169b4-130">Informazioni su altri oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="169b4-130">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="169b4-131">Per informazioni sugli altri tipi di oggetti personalizzati che è possibile creare in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="169b4-131">For information about the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="169b4-132">Sviluppo di una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="169b4-132">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="169b4-133">Viene descritto come programmare gestioni connessioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="169b4-133">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="169b4-134">Sviluppo di un provider di log personalizzato</span><span class="sxs-lookup"><span data-stu-id="169b4-134">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="169b4-135">Viene descritto come programmare provider di log personalizzati.</span><span class="sxs-lookup"><span data-stu-id="169b4-135">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="169b4-136">Sviluppo di un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="169b4-136">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="169b4-137">Viene descritto come programmare enumeratori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="169b4-137">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="169b4-138">Sviluppo di un componente flusso di dati personalizzato</span><span class="sxs-lookup"><span data-stu-id="169b4-138">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="169b4-139">Viene descritto come programmare origini, trasformazioni e destinazioni personalizzate del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="169b4-139">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="169b4-140">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="169b4-140">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="169b4-141">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="169b4-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="169b4-142">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="169b4-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="169b4-143">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="169b4-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169b4-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="169b4-144">See Also</span></span>  
 <span data-ttu-id="169b4-145">[Estensione del pacchetto con l'attività Script](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span><span class="sxs-lookup"><span data-stu-id="169b4-145">[Extending the Package with the Script Task](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span></span>  
 [<span data-ttu-id="169b4-146">Confronto tra soluzioni di scripting e oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="169b4-146">Comparing Scripting Solutions and Custom Objects</span></span>](../../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)  
  
  
