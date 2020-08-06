---
title: Aumentare o disabilitare l'opzione blocked process threshold | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 71db8ef6-341b-4465-99db-5c63e48d4c7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a7a90aea3fa8fb4d9c423cea1ec6008b01cde883
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624685"
---
# <a name="increase-or-disable-blocked-process-threshold"></a><span data-ttu-id="58d84-102">Aumento o disabilitazione dell'opzione blocked process threshold</span><span class="sxs-lookup"><span data-stu-id="58d84-102">Increase or Disable Blocked Process Threshold</span></span>
  <span data-ttu-id="58d84-103">Queste regole consentono di controllare che l'opzione blocked process threshold sia impostata su 0, o disabilitata, o su un valore maggiore o uguale a 5 (secondi).</span><span class="sxs-lookup"><span data-stu-id="58d84-103">This rules checks that the blocked process threshold option is set to 0 (disabled) or set to a value higher than or equal to 5 (seconds).</span></span> <span data-ttu-id="58d84-104">L'impostazione dell'opzione blocked process threshold su un valore compreso tra 1 e 4 comporta l'esecuzione continua del monitoraggio deadlock.</span><span class="sxs-lookup"><span data-stu-id="58d84-104">Setting the blocked process threshold option to a value from 1 to 4 can cause the deadlock monitor to run constantly.</span></span> <span data-ttu-id="58d84-105">È consigliabile utilizzare i valori compresi tra 1 e 4 solo per la risoluzione dei problemi e mai a lungo termine o in un ambiente di produzione senza l'assistenza del Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58d84-105">Values 1 to 4 should only be used for troubleshooting, and never long term or in a production environment without the assistance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="58d84-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="58d84-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="58d84-107">Per risolvere questo problema, impostare l'opzione blocked process threshold su un valore maggiore o uguale a 5 oppure su 0 per disabilitarla.</span><span class="sxs-lookup"><span data-stu-id="58d84-107">To resolve this problem, set the blocked process threshold option to a value of 5 (seconds) or higher, or disable blocked process threshold by setting the value to 0.</span></span> <span data-ttu-id="58d84-108">Per impostare l'opzione su un valore di `5` secondi, eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="58d84-108">To set the blocked process threshold to a value of `5` seconds, execute the following statement:</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 5 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="58d84-109">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="58d84-109">For More Information</span></span>  
 [<span data-ttu-id="58d84-110">Opzione di configurazione del server blocked process threshold</span><span class="sxs-lookup"><span data-stu-id="58d84-110">blocked process threshold Server Configuration Option</span></span>](../../database-engine/configure-windows/blocked-process-threshold-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="58d84-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58d84-111">See Also</span></span>  
 [<span data-ttu-id="58d84-112">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="58d84-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
