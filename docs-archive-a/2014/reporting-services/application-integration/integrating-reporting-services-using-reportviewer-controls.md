---
title: Integrazione di Reporting Services tramite i controlli ReportViewer | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- ReportViewer controls
- integrating reports [Reporting Services]
ms.assetid: 3ba47fb4-73a9-4059-89fd-329adebe94a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 18e28dbf1557bf36106b454738d0c0bfc037f2a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623920"
---
# <a name="integrating-reporting-services-using-the-reportviewer-controls"></a><span data-ttu-id="ed875-102">Integrazione di Reporting Services tramite i controlli ReportViewer</span><span class="sxs-lookup"><span data-stu-id="ed875-102">Integrating Reporting Services Using the ReportViewer Controls</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="ed875-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)]in sono disponibili due controlli ReportViewer per l'integrazione delle funzionalità di visualizzazione dei report nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ed875-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] provides two ReportViewer controls for integrating report viewing functionality into your applications.</span></span> <span data-ttu-id="ed875-104">È disponibile una versione per le applicazioni basate su Windows Form e una per le applicazioni Web Form.</span><span class="sxs-lookup"><span data-stu-id="ed875-104">There is a version for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="ed875-105">Ogni controllo offre funzionalità simili, ma ognuno è progettato per un ambiente specifico.</span><span class="sxs-lookup"><span data-stu-id="ed875-105">Each control provides similar functionality but each is designed to target their individual environments.</span></span> <span data-ttu-id="ed875-106">Entrambi i controlli consentono di elaborare i report distribuiti in un server di report (modalità di elaborazione remota) o copiati in un computer in cui [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] non è stato installato (modalità di elaborazione locale).</span><span class="sxs-lookup"><span data-stu-id="ed875-106">Both controls can process reports that have been deployed to a report server (remote processing mode) or have been copied to a computer where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] has not been installed (local processing mode).</span></span>  
  
 <span data-ttu-id="ed875-107">Il controllo ReportViewer non include il supporto integrato per l'adattamento dinamico ai diversi dispositivi con risoluzioni dello schermo diverse.</span><span class="sxs-lookup"><span data-stu-id="ed875-107">The ReportViewer control does not include built-in support for dynamically adapting to different devices with different screen resolutions.</span></span>  
  
## <a name="remote-processing-mode"></a><span data-ttu-id="ed875-108">Modalità di elaborazione remota</span><span class="sxs-lookup"><span data-stu-id="ed875-108">Remote Processing Mode</span></span>  
 <span data-ttu-id="ed875-109">La modalità di elaborazione remota è il metodo migliore per la visualizzazione dei report distribuiti in un server di report.</span><span class="sxs-lookup"><span data-stu-id="ed875-109">Remote processing mode is the preferred method for viewing reports that have been deployed to a report server.</span></span> <span data-ttu-id="ed875-110">La modalità di elaborazione remota offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed875-110">Remote processing mode provides the following advantages:</span></span>  
  
-   <span data-ttu-id="ed875-111">L'elaborazione remota fornisce una soluzione ottimizzata per l'esecuzione di report, in quanto il rendering e l'elaborazione dei report vengono eseguiti dal server di report.</span><span class="sxs-lookup"><span data-stu-id="ed875-111">Remote processing provides an optimized solution for running reports because the report is processed by the report server.</span></span>  
  
-   <span data-ttu-id="ed875-112">Poiché l'elaborazione viene gestita dal server di report, una richiesta del report può essere elaborata da più server di report in una distribuzione con scalabilità orizzontale o da un server con più processori in uno scenario con scalabilità verticale.</span><span class="sxs-lookup"><span data-stu-id="ed875-112">Because all processing is handled by the report server, a report request can be processed by multiple report servers in a scale-out deployment or a server that has multiple processors in a scale-up scenario.</span></span>  
  
 <span data-ttu-id="ed875-113">Per i report eseguiti in modalità remota possono inoltre venire usate le funzionalità complete del server di report, incluse tutte le estensioni dati e per il rendering.</span><span class="sxs-lookup"><span data-stu-id="ed875-113">In addition, reports run in remote mode can utilize the full functionality of the report server including all rendering and data extensions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed875-114">L'elenco di estensioni disponibili per il controllo ReportViewer quando l'esecuzione avviene in modalità di elaborazione remota dipende dall'edizione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installata nel server di report.</span><span class="sxs-lookup"><span data-stu-id="ed875-114">The list of extensions available to the ReportViewer control when it is running in remote processing mode depends on the edition of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is installed on the report server.</span></span>  
  
## <a name="local-processing-mode"></a><span data-ttu-id="ed875-115">Modalità di elaborazione locale</span><span class="sxs-lookup"><span data-stu-id="ed875-115">Local Processing Mode</span></span>  
 <span data-ttu-id="ed875-116">La modalità di elaborazione locale offre un metodo alternativo per la visualizzazione e il rendering dei report quando [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] non è installato.</span><span class="sxs-lookup"><span data-stu-id="ed875-116">Local processing mode provides an alternative method for viewing and rendering reports when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is not installed.</span></span> <span data-ttu-id="ed875-117">A differenza dell'elaborazione remota, nel controllo è disponibile solo un subset delle funzionalità fornite dal server di report.</span><span class="sxs-lookup"><span data-stu-id="ed875-117">Unlike remote processing only a subset of the functionality provided by the report server is available in the control.</span></span> <span data-ttu-id="ed875-118">Nella modalità locale l'elaborazione dei dati non viene gestita dal controllo ma implementata dall'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="ed875-118">In local processing mode, data processing is not handled by the control but rather implemented by the hosting application.</span></span> <span data-ttu-id="ed875-119">L'elaborazione dei report viene tuttavia gestita dal controllo.</span><span class="sxs-lookup"><span data-stu-id="ed875-119">However report processing is handled by the control itself.</span></span> <span data-ttu-id="ed875-120">Nella modalità di elaborazione locale sono disponibili solo le estensioni per il rendering PDF, Excel, Word e Image.</span><span class="sxs-lookup"><span data-stu-id="ed875-120">In local processing mode, only the PDF, Excel, Word, and Image rendering extensions are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed875-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed875-121">See Also</span></span>  
 <span data-ttu-id="ed875-122">[Integrazione di Reporting Services in applicazioni](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="ed875-122">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="ed875-123">Creazione di report SSRS con Visual Studio (Blog)</span><span class="sxs-lookup"><span data-stu-id="ed875-123">Create SSRS Reports Using Visual Studio (Blog)</span></span>](https://jwcooney.com/2015/01/07/ssrs-basics-set-up-visual-studio-to-write-a-new-ssrs-report/)  
  
  
