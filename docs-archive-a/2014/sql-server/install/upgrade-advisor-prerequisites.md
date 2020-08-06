---
title: Prerequisiti di preparazione aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- requirements [Upgrade Advisor]
- software [Upgrade Advisor]
- system requirements [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, prerequisites
- prerequisites [Upgrade Advisor]
- Upgrade Advisor [SQL Server], prerequisites
ms.assetid: d21a39e5-5f81-4096-a7dd-f244e4779992
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 41c97cf585d1768c7aebeec2613ee8744cb220da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628119"
---
# <a name="upgrade-advisor-prerequisites"></a><span data-ttu-id="6bbe2-102">Prerequisiti di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="6bbe2-102">Upgrade Advisor Prerequisites</span></span>
  <span data-ttu-id="6bbe2-103">In questo argomento vengono descritti i requisiti software di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="6bbe2-103">This topic describes the software requirements for Upgrade Advisor.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6bbe2-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6bbe2-104">Prerequisites</span></span>  
 <span data-ttu-id="6bbe2-105">Di seguito vengono indicati i prerequisiti per l'installazione e l'esecuzione di Preparazione aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="6bbe2-105">The prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[wiprlhext](../../includes/wiprlhext-md.md)] <span data-ttu-id="6bbe2-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] a partire da SP2, Windows 7 o [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span><span class="sxs-lookup"><span data-stu-id="6bbe2-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] beginning with SP2, Windows 7, or [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span></span>  
  
-   <span data-ttu-id="6bbe2-107">Windows Installer 4.5.</span><span class="sxs-lookup"><span data-stu-id="6bbe2-107">Windows Installer 4.5.</span></span> <span data-ttu-id="6bbe2-108">È possibile installare Windows Installer dal [sito Web di Windows Installer](https://www.microsoft.com/download/details.aspx?id=8483).</span><span class="sxs-lookup"><span data-stu-id="6bbe2-108">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="6bbe2-109">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6bbe2-109">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], beginning with .NET Framework 4.</span></span> <span data-ttu-id="6bbe2-110">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]È disponibile sul supporto del [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] prodotto e dal [sito Web SDK, ridistribuibile e scaricabile da Service Pack](https://go.microsoft.com/fwlink/?LinkId=48882).</span><span class="sxs-lookup"><span data-stu-id="6bbe2-110">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [SDK, redistributable, and service pack download Web site](https://go.microsoft.com/fwlink/?LinkId=48882).</span></span>  
  
    -   <span data-ttu-id="6bbe2-111">Per eseguire l'installazione di .NET Framework 4 dai supporti di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], individuare la radice dell'unità disco.</span><span class="sxs-lookup"><span data-stu-id="6bbe2-111">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="6bbe2-112">Fare quindi doppio clic sulla cartella \redist, sulla cartella DotNetFrameworks ed eseguire dotNetFx40_Full_x86_x64.exe (sia per i sistemi operativi a 32 bit che per quelli a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="6bbe2-112">Then double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for both 32-bit and 64-bit operating systems).</span></span>  
  
-   <span data-ttu-id="6bbe2-113">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom è un prerequisito per l'installazione [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] di preparazione aggiornamento e non viene installato tramite l'installazione di preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="6bbe2-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="6bbe2-114">Per il programma di installazione è necessario scaricare e installare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="6bbe2-114">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bbe2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bbe2-115">See Also</span></span>  
 [<span data-ttu-id="6bbe2-116">Procedura: Installare Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="6bbe2-116">How to: Install Upgrade Advisor</span></span>](../../../2014/sql-server/install/how-to-install-upgrade-advisor.md)  
  
  
