---
title: Riferimenti ad altri assembly nelle soluzioni di scripting | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, .NET Framework
- Script task [Integration Services], adding references
- referencing custom assemblies
- SSIS Script task, VisualBasic namespace
- assemblies [Integration Services]
- VisualBasic namespace
- Script task [Integration Services], VisualBasic namespace
- Microsoft.VisualBasic namespace
- Script task [Integration Services], .NET Framework
- .NET Framework [Integration Services]
- referencing Web services
ms.assetid: 9b655bcd-19f6-43d8-9f89-1b4d299c6380
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 685bbaa62da88e84cd848eb49dcf5bedb03d5390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625466"
---
# <a name="referencing-other-assemblies-in-scripting-solutions"></a><span data-ttu-id="24798-102">Riferimenti ad altri assembly nelle soluzioni di scripting</span><span class="sxs-lookup"><span data-stu-id="24798-102">Referencing Other Assemblies in Scripting Solutions</span></span>
  <span data-ttu-id="24798-103">La libreria di classi [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fornisce allo sviluppatore di script un potente set di strumenti per l'implementazione di funzionalità personalizzate nei pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24798-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library provides the script developer with a powerful set of tools for implementing custom functionality in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="24798-104">L'attività Script e il componente script possono anche utilizzare assembly gestiti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="24798-104">The Script task and the Script component can also use custom managed assemblies.</span></span>

> [!NOTE]
>  <span data-ttu-id="24798-105">Per consentire ai pacchetti di usare gli oggetti e i metodi di un servizio Web, usare il comando **Aggiungi riferimento Web** disponibile in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="24798-105">To enable your packages to use the objects and methods from a Web service, use the **Add Web Reference** command available in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="24798-106">Nelle versioni precedenti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è necessario generare una classe proxy per utilizzare un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="24798-106">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you had to generate a proxy class to use a Web service.</span></span>

## <a name="using-a-managed-assembly"></a><span data-ttu-id="24798-107">Utilizzo di un assembly gestito</span><span class="sxs-lookup"><span data-stu-id="24798-107">Using a Managed Assembly</span></span>
 <span data-ttu-id="24798-108">Affinché [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] trovi un assembly gestito in fase di progettazione, è necessario effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="24798-108">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find a managed assembly at design time, you must do the following steps:</span></span>

1.  <span data-ttu-id="24798-109">Archiviare l'assembly gestito in qualsiasi cartella del computer.</span><span class="sxs-lookup"><span data-stu-id="24798-109">Store the managed assembly in any folder on your computer.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="24798-110">Nelle versioni precedenti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è possibile aggiungere solo un riferimento a un assembly gestito archiviato nella cartella %windir%\Microsoft.NET\Framework\vx.x.xxxxx o nella cartella %Programmi%\Microsoft SQL Server\100\SDK\Assemblies.</span><span class="sxs-lookup"><span data-stu-id="24798-110">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you could only add a reference to a managed assembly that was stored in the %windir%\Microsoft.NET\Framework\vx.x.xxxxx folder or the %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies folder.</span></span>

2.  <span data-ttu-id="24798-111">Aggiungere un riferimento all'assembly gestito.</span><span class="sxs-lookup"><span data-stu-id="24798-111">Add a reference to the managed assembly.</span></span>

     <span data-ttu-id="24798-112">Per aggiungere il riferimento, nella scheda **Sfoglia** della finestra di dialogo **Aggiungi riferimento** in VSTA individuare e aggiungere l'assembly gestito.</span><span class="sxs-lookup"><span data-stu-id="24798-112">To add the reference, in VSTA, in the **Add Reference** dialog box, on the **Browse** tab, locate and add the managed assembly.</span></span>

 <span data-ttu-id="24798-113">Affinché [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] trovi l'assembly gestito in fase di esecuzione, è necessario effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="24798-113">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find the managed assembly at run time, you must do the following steps:</span></span>

1.  <span data-ttu-id="24798-114">Firmare l'assembly gestito con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="24798-114">Sign the managed assembly with a strong name.</span></span>

2.  <span data-ttu-id="24798-115">Installare l'assembly nella Global Assembly Cache nel computer in cui viene eseguito il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="24798-115">Install the assembly in the global assembly cache on the computer on which the package is run.</span></span>

     <span data-ttu-id="24798-116">Per altre informazioni, vedere [Compilazione, distribuzione e debug di oggetti personalizzati](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="24798-116">For more information, see [Building, Deploying, and Debugging Custom Objects](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span></span>

## <a name="using-the-microsoft-net-framework-class-library"></a><span data-ttu-id="24798-117">Utilizzo della libreria di classi Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="24798-117">Using the Microsoft .NET Framework Class Library</span></span>
 <span data-ttu-id="24798-118">L'attività Script e il componente script possono trarre vantaggio da tutti gli altri oggetti e funzionalità esposti dalla libreria di classi [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24798-118">The Script task and the Script component can take advantage of all the other objects and functionality exposed by the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="24798-119">Ad esempio, tramite [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] è possibile recuperare informazioni sull'ambiente e interagire con il computer in cui viene eseguito il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="24798-119">For example, by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can retrieve information about your environment and interact with the computer that is running the package.</span></span>

 <span data-ttu-id="24798-120">In questo elenco vengono descritte alcune delle classi [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] utilizzate più di frequente:</span><span class="sxs-lookup"><span data-stu-id="24798-120">This list describes several of the more frequently used [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes:</span></span>

-   <span data-ttu-id="24798-121">`System.Data`Contiene l'architettura ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="24798-121">`System.Data` Contains the ADO.NET architecture.</span></span>

-   <span data-ttu-id="24798-122">`System.IO`Fornisce un'interfaccia per la file system e i flussi.</span><span class="sxs-lookup"><span data-stu-id="24798-122">`System.IO` Provides an interface to the file system and streams.</span></span>

-   <span data-ttu-id="24798-123">`System.Windows.Forms`Consente la creazione di form.</span><span class="sxs-lookup"><span data-stu-id="24798-123">`System.Windows.Forms` Provides form creation.</span></span>

-   <span data-ttu-id="24798-124">`System.Text.RegularExpressions`Fornisce classi per l'utilizzo di espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="24798-124">`System.Text.RegularExpressions` Provides classes for working with regular expressions.</span></span>

-   <span data-ttu-id="24798-125">`System.Environment`Restituisce informazioni sul computer locale, l'utente corrente e le impostazioni del computer e dell'utente.</span><span class="sxs-lookup"><span data-stu-id="24798-125">`System.Environment` Returns information about the local computer, the current user, and computer and user settings.</span></span>

-   <span data-ttu-id="24798-126">`System.Net`Fornisce le comunicazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="24798-126">`System.Net` Provides network communications.</span></span>

-   <span data-ttu-id="24798-127">`System.DirectoryServices`Espone Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24798-127">`System.DirectoryServices` Exposes Active Directory.</span></span>

-   <span data-ttu-id="24798-128">`System.Drawing`Fornisce librerie di manipolazione delle immagini estese.</span><span class="sxs-lookup"><span data-stu-id="24798-128">`System.Drawing` Provides extensive image manipulation libraries.</span></span>

-   <span data-ttu-id="24798-129">`System.Threading`Consente la programmazione multithreading.</span><span class="sxs-lookup"><span data-stu-id="24798-129">`System.Threading` Enables multithreaded programming.</span></span>

 <span data-ttu-id="24798-130">Per ulteriori informazioni su [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], consultare MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="24798-130">For more information about the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see the MSDN Library.</span></span>

<span data-ttu-id="24798-131">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="24798-131">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="24798-132">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="24798-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="24798-133">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="24798-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="24798-134">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="24798-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="24798-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24798-135">See Also</span></span>
 [<span data-ttu-id="24798-136">Estensione di pacchetti tramite scripting</span><span class="sxs-lookup"><span data-stu-id="24798-136">Extending Packages with Scripting</span></span>](extending-packages-with-scripting.md)


