---
title: Compilare progetti di database con SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], database projects
- database projects [SQL Server]
- projects [SQL Server Management Studio], about projects
- projects [SQL Server Management Studio]
ms.assetid: c2e80045-894d-44cf-b65c-e547ed738947
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3ddf3f61e69623716b2987c5c4d849398e822d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623038"
---
# <a name="build-database-projects-by-using-sql-server-management-studio"></a><span data-ttu-id="3ef81-102">Compilazione di progetti di database utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ef81-102">Build Database Projects by Using SQL Server Management Studio</span></span>
  <span data-ttu-id="3ef81-103">Un progetto di script del database è un set organizzato di script, informazioni di connessione e modelli tutti associati a un database o a una parte di un database.</span><span class="sxs-lookup"><span data-stu-id="3ef81-103">A database script project is an organized set of scripts, connection information, and templates that are all associated with a database or one part of a database.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="3ef81-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] include [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per l'amministrazione e la progettazione di database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nel contesto di un progetto script.</span><span class="sxs-lookup"><span data-stu-id="3ef81-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provides the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for administering and designing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] databases within the context of a script project.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3ef81-105">include finestre di progettazione, editor, guide e procedure guidate per assistere gli utenti nello sviluppo, nella distribuzione e nella gestione di database.</span><span class="sxs-lookup"><span data-stu-id="3ef81-105">includes designers, editors, guides and wizards to assist users in developing, deploying and maintaining databases.</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="3ef81-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ef81-106">SQL Server Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3ef81-107">è un insieme di strumenti di amministrazione per la gestione dei componenti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ef81-107">is a suite of administrative tools for managing the components belonging to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3ef81-108">Questo ambiente integrato consente l'esecuzione di un'ampia gamma di attività, quali backup dei dati, modifica delle query e automazione delle funzioni comuni, all'interno di un'unica interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3ef81-108">This integrated environment allows users to perform a variety of tasks, such as backing up data, editing queries, and automating common functions within a single interface.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3ef81-109">include i seguenti strumenti:</span><span class="sxs-lookup"><span data-stu-id="3ef81-109">includes the following tools:</span></span>  
  
-   <span data-ttu-id="3ef81-110">Editor del codice, un editor completo per la scrittura e la modifica degli script</span><span class="sxs-lookup"><span data-stu-id="3ef81-110">Code Editor is a rich script editor for writing and editing scripts.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3ef81-111">offre quattro versioni dell'editor di codice: l'editor di query [!INCLUDE[ssDE](../includes/ssde-md.md)] per script [!INCLUDE[tsql](../includes/tsql-md.md)] , l'editor di query DMX, l'editor di query MDX e l'editor di query XML/A.</span><span class="sxs-lookup"><span data-stu-id="3ef81-111">provides four versions of the Code Editor; the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor for [!INCLUDE[tsql](../includes/tsql-md.md)] scripts, the DMX Query Editor, the MDX Query Editor, and the XML/A Query Editor.</span></span>  
  
-   <span data-ttu-id="3ef81-112">Esplora oggetti, per l'individuazione, la modifica, la creazione di script o l'esecuzione di oggetti appartenenti a istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ef81-112">Object Explorer for locating, modifying, scripting or running objects belonging to instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="3ef81-113">Esplora modelli, per l'individuazione e la creazione di script di modelli.</span><span class="sxs-lookup"><span data-stu-id="3ef81-113">Template Explorer for locating and scripting templates.</span></span>  
  
-   <span data-ttu-id="3ef81-114">Esplora soluzioni, per l'organizzazione e l'archiviazione di script correlati come parti di un progetto.</span><span class="sxs-lookup"><span data-stu-id="3ef81-114">Solution Explorer for organizing and storing related scripts as parts of a project.</span></span>  
  
-   <span data-ttu-id="3ef81-115">Finestra Proprietà, per la visualizzazione delle proprietà correnti degli oggetti selezionati.</span><span class="sxs-lookup"><span data-stu-id="3ef81-115">Properties Window for displaying the current properties of selected objects.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3ef81-116">supporta processi di lavoro efficienti offrendo quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3ef81-116">supports efficient work processes by providing:</span></span>  
  
-   <span data-ttu-id="3ef81-117">Accesso disconnesso.</span><span class="sxs-lookup"><span data-stu-id="3ef81-117">Disconnected access.</span></span> <span data-ttu-id="3ef81-118">È possibile creare e modificare script senza connettersi a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ef81-118">You can write and edit scripts without connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="3ef81-119">Creazione di script da qualsiasi finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3ef81-119">Scripting from any dialog box.</span></span> <span data-ttu-id="3ef81-120">È possibile creare uno script da qualsiasi finestra di dialogo, così da poter leggere, modificare, archiviare e riutilizzare gli script dopo averli creati.</span><span class="sxs-lookup"><span data-stu-id="3ef81-120">You can create a script from any dialog box so that you can read, modify, store and reuse the scripts after you create them.</span></span>  
  
-   <span data-ttu-id="3ef81-121">Finestre di dialogo non modali.</span><span class="sxs-lookup"><span data-stu-id="3ef81-121">Nonmodal dialog boxes.</span></span> <span data-ttu-id="3ef81-122">Quando si accede a una finestra di dialogo dell'interfaccia utente è possibile esplorare altre risorse in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] senza chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="3ef81-122">When you access a UI dialog box you can browse other resources in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] without closing the dialog box.</span></span>  
  
## <a name="solutions-and-script-projects"></a><span data-ttu-id="3ef81-123">Soluzioni e progetti script</span><span class="sxs-lookup"><span data-stu-id="3ef81-123">Solutions and Script Projects</span></span>  
 <span data-ttu-id="3ef81-124">Esplora soluzioni è un'utilità per l'archiviazione e la riapertura di soluzioni di database.</span><span class="sxs-lookup"><span data-stu-id="3ef81-124">Solution Explorer is a utility to store and reopen database solutions.</span></span> <span data-ttu-id="3ef81-125">Le soluzioni consentono di organizzare progetti script e file correlati.</span><span class="sxs-lookup"><span data-stu-id="3ef81-125">Solutions organize related script projects and files.</span></span> <span data-ttu-id="3ef81-126">I progetti script consentono di archiviare file script di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , modelli SQL, informazioni di connessione e file esterni.</span><span class="sxs-lookup"><span data-stu-id="3ef81-126">Script projects store [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] script files, SQL templates, connection information and other miscellaneous files.</span></span> <span data-ttu-id="3ef81-127">Quando uno script è salvato in un progetto script è possibile:</span><span class="sxs-lookup"><span data-stu-id="3ef81-127">When a script is saved in a script project, users are able to:</span></span>  
  
-   <span data-ttu-id="3ef81-128">Mantenere il controllo della versione degli script.</span><span class="sxs-lookup"><span data-stu-id="3ef81-128">Maintain version control on scripts.</span></span>  
  
-   <span data-ttu-id="3ef81-129">Archiviare opzioni di risultati con gli script.</span><span class="sxs-lookup"><span data-stu-id="3ef81-129">Store results options with a script.</span></span>  
  
-   <span data-ttu-id="3ef81-130">Organizzare script correlati in un unico progetto script.</span><span class="sxs-lookup"><span data-stu-id="3ef81-130">Organize related scripts in a single script project.</span></span>  
  
-   <span data-ttu-id="3ef81-131">Salvare le informazioni di connessione con gli script.</span><span class="sxs-lookup"><span data-stu-id="3ef81-131">Save connection information with scripts.</span></span>  
  
 <span data-ttu-id="3ef81-132">Esplora soluzioni è uno strumento per gli sviluppatori che creano e riutilizzano script correlati allo stesso progetto.</span><span class="sxs-lookup"><span data-stu-id="3ef81-132">Solution Explorer is a tool for developers who are creating and reusing scripts that are related to the same project.</span></span> <span data-ttu-id="3ef81-133">Se in un momento successivo si rende necessaria un'attività simile, è possibile utilizzare i gruppi di script archiviati in un progetto.</span><span class="sxs-lookup"><span data-stu-id="3ef81-133">If a similar task is required later, you can use group of scripts that were stored in a project.</span></span> <span data-ttu-id="3ef81-134">Se sono state create applicazioni usando [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], Esplora soluzioni risulterà semplice da usare.</span><span class="sxs-lookup"><span data-stu-id="3ef81-134">If you have created applications by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], you will find Solution Explorer very familiar.</span></span>  
  
 <span data-ttu-id="3ef81-135">Una soluzione è costituita da uno o più progetti script.</span><span class="sxs-lookup"><span data-stu-id="3ef81-135">A solution consists of one or more script projects.</span></span> <span data-ttu-id="3ef81-136">Un progetto è costituito da uno o più script o connessioni.</span><span class="sxs-lookup"><span data-stu-id="3ef81-136">A project consists of one or more scripts or connections.</span></span> <span data-ttu-id="3ef81-137">Un progetto può anche contenere file che non sono script.</span><span class="sxs-lookup"><span data-stu-id="3ef81-137">A project may also include nonscript files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef81-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ef81-138">See Also</span></span>  
 <span data-ttu-id="3ef81-139">[Usa SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3ef81-139">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="3ef81-140">[Editor di query e di testo &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3ef81-140">[Query and Text Editors &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="3ef81-141">Soluzioni &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3ef81-141">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solution/solutions-sql-server-management-studio.md)  
  
  
