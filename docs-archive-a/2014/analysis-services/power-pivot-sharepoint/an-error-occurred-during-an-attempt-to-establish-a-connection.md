---
title: "Errore durante il tentativo di stabilire una connessione all'origine dati esterna. Impossibile aggiornare le connessioni seguenti: dati PowerPivot | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1b951da1-f62d-43d2-b40b-270a4a9ab92c
author: minewiskan
ms.author: owend
ms.openlocfilehash: eb4329440b69d1bdfdbb96fbcc3926fa000d8877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715768"
---
# <a name="an-error-occurred-during-an-attempt-to-establish-a-connection-to-the-external-data-source-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="95217-103">Errore durante il tentativo di stabilire una connessione all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="95217-103">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="95217-104">Impossibile aggiornare le connessioni seguenti: Dati di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="95217-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="95217-105">Questo errore si verifica se si esegue una query sui dati PowerPivot in un server in cui non è installato PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95217-105">This error occurs if you query PowerPivot data on a server that does not have PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="95217-106">Si verifica anche se viene arrestato il servizio SQL Server Analysis Services (PowerPivot) o se si tenta di visualizzare dati PowerPivot di una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="95217-106">It also occurs if the SQL Server Analysis Services (PowerPivot) service is stopped, or if you are attempting to view PowerPivot data from an earlier version.</span></span>  
  
## <a name="details"></a><span data-ttu-id="95217-107">Dettagli</span><span class="sxs-lookup"><span data-stu-id="95217-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="95217-108">Si applica a</span><span class="sxs-lookup"><span data-stu-id="95217-108">Applies to</span></span>|<span data-ttu-id="95217-109">PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="95217-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="95217-110">Versione prodotto</span><span class="sxs-lookup"><span data-stu-id="95217-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="95217-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95217-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="95217-112">Causa</span><span class="sxs-lookup"><span data-stu-id="95217-112">Cause</span></span>|<span data-ttu-id="95217-113">Impossibile stabilire la connessione dati.</span><span class="sxs-lookup"><span data-stu-id="95217-113">The data connection failed.</span></span>|  
|<span data-ttu-id="95217-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="95217-114">Message Text</span></span>|<span data-ttu-id="95217-115">Errore durante il tentativo di stabilire una connessione all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="95217-115">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="95217-116">Impossibile aggiornare le connessioni seguenti: Dati di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="95217-116">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="95217-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="95217-117">Explanation</span></span>  
 <span data-ttu-id="95217-118">Excel Services restituisce questo errore quando si esegue una query sui dati PowerPivot in una cartella di lavoro di Excel pubblicata in SharePoint e l'ambiente SharePoint non include un server PowerPivot per SharePoint o se il servizio SQL Server Analysis Services (PowerPivot) è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="95217-118">Excel Services returns this error when you query PowerPivot data in an Excel workbook that is published to SharePoint, and the SharePoint environment does not have a PowerPivot for SharePoint server, or the SQL Server Analysis Services (PowerPivot) service is stopped.</span></span>  
  
 <span data-ttu-id="95217-119">L'errore si verifica quando si sezionano o filtrano dati PowerPivot quando il motore di query non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="95217-119">The error occurs when you slice or filter PowerPivot data when the query engine is not available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95217-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="95217-120">User Action</span></span>  
 <span data-ttu-id="95217-121">Installare PowerPivot per SharePoint o spostare la cartella di lavoro di PowerPivot in un ambiente SharePoint in cui sia installato PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95217-121">Install PowerPivot for SharePoint or move the PowerPivot workbook to a SharePoint environment that has PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="95217-122">Per ulteriori informazioni, vedere [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span><span class="sxs-lookup"><span data-stu-id="95217-122">For more information, see [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span></span>  
  
 <span data-ttu-id="95217-123">Se il software è installato, verificare che l'istanza di SQL Server Analysis Services (PowerPivot) sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="95217-123">If the software is installed, verify that the SQL Server Analysis Services (PowerPivot) instance is running.</span></span> <span data-ttu-id="95217-124">Selezionare **Gestisci servizi nel server** in Amministrazione centrale.</span><span class="sxs-lookup"><span data-stu-id="95217-124">Check **Manage services on server** in Central Administration.</span></span> <span data-ttu-id="95217-125">Selezionare inoltre l'applicazione console Servizi in Strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="95217-125">Also check the Services console application in Administrative Tools.</span></span>  
  
 <span data-ttu-id="95217-126">Per le cartelle di lavoro di PowerPivot create nella versione SQL Server 2008 R2 di PowerPivot per Excel è necessario installare la versione SQL Server 2008 R2 del provider OLE DB per Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="95217-126">For PowerPivot workbooks that were created in a SQL Server 2008 R2 version of PowerPivot for Excel, you must install the SQL Server 2008 R2 version of the Analysis Services OLE DB provider.</span></span> <span data-ttu-id="95217-127">Si verificherà questo errore se è stato installato il provider, ma non è stato registrato il file Microsoft.AnalysisServices.ChannelTransport.dll.</span><span class="sxs-lookup"><span data-stu-id="95217-127">This error will occur if you installed the provider, but did not register the Microsoft.AnalysisServices.ChannelTransport.dll file.</span></span> <span data-ttu-id="95217-128">Per altre informazioni sulla registrazione dei file, vedere [Installazione del provider OLE DB di Analysis Services nei server di SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="95217-128">For more information about file registration, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95217-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95217-129">See Also</span></span>  
 [<span data-ttu-id="95217-130">Per la connessione dati viene utilizzata l'autenticazione di Windows e non è stato possibile delegare le credenziali utente. Impossibile aggiornare le connessioni seguenti: dati PowerPivot</span><span class="sxs-lookup"><span data-stu-id="95217-130">The data connection uses Windows Authentication and user credentials could not be delegated. The following connections failed to refresh: PowerPivot Data</span></span>](the-data-connection-user-could-not-be-delegated.md)  
  
  
