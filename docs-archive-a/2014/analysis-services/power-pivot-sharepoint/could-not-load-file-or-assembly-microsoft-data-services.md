---
title: Impossibile caricare il file o l'assembly &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39; | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6e350b67-5e18-4b90-8fb7-a0109cbb27b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: b7ba75bdbd8e25f98d11d822c22fa7881352ad88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635796"
---
# <a name="could-not-load-file-or-assembly-39microsoftanalysisservicessharepointintegration39"></a><span data-ttu-id="8a9dd-102">Impossibile caricare il file o l'assembly &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39;</span><span class="sxs-lookup"><span data-stu-id="8a9dd-102">Could not load file or assembly &#39;Microsoft.AnalysisServices.SharePoint.Integration&#39;</span></span>
  <span data-ttu-id="8a9dd-103">Negli ambienti di SharePoint 2010 in cui è disponibile PowerPivot per SharePoint, questo errore si verificherà se la distribuzione della soluzione a livello di applicazione per PowerPivot non è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-103">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if the application-level solution for PowerPivot did not deploy correctly.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a9dd-104">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8a9dd-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a9dd-105">Si applica a</span><span class="sxs-lookup"><span data-stu-id="8a9dd-105">Applies to</span></span>|<span data-ttu-id="8a9dd-106">PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="8a9dd-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="8a9dd-107">Versione prodotto</span><span class="sxs-lookup"><span data-stu-id="8a9dd-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="8a9dd-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a9dd-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="8a9dd-109">Causa</span><span class="sxs-lookup"><span data-stu-id="8a9dd-109">Cause</span></span>|<span data-ttu-id="8a9dd-110">La soluzione Powerpivotwebapp non è stata distribuita o non ha eseguito correttamente la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-110">Powerpivotwebapp solution is not deployed or did not deploy correctly.</span></span>|  
|<span data-ttu-id="8a9dd-111">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8a9dd-111">Message Text</span></span>|<span data-ttu-id="8a9dd-112">Impossibile caricare il file o l'assembly "Microsoft.AnalysisServices.SharePoint.Integration"</span><span class="sxs-lookup"><span data-stu-id="8a9dd-112">Could not load file or assembly 'Microsoft.AnalysisServices.SharePoint.Integration'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8a9dd-113">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8a9dd-113">Explanation</span></span>  
 <span data-ttu-id="8a9dd-114">PowerPivot per SharePoint utilizza i pacchetti della soluzione per distribuire le funzionalità in un server SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-114">PowerPivot for SharePoint uses solution packages to deploy its features on a SharePoint server.</span></span> <span data-ttu-id="8a9dd-115">Una delle soluzioni non è distribuita correttamente.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-115">One of the solutions is not deployed correctly.</span></span> <span data-ttu-id="8a9dd-116">Di conseguenza, questo errore viene visualizzato quando si tenta di aprire la raccolta PowerPivot o altre pagine dell'applicazione PowerPivot in un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-116">As a result, this error appears whenever you try to open PowerPivot Gallery or other PowerPivot application pages on a SharePoint site.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a9dd-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8a9dd-117">User Action</span></span>  
 <span data-ttu-id="8a9dd-118">Distribuire il pacchetto della soluzione.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-118">Deploy the solution package.</span></span>  
  
1.  <span data-ttu-id="8a9dd-119">In Impostazioni sistema di Amministrazione centrale fare clic su **Gestisci soluzioni farm**.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-119">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="8a9dd-120">Fare clic su **Powerpivotwebapp**.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-120">Click **Powerpivotwebapp**.</span></span>  
  
3.  <span data-ttu-id="8a9dd-121">Fare clic su **Distribuisci soluzione**.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-121">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="8a9dd-122">Scegliere l'applicazione Web per la quale si sta verificando questo errore.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-122">Choose the web application for which this error is occurring.</span></span> <span data-ttu-id="8a9dd-123">Se sono presenti più applicazioni Web, ridistribuire la soluzione per tutte.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-123">If there is more than one web application, redeploy the solution for all of hem.</span></span>  
  
5.  <span data-ttu-id="8a9dd-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a9dd-124">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a9dd-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a9dd-125">See Also</span></span>  
 [<span data-ttu-id="8a9dd-126">Distribuire soluzioni PowerPivot in SharePoint</span><span class="sxs-lookup"><span data-stu-id="8a9dd-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
