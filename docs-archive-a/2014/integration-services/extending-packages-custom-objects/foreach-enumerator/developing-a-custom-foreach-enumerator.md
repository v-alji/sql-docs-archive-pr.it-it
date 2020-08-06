---
title: Sviluppo di un enumeratore Foreach personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services]
- custom foreach enumerators [Integration Services], about custom foreach enumerators
- foreach enumerators [Integration Services]
ms.assetid: bffe26e0-1b9a-47ad-bae6-6b708cb4cf4f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3d61f98266320f63d7ee56262b7c85dfb64d39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628915"
---
# <a name="developing-a-custom-foreach-enumerator"></a><span data-ttu-id="17d0d-102">Sviluppo di un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="17d0d-102">Developing a Custom ForEach Enumerator</span></span>
  <span data-ttu-id="17d0d-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] gli enumeratori Foreach vengono utilizzati per scorrere gli elementi di una raccolta ed eseguire le stesse attività per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="17d0d-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] uses foreach enumerators to iterate over the items in a collection and perform the same tasks for each element.</span></span> <span data-ttu-id="17d0d-104">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] è inclusa una varietà di enumeratori Foreach che supportano le raccolte più comunemente utilizzate, ad esempio tutti i file di una cartella, tutte le tabelle di un database o tutti gli elementi di un elenco archiviato in una variabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="17d0d-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of foreach enumerators that support the most commonly used collections, such as all the files in a folder, all the tables in a database, or all the elements of a list stored in a package variable.</span></span> <span data-ttu-id="17d0d-105">Se gli enumeratori Foreach e le raccolte disponibili non soddisfano completamente specifici requisiti, è possibile creare un enumeratore Foreach personalizzato.</span><span class="sxs-lookup"><span data-stu-id="17d0d-105">If the foreach enumerators and collections that are provided do not entirely meet your requirements, you can create a custom foreach enumerator.</span></span>  
  
 <span data-ttu-id="17d0d-106">A tale scopo, è necessario creare una classe che eredita dalla classe di base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, applicare l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> alla nuova classe ed eseguire l'override dei metodi e delle proprietà importanti della classe di base, tra cui il metodo <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="17d0d-106">To create a custom foreach enumerator, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17d0d-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="17d0d-107">In This Section</span></span>  
 <span data-ttu-id="17d0d-108">In questa sezione viene descritto come creare, configurare e scrivere il codice di un enumeratore Foreach personalizzato e della relativa interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="17d0d-108">This section describes how to create, configure, and code a custom foreach enumerator and its custom user interface.</span></span>  
  
 [<span data-ttu-id="17d0d-109">Creazione di un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="17d0d-109">Creating a Custom Foreach Enumerator</span></span>](creating-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="17d0d-110">Viene descritto come creare le classi per un progetto di enumeratore Foreach personalizzato.</span><span class="sxs-lookup"><span data-stu-id="17d0d-110">Describes how to create the classes for a custom foreach enumerator project.</span></span>  
  
 [<span data-ttu-id="17d0d-111">Scrittura del codice di un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="17d0d-111">Coding a Custom Foreach Enumerator</span></span>](coding-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="17d0d-112">Viene descritto come implementare un enumeratore Foreach personalizzato eseguendo l'override dei metodi e delle proprietà della classe di base.</span><span class="sxs-lookup"><span data-stu-id="17d0d-112">Describes how to implement a custom foreach enumerator by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="17d0d-113">Sviluppo di un'interfaccia utente per un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="17d0d-113">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="17d0d-114">Viene descritto come implementare la classe dell'interfaccia utente e il form utilizzato per configurare l'enumeratore Foreach personalizzato.</span><span class="sxs-lookup"><span data-stu-id="17d0d-114">Describes how to implement the user interface class and the form that is used to configure the custom foreach enumerator.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="17d0d-115">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="17d0d-115">Related Topics</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="17d0d-116">Informazioni comuni per tutti gli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="17d0d-116">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="17d0d-117">Per informazioni comuni a tutti i tipi di oggetti personalizzati che è possibile creare in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="17d0d-117">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="17d0d-118">Sviluppo di oggetti personalizzati per Integration Services</span><span class="sxs-lookup"><span data-stu-id="17d0d-118">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="17d0d-119">Vengono descritti i passaggi di base per implementare tutti i tipi di oggetti personalizzati in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17d0d-119">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="17d0d-120">Persistenza degli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="17d0d-120">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="17d0d-121">Viene descritta la persistenza personalizzata e vengono illustrati i casi in cui è necessaria.</span><span class="sxs-lookup"><span data-stu-id="17d0d-121">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="17d0d-122">Compilazione, distribuzione e debug di oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="17d0d-122">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="17d0d-123">Vengono descritte le tecniche per la compilazione, la firma, la distribuzione e il debug di oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="17d0d-123">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="17d0d-124">Informazioni su altri oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="17d0d-124">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="17d0d-125">Per informazioni sugli altri tipi di oggetti personalizzati che è possibile creare in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="17d0d-125">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="17d0d-126">Sviluppo di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="17d0d-126">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="17d0d-127">Viene descritto come programmare attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="17d0d-127">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="17d0d-128">Sviluppo di una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="17d0d-128">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="17d0d-129">Viene descritto come programmare gestioni connessioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="17d0d-129">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="17d0d-130">Sviluppo di un provider di log personalizzato</span><span class="sxs-lookup"><span data-stu-id="17d0d-130">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="17d0d-131">Viene descritto come programmare provider di log personalizzati.</span><span class="sxs-lookup"><span data-stu-id="17d0d-131">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="17d0d-132">Sviluppo di un componente flusso di dati personalizzato</span><span class="sxs-lookup"><span data-stu-id="17d0d-132">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="17d0d-133">Viene descritto come programmare origini, trasformazioni e destinazioni personalizzate del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="17d0d-133">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="17d0d-134">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="17d0d-134">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="17d0d-135">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="17d0d-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="17d0d-136">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="17d0d-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="17d0d-137">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="17d0d-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
