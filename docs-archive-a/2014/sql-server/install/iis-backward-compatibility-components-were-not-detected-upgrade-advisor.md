---
title: Non sono stati rilevati componenti di compatibilità con le versioni precedenti IIS (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IIS [Reporting Services]
ms.assetid: e794185a-0a77-480a-9aea-d09f8760a6b8
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a5aad54a01b3840e121c6a63de0ea26f35921fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637037"
---
# <a name="iis-backward-compatibility-components-were-not-detected-upgrade-advisor"></a><span data-ttu-id="055ee-102">Non sono stati rilevati componenti di compatibilità con le versioni precedenti di IIS (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="055ee-102">IIS backward compatibility components were not detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="055ee-103">Non sono stati rilevati componenti e impostazioni IIS che forniscono le informazioni utilizzate dal programma di installazione per creare nuovi URL di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="055ee-103">Upgrade Advisor did not detect IIS components and settings that provide information used by Setup to create new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLS.</span></span>  
  
||  
|-|  
|<span data-ttu-id="055ee-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="055ee-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="055ee-105">Componente</span><span class="sxs-lookup"><span data-stu-id="055ee-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="055ee-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="055ee-106">Description</span></span>  
 <span data-ttu-id="055ee-107">IIS include componenti che forniscono informazioni sulle directory virtuali del server di report e di Gestione report. Tali componenti non sono installati nel computer del server di report.</span><span class="sxs-lookup"><span data-stu-id="055ee-107">IIS includes components that provide information about the report server and Report Manager virtual directories, and those components are not installed on the report server computer.</span></span> <span data-ttu-id="055ee-108">L'aggiornamento può continuare, ma gli URL per il server di report o per Gestione report non verranno ricreati con l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="055ee-108">Upgrade can continue, but URLs for the report server or Report Manager will not be recreated by upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="055ee-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="055ee-109">Corrective Action</span></span>  
 <span data-ttu-id="055ee-110">Dopo l'aggiornamento, utilizzare lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] per impostare gli URL per il server di report o Gestione report.</span><span class="sxs-lookup"><span data-stu-id="055ee-110">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set the URLs for report server or Report Manager.</span></span> <span data-ttu-id="055ee-111">Utilizzare Gestione IIS per rimuovere le directory virtuali non più necessarie.</span><span class="sxs-lookup"><span data-stu-id="055ee-111">Use IIS Manager to remove the virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="055ee-112">Per ulteriori informazioni, vedere [configurare un URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentazione online di.</span><span class="sxs-lookup"><span data-stu-id="055ee-112">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="055ee-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="055ee-113">See Also</span></span>  
 [<span data-ttu-id="055ee-114">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="055ee-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
