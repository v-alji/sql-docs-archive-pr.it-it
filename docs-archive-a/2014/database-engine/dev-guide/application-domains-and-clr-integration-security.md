---
title: Domini applicazione e sicurezza dell'integrazione con CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- application domains [CLR integration]
ms.assetid: 54ee904e-e21a-4ee7-b4ad-a6f6f71bd473
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85d6e66b1d51cc9d7c5829b8e83c510bea750e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626254"
---
# <a name="application-domains-and-clr-integration-security"></a><span data-ttu-id="5b151-102">Domini applicazione e sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="5b151-102">Application Domains and CLR Integration Security</span></span>
  <span data-ttu-id="5b151-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono caricati gli assembly che appartengono allo stesso proprietario in un dominio applicazione comune.</span><span class="sxs-lookup"><span data-stu-id="5b151-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] loads assemblies belonging to the same owner in the same application domain.</span></span> <span data-ttu-id="5b151-104">Grazie a un set di assembly in esecuzione nello stesso dominio applicazione, gli assembly possono individuare altri assembly in fase di esecuzione utilizzando le API di reflection di .NET Framework o altri strumenti e possono effettuare una chiamata in tali assembly in modalità di associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="5b151-104">By virtue of a set of assemblies running in the same application domain, assemblies are able to discover each other at execution time using the.NET Framework reflection application programming interfaces or other means, and can call into them in late-bound fashion.</span></span> <span data-ttu-id="5b151-105">Poiché tali chiamate vengono effettuate verso assembly che appartengono allo stesso proprietario, le autorizzazioni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per queste chiamate non vengono controllate.</span><span class="sxs-lookup"><span data-stu-id="5b151-105">Because such calls are occurring against assemblies belonging to the same owner, there are no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions checked for these calls.</span></span> <span data-ttu-id="5b151-106">Lo schema di posizione degli assembly nei domini applicazione è stato progettato principalmente per realizzare obiettivi di scalabilità, sicurezza e isolamento e potrebbe cambiare nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="5b151-106">The placement scheme of assemblies in application domains is designed primarily to achieve scalability, security, and isolation goals, and can potentially change in future releases.</span></span> <span data-ttu-id="5b151-107">Di conseguenza è consigliabile non basarsi sui meccanismi di associazione tardiva per individuare gli assembly nello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="5b151-107">Hence, you should not rely on finding assemblies in the same application domain through late-bound mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b151-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b151-108">See Also</span></span>  
 [<span data-ttu-id="5b151-109">Sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="5b151-109">CLR Integration Security</span></span>](../../relational-databases/clr-integration/security/clr-integration-security.md)  
  
  
