---
title: Monitoraggio dei log degli errori | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server]
- database performance [SQL Server], errors
- Windows application logs [SQL Server]
- monitoring performance [SQL Server], errors
- server performance [SQL Server], errors
- comparing error and application log output
- errors [SQL Server], logs
- tuning databases [SQL Server], errors
- database monitoring [SQL Server], errors
- SQL Server error log
- logs [SQL Server], SQL Server error logs
- error logs [SQL Server]
- logs [SQL Server], Windows application logs
ms.assetid: e250336b-0695-44f6-a42f-23222f94e377
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a47891599dbe735bd437f5239c73bfd34c422ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628044"
---
# <a name="monitoring-the-error-logs"></a><span data-ttu-id="f427a-102">Monitoraggio dei log degli errori</span><span class="sxs-lookup"><span data-stu-id="f427a-102">Monitoring the Error Logs</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f427a-103">alcuni eventi di sistema e definiti dall'utente vengono registrati nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e nel registro applicazioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="f427a-103">logs certain system events and user-defined events to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span> <span data-ttu-id="f427a-104">Sia nel registro errori che nel registro applicazioni viene applicato automaticamente un timestamp a tutti gli eventi registrati.</span><span class="sxs-lookup"><span data-stu-id="f427a-104">Both logs automatically timestamp all recorded events.</span></span> <span data-ttu-id="f427a-105">Utilizzare le informazioni contenute nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la risoluzione di problemi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f427a-105">Use the information in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to troubleshoot problems related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f427a-106">Il registro applicazioni di Windows offre un quadro generale degli eventi generati nel sistema operativo Windows, nonché degli eventi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="f427a-106">The Windows application log provides an overall picture of events that occur on the Windows operating system, as well as events in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="f427a-107">Tramite il Visualizzatore eventi di Windows è possibile visualizzare il contenuto del registro applicazioni di Windows e filtrare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="f427a-107">Use the Windows Event Viewer to view the Windows application log and to filter the information.</span></span> <span data-ttu-id="f427a-108">È possibile, ad esempio, filtrare eventi informativi, di avviso, di errore, di controllo con esito positivo e di controllo con esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f427a-108">For example, you can filter events, such as information, warning, error, success audit, and failure audit.</span></span>  
  
## <a name="comparing-error-and-application-log-output"></a><span data-ttu-id="f427a-109">confronto tra output del log degli errori e output del registro applicazioni</span><span class="sxs-lookup"><span data-stu-id="f427a-109">Comparing Error and Application Log Output</span></span>  
 <span data-ttu-id="f427a-110">Per identificare la causa di eventuali problemi, è possibile utilizzare sia il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che il registro applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="f427a-110">You can use both the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the Windows application log to identify the cause of problems.</span></span> <span data-ttu-id="f427a-111">Ad esempio, durante il monitoraggio del log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] potrebbero venire visualizzati messaggi di errore privi di informazioni sulla causa dell'errore.</span><span class="sxs-lookup"><span data-stu-id="f427a-111">For example, while monitoring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, you may encounter error messages that do not contain cause information.</span></span> <span data-ttu-id="f427a-112">Confrontando la data e l'ora degli eventi riportate nel registro errori e la data e l'ora riportate nel registro applicazioni è possibile circoscrivere le possibili cause.</span><span class="sxs-lookup"><span data-stu-id="f427a-112">By comparing the dates and times for events between these logs, you can narrow the list of probable causes.</span></span> <span data-ttu-id="f427a-113">Nel Visualizzatore file di log di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] è possibile integrare in un unico elenco il log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e il registro applicazioni di Windows. Ciò consente di capire più facilmente gli eventi del server e gli eventi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correlati.</span><span class="sxs-lookup"><span data-stu-id="f427a-113">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Log File Viewer lets you integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, and the Windows logs into a single list, making it easy to understand related server events and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="f427a-114">Per ulteriori informazioni, vedere l'argomento "Visualizzatore file di log" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f427a-114">For more information, see the topic "Log File Viewer" in SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f427a-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f427a-115">In This Section</span></span>  
  
|<span data-ttu-id="f427a-116">Argomento</span><span class="sxs-lookup"><span data-stu-id="f427a-116">Topic</span></span>|<span data-ttu-id="f427a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f427a-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f427a-118">Visualizzazione del log degli errori di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f427a-118">Viewing the SQL Server Error Log</span></span>](../../../2014/tools/configuration-manager/viewing-the-sql-server-error-log.md)|<span data-ttu-id="f427a-119">Contiene informazioni sul log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e descrive come visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="f427a-119">Contains information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and how to view it.</span></span>|  
|[<span data-ttu-id="f427a-120">Visualizzazione del registro applicazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="f427a-120">Viewing the Windows Application Log</span></span>](viewing-the-windows-application-log.md)|<span data-ttu-id="f427a-121">Contiene informazioni sul registro applicazioni di Windows e descrive come visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="f427a-121">Contains information about the Windows application log and how to view it.</span></span>|  
  
  
