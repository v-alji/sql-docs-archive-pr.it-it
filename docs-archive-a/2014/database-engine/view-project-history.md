---
title: Visualizza cronologia progetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- viewing project history
- version control services [SQL Server], project history
- projects [SQL Server Management Studio], historical information
- historical information [SQL Server], projects
ms.assetid: be0ea2ac-4a35-429c-9c9e-4001ea9035a4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85028141050e19e6ed6394a5bb17709ac8f906ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637444"
---
# <a name="view-project-history"></a><span data-ttu-id="318a6-102">Visualizzare cronologia progetti</span><span class="sxs-lookup"><span data-stu-id="318a6-102">View Project History</span></span>
  <span data-ttu-id="318a6-103">Nella cronologia di un progetto di [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) è incluso un elenco di tutte le azioni eseguite su ognuno dei file del progetto, ad esempio la creazione, l'aggiunta, l'eliminazione e il recupero di file.</span><span class="sxs-lookup"><span data-stu-id="318a6-103">The history of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) project includes a list of all the actions taken on each of the project files, including file creation, addition, deletion, and recovery.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="318a6-104">Un progetto di Visual SourceSafe viene più comunemente indicato come la cartella del server di controllo del codice sorgente, ovvero il percorso nel quale viene archiviata la versione del server di un file incluso nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="318a6-104">A Visual SourceSafe project is more commonly referred to as the source control server folder, the location where the server version of a source-controlled file is stored on the server.</span></span>  
  
 <span data-ttu-id="318a6-105">Per esaminare la cronologia del progetto di Visual SourceSafe al quale appartiene la soluzione caricata attualmente, è possibile utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="318a6-105">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to examine the history of the Visual SourceSafe project to which the currently loaded solution belongs.</span></span> <span data-ttu-id="318a6-106">In base alle informazioni visualizzate nella cronologia di un progetto sarà possibile recuperare le copie locali delle versioni dei file, ripristinare le versioni eliminate oppure condividere la versione di un file tra progetti.</span><span class="sxs-lookup"><span data-stu-id="318a6-106">Based on the information displayed as part of the history of a project, you can retrieve local copies of file versions, restore deleted versions, or share a file version between projects.</span></span>  
  
### <a name="to-view-the-history-of-a-vss-project"></a><span data-ttu-id="318a6-107">Per visualizzare la cronologia di un progetto di VSS</span><span class="sxs-lookup"><span data-stu-id="318a6-107">To view the history of a VSS project</span></span>  
  
1.  <span data-ttu-id="318a6-108">In Esplora soluzioni selezionare il progetto.</span><span class="sxs-lookup"><span data-stu-id="318a6-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="318a6-109">Scegliere **controllo del codice sorgente** dal menu **file** e fare clic su **Visualizza cronologia**.</span><span class="sxs-lookup"><span data-stu-id="318a6-109">On the **File** menu, point to **Source Control** and click **View History**.</span></span>  
  
3.  <span data-ttu-id="318a6-110">Nella finestra **di dialogo cronologia di** \<Project> eseguire una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="318a6-110">In the **History of** \<Project> dialog box, perform any of the following actions:</span></span>  
  
    -   <span data-ttu-id="318a6-111">Visualizzare una copia del sistema di controllo del codice sorgente di un file selezionato.</span><span class="sxs-lookup"><span data-stu-id="318a6-111">View the source control system's copy of a selected file.</span></span>  
  
    -   <span data-ttu-id="318a6-112">Visualizzare informazioni dettagliate su un file selezionato.</span><span class="sxs-lookup"><span data-stu-id="318a6-112">View detailed information about a selected file.</span></span>  
  
    -   <span data-ttu-id="318a6-113">Recuperare un file selezionato sul disco locale.</span><span class="sxs-lookup"><span data-stu-id="318a6-113">Retrieve a selected file to your local disk.</span></span>  
  
    -   <span data-ttu-id="318a6-114">Estrarre un file selezionato.</span><span class="sxs-lookup"><span data-stu-id="318a6-114">Check out a selected file.</span></span>  
  
    -   <span data-ttu-id="318a6-115">Condividere un file selezionato tra due progetti di controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="318a6-115">Share a selected file between two source control projects.</span></span>  
  
    -   <span data-ttu-id="318a6-116">Esportare il report della cronologia su una stampante, su un file o negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="318a6-116">Export the history report to a printer, a file, or the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318a6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="318a6-117">See Also</span></span>  
 <span data-ttu-id="318a6-118">[Impostare e recuperare le informazioni sulla versione](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="318a6-118">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="318a6-119">[Visualizza stato file](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="318a6-119">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 <span data-ttu-id="318a6-120">[Recuperare i file](../../2014/database-engine/retrieve-files.md) </span><span class="sxs-lookup"><span data-stu-id="318a6-120">[Retrieve Files](../../2014/database-engine/retrieve-files.md) </span></span>  
 [<span data-ttu-id="318a6-121">Confronto di file</span><span class="sxs-lookup"><span data-stu-id="318a6-121">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
  
