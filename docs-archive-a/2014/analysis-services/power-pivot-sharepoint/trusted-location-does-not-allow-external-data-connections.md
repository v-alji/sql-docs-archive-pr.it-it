---
title: 'Il percorso attendibile in cui è archiviata la cartella di lavoro non consente connessioni dati esterne. Impossibile aggiornare le connessioni seguenti: dati PowerPivot | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dc0cedfd-a7d0-40ef-bdd6-ea508130640a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b7f6d335eac0bec0f67012cc413f3917c50348b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623512"
---
# <a name="the-trusted-location-where-the-workbook-is-stored-does-not-allow-external-data-connections-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="7d98b-103">Il percorso attendibile in cui è archiviata la cartella di lavoro non consente connessioni dati esterne.</span><span class="sxs-lookup"><span data-stu-id="7d98b-103">The trusted location where the workbook is stored does not allow external data connections.</span></span> <span data-ttu-id="7d98b-104">Impossibile aggiornare le connessioni seguenti: Dati di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="7d98b-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="7d98b-105">Per cartelle di lavoro di Excel contenenti dati PowerPivot, in Excel Services viene restituito questo errore se non è possibile connettersi a origini dati incorporate.</span><span class="sxs-lookup"><span data-stu-id="7d98b-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to embedded data sources.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7d98b-106">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7d98b-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d98b-107">Si applica a</span><span class="sxs-lookup"><span data-stu-id="7d98b-107">Applies to</span></span>|<span data-ttu-id="7d98b-108">PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d98b-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="7d98b-109">Versione prodotto</span><span class="sxs-lookup"><span data-stu-id="7d98b-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="7d98b-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d98b-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="7d98b-111">Causa</span><span class="sxs-lookup"><span data-stu-id="7d98b-111">Cause</span></span>|<span data-ttu-id="7d98b-112">Excel Services è configurato per negare l'accesso ai dati esterni.</span><span class="sxs-lookup"><span data-stu-id="7d98b-112">Excel Services is configured to deny external data access.</span></span>|  
|<span data-ttu-id="7d98b-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="7d98b-113">Message Text</span></span>|<span data-ttu-id="7d98b-114">Il percorso attendibile in cui è archiviata la cartella di lavoro non consente connessioni dati esterne.</span><span class="sxs-lookup"><span data-stu-id="7d98b-114">The trusted location where the workbook is stored does not allow external data connections.</span></span> <span data-ttu-id="7d98b-115">Impossibile aggiornare le connessioni seguenti: Dati di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="7d98b-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d98b-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="7d98b-116">Explanation</span></span>  
 <span data-ttu-id="7d98b-117">Le cartelle di lavoro di PowerPivot contengono connessioni dati incorporate.</span><span class="sxs-lookup"><span data-stu-id="7d98b-117">PowerPivot workbooks contain embedded data connections.</span></span> <span data-ttu-id="7d98b-118">Per supportare l'interazione della cartella di lavoro tramite filtri dei dati e filtri, Excel Services deve essere configurato in modo da consentire l'accesso ai dati esterni tramite informazioni di connessione incorporate.</span><span class="sxs-lookup"><span data-stu-id="7d98b-118">To support workbook interaction through slicers and filters, Excel Services must be configured to allow external data access through embedded connection information.</span></span> <span data-ttu-id="7d98b-119">L'accesso ai dati esterni è necessario per il recupero di dati PowerPivot caricati sui server PowerPivot nella farm.</span><span class="sxs-lookup"><span data-stu-id="7d98b-119">External data access is required for retrieving PowerPivot data that is loaded on PowerPivot servers in the farm.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d98b-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7d98b-120">User Action</span></span>  
 <span data-ttu-id="7d98b-121">Modificare le impostazioni di configurazione per consentire le origini dati incorporate.</span><span class="sxs-lookup"><span data-stu-id="7d98b-121">Change the configuration settings to allow embedded data sources.</span></span>  
  
1.  <span data-ttu-id="7d98b-122">In Gestione applicazioni di Amministrazione centrale fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="7d98b-122">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="7d98b-123">Fare clic su **Applicazione Excel Services**.</span><span class="sxs-lookup"><span data-stu-id="7d98b-123">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="7d98b-124">Fare clic su **Posizione attendibile file**.</span><span class="sxs-lookup"><span data-stu-id="7d98b-124">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="7d98b-125">Fare clic su **http://** o sul percorso che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="7d98b-125">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="7d98b-126">In Dati esterni di Impostazione dati esterni consentiti fare clic su **Raccolte di connessioni dati attendibili e connessioni incorporate**.</span><span class="sxs-lookup"><span data-stu-id="7d98b-126">In External Data, in Allow External Data, click **Trusted data connection libraries and embedded**.</span></span>  
  
6.  <span data-ttu-id="7d98b-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d98b-127">Click **OK**.</span></span>  
  
 <span data-ttu-id="7d98b-128">In alternativa, è possibile creare un nuovo percorso attendibile per i siti che contengono cartelle di lavoro di PowerPivot, quindi modificare le impostazioni di configurazione solo per questo sito.</span><span class="sxs-lookup"><span data-stu-id="7d98b-128">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="7d98b-129">Per altre informazioni, vedere [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="7d98b-129">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
