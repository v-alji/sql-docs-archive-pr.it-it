---
title: Gestione dei pacchetti in esecuzione a livello di programmazione| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], managing
- running packages [Integration Services]
ms.assetid: 0e91f4ac-6f29-40d7-8c28-9b82e4802c35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95c5f9c28b407631764d64523b37a6295870542a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723988"
---
# <a name="managing-running-packages-programmatically"></a><span data-ttu-id="8ae75-102">Gestione dei pacchetti in esecuzione a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="8ae75-102">Managing Running Packages Programmatically</span></span>
  <span data-ttu-id="8ae75-103">Quando si utilizzano i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a livello di programmazione, può essere necessario determinare quali sono attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8ae75-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine which packages are currently running.</span></span> <span data-ttu-id="8ae75-104">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> dello spazio dei nomi <xref:Microsoft.SqlServer.Dts.Runtime> fornisce metodi e classi per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="8ae75-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides methods and classes to satisfy these requirements.</span></span>  
  
 <span data-ttu-id="8ae75-105">Per altre informazioni sul monitoraggio dei pacchetti, vedere [Gestione dei pacchetti &#40;servizio SSIS&#41;](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="8ae75-105">For more information about monitoring packages, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="8ae75-106">Tutti i metodi descritti in questo argomento richiedono un riferimento all'assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="8ae75-106">All the methods discussed in this topic require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="8ae75-107">Dopo aver aggiunto il riferimento in un nuovo progetto, importare lo spazio dei nomi <xref:Microsoft.SqlServer.Dts.Runtime> con un'istruzione `using` o `Imports`.</span><span class="sxs-lookup"><span data-stu-id="8ae75-107">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8ae75-108">I metodi della classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> per l'utilizzo dell'archivio pacchetti SSIS supportano solo ".", localhost o il nome del server locale.</span><span class="sxs-lookup"><span data-stu-id="8ae75-108">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="8ae75-109">Non è possibile utilizzare "(local)".</span><span class="sxs-lookup"><span data-stu-id="8ae75-109">You cannot use "(local)".</span></span>  
  
## <a name="determining-which-packages-are-currently-running"></a><span data-ttu-id="8ae75-110">Identificazione dei pacchetti in esecuzione</span><span class="sxs-lookup"><span data-stu-id="8ae75-110">Determining Which Packages Are Currently Running</span></span>  
 <span data-ttu-id="8ae75-111">Per determinare quali pacchetti sono attualmente in esecuzione in un server specificato, chiamare il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ae75-111">To determine which packages are currently running on the specified server, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A> method.</span></span> <span data-ttu-id="8ae75-112">Il metodo restituisce una raccolta <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> di oggetti <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage>.</span><span class="sxs-lookup"><span data-stu-id="8ae75-112">This method returns a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection of <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ae75-113">Gli amministratori vedono tutti i pacchetti attualmente in esecuzione nel computer, mentre gli altri utenti vedono solo quelli che hanno avviato.</span><span class="sxs-lookup"><span data-stu-id="8ae75-113">Administrators see all packages that are currently executing on the computer; other users see only those packages that they have launched.</span></span>  
  
## <a name="working-with-running-packages"></a><span data-ttu-id="8ae75-114">Utilizzo dei pacchetti in esecuzione</span><span class="sxs-lookup"><span data-stu-id="8ae75-114">Working with Running Packages</span></span>  
 <span data-ttu-id="8ae75-115">Dopo aver determinato quali pacchetti sono attualmente in esecuzione, è possibile recuperare le relative informazioni e richiedere l'arresto di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8ae75-115">After you have determined which packages are currently running, you can retrieve information about the packages and request that a package be stopped.</span></span>  
  
### <a name="getting-information-about-a-running-package"></a><span data-ttu-id="8ae75-116">Recupero di informazioni su un pacchetto in esecuzione</span><span class="sxs-lookup"><span data-stu-id="8ae75-116">Getting Information about a Running Package</span></span>  
 <span data-ttu-id="8ae75-117">Mentre si scorre la raccolta <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages>, è possibile utilizzare le proprietà dell'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> per individuare un pacchetto o per ottenere ulteriori informazioni sui pacchetti in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="8ae75-117">As you iterate through the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection, you can use the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to locate a package or to obtain additional information about the packages that are running:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionDuration%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionStartTime%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.InstanceID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageDescription%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageName%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.UserName%2A>  
  
### <a name="stopping-a-running-package"></a><span data-ttu-id="8ae75-118">Arresto di un pacchetto in esecuzione</span><span class="sxs-lookup"><span data-stu-id="8ae75-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="8ae75-119">È possibile chiamare il metodo <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> di un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> per richiedere l'arresto del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8ae75-119">You can call the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to request that the package be stopped.</span></span> <span data-ttu-id="8ae75-120">È possibile che si verifichi un ritardo tra il momento in cui viene emessa una richiesta di arresto e il momento dell'arresto effettivo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8ae75-120">There may be a delay between the time that a stop request is issued and the time that the package actually stops.</span></span>  
  
<span data-ttu-id="8ae75-121">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8ae75-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8ae75-122">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="8ae75-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8ae75-123">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="8ae75-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8ae75-124">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="8ae75-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ae75-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ae75-125">See Also</span></span>  
 <span data-ttu-id="8ae75-126">[Gestione pacchetti &#40;servizio SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="8ae75-126">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="8ae75-127">Enumerazione dei pacchetti disponibili a livello di codice</span><span class="sxs-lookup"><span data-stu-id="8ae75-127">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
