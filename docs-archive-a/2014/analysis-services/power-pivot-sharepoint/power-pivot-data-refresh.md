---
title: Aggiornamento dati PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: ac8358a3-ee71-44c7-8ee6-ac7afe3ebaa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f7d5ed5c2f8882cbc0c47a1c711748d26e0193c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629035"
---
# <a name="powerpivot-data-refresh"></a><span data-ttu-id="0945b-102">Aggiornamento dei dati PowerPivot</span><span class="sxs-lookup"><span data-stu-id="0945b-102">PowerPivot Data Refresh</span></span>
  <span data-ttu-id="0945b-103">Dopo avere creato una cartella di lavoro che contiene dati PowerPivot, è possibile aggiornare periodicamente i dati rieseguendo una query o un comando per ottenere informazioni aggiornate dalle origini utilizzate in origine per creare la cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0945b-103">After you create a workbook that contains PowerPivot data, you might want to periodically refresh the data by rerunning a query or command to get updated information from the sources you used originally to create the workbook.</span></span> <span data-ttu-id="0945b-104">Questo processo, denominato `data refresh`, consente di aggiornare i dati su richiesta in [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] o come operazione pianificata eseguita come processo di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in un server applicazioni in una farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0945b-104">This process is called `data refresh`, and you can refresh data on demand in [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], or as a scheduled operation that runs as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process on an application server in a SharePoint farm.</span></span> <span data-ttu-id="0945b-105">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="0945b-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="0945b-106">Aggiornamento di dati PowerPivot con SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="0945b-106">PowerPivot Data Refresh with SharePoint 2010</span></span>](../powerpivot-data-refresh-with-sharepoint-2010.md)  
  
-   [<span data-ttu-id="0945b-107">Configurare l'account di aggiornamento dati automatico PowerPivot &#40;PowerPivot per SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="0945b-107">Configure the PowerPivot Unattended Data Refresh Account &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-unattended-data-refresh-account-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="0945b-108">Configurare le credenziali archiviate per l'aggiornamento dati PowerPivot &#40;PowerPivot per SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="0945b-108">Configure Stored Credentials for PowerPivot Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="0945b-109">Pianificare un aggiornamento dati &#40;PowerPivot per SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="0945b-109">Schedule a Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../schedule-a-data-refresh-powerpivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="0945b-110">Visualizzare la cronologia dell'aggiornamento dati &#40;PowerPivot per SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="0945b-110">View Data Refresh History &#40;PowerPivot for SharePoint&#41;</span></span>](view-data-refresh-history-power-pivot-for-sharepoint.md)  
  
> [!NOTE]
>  <span data-ttu-id="0945b-111">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e SharePoint Server 2013 Excel Services viene utilizzata un'architettura diversa per i modelli di dati PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="0945b-111">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and SharePoint Server 2013 Excel Services use a different architecture for data refresh of PowerPivot data models.</span></span> <span data-ttu-id="0945b-112">Nell'architettura supportata da SharePoint 2013 viene utilizzato Excel Services come componente principale per caricare modelli di dati PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="0945b-112">The SharePoint 2013 supported architecture utilizes Excel Services as the primary component to load PowerPivot data models.</span></span> <span data-ttu-id="0945b-113">L'architettura di aggiornamento dati utilizzata in precedenza era basata su un server con in esecuzione il servizio di sistema di PowerPivot e [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in modalità SharePoint per caricare i modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="0945b-113">The previous data refresh architecture used relied on a server running PowerPivot System Service and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in SharePoint mode to load data models.</span></span> <span data-ttu-id="0945b-114">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0945b-114">For more information, see the following:</span></span>  
> 
>  -   [<span data-ttu-id="0945b-115">Aggiornamento dati PowerPivot con SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="0945b-115">PowerPivot Data Refresh with SharePoint 2013</span></span>](power-pivot-data-refresh-with-sharepoint-2013.md)  
> -   [<span data-ttu-id="0945b-116">Aggiornare le cartelle di lavoro e l'aggiornamento dati pianificato &#40;SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="0945b-116">Upgrade Workbooks and Scheduled Data Refresh &#40;SharePoint 2013&#41;</span></span>](../instances/install-windows/upgrade-workbooks-and-scheduled-data-refresh-sharepoint-2013.md)  
  
  
