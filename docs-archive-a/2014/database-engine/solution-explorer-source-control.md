---
title: Controllo del codice sorgente Esplora soluzioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Visual SourceSafe
- SQL Server Management Studio [SQL Server], source control services
- source-controlled files [SQL Server]
- source controls [SQL Server Management Studio], services
- version control services [SQL Server]
- file source control services [SQL Server]
- VSS [Visual SourceSafe]
ms.assetid: 6373adb8-3d81-4945-a9fc-1d0d5799d29a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 46471ba8149c26f80e78006bc3a8befc2e81b416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635196"
---
# <a name="solution-explorer-source-control"></a><span data-ttu-id="3c017-102">Controllo del codice sorgente di Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="3c017-102">Solution Explorer Source Control</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="3c017-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]Esplora soluzioni possono essere integrati in un sistema di controllo del codice sorgente distinto.</span><span class="sxs-lookup"><span data-stu-id="3c017-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Solution Explorer can be integrated into a separate source control system.</span></span> <span data-ttu-id="3c017-104">Dopo aver integrato una soluzione o un progetto in un sistema di controllo del codice sorgente, è possibile controllare l'accesso ai file e il controllo delle versioni per gli script e le query dei progetti.</span><span class="sxs-lookup"><span data-stu-id="3c017-104">Once a solution or project is integrated into a source control system, you can control file access and versioning for the scripts and queries in your projects.</span></span>  
  
## <a name="solution-and-project-source-control"></a><span data-ttu-id="3c017-105">Controllo del codice sorgente di soluzioni e progetti</span><span class="sxs-lookup"><span data-stu-id="3c017-105">Solution and Project Source Control</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="3c017-106">Il controllo del codice sorgente è un sistema nel quale un componente centrale di un prodotto server archivia e tiene traccia delle versioni dei file, controllando inoltre l'accesso ai file.</span><span class="sxs-lookup"><span data-stu-id="3c017-106">Source control refers to a system in which a central piece of server software stores and tracks file versions, and also controls access to files.</span></span> <span data-ttu-id="3c017-107">Un tipico sistema di controllo del codice sorgente include un provider di controllo del codice sorgente e due o più client di controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-107">A typical source control system includes a source control provider and two or more source control clients.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3c017-108">può essere integrato con un servizio di controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-108">can be integrated with a source control service.</span></span> <span data-ttu-id="3c017-109">Ciò significa che è possibile utilizzare lo strumento come client per il provider di controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-109">This means you can use the tool as a client for your source control provider.</span></span> <span data-ttu-id="3c017-110">Senza uscire dall'ambiente, è possibile gestire facilmente sia i progetti individuali che quelli di team.</span><span class="sxs-lookup"><span data-stu-id="3c017-110">Without leaving the environment, you can manage your individual and team projects easily.</span></span> <span data-ttu-id="3c017-111">Il provider del controllo del codice sorgente non è incluso in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c017-111">The source control provider is not included with [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
#### <a name="to-select-a-source-control-provider"></a><span data-ttu-id="3c017-112">Per selezionare un provider del controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="3c017-112">To select a source control provider</span></span>  
  
1.  <span data-ttu-id="3c017-113">Installare la parte client del provider del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-113">Install the client portion of your source control provider.</span></span>  
  
2.  <span data-ttu-id="3c017-114">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="3c017-114">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="3c017-115">Nella finestra di dialogo **Opzioni** espandere **controllo del codice sorgente**, quindi fare clic sulla pagina **Selezione plug-in** .</span><span class="sxs-lookup"><span data-stu-id="3c017-115">In the **Options** dialog box, expand **Source Control**, and then click the **Plug-in Selection** page.</span></span>  
  
4.  <span data-ttu-id="3c017-116">Nella casella **plug-in del controllo del codice sorgente corrente** selezionare il plug-in del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-116">In the **Current source control plug-in** box, select the source control plug-in.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c017-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3c017-117">In This Section</span></span>  
  
|<span data-ttu-id="3c017-118">Argomento</span><span class="sxs-lookup"><span data-stu-id="3c017-118">Topic</span></span>|<span data-ttu-id="3c017-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c017-119">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3c017-120">Nozioni fondamentali sul controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="3c017-120">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)|<span data-ttu-id="3c017-121">Viene definita la terminologia di base del controllo del codice sorgente e vengono spiegati i vantaggi per il progetto offerti dai servizi di controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-121">Defines basic source control terminology, and explains how your project can benefit from using source control services.</span></span>|  
|[<span data-ttu-id="3c017-122">Aggiungere soluzioni e progetti al controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="3c017-122">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)|<span data-ttu-id="3c017-123">Viene spiegato come utilizzare l'ambiente [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] per aggiungere soluzioni e progetti al controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-123">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to add solutions and projects to source control.</span></span>|  
|[<span data-ttu-id="3c017-124">Apertura di soluzioni e progetti dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="3c017-124">Open Solutions and Projects from Source Control</span></span>](../../2014/database-engine/open-solutions-and-projects-from-source-control.md)|<span data-ttu-id="3c017-125">Viene spiegato come utilizzare l'ambiente [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] per aprire soluzioni e progetti inclusi nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-125">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to open source-controlled solutions and projects.</span></span>|  
|[<span data-ttu-id="3c017-126">Gestione delle estrazioni</span><span class="sxs-lookup"><span data-stu-id="3c017-126">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)|<span data-ttu-id="3c017-127">Viene spiegato come estrarre soluzioni e file dal controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-127">Explains how to check out solutions and files from source control.</span></span>|  
|[<span data-ttu-id="3c017-128">Gestione delle archiviazioni</span><span class="sxs-lookup"><span data-stu-id="3c017-128">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)|<span data-ttu-id="3c017-129">Viene spiegato come archiviare soluzioni e file nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3c017-129">Explains how to check solutions and files into source control.</span></span>|  
|[<span data-ttu-id="3c017-130">Impostazione e recupero delle informazioni sulla versione</span><span class="sxs-lookup"><span data-stu-id="3c017-130">Set and Retrieve Version Information</span></span>](../../2014/database-engine/set-and-retrieve-version-information.md)|<span data-ttu-id="3c017-131">Viene spiegato come recuperare la cronologia di un progetto o di un elemento, una copia locale di un elemento o come confrontare due versioni di un elemento.</span><span class="sxs-lookup"><span data-stu-id="3c017-131">Explains how to retrieve the history of a project or item, retrieve a local copy of an item, or compare two item versions.</span></span>|  
|||  
  
## <a name="see-also"></a><span data-ttu-id="3c017-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c017-132">See Also</span></span>  
 <span data-ttu-id="3c017-133">[Esplora soluzioni](../ssms/solution/solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="3c017-133">[Solution Explorer](../ssms/solution/solution-explorer.md) </span></span>  
 <span data-ttu-id="3c017-134">[Soluzioni &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="3c017-134">[Solutions &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span></span>  
 <span data-ttu-id="3c017-135">[Progetti &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3c017-135">[Projects &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="3c017-136">File per la gestione di soluzioni e progetti</span><span class="sxs-lookup"><span data-stu-id="3c017-136">Files That Manage Solutions and Projects</span></span>](../ssms/solution/files-that-manage-solutions-and-projects.md)  
  
  
