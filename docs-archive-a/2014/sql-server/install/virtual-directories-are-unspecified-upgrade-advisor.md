---
title: Le directory virtuali non sono specificate (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 7d32b560-49d6-4558-b5d6-9127067f82d6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e20c48d0bf58d28cb2894baa26c2e11db26fab96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628114"
---
# <a name="virtual-directories-are-unspecified-upgrade-advisor"></a><span data-ttu-id="753a3-102">Non sono state specificate directory virtuali (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="753a3-102">Virtual directories are unspecified (Upgrade Advisor)</span></span>
  <span data-ttu-id="753a3-103">Non sono state rilevate impostazioni di directory virtuali per il servizio Web ReportServer o Gestione report.</span><span class="sxs-lookup"><span data-stu-id="753a3-103">Upgrade Advisor did not detect virtual directory settings for the Report Server Web service or Report Manager.</span></span> <span data-ttu-id="753a3-104">Dopo che l'aggiornamento è stato completato, è necessario configurare le prenotazioni URL per il server di report tramite Gestione configurazione [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="753a3-104">After upgrade completes, you must configure URL reservations for the report server by using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager.</span></span>  
  
||  
|-|  
|<span data-ttu-id="753a3-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="753a3-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="753a3-106">Componente</span><span class="sxs-lookup"><span data-stu-id="753a3-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="753a3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="753a3-107">Description</span></span>  
 <span data-ttu-id="753a3-108">L'aggiornamento di un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] richiede di riservare nuovi URL per il servizio Web ReportServer e Gestione report.</span><span class="sxs-lookup"><span data-stu-id="753a3-108">Upgrading a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation includes reserving new URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="753a3-109">Per l'istanza da aggiornare, non sono state rilevate directory virtuali per il server di report o Gestione report. Pertanto, le informazioni disponibili non sono sufficienti per creare prenotazioni URL per il server di report aggiornato.</span><span class="sxs-lookup"><span data-stu-id="753a3-109">Upgrade Advisor did not detect virtual directories for the report server or Report Manager for the instance to be upgraded, and therefore the upgrade process has insufficient information to create URL reservations for the upgraded report server.</span></span> <span data-ttu-id="753a3-110">L'aggiornamento può continuare, ma la directory virtuale del server di report o di Gestione report non sarà definita dopo che l'installazione è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="753a3-110">Upgrade can continue, but the report server or Report Manager virtual directory will be undefined after the upgraded installation.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="753a3-111">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="753a3-111">Corrective Action</span></span>  
 <span data-ttu-id="753a3-112">Dopo l'aggiornamento, utilizzare Gestione configurazione [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] per impostare gli URL per il server di report e Gestione report.</span><span class="sxs-lookup"><span data-stu-id="753a3-112">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to set the URLs for report server and Report Manager.</span></span> <span data-ttu-id="753a3-113">Utilizzare Gestione IIS per rimuovere le directory virtuali non più necessarie.</span><span class="sxs-lookup"><span data-stu-id="753a3-113">Use IIS Manager to remove any virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="753a3-114">Per ulteriori informazioni, vedere [configurare un URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentazione online di.</span><span class="sxs-lookup"><span data-stu-id="753a3-114">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753a3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="753a3-115">See Also</span></span>  
 [<span data-ttu-id="753a3-116">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="753a3-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
