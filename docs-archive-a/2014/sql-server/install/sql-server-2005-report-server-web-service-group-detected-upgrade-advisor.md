---
title: Rilevato gruppo di servizi Web ReportServer SQL Server 2005 (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- deployment [Reporting Services]
ms.assetid: 699d24eb-7756-4b41-9294-ef1a94b2f267
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 70be2b9c4e7abd55daaa752830a73cbe6e222659
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726475"
---
# <a name="sql-server-2005-report-server-web-service-group-detected-upgrade-advisor"></a><span data-ttu-id="57508-102">Rilevato un gruppo di servizi Web ReportServer di SQL Server 2005 (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="57508-102">SQL Server 2005 Report Server Web Service group detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="57508-103">È stato rilevato che l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istanza è associata a un [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] gruppo di servizi Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="57508-103">Upgrade Advisor detected that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is associated with a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span>  
  
||  
|-|  
|<span data-ttu-id="57508-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="57508-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="57508-105">Componente</span><span class="sxs-lookup"><span data-stu-id="57508-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="57508-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57508-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="57508-107">non [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Usa il [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Gruppo di servizi Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="57508-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not use the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="57508-108">Quando si esegue l'aggiornamento da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], questo gruppo di servizi viene eliminato e gli elenchi di controllo di accesso (ACL) personalizzati o gli utenti che appartengono al gruppo non vengono mantenuti durante l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="57508-108">When you upgrade from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this service group is deleted and custom Access Control Lists (ACLs) for this group or users who belong to the group are not retained during the upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="57508-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="57508-109">Corrective Action</span></span>  
 <span data-ttu-id="57508-110">Prima di eseguire l'aggiornamento, eseguire il backup di tutti gli elenchi di controllo di accesso o utenti che appartengono al gruppo di servizi Web ReportServer di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57508-110">Before you upgrade, back up any custom ACLs or users who belong to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="57508-111">A tale scopo, è possibile usare lo strumento da riga di comando **Icacls.exe** in [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2 e versioni successive o lo strumento da riga di comando Cacls.exe nei sistemi operativi Windows precedenti a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span><span class="sxs-lookup"><span data-stu-id="57508-111">To do this, you can use the **Icacls.exe** command-line tool in [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2 and later or the Cacls.exe command-line tool in Windows operating systems prior to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span></span> <span data-ttu-id="57508-112">Per ulteriori informazioni sulla sintassi per questi strumenti, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="57508-112">For more information about the syntax for these tools, see the Windows product documentation.</span></span> <span data-ttu-id="57508-113">Dopo che l'installazione è stata completata, applicare gli elenchi di controllo di accesso personalizzati o gli utenti al gruppo Windows del server di report di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] per l'istanza del server di report.</span><span class="sxs-lookup"><span data-stu-id="57508-113">After setup successfully completes, apply the custom ACLs or users to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group for your report server instance.</span></span> <span data-ttu-id="57508-114">Il [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] gruppo di Windows del server di report assume il formato SQLServerReportServerUser $ \<*computer_name*> $ \<*instance_name*> .</span><span class="sxs-lookup"><span data-stu-id="57508-114">The [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group takes the form of SQLServerReportServerUser$\<*computer_name*>$\<*instance_name*>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57508-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57508-115">See Also</span></span>  
 [<span data-ttu-id="57508-116">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="57508-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
