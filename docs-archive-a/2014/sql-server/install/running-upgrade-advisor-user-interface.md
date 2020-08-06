---
title: Esecuzione di preparazione aggiornamento (interfaccia utente) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Report Viewer
- Upgrade Advisor [SQL Server], running
- launching Upgrade Advisor
- Upgrade Advisor Analysis Wizard
- starting Upgrade Advisor
- SQL Server Upgrade Advisor, running
ms.assetid: 7f47c9b3-88d3-43d6-837e-f157b49a55ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a5e47ef2b8183823dff884e114adc420e371adf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637597"
---
# <a name="running-upgrade-advisor-user-interface"></a><span data-ttu-id="81fc4-102">Esecuzione di Preparazione aggiornamento (interfaccia utente)</span><span class="sxs-lookup"><span data-stu-id="81fc4-102">Running Upgrade Advisor (User Interface)</span></span>
  <span data-ttu-id="81fc4-103">È possibile eseguire Preparazione aggiornamento per analizzare componenti locali o remoti durante la pianificazione dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="81fc4-103">You can run Upgrade Advisor to analyze local or remote components during upgrade planning.</span></span> <span data-ttu-id="81fc4-104">Per ogni istanza e componente analizzato, viene prodotto un report.</span><span class="sxs-lookup"><span data-stu-id="81fc4-104">Upgrade Advisor produces a report for each component and instance that is analyzed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="81fc4-105">Le istanze remote di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] non vengono analizzate.</span><span class="sxs-lookup"><span data-stu-id="81fc4-105">Upgrade Advisor does not analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="81fc4-106">Per analizzare un'istanza di [!INCLUDE[ssRS](../../includes/ssrs.md)], è necessario installare Preparazione aggiornamento nel computer in cui è installato [!INCLUDE[ssRS](../../includes/ssrs.md)].</span><span class="sxs-lookup"><span data-stu-id="81fc4-106">To analyze an instance of [!INCLUDE[ssRS](../../includes/ssrs.md)], Upgrade Advisor must be installed on the computer where [!INCLUDE[ssRS](../../includes/ssrs.md)] is installed.</span></span>  
>   
>  <span data-ttu-id="81fc4-107">Per analizzare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, è necessario che sia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] installato e [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installato nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="81fc4-107">To analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, you must have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] installed and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed on the same computer.</span></span>  
  
## <a name="running-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="81fc4-108">Esecuzione dell'Analisi guidata di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="81fc4-108">Running the Upgrade Advisor Analysis Wizard</span></span>  
 <span data-ttu-id="81fc4-109">L'esecuzione dell'Analisi guidata di Preparazione aggiornamento prevede sei passaggi:</span><span class="sxs-lookup"><span data-stu-id="81fc4-109">Running the Upgrade Advisor Analysis Wizard has six steps:</span></span>  
  
1.  <span data-ttu-id="81fc4-110">Avvio della procedura guidata dalla pagina iniziale di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="81fc4-110">Launch the wizard from the Upgrade Advisor start page.</span></span>  
  
2.  <span data-ttu-id="81fc4-111">Identificazione dei server e dei componenti da analizzare.</span><span class="sxs-lookup"><span data-stu-id="81fc4-111">Identify server and components to analyze.</span></span>  
  
3.  <span data-ttu-id="81fc4-112">Raccolta di informazioni sull'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="81fc4-112">Gather authentication information.</span></span>  
  
4.  <span data-ttu-id="81fc4-113">Raccolta di parametri aggiuntivi in base al tipo di componente.</span><span class="sxs-lookup"><span data-stu-id="81fc4-113">Gather additional parameters based on component type.</span></span>  
  
5.  <span data-ttu-id="81fc4-114">Analisi dei componenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="81fc4-114">Analyze selected components.</span></span>  
  
6.  <span data-ttu-id="81fc4-115">Generazione del report dei problemi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="81fc4-115">Generate report of upgrade issues.</span></span>  
  
 <span data-ttu-id="81fc4-116">Per ulteriori informazioni sull'analisi guidata di preparazione aggiornamento, vedere [procedura: esecuzione dell'analisi guidata di preparazione aggiornamento](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="81fc4-116">For more information about the Upgrade Advisor Analysis Wizard, see [How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span></span>  
  
 <span data-ttu-id="81fc4-117">Per informazioni specifiche richieste per ogni passaggio, vedere Guida di [riferimento all'interfaccia utente di preparazione aggiornamento](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="81fc4-117">For specific information that is required for each step, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
## <a name="running-the-upgrade-advisor-report-viewer"></a><span data-ttu-id="81fc4-118">Esecuzione del Visualizzatore report di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="81fc4-118">Running the Upgrade Advisor Report Viewer</span></span>  
 <span data-ttu-id="81fc4-119">Utilizzare il Visualizzatore report di Preparazione aggiornamento per visualizzare i report generati dall'Analisi guidata di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="81fc4-119">You use the Upgrade Advisor Report Viewer to view reports generated by the Upgrade Advisor Analysis Wizard.</span></span> <span data-ttu-id="81fc4-120">Quando il report viene caricato, è possibile filtrare i componenti del report in base ai fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="81fc4-120">When the report is loaded, you can filter the components of the report by the following factors:</span></span>  
  
-   <span data-ttu-id="81fc4-121">Tutti i problemi</span><span class="sxs-lookup"><span data-stu-id="81fc4-121">All issues</span></span>  
  
-   <span data-ttu-id="81fc4-122">Tutti i problemi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="81fc4-122">All upgrade issues</span></span>  
  
-   <span data-ttu-id="81fc4-123">Problemi di pre-aggiornamento</span><span class="sxs-lookup"><span data-stu-id="81fc4-123">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="81fc4-124">Tutti i problemi di migrazione</span><span class="sxs-lookup"><span data-stu-id="81fc4-124">All migration issues</span></span>  
  
-   <span data-ttu-id="81fc4-125">Problemi risolti</span><span class="sxs-lookup"><span data-stu-id="81fc4-125">Resolved issues</span></span>  
  
-   <span data-ttu-id="81fc4-126">Problemi irrisolti</span><span class="sxs-lookup"><span data-stu-id="81fc4-126">Unresolved issues</span></span>  
  
 <span data-ttu-id="81fc4-127">Per le istruzioni dettagliate per l'utilizzo del visualizzatore di report, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="81fc4-127">For step-by-step instructions for using the report viewer, see the following topics:</span></span>  
  
-   [<span data-ttu-id="81fc4-128">Procedura: Visualizzare un report di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="81fc4-128">How to: View an Upgrade Advisor Report</span></span>](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md)  
  
-   [<span data-ttu-id="81fc4-129">Procedura: Filtrare i report</span><span class="sxs-lookup"><span data-stu-id="81fc4-129">How to: Filter Reports</span></span>](../../../2014/sql-server/install/how-to-filter-reports.md)  
  
-   [<span data-ttu-id="81fc4-130">Procedura: Esportare i report</span><span class="sxs-lookup"><span data-stu-id="81fc4-130">How to: Export Reports</span></span>](../../../2014/sql-server/install/how-to-export-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="81fc4-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81fc4-131">See Also</span></span>  
 <span data-ttu-id="81fc4-132">[Procedura: esecuzione dell'analisi guidata di preparazione aggiornamento](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-132">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="81fc4-133">[Guida di riferimento all'interfaccia utente di preparazione aggiornamento](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-133">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 <span data-ttu-id="81fc4-134">[Risoluzione dei problemi di aggiornamento](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-134">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="81fc4-135">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="81fc4-135">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
