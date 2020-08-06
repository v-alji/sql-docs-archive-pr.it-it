---
title: Ricicla log degli errori di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.errorlog.recyclesqlagenterrorlogs.f1
ms.assetid: 10bc2dd1-0505-4527-8ec7-d3b4e5d6352b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b30f0a2ba9a2d861d4a36a86489757cde512fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637571"
---
# <a name="recycle-sql-server-agent-error-logs"></a><span data-ttu-id="52cfb-102">Ricicla log degli errori di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="52cfb-102">Recycle SQL Server Agent Error Logs</span></span>
  <span data-ttu-id="52cfb-103">Utilizzare questa pagina per riciclare i [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log degli errori di Agent.</span><span class="sxs-lookup"><span data-stu-id="52cfb-103">Use this page to recycle the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Error Logs.</span></span> <span data-ttu-id="52cfb-104">Il riciclo dei log chiude il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e avvia un nuovo registro errori senza riavviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="52cfb-104">Recycling the log closes the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log and starts a new error log without restarting the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="52cfb-105">Si noti che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantiene gli ultimi nove log degli errori.</span><span class="sxs-lookup"><span data-stu-id="52cfb-105">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent maintains the nine most recent error logs.</span></span> <span data-ttu-id="52cfb-106">Se esistono già nove log degli errori, il riciclo causa l'eliminazione del log degli errori meno recente da parte di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="52cfb-106">If there are already nine error logs present, recycling the error log causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to remove the oldest error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52cfb-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52cfb-107">See Also</span></span>  
 [<span data-ttu-id="52cfb-108">Log degli errori di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="52cfb-108">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
