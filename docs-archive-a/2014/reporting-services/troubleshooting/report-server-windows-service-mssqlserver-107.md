---
title: Servizio Windows ReportServer (MSSQLServer) 107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- MSSQLServer 107 error
ms.assetid: 52b5704b-27f9-400a-a821-d8fa0786afe4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8651f98b47b698fbe3cfb6a152b9220a84ed7256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627639"
---
# <a name="report-server-windows-service-mssqlserver-107"></a><span data-ttu-id="bded2-102">Servizio Windows ReportServer (MSSQLServer) 107</span><span class="sxs-lookup"><span data-stu-id="bded2-102">Report Server Windows Service (MSSQLServer) 107</span></span>
    
## <a name="details"></a><span data-ttu-id="bded2-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bded2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bded2-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="bded2-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="bded2-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="bded2-105">Event ID</span></span>|<span data-ttu-id="bded2-106">107</span><span class="sxs-lookup"><span data-stu-id="bded2-106">107</span></span>|  
|<span data-ttu-id="bded2-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="bded2-107">Event Source</span></span>|<span data-ttu-id="bded2-108">Servizio Windows ReportServer</span><span class="sxs-lookup"><span data-stu-id="bded2-108">Report Server Windows Service</span></span>|  
|<span data-ttu-id="bded2-109">Componente</span><span class="sxs-lookup"><span data-stu-id="bded2-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="bded2-110">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="bded2-110">Message Text</span></span>|<span data-ttu-id="bded2-111">Il servizio Windows ReportServer (MSSQLSERVER) non è in grado di connettersi al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bded2-111">Report Server Windows Service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bded2-112">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bded2-112">Explanation</span></span>  
 <span data-ttu-id="bded2-113">Il servizio del server di report di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è in grado di connettersi al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bded2-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service cannot connect to the report server database.</span></span> <span data-ttu-id="bded2-114">Questo errore si verifica durante un riavvio del servizio se non è possibile stabilire una connessione al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bded2-114">This error occurs during a service restart if a connection to the report server database cannot be established.</span></span> <span data-ttu-id="bded2-115">Di seguito vengono riportate le condizioni in presenza delle quali si verifica l'errore:</span><span class="sxs-lookup"><span data-stu-id="bded2-115">Conditions under which this error occurs include the following:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bded2-116">[!INCLUDE[ssDE](../../includes/ssde-md.md)] non è in esecuzione quando il servizio del server di report viene avviato.</span><span class="sxs-lookup"><span data-stu-id="bded2-116">[!INCLUDE[ssDE](../../includes/ssde-md.md)] service is not running when the Report Server service starts.</span></span>  
  
-   <span data-ttu-id="bded2-117">Non è possibile eseguire la connessione al servizio [!INCLUDE[ssDE](../../includes/ssde-md.md)] perché le connessioni remote o il protocollo TCP/IP non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="bded2-117">The connection to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service fails because remote connections or the TCP/IP protocol is not enabled.</span></span>  
  
-   <span data-ttu-id="bded2-118">Il database del server di report non è configurato in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="bded2-118">The report server database is not configured correctly.</span></span>  
  
-   <span data-ttu-id="bded2-119">L'account di servizio non è configurato correttamente o l'account non dispone più di autorizzazioni sul database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bded2-119">The service account is not configured correctly, or the account no longer has permissions on the report server database.</span></span> <span data-ttu-id="bded2-120">Questa situazione può verificarsi se non si utilizza lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] per configurare l'account o il database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bded2-120">This can occur if you do not use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set up the account or the report server database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bded2-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="bded2-121">User Action</span></span>  
 <span data-ttu-id="bded2-122">Avviare il servizio [!INCLUDE[ssDE](../../includes/ssde-md.md)] se non è in esecuzione e verificare che le connessioni remote siano abilitate per il protocollo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="bded2-122">Start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service if it is not running and check that remote connections are enabled for TCP/IP protocol.</span></span>  
  
 <span data-ttu-id="bded2-123">Utilizzare lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] per configurare il database del server di report e l'account di servizio.</span><span class="sxs-lookup"><span data-stu-id="bded2-123">Use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to configure the report server database and service account.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="bded2-124">Solo interno</span><span class="sxs-lookup"><span data-stu-id="bded2-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bded2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bded2-125">See Also</span></span>  
 <span data-ttu-id="bded2-126">[Configurare l'account del servizio del server di report &#40;Gestione configurazione SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="bded2-126">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="bded2-127">[Gestione configurazione Reporting Services &#40;modalità nativa&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="bded2-127">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 [<span data-ttu-id="bded2-128">Avviare e arrestare il servizio del server di report</span><span class="sxs-lookup"><span data-stu-id="bded2-128">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
