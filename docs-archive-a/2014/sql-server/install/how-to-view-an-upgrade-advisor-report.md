---
title: 'Procedura: visualizzazione di un report di preparazione aggiornamento | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- viewing reports
- Upgrade Advisor [SQL Server], reports
- SQL Server Upgrade Advisor, reports
- reports [Upgrade Advisor], viewing
ms.assetid: d13b38af-0ac3-4030-83cd-e7d7825dd09f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e6df35b869186a601458889c348153093ccbce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637044"
---
# <a name="how-to-view-an-upgrade-advisor-report"></a><span data-ttu-id="5b809-102">Procedura: Visualizzazione di un report di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="5b809-102">How to: View an Upgrade Advisor Report</span></span>
  <span data-ttu-id="5b809-103">Preparazione aggiornamento crea report per ogni componente selezionato da analizzare.</span><span class="sxs-lookup"><span data-stu-id="5b809-103">Upgrade Advisor creates reports for each component that you select to analyze.</span></span> <span data-ttu-id="5b809-104">In questo argomento viene descritto come visualizzare un report di Preparazione aggiornamento dalla pagina iniziale di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5b809-104">This topic describes how to view an Upgrade Advisor report from the Upgrade Advisor start page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5b809-105">Il visualizzatore di report carica file in base ai nomi file standard.</span><span class="sxs-lookup"><span data-stu-id="5b809-105">The report viewer loads files based on standard file names.</span></span> <span data-ttu-id="5b809-106">Se i file sono stati rinominati, non verranno caricati.</span><span class="sxs-lookup"><span data-stu-id="5b809-106">If the files have been renamed, the report viewer will not load them.</span></span>  
  
### <a name="to-view-a-report"></a><span data-ttu-id="5b809-107">Per visualizzare un report</span><span class="sxs-lookup"><span data-stu-id="5b809-107">To view a report</span></span>  
  
1.  <span data-ttu-id="5b809-108">Fare clic su **Start**, scegliere **tutti i programmi**, fare clic su **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]** , quindi su \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Preparazione aggiornamento\*\*.</span><span class="sxs-lookup"><span data-stu-id="5b809-108">Click **Start**, click **All Programs**, click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**, and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
2.  <span data-ttu-id="5b809-109">Nella pagina iniziale di preparazione aggiornamento fare clic su **Avvia Visualizzatore report di preparazione aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="5b809-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
3.  <span data-ttu-id="5b809-110">Per selezionare un report nel percorso predefinito nel computer:</span><span class="sxs-lookup"><span data-stu-id="5b809-110">To select a report in the default location on your computer:</span></span>  
  
    1.  <span data-ttu-id="5b809-111">Nell'elenco **Server** selezionare un server.</span><span class="sxs-lookup"><span data-stu-id="5b809-111">In the **Server** list, select a server.</span></span>  
  
    2.  <span data-ttu-id="5b809-112">Nell'elenco **istanza o** componente selezionare una combinazione componente o componente/istanza.</span><span class="sxs-lookup"><span data-stu-id="5b809-112">In the **Instance or component** list, select a component or component/instance combination.</span></span>  
  
     <span data-ttu-id="5b809-113">Per selezionare un report in un altro percorso:</span><span class="sxs-lookup"><span data-stu-id="5b809-113">To select a report at another location:</span></span>  
  
    1.  <span data-ttu-id="5b809-114">Fare clic sul collegamento **Apri report** .</span><span class="sxs-lookup"><span data-stu-id="5b809-114">Click the **Open Report** link.</span></span>  
  
    2.  <span data-ttu-id="5b809-115">Passare al percorso del report, quindi fare doppio clic sul file XML.</span><span class="sxs-lookup"><span data-stu-id="5b809-115">Browse to the report location and then double-click the XML file.</span></span>  
  
     <span data-ttu-id="5b809-116">Preparazione aggiornamento consente di archiviare fino a cinque report dell'analisi precedente come cronologia.</span><span class="sxs-lookup"><span data-stu-id="5b809-116">Upgrade Advisor stores up to five reports from previous analysis as history.</span></span> <span data-ttu-id="5b809-117">Per visualizzare i report, fare clic sulla casella di riepilogo a discesa **report** e selezionare un report.</span><span class="sxs-lookup"><span data-stu-id="5b809-117">To view these reports, click the **Report** drop-down list box, and select a report.</span></span> <span data-ttu-id="5b809-118">I report vengono elencati in base al valore timestamp che indica la data e l'ora in cui sono stati generati.</span><span class="sxs-lookup"><span data-stu-id="5b809-118">The reports are listed by the timestamp from when they were generated.</span></span>  
  
     <span data-ttu-id="5b809-119">Il report contiene i dettagli seguenti per tutti i problemi rilevati:</span><span class="sxs-lookup"><span data-stu-id="5b809-119">The report contains the following details for all detected issues:</span></span>  
  
    -   <span data-ttu-id="5b809-120">**Importanza**, che indica l'importanza della risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="5b809-120">**Importance**, which indicates how important it is to fix the issue.</span></span>  
  
    -   <span data-ttu-id="5b809-121">**Quando correggere**, che indica se è necessario (o) correggere il problema prima o dopo l'aggiornamento a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , prima o dopo la migrazione dell'applicazione o dei dati o in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="5b809-121">**When to fix**, which indicates if you should (or must) fix the issue before or after upgrading to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], before or after migrating the application or data, or anytime.</span></span>  
  
    -   <span data-ttu-id="5b809-122">Breve descrizione del problema.</span><span class="sxs-lookup"><span data-stu-id="5b809-122">A brief description of the issue.</span></span>  
  
4.  <span data-ttu-id="5b809-123">Se il report contiene più di 20 elementi, fare clic sulla freccia avanti verde nella parte superiore o inferiore del report per visualizzare il set successivo di elementi.</span><span class="sxs-lookup"><span data-stu-id="5b809-123">If the report contains more than 20 items, click the green forward arrow at the top or bottom of the report to view the next set of items.</span></span> <span data-ttu-id="5b809-124">Fare clic sul pulsante indietro verde per visualizzare i 20 elementi precedenti.</span><span class="sxs-lookup"><span data-stu-id="5b809-124">Click the green back button to view the previous 20 items.</span></span>  
  
5.  <span data-ttu-id="5b809-125">Per ordinare il report, fare clic su un'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="5b809-125">To sort the report, click a column heading.</span></span>  
  
6.  <span data-ttu-id="5b809-126">Per visualizzare i dettagli per un elemento specifico, fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="5b809-126">To view details for a specific item, click the item.</span></span> <span data-ttu-id="5b809-127">Verrà visualizzata una descrizione del problema, oltre a opzioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="5b809-127">A description of the issue appears, along with additional options:</span></span>  
  
    -   <span data-ttu-id="5b809-128">Per visualizzare gli oggetti in cui è stato rilevato il problema, fare clic su **Mostra oggetti interessati**.</span><span class="sxs-lookup"><span data-stu-id="5b809-128">To view the objects where this issue was found, click **Show affected objects**.</span></span>  
  
    -   <span data-ttu-id="5b809-129">Per visualizzare la guida per il problema, fare clic su **ulteriori informazioni su questo problema e su come risolverlo**.</span><span class="sxs-lookup"><span data-stu-id="5b809-129">To view help for the issue, click **Tell me more about this issue and how to resolve it**.</span></span>  
  
    -   <span data-ttu-id="5b809-130">Per contrassegnare il problema come risolto, in modo da nascondere il problema quando si visualizza di nuovo il report, selezionare **questo problema è stato risolto**.</span><span class="sxs-lookup"><span data-stu-id="5b809-130">To mark the issue as resolved, which hides the issue when you view the report again, select **This issue has been resolved**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b809-131">Il report può contenere un elemento relativo a problemi non rilevabili,</span><span class="sxs-lookup"><span data-stu-id="5b809-131">The report may contain an item for undetectable issues.</span></span> <span data-ttu-id="5b809-132">ovvero problemi che non è possibile rilevare o che genererebbero un numero eccessivo di risultati falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="5b809-132">These are issues that cannot be detected or that would generate too many false-positive results.</span></span> <span data-ttu-id="5b809-133">Fare clic sul collegamento **ulteriori informazioni su questo problema e su come risolverlo** per visualizzare un elenco di problemi non rilevabili per il componente.</span><span class="sxs-lookup"><span data-stu-id="5b809-133">Click the **Tell me more about this issue and how to resolve it** link to see a list of undetectable issues for the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b809-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b809-134">See Also</span></span>  
 <span data-ttu-id="5b809-135">[Procedura: esportazione di report](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="5b809-135">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="5b809-136">[Procedura: esecuzione dell'analisi guidata di preparazione aggiornamento](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="5b809-136">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="5b809-137">[Risoluzione dei problemi di aggiornamento](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="5b809-137">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 <span data-ttu-id="5b809-138">[Procedure per preparazione aggiornamento](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="5b809-138">[Upgrade Advisor How-to Topics](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span></span>  
 [<span data-ttu-id="5b809-139">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="5b809-139">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
