---
title: Aggiungere elementi esistenti a un progetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 084b3879-e96b-45a7-b421-6a4b0db2b92b
author: stevestein
ms.author: sstein
ms.openlocfilehash: cffa683bfa2a2c81c059d887231531f03d5c892b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637540"
---
# <a name="add-existing-items-to-a-project"></a><span data-ttu-id="62dc8-102">Aggiunta di elementi esistenti a un progetto</span><span class="sxs-lookup"><span data-stu-id="62dc8-102">Add Existing Items to a Project</span></span>
  <span data-ttu-id="62dc8-103">È possibile aggiungere nuovi elementi a un progetto per estendere la funzionalità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62dc8-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="62dc8-104">Un elemento esistente può essere una query o un file esterno.</span><span class="sxs-lookup"><span data-stu-id="62dc8-104">An existing item can be a query or a miscellaneous file.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="62dc8-105">ha due tipi di progetto: progetto script di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e progetto script di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="62dc8-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="62dc8-106">I file di query che è possibile aggiungere varieranno a seconda del tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="62dc8-106">The project type determines the query files that you can add to the project.</span></span> <span data-ttu-id="62dc8-107">È possibile aggiungere, ad esempio, una query [!INCLUDE[tsql](../../includes/tsql-md.md)] (un file con estensione sql) a un progetto script di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ma non a un progetto script di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="62dc8-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span> <span data-ttu-id="62dc8-108">Per associare estensioni di file aggiuntive a un tipo di progetto, vedere [associare estensioni di file a un editor di codice](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span><span class="sxs-lookup"><span data-stu-id="62dc8-108">To associate additional file extensions to a project type, see [Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span></span>  
  
### <a name="to-add-an-existing-query-or-a-miscellaneous-file-to-a-project"></a><span data-ttu-id="62dc8-109">Per aggiungere una query o un file esterno esistente a un progetto</span><span class="sxs-lookup"><span data-stu-id="62dc8-109">To add an existing query or a miscellaneous file to a project</span></span>  
  
1.  <span data-ttu-id="62dc8-110">In Esplora soluzioni selezionare un progetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="62dc8-110">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="62dc8-111">Nel menu **Progetto** fare clic su **Aggiungi elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="62dc8-111">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
     <span data-ttu-id="62dc8-112">**Look in**</span><span class="sxs-lookup"><span data-stu-id="62dc8-112">**Look in**</span></span>  
     <span data-ttu-id="62dc8-113">Utilizzare questo elenco per individuare i file o le cartelle da aggiungere al progetto.</span><span class="sxs-lookup"><span data-stu-id="62dc8-113">Locate the files or folders to add to your project from this list.</span></span> <span data-ttu-id="62dc8-114">Per i servizi Web XML e le applicazioni Web ASP.NET, i file si trovano nel server Web.</span><span class="sxs-lookup"><span data-stu-id="62dc8-114">For XML Web services and ASP.NET Web applications, the files are located on the Web server.</span></span>  
  
     <span data-ttu-id="62dc8-115">**Desktop**</span><span class="sxs-lookup"><span data-stu-id="62dc8-115">**Desktop**</span></span>  
     <span data-ttu-id="62dc8-116">Consente di visualizzare i file e le cartelle che si trovano sul desktop.</span><span class="sxs-lookup"><span data-stu-id="62dc8-116">Displays the files and folders located on the desktop.</span></span>  
  
     <span data-ttu-id="62dc8-117">**Progetti**</span><span class="sxs-lookup"><span data-stu-id="62dc8-117">**My Projects**</span></span>  
     <span data-ttu-id="62dc8-118">Consente di visualizzare i file e le cartelle nella posizione predefinita **Progetti** .</span><span class="sxs-lookup"><span data-stu-id="62dc8-118">Displays the files and folders at the default **My Projects** location.</span></span>  
  
     <span data-ttu-id="62dc8-119">**Risorse del computer**</span><span class="sxs-lookup"><span data-stu-id="62dc8-119">**My Computer**</span></span>  
     <span data-ttu-id="62dc8-120">Consente di visualizzare il contenuto della cartella **Risorse del computer** .</span><span class="sxs-lookup"><span data-stu-id="62dc8-120">Displays the contents of your **My Computer** folder.</span></span>  
  
     <span data-ttu-id="62dc8-121">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="62dc8-121">**File name**</span></span>  
     <span data-ttu-id="62dc8-122">Questa opzione consente di applicare un filtro alle cartelle e ai file visualizzati.</span><span class="sxs-lookup"><span data-stu-id="62dc8-122">Use this option to filter the files and folders that are displayed.</span></span> <span data-ttu-id="62dc8-123">Immettere il nome completo o parziale del file in base al quale applicare il filtro. Utilizzare un asterisco (`*`) come carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="62dc8-123">Enter the full or partial file name on which to filter; use an asterisk (`*`) as a wildcard.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62dc8-124">Per spostarsi su percorsi Web e di rete, immettere l'URL o il percorso di rete nella casella **Nome file** .</span><span class="sxs-lookup"><span data-stu-id="62dc8-124">Navigate to Web and network locations by entering the URL or network path in the **File name** box.</span></span> <span data-ttu-id="62dc8-125">Ad esempio, se si digita **http://mywebsite** vengono visualizzati i file disponibili nel percorso Web mywebsite, mentre se si digita **\\\myserver\myshare** vengono visualizzati i file disponibili nel percorso myshare del server myserver.</span><span class="sxs-lookup"><span data-stu-id="62dc8-125">For example, **http://mywebsite** displays the files available at the mywebsite Web location, and **\\\myserver\myshare** displays the files available at the myshare location on myserver.</span></span>  
  
     <span data-ttu-id="62dc8-126">**Tipo file**</span><span class="sxs-lookup"><span data-stu-id="62dc8-126">**Files of type**</span></span>  
     <span data-ttu-id="62dc8-127">Questa opzione consente di applicare un filtro ai file in base all'estensione.</span><span class="sxs-lookup"><span data-stu-id="62dc8-127">Use this option to filter files based on file extension.</span></span> <span data-ttu-id="62dc8-128">In ogni prodotto vengono elencati i filtri predefiniti dei tipi di file più comuni.</span><span class="sxs-lookup"><span data-stu-id="62dc8-128">Each product lists default filters of the most common file types.</span></span>  
  
     <span data-ttu-id="62dc8-129">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="62dc8-129">**Add**</span></span>  
     <span data-ttu-id="62dc8-130">Utilizzare questo pulsante a discesa per aggiungere l'elemento al progetto e aprirlo nell'editor predefinito.</span><span class="sxs-lookup"><span data-stu-id="62dc8-130">Use this drop-down button to add the item to the project and open the item in its default editor.</span></span>  
  
    -   <span data-ttu-id="62dc8-131">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="62dc8-131">**Add**</span></span>  
  
         <span data-ttu-id="62dc8-132">Consente di copiare l'elemento esistente nella cartella del progetto memorizzata sul disco e di aggiungerlo sotto il progetto selezionato in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="62dc8-132">Copies the existing item to your project folder on disk and adds the item under the selected project in Solution Explorer.</span></span> <span data-ttu-id="62dc8-133">Le modifiche apportate all'elemento non si rifletteranno su quello presente nella posizione originale.</span><span class="sxs-lookup"><span data-stu-id="62dc8-133">Any changes made to the item are not reflected in the item at the original location.</span></span> <span data-ttu-id="62dc8-134">Si tratta dell'editor predefinito per il tipo di file.</span><span class="sxs-lookup"><span data-stu-id="62dc8-134">This is the default editor for the file type.</span></span>  
  
    -   <span data-ttu-id="62dc8-135">**Aggiungi come collegamento**</span><span class="sxs-lookup"><span data-stu-id="62dc8-135">**Add As Link**</span></span>  
  
         <span data-ttu-id="62dc8-136">Consente di aggiungere il file selezionato al progetto e di aprirlo nell'editor predefinito per il tipo di file.</span><span class="sxs-lookup"><span data-stu-id="62dc8-136">Adds the selected file to the project and opens it with the default editor for the file type.</span></span> <span data-ttu-id="62dc8-137">Il file selezionato originariamente viene aperto, ma non copiato nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="62dc8-137">This option opens the originally selected file and does not copy the file to the project folder.</span></span>  
  
3.  <span data-ttu-id="62dc8-138">Se vengono aggiunti file di query, nella finestra di dialogo di connessione verrà visualizzato un messaggio in cui si chiede di specificare una connessione per la query.</span><span class="sxs-lookup"><span data-stu-id="62dc8-138">If you are adding query files, the connection dialog will prompt you to specify a connection for the query.</span></span> <span data-ttu-id="62dc8-139">Se non si desidera associare una connessione alla query, fare clic su **Annulla** nella finestra di dialogo di connessione.</span><span class="sxs-lookup"><span data-stu-id="62dc8-139">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the query.</span></span>  
  
4.  <span data-ttu-id="62dc8-140">Il file verrà aggiunto alla cartella **Query** o **File esterni** del progetto.</span><span class="sxs-lookup"><span data-stu-id="62dc8-140">The file will be added to the **Queries** or **Miscellaneous Files** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62dc8-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62dc8-141">See Also</span></span>  
 <span data-ttu-id="62dc8-142">[Esplora soluzioni](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="62dc8-142">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="62dc8-143">[Aggiungere nuovi elementi a un progetto](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="62dc8-143">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="62dc8-144">Rimuovere o eliminare un elemento o un progetto</span><span class="sxs-lookup"><span data-stu-id="62dc8-144">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
