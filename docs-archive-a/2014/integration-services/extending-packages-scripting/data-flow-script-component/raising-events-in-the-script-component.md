---
title: Generazione di eventi nel componente script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], raising events
ms.assetid: bb389073-e1d0-4794-8d29-c8b293b6a5e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 78eb44239f4e58e43bdd65c41d5fdeb58d053a6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629911"
---
# <a name="raising-events-in-the-script-component"></a><span data-ttu-id="fdc05-102">Generazione di eventi nel componente script</span><span class="sxs-lookup"><span data-stu-id="fdc05-102">Raising Events in the Script Component</span></span>
  <span data-ttu-id="fdc05-103">Gli eventi consentono di segnalare errori, avvisi e altre informazioni, ad esempio l'avanzamento o lo stato delle attività, al pacchetto contenitore.</span><span class="sxs-lookup"><span data-stu-id="fdc05-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="fdc05-104">Il pacchetto fornisce gestori eventi per la gestione di notifiche degli eventi.</span><span class="sxs-lookup"><span data-stu-id="fdc05-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="fdc05-105">Il componente script può generare eventi chiamando metodi sulla proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> della classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="fdc05-105">The Script component can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class.</span></span> <span data-ttu-id="fdc05-106">Per altre informazioni sulla gestione degli eventi da parte dei pacchetti di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere [Gestori eventi di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="fdc05-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="fdc05-107">Gli eventi possono essere registrati in qualsiasi provider di log abilitato nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fdc05-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="fdc05-108">I provider di log archiviano informazioni sugli eventi in un archivio dati.</span><span class="sxs-lookup"><span data-stu-id="fdc05-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="fdc05-109">Il componente script può anche utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> per registrare informazioni in un provider di log senza generare un evento.</span><span class="sxs-lookup"><span data-stu-id="fdc05-109">The Script component can also use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="fdc05-110">Per ulteriori informazioni sull'utilizzo del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A>, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="fdc05-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method, see the following section.</span></span>  
  
 <span data-ttu-id="fdc05-111">Per generare un evento, l'attività Script chiama uno dei metodi seguenti dell'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> esposta dalla proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A>:</span><span class="sxs-lookup"><span data-stu-id="fdc05-111">To raise an event, the Script task calls one of the following methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface exposed by the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property:</span></span>  
  
|<span data-ttu-id="fdc05-112">Event</span><span class="sxs-lookup"><span data-stu-id="fdc05-112">Event</span></span>|<span data-ttu-id="fdc05-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdc05-113">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>|<span data-ttu-id="fdc05-114">Genera un evento personalizzato definito dall'utente nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fdc05-114">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A>|<span data-ttu-id="fdc05-115">Informa il pacchetto di una condizione di errore.</span><span class="sxs-lookup"><span data-stu-id="fdc05-115">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A>|<span data-ttu-id="fdc05-116">Fornisce informazioni all'utente.</span><span class="sxs-lookup"><span data-stu-id="fdc05-116">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireProgress%2A>|<span data-ttu-id="fdc05-117">Informa il pacchetto dello stato del componente.</span><span class="sxs-lookup"><span data-stu-id="fdc05-117">Informs the package of the progress of the component.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A>|<span data-ttu-id="fdc05-118">Informa il pacchetto che il componente è in uno stato che garantisce la notifica all'utente, ma non è una condizione di errore.</span><span class="sxs-lookup"><span data-stu-id="fdc05-118">Informs the package that the component is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
 <span data-ttu-id="fdc05-119">Di seguito è riportato un semplice esempio di generazione di un evento Error:</span><span class="sxs-lookup"><span data-stu-id="fdc05-119">Here is a simple example of raising an Error event:</span></span>  
  
 `Dim myMetadata as IDTSComponentMetaData100`  
  
 `myMetaData = Me.ComponentMetaData`  
  
 `myMetaData.FireError(...)`  
  
<span data-ttu-id="fdc05-120">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="fdc05-120">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="fdc05-121">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="fdc05-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="fdc05-122">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="fdc05-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="fdc05-123">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="fdc05-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc05-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdc05-124">See Also</span></span>  
 <span data-ttu-id="fdc05-125">[Gestori eventi di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="fdc05-125">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="fdc05-126">Aggiunta di un gestore eventi a un pacchetto</span><span class="sxs-lookup"><span data-stu-id="fdc05-126">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
