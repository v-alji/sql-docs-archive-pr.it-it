---
title: Avvio dello strumento Ottimizzazione guidata motore di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- tuning databases [SQL Server]
- Database Engine Tuning Advisor [SQL Server], starting
ms.assetid: 4abc0e10-96fd-4e46-93d6-d7ee03eec844
author: stevestein
ms.author: sstein
ms.openlocfilehash: ad8a594873e581d116acd50a336652f27002112d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719218"
---
# <a name="launching-database-engine-tuning-advisor"></a><span data-ttu-id="b4a9c-102">Avvio dello strumento Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="b4a9c-102">Launching Database Engine Tuning Advisor</span></span>
  <span data-ttu-id="b4a9c-103">Accedere in primo luogo all'interfaccia utente grafica (GUI) dello strumento Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-103">To begin, open the Database Engine Tuning Advisor graphical user interface (GUI).</span></span> <span data-ttu-id="b4a9c-104">Al primo uso, per inizializzare l'applicazione è necessario che lo strumento Ottimizzazione guidata motore di database sia avviato da un membro del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="b4a9c-104">On first use, a member of the **sysadmin** fixed server role must launch Database Engine Tuning Advisor to initialize the application.</span></span> <span data-ttu-id="b4a9c-105">Dopo l'inizializzazione i membri del ruolo predefinito del database **db_owner** possono usare lo strumento Ottimizzazione guidata motore di database per ottimizzare i database di cui sono proprietari.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-105">After initialization, members of the **db_owner** fixed database role can use Database Engine Tuning Advisor to tune databases that they own.</span></span> <span data-ttu-id="b4a9c-106">Per altre informazioni sull'inizializzazione di Ottimizzazione guidata motore di database, vedere [Avvio e utilizzo di Ottimizzazione guidata motore di database](../../relational-databases/performance/database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="b4a9c-106">For more information about initializing Database Engine Tuning Advisor, see [Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md).</span></span>  
  
### <a name="open-the-database-engine-tuning-advisor-gui"></a><span data-ttu-id="b4a9c-107">Accesso all'interfaccia utente grafica dello strumento Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="b4a9c-107">Open the Database Engine Tuning Advisor GUI</span></span>  
  
1.  <span data-ttu-id="b4a9c-108">Dal menu **Start** di Windows scegliere **Tutti i programmi**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Strumenti per le prestazioni**e quindi fare clic su **Ottimizzazione guidata motore di database**.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-108">On the Windows **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and then click **Database Engine Tuning Advisor**.</span></span>  
  
2.  <span data-ttu-id="b4a9c-109">Nella finestra di dialogo **Connetti al server** verificare le impostazioni predefinite e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-109">In the **Connect to Server** dialog box, verify the default settings, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="b4a9c-110">Per impostazione predefinita, la configurazione all'avvio dello strumento Ottimizzazione guidata motore di database è quella illustrata nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="b4a9c-110">By default, Database Engine Tuning Advisor opens to the configuration in the following illustration:</span></span>  
  
 <span data-ttu-id="b4a9c-111">![Finestra predefinita di Ottimizzazione guidata motore di database](media/defaultdtagui.gif "Finestra predefinita di Ottimizzazione guidata motore di database")</span><span class="sxs-lookup"><span data-stu-id="b4a9c-111">![Database Engine Tuning Advisor default window](media/defaultdtagui.gif "Database Engine Tuning Advisor default window")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4a9c-112">Nella casella scheda e **nome sessione** vengono visualizzati il nome del computer e l'istanza a cui si è connessi.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-112">The tab and **Session Name** box display the name of your computer and the instance you are connected to.</span></span> <span data-ttu-id="b4a9c-113">Inoltre, vengono visualizzate la data e l'ora correnti.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-113">The tab and box also display the current date and time.</span></span>  
  
 <span data-ttu-id="b4a9c-114">Al primo avvio dell'interfaccia utente grafica dello strumento Ottimizzazione guidata motore di database vengono visualizzati due riquadri principali.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-114">Two main panes are displayed in the Database Engine Tuning Advisor GUI when it is first opened.</span></span>  
  
-   <span data-ttu-id="b4a9c-115">Il riquadro sinistro contiene Monitoraggio sessione in cui sono elencate tutte le sessioni di ottimizzazione eseguite su questa [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istanza.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-115">The left pane contains the Session Monitor, which lists all tuning sessions that have been performed on this [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="b4a9c-116">All'avvio dello strumento Ottimizzazione guidata motore di database, nella parte superiore del riquadro viene visualizzata una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-116">When you open Database Engine Tuning Advisor, it displays a new session at the top of the pane.</span></span> <span data-ttu-id="b4a9c-117">È possibile assegnare un nome alla sessione nel riquadro adiacente.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-117">You can name this session in the adjacent pane.</span></span> <span data-ttu-id="b4a9c-118">L'elenco contiene inizialmente una sola sessione.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-118">Initially, only a default session is listed.</span></span> <span data-ttu-id="b4a9c-119">Si tratta della sessione predefinita creata automaticamente dallo strumento Ottimizzazione guidata motore di database per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-119">This is the default session that Database Engine Tuning Advisor automatically creates for you.</span></span> <span data-ttu-id="b4a9c-120">Dopo aver eseguito l'ottimizzazione dei database, tutte le sessioni di ottimizzazione per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alle quali si è connessi verranno elencate al di sotto della nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-120">After you have tuned databases, all tuning sessions for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to which you are connected are listed below the new session.</span></span> <span data-ttu-id="b4a9c-121">È possibile fare clic con il pulsante destro del mouse su una sessione di ottimizzazione per rinominarla, chiuderla, eliminarla o clonarla.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-121">You can right-click a tuning session to rename it, close it, delete it, or clone it.</span></span> <span data-ttu-id="b4a9c-122">Se si fa clic con il pulsante destro del mouse nell'elenco è possibile ordinare le sessioni in base al nome, allo stato, alla data e all'ora di creazione oppure creare una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-122">If you right-click in the list you can sort the sessions by name, status, or creation time, or create a new session.</span></span> <span data-ttu-id="b4a9c-123">Nella parte inferiore del riquadro vengono visualizzati i dettagli della sessione di ottimizzazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-123">In the bottom section of this pane, details of the selected tuning session are displayed.</span></span> <span data-ttu-id="b4a9c-124">È possibile scegliere di visualizzare i dettagli organizzati in categorie usando il pulsante **Per categoria** oppure in un elenco alfabetico usando il pulsante **Per nome** .</span><span class="sxs-lookup"><span data-stu-id="b4a9c-124">You can choose to display the details organized into categories with the **Categorized** button, or you can display them in an alphabetized list by using the **Alphabetical** button.</span></span> <span data-ttu-id="b4a9c-125">È inoltre possibile nascondere Monitoraggio sessione trascinando il bordo destro del riquadro verso il lato sinistro della finestra.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-125">You can also hide Session Monitor by dragging the right pane border to the left side of the window.</span></span> <span data-ttu-id="b4a9c-126">Per visualizzarlo nuovamente, trascinare il bordo del riquadro verso destra.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-126">To view it again, drag the pane border back to the right.</span></span> <span data-ttu-id="b4a9c-127">Monitoraggio sessione consente di visualizzare sessioni di ottimizzazione precedenti e di utilizzarle per la creazione di nuove sessioni con definizioni simili.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-127">Session Monitor enables you to view previous tuning sessions, or to use them to create new sessions with similar definitions.</span></span> <span data-ttu-id="b4a9c-128">È inoltre possibile utilizzare Monitoraggio sessione per valutare le indicazioni di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-128">You can also use Session Monitor to evaluate tuning recommendations.</span></span> <span data-ttu-id="b4a9c-129">Per altre informazioni, vedere [Visualizzare e utilizzare l'output di Ottimizzazione guidata motore di database](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="b4a9c-129">For more information, see [View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="b4a9c-130">Usare il pulsante **Indietro** nel browser per tornare a questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-130">Use the **Back** button on your browser to return to this tutorial.</span></span>  
  
-   <span data-ttu-id="b4a9c-131">Il riquadro destro contiene le schede **Generale** e **Opzioni di ottimizzazione** .</span><span class="sxs-lookup"><span data-stu-id="b4a9c-131">The right pane contains the **General** and the **Tuning Options** tabs.</span></span> <span data-ttu-id="b4a9c-132">In questo riquadro è possibile definire la sessione di ottimizzazione del Motore di database.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-132">This is where you can define your Database Engine Tuning session.</span></span> <span data-ttu-id="b4a9c-133">Nella scheda **Generale** è possibile digitare un nome per la sessione di ottimizzazione, specificare il file o la tabella del carico di lavoro da usare e selezionare i database e le tabelle che si vuole ottimizzare in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-133">In the **General** tab, you type the name for your tuning session, specify the workload file or table to use, and select the databases and tables you want to tune in this session.</span></span> <span data-ttu-id="b4a9c-134">Un carico di lavoro è un set di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sui database che si desidera ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-134">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="b4a9c-135">Lo strumento Ottimizzazione guidata motore di database utilizza file di traccia, tabelle di traccia, script [!INCLUDE[tsql](../../includes/tsql-md.md)] o file XML come input del carico di lavoro per l'ottimizzazione dei database.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-135">Database Engine Tuning Advisor uses trace files, trace tables, [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, or XML files as workload input when tuning databases.</span></span> <span data-ttu-id="b4a9c-136">Nella scheda **Opzioni di ottimizzazione** è possibile selezionare le strutture di progettazione fisica dei database (indici e viste indicizzate) e la strategia di partizionamento che verrà seguita dallo strumento Ottimizzazione guidata motore di database durante l'analisi.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-136">On the **Tuning Options** tab, you can select the physical database design structures (indexes or indexed views) and the partitioning strategy that you want Database Engine Tuning Advisor to consider during its analysis.</span></span> <span data-ttu-id="b4a9c-137">In questa scheda è inoltre possibile specificare il tempo massimo consentito per l'ottimizzazione di un carico di lavoro con lo strumento Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-137">On this tab you also can specify the maximum time that Database Engine Tuning Advisor takes to tune a workload.</span></span> <span data-ttu-id="b4a9c-138">Per impostazione predefinita, lo strumento Ottimizzazione guidata motore di database eseguirà l'ottimizzazione di un carico di lavoro in un'ora.</span><span class="sxs-lookup"><span data-stu-id="b4a9c-138">By default, Database Engine Tuning Advisor will tune a workload for one hour.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4a9c-139">Lo strumento Ottimizzazione guidata motore di database può usare come input file in formato XML quando uno script [!INCLUDE[tsql](../../includes/tsql-md.md)] viene importato dall'editor di query di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4a9c-139">Database Engine Tuning Advisor can take XML files as input when a [!INCLUDE[tsql](../../includes/tsql-md.md)] script is imported from [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span> <span data-ttu-id="b4a9c-140">Per altre informazioni, vedere la sezione relativa all'avvio dello strumento Ottimizzazione guidata motore di database dall'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [Avvio e utilizzo di Ottimizzazione guidata motore di database](../../relational-databases/performance/database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="b4a9c-140">For more information, see the section on launching Database Engine Tuning Advisor from the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor in [Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b4a9c-141">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="b4a9c-141">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b4a9c-142">Impostazione del layout e delle opzioni dello strumento</span><span class="sxs-lookup"><span data-stu-id="b4a9c-142">Setting Tool Options and Layout</span></span>](lesson-1-2-setting-tool-options-and-layout.md)  
  
  