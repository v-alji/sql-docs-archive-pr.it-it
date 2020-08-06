---
title: Confronto tra soluzioni di scripting e oggetti personalizzati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- managed tasks [Integration Services]
- Script task [Integration Services], vs. custom managed tasks
- SSIS Script task, vs. custom managed tasks
- custom tasks [Integration Services], scripts
ms.assetid: c0aea822-a21e-44e1-a3d3-8777bd0a1c34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: acf6faf9cdd78e951b8298c4e3b144d3444fb1ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624865"
---
# <a name="comparing-scripting-solutions-and-custom-objects"></a><span data-ttu-id="d6b33-102">Confronto tra soluzioni di scripting e oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="d6b33-102">Comparing Scripting Solutions and Custom Objects</span></span>
  <span data-ttu-id="d6b33-103">Un'attività Script o un componente script di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] può implementare molte delle funzionalità disponibili in un componente flusso di dati o un'attività gestita personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d6b33-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task or Script component can implement much of the same functionality that is possible in a custom managed task or data flow component.</span></span> <span data-ttu-id="d6b33-104">Di seguito sono riportate alcune considerazioni che consentono di scegliere il tipo di attività appropriato per specifiche esigenze:</span><span class="sxs-lookup"><span data-stu-id="d6b33-104">Here are some considerations to help you choose the appropriate type of task for your needs:</span></span>  
  
-   <span data-ttu-id="d6b33-105">Se la configurazione o la funzionalità è specifica di un singolo pacchetto, è consigliabile utilizzare l'attività Script o il componente di script anziché sviluppare un oggetto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d6b33-105">If the configuration or functionality is specific to an individual package, you should use the Script task or the Script component instead of a developing a custom object.</span></span>  
  
-   <span data-ttu-id="d6b33-106">Se la funzionalità è generica e può essere utilizzata in futuro per altri pacchetti e da altri sviluppatori, è consigliabile creare un oggetto personalizzato anziché utilizzare una soluzione di scripting.</span><span class="sxs-lookup"><span data-stu-id="d6b33-106">If the functionality is generic, and might be used in the future for other packages and by other developers, you should create a custom object instead of using a scripting solution.</span></span> <span data-ttu-id="d6b33-107">È possibile utilizzare un oggetto personalizzato in qualsiasi pacchetto, mentre uno script può essere utilizzato solo nel pacchetto per cui è stato creato.</span><span class="sxs-lookup"><span data-stu-id="d6b33-107">You can use a custom object in any package, whereas a script can be used only in the package for which it was created.</span></span>  
  
-   <span data-ttu-id="d6b33-108">Se il codice sarà riutilizzato all'interno dello stesso pacchetto, è consigliabile creare un oggetto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d6b33-108">If the code will be reused within the same package, you should consider creating a custom object.</span></span> <span data-ttu-id="d6b33-109">La copia di codice tra attività Script o componenti script diversi riduce le possibilità di manutenzione in quanto rende più difficile mantenere e aggiornare più copie del codice.</span><span class="sxs-lookup"><span data-stu-id="d6b33-109">Copying code from one Script task or component to another leads to reduced maintainability by making it more difficult to maintain and update multiple copies of the code.</span></span>  
  
-   <span data-ttu-id="d6b33-110">Se l'implementazione cambia nel corso del tempo, è consigliabile utilizzare un oggetto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d6b33-110">If the implementation will change over time, consider using a custom object.</span></span> <span data-ttu-id="d6b33-111">Gli oggetti personalizzati possono essere sviluppati e distribuiti separatamente rispetto al pacchetto padre, mentre un aggiornamento apportato a una soluzione di scripting richiede la ridistribuzione dell'intero pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d6b33-111">Custom objects can be developed and deployed separately from the parent package, whereas an update made to a scripting solution requires the redeployment of the whole package.</span></span>  
  
<span data-ttu-id="d6b33-112">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d6b33-112">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d6b33-113">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="d6b33-113">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d6b33-114">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="d6b33-114">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d6b33-115">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="d6b33-115">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b33-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6b33-116">See Also</span></span>  
 [<span data-ttu-id="d6b33-117">Estensione di pacchetti tramite oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="d6b33-117">Extending Packages with Custom Objects</span></span>](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
  
  
