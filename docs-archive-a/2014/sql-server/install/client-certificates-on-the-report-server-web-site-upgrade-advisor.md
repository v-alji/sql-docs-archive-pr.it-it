---
title: Certificati client sul sito Web del server di report (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 5ecce26b-99df-4109-8e51-d150d369dff7
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 563a64e695ef552a712a5678f56d38fdfbff619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628213"
---
# <a name="client-certificates-on-the-report-server-web-site-upgrade-advisor"></a><span data-ttu-id="7b8b3-102">Certificati client sul sito Web del server di report (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="7b8b3-102">Client certificates on the report server web site (Upgrade Advisor)</span></span>
  <span data-ttu-id="7b8b3-103">Sono stati rilevati uno o più certificati client sul sito Web IIS che ospita le directory virtuali del server di report o di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="7b8b3-103">Upgrade Advisor detected one or more client certificates on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span>  
  
||  
|-|  
|<span data-ttu-id="7b8b3-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="7b8b3-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="7b8b3-105">Componente</span><span class="sxs-lookup"><span data-stu-id="7b8b3-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="7b8b3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b8b3-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="7b8b3-107">non [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] supporta l'utilizzo di certificati client per autenticare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7b8b3-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not support the use of client certificates to authenticate users.</span></span> <span data-ttu-id="7b8b3-108">L'aggiornamento può continuare, ma i certificati client non verranno utilizzati dal server di report aggiornato.</span><span class="sxs-lookup"><span data-stu-id="7b8b3-108">Upgrade can continue, but client certificates will not be used by the upgraded report server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7b8b3-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="7b8b3-109">Corrective Action</span></span>  
 <span data-ttu-id="7b8b3-110">Sarà necessario utilizzare una soluzione distinta, ad esempio ISA Server, per assicurarsi di rispettare i requisiti di autenticazione dei certificati client.</span><span class="sxs-lookup"><span data-stu-id="7b8b3-110">You will have to use a separate solution such as ISA Server to ensure any client certificate authentication requirements are addressed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8b3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b8b3-111">See Also</span></span>  
 [<span data-ttu-id="7b8b3-112">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="7b8b3-112">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
