---
title: Archiviazione di gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, storage
ms.assetid: d0cbf214-fc2e-4917-8d31-1d71c9ffa61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0e775d038c5bb4f7a467f2691e374296f1389d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715192"
---
# <a name="policy-based-management-storage"></a><span data-ttu-id="0cd54-102">Archiviazione di gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="0cd54-102">Policy-Based Management Storage</span></span>
  <span data-ttu-id="0cd54-103">I criteri vengono archiviati nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="0cd54-103">Policies are stored in the msdb database.</span></span> <span data-ttu-id="0cd54-104">In seguito alla modifica di criteri o di una condizione, è consigliabile eseguire il backup del database msdb.</span><span class="sxs-lookup"><span data-stu-id="0cd54-104">After a policy or condition is changed, msdb should be backed up.</span></span> <span data-ttu-id="0cd54-105">Per altre informazioni, vedere [Backup e ripristino di Database di sistema &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0cd54-105">For more information, see [Back Up and Restore of System Databases &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span></span>  
  
## <a name="storing-policies"></a><span data-ttu-id="0cd54-106">Archiviazione di criteri</span><span class="sxs-lookup"><span data-stu-id="0cd54-106">Storing Policies</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="0cd54-107">include criteri che consentono di monitorare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cd54-107">includes policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0cd54-108">Per impostazione predefinita, questi criteri non vengono installati nel, ma [!INCLUDE[ssDE](../../includes/ssde-md.md)] possono essere importati dal percorso di installazione predefinito C:\Program Files (x86) \Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span><span class="sxs-lookup"><span data-stu-id="0cd54-108">By default, these policies are not installed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)]; however, they can be imported from the default installation location of C:\Program Files (x86)\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
 <span data-ttu-id="0cd54-109">È possibile creare direttamente criteri utilizzando il menu **File/Nuovo** , quindi salvando i criteri in un file.</span><span class="sxs-lookup"><span data-stu-id="0cd54-109">You can directly create policies by using the **File/New** menu, and then saving them to a file.</span></span> <span data-ttu-id="0cd54-110">In questo modo è possibile creare criteri quando non si è connessi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cd54-110">This enables you to create policies when you are not connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="0cd54-111">Una cronologia dei criteri valutati nell'istanza corrente del [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene gestita nelle tabelle di sistema msdb.</span><span class="sxs-lookup"><span data-stu-id="0cd54-111">Policy history for policies evaluated in the current instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is maintained in msdb system tables.</span></span> <span data-ttu-id="0cd54-112">Non viene mantenuta alcuna cronologia dei criteri applicati ad altre istanze del [!INCLUDE[ssDE](../../includes/ssde-md.md)] o a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cd54-112">Policy history for policies applied to other instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] or applied to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not retained.</span></span>  
  
  
