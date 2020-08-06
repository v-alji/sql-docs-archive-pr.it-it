---
title: rsServerConfigurationError - Errore di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsServerConfigurationError
ms.assetid: 0913afc2-34b4-4713-b570-cfd5718975ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02f8a18c42715d1f118920614eb425820130dacb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722468"
---
# <a name="rsserverconfigurationerror---reporting-services-error"></a><span data-ttu-id="df1c1-102">rsServerConfigurationError - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="df1c1-102">rsServerConfigurationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="df1c1-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="df1c1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df1c1-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="df1c1-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="df1c1-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="df1c1-105">Event ID</span></span>|<span data-ttu-id="df1c1-106">rsServerConfiguration</span><span class="sxs-lookup"><span data-stu-id="df1c1-106">rsServerConfiguration</span></span>|  
|<span data-ttu-id="df1c1-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="df1c1-107">Event Source</span></span>|<span data-ttu-id="df1c1-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="df1c1-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="df1c1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="df1c1-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="df1c1-110">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="df1c1-110">Message Text</span></span>|<span data-ttu-id="df1c1-111">Il server di report ha rilevato un errore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="df1c1-111">The report server has encountered a configuration error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df1c1-112">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="df1c1-112">Explanation</span></span>  
 <span data-ttu-id="df1c1-113">Questo errore è generico e si verifica quando le impostazioni di configurazione del server di report o di uno strumento di creazione dei report non sono valide.</span><span class="sxs-lookup"><span data-stu-id="df1c1-113">This is a general purpose error that occurs when either the report server or a report authoring tool has invalid configuration settings.</span></span> <span data-ttu-id="df1c1-114">All'errore è generalmente associato un secondo messaggio che indica la causa effettiva dell'errore stesso.</span><span class="sxs-lookup"><span data-stu-id="df1c1-114">The error is usually accompanied by a second message that states the actual cause of the error.</span></span>  
  
 <span data-ttu-id="df1c1-115">Nell'elenco seguente vengono riepilogate le possibili cause:</span><span class="sxs-lookup"><span data-stu-id="df1c1-115">The following list summarizes possible causes:</span></span>  
  
-   <span data-ttu-id="df1c1-116">Il file RSReportServer.config o RSReportDesigner.config non può essere trovato o letto.</span><span class="sxs-lookup"><span data-stu-id="df1c1-116">The RSReportServer.config or RSReportDesigner.config file cannot be found or read.</span></span>  
  
-   <span data-ttu-id="df1c1-117">Gli elementi XML nel file di configurazione mancano o non sono validi.</span><span class="sxs-lookup"><span data-stu-id="df1c1-117">XML elements in either configuration file are missing or invalid.</span></span>  
  
-   <span data-ttu-id="df1c1-118">I valori per uno o più elementi XML mancano o non sono validi.</span><span class="sxs-lookup"><span data-stu-id="df1c1-118">Values for one or more XML elements are missing or invalid.</span></span>  
  
-   <span data-ttu-id="df1c1-119">Le impostazioni del Registro di sistema non sono valide.</span><span class="sxs-lookup"><span data-stu-id="df1c1-119">Registry settings are invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df1c1-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="df1c1-120">User Action</span></span>  
 <span data-ttu-id="df1c1-121">Se questo errore inizia a verificarsi dopo che il file di configurazione è stato modificato manualmente, rimuovere le modifiche e immettere il valore precedente o ripristinare una versione precedente se è disponibile un backup.</span><span class="sxs-lookup"><span data-stu-id="df1c1-121">If this error began to occur after you manually edited a configuration file, remove your changes and enter the previous value, or restore a previous version if you have a backup.</span></span>  
  
 <span data-ttu-id="df1c1-122">Per rivedere informazioni aggiuntive sul messaggio di errore che accompagnano l' `rsServerConfiguration` errore, esaminare i file di log di traccia del server di report, disponibili in \Microsoft SQL Server\MSRS12. \<instancename > Services\LogFiles. \Reporting</span><span class="sxs-lookup"><span data-stu-id="df1c1-122">To review additional error message information that accompanies the `rsServerConfiguration` error, review the report server trace log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="df1c1-123">Per altre informazioni, vedere [File di log e origini di Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="df1c1-123">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="df1c1-124">Solo interno</span><span class="sxs-lookup"><span data-stu-id="df1c1-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df1c1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df1c1-125">See Also</span></span>  
 <span data-ttu-id="df1c1-126">[File di configurazione di Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="df1c1-126">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="df1c1-127">Modificare un file di configurazione di Reporting Services &#40;RSreportserver.config&#41;</span><span class="sxs-lookup"><span data-stu-id="df1c1-127">Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;</span></span>](../report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md)  
  
  
