---
title: File per la gestione di soluzioni e progetti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], files
- .ssmssln files
- .ssmsmobileproj files
- .ssmsasproj files
- .ssmssqlproj files
- .sqlsuo files
- files [SQL Server Management Studio], projects
ms.assetid: e19d2859-0b97-4727-ac27-c4c226d86b2f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c94f1f853263c3969961de91ec95b921f5d78ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715928"
---
# <a name="files-that-manage-solutions-and-projects"></a><span data-ttu-id="180fa-102">File per la gestione di soluzioni e progetti</span><span class="sxs-lookup"><span data-stu-id="180fa-102">Files That Manage Solutions and Projects</span></span>
  <span data-ttu-id="180fa-103">Questo argomento descrive i tipi di file specifici di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="180fa-103">This topic describes the file types that are specific to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="180fa-104">Per impostazione predefinita, tutte le soluzioni e i relativi progetti vengono creati in \Documenti\SQL Server Management Studio Projects.</span><span class="sxs-lookup"><span data-stu-id="180fa-104">By default, all solutions and their projects are created in \My Documents\SQL Server Management Studio Projects.</span></span>  
  
## <a name="management-studio-solution-files"></a><span data-ttu-id="180fa-105">File della soluzione di Management Studio</span><span class="sxs-lookup"><span data-stu-id="180fa-105">Management Studio Solution Files</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="180fa-106">usa tipi di file diversi rispetto a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="180fa-106">uses different file types than [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span></span> <span data-ttu-id="180fa-107">Ciò vuol dire che non è possibile aprire una soluzione [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="180fa-107">This means you cannot open a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or in Visual Studio.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="180fa-108">I file della soluzione consentono a Esplora soluzioni di visualizzare un'interfaccia grafica per la gestione dei file.</span><span class="sxs-lookup"><span data-stu-id="180fa-108">solution files allow Solution Explorer to display a graphical interface for managing your files.</span></span>  
  
|<span data-ttu-id="180fa-109">Estensione</span><span class="sxs-lookup"><span data-stu-id="180fa-109">Extension</span></span>|<span data-ttu-id="180fa-110">Tipo file</span><span class="sxs-lookup"><span data-stu-id="180fa-110">File type</span></span>|<span data-ttu-id="180fa-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="180fa-111">Description</span></span>|<span data-ttu-id="180fa-112">Creato da</span><span class="sxs-lookup"><span data-stu-id="180fa-112">Created by</span></span>|  
|---------------|---------------|-----------------|----------------|  
|<span data-ttu-id="180fa-113">ssmssln</span><span class="sxs-lookup"><span data-stu-id="180fa-113">.ssmssln</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="180fa-114">Oggetto della soluzione</span><span class="sxs-lookup"><span data-stu-id="180fa-114">Solution Object</span></span>|<span data-ttu-id="180fa-115">Fornisce l'ambiente con riferimenti alla posizione sul disco di progetti, elementi di progetto e soluzione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="180fa-115">Provides the environment with references to the location on disk of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] projects, project items, and solution</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]|  
  
## <a name="management-studio-project-files"></a><span data-ttu-id="180fa-116">File del progetto di Management Studio</span><span class="sxs-lookup"><span data-stu-id="180fa-116">Management Studio Project Files</span></span>  
 <span data-ttu-id="180fa-117">Mentre le soluzioni contengono i file della soluzione per la gestione degli oggetti presenti in una soluzione, i progetti contengono i file del progetto.</span><span class="sxs-lookup"><span data-stu-id="180fa-117">In the same way that solutions contain solution files that manage objects in a solution, projects contain project files.</span></span> <span data-ttu-id="180fa-118">Il tipo di file del progetto creato da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per un progetto dipende dal modello utilizzato per la creazione del progetto stesso.</span><span class="sxs-lookup"><span data-stu-id="180fa-118">The type of project file that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates for a project depends on the template used to create the project.</span></span> <span data-ttu-id="180fa-119">Nella tabella seguente viene descritto il tipo di file creato per ogni progetto.</span><span class="sxs-lookup"><span data-stu-id="180fa-119">The following table describes the type of file created for each project.</span></span>  
  
|<span data-ttu-id="180fa-120">Estensione</span><span class="sxs-lookup"><span data-stu-id="180fa-120">Extension</span></span>|<span data-ttu-id="180fa-121">Modello di progetto</span><span class="sxs-lookup"><span data-stu-id="180fa-121">Project template</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="180fa-122">ssmssqlproj</span><span class="sxs-lookup"><span data-stu-id="180fa-122">.ssmssqlproj</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="180fa-123">Progetto di script</span><span class="sxs-lookup"><span data-stu-id="180fa-123">Scripts Project</span></span>|  
|<span data-ttu-id="180fa-124">ssmsasproj</span><span class="sxs-lookup"><span data-stu-id="180fa-124">.ssmsasproj</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="180fa-125">Progetto di script</span><span class="sxs-lookup"><span data-stu-id="180fa-125">Scripts Project</span></span>|  
  
## <a name="location-of-solution-level-files"></a><span data-ttu-id="180fa-126">Posizione dei file a livello di soluzione</span><span class="sxs-lookup"><span data-stu-id="180fa-126">Location of Solution-Level Files</span></span>  
 <span data-ttu-id="180fa-127">Per impostazione predefinita, i file a livello di soluzione vengono creati nella directory fisica del primo progetto creato con la soluzione.</span><span class="sxs-lookup"><span data-stu-id="180fa-127">By default, solution-level files are created in the physical directory of the first project that is created with the solution.</span></span> <span data-ttu-id="180fa-128">È possibile specificare una directory per la soluzione creando una soluzione oppure specificare la directory quando si crea un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="180fa-128">You can specify a directory for the solution by creating a solution, or you can specify the directory when you create a new project.</span></span>  
  
 <span data-ttu-id="180fa-129">Se la struttura della directory è simile alla struttura logica visualizzata in Esplora soluzioni, è più facile individuare i file del progetto e della soluzione e condividerli con altri sviluppatori di un team.</span><span class="sxs-lookup"><span data-stu-id="180fa-129">If you have a directory structure similar to the logical structure shown in Solution Explorer, project and solution files are easier to locate and share with other developers on a team.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="180fa-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="180fa-130">See Also</span></span>  
 <span data-ttu-id="180fa-131">[Gestire file con codifica](manage-files-with-encoding.md) </span><span class="sxs-lookup"><span data-stu-id="180fa-131">[Manage Files with Encoding](manage-files-with-encoding.md) </span></span>  
 <span data-ttu-id="180fa-132">[File esterni](miscellaneous-files.md) </span><span class="sxs-lookup"><span data-stu-id="180fa-132">[Miscellaneous Files](miscellaneous-files.md) </span></span>  
 <span data-ttu-id="180fa-133">[Esplora soluzioni](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="180fa-133">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="180fa-134">[Soluzioni &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="180fa-134">[Solutions &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="180fa-135">[Progetti &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="180fa-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="180fa-136">Controllo del codice sorgente di Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="180fa-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
