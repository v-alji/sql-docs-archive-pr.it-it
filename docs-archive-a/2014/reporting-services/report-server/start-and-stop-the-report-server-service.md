---
title: Avviare e arrestare il servizio del server di report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- stopping Report Server service
- Report Server Windows service, starting
- Report Server service, starting
- starting Report Server service
ms.assetid: 6ec69ac3-27b0-472d-91e1-733af9078ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b751fd1a31830ffdc96cb296fa39d08e396c8c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628334"
---
# <a name="start-and-stop-the-report-server-service"></a><span data-ttu-id="13f19-102">Avviare e arrestare il servizio del server di report</span><span class="sxs-lookup"><span data-stu-id="13f19-102">Start and Stop the Report Server Service</span></span>
  <span data-ttu-id="13f19-103">Un server di report viene implementato come un servizio Windows che contiene il servizio Web ReportServer, Gestione report e un'applicazione di elaborazione in background.</span><span class="sxs-lookup"><span data-stu-id="13f19-103">A report server is implemented as a Windows service that contains the Report Server Web service, Report Manager, and a background processing application.</span></span> <span data-ttu-id="13f19-104">Se si desidera utilizzare qualsiasi funzionalità del server di report, è necessario che il servizio sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="13f19-104">The service must be running if you want to use any report server functionality.</span></span> <span data-ttu-id="13f19-105">L'arresto del servizio determina l'interruzione di tutte le operazioni eseguite sul server di report.</span><span class="sxs-lookup"><span data-stu-id="13f19-105">Stopping the service stops all report server operations.</span></span>  
  
 <span data-ttu-id="13f19-106">Mentre il servizio è arrestato, le richieste di elaborazione di report e sottoscrizioni pianificate che sarebbero state eseguite in caso di attività del servizio vengono aggiunte alla coda.</span><span class="sxs-lookup"><span data-stu-id="13f19-106">While the service is stopped, requests for scheduled report and subscription processing that would have occurred had the service been running are added to the queue.</span></span> <span data-ttu-id="13f19-107">Questa situazione si verifica poiché i processi eseguiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent creano gli eventi.</span><span class="sxs-lookup"><span data-stu-id="13f19-107">This is because jobs that are run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent create the events.</span></span> <span data-ttu-id="13f19-108">Se si desidera evitare un backlog di operazioni mentre il servizio è disattivato, arrestare anche [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="13f19-108">If you want to avoid a backlog of operations while the service is off, consider stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent as well.</span></span>  
  
 <span data-ttu-id="13f19-109">Per avviare e arrestare il servizio del server di report, è possibile utilizzare diversi strumenti, ad esempio lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e lo strumento Servizi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="13f19-109">You can use a variety of tools to start or stop the Report Server service, including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, and the Services tool provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span></span>  
  
 <span data-ttu-id="13f19-110">Se, oltre ad avviare o arrestare il servizio, si modifica ad esempio l'account del servizio, è necessario utilizzare lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13f19-110">If you are doing more than starting or stopping the service, such as changing the service account, you must use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="13f19-111">L'utilizzo di altri strumenti per modificare l'account del servizio può causare l'interruzione dell'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13f19-111">Using other tools to change the service account can break your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="13f19-112">Per altre informazioni, vedere [Configurare l'account del servizio del server di report &#40;Gestione configurazione SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="13f19-112">For more information, see [Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="13f19-113">Non è possibile sospendere e riprendere l'esecuzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="13f19-113">You cannot pause and resume the service.</span></span> <span data-ttu-id="13f19-114">Non sono disponibili parametri di avvio.</span><span class="sxs-lookup"><span data-stu-id="13f19-114">There are no start parameters.</span></span> <span data-ttu-id="13f19-115">Sebbene non esistano dipendenze esplicite, se il server di report deve supportare sottoscrizioni o operazioni su report pianificate, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="13f19-115">Although there are no explicit dependencies, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running if you support any subscriptions or scheduled report operations on the report server.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-the-reporting-services-configuration-tool"></a><span data-ttu-id="13f19-116">Per avviare o arrestare il servizio utilizzando lo strumento di configurazione di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="13f19-116">To start or stop the service using the Reporting Services Configuration tool</span></span>  
  
1.  <span data-ttu-id="13f19-117">Avviare lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e connettersi al server di report.</span><span class="sxs-lookup"><span data-stu-id="13f19-117">Start [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and connect to the report server.</span></span>  
  
2.  <span data-ttu-id="13f19-118">Nella pagina Stato Server report fare clic su **Arresta** o **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="13f19-118">On the Report Server Status page, click **Stop** or **Start**.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-services-in-administrative-tools"></a><span data-ttu-id="13f19-119">Per avviare o arrestare il servizio utilizzando lo strumento Servizi in Strumenti di amministrazione</span><span class="sxs-lookup"><span data-stu-id="13f19-119">To start or stop the service using Services in Administrative Tools</span></span>  
  
-   <span data-ttu-id="13f19-120">In Strumenti di amministrazione aprire Servizi, fare clic con il pulsante destro del mouse su **SQL Server Reporting Services (MSSQLSERVER)**, quindi scegliere **Arresta** o **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="13f19-120">In Administrative Tools, open Services, right-click **SQL Server Reporting Services (MSSQLSERVER)**, and click **Stop** or **Restart**.</span></span>  
  
 <span data-ttu-id="13f19-121">Se si eseguono più istanze o se il server di report è in esecuzione come istanza denominata, verificare che il nome dell'istanza tra parentesi corrisponda all'istanza del server di report da arrestare o riavviare.</span><span class="sxs-lookup"><span data-stu-id="13f19-121">If you are running multiple instance or if the report server is running as a named instance, verify that the instance name in parentheses corresponds to the report server instance you want to stop or restart.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-sql-server-configuration-manager"></a><span data-ttu-id="13f19-122">Per arrestare e riavviare il servizio utilizzando Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13f19-122">To start or stop the service using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="13f19-123">Avviare Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13f19-123">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
2.  <span data-ttu-id="13f19-124">Selezionare Servizi di SQL Server, fare clic con il pulsante destro del mouse su **SQL Server Reporting Services**, quindi scegliere **Arresta** o **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="13f19-124">Select SQL Server Services, right-click **SQL Server Reporting Services**, and click **Stop** or **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f19-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13f19-125">See Also</span></span>  
 [<span data-ttu-id="13f19-126">Gestione configurazione Reporting Services &#40;modalità nativa&#41;</span><span class="sxs-lookup"><span data-stu-id="13f19-126">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
