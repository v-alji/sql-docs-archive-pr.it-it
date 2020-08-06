---
title: Rinominare un computer del server di report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- renaming report servers
ms.assetid: 82fc4ba2-291a-4939-a025-271b8d687c54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe8f699c17f9e5f1e11406ac6e5c161488767ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637643"
---
# <a name="rename-a-report-server-computer"></a><span data-ttu-id="8e514-102">Rinominare un computer del server di report</span><span class="sxs-lookup"><span data-stu-id="8e514-102">Rename a Report Server Computer</span></span>
  <span data-ttu-id="8e514-103">La ridenominazione di un computer provoca una corrispondente modifica del nome del server Web e dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se presente sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="8e514-103">Renaming a computer causes a corresponding name change for the Web server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (if it is on the same computer).</span></span> <span data-ttu-id="8e514-104">In alcuni casi, dopo una modifica del nome del computer potrebbe non essere possibile accedere a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e514-104">In some cases, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] may not be accessible after a computer name change.</span></span> <span data-ttu-id="8e514-105">Utilizzare la procedura descritta in questo argomento per riconfigurare un server di report dopo la modifica del nome del computer.</span><span class="sxs-lookup"><span data-stu-id="8e514-105">Use the steps provided in this topic to reconfigure a report server after a computer name change.</span></span>  
  
## <a name="renaming-a-sql-server-database-engine"></a><span data-ttu-id="8e514-106">Ridenominazione di un Motore di database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e514-106">Renaming a SQL Server Database Engine</span></span>  
 <span data-ttu-id="8e514-107">Se si rinomina l'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] che esegue il database del server di report, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e514-107">If you rename the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance that runs the report server database, do the following:</span></span>  
  
1.  <span data-ttu-id="8e514-108">Avviare lo strumento di configurazione Reporting Services e connettersi al server di report che utilizza il database del server di report sul server rinominato.</span><span class="sxs-lookup"><span data-stu-id="8e514-108">Start the Reporting Services Configuration tool and connect to the report server that uses the report server database on the renamed server.</span></span>  
  
2.  <span data-ttu-id="8e514-109">Aprire la pagina Impostazione database.</span><span class="sxs-lookup"><span data-stu-id="8e514-109">Open the Database Setup page.</span></span>  
  
3.  <span data-ttu-id="8e514-110">In **Nome server**digitare o selezionare il nome del server di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="8e514-110">In **Server Name**, type or select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="8e514-111">Fare clic su **Apply**.</span><span class="sxs-lookup"><span data-stu-id="8e514-111">Click **Apply**.</span></span>  
  
 <span data-ttu-id="8e514-112">Se il server di report utilizza un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] locale, è possibile usare *(locale)* o *(locale)\nomeistanza* per specificare il server.</span><span class="sxs-lookup"><span data-stu-id="8e514-112">If the report server is using a local [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, you can use *(local)* or *(local)\instancename* to specify the server.</span></span> <span data-ttu-id="8e514-113">Se si usa *(locale)* per fare riferimento al server, è possibile rinominare il server e le connessioni continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="8e514-113">If you use *(local)* to refer to the server, you can rename the server and the connections will continue to work.</span></span> <span data-ttu-id="8e514-114">Se si utilizza un server remoto, o se [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è configurato con il nome del server, è necessario aggiornare le informazioni di connessione al database ogni volta che si modifica il nome server.</span><span class="sxs-lookup"><span data-stu-id="8e514-114">If you are using a remote server, or if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is configured using the server name, you must update the database connection information whenever the server name is changed.</span></span>  
  
## <a name="renaming-a-report-server-computer"></a><span data-ttu-id="8e514-115">Ridenominazione di un computer server di report</span><span class="sxs-lookup"><span data-stu-id="8e514-115">Renaming a Report Server Computer</span></span>  
 <span data-ttu-id="8e514-116">Se si rinomina un computer in cui viene eseguito un server di report, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e514-116">If you rename a computer that runs a report server, do the following:</span></span>  
  
1.  <span data-ttu-id="8e514-117">Aprire **RSReportServer.config** in un editor di testo e modificare l' `UrlRoot` impostazione in modo da riflettere il nuovo nome del server.</span><span class="sxs-lookup"><span data-stu-id="8e514-117">Open **RSReportServer.config** in a text editor and modify the `UrlRoot` setting to reflect the new server name.</span></span> <span data-ttu-id="8e514-118">L'impostazione `UrlRoot` viene utilizzata nelle estensioni per il recapito per comporre l'URL utilizzato per accedere agli elementi archiviati sul server di report.</span><span class="sxs-lookup"><span data-stu-id="8e514-118">The `UrlRoot` setting is used by delivery extensions to compose the URL used to access items stored on the report server.</span></span> <span data-ttu-id="8e514-119">Per modificare l'indirizzo URL del server di report è necessario aggiornare l'impostazione `UrlRoot` in modo che le sottoscrizioni continuino a recapitare i report come previsto.</span><span class="sxs-lookup"><span data-stu-id="8e514-119">Changing the report server URL address requires that you update the `UrlRoot` setting so that subscriptions continue to deliver reports as expected.</span></span>  
  
2.  <span data-ttu-id="8e514-120">Nello stesso file, se impostato, modificare l'impostazione `ReportServerUrl` per riflettere il nuovo nome del server.</span><span class="sxs-lookup"><span data-stu-id="8e514-120">In the same file, if it is set, modify the `ReportServerUrl` setting to reflect the new server name.</span></span> <span data-ttu-id="8e514-121">Si noti che questa impostazione non viene utilizzata in ogni installazione.</span><span class="sxs-lookup"><span data-stu-id="8e514-121">Note that this setting is not used in every installation.</span></span> <span data-ttu-id="8e514-122">Se è vuota, non eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="8e514-122">If it is empty, do nothing.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e514-123">Se si utilizza Windows Internet Naming Service (WINS) sulla rete aziendale, il server di report e Gestione report potrebbero continuare a essere disponibili con il nome precedente per un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8e514-123">If you are using Windows Internet Naming Service (WINS) on your corporate network, the report server and Report Manager may continue to be available under the previous name for a period of time.</span></span> <span data-ttu-id="8e514-124">WINS esegue il mapping di un indirizzo IP a ogni computer incluso nel servizio.</span><span class="sxs-lookup"><span data-stu-id="8e514-124">WINS maps an IP address to each computer it services.</span></span> <span data-ttu-id="8e514-125">Dopo che WINS ha aggiornato l'indirizzo IP per il computer rinominato, il precedente nome del computer non potrà più essere utilizzato per accedere a un server di report o a Gestione report.</span><span class="sxs-lookup"><span data-stu-id="8e514-125">After WINS refreshes the IP address for the renamed computer, the old computer name can no longer be used to access a report server or Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e514-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e514-126">See Also</span></span>  
 <span data-ttu-id="8e514-127">[File di configurazione RSReportServer](rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="8e514-127">[RSReportServer Configuration File](rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="8e514-128">[Gestione configurazione Reporting Services &#40;modalità nativa&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="8e514-128">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="8e514-129">[Server di report di Reporting Services &#40;modalità nativa&#41;](reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="8e514-129">[Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="8e514-130">[Avviare e arrestare il servizio del server di report](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="8e514-130">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 [<span data-ttu-id="8e514-131">Utilità rsconfig &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e514-131">rsconfig Utility &#40;SSRS&#41;</span></span>](../tools/rsconfig-utility-ssrs.md)  
  
  
