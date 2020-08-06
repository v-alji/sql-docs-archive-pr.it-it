---
title: Visualizzatore file di log | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer
ms.assetid: a4ea7fc8-1cb2-4c98-bc86-8991c5e748b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5139a32838070b817fce3bccf22b9fe08b5012e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627243"
---
# <a name="log-file-viewer"></a><span data-ttu-id="35a11-102">Visualizzatore file di log</span><span class="sxs-lookup"><span data-stu-id="35a11-102">Log File Viewer</span></span>
  <span data-ttu-id="35a11-103">È possibile utilizzare il Visualizzatore file di log in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per accedere alle informazioni relative a errori ed eventi acquisite nei file di log.</span><span class="sxs-lookup"><span data-stu-id="35a11-103">Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is used to access information about errors and events that are captured in log files.</span></span>  
  
## <a name="benefits-of-using-log-file-viewer"></a><span data-ttu-id="35a11-104">Vantaggi dell'utilizzo del Visualizzatore file di log</span><span class="sxs-lookup"><span data-stu-id="35a11-104">Benefits of using Log File Viewer</span></span>  
 <span data-ttu-id="35a11-105">È possibile visualizzare i file di log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un'istanza locale o remota di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando l'istanza di destinazione è offline o non può essere avviata.</span><span class="sxs-lookup"><span data-stu-id="35a11-105">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span> <span data-ttu-id="35a11-106">È possibile accedere ai file di log offline tramite lo strumento Server registrati o a livello di codice tramite query WMI e WQL (WMI Query Language).</span><span class="sxs-lookup"><span data-stu-id="35a11-106">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span> <span data-ttu-id="35a11-107">Per altre informazioni, vedere [Visualizzare file di log offline](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="35a11-107">For more information, see [View Offline Log Files](view-offline-log-files.md).</span></span> <span data-ttu-id="35a11-108">Di seguito vengono indicati i tipi di file di log a cui è possibile accedere utilizzando il Visualizzatore file di log:</span><span class="sxs-lookup"><span data-stu-id="35a11-108">Following are the types of log files you can access using Log File Viewer:</span></span>  
  
-   <span data-ttu-id="35a11-109">Raccolta controlli</span><span class="sxs-lookup"><span data-stu-id="35a11-109">Audit Collection</span></span>  
  
-   <span data-ttu-id="35a11-110">Raccolta di dati</span><span class="sxs-lookup"><span data-stu-id="35a11-110">Data Collection</span></span>  
  
-   <span data-ttu-id="35a11-111">Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="35a11-111">Database Mail</span></span>  
  
-   <span data-ttu-id="35a11-112">Cronologia processi</span><span class="sxs-lookup"><span data-stu-id="35a11-112">Job History</span></span>  
  
-   <span data-ttu-id="35a11-113">Piani di manutenzione</span><span class="sxs-lookup"><span data-stu-id="35a11-113">Maintenance Plans</span></span>  
  
-   <span data-ttu-id="35a11-114">Piani di manutenzione remoti</span><span class="sxs-lookup"><span data-stu-id="35a11-114">Remote Maintenance Plans</span></span>  
  
-   <span data-ttu-id="35a11-115">SQL Server</span><span class="sxs-lookup"><span data-stu-id="35a11-115">SQL Server</span></span>  
  
-   <span data-ttu-id="35a11-116">SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="35a11-116">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="35a11-117">Windows NT (eventi di Windows a cui è possibile accedere dal Visualizzatore eventi di Windows)</span><span class="sxs-lookup"><span data-stu-id="35a11-117">Windows NT (These are Windows events that can also be accessed from Event Viewer.)</span></span>  
  
## <a name="log-file-viewer-tasks"></a><span data-ttu-id="35a11-118">Attività del Visualizzatore file di log</span><span class="sxs-lookup"><span data-stu-id="35a11-118">Log File Viewer Tasks</span></span>  
  
|<span data-ttu-id="35a11-119">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="35a11-119">Task Description</span></span>|<span data-ttu-id="35a11-120">Argomento</span><span class="sxs-lookup"><span data-stu-id="35a11-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="35a11-121">Viene descritto come aprire il Visualizzatore file di log, a seconda delle informazioni da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="35a11-121">Describes how to open Log File Viewer depending on the information that you want to view.</span></span>|[<span data-ttu-id="35a11-122">Aprire il visualizzatore file di log</span><span class="sxs-lookup"><span data-stu-id="35a11-122">Open Log File Viewer</span></span>](open-log-file-viewer.md)|  
|<span data-ttu-id="35a11-123">Viene descritto come visualizzare file di log offline tramite server registrati e come verificare autorizzazioni WMI.</span><span class="sxs-lookup"><span data-stu-id="35a11-123">Describes how to view offline log files through registered servers and how to verify WMI permissions.</span></span>|[<span data-ttu-id="35a11-124">Visualizzare file di log offline</span><span class="sxs-lookup"><span data-stu-id="35a11-124">View Offline Log Files</span></span>](view-offline-log-files.md)|  
|<span data-ttu-id="35a11-125">Viene fornita la Guida sensibile al contesto del Visualizzatore file di log.</span><span class="sxs-lookup"><span data-stu-id="35a11-125">Provides Log File Viewer F1 Help.</span></span>|[<span data-ttu-id="35a11-126">Guida sensibile al contesto del Visualizzatore file di log</span><span class="sxs-lookup"><span data-stu-id="35a11-126">Log File Viewer F1 Help</span></span>](log-file-viewer-f1-help.md)|  
  
## <a name="see-also"></a><span data-ttu-id="35a11-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35a11-127">See Also</span></span>  
 <span data-ttu-id="35a11-128">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="35a11-128">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="35a11-129">Log degli errori di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="35a11-129">SQL Server Agent Error Log</span></span>](../../ssms/agent/sql-server-agent-error-log.md)  
  
  
