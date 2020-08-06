---
title: "Il percorso della connessione dati nella cartella di lavoro fa riferimento a un file nell'unità locale o è un URI non valido. Impossibile aggiornare le connessioni seguenti: dati PowerPivot | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bd22e41a-0931-4d32-888a-633a3046fc5e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3349af08290e2ff659db1441d849b2afef51e95b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628015"
---
# <a name="the-data-connection-path-in-the-workbook-points-to-a-file-on-the-local-drive-or-is-an-invalid-uri-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="da514-103">Il percorso della connessione dati nella cartella di lavoro fa riferimento a un file nell'unità locale o è un URI non valido.</span><span class="sxs-lookup"><span data-stu-id="da514-103">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="da514-104">Impossibile aggiornare le connessioni seguenti: Dati di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="da514-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="da514-105">Per cartelle di lavoro di Excel contenenti dati PowerPivot, in Excel Services viene restituito questo errore se non è possibile connettersi a origini dati incorporate.</span><span class="sxs-lookup"><span data-stu-id="da514-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to embedded data sources.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da514-106">Dettagli</span><span class="sxs-lookup"><span data-stu-id="da514-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da514-107">Si applica a</span><span class="sxs-lookup"><span data-stu-id="da514-107">Applies to</span></span>|<span data-ttu-id="da514-108">PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="da514-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="da514-109">Versione prodotto</span><span class="sxs-lookup"><span data-stu-id="da514-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="da514-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da514-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="da514-111">Causa</span><span class="sxs-lookup"><span data-stu-id="da514-111">Cause</span></span>|<span data-ttu-id="da514-112">Excel Services è configurato per consentire solo connessioni dati da file con estensione odc inclusi in una raccolta connessioni dati attendibili.</span><span class="sxs-lookup"><span data-stu-id="da514-112">Excel Services is configured to only allow data connections from .odc files that are in a trusted data connection library.</span></span>|  
|<span data-ttu-id="da514-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="da514-113">Message Text</span></span>|<span data-ttu-id="da514-114">Il percorso della connessione dati nella cartella di lavoro fa riferimento a un file nell'unità locale o è un URI non valido.</span><span class="sxs-lookup"><span data-stu-id="da514-114">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="da514-115">Impossibile aggiornare le connessioni seguenti: Dati di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="da514-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="da514-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="da514-116">Explanation</span></span>  
 <span data-ttu-id="da514-117">Le cartelle di lavoro di PowerPivot contengono connessioni dati incorporate.</span><span class="sxs-lookup"><span data-stu-id="da514-117">PowerPivot workbooks contain embedded data connections.</span></span> <span data-ttu-id="da514-118">Per supportare l'interazione della cartella di lavoro tramite filtri dei dati e filtri, Excel Services deve essere configurato in modo da consentire l'accesso ai dati esterni tramite informazioni di connessione incorporate.</span><span class="sxs-lookup"><span data-stu-id="da514-118">To support workbook interaction through slicers and filters, Excel Services must be configured to allow external data access through embedded connection information.</span></span> <span data-ttu-id="da514-119">L'accesso ai dati esterni è necessario per il recupero di dati PowerPivot caricati sui server PowerPivot nella farm.</span><span class="sxs-lookup"><span data-stu-id="da514-119">External data access is required for retrieving PowerPivot data that is loaded on PowerPivot servers in the farm.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="da514-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="da514-120">User Action</span></span>  
 <span data-ttu-id="da514-121">Modificare le impostazioni di configurazione per consentire le connessioni alle origini dati incorporate.</span><span class="sxs-lookup"><span data-stu-id="da514-121">Change the configuration settings to allow embedded data source connections.</span></span>  
  
1.  <span data-ttu-id="da514-122">In Gestione applicazioni di Amministrazione centrale fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="da514-122">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="da514-123">Fare clic su **Applicazione Excel Services**.</span><span class="sxs-lookup"><span data-stu-id="da514-123">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="da514-124">Fare clic su **Posizione attendibile file**.</span><span class="sxs-lookup"><span data-stu-id="da514-124">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="da514-125">Fare clic su **http://** o sul percorso che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="da514-125">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="da514-126">In Dati esterni di Impostazione dati esterni consentiti fare clic su **Raccolte di connessioni dati attendibili e connessioni incorporate**.</span><span class="sxs-lookup"><span data-stu-id="da514-126">In External Data, in Allow External Data, click **Trusted data connection libraries and embedded**.</span></span>  
  
6.  <span data-ttu-id="da514-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="da514-127">Click **OK**.</span></span>  
  
 <span data-ttu-id="da514-128">In alternativa, è possibile creare un nuovo percorso attendibile per i siti che contengono cartelle di lavoro di PowerPivot, quindi modificare le impostazioni di configurazione solo per questo sito.</span><span class="sxs-lookup"><span data-stu-id="da514-128">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="da514-129">Per altre informazioni, vedere [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="da514-129">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
