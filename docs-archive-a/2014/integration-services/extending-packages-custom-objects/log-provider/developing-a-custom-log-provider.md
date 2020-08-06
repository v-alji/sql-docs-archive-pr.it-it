---
title: Sviluppo di un provider di log personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- SSIS packages, log providers
- custom log providers [Integration Services]
- SQL Server Integration Services packages, log providers
- log providers [Integration Services]
- packages [Integration Services], logs
- Integration Services packages, log providers
ms.assetid: 3f715b95-7074-4f5c-8ae2-246998052e78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 88d4f70fa9d50628b831b56f9fa22100648fce51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624873"
---
# <a name="developing-a-custom-log-provider"></a><span data-ttu-id="97de4-102">Sviluppo di un provider di log personalizzato</span><span class="sxs-lookup"><span data-stu-id="97de4-102">Developing a Custom Log Provider</span></span>
  <span data-ttu-id="97de4-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sono disponibili funzionalità di registrazione estese che consentono di acquisire eventi che si verificano durante l'esecuzione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="97de4-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] has extensive logging capabilities that make it possible to capture events that occur during package execution.</span></span> <span data-ttu-id="97de4-104">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] è inclusa una varietà di provider di log che consentono di creare e archiviare log in formati quali XML, testo, database o nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="97de4-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of log providers that enable logs to be created and stored in formats such as XML, text, database, or in the Windows event log.</span></span> <span data-ttu-id="97de4-105">Se i provider di log e i formati di output disponibili non soddisfano completamente specifici requisiti, è possibile creare un provider di log personalizzato.</span><span class="sxs-lookup"><span data-stu-id="97de4-105">If the log providers and the output formats that are provided do not entirely meet your requirements, you can create a custom log provider.</span></span>

 <span data-ttu-id="97de4-106">A tale scopo, è necessario creare una classe che eredita dalla classe di base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, applicare l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> alla nuova classe ed eseguire l'override dei metodi e delle proprietà importanti della classe di base, tra cui la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> e il metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="97de4-106">To create a custom log provider, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="97de4-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="97de4-107">In This Section</span></span>
 <span data-ttu-id="97de4-108">In questa sezione viene descritto come creare, configurare e scrivere codice per un provider di log personalizzato.</span><span class="sxs-lookup"><span data-stu-id="97de4-108">This section describes how to create, configure, and code a custom log provider.</span></span>

 <span data-ttu-id="97de4-109">[Creazione di un provider di log personalizzato](creating-a-custom-log-provider.md) Viene descritto come creare le classi per un progetto di provider di log personalizzato.</span><span class="sxs-lookup"><span data-stu-id="97de4-109">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) Describes how to create the classes for a custom log provider project.</span></span>

 <span data-ttu-id="97de4-110">[Codifica di un provider di log personalizzato](coding-a-custom-log-provider.md) Viene descritto come implementare un provider di log personalizzato eseguendo l'override dei metodi e delle proprietà della classe di base.</span><span class="sxs-lookup"><span data-stu-id="97de4-110">[Coding a Custom Log Provider](coding-a-custom-log-provider.md) Describes how to implement a custom log provider by overriding the methods and properties of the base class.</span></span>

 <span data-ttu-id="97de4-111">[Sviluppo di un'interfaccia utente per un provider di log personalizzato](developing-a-user-interface-for-a-custom-log-provider.md) Le interfacce utente personalizzate per i provider di log personalizzati non sono supportate in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97de4-111">[Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md) Custom user interfaces for custom log providers are not supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

## <a name="related-topics"></a><span data-ttu-id="97de4-112">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="97de4-112">Related Topics</span></span>

### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="97de4-113">Informazioni comuni per tutti gli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="97de4-113">Information Common to all Custom Objects</span></span>
 <span data-ttu-id="97de4-114">Per informazioni comuni a tutti i tipi di oggetti personalizzati che è possibile creare in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="97de4-114">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="97de4-115">[Sviluppo di oggetti personalizzati per Integration Services](../developing-custom-objects-for-integration-services.md) Vengono descritti i passaggi di base per l'implementazione di tutti i tipi di oggetti personalizzati per [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97de4-115">[Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="97de4-116">[Salvataggio permanente di oggetti personalizzati](../persisting-custom-objects.md) Viene descritta la persistenza personalizzata e viene spiegato quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="97de4-116">[Persisting Custom Objects](../persisting-custom-objects.md) Describes custom persistence and explains when it is necessary.</span></span>

 <span data-ttu-id="97de4-117">[Compilazione, distribuzione e debug di oggetti personalizzati](../building-deploying-and-debugging-custom-objects.md) Vengono descritte le tecniche per la compilazione, la firma, la distribuzione e il debug di oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="97de4-117">[Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md) Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>

### <a name="information-about-other-custom-objects"></a><span data-ttu-id="97de4-118">Informazioni su altri oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="97de4-118">Information about Other Custom Objects</span></span>
 <span data-ttu-id="97de4-119">Per informazioni sugli altri tipi di oggetti personalizzati che è possibile creare in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="97de4-119">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="97de4-120">[Sviluppo di un'attività personalizzata](../task/developing-a-custom-task.md) Viene illustrato come programmare attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="97de4-120">[Developing a Custom Task](../task/developing-a-custom-task.md) Discusses how to program custom tasks.</span></span>

 <span data-ttu-id="97de4-121">[Sviluppo di una gestione connessione personalizzata](../connection-manager/developing-a-custom-connection-manager.md) Viene illustrato come programmare gestioni connessioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="97de4-121">[Developing a Custom Connection Manager](../connection-manager/developing-a-custom-connection-manager.md) Discusses how to program custom connection managers.</span></span>

 <span data-ttu-id="97de4-122">[Sviluppo di un enumeratore Foreach personalizzato](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Viene illustrato come programmare gli enumeratori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="97de4-122">[Developing a Custom ForEach Enumerator](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Discusses how to program custom enumerators.</span></span>

 <span data-ttu-id="97de4-123">[Sviluppo di un componente flusso di dati personalizzato](../data-flow/developing-a-custom-data-flow-component.md) Viene illustrato come programmare origini, trasformazioni e destinazioni personalizzate del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="97de4-123">[Developing a Custom Data Flow Component](../data-flow/developing-a-custom-data-flow-component.md) Discusses how to program custom data flow sources, transformations, and destinations.</span></span>

<span data-ttu-id="97de4-124">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="97de4-124">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="97de4-125">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="97de4-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="97de4-126">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="97de4-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="97de4-127">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="97de4-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>


