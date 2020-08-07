---
title: Restrizione indirizzi IP rilevata (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 9a154455-c68f-4403-a3a7-b90f4d35eecb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 2028e59e91d42bfdced2d18fa6ce129dfb108302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715975"
---
# <a name="ip-address-restriction-detected-upgrade-advisor"></a><span data-ttu-id="d001f-102">Rilevata restrizione degli indirizzi IP (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="d001f-102">IP address restriction detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="d001f-103">Sono state rilevate una o più restrizioni degli indirizzi IP sul sito Web di IIS che ospita le directory virtuali del server di report o di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="d001f-103">Upgrade Advisor detected one or more IP address restrictions on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span> <span data-ttu-id="d001f-104">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] non è disponibile il supporto nativo per le restrizioni degli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="d001f-104">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide native support for IP address restrictions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="d001f-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Native.</span><span class="sxs-lookup"><span data-stu-id="d001f-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="d001f-106">Componente</span><span class="sxs-lookup"><span data-stu-id="d001f-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="d001f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d001f-107">Description</span></span>  
 <span data-ttu-id="d001f-108">Non è possibile definire le restrizioni degli indirizzi IP sugli URL creati per un server di report aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d001f-108">Setup cannot define IP address restrictions on URLs created for an upgraded report server.</span></span> <span data-ttu-id="d001f-109">L'aggiornamento può continuare, ma le restrizioni degli indirizzi IP non saranno definite sugli URL di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d001f-109">Upgrade can continue, but IP address restrictions will not be defined on the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="d001f-110">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="d001f-110">Corrective Action</span></span>  
 <span data-ttu-id="d001f-111">Dopo l'aggiornamento, utilizzare ISA Server, il software del firewall o un'altra soluzione per consentire o escludere richieste dagli indirizzi IP specifici al server di report.</span><span class="sxs-lookup"><span data-stu-id="d001f-111">After upgrade, use ISA Server, your firewall software, or another solution to allow or exclude requests from specific IP addresses to the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d001f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d001f-112">See Also</span></span>  
 [<span data-ttu-id="d001f-113">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="d001f-113">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
