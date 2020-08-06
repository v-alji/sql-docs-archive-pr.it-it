---
title: Differenze tra l'esecuzione locale e remota | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- packages [Integration Services], troubleshooting
ms.assetid: 610ee7d9-4fea-4aba-9395-57add826923b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 399584c790f4c5a5dd136121c58a5ff7743f4969
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714516"
---
# <a name="understanding-the-differences-between-local-and-remote-execution"></a><span data-ttu-id="698bc-102">Differenze tra l'esecuzione locale e remota</span><span class="sxs-lookup"><span data-stu-id="698bc-102">Understanding the Differences between Local and Remote Execution</span></span>
  <span data-ttu-id="698bc-103">Gli sviluppatori e gli amministratori di pacchetti dovrebbero essere consapevoli dell'esistenza di restrizioni in merito a dove può essere eseguito un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="698bc-103">Package developers and administrators should be aware that there are restrictions related to where an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package runs.</span></span>  
  
-   <span data-ttu-id="698bc-104">**Un pacchetto viene eseguito nello stesso computer del programma che lo avvia**.</span><span class="sxs-lookup"><span data-stu-id="698bc-104">**A package runs on the same computer as the program that launches it**.</span></span> <span data-ttu-id="698bc-105">Anche quando un programma carica un pacchetto archiviato in remoto in un altro server, il pacchetto viene eseguito nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="698bc-105">Even when a program loads a package that is stored remotely on another server, the package runs on the local computer.</span></span>  
  
-   <span data-ttu-id="698bc-106">**È possibile eseguire un pacchetto all'esterno dell'ambiente di sviluppo solo in un computer in cui è installato Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="698bc-106">**You can only run a package outside the development environment on a computer that has Integration Services installed**.</span></span> <span data-ttu-id="698bc-107">Non è possibile eseguire i pacchetti all'esterno di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in un computer client in cui [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] non è installato e le condizioni di licenza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] potrebbero non consentire l'installazione di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] in computer aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="698bc-107">You cannot run packages outside of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing may not permit you to install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="698bc-108">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è un componente server e non è ridistribuibile a computer client.</span><span class="sxs-lookup"><span data-stu-id="698bc-108">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span> <span data-ttu-id="698bc-109">Per eseguire pacchetti da un computer client, è necessario avviarli in modo da assicurarsi che vengano eseguiti nel server.</span><span class="sxs-lookup"><span data-stu-id="698bc-109">To run packages from a client computer, you need to launch them in a manner that ensures that the packages run on the server.</span></span>  
  
 <span data-ttu-id="698bc-110">Per ulteriori informazioni sul caricamento e l'esecuzione di un pacchetto salvato, vedere:</span><span class="sxs-lookup"><span data-stu-id="698bc-110">For more information about loading and running a saved package, see:</span></span>  
  
-   [<span data-ttu-id="698bc-111">Caricamento ed esecuzione di un pacchetto locale a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="698bc-111">Loading and Running a Local Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
  
-   [<span data-ttu-id="698bc-112">Caricamento ed esecuzione di un pacchetto remoto a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="698bc-112">Loading and Running a Remote Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
  
 <span data-ttu-id="698bc-113">Per ulteriori informazioni sull'esecuzione di un pacchetto e il caricamento del relativo output in un programma personalizzato, vedere:</span><span class="sxs-lookup"><span data-stu-id="698bc-113">For more information about running a package and loading its output into a custom program, see:</span></span>  
  
-   [<span data-ttu-id="698bc-114">Caricamento dell'output di un pacchetto locale</span><span class="sxs-lookup"><span data-stu-id="698bc-114">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
<span data-ttu-id="698bc-115">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="698bc-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="698bc-116">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="698bc-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="698bc-117">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="698bc-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="698bc-118">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="698bc-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="698bc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="698bc-119">See Also</span></span>  
 <span data-ttu-id="698bc-120">[Caricamento ed esecuzione di un pacchetto locale a livello di codice](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="698bc-120">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 <span data-ttu-id="698bc-121">[Caricamento ed esecuzione di un pacchetto remoto a livello di programmazione](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="698bc-121">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="698bc-122">Caricamento dell'output di un pacchetto locale</span><span class="sxs-lookup"><span data-stu-id="698bc-122">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
