---
title: Sono stati rilevati elementi del report personalizzati nel server di report (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- custom report items, upgrading
ms.assetid: aee32006-65b2-4dfe-9570-d85a249d17b2
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: feacf6aa6f233f85a67b43e7b72d3a50913991bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626475"
---
# <a name="custom-report-items-were-detected-on-the-report-server-upgrade-advisor"></a><span data-ttu-id="4f377-102">Sono stati rilevati elementi di report personalizzati nel server di report (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="4f377-102">Custom report items were detected on the report server (Upgrade Advisor)</span></span>
  <span data-ttu-id="4f377-103">Gli elementi del report personalizzati creati per le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] non sono compatibili con [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f377-103">Custom report items that were created for previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] are not compatible with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="4f377-104">L'aggiornamento può continuare, ma i report che utilizzano l'elemento del report personalizzato non verranno eseguiti come previsto.</span><span class="sxs-lookup"><span data-stu-id="4f377-104">Upgrade can continue, but reports that use the custom report item will not run as expected.</span></span> <span data-ttu-id="4f377-105">Sono stati rilevati elementi del report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4f377-105">Upgrade Advisor detected custom report items.</span></span> <span data-ttu-id="4f377-106">L'aggiornamento può continuare, ma è necessario spostare manualmente i file relativi agli elementi del report personalizzati nella nuova cartella di installazione dopo che l'aggiornamento è stato completato.</span><span class="sxs-lookup"><span data-stu-id="4f377-106">Upgrade can continue, but you must manually move the custom report item files to the new installation folder after upgrade completes.</span></span>  
  
||  
|-|  
|<span data-ttu-id="4f377-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  Modalità nativa di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; Modalità SharePoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f377-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="4f377-108">Componente</span><span class="sxs-lookup"><span data-stu-id="4f377-108">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="4f377-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f377-109">Description</span></span>  
 <span data-ttu-id="4f377-110">Nei file di configurazione sono state rilevate impostazioni di estensioni [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] personalizzate, indicanti che l'installazione include uno o più assembly personalizzati per il report.</span><span class="sxs-lookup"><span data-stu-id="4f377-110">Upgrade Advisor detected custom [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] extension settings in the configuration files, indicating that your installation includes one or more custom assemblies for reports.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="4f377-111">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="4f377-111">Corrective Action</span></span>  
 <span data-ttu-id="4f377-112">Dopo che l'aggiornamento è stato completato, spostare manualmente i file relativi agli elementi del report personalizzati nella nuova cartella di installazione.</span><span class="sxs-lookup"><span data-stu-id="4f377-112">After upgrade completes, manually move the custom report item files to the new installation folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f377-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f377-113">See Also</span></span>  
 [<span data-ttu-id="4f377-114">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="4f377-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
