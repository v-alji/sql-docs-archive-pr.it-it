---
title: Proprietà server (pagina Registrazione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.logging.f1
ms.assetid: b338deab-4868-4951-9f22-0605add2fc95
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a04c27fd790a1ad5c4ba453b43af5983a6440e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629718"
---
# <a name="server-properties-logging-page"></a><span data-ttu-id="8e4a6-102">Proprietà  server (pagina Registrazione)</span><span class="sxs-lookup"><span data-stu-id="8e4a6-102">Server Properties (Logging Page)</span></span>
  <span data-ttu-id="8e4a6-103">Utilizzare questa pagina per impostare i limiti relativi ai dati sull'esecuzione dei report raccolti dal server di report.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-103">Use this page to set limits on the report execution data that is collected by a report server.</span></span> <span data-ttu-id="8e4a6-104">I dati di esecuzione vengono archiviati internamente nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-104">Execution data is stored internally in the report server database.</span></span> <span data-ttu-id="8e4a6-105">È possibile tenere traccia dell'attività di un server di report eseguito in modalità nativa o in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-105">You can track report activity for report server that runs in native mode or SharePoint integrated mode.</span></span> <span data-ttu-id="8e4a6-106">Se il server di report fa parte di una distribuzione con scalabilità orizzontale, nel log di esecuzione del report viene conservato un record di tutte le attività del report per l'intera distribuzione in un unico file di log.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-106">If the report server is part of a scale-out deployment, the report execution log maintains a record of all report activity for the entire deployment in a single log file.</span></span>  
  
 <span data-ttu-id="8e4a6-107">Per aprire questa pagina, avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , connettersi a un server di report, fare clic con il pulsante destro del mouse sul nome del server di report e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="8e4a6-108">Fare clic su **Registrazione** per aprire la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-108">Click **Logging** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e4a6-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8e4a6-109">Options</span></span>  
 <span data-ttu-id="8e4a6-110">**Attiva la registrazione per l'esecuzione di report**</span><span class="sxs-lookup"><span data-stu-id="8e4a6-110">**Enable report execution logging**</span></span>  
 <span data-ttu-id="8e4a6-111">Fare clic per creare e archiviare le informazioni sull'attività del report nel server.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-111">Click to create and store information about report activity on the server.</span></span> <span data-ttu-id="8e4a6-112">Se questa opzione è attivata, tramite il server di report verranno registrati i report utilizzati, la frequenza di elaborazione dei report, il tipo di operazione del report eseguita, il formato di output e l'utente che ha eseguito il report.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-112">If this option is enabled, the report server will track which reports are used, the frequency of report processing, the type of report operation that was performed, the output format, and who ran the report.</span></span> <span data-ttu-id="8e4a6-113">Per ulteriori informazioni sui punti dati aggiuntivi acquisiti nel log, vedere [il log di esecuzione del server di report e la visualizzazione ExecutionLog3](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="8e4a6-113">For more information about additional data points that are captured in the log, see [Report Server Execution Log and the ExecutionLog3 View](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
 <span data-ttu-id="8e4a6-114">**Rimuovi le voci del log dopo il numero di giorni seguente**</span><span class="sxs-lookup"><span data-stu-id="8e4a6-114">**Remove log entries older than this number of days**</span></span>  
 <span data-ttu-id="8e4a6-115">Consente di specificare il numero di giorni trascorsi i quali le voci di log verranno rimosse dal log di esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-115">Specify the number of days after which log entries will be trimmed from the report execution log.</span></span> <span data-ttu-id="8e4a6-116">Il valore predefinito è 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="8e4a6-116">The default value is 60 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e4a6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e4a6-117">See Also</span></span>  
 <span data-ttu-id="8e4a6-118">[Impostazione delle proprietà del server di report &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8e4a6-118">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="8e4a6-119">[Connettersi a un server di report in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8e4a6-119">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="8e4a6-120">[File di log e origini di Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="8e4a6-120">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="8e4a6-121">[Guida sensibile al contesto del server di report Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="8e4a6-121">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="8e4a6-122">Log di esecuzione del server di report e la vista ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="8e4a6-122">Report Server Execution Log and the ExecutionLog3 View</span></span>](../report-server/report-server-executionlog-and-the-executionlog3-view.md)  
  
  
