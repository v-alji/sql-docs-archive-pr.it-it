---
title: Stato di preparazione aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], analysis progress status
- analyzing system [Upgrade Advisor], progress information
- SQL Server Upgrade Advisor, analysis progress status
- monitoring analysis progress
- progress information [Upgrade Advisor]
- status information [Upgrade Advisor]
ms.assetid: a9e3d1c8-d492-4beb-93c7-f1bc40d4a910
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b504b8f1c8392ad2cf55837dc65bbb2f019d6f48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628117"
---
# <a name="upgrade-advisor-progress"></a><span data-ttu-id="92e00-102">Stato Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="92e00-102">Upgrade Advisor Progress</span></span>
  <span data-ttu-id="92e00-103">L'analisi di Preparazione aggiornamento inizia con un analizzatore dedicato che esegue un'analisi di ogni componente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] selezionato.</span><span class="sxs-lookup"><span data-stu-id="92e00-103">Upgrade Advisor analysis starts with a dedicated analyzer that performs an analysis of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that you selected.</span></span> <span data-ttu-id="92e00-104">Quando si analizzano i componenti, lo stato di avanzamento viene segnalato nella finestra di dialogo **stato** .</span><span class="sxs-lookup"><span data-stu-id="92e00-104">As components are analyzed, progress is reported in the **Progress** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="92e00-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="92e00-105">Options</span></span>  
 <span data-ttu-id="92e00-106">**Azione**</span><span class="sxs-lookup"><span data-stu-id="92e00-106">**Action**</span></span>  
 <span data-ttu-id="92e00-107">Specifica il componente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] selezionato per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="92e00-107">Specifies the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that is selected for analysis.</span></span>  
  
 <span data-ttu-id="92e00-108">**Status**</span><span class="sxs-lookup"><span data-stu-id="92e00-108">**Status**</span></span>  
 <span data-ttu-id="92e00-109">Visualizza il valore relativo allo stato restituito dall'interfaccia di avanzamento dei componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92e00-109">Displays the status value returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component progress interface.</span></span>  
  
 <span data-ttu-id="92e00-110">**Message**</span><span class="sxs-lookup"><span data-stu-id="92e00-110">**Message**</span></span>  
 <span data-ttu-id="92e00-111">Visualizza i messaggi di errore oppure quelli relativi a esito positivo o negativo restituiti dal singolo analizzatore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92e00-111">Displays error, failure, or success messages returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] individual analyzer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92e00-112">Se l'analisi risulta troppo lenta, è possibile arrestarla, chiudere l'Analisi guidata di Preparazione aggiornamento e quindi eseguire nuovamente la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="92e00-112">If the analysis is taking too long, you can stop the analysis, exit the Upgrade Advisor Analysis Wizard, and then rerun the wizard.</span></span> <span data-ttu-id="92e00-113">Per ridurre i tempi di analisi, selezionare un numero minore di componenti da analizzare.</span><span class="sxs-lookup"><span data-stu-id="92e00-113">To reduce analysis time, select fewer components to scan.</span></span>  
  
 <span data-ttu-id="92e00-114">Al termine dell'analisi, il report viene scritto in un file.</span><span class="sxs-lookup"><span data-stu-id="92e00-114">When analysis is complete, the report is written to a file.</span></span> <span data-ttu-id="92e00-115">È possibile visualizzare il report facendo clic su **Avvia report** per avviare il Visualizzatore di report da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="92e00-115">You can view the report by clicking **Launch Report** to launch the report viewer from this page.</span></span> <span data-ttu-id="92e00-116">Se si desidera visualizzare il report in un secondo momento, è possibile aprire il **Visualizzatore report di preparazione aggiornamento** dalla pagina iniziale di preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="92e00-116">If you want to view the report later, you can open the **Upgrade Advisor Report Viewer** from the Upgrade Advisor start page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92e00-117">I report precedenti vengono salvati ogni volta che si analizza un server.</span><span class="sxs-lookup"><span data-stu-id="92e00-117">Previous reports are saved every time you analyze a server.</span></span> <span data-ttu-id="92e00-118">I report vengono salvati utilizzando il valore timestamp come nome del file.</span><span class="sxs-lookup"><span data-stu-id="92e00-118">The reports are saved using the timestamp for the file name.</span></span> <span data-ttu-id="92e00-119">Nel visualizzatore di report vengono visualizzati gli ultimi cinque report salvati.</span><span class="sxs-lookup"><span data-stu-id="92e00-119">The report viewer displays the latest five saved reports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e00-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92e00-120">See Also</span></span>  
 <span data-ttu-id="92e00-121">[Procedura: avvio di preparazione aggiornamento](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="92e00-121">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="92e00-122">[Procedura: esecuzione dell'analisi guidata di preparazione aggiornamento](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="92e00-122">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="92e00-123">[Componenti SQL Server](../../../2014/sql-server/install/sql-server-components.md) </span><span class="sxs-lookup"><span data-stu-id="92e00-123">[SQL Server Components](../../../2014/sql-server/install/sql-server-components.md) </span></span>  
 <span data-ttu-id="92e00-124">[Guida di riferimento all'interfaccia utente di preparazione aggiornamento](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="92e00-124">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 [<span data-ttu-id="92e00-125">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="92e00-125">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
