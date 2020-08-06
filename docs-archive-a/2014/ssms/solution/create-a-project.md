---
title: Creare un progetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], creating
ms.assetid: 7897be19-365b-4b06-bcf0-8a669f67a673
author: stevestein
ms.author: sstein
ms.openlocfilehash: 269feee7225ceb09b1c2ed86419b19ec4001c1f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630227"
---
# <a name="create-a-project"></a><span data-ttu-id="68387-102">Creazione di un progetto</span><span class="sxs-lookup"><span data-stu-id="68387-102">Create a Project</span></span>
  <span data-ttu-id="68387-103">È possibile creare uno o più progetti in una soluzione esistente.</span><span class="sxs-lookup"><span data-stu-id="68387-103">You can create one or more projects within an existing solution.</span></span>  
  
### <a name="to-create-a-new-project-and-add-it-to-a-solution"></a><span data-ttu-id="68387-104">Per creare un nuovo progetto e aggiungerlo a una soluzione</span><span class="sxs-lookup"><span data-stu-id="68387-104">To create a new project and add it to a solution</span></span>  
  
1.  <span data-ttu-id="68387-105">Selezionare la soluzione in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="68387-105">In Solution Explorer, select the solution.</span></span>  
  
2.  <span data-ttu-id="68387-106">Nel menu **File** , fare clic su **Aggiungi**e scegliere **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="68387-106">On the **File** menu, point to **Add**, and click **New Project**.</span></span>  
  
3.  <span data-ttu-id="68387-107">Nella finestra di dialogo  **Nuovo progetto** fare clic su un tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="68387-107">In the  **New Project** dialog box, click a type of project.</span></span>  
  
     <span data-ttu-id="68387-108">**Modelli**</span><span class="sxs-lookup"><span data-stu-id="68387-108">**Templates**</span></span>  
     <span data-ttu-id="68387-109">Nella casella **Modelli** selezionare un modello.</span><span class="sxs-lookup"><span data-stu-id="68387-109">In the **Templates** box, select a template.</span></span> <span data-ttu-id="68387-110">Sotto la casella **Modelli** viene visualizzata una breve descrizione del modello di progetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="68387-110">A brief description of the selected project template appears beneath the **Templates** box.</span></span>  
  
     <span data-ttu-id="68387-111">**Nome**</span><span class="sxs-lookup"><span data-stu-id="68387-111">**Name**</span></span>  
     <span data-ttu-id="68387-112">Immettere il nome del progetto script che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="68387-112">Enter the name of the script project you want to create.</span></span> <span data-ttu-id="68387-113">Nel percorso visualizzato nel campo **Percorso** viene inoltre creata una cartella con lo stesso nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="68387-113">A folder with the same name as the project is also created in the location displayed in the **Location** field.</span></span> <span data-ttu-id="68387-114">Per alcuni progetti, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] crea file di origine e altri file di supporto e li aggiunge alla nuova cartella di progetto.</span><span class="sxs-lookup"><span data-stu-id="68387-114">For some projects, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates source and other supporting files and adds them to the new project folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="68387-115">Per alcuni tipi di progetto, la casella di testo **Name** non è disponibile perché il nome viene impostato automaticamente quando si specifica il percorso.</span><span class="sxs-lookup"><span data-stu-id="68387-115">For some project types, the **Name** text box is unavailable because specifying the location sets the name.</span></span> <span data-ttu-id="68387-116">Le applicazioni e i servizi Web ad esempio vengono posizionati su un server Web e i relativi nomi si basano sulla directory virtuale specificata su tale server.</span><span class="sxs-lookup"><span data-stu-id="68387-116">For example, Web applications and Web services are located on a Web server and derive their name from the virtual directory specified on that server.</span></span>  
  
     <span data-ttu-id="68387-117">I nomi non possono includere i caratteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="68387-117">Names cannot contain the following characters:</span></span>  
  
    -   <span data-ttu-id="68387-118">Cancelletto (#)</span><span class="sxs-lookup"><span data-stu-id="68387-118">Pound (#)</span></span>  
  
    -   <span data-ttu-id="68387-119">Percentuale (%)</span><span class="sxs-lookup"><span data-stu-id="68387-119">Percent (%)</span></span>  
  
    -   <span data-ttu-id="68387-120">E commerciale (&)</span><span class="sxs-lookup"><span data-stu-id="68387-120">Ampersand (&)</span></span>  
  
    -   <span data-ttu-id="68387-121">Asterisco (\*)</span><span class="sxs-lookup"><span data-stu-id="68387-121">Asterisk (\*)</span></span>  
  
    -   <span data-ttu-id="68387-122">Barra verticale {|}</span><span class="sxs-lookup"><span data-stu-id="68387-122">Vertical bar (|)</span></span>  
  
    -   <span data-ttu-id="68387-123">Barra rovesciata (\\)</span><span class="sxs-lookup"><span data-stu-id="68387-123">Backslash (\\)</span></span>  
  
    -   <span data-ttu-id="68387-124">Due punti (:)</span><span class="sxs-lookup"><span data-stu-id="68387-124">Colon (:)</span></span>  
  
    -   <span data-ttu-id="68387-125">Virgoletta (")</span><span class="sxs-lookup"><span data-stu-id="68387-125">Quotation mark (")</span></span>  
  
    -   <span data-ttu-id="68387-126">Minore di (\<)</span><span class="sxs-lookup"><span data-stu-id="68387-126">Less than (\<)</span></span>  
  
    -   <span data-ttu-id="68387-127">Maggiore di (>)</span><span class="sxs-lookup"><span data-stu-id="68387-127">Greater than (>)</span></span>  
  
    -   <span data-ttu-id="68387-128">Punto interrogativo (?)</span><span class="sxs-lookup"><span data-stu-id="68387-128">Question mark (?)</span></span>  
  
    -   <span data-ttu-id="68387-129">Barra (/)</span><span class="sxs-lookup"><span data-stu-id="68387-129">Forward slash (/)</span></span>  
  
    -   <span data-ttu-id="68387-130">Spazi iniziali o finali (' ')</span><span class="sxs-lookup"><span data-stu-id="68387-130">Leading or trailing spaces (' ')</span></span>  
  
    -   <span data-ttu-id="68387-131">Nomi riservati di Microsoft Windows o MS-DOS, ad esempio "nul", "aux", "con", "com1", "lpt1" e così via</span><span class="sxs-lookup"><span data-stu-id="68387-131">Names reserved for Microsoft Windows or MS-DOS, such as ("nul", "aux", "con", "com1", "lpt1", and so on)</span></span>  
  
     <span data-ttu-id="68387-132">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="68387-132">**Location**</span></span>  
     <span data-ttu-id="68387-133">Immettere il percorso in cui si desidera creare il progetto oppure sceglierne uno dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="68387-133">Enter the location where you want to create your project, or choose one from the list.</span></span>  
  
     <span data-ttu-id="68387-134">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="68387-134">**Browse**</span></span>  
     <span data-ttu-id="68387-135">Apre la finestra di dialogo **Percorso progetto** che consente di per selezionare una nuova directory in cui salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="68387-135">Displays the **Project Location** dialog box, allowing you to navigate to a new directory in which to save the project.</span></span>  
  
     <span data-ttu-id="68387-136">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="68387-136">**Solution**</span></span>  
     <span data-ttu-id="68387-137">Selezionare **Crea nuova soluzione** per creare una soluzione in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="68387-137">Select **Create new Solution** to create a solution in Solution Explorer.</span></span> <span data-ttu-id="68387-138">Selezionare **Aggiungi a soluzione** per aggiungere il nuovo progetto alla soluzione attualmente aperta in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="68387-138">Select **Add to Solution** to add the new project to the solution currently open in Solution Explorer.</span></span>  
  
     <span data-ttu-id="68387-139">**Crea directory per soluzione**</span><span class="sxs-lookup"><span data-stu-id="68387-139">**Create directory for Solution**</span></span>  
     <span data-ttu-id="68387-140">Consente di abilitare la casella di testo **Nome soluzione** .</span><span class="sxs-lookup"><span data-stu-id="68387-140">Select to enable the **(Solution) Name** text box.</span></span> <span data-ttu-id="68387-141">Questa opzione consente di creare una nuova directory con il nome scelto per il progetto e la soluzione.</span><span class="sxs-lookup"><span data-stu-id="68387-141">This option creates a new directory of the name you choose for your project and solution.</span></span>  
  
     <span data-ttu-id="68387-142">**Nome soluzione**</span><span class="sxs-lookup"><span data-stu-id="68387-142">**Solution Name**</span></span>  
     <span data-ttu-id="68387-143">Immettere il nome della nuova soluzione in cui si desidera creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="68387-143">Enter the name of the new solution in which you want your project to be created.</span></span> <span data-ttu-id="68387-144">Per impostazione predefinita, in questo campo è visualizzato lo stesso nome digitato nel campo **Nome** .</span><span class="sxs-lookup"><span data-stu-id="68387-144">By default, this field uses the same name as entered in the **Name** field.</span></span>  
  
     <span data-ttu-id="68387-145">**Note** : per accedere a questa opzione, è necessario selezionare entrambe le caselle di controllo **Crea nuova soluzione** in **Soluzione** e **Crea directory per soluzione** .</span><span class="sxs-lookup"><span data-stu-id="68387-145">**Note** To access this option, you must select both the **Create New Solution** in the **Solution** and the **Create directory for Solution** check boxes.</span></span> <span data-ttu-id="68387-146">Alcuni modelli di progetto, ad esempio le applicazioni Web, non supportano questa opzione.</span><span class="sxs-lookup"><span data-stu-id="68387-146">Some project templates do not support this option, such as Web applications.</span></span>  
  
     <span data-ttu-id="68387-147">**Aggiungi al controllo del codice sorgente**</span><span class="sxs-lookup"><span data-stu-id="68387-147">**Add to Source Control**</span></span>  
     <span data-ttu-id="68387-148">Se questa casella di controllo è selezionata, l'applicazione del controllo del codice sorgente si apre quando si fa clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="68387-148">When this check box is selected, your source control application opens when you click **OK**.</span></span> <span data-ttu-id="68387-149">Per continuare, immettere tutte le informazioni richieste dall'applicazione del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="68387-149">Complete any information required by your source control application to continue.</span></span> <span data-ttu-id="68387-150">Per utilizzare questa opzione, è necessario disporre di un'applicazione client del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="68387-150">You must have a source control client application installed to use this option.</span></span>  
  
4.  <span data-ttu-id="68387-151">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="68387-151">Click **OK**.</span></span>  
  
 <span data-ttu-id="68387-152">È possibile stabilire un nome per il progetto script. I nomi delle cartelle vengono invece stabiliti da [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="68387-152">You can set a name for the script project, but the folder names are established by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and cannot be changed.</span></span> <span data-ttu-id="68387-153">È possibile configurare il percorso e l'unità per il set di cartelle comune mediante la finestra di dialogo **Aggiungi nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="68387-153">You can configure the drive and path specification for the common set of folders by using the **Add New Project** dialog box.</span></span> <span data-ttu-id="68387-154">Fare clic con il pulsante destro del mouse sull'icona della soluzione in **Esplora soluzioni**e scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="68387-154">Right-click the solution icon in **Solution Explorer**, and then click **Add**.</span></span> <span data-ttu-id="68387-155">Il percorso predefinito per le cartelle dei progetti script è C:\Documents and Settings\\*nomeutente*\Documenti\SQL Server Management Studio\Projects\\.</span><span class="sxs-lookup"><span data-stu-id="68387-155">The default location for script project folders is: C:\Documents and Settings\\*username*\My Documents\SQL Server Management Studio\Projects\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68387-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68387-156">See Also</span></span>  
 <span data-ttu-id="68387-157">[Esplora soluzioni](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="68387-157">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="68387-158">[Aggiungere un progetto esistente a una soluzione](add-an-existing-project-to-a-solution.md) </span><span class="sxs-lookup"><span data-stu-id="68387-158">[Add an Existing Project to a Solution](add-an-existing-project-to-a-solution.md) </span></span>  
 <span data-ttu-id="68387-159">[Aggiungere nuovi elementi a un progetto](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="68387-159">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 <span data-ttu-id="68387-160">[Aggiungere elementi esistenti a un progetto](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="68387-160">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 <span data-ttu-id="68387-161">[Modificare il percorso predefinito per i progetti](change-the-default-location-for-projects.md) </span><span class="sxs-lookup"><span data-stu-id="68387-161">[Change the Default Location for Projects](change-the-default-location-for-projects.md) </span></span>  
 <span data-ttu-id="68387-162">[Rimuovere o eliminare un elemento o un progetto](remove-or-delete-an-item-or-project.md) </span><span class="sxs-lookup"><span data-stu-id="68387-162">[Remove or Delete an Item or Project](remove-or-delete-an-item-or-project.md) </span></span>  
 [<span data-ttu-id="68387-163">Eliminazione di una soluzione</span><span class="sxs-lookup"><span data-stu-id="68387-163">Delete a Solution</span></span>](delete-a-solution.md)  
  
  
