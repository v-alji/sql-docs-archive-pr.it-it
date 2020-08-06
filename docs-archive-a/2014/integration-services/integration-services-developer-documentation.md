---
title: Guida a Developer&#39;s (Integration Services) | Microsoft Docs
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
- Integration Services, programming
- SSIS, programming
- SQL Server Integration Services, programming
- packages [Integration Services], programming
ms.assetid: 60fe148b-a7c4-4289-ae3e-2e949fc1886c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c16ec1a21cf7ebb711f6d3996eb6239ea052c83c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636267"
---
# <a name="developer39s-guide-integration-services"></a><span data-ttu-id="77394-102">Guida a Developer&#39;s (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="77394-102">Developer&#39;s Guide (Integration Services)</span></span>
  <span data-ttu-id="77394-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] è disponibile un modello a oggetti completamente riscritto, potenziato con diverse funzionalità grazie alle quali l'estensione e la programmazione di pacchetti diventano operazioni più semplici, flessibili ed efficaci.</span><span class="sxs-lookup"><span data-stu-id="77394-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes a completely rewritten object model, which has been enhanced with many features that make extending and programming packages easier, more flexible, and more powerful.</span></span> <span data-ttu-id="77394-104">Gli sviluppatori possono estendere e programmare quasi ogni aspetto dei pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77394-104">Developers can extend and program almost every aspect of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="77394-105">Gli sviluppatori di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] possono adottare due approcci fondamentali per la programmazione di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="77394-105">As an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] developer, there are two fundamental approaches that you can take to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming:</span></span>  
  
-   <span data-ttu-id="77394-106">È possibile estendere i pacchetti scrivendo componenti che diventano disponibili in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] per fornire funzionalità personalizzate.</span><span class="sxs-lookup"><span data-stu-id="77394-106">You can extend packages by writing components that become available within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to provide custom functionality in a package.</span></span>  
  
-   <span data-ttu-id="77394-107">È possibile creare, configurare ed eseguire i pacchetti a livello di programmazione dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="77394-107">You can create, configure, and run packages programmatically from your own applications.</span></span>  
  
 <span data-ttu-id="77394-108">Se i componenti predefiniti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] non soddisfano i propri requisiti, è possibile estendere le funzionalità di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] utilizzando il codice per definire estensioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="77394-108">If you find that the built-in components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="77394-109">Questo approccio rende disponibili due opzioni discrete:</span><span class="sxs-lookup"><span data-stu-id="77394-109">In this approach, you have two discrete options:</span></span>  
  
-   <span data-ttu-id="77394-110">Per l'utilizzo ad hoc in un singolo pacchetto, è possibile creare un'attività personalizzata scrivendo codice nell'attività Script o un componente del flusso di dati personalizzato scrivendo codice nel componente script, che può essere configurato come origine, trasformazione o destinazione.</span><span class="sxs-lookup"><span data-stu-id="77394-110">For ad hoc use in a single package, you can create a custom task by writing code in the Script task, or a custom data flow component by writing code in the Script component, which you can configure as a source, transformation, or destination.</span></span> <span data-ttu-id="77394-111">Questi potenti wrapper scrivono il codice dell'infrastruttura e consentono agli sviluppatori di concentrarsi esclusivamente sullo sviluppo di funzionalità personalizzate. Tuttavia, non sono facilmente riutilizzabili altrove.</span><span class="sxs-lookup"><span data-stu-id="77394-111">These powerful wrappers write the infrastructure code for you and let you focus exclusively on developing your custom functionality; however, they are not easily reusable elsewhere.</span></span>  
  
-   <span data-ttu-id="77394-112">Per l'utilizzo in più pacchetti, è possibile creare estensioni di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] personalizzate, ad esempio gestioni connessioni, attività, enumeratori, provider di log e componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="77394-112">For use in multiple packages, you can create custom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] extensions such as connection managers, tasks, enumerators, log providers, and data flow components.</span></span> <span data-ttu-id="77394-113">Il modello a oggetti gestiti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contiene classi di base che forniscono un punto iniziale e semplificano lo sviluppo di estensioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="77394-113">The managed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model contains base classes that provide a starting point and make developing custom extensions easier than ever.</span></span>  
  
 <span data-ttu-id="77394-114">Se si desidera creare pacchetti in modo dinamico oppure gestire ed eseguire pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] all'esterno dell'ambiente di sviluppo, è possibile modificare i pacchetti a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="77394-114">If you want to create packages dynamically, or to manage and run [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages outside the development environment, you can manipulate packages programmatically.</span></span> <span data-ttu-id="77394-115">È possibile caricare, modificare ed eseguire pacchetti esistenti oppure creare ed eseguire pacchetti interamente nuovi a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="77394-115">You can load, modify, and run existing packages, or you can create and run entirely new packages programmatically.</span></span> <span data-ttu-id="77394-116">Questo approccio rende disponibili diverse opzioni:</span><span class="sxs-lookup"><span data-stu-id="77394-116">In this approach, you have a continuous range of options:</span></span>  
  
-   <span data-ttu-id="77394-117">Caricare ed eseguire un pacchetto esistente senza modifiche.</span><span class="sxs-lookup"><span data-stu-id="77394-117">Load and run an existing package without modification.</span></span>  
  
-   <span data-ttu-id="77394-118">Caricare un pacchetto esistente, riconfigurarlo (ad esempio specificando un'origine dati diversa) ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="77394-118">Load an existing package, reconfigure it (for example, specify a different data source), and run it.</span></span>  
  
-   <span data-ttu-id="77394-119">Creare un nuovo pacchetto, aggiungere e configurare i componenti, apportare modifiche oggetto per oggetto e proprietà per proprietà, salvarlo ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="77394-119">Create a new package, add and configure components, making changes object by object and property by property, save it, and then run it.</span></span>  
  
 <span data-ttu-id="77394-120">Questi approcci alla programmazione di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] vengono descritti e illustrati con esempi in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="77394-120">These approaches to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming are described in this section and demonstrated with examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77394-121">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="77394-121">In This Section</span></span>  
 [<span data-ttu-id="77394-122">Panoramica della programmazione di Integration Services</span><span class="sxs-lookup"><span data-stu-id="77394-122">Integration Services Programming Overview</span></span>](integration-services-programming-overview.md)  
 <span data-ttu-id="77394-123">Vengono descritti i ruoli del flusso di controllo e del flusso di dati nello sviluppo di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77394-123">Describes the roles of control flow and data flow in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] development.</span></span>  
  
 [<span data-ttu-id="77394-124">Informazioni sulle trasformazioni sincrone e asincrone</span><span class="sxs-lookup"><span data-stu-id="77394-124">Understanding Synchronous and Asynchronous Transformations</span></span>](understanding-synchronous-and-asynchronous-transformations.md)  
 <span data-ttu-id="77394-125">Vengono descritte le importanti differenze tra output sincroni e asincroni e vengono illustrati i componenti che li utilizzano nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="77394-125">Describes the important distinction between synchronous and asynchronous outputs and the components that use them in the data flow.</span></span>  
  
 [<span data-ttu-id="77394-126">Utilizzo di gestioni connessioni a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="77394-126">Working with Connection Managers Programmatically</span></span>](working-with-connection-managers-programmatically.md)  
 <span data-ttu-id="77394-127">Sono elencate le gestioni connessioni che è possibile utilizzare dal codice gestito e i valori restituiti quando viene chiamato il metodo `AcquireConnection`.</span><span class="sxs-lookup"><span data-stu-id="77394-127">Lists the connection managers that you can use from managed code, and the values that the connection managers return when the code calls the `AcquireConnection` method.</span></span>  
  
 [<span data-ttu-id="77394-128">Estensione di pacchetti tramite scripting</span><span class="sxs-lookup"><span data-stu-id="77394-128">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="77394-129">Viene descritto come estendere il flusso di controllo utilizzando l'attività Script o il flusso di dati utilizzando il componente script.</span><span class="sxs-lookup"><span data-stu-id="77394-129">Describes how to extend the control flow by using the Script task, or the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="77394-130">Estensione di pacchetti tramite oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="77394-130">Extending Packages with Custom Objects</span></span>](extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 <span data-ttu-id="77394-131">Viene descritto come creare e programmare attività personalizzate, componenti del flusso di dati e altri oggetti di pacchetto da utilizzare in più pacchetti.</span><span class="sxs-lookup"><span data-stu-id="77394-131">Describes how to create and program custom tasks, data flow components, and other package objects for use in multiple packages.</span></span>  
  
 [<span data-ttu-id="77394-132">Compilazione di pacchetti a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="77394-132">Building Packages Programmatically</span></span>](building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="77394-133">Viene descritto come creare, configurare e salvare pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="77394-133">Describes how to create, configure, and save [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
 [<span data-ttu-id="77394-134">Esecuzione e gestione dei pacchetti a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="77394-134">Running and Managing Packages Programmatically</span></span>](run-manage-packages-programmatically/running-and-managing-packages-programmatically.md)  
 <span data-ttu-id="77394-135">Viene descritto come enumerare, eseguire e gestire i pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="77394-135">Describes how to enumerate, run, and manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="77394-136">Riferimento</span><span class="sxs-lookup"><span data-stu-id="77394-136">Reference</span></span>  
 [<span data-ttu-id="77394-137">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="77394-137">Integration Services Error and Message Reference</span></span>](integration-services-error-and-message-reference.md)  
 <span data-ttu-id="77394-138">Vengono elencati i codici di errore predefiniti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], oltre ai relativi nomi simbolici e descrizioni.</span><span class="sxs-lookup"><span data-stu-id="77394-138">Lists the predefined [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error codes, together with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="77394-139">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="77394-139">Related Sections</span></span>  
 [<span data-ttu-id="77394-140">Strumenti per la risoluzione dei problemi di sviluppo di pacchetti</span><span class="sxs-lookup"><span data-stu-id="77394-140">Troubleshooting Tools for Package Development</span></span>](troubleshooting/troubleshooting-tools-for-package-development.md)  
 <span data-ttu-id="77394-141">Descrive le funzionalità e gli strumenti disponibili in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per la risoluzione di problemi relativi ai pacchetti che si verificano durante lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="77394-141">Describes the features and tools that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides for troubleshooting packages during development.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="77394-142">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="77394-142">External Resources</span></span>  
  
-   <span data-ttu-id="77394-143">Esempi CodePlex relativi ai [prodotti di Integration Services](https://go.microsoft.com/fwlink/?LinkID=131204) sul sito Web www.codeplex.com/MSFTISProdSamples</span><span class="sxs-lookup"><span data-stu-id="77394-143">CodePlex samples, [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=131204), on www.codeplex.com/MSFTISProdSamples</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77394-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77394-144">See Also</span></span>  
 [<span data-ttu-id="77394-145">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="77394-145">SQL Server Integration Services</span></span>](sql-server-integration-services.md)  
  
  
