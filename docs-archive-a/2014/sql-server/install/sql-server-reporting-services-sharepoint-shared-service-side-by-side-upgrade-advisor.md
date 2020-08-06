---
title: Microsoft SQL Server Reporting Services servizio SharePoint Shared è installato side-by-Side (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6ae1017e-129b-4702-9ea7-00ac9b024062
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b8a26fedd892dfb26dea4616efd46d3b3748b508
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635328"
---
# <a name="microsoft-sql-server-reporting-services-sharepoint-shared-service-is-installed-side-by-side-upgrade-advisor"></a><span data-ttu-id="9d215-102">Il servizio Shared SharePoint di Microsoft SQL Server Reporting Services è installato in modalità affiancata (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="9d215-102">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side (Upgrade Advisor)</span></span>
  <span data-ttu-id="9d215-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] È stato rilevato che il servizio SharePoint Shared è installato side-by-side con una versione precedente di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d215-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="9d215-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità SharePoint di.</span><span class="sxs-lookup"><span data-stu-id="9d215-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="9d215-105">Componente</span><span class="sxs-lookup"><span data-stu-id="9d215-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="9d215-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d215-106">Description</span></span>  
 <span data-ttu-id="9d215-107">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] È stato rilevato che il servizio condiviso SharePoint è installato side-by-side con una versione precedente di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] che non si basa sull'architettura del servizio SharePoint Shared.</span><span class="sxs-lookup"><span data-stu-id="9d215-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is not based on the SharePoint shared service architecture.</span></span> <span data-ttu-id="9d215-108">Poiché nel computer sono installate side-by-side la tecnologia precedente e la nuova tecnologia SharePoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], l'aggiornamento viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="9d215-108">Because the computer has both older and newer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint related technologies installed side by side, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9d215-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="9d215-109">Corrective Action</span></span>  
 <span data-ttu-id="9d215-110">Per procedere con l'aggiornamento, è necessario disinstallare una delle installazioni esistenti di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d215-110">To continue with upgrade, you must uninstall one of the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installations.</span></span> <span data-ttu-id="9d215-111">Dopo aver rimosso una delle installazioni di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], eseguire nuovamente Upgrade Advisor per confermare che non sono presenti altri errori di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="9d215-111">After removing one of the installations of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
  
