---
title: Soluzioni (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- solutions [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d06a8a05-7201-4055-8cf3-21bcb4e82c25
author: stevestein
ms.author: sstein
ms.openlocfilehash: 836d3b3002d72541ad88ae55eac6d951530e0ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627012"
---
# <a name="solutions-sql-server-management-studio"></a><span data-ttu-id="048a6-102">Soluzioni (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="048a6-102">Solutions (SQL Server Management Studio)</span></span>
  <span data-ttu-id="048a6-103">Una soluzione [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] è una raccolta di uno o più progetti correlati.</span><span class="sxs-lookup"><span data-stu-id="048a6-103">A [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution is a collection of one or more related projects.</span></span> <span data-ttu-id="048a6-104">I progetti sono contenitori che gli sviluppatori utilizzano per organizzare file correlati, ad esempio set di script di amministrazione di uso comune.</span><span class="sxs-lookup"><span data-stu-id="048a6-104">Projects are containers that developers use to organize related files, such as sets of commonly used administration scripts.</span></span>  
  
## <a name="solution-overview"></a><span data-ttu-id="048a6-105">Panoramica della soluzione</span><span class="sxs-lookup"><span data-stu-id="048a6-105">Solution Overview</span></span>  
 <span data-ttu-id="048a6-106">È possibile utilizzare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] come piattaforma per lo sviluppo di script per [!INCLUDE[ssDE](../../includes/ssde-md.md)] e [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="048a6-106">You can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] as a script development platform for [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="048a6-107">Utilizzare gli editor di codice di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] per sviluppare script e query per database relazionali e multidimensionali e per raccogliere script e query correlati in progetti.</span><span class="sxs-lookup"><span data-stu-id="048a6-107">Use the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] code editors to develop scripts and queries for relational and multidimensional databases, and collect related scripts and queries together in projects.</span></span>  
  
 <span data-ttu-id="048a6-108">I progetti possono contenere:</span><span class="sxs-lookup"><span data-stu-id="048a6-108">Projects can contain:</span></span>  
  
-   <span data-ttu-id="048a6-109">Query e script che implementano processi di produzione.</span><span class="sxs-lookup"><span data-stu-id="048a6-109">Queries and scripts that implement production processes.</span></span>  
  
-   <span data-ttu-id="048a6-110">File e informazioni di connessione utilizzati da query e script.</span><span class="sxs-lookup"><span data-stu-id="048a6-110">Connection information and files used by the queries and scripts.</span></span>  
  
 <span data-ttu-id="048a6-111">È possibile combinare uno o più progetti correlati in una soluzione.</span><span class="sxs-lookup"><span data-stu-id="048a6-111">One or more related projects can be combined in a solution.</span></span> <span data-ttu-id="048a6-112">Soluzioni e progetti possono essere gestiti tramite il riquadro Esplora soluzioni in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="048a6-112">Solutions and projects can be managed by using the Solution Explorer pane in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="048a6-113">Le soluzioni e i progetti possono integrati in un database di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) o di altri provider di controllo del codice sorgente di terze parti per il rilevamento delle modifiche di sviluppo e la gestione del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="048a6-113">Solutions and projects can be integrated into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) database or other third-party source control providers, for development change tracking and life-cycle management.</span></span>  
  
## <a name="solution-tasks"></a><span data-ttu-id="048a6-114">Attività di soluzione</span><span class="sxs-lookup"><span data-stu-id="048a6-114">Solution Tasks</span></span>  
  
|<span data-ttu-id="048a6-115">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="048a6-115">Task Description</span></span>|<span data-ttu-id="048a6-116">Argomento</span><span class="sxs-lookup"><span data-stu-id="048a6-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="048a6-117">Viene descritto come creare una nuova soluzione utilizzabile per contenere uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="048a6-117">Describes how to create a new solution that can then be used to contain one or more projects.</span></span>|[<span data-ttu-id="048a6-118">Creare una nuova soluzione</span><span class="sxs-lookup"><span data-stu-id="048a6-118">Create a New Solution</span></span>](create-a-new-solution.md)|  
|<span data-ttu-id="048a6-119">Viene descritto come aprire una soluzione esistente in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="048a6-119">Describes how to open an existing solution in Solution Explorer.</span></span>|[<span data-ttu-id="048a6-120">Apertura di una soluzione esistente</span><span class="sxs-lookup"><span data-stu-id="048a6-120">Open an Existing Solution</span></span>](open-an-existing-solution.md)|  
|<span data-ttu-id="048a6-121">Viene illustrato come chiudere una soluzione.</span><span class="sxs-lookup"><span data-stu-id="048a6-121">Describes how to close a solution.</span></span>|[<span data-ttu-id="048a6-122">Chiusura di una soluzione</span><span class="sxs-lookup"><span data-stu-id="048a6-122">Close a Solution</span></span>](close-a-solution.md)|  
|<span data-ttu-id="048a6-123">Viene descritto come eliminare una soluzione.</span><span class="sxs-lookup"><span data-stu-id="048a6-123">Describes how to delete a solution.</span></span>|[<span data-ttu-id="048a6-124">Eliminazione di una soluzione</span><span class="sxs-lookup"><span data-stu-id="048a6-124">Delete a Solution</span></span>](delete-a-solution.md)|  
|<span data-ttu-id="048a6-125">Viene descritto come copiare elementi tra progetti.</span><span class="sxs-lookup"><span data-stu-id="048a6-125">Describes how to copy items between projects.</span></span>|[<span data-ttu-id="048a6-126">Copiare elementi in una soluzione</span><span class="sxs-lookup"><span data-stu-id="048a6-126">Copy Items in a Solution</span></span>](copy-items-in-a-solution.md)|  
|<span data-ttu-id="048a6-127">Viene descritto come eliminare elementi in un progetto o un intero progetto.</span><span class="sxs-lookup"><span data-stu-id="048a6-127">Describes how to delete items in a project, or an entire project.</span></span>|[<span data-ttu-id="048a6-128">Rimuovere o eliminare un elemento o un progetto</span><span class="sxs-lookup"><span data-stu-id="048a6-128">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)|  
|<span data-ttu-id="048a6-129">Viene descritto come spostare elementi tra i progetti di una soluzione.</span><span class="sxs-lookup"><span data-stu-id="048a6-129">Describes how to move items between projects in a solution.</span></span>|[<span data-ttu-id="048a6-130">Spostare elementi in una soluzione</span><span class="sxs-lookup"><span data-stu-id="048a6-130">Move Items in a Solution</span></span>](move-items-in-a-solution.md)|  
|<span data-ttu-id="048a6-131">Viene descritto come rinominare una soluzione o gli elementi nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="048a6-131">Describes how to rename a solution or the items in the solution.</span></span>|[<span data-ttu-id="048a6-132">Ridenominazione di soluzioni ed elementi del progetto</span><span class="sxs-lookup"><span data-stu-id="048a6-132">Rename Solutions and Project Items</span></span>](rename-solutions-and-project-items.md)|  
  
## <a name="see-also"></a><span data-ttu-id="048a6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="048a6-133">See Also</span></span>  
 <span data-ttu-id="048a6-134">[Esplora soluzioni](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="048a6-134">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="048a6-135">[Progetti &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="048a6-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="048a6-136">Controllo del codice sorgente di Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="048a6-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
