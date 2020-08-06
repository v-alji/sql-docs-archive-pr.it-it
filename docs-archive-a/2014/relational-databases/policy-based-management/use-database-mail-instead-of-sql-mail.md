---
title: Usare Posta elettronica database anziché SQL Mail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b08df7be-d8be-4184-a661-38ec0ac85cd1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a6a957b65975645bdeb9f55faee4e650b53718b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626692"
---
# <a name="use-database-mail-instead-of-sql-mail"></a><span data-ttu-id="b8145-102">Utilizzo di Posta elettronica database anziché di SQL Mail</span><span class="sxs-lookup"><span data-stu-id="b8145-102">Use Database Mail Instead of SQL Mail</span></span>
  <span data-ttu-id="b8145-103">Questa regola consente di controllare la vista del catalogo sys.configurations per determinare se l'opzione di configurazione SQL Mail XPS per l'intero server è impostata su ON.</span><span class="sxs-lookup"><span data-stu-id="b8145-103">This rule checks the sys.configurations catalog view to determine whether the SQL Mail XPs server-wide configuration option is set to ON.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b8145-104">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="b8145-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b8145-105">SQL Mail verrà rimosso in una delle versioni future di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8145-105">SQL Mail will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b8145-106">Evitare di usare questa funzionalità in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui è attualmente implementata.</span><span class="sxs-lookup"><span data-stu-id="b8145-106">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="b8145-107">Per inviare messaggi, utilizzare Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="b8145-107">To send mail, use Database Mail.</span></span>  
  
 <span data-ttu-id="b8145-108">SQL Mail viene eseguito in-process nel servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8145-108">SQL Mail runs in-process to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="b8145-109">Se l'esecuzione di SQL Mail si interrompe, anche il server diventa inattivo.</span><span class="sxs-lookup"><span data-stu-id="b8145-109">If SQL Mail goes down, so does the server.</span></span> <span data-ttu-id="b8145-110">Posta elettronica database viene eseguito in un processo distinto di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è scalabile e non richiede l'installazione di componenti client MAPI estesi nel server di produzione.</span><span class="sxs-lookup"><span data-stu-id="b8145-110">Database Mail runs outside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a separate process, is scalable, and does not require Extended MAPI client components to be installed on the production server.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b8145-111">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b8145-111">For More Information</span></span>  
 [<span data-ttu-id="b8145-112">Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="b8145-112">Database Mail</span></span>](../database-mail/database-mail.md)  
  
## <a name="see-also"></a><span data-ttu-id="b8145-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8145-113">See Also</span></span>  
 [<span data-ttu-id="b8145-114">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="b8145-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
