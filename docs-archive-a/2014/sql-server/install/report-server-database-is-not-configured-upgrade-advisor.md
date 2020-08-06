---
title: Il database del server di report non è configurato (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: b964300c-b220-4244-9fa6-c0c6a57760f6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 072e689da3f43222396f071e607214a2ec494749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623747"
---
# <a name="report-server-database-is-not-configured-upgrade-advisor"></a><span data-ttu-id="1013e-102">Il database del server di report non è configurato (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="1013e-102">Report server database is not configured (Upgrade Advisor)</span></span>
  <span data-ttu-id="1013e-103">L'aggiornamento è bloccato a causa di una configurazione del server di report incompleta.</span><span class="sxs-lookup"><span data-stu-id="1013e-103">Upgrade is blocked due to an incomplete report server configuration.</span></span> <span data-ttu-id="1013e-104">Il database del server di report non è configurato.</span><span class="sxs-lookup"><span data-stu-id="1013e-104">The report server database is not configured.</span></span>  
  
||  
|-|  
|<span data-ttu-id="1013e-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  Modalità nativa di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; Modalità SharePoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1013e-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="1013e-106">Componente</span><span class="sxs-lookup"><span data-stu-id="1013e-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="1013e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1013e-107">Description</span></span>  
 <span data-ttu-id="1013e-108">L'installazione può aggiornare solo un'istanza del server di report completamente configurata.</span><span class="sxs-lookup"><span data-stu-id="1013e-108">Setup can only upgrade a fully configured report server instance.</span></span> <span data-ttu-id="1013e-109">Per continuare, è necessario configurare il database del server di report oppure utilizzare il **Pannello di controllo** di Microsoft Windows per rimuovere la funzionalità del server di report dall' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installazione di.</span><span class="sxs-lookup"><span data-stu-id="1013e-109">To continue, you must either configure the report server database, or use Microsoft Windows **Control Panel** to remove the report server feature from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="1013e-110">Dopo la rimozione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è possibile aggiornare gli altri componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1013e-110">After you remove [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can upgrade other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="1013e-111">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="1013e-111">Corrective Action</span></span>  
 <span data-ttu-id="1013e-112">Se il database del server di report non è stato configurato, il server di report non è operativo e deve essere rimosso prima dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1013e-112">If you did not configure the report server database, the report server is not operational and should be removed prior to upgrade.</span></span>  
  
 <span data-ttu-id="1013e-113">Per ulteriori informazioni sulla disinstallazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , vedere [Uninstall Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span><span class="sxs-lookup"><span data-stu-id="1013e-113">For additional information on uninstalling [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , see [Uninstall Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span></span> <span data-ttu-id="1013e-114">Nell'argomento viene descritto come disinstallare una versione specifica e le procedure sono simili a quelle delle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="1013e-114">the topic describes how to uninstall a specific version and the procedures are similar for previous versions as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1013e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1013e-115">See Also</span></span>  
 [<span data-ttu-id="1013e-116">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="1013e-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
