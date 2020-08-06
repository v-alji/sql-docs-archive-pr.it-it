---
title: Uso dei report | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- overriding reports
- Upgrade Advisor Report Viewer
- reports [Upgrade Advisor], about reports
- formatting reports
- resolved issues [Upgrade Advisor]
- distributing reports [Reporting Services]
- filtering reports [Reporting Services]
- removing report items
- viewing reports
- rerunning analysis
- information issues [Upgrade Advisor]
- deleting report items
- icons [Upgrade Advisor]
- Upgrade Advisor [SQL Server], reports
- sending reports
- blocking issues [Upgrade Advisor]
- sharing reports
- reports [Upgrade Advisor]
- SQL Server Upgrade Advisor, reports
- modifying reports
- distributing reports [Reporting Services], about report distribution
- warnings [Upgrade Advisor]
- analyzing system [Upgrade Advisor], reports
ms.assetid: 4a3cb94a-a7ac-4cec-94c7-db26fcf6d161
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f52afcfdaa7de33d83d64a049f9a350f0463b4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726436"
---
# <a name="using-reports"></a><span data-ttu-id="1a97e-102">Utilizzo dei report</span><span class="sxs-lookup"><span data-stu-id="1a97e-102">Using Reports</span></span>
  <span data-ttu-id="1a97e-103">Per ogni componente e, se necessario, per ogni istanza analizzata tramite l'Analisi guidata di Preparazione aggiornamento su un server viene generato un report distinto,</span><span class="sxs-lookup"><span data-stu-id="1a97e-103">A separate report is generated for each component, and, where necessary, each instance, that the Upgrade Advisor Analysis Wizard analyzes on a server.</span></span> <span data-ttu-id="1a97e-104">in cui sono forniti dettagli su problemi noti che influiscono su un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1a97e-104">The report provides details about known issues that affect an upgrade.</span></span> <span data-ttu-id="1a97e-105">Il report contiene inoltre collegamenti a informazioni e ad azioni consigliate per la risoluzione dei problemi identificati.</span><span class="sxs-lookup"><span data-stu-id="1a97e-105">It also provides links to information and suggested actions for addressing the identified issues.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a97e-106">Se il Visualizzatore report di preparazione aggiornamento non trova alcun report nella directory dei report predefinita, è possibile caricare un report da una directory diversa utilizzando il collegamento **Apri report** .</span><span class="sxs-lookup"><span data-stu-id="1a97e-106">If the Upgrade Advisor Report Viewer does not find any reports in the default reports directory, you can load a report from a different directory by using the **Open Report** link.</span></span>  
  
## <a name="viewing-reports"></a><span data-ttu-id="1a97e-107">Visualizzazione dei report</span><span class="sxs-lookup"><span data-stu-id="1a97e-107">Viewing Reports</span></span>  
 <span data-ttu-id="1a97e-108">Utilizzare il Visualizzatore report di Preparazione aggiornamento per visualizzare i report di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1a97e-108">You use the Upgrade Advisor Report Viewer to view Upgrade Advisor reports.</span></span> <span data-ttu-id="1a97e-109">Per visualizzare i report, nella pagina iniziale di preparazione aggiornamento fare clic su **Avvia Visualizzatore report di preparazione aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="1a97e-109">To view reports, on the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
 <span data-ttu-id="1a97e-110">Dopo avere caricato un report per un server, è possibile selezionare un componente per cui visualizzare i problemi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1a97e-110">After you load a report for a server, you can select a component for which you want to see upgrade issues.</span></span> <span data-ttu-id="1a97e-111">È possibile applicare un filtro dalla casella **Filtra** per per vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a97e-111">You can apply a filter from the **Filter By** box to see the following:</span></span>  
  
-   <span data-ttu-id="1a97e-112">Tutti i problemi</span><span class="sxs-lookup"><span data-stu-id="1a97e-112">All issues</span></span>  
  
-   <span data-ttu-id="1a97e-113">Tutti i problemi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1a97e-113">All upgrade issues</span></span>  
  
-   <span data-ttu-id="1a97e-114">Problemi di pre-aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1a97e-114">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="1a97e-115">Tutti i problemi di migrazione</span><span class="sxs-lookup"><span data-stu-id="1a97e-115">All migration issues</span></span>  
  
-   <span data-ttu-id="1a97e-116">Problemi risolti</span><span class="sxs-lookup"><span data-stu-id="1a97e-116">Resolved issues</span></span>  
  
-   <span data-ttu-id="1a97e-117">Problemi irrisolti</span><span class="sxs-lookup"><span data-stu-id="1a97e-117">Unresolved issues</span></span>  
  
 <span data-ttu-id="1a97e-118">Se il report contiene più di 20 problemi, è possibile passare al gruppo di problemi successivo o precedente facendo clic su **Avanti 20** o **20 precedente** nella parte superiore o inferiore dell'elenco problemi.</span><span class="sxs-lookup"><span data-stu-id="1a97e-118">If your report has more than 20 issues, you can move to the next or previous group of issues by clicking **Next 20** or **Previous 20** at the top or bottom of the issues list.</span></span>  
  
 <span data-ttu-id="1a97e-119">È possibile visualizzare fino a cinque report salvati selezionando i report dall'elenco a discesa **report** .</span><span class="sxs-lookup"><span data-stu-id="1a97e-119">You can view up to five saved reports by selecting the reports from the **Report** drop-down list box.</span></span> <span data-ttu-id="1a97e-120">I report vengono elencati in base al valore timestamp che indica la data e l'ora in cui sono stati generati.</span><span class="sxs-lookup"><span data-stu-id="1a97e-120">The reports are listed by the timestamp from when they were generated.</span></span>  
  
## <a name="report-format"></a><span data-ttu-id="1a97e-121">Formato dei report</span><span class="sxs-lookup"><span data-stu-id="1a97e-121">Report Format</span></span>  
 <span data-ttu-id="1a97e-122">Il visualizzatore di report suddivide i problemi in tre colonne.</span><span class="sxs-lookup"><span data-stu-id="1a97e-122">The report viewer displays report issues in three columns.</span></span> <span data-ttu-id="1a97e-123">Ogni problema è comprimibile, in modo che sia possibile nascondere la descrizione e visualizzare solo le informazioni essenziali.</span><span class="sxs-lookup"><span data-stu-id="1a97e-123">Each issue is collapsible so that you can hide the description and view only the key information.</span></span>  
  
 <span data-ttu-id="1a97e-124">La prima colonna è la colonna **priorità** .</span><span class="sxs-lookup"><span data-stu-id="1a97e-124">The first column is the **Importance** column.</span></span> <span data-ttu-id="1a97e-125">Le icone indicano l'importanza di ogni problema: viene visualizzato un cerchio rosso con una X per problemi importanti o che bloccano l'aggiornamento oppure un triangolo giallo con un punto esclamativo per problemi paragonabili a messaggi di avviso o informativi.</span><span class="sxs-lookup"><span data-stu-id="1a97e-125">Icons indicate the importance for each issue by displaying either a red circle with an X for blocking or important issues or a yellow triangle with an exclamation mark for Warning and Information issues.</span></span> <span data-ttu-id="1a97e-126">La seconda colonna, **quando correggere**, indica quando è necessario risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="1a97e-126">The second column, **When to fix**, indicates when you must resolve the issue.</span></span> <span data-ttu-id="1a97e-127">È possibile ordinare il report in modo che sia la colonna **importanza** o **quando correggere** .</span><span class="sxs-lookup"><span data-stu-id="1a97e-127">You can sort the report on either the **Importance** or **When to fix** column.</span></span> <span data-ttu-id="1a97e-128">Nella terza colonna, **Descrizione**, viene elencato il titolo del problema.</span><span class="sxs-lookup"><span data-stu-id="1a97e-128">The third column, **Description**, lists the title of the issue.</span></span>  
  
 <span data-ttu-id="1a97e-129">È possibile espandere un problema per visualizzare informazioni aggiuntive, un collegamento a informazioni dettagliate sulla risoluzione e un collegamento per visualizzare i dettagli del problema.</span><span class="sxs-lookup"><span data-stu-id="1a97e-129">You can expand an issue to display additional information, a link to detailed information about resolving the issue, and a link to show issue details.</span></span> <span data-ttu-id="1a97e-130">Quando si fa clic sul collegamento per ottenere informazioni dettagliate per il problema, verrà visualizzato un argomento della Guida con informazioni e istruzioni per risolverlo.</span><span class="sxs-lookup"><span data-stu-id="1a97e-130">When you click the link to get detailed information for the issue, a Help topic with information about the issue and instructions for addressing the issue is displayed.</span></span> <span data-ttu-id="1a97e-131">Dopo aver risolto un problema o aver gestito gli elementi dell'azione, è possibile contrassegnare i problemi come completi selezionando la casella di controllo **questo problema è stato risolto** .</span><span class="sxs-lookup"><span data-stu-id="1a97e-131">After you have fixed an issue, or to manage your action items, you can mark issues as complete by selecting the **This issue has been resolved** check box.</span></span> <span data-ttu-id="1a97e-132">Se si desidera rimuovere i problemi risolti dall'elenco dei problemi di aggiornamento, fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="1a97e-132">If you want to remove the resolved issues from the list of upgrade issues, click **Refresh**.</span></span> <span data-ttu-id="1a97e-133">Il problema non viene visualizzato di nuovo fino a quando non si esegue l'analisi guidata di preparazione aggiornamento sullo stesso componente o si applica il filtro **problemi risolti** dall'opzione **Filtra per** .</span><span class="sxs-lookup"><span data-stu-id="1a97e-133">The issue is not displayed again until you either run the Upgrade Advisor Analysis Wizard against the same component or apply the **Resolved Issues** filter from the **Filter By** option.</span></span>  
  
## <a name="report-files"></a><span data-ttu-id="1a97e-134">File di report</span><span class="sxs-lookup"><span data-stu-id="1a97e-134">Report Files</span></span>  
 <span data-ttu-id="1a97e-135">L'analisi guidata di preparazione aggiornamento consente di creare report nella directory My Documents \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade Advisor\110\Reports e di creare una sottodirectory per ogni server analizzato.</span><span class="sxs-lookup"><span data-stu-id="1a97e-135">The Upgrade Advisor Analysis Wizard creates reports in the My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports directory and creates a subdirectory for each server that you analyze.</span></span> <span data-ttu-id="1a97e-136">I file di report sono in formato XML e seguono una convenzione di denominazione specifica.</span><span class="sxs-lookup"><span data-stu-id="1a97e-136">The report files are XML files that follow a specific naming convention.</span></span> <span data-ttu-id="1a97e-137">Quando si avvia il Visualizzatore report di Preparazione aggiornamento, vengono visualizzati i file di report della directory predefinita.</span><span class="sxs-lookup"><span data-stu-id="1a97e-137">When you launch the Upgrade Advisor Report Viewer, the report files in the default directory are displayed.</span></span> <span data-ttu-id="1a97e-138">Se vengono copiati file di report in questa cartella, è necessario che rispettino la convenzione di denominazione, altrimenti non verranno visualizzati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1a97e-138">If you copy report files into this folder, they must adhere to the naming convention or the report viewer will not display them automatically.</span></span>  
  
 <span data-ttu-id="1a97e-139">Se si desidera condividere le informazioni con altri utenti, è possibile inviare il report XML.</span><span class="sxs-lookup"><span data-stu-id="1a97e-139">If you want to share the information with other people, you can send them the XML report.</span></span> <span data-ttu-id="1a97e-140">In alternativa, se si desidera utilizzare un'altra applicazione, è possibile esportare il report in un file con valori delimitati da virgole da utilizzare per creare un foglio di calcolo, un file di testo o un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1a97e-140">Or, if you want to use another application, you can export the report into a comma-separated value file that you can use to create a spreadsheet, text file, or e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a97e-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a97e-141">See Also</span></span>  
 <span data-ttu-id="1a97e-142">[Procedura: visualizzazione di un report di preparazione aggiornamento](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span><span class="sxs-lookup"><span data-stu-id="1a97e-142">[How to: View an Upgrade Advisor Report](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span></span>  
 <span data-ttu-id="1a97e-143">[Procedura: esportazione di report](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="1a97e-143">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="1a97e-144">[Procedura: filtrare i report](../../../2014/sql-server/install/how-to-filter-reports.md) </span><span class="sxs-lookup"><span data-stu-id="1a97e-144">[How to: Filter Reports](../../../2014/sql-server/install/how-to-filter-reports.md) </span></span>  
 <span data-ttu-id="1a97e-145">[Risoluzione dei problemi di aggiornamento](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="1a97e-145">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="1a97e-146">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="1a97e-146">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
