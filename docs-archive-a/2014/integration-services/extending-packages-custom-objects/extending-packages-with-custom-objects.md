---
title: Estensione di pacchetti tramite oggetti personalizzati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
ms.assetid: 26616eb8-9e80-434d-b22a-ece1b00f449d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0159983f518e51aa082ea23745663e7f09eee1fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710968"
---
# <a name="extending-packages-with-custom-objects"></a><span data-ttu-id="6dbe1-102">Estensione di pacchetti tramite oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="6dbe1-102">Extending Packages with Custom Objects</span></span>
  <span data-ttu-id="6dbe1-103">Se i componenti forniti in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] non soddisfano i requisiti, è possibile estendere le funzionalità di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilizzando il codice per definire estensioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-103">If you find that the components provided in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="6dbe1-104">Per l'estensione dei pacchetti sono disponibili due opzioni discrete: è possibile scrivere codice all'interno dei potenti wrapper forniti dall'attività Script e dal componente script oppure creare da zero estensioni personalizzate di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] derivando dalla classe di base fornita dal modello a oggetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dbe1-104">You have two discrete options for extending your packages: you can write code within the powerful wrappers provided by the Script task and the Script component, or you can create custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] extensions from scratch by deriving from the base classes provided by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model.</span></span>  
  
 <span data-ttu-id="6dbe1-105">In questa sezione viene esaminata la più avanzata delle due opzioni, ovvero l'estensione di pacchetti tramite oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-105">This section explores the more advanced of the two options - extending packages with custom objects.</span></span>  
  
 <span data-ttu-id="6dbe1-106">Quando una soluzione [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personalizzata richiede una maggiore flessibilità di quanto non forniscano l'attività Script e il componente script oppure quando è necessario un componente riutilizzabile in più pacchetti, il modello a oggetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] consente di compilare completamente da zero attività personalizzate, componenti flusso di dati e altri oggetti del pacchetto in codice gestito.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-106">When your custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solution requires more flexibility than the Script task and the Script component provide, or when you need a component that you can reuse in multiple packages, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model lets you build custom tasks, data flow components, and other package objects in managed code from the ground up.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6dbe1-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6dbe1-107">In This Section</span></span>  
 [<span data-ttu-id="6dbe1-108">Sviluppo di oggetti personalizzati per Integration Services</span><span class="sxs-lookup"><span data-stu-id="6dbe1-108">Developing Custom Objects for Integration Services</span></span>](developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="6dbe1-109">Vengono descritti gli oggetti personalizzati che è possibile creare per [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], con un riepilogo dei passaggi e delle impostazioni essenziali.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-109">Discusses the custom objects that can be created for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and summarizes the essential steps and settings.</span></span>  
  
 [<span data-ttu-id="6dbe1-110">Persistenza degli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="6dbe1-110">Persisting Custom Objects</span></span>](persisting-custom-objects.md)  
 <span data-ttu-id="6dbe1-111">Viene descritta la persistenza predefinita degli oggetti personalizzati e viene illustrato il relativo processo di implementazione.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-111">Discusses the default persistence of custom objects, and the process of implementing custom persistence.</span></span>  
  
 [<span data-ttu-id="6dbe1-112">Compilazione, distribuzione e debug di oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="6dbe1-112">Building, Deploying, and Debugging Custom Objects</span></span>](building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="6dbe1-113">Vengono descritti gli approcci comuni per la compilazione, la distribuzione e il test di vari tipi di oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-113">Discusses the common approaches to building, deploying and testing the various types of custom objects.</span></span>  
  
 [<span data-ttu-id="6dbe1-114">Sviluppo di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="6dbe1-114">Developing a Custom Task</span></span>](task/developing-a-custom-task.md)  
 <span data-ttu-id="6dbe1-115">Viene descritto il processo di scrittura del codice di un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-115">Describes the process of coding a custom task.</span></span>  
  
 [<span data-ttu-id="6dbe1-116">Sviluppo di una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="6dbe1-116">Developing a Custom Connection Manager</span></span>](connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="6dbe1-117">Viene descritto il processo di scrittura del codice di una gestione connessione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-117">Describes the process of coding a custom connection manager.</span></span>  
  
 [<span data-ttu-id="6dbe1-118">Sviluppo di un provider di log personalizzato</span><span class="sxs-lookup"><span data-stu-id="6dbe1-118">Developing a Custom Log Provider</span></span>](log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="6dbe1-119">Viene descritto il processo di scrittura del codice di un provider di log personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-119">Describes the process of coding a custom log provider.</span></span>  
  
 [<span data-ttu-id="6dbe1-120">Sviluppo di un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="6dbe1-120">Developing a Custom ForEach Enumerator</span></span>](foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="6dbe1-121">Viene descritto il processo di scrittura del codice di un enumeratore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-121">Describes the process of coding a custom enumerator.</span></span>  
  
 [<span data-ttu-id="6dbe1-122">Sviluppo di un componente flusso di dati personalizzato</span><span class="sxs-lookup"><span data-stu-id="6dbe1-122">Developing a Custom Data Flow Component</span></span>](data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="6dbe1-123">Viene descritto come programmare origini, trasformazioni e destinazioni personalizzate del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-123">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6dbe1-124">Riferimento</span><span class="sxs-lookup"><span data-stu-id="6dbe1-124">Reference</span></span>  
 [<span data-ttu-id="6dbe1-125">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="6dbe1-125">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
 <span data-ttu-id="6dbe1-126">Vengono elencati i codici di errore predefiniti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con i relativi nomi simbolici e le descrizioni.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-126">Lists the predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error codes with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6dbe1-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6dbe1-127">Related Sections</span></span>  
 [<span data-ttu-id="6dbe1-128">Estensione di pacchetti tramite scripting</span><span class="sxs-lookup"><span data-stu-id="6dbe1-128">Extending Packages with Scripting</span></span>](../extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="6dbe1-129">Viene descritto come estendere il flusso di controllo utilizzando l'attività Script o il flusso di dati utilizzando il componente script.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-129">Discusses how to extend the control flow by using the Script task, or extend the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="6dbe1-130">Compilazione di pacchetti a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="6dbe1-130">Building Packages Programmatically</span></span>](../building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="6dbe1-131">Viene descritto come creare, configurare, eseguire, caricare, salvare e gestire pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-131">Describes how to create, configure, run, load, save, and manage [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
<span data-ttu-id="6dbe1-132">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6dbe1-132">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6dbe1-133">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="6dbe1-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6dbe1-134">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="6dbe1-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6dbe1-135">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="6dbe1-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbe1-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6dbe1-136">See Also</span></span>  
 <span data-ttu-id="6dbe1-137">[Confronto tra soluzioni di scripting e oggetti personalizzati](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="6dbe1-137">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="6dbe1-138">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="6dbe1-138">SQL Server Integration Services</span></span>](../sql-server-integration-services.md)  
  
  
