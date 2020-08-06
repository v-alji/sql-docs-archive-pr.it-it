---
title: Impostare e recuperare le informazioni sulla versione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- historical information [SQL Server]
- source controls [SQL Server Management Studio], version information
- retrieving version information
- current file version information
- version control services [SQL Server], retrieving version information
- version control services [SQL Server], setting version information
- status information [SQL Server], source control files
- historical information [SQL Server], source control files
ms.assetid: c3f253c4-4e3d-48e8-8d90-bd6ee899faf7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: eff3d40ba9b663ba8611508c5b9f0c9961005b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712347"
---
# <a name="set-and-retrieve-version-information"></a><span data-ttu-id="167a9-102">Impostazione e recupero delle informazioni sulla versione</span><span class="sxs-lookup"><span data-stu-id="167a9-102">Set and Retrieve Version Information</span></span>
  <span data-ttu-id="167a9-103">Le informazioni sulla versione comprendono la cronologia e lo stato corrente di un file incluso nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="167a9-103">Version information includes the history and current status of a source-controlled file.</span></span> <span data-ttu-id="167a9-104">Per ogni file incluso nel controllo del codice sorgente, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe conserva una cronologia completa che consente di tenere traccia dell'evoluzione di uno o più file nel tempo.</span><span class="sxs-lookup"><span data-stu-id="167a9-104">For every source-controlled file, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe maintains a comprehensive history, so you can track the evolution of one or more files over time.</span></span> <span data-ttu-id="167a9-105">È inoltre possibile utilizzare queste informazioni per recuperare una copia locale di qualsiasi versione del file oppure eseguire il confronto tra due versioni qualsiasi del file.</span><span class="sxs-lookup"><span data-stu-id="167a9-105">You can also use this information to retrieve a local copy of any version of the file or to compare any two file versions.</span></span>  
  
 <span data-ttu-id="167a9-106">Nella cronologia di un file sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="167a9-106">The history of a file includes:</span></span>  
  
-   <span data-ttu-id="167a9-107">Il numero della versione, che ne identifica la sequenza rispetto ad altre versioni dello stesso file.</span><span class="sxs-lookup"><span data-stu-id="167a9-107">The version number, which identifies its sequence among other versions of the same file.</span></span>  
  
-   <span data-ttu-id="167a9-108">L'azione eseguita.</span><span class="sxs-lookup"><span data-stu-id="167a9-108">The action performed.</span></span> <span data-ttu-id="167a9-109">Tra le operazioni rilevate vi sono la creazione, l'archiviazione e l'eliminazione del file.</span><span class="sxs-lookup"><span data-stu-id="167a9-109">Tracked operations include file creation, check in, and deletion.</span></span>  
  
-   <span data-ttu-id="167a9-110">Il nome dell'utente che ha eseguito un'azione sul file.</span><span class="sxs-lookup"><span data-stu-id="167a9-110">The user name of the person who performed an action involving the file.</span></span>  
  
-   <span data-ttu-id="167a9-111">La data e l'ora in cui l'operazione è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="167a9-111">The date and time when the operation was performed.</span></span>  
  
 <span data-ttu-id="167a9-112">In Visual SourceSafe vengono inoltre conservate le informazioni relative alla soluzione attualmente caricata.</span><span class="sxs-lookup"><span data-stu-id="167a9-112">Visual SourceSafe also maintains current status information on the currently loaded solution.</span></span> <span data-ttu-id="167a9-113">Queste informazioni offrono uno snapshot dello stato attuale del file, inclusi:</span><span class="sxs-lookup"><span data-stu-id="167a9-113">This information provides a snapshot of the current state of the file, including:</span></span>  
  
-   <span data-ttu-id="167a9-114">L'identità dell'utente il cui file viene estratto.</span><span class="sxs-lookup"><span data-stu-id="167a9-114">The identity of the user who has the file checked out.</span></span>  
  
-   <span data-ttu-id="167a9-115">Il numero dell'ultima versione del file selezionato.</span><span class="sxs-lookup"><span data-stu-id="167a9-115">The latest version number of the selected file.</span></span>  
  
-   <span data-ttu-id="167a9-116">La data in cui la versione è stata creata.</span><span class="sxs-lookup"><span data-stu-id="167a9-116">The date when the version was created.</span></span>  
  
-   <span data-ttu-id="167a9-117">Il commento dell'utente associato alla versione.</span><span class="sxs-lookup"><span data-stu-id="167a9-117">The user comment associated with the version.</span></span>  
  
-   <span data-ttu-id="167a9-118">I percorsi dei progetti con cui il file viene condiviso.</span><span class="sxs-lookup"><span data-stu-id="167a9-118">The paths to the projects with which the file is shared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="167a9-119">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="167a9-119">In This Section</span></span>  
  
-   [<span data-ttu-id="167a9-120">Visualizzazione della cronologia dei file</span><span class="sxs-lookup"><span data-stu-id="167a9-120">View File History</span></span>](../../2014/database-engine/view-file-history.md)  
  
-   [<span data-ttu-id="167a9-121">Visualizzare cronologia progetti</span><span class="sxs-lookup"><span data-stu-id="167a9-121">View Project History</span></span>](../../2014/database-engine/view-project-history.md)  
  
-   [<span data-ttu-id="167a9-122">Visualizzazione dello stato dei file</span><span class="sxs-lookup"><span data-stu-id="167a9-122">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
-   [<span data-ttu-id="167a9-123">Recupero di file</span><span class="sxs-lookup"><span data-stu-id="167a9-123">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
-   [<span data-ttu-id="167a9-124">Specifica di una versione come ultima versione</span><span class="sxs-lookup"><span data-stu-id="167a9-124">Specify a Version as the Latest Version</span></span>](../../2014/database-engine/specify-a-version-as-the-latest-version.md)  
  
-   [<span data-ttu-id="167a9-125">Confronto di file</span><span class="sxs-lookup"><span data-stu-id="167a9-125">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
-   [<span data-ttu-id="167a9-126">Condividere file</span><span class="sxs-lookup"><span data-stu-id="167a9-126">Share Files</span></span>](../../2014/database-engine/share-files.md)  
  
-   [<span data-ttu-id="167a9-127">Creazione di report relativi alla cronologia e allo stato</span><span class="sxs-lookup"><span data-stu-id="167a9-127">Create History and Status Reports</span></span>](../../2014/database-engine/create-history-and-status-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="167a9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="167a9-128">See Also</span></span>  
 [<span data-ttu-id="167a9-129">Nozioni fondamentali sul controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="167a9-129">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
