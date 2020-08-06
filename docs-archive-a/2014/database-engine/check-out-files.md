---
title: Estrai file | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- Visual Studio.SourceControl.CheckOutDialog
helpviewer_keywords:
- checking out files
ms.assetid: cc033727-51bb-4b58-a12b-8977ce61ff56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 151f554742bd6c381b27b58155d3f0e40e9eeb0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630070"
---
# <a name="check-out-files"></a><span data-ttu-id="2a050-102">Estrazione di file</span><span class="sxs-lookup"><span data-stu-id="2a050-102">Check Out Files</span></span>
  <span data-ttu-id="2a050-103">Se l'ambiente [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] non è stato configurato per consentire la modifica dei file archiviati, è necessario eseguire l'estrazione di un file prima di poterlo modificare.</span><span class="sxs-lookup"><span data-stu-id="2a050-103">Unless you have configured the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment to permit checked-in files to be edited, you must check out a file before you can modify it.</span></span> <span data-ttu-id="2a050-104">Quando si estrae un file, una copia della sua versione viene salvata sul disco locale e l'attributo di sola lettura del file viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="2a050-104">When you check out a file, a copy of the file version is copied to your local disk, and the read-only attribute of the file is removed.</span></span>  
  
 <span data-ttu-id="2a050-105">È possibile estrarre i file in modalità esclusiva o condivisa.</span><span class="sxs-lookup"><span data-stu-id="2a050-105">You can check files out either exclusively or in shared mode.</span></span> <span data-ttu-id="2a050-106">Quando si estrae un file in modalità esclusiva, il file non può essere estratto da altri utenti finché non viene archiviato.</span><span class="sxs-lookup"><span data-stu-id="2a050-106">When you check out a file exclusively, no other user can check out the file until you check it in.</span></span> <span data-ttu-id="2a050-107">Se un file viene estratto in modalità condivisa, può essere estratto e modificato da altri utenti. Al momento dell'archiviazione potrebbe essere quindi necessario unire le versioni create dai diversi utenti.</span><span class="sxs-lookup"><span data-stu-id="2a050-107">When you check out a file in shared mode, other users can check out and modify the file, and when you check it in, you may need to merge the version you have checked out with the versions created by other users.</span></span>  
  
 <span data-ttu-id="2a050-108">Usare il comando **Estrai** per estrarre i file e i progetti inclusi nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="2a050-108">Use the **Check Out** command to check out source-controlled projects and files.</span></span> <span data-ttu-id="2a050-109">Se si usa questo comando per estrarre una soluzione o un progetto, vengono estratti anche tutti i file inclusi nella soluzione o nel progetto. Tuttavia, l'estrazione di un singolo file di codice sorgente non comporta l'estrazione del progetto o della soluzione a cui appartiene.</span><span class="sxs-lookup"><span data-stu-id="2a050-109">If you use this command to check out a solution or project, all the files in the solution or project are also checked out. However, checking out an individual source code file does not result in the check out of the project or solution to which it belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a050-110">Se il [!INCLUDE[msCoName](../includes/msconame-md.md)] database di Visual SourceSafe per il progetto è configurato per consentire più estrazioni e si desidera estrarre un file esclusivamente, è necessario deselezionare l'opzione **Consenti più estrazioni** nella finestra di dialogo **Opzioni di estrazione avanzata** prima di estrarre il file.</span><span class="sxs-lookup"><span data-stu-id="2a050-110">If the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database for your project is configured to allow multiple checkouts, and you want to check out a file exclusively, you must clear the **Allow multiple checkouts** option in the **Advanced Check Out Options** dialog box before checking out the file.</span></span> <span data-ttu-id="2a050-111">Per rendere effettiva questa impostazione è necessario riavviare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a050-111">You must restart the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for this setting to take effect.</span></span>  
  
### <a name="to-check-out-a-file"></a><span data-ttu-id="2a050-112">Per estrarre un file</span><span class="sxs-lookup"><span data-stu-id="2a050-112">To check out a file</span></span>  
  
1.  <span data-ttu-id="2a050-113">In Esplora soluzioni selezionare il progetto o il file desiderato.</span><span class="sxs-lookup"><span data-stu-id="2a050-113">In Solution Explorer, select the project or file.</span></span>  
  
2.  <span data-ttu-id="2a050-114">Scegliere **controllo del codice sorgente**dal menu **file** e quindi fare clic su **Estrai per la modifica**.</span><span class="sxs-lookup"><span data-stu-id="2a050-114">On the **File** menu, point to **Source Control**, and then click **Check Out for Edit**.</span></span>  
  
3.  <span data-ttu-id="2a050-115">Se viene visualizzata la finestra **di dialogo Estrai per la modifica** , selezionare gli elementi desiderati e fare clic su **Estrai**. Se l'ambiente non è stato configurato [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] per visualizzare la finestra di dialogo **Estrai** , gli elementi selezionati in Esplora soluzioni e gli eventuali elementi figlio che potrebbero avere sono estratti immediatamente.</span><span class="sxs-lookup"><span data-stu-id="2a050-115">If the **Check Out for Edit** dialog box is displayed, select the items you want, and click **Check Out**. If you have configured the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment not to display the **Check Out** dialog box, the items selected in Solution Explorer and any children they might have are checked out immediately.</span></span>  
  
     <span data-ttu-id="2a050-116">**Estrai**</span><span class="sxs-lookup"><span data-stu-id="2a050-116">**Check Out**</span></span>  
     <span data-ttu-id="2a050-117">Consente di estrarre tutti gli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="2a050-117">Check out all the selected items.</span></span>  
  
     <span data-ttu-id="2a050-118">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2a050-118">**Columns**</span></span>  
     <span data-ttu-id="2a050-119">Consente di specificare le colonne da visualizzare e il relativo ordine.</span><span class="sxs-lookup"><span data-stu-id="2a050-119">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="2a050-120">**Commenti**</span><span class="sxs-lookup"><span data-stu-id="2a050-120">**Comments**</span></span>  
     <span data-ttu-id="2a050-121">Consente di digitare un commento da associare all'operazione di estrazione.</span><span class="sxs-lookup"><span data-stu-id="2a050-121">Specify a comment to associate with the checkout operation.</span></span>  
  
     <span data-ttu-id="2a050-122">**Non visualizzare la finestra di dialogo Estrai durante l'estrazione degli elementi**</span><span class="sxs-lookup"><span data-stu-id="2a050-122">**Don't Show Check Out dialog box when checking out items**</span></span>  
     <span data-ttu-id="2a050-123">Consente di impedire la visualizzazione della finestra di dialogo durante le operazioni di estrazione.</span><span class="sxs-lookup"><span data-stu-id="2a050-123">Suppress the dialog box during checkout operations.</span></span>  
  
     <span data-ttu-id="2a050-124">**Visualizzazione semplice**</span><span class="sxs-lookup"><span data-stu-id="2a050-124">**Flat View**</span></span>  
     <span data-ttu-id="2a050-125">Consente di visualizzare gli elementi che si stanno estraendo in elenchi semplici con la rispettiva connessione del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="2a050-125">Display the items you are checking out as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="2a050-126">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="2a050-126">**Edit**</span></span>  
     <span data-ttu-id="2a050-127">Modificare un elemento senza estrarlo. Il pulsante **modifica** viene visualizzato solo se è stato [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configurato per supportare la modifica dei file archiviati.</span><span class="sxs-lookup"><span data-stu-id="2a050-127">Modify an item without checking it out. The **Edit** button appears only if you have [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configured to support the editing of checked-in files.</span></span>  
  
     <span data-ttu-id="2a050-128">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2a050-128">**Name**</span></span>  
     <span data-ttu-id="2a050-129">Visualizza i nomi degli elementi che è possibile estrarre.</span><span class="sxs-lookup"><span data-stu-id="2a050-129">Displays the names of the items available for checkout.</span></span> <span data-ttu-id="2a050-130">Accanto a ogni elemento selezionato è disponibile una casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="2a050-130">Items that are selected appear with check boxes next to them.</span></span> <span data-ttu-id="2a050-131">Deselezionare tale casella se non si desidera estrarre l'elemento corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2a050-131">If you do not want to check out a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="2a050-132">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="2a050-132">**Options**</span></span>  
     <span data-ttu-id="2a050-133">Consente di visualizzare le opzioni di estrazione specifiche del plug-in del controllo del codice sorgente quando si fa clic sulla freccia a destra del pulsante.</span><span class="sxs-lookup"><span data-stu-id="2a050-133">Displays source control plug-in-specific checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="2a050-134">**Sort**</span><span class="sxs-lookup"><span data-stu-id="2a050-134">**Sort**</span></span>  
     <span data-ttu-id="2a050-135">Consente di scegliere l'ordine delle colonne visualizzate.</span><span class="sxs-lookup"><span data-stu-id="2a050-135">Sort the order of the displayed columns.</span></span>  
  
     <span data-ttu-id="2a050-136">**Visualizzazione albero**</span><span class="sxs-lookup"><span data-stu-id="2a050-136">**Tree View**</span></span>  
     <span data-ttu-id="2a050-137">Consente di visualizzare la gerarchia di file e cartelle relativa all'elemento che si desidera estrarre.</span><span class="sxs-lookup"><span data-stu-id="2a050-137">Display the folder and file hierarchy for the item you are checking out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a050-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a050-138">See Also</span></span>  
 <span data-ttu-id="2a050-139">[Modifica file archiviati](../../2014/database-engine/edit-checked-in-files.md) </span><span class="sxs-lookup"><span data-stu-id="2a050-139">[Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md) </span></span>  
 <span data-ttu-id="2a050-140">[Estrai automaticamente i file al momento della modifica](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span><span class="sxs-lookup"><span data-stu-id="2a050-140">[Automatically Check Out Files Upon Edit](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span></span>  
 <span data-ttu-id="2a050-141">[Annulla estrazioni](../../2014/database-engine/undo-checkouts.md) </span><span class="sxs-lookup"><span data-stu-id="2a050-141">[Undo Checkouts](../../2014/database-engine/undo-checkouts.md) </span></span>  
 [<span data-ttu-id="2a050-142">Gestione delle estrazioni</span><span class="sxs-lookup"><span data-stu-id="2a050-142">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
