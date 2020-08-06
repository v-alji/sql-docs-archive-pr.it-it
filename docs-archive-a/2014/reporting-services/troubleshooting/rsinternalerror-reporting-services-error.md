---
title: rsInternalError - Errore di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsInternalError
ms.assetid: 52613d52-fc78-4870-93f0-7d393ab9c335
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 85b88519df810f60c580ad2d6eb355dde236d081
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629165"
---
# <a name="rsinternalerror---reporting-services-error"></a><span data-ttu-id="b5982-102">rsInternalError - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b5982-102">rsInternalError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="b5982-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b5982-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5982-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b5982-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="b5982-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="b5982-105">Event ID</span></span>|<span data-ttu-id="b5982-106">rsInternalError</span><span class="sxs-lookup"><span data-stu-id="b5982-106">rsInternalError</span></span>|  
|<span data-ttu-id="b5982-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b5982-107">Event Source</span></span>|<span data-ttu-id="b5982-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="b5982-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="b5982-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b5982-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="b5982-110">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b5982-110">Message Text</span></span>|<span data-ttu-id="b5982-111">Errore interno nel server di report.</span><span class="sxs-lookup"><span data-stu-id="b5982-111">An internal error occurred on the report server.</span></span> <span data-ttu-id="b5982-112">Per altre informazioni, vedere il log degli errori.</span><span class="sxs-lookup"><span data-stu-id="b5982-112">See the error log for more details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5982-113">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b5982-113">Explanation</span></span>  
 <span data-ttu-id="b5982-114">Si tratta di un messaggio di errore generico, spesso seguito da un errore più descrittivo che include ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="b5982-114">This is a generic error message that is often followed by a more descriptive error that provides more detail.</span></span>  
  
 <span data-ttu-id="b5982-115">Gli errori interni non sono comuni.</span><span class="sxs-lookup"><span data-stu-id="b5982-115">Internal errors are uncommon.</span></span> <span data-ttu-id="b5982-116">Se viene visualizzato questo errore, nei log di traccia del server di report sono disponibili ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="b5982-116">If you get this error, more information is available in report server trace logs.</span></span> <span data-ttu-id="b5982-117">Se inoltre si esegue il servizio come amministratore locale nello stesso computer in cui si è verificato l'errore, è possibile visualizzare lo stack di chiamate per ottenere ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="b5982-117">In addition, if you are running as local administrator on the same computer on which the error occurs, you can view the call stack for more information.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5982-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b5982-118">User Action</span></span>  
 <span data-ttu-id="b5982-119">Per determinare la determinata ragione di questo messaggio, esaminare i file di log del server di report, disponibili in \Microsoft SQL Server\MSRS12. \<instancename > Services\LogFiles. \Reporting</span><span class="sxs-lookup"><span data-stu-id="b5982-119">To determine the specific cause for this message, review the report server log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="b5982-120">Per altre informazioni, vedere [File di log e origini di Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="b5982-120">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
 <span data-ttu-id="b5982-121">Per visualizzare lo stack di chiamate, fare clic con il pulsante destro del mouse nella pagina in cui si è verificato l'errore e scegliere **Visualizza origine**.</span><span class="sxs-lookup"><span data-stu-id="b5982-121">To view the call stack, right-click the page on which the error occurs and point to **View Source**.</span></span> <span data-ttu-id="b5982-122">Per visualizzare lo stack di chiamate, è necessario disporre delle autorizzazioni di amministratore nello stesso computer in cui si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="b5982-122">Viewing the call stack requires administrator permissions on the same computer on which the error occurs.</span></span>  
  
 <span data-ttu-id="b5982-123">Se non sono disponibili informazioni aggiuntive, è possibile riprovare a eseguire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="b5982-123">If there is no additional information available, you can try your request again.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="b5982-124">Solo interno</span><span class="sxs-lookup"><span data-stu-id="b5982-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5982-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5982-125">See Also</span></span>  
 [<span data-ttu-id="b5982-126">Avviare e arrestare il servizio del server di report</span><span class="sxs-lookup"><span data-stu-id="b5982-126">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
